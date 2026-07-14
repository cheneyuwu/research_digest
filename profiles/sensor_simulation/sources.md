# Research Digest — Source List
> Topics: Autonomous Driving · Sensor Simulation · Scene Reconstruction · World Modeling
>
> **To add a source:** find the right section, copy an existing row, fill in the fields.
> Each row uses pipe-delimited format: `Label | URL-or-query | Notes`

---

## SECTION: ARXIV_QUERIES
> Search queries for recent arXiv papers.
> Format: `Topic Label | search query string | field hint`

Gaussian Splatting + Driving          | gaussian splatting autonomous driving          | abs
Scene Reconstruction + Driving        | scene reconstruction autonomous driving        | abs
Sensor Simulation (Neural)            | sensor simulation autonomous driving neural     | abs
World Models for Driving              | world model autonomous driving                  | abs
NeRF + LiDAR Simulation               | nerf lidar simulation driving                   | abs
4D Gaussian Splatting + Driving       | 4D gaussian splatting driving                   | abs
Neural Radiance Field + Driving       | neural radiance field driving simulation        | abs
Video Generation + Driving            | video generation driving world model            | abs
Occupancy Prediction + Driving        | occupancy prediction autonomous driving         | abs
Diffusion Models + Simulation         | diffusion model autonomous driving simulation   | abs

---

## SECTION: ARXIV_RSS_CATEGORIES
> arXiv categories to check for relevant new submissions.
> Format: `Category | RSS URL | What to look for`

cs.CV  (Computer Vision)      | https://arxiv.org/rss/cs.CV   | Scene reconstruction, novel view synthesis, sensor sim, video gen
cs.RO  (Robotics)             | https://arxiv.org/rss/cs.RO   | AV planning, sensor fusion, closed-loop driving, sim-to-real
cs.AI                         | https://arxiv.org/rss/cs.AI   | World models, foundation models for driving
cs.LG  (Machine Learning)     | https://arxiv.org/rss/cs.LG   | Generative models, diffusion, neural sim
eess.SP (Signal Processing)   | https://arxiv.org/rss/eess.SP | LiDAR signal modeling, radar simulation

---

## SECTION: INDUSTRY_BLOGS
> Company/org blogs to check for recent posts.
> Format: `Org Name | Blog URL | RSS URL (or NONE) | Topics to watch`

Waymo          | https://waymo.com/blog/                                        | https://waymo.com/blog/rss.xml                        | World model, sensor sim, deployment
Wayve          | https://wayve.ai/thinking/                                     | NONE                                                  | GAIA world models, E2E driving
NVIDIA         | https://developer.nvidia.com/blog/tag/autonomous-vehicles/     | NONE                                                  | Cosmos, DRIVE platform, sensor sim
NVIDIA AI Blog | https://blogs.nvidia.com/blog/category/autonomous-vehicles/    | NONE                                                  | Product launches, Cosmos updates
NVIDIA Research| https://research.nvidia.com/publications                       | NONE                                                  | Papers on scene generation, sensor sim
Waabi          | https://waabi.ai/blog/                                         | NONE                                                  | World sim, sensor generation
Tesla AI       | https://www.tesla.com/blog/category/autopilot                  | NONE                                                  | Vision-only, FSD, dojo
Mobileye       | https://www.mobileye.com/blog/driving-ai/                      | NONE                                                  | AV stack, sensor fusion, L3/L4
Zoox           | https://zoox.com/hadaept/                                      | NONE                                                  | Robotaxi deployment, sensor design
Google DeepMind| https://deepmind.google/discover/blog/                         | https://deepmind.google/discover/blog/rss.xml         | Genie world model, robotics, video gen
Meta AI (FAIR) | https://ai.meta.com/blog/                                      | https://ai.meta.com/blog/rss/                         | 3D reconstruction, video gen, embodied AI
Apple ML       | https://machinelearning.apple.com                              | https://machinelearning.apple.com/rss.xml             | Perception, 3D scene understanding
Microsoft Research | https://www.microsoft.com/en-us/research/research-area/autonomous-systems/ | NONE | AV simulation, perception
DeepRoute.ai   | https://www.deeproute.ai/en/news                              | NONE                                                  | VLA models, E2E driving, mass deployment
Applied Intuition | https://www.appliedintuition.com/blog                        | NONE                                                  | AV simulation platform, scenario gen, validation
Nuro               | https://www.nuro.ai/blog                                       | NONE                                                  | E2E driving, zero-shot autonomy, deployment
Motional           | https://motional.com/news                                      | NONE                                                  | Robotaxi deployment, IONIQ 5 fleet, Uber partnership
Hesai Technology   | https://www.hesaitech.com/news                                 | NONE                                                  | LiDAR hardware, 6D color sensing, SPAD-SoC, AV perception
Glydways           | https://www.glydways.com/                                      | NONE                                                  | Autonomous pod transit, dedicated guideways, urban mobility
XPENG              | https://www.xpeng.com/news                                     | NONE                                                  | VLA 2.0 production deployment, E2E driving, VW licensing, L4 robotaxi mass production (Guangzhou)
QCraft             | https://www.qcraft.ai                                          | NONE                                                  | Physical AI Model, World Model + RL, QPilot MAX, L4 robotaxi, mass OEM deployment
Baidu Apollo       | https://www.apollo.auto/news                                   | NONE                                                  | Apollo Go robotaxi, China L4 deployment, Wuhan/Beijing fleet, system reliability
Aurora Innovation  | https://aurora.tech/newsroom                                   | NONE                                                  | Aurora Driver, autonomous trucking, Volvo VAS / Hirschbach / PACCAR partners, Texas + Sun Belt
Kodiak AI          | https://kodiak.ai/news/                                        | NONE                                                  | Kodiak Driver, driverless trucking, West Texas commercial ops, logging/forestry, first intl. (Alberta)
Wayve press        | https://wayve.ai/press                                         | NONE                                                  | Wayve press releases (gov MoUs, Series E follow-ons, OEM partnerships)
bitsensing         | https://www.bitsensing.com                                     | NONE                                                  | 4D imaging radar (AIR4D), raw point cloud + Doppler, long-range AV perception
May Mobility        | https://maymobility.com/posts                                  | NONE                                                  | Gen 5 world-model-based autonomy, predictive world model, Uber deployment, ECARX partnership
Helm.ai            | https://www.helmai.com/news                                    | NONE                                                  | GenSim-3/VidGen-3 generative sensor sim, hardware-accurate artifacts, full HD 360° synthesis
Foretellix         | https://www.foretellix.com/blog                                | NONE                                                  | AV validation platform, NVIDIA Alpamayo integration, ODD coverage, synthetic scenario gen
Autobrains         | https://www.autobrains.ai/news                                 | NONE                                                  | Agentic AI L4, VinFast partnership, NVIDIA DRIVE Hyperion, unsupervised perception
Avride             | https://avride.ai/news                                         | NONE                                                  | 200+ Ioniq 5 robotaxi fleet, Uber Dallas/Austin, rapid Texas scaling
Verne              | https://www.verne.co/news                                      | NONE                                                  | Robotaxi operator, Europe's first commercial service (Zagreb), Pony.ai tech

---

## SECTION: ACADEMIC_LABS
> Research labs to check for recent publications/releases.
> Format: `Lab Name | URL | Affiliation | Research focus`

OpenDriveLab         | https://opendrivelab.com                     | Shanghai AI Lab    | End-to-end AD, world models, occupancy
Thinklab (SJTU)      | https://github.com/Thinklab-SJTU/Awesome-LLM4AD | Shanghai Jiao Tong | LLM/VLM for driving
Autonomous Vision Grp| https://github.com/autonomousvision           | U Tübingen         | 3D reconstruction, occupancy, NeRF, 3DGS
MARS Lab             | https://mars.engineering.umich.edu            | U Michigan         | Scene reconstruction, AV sim
Waabi Research       | https://waabi.ai/research/                   | Waabi / Toronto    | Sensor gen, world sim

---

## SECTION: GITHUB_AWESOME_LISTS
> Curated paper lists to check for newly added entries.
> Format: `List Name | GitHub URL | Main topic`

Awesome-World-Model (LMD0311)       | https://github.com/LMD0311/Awesome-World-Model                            | World models for AD & robotics
Awesome-World-Models (leofan90)     | https://github.com/leofan90/Awesome-World-Models                          | World models (video gen, embodied AI, AD)
World-Models-AD-Survey (HaoranZhu)  | https://github.com/HaoranZhuExplorer/World-Models-Autonomous-Driving-Latest-Survey | World models for AD
Awesome-LLM4AD (Thinklab-SJTU)      | https://github.com/Thinklab-SJTU/Awesome-LLM4AD                           | LLM/VLM/VLA/World Model for AD
End-to-end-AD (OpenDriveLab)        | https://github.com/OpenDriveLab/End-to-end-Autonomous-Driving             | E2E autonomous driving papers
CVPR2026-Papers-with-Code (amusi)   | https://github.com/amusi/CVPR2026-Papers-with-Code                        | CVPR 2026 papers tracker
Awesome-3D-Gaussian-Splatting       | https://github.com/MrNeRF/awesome-3D-gaussian-splatting                   | 3DGS methods and applications
Awesome-NeRF                        | https://github.com/awesome-NeRF/awesome-NeRF                              | NeRF papers and applications

---

## SECTION: GITHUB_REPOS
> GitHub orgs and users to monitor for new repositories.
> Flag new repos that match the profile's topics (sensor sim, 3DGS, world models, AD, etc.).
> Format: `Name | GitHub URL | What to look for`

NVIDIA Research (nv-tlabs) | https://github.com/nv-tlabs                | Highest-signal NVIDIA org — Fidler group, scene gen, neural sim, 3DGS, OmniDreams, asset generation
NVlabs                  | https://github.com/NVlabs                    | AlpaSim (AV sim), rcm (world model diffusion), nurec tools, trajdata — high-signal research code
NVIDIA (main)           | https://github.com/NVIDIA                    | Cosmos, flashdreams, nurec-skills, asset-harvester, DRIVE — noisy, check selectively
OpenDriveLab            | https://github.com/OpenDriveLab              | E2E driving, occupancy, world models, benchmarks, SimScale
Autonomous Vision (Geiger) | https://github.com/autonomousvision        | 3DGS, NeRF, scene reconstruction, AD planning, Bench2Drive
Waymo Research          | https://github.com/waymo-research            | Waymo open datasets, perception, world models — sparse, few public repos
Wayve                   | https://github.com/wayveai                   | GAIA world models, E2E driving, embodied AI
Applied Intuition       | https://github.com/applied-intuition         | AV simulation platform, scenario tools
Nuro                    | https://github.com/nuro-ai                   | E2E driving, autonomy stack

---

## SECTION: PAPERS_WITH_CODE
> Task pages to check for trending papers.
> Format: `Task Name | URL`

Autonomous Driving      | https://paperswithcode.com/task/autonomous-driving
Novel View Synthesis    | https://paperswithcode.com/task/novel-view-synthesis
3D Scene Reconstruction | https://paperswithcode.com/task/3d-reconstruction
Scene Generation        | https://paperswithcode.com/task/scene-generation
Video Generation        | https://paperswithcode.com/task/video-generation
LiDAR Object Detection  | https://paperswithcode.com/task/lidar-object-detection

---

## SECTION: NEWS_AND_NEWSLETTERS
> News sites to search for recent AV/simulation/ML coverage.
> Format: `Source Name | URL | Search hint`

Self Drive News     | https://selfdrivenews.com         | autonomous driving simulation sensor
The Robot Report    | https://www.therobotreport.com    | autonomous vehicle simulation
Synced Review       | https://syncedreview.com          | autonomous driving world model gaussian splatting
Hugging Face Papers | https://huggingface.co/papers     | autonomous driving scene reconstruction sensor simulation

---

## SECTION: CONFERENCE_PROCEEDINGS
> Conferences to check for accepted papers and preprints.
> Format: `Conference | URL | Notes`

CVPR 2026              | https://cvpr.thecvf.com/Conferences/2026        | Jun 3–7 Denver; workshops Jun 3-4, main Jun 5-7
CVPR Open Access       | https://openaccess.thecvf.com                   | All prior CVPR papers, free
NeurIPS 2026           | https://neurips.cc                              | Dec 2026; monitor OpenReview submissions
ICRA 2026              | https://2026.ieee-icra.org                      | Jun 1–5 Vienna; robotics + AV
OpenReview             | https://openreview.net                          | NeurIPS/ICLR submissions and reviews
WAD Workshop (CVPR)    | https://cvpr2026.wad.vision/                    | Workshop on Autonomous Driving
SAD Workshop (CVPR)    | https://agents4ad.github.io/                    | Simulation for Autonomous Driving workshop
AUTOPILOT Workshop     | https://www.autopilot-cvpr.net/                 | AD & VLMs, open-world perception; Elluswamy keynote
DriveX Workshop        | https://drivex-workshop.github.io/cvpr2026/      | Foundation models for cooperative AD, V2X
WDFM-EAI Workshop     | https://wdfm-eai.github.io/CVPR26/              | World and Driving Foundation Models — directly on-topic
4D World Models Wkshp  | https://4d-world-models.github.io/               | Bridging generation and reconstruction; Brown University
VideoWorldModel Wkshp  | https://videoworldmodel-workshop.github.io/      | Video world models for physical AI

---

## SECTION: KEY_RESEARCHERS
> Leading researchers to track for recent papers. arXiv URL is the primary fetch target during runs — chronological, catches fresh preprints. Scholar URL is for reference.
> Format: `Name | Affiliation | Scholar URL | arXiv author URL | Research focus`

Marco Pavone        | Stanford / NVIDIA            | https://scholar.google.com/citations?user=RhOpyXcAAAAJ | https://arxiv.org/search/?searchtype=author&query=Marco+Pavone&size=50        | AV planning, decision-making, world models, sim
Sanja Fidler        | U Toronto / NVIDIA           | https://scholar.google.com/citations?user=CUlqK5EAAAAJ | https://arxiv.org/search/?searchtype=author&query=Sanja+Fidler&size=50        | 3D scene generation, neural sim, Cosmos, NeRF
Raquel Urtasun      | U Toronto / Waabi            | https://scholar.google.com/citations?user=jyxO2akAAAAJ | https://arxiv.org/search/?searchtype=author&query=Raquel+Urtasun&size=50      | Sensor sim, world sim, E2E driving, UniSim
Vladlen Koltun      | Apple                        | https://scholar.google.com/citations?user=nv7ovAIAAAAJ | https://arxiv.org/search/?searchtype=author&query=Vladlen+Koltun&size=50      | Dense 3D reconstruction, scene understanding
Philipp Krahenbuhl  | UT Austin / Apple            | https://scholar.google.com/citations?user=8lkFMDcAAAAJ | https://arxiv.org/search/?searchtype=author&query=Philipp+Krahenbuhl&size=50  | E2E driving, imitation learning, planning, world models, "Electric Sheep" mental imagery
Yue Wang            | USC                          | https://scholar.google.com/citations?user=APeO9LAAAAAJ | https://arxiv.org/search/?searchtype=author&query=Yue+Wang&size=50            | 3D perception, point clouds, LiDAR (common name — post-fetch affiliation filter required)
Hang Zhao           | Tsinghua / Shanghai AI Lab   | https://scholar.google.com/citations?user=DmahiOYAAAAJ | https://arxiv.org/search/?searchtype=author&query=Hang+Zhao&size=50           | World models, occupancy, BEV perception (common name — post-fetch affiliation filter required)
Boris Ivanovic      | Stanford / NVIDIA            | https://scholar.google.com/citations?user=bQHmVpoAAAAJ | https://arxiv.org/search/?searchtype=author&query=Boris+Ivanovic&size=50      | Trajectory prediction, diffusion planning, sim
Sergio Casas        | Waymo                        | https://scholar.google.com/citations?user=4wKIGfYAAAAJ | https://arxiv.org/search/?searchtype=author&query=Sergio+Casas&size=50        | Self-driving, sensor sim, motion forecasting (arXiv author search returns astrophysics — use Scholar)
Andreas Geiger      | U Tubingen / ETH             | https://scholar.google.com/citations?user=SrVnrPcAAAAJ | https://arxiv.org/search/?searchtype=author&query=Andreas+Geiger&size=50      | 3D vision, autonomous driving, NeRF, 3DGS
Kashyap Chitta      | U Tubingen (Geiger group)    | https://scholar.google.com/citations?user=mDFn5q4AAAAJ | https://arxiv.org/search/?searchtype=author&query=Kashyap+Chitta&size=50      | E2E driving, PlanT, foundation data infra (123D), CARLA benchmarks
Daniel Dauner       | U Tubingen (Geiger group)    | NONE                                                   | https://arxiv.org/search/?searchtype=author&query=Daniel+Dauner&size=50       | AV data infrastructure, multi-modal driving datasets (lead author 123D)
Frieda Rong         | Waabi                        | NONE                                                   | https://arxiv.org/search/?searchtype=author&query=Frieda+Rong&size=50         | NL-controllable scenario generation, scenario constraint solving (lead author 2605.06966)
Tianshi Cao         | NVIDIA / U Toronto           | NONE                                                   | https://arxiv.org/search/?searchtype=author&query=Tianshi+Cao&size=50         | Generative 3D world simulation, asset harvesting (lead author 2604.18468 Asset Harvester, co-lead Lyra 2.0)
Ze Yang             | Waabi                        | NONE                                                   | https://arxiv.org/search/?searchtype=author&query=Ze+Yang&size=50             | In-the-wild 3D latent diffusion, neural sim (lead author 2604.23010 GenAssets) — common name, post-fetch affiliation filter required
Haibao Yu           | HKU                          | NONE                                                   | https://arxiv.org/search/?searchtype=author&query=Haibao+Yu&size=50           | Feed-forward 4D Gaussian Splatting, urban reconstruction (lead author 2603.07552 ReconDrive)
Rajeev Yasarla      | Qualcomm AI Research         | NONE                                                   | https://arxiv.org/search/?searchtype=author&query=Rajeev+Yasarla&size=50      | VLA for AD, latent multi-agent simulation, E2E driving (lead author 2605.14201 MAPLE — SOTA Bench2Drive)
Yuzhou Huang        | (Chinese univ/industry — verify) | NONE                                               | https://arxiv.org/search/?searchtype=author&query=Yuzhou+Huang&size=50        | Unified streaming VLA for AD, first to beat expert humans on WOD-E2E (lead author 2605.12624 MindVLA-U1) — common name, post-fetch affiliation filter required
Naama Pearl         | Tübingen (Geiger group) / Meta | NONE                                                 | https://arxiv.org/search/?searchtype=author&query=Naama+Pearl&size=50         | Learned 3DGS optimization, meta-learning for scene reconstruction (lead author 2605.15760 Learn2Splat)
Andrea Bajcsy       | CMU (Robotics Institute)     | NONE                                                   | https://arxiv.org/search/?searchtype=author&query=Andrea+Bajcsy&size=50       | Robust policy evaluation, steering video world models toward plausible failures, safe autonomy (senior author 2606.00267 StressDream)

---

## SECTION: X_POSTS
> X/Twitter accounts of key AV/AI figures. Check for recent posts with industry signal — milestone announcements, strategic hints, technical commentary.
> Format: `Name | Role | X Handle | What to look for`

Andrej Karpathy     | Eureka Labs (ex-Tesla AI)    | @karpathy        | FSD commentary, AI/driving opinions, technical takes
Elon Musk           | Tesla CEO                    | @elonmusk        | FSD milestones, Cybercab/robotaxi updates, timeline claims
Ashok Elluswamy     | Tesla VP AI Software         | @aelluswamy      | FSD technical progress, upcoming releases, team milestones
Jensen Huang        | NVIDIA CEO                   | @Jensen_Huang    | Alpamayo, DRIVE platform, physical AI, partner announcements
Dmitri Dolgov       | Waymo co-CEO                 | @dmitri_dolgov   | Waymo operations milestones, expansion, safety data
Alex Kendall        | Wayve CEO                    | @alexgkendall    | Embodied AI, GAIA world models, Wayve partnerships
Jim Fan             | NVIDIA GEAR team lead        | @DrJimFan        | Physical AI, embodied agents, FSD/robotaxi commentary
Raquel Urtasun      | Waabi CEO                    | @RaquelUrtasun   | Waabi progress, generative AI for physical world, L4 trucking
