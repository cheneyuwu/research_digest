---
name: research_digest
description: Runs a topic research digest — sweeps tracked papers, blogs, GitHub, and news, then summarizes what's new.
disable-model-invocation: true
user-invocable: true
---

# Research Digest Skill

Check every source, surface what's genuinely new, produce a concise digest. Completeness matters — nothing important should slip through.

## Invocation

- `/research_digest {profile}` — run that profile's digest (e.g. `/research_digest sensor_simulation`).
- `/research_digest {profile} {gcs_dir}` — also write the full digest as an HTML report to `{gcs_dir}` (e.g. `gs://my-bucket/digests/`) instead of printing it inline. See Step 7.
- `/research_digest` — list available profiles and ask which to run.

Each profile has its own source list (`sources.md`) and run state (`state.md`).

---

## Step 0: Setup

### Resolve profile

Each subdirectory under `profiles/` (except `_template`) is a topic profile containing
a `sources.md`.

- **Argument provided** (e.g., `/research_digest sensor_simulation`): use the first argument as the profile name. If no matching directory exists, list available profiles.
- **No argument, user present**: list profiles with a one-line description (from the `> Topics:` header in each `sources.md`) and ask which to run.
- **No argument, scheduled task**: check the scheduled task file for the profile argument; if none, run all profiles sequentially.

A second argument, if present, is a GCS directory (`gs://...`) — the output destination for the HTML report. Carry it through to Step 7.

### Load state

Look for `state.md` in the profile directory (`profiles/{profile}/state.md`). It tracks:
- **Last run date** — focus on items since then
- **Items already reported** — skip unless meaningfully updated (code release, new results, conference acceptance)
- **Date validation errors** — known false positives; never include again
- **Coverage gaps** — sources missed or low-signal last time; prioritize these

First run? No file needed — create it after the digest completes.

### Load sources

Read `profiles/{profile}/sources.md`. This is the single source of truth for this profile. If the user scopes further (e.g., "just world models"), narrow accordingly.

---

## Step 1: Build Checklist

Build an internal checklist — one line per source from the sources file. Only include sections that exist in this profile. Work through every item; don't print this to the user.

```
ARXIV QUERIES       (N queries)    [ ] ...
ARXIV RSS           (N categories) [ ] ...
INDUSTRY BLOGS      (N orgs)       [ ] ...
ACADEMIC LABS       (N labs)       [ ] ...
GITHUB LISTS        (N repos)      [ ] ...
GITHUB REPOS        (N orgs/users) [ ] ...
PAPERS WITH CODE    (N tasks)      [ ] ...
NEWS & NEWSLETTERS  (N sources)    [ ] ...
CONFERENCES         (N entries)    [ ] ...
KEY RESEARCHERS     (N people)     [ ] ...
X POSTS             (N accounts)   [ ] ...
```

---

## Step 2: Search All Sources

Work through the checklist section by section. Batch into parallel search groups for efficiency. Prefer direct URL/RSS access; fall back to web search.

### How to search each source type

| Section | Query pattern | Notes |
|---|---|---|
| ARXIV_QUERIES | `"[topic] arxiv [year]"` | Last 2–4 weeks |
| ARXIV_RSS_CATEGORIES | `"arxiv [category] [keywords] [year] new"` | Filter by tracked keywords |
| INDUSTRY_BLOGS | `"[Org] blog [year]"` | Past 2 weeks |
| ACADEMIC_LABS | `"[Lab name] [year] paper"` | — |
| GITHUB_AWESOME_LISTS | `"site:github.com [repo] [year]"` | — |
| GITHUB_REPOS | Fetch `https://api.github.com/orgs/{org}/repos?sort=created&direction=desc&per_page=15` | Returns JSON with `name`, `description`, `created_at`. Flag repos created since last run that match profile topics. For large orgs (NVIDIA, Google), sort-by-created is essential — sort-by-updated buries new small repos. High-signal — code releases often accompany paper drops. |
| PAPERS_WITH_CODE | `"papers with code [task] trending"` | — |
| NEWS_AND_NEWSLETTERS | Use search hint from sources file | — |
| CONFERENCE_PROCEEDINGS | `"[Conference] [year] accepted papers [topic]"` | — |
| KEY_RESEARCHERS | Fetch the arXiv author URL directly | Don't keyword-search by name — citation rank buries preprints. Read abstracts, not just titles. |
| X_POSTS | `"[Handle] X [topic] [month] [year]"` | Milestones, technical takes, strategic signals. Include 3–6 in digest. |

**Every source must be checked.** "Nothing new" is valid. If unreachable, note it.

---

## Step 3: Consolidate and Filter

### Deduplicate
Same paper from multiple sources → keep once with the best description.

### Validate dates — MANDATORY GATE

Every item must pass date verification. **Getting dates wrong erodes trust.**

1. **ArXiv papers**: Check the ID prefix (YYMM). Ambiguous IDs (e.g., `2503.XXXXX`) → fetch the abstract page and read the "Submitted" date. Cross-reference the state file's known errors.
2. **Blog/news items**: A blog's feature date ≠ the paper's publication date. Trace to primary source. Work older than 30 days is a **rediscovery** — omit or label as such.
3. **Updated papers**: Use the **original submission date** for bucketing. Mention updates only if the revision is substantial.
4. **No exceptions**: no item enters a time bucket without a verified primary-source date.

### Bucket by time

| Bucket | Window | Notes |
|---|---|---|
| Today | ≤48h | — |
| This Week | 3–7 days | Not in Today |
| This Month | 8–30 days | Only if noteworthy |
| Older | >30 days | Only if significant and not previously reported |

Based on **verified primary-source dates**, never discovery date.

### Sort and filter
- Within each bucket: papers → lab updates → company posts → news. More on-topic ranks higher.
- Cast a wide net — include borderline-relevant papers with a one-liner.
- Discard items with no connection to the profile's tracked topics.

---

## Step 4: Write the Digest

Organize by **time**, not topic. Use `#hashtag` tags (derived from the profile's domain) for scanning.

### Format

```markdown
# Research Digest: {Profile Name} — [Full Date]

## TL;DR
- [3–5 bullets: most important items a researcher needs to know NOW]

---

## Today
*(past ~48 hours)*

**[Title](link)**
*[Authors/Org] · [date] · [paper/blog/release/news]*
`#tag1` `#tag2` `#tag3`

2–3 sentences: what it does and why it matters.

---

## This Week
*(past 7 days, not in Today)*

[same format]

---

## This Month
*(past 30 days, not above — only if noteworthy)*

[same format]

---

## Upcoming
- **[Event]** · [date/location] · [link] — [why relevant]

---

## Notable X Posts
*(3–6 posts from key figures — milestones, technical takes, strategic signals)*

**[Name]** (@handle) — [link]
Brief summary and why it matters. Do not reproduce full post text.

---

## Observations
*(Optional — only if you spotted a real pattern. Skip if nothing substantive.)*

---

## New Sources Spotted
*[Output from Step 5]*

---

*Sources checked: [AUDIT checklist. Per section: ✓ = all searched, ✗ = some missed (name them), ⚠ = unreachable]*
```

### Rules

- **TL;DR**: 3–5 bullets max. New SOTA, major releases, significant moves.
- **Tags**: 2–4 per item, derived from the profile's domain.
- **Papers**: include generously. Mark significant ones with ⭐.
- **Upcoming**: always include. Pull from CONFERENCES + deadlines found during search.
- **Observations**: don't force it. Good: "three independent groups published X this week."
- **Omit empty sections** rather than writing placeholders.
- **Do not include**: "Topics covered", "Resource References", or "Academic Research Infrastructure" sections.
- **Tone**: lead with what the work does. "decouples spatial and appearance regression" > "improves performance."

---

## Step 5: Discover New Sources & Update Existing

### Discover

Run 3–5 exploratory searches for sources not yet tracked:
- New companies/startups in the domain
- First/senior authors of hot papers from this run
- New labs, newsletters, substacks, awesome-lists

Assess: will it produce relevant content **regularly** (not a one-off)?

### Update existing

Review entries against what you observed. Update drifted metadata (research focus, affiliations, topic lists, URLs). Edit the sources file directly and note changes in the digest.

### Output

```markdown
## New Sources Spotted
*Potential additions — added automatically unless flagged.*

| Type | Name | URL | Why |
|---|---|---|---|
| researcher | [Name] | [URL] | [reason] |
```

If genuinely strong, add to the sources file directly. If nothing new: `*No new sources identified this run.*`

---

## Step 6: Update State

Update the state file (`profiles/{profile}/state.md`) so the next run picks up where this one left off. First run? Create it now.

**Record:**
- New run date.
- Items reported this run (so they're skipped next time unless meaningfully updated).
- Any date errors caught this run (known false positives to never include again).
- Coverage notes — sources missed, unreachable, or low-signal — to prioritize next run.

**Clear obsolete entries** — the state file must not grow unbounded:
- Drop reported-item entries older than the longest lookback window (>30 days); they'll never resurface in a bucket, so tracking them is dead weight.
- Remove coverage gaps that were resolved this run.
- Delete date-error and false-positive entries that no longer correspond to anything in the active sources.
- Reconcile against the sources file: drop state tied to sources that were removed.

---

## Step 7: Deliver

**If a GCS directory was provided** (second invocation argument):
1. Render the full digest (the Markdown from Step 4) into a standalone, self-contained HTML file (inline CSS, no external assets) named `research_digest_{profile}_{YYYYMMDD}.html`.
2. Upload it to the GCS directory: `gcloud storage cp <file> {gcs_dir}/`.
3. Output to the CLI **the TL;DR + Today sections only, formatted as Slack `mrkdwn`** — this short excerpt is typically pasted straight into Slack — followed by a Slack-formatted link to the full report. Rewrite the `gs://{bucket}/{path}` destination to `https://storage.cloud.google.com/{bucket}/{path}` (this host requires Google sign-in) and present it as `<https://storage.cloud.google.com/{bucket}/{path}|View full report>`.

   Slack `mrkdwn` differs from Markdown — convert as you emit those two sections:
   - Links: `<https://url|text>`, not `[text](url)`.
   - Bold: `*text*` (single asterisks); italic: `_text_`.
   - No `#`/`##` headings (use a bold, optionally emoji-led line); no `---` rules; no tables.
   - Bullets start with `•`; keep `#tags` in backticks.

**Otherwise** (no GCS directory):
1. Print the full digest directly to CLI output in **standard Markdown** (exactly the format defined in Step 4).
