# Awesome Human Data for Manipulation

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://makeapullrequest.com)

A curated list of **papers and datasets** on using **human data** (egocentric videos, VR/teleop, motion capture, hand pose, edited/robotized videos, etc.) to pretrain and scale **robot manipulation foundation models**.

---

## Contents

- [Taxonomy](#taxonomy)
- [Papers](#papers)
  - [Retargeting](#retargeting)
  - [Human Embodiment (Train w/o Retargeting)](#human-embodiment-train-wo-retargeting)
  - [Data Editing / Synthetic Retargeting](#data-editing--synthetic-retargeting)
  - [World Models / Predictive Representations](#world-models--predictive-representations)
- [Datasets](#datasets)
  - [Egocentric Human Manipulation Datasets](#egocentric-human-manipulation-datasets)
  - [Human → Robot “Robotized Video” Datasets](#human--robot-robotized-video-datasets)
  - [Human Embodiment / Hand-Action Supervision Datasets](#human-embodiment--hand-action-supervision-datasets)
  - [Humanoid Manipulation Benchmarks & Datasets](#humanoid-manipulation-benchmarks--datasets)

---

## Taxonomy

> Categories are **not mutually exclusive** — many works combine multiple.

### 1) Retargeting

Use estimated human motion (hands/wrists/body) and explicitly map it to a robot’s action space (IK / optimization / kinematic alignment).

**Typical outputs:** robot joint actions, end-effector poses, dexterous hand commands.

### 2) Human Embodiment (Train w/o Retargeting)

Treat humans as another “embodiment” during training by learning in a **human action space** (e.g., hand pose / fingertip positions / MANO) and transfer via modular adapters or shared representations.

**Key theme:** design an action representation that is meaningful for both humans and robots.

### 3) Data Editing / Synthetic Retargeting

Transform human videos into robot-compatible training data (compositing robot arms, inpainting humans away, pose-conditioned rendering, etc.) to reduce **visual** and/or **embodiment** gaps.

**Key theme:** keep scene/task semantics while making the visuals “robot-like”.

### 4) World Models / Predictive Representations

Pretrain models that predict future visual states (video diffusion / autoregressive video) and use these predictive representations to condition or unify policies.

**Key theme:** leverage human/robot videos to learn dynamics priors.

---

## Papers

> **Format:** **Title** (Year). *Authors/Venue* [[Paper]](…) [[Project]](…) [[Code]](…) [[Data]](…)

### Retargeting

- **EgoVLA: Learning Vision-Language-Action Models from Egocentric Human Videos** (2025).  
  [[arXiv]](https://arxiv.org/abs/2507.12440) [[Project]](https://rchalyang.github.io/EgoVLA/) [[Code]](https://github.com/RchalYang/EgoVLA_Release) [[Benchmark]](https://github.com/quincy-u/Ego_Humanoid_Manipulation_Benchmark)

- **MotionTrans: Human VR Data Enable Motion-Level Learning for Robotic Manipulation Policies** (2025).  
  [[arXiv]](https://arxiv.org/abs/2509.17759) [[Project]](https://motiontrans.github.io/) [[Code]](https://github.com/michaelyuancb/motiontrans) [[Dataset]](https://huggingface.co/datasets/michaelyuanqwq/motiontrans)

- **Humanoid Policy ~ Human Policy** (2025).  
  [[arXiv]](https://arxiv.org/abs/2503.13441) [[Project]](https://human-as-robot.github.io/) [[Code]](https://github.com/RogerQi/human-policy) [[Data]](https://huggingface.co/datasets/RogerQi/PH2D) [[Hardware]](https://github.com/RogerQi/human-policy?tab=readme-ov-file#human-data-collection-guide)

- **In-N-On: Scaling Egocentric manipulation with in-the-wild and on-task data** (2025).  
  [[arXiv]](https://arxiv.org/abs/2511.15704) [[Project]](https://xiongyicai.github.io/In-N-On/)

---

### Human Embodiment (Train w/o Retargeting)

- **Emergence of Human to Robot Transfer in Vision-Language-Action Models** (2025).  
  [[Paper]](https://www.physicalintelligence.company/download/human_to_robot.pdf) [[Blog]](https://www.physicalintelligence.company/research/human_to_robot)


- **EgoMimic: Scaling Imitation Learning via Egocentric Video** (2024).  
  [[arXiv]](https://arxiv.org/abs/2410.24221) [[Project]](https://egomimic.github.io/) [[Code]](https://github.com/SimarKareer/EgoMimic) [[Dataset]](https://huggingface.co/datasets/gatech/EgoMimic)

- **H-RDT: Human Manipulation Enhanced Bimanual Robotic Manipulation** (2025).  
  [[arXiv]](https://arxiv.org/abs/2507.23523) [[Project]](https://embodiedfoundation.github.io/hrdt) [[Code]](https://github.com/HongzheBi/H_RDT) [[Model]](https://huggingface.co/embodiedfoundation/H-RDT)

- **EgoDex: Learning Dexterous Manipulation from Large-Scale Egocentric Video** (2025).  
  [[arXiv]](https://arxiv.org/abs/2505.11709) [[Project]](https://embodiedfoundation.github.io/egodex) [[Code]](https://github.com/apple/ml-egodex)

---

### Data Editing / Synthetic Retargeting

- **H2R: A Human-to-Robot Data Augmentation for Robot Pre-training from Videos** (2025).  
  [[arXiv]](https://arxiv.org/abs/2505.11920) [[Dataset (H2R-1M)]](https://huggingface.co/datasets/yaoxu789/H2R-1M)

- **Phantom: Training Robots Without Robots Using Only Human Videos** (2025).  
  [[arXiv]](https://arxiv.org/abs/2503.00779) [[Project]](https://phantom-human-videos.github.io/) [[Code]](https://github.com/MarionLepert/phantom)

- **Masquerade: Learning from In-the-wild Human Videos using Data-Editing** (2025).  
  [[arXiv]](https://arxiv.org/abs/2508.09976) [[Project]](https://masquerade-robot.github.io/) [[Code]](https://github.com/MarionLepert/phantom)

---

### World Models / Predictive Representations

- **CLAP: Contrastive Latent Action Pretraining for Learning Vision-Language-Action Models from Human Videos** (2026).  
  [[arXiv]](https://arxiv.org/abs/2601.04061) [[Project]](https://lin-shan.com/CLAP/) *(Code: coming soon)*

- **Large Video Planner Enables Generalizable Robot Control** (2025).  
  [[arXiv]](https://arxiv.org/abs/2512.15840) [[Project]](https://www.boyuan.space/large-video-planner/) [[Code]](https://github.com/buoyancy99/large-video-planner) [[Hugging Face]](https://huggingface.co/KempnerInstituteAI/LVP)

- **Motus: A Unified Latent Action World Model** (2025).    
  [[arXiv]](https://arxiv.org/pdf/2512.13030) [[Project]](https://motus-robotics.github.io/motus)[[Code]](https://github.com/thu-ml/Motus)
  
- **World Models Can Leverage Human Videos for Dexterous Manipulation** (2025).  
  [[arXiv]](https://arxiv.org/pdf/2512.13644) [[Project]](https://raktimgg.github.io/dexwm/) 

- **Video Prediction Policy: A Generalist Robot Policy with Predictive Visual Representations** (2025).   
  [[Project]](https://video-prediction-policy.github.io/) [[Code]](https://github.com/roboterax/video-prediction-policy)

- **RynnVLA-002: A Unified Vision-Language-Action and World Model** (2025).  
  [[arXiv]](https://arxiv.org/abs/2511.17502) [[Code]](https://github.com/alibaba-damo-academy/RynnVLA-002) [[Model]](https://huggingface.co/Alibaba-DAMO-Academy/RynnVLA-002)

- **UniVLA: Learning to Act Anywhere with Task-Centric Latent Actions** (2025).  
  [[arXiv]](https://arxiv.org/abs/2505.06111) [[Code]](https://github.com/OpenDriveLab/UniVLA)

- **AgiBot World Colosseo:
  A Large-scale Manipulation Platform for Scalable and Intelligent Embodied Systems** (2025)  
  [[arXiv]](https://arxiv.org/abs/2503.06669) [[Code]](https://github.com/OpenDriveLab/AgiBot-World)

---

## Datasets

### Egocentric Human Manipulation Datasets

- **Ego4D** (Meta) — large-scale egocentric video.  
  [[Website]](https://ego4d-data.org/) [[GitHub]](https://github.com/facebookresearch/Ego4d)
- **EPIC-KITCHENS** — egocentric cooking activities and actions.  
  [[Website]](https://epic-kitchens.github.io/)
- **Ego-Exo4D** — paired egocentric + exocentric.  
  [[Website]](https://ego-exo4d-data.org/)
- **HoloAssist** — egocentric assistive tasks (AR/egocentric).  
  [[Website]](https://holoassist.github.io/)
- **HOT3D** — egocentric tasks with hand/object annotations (Meta).  
  [[GitHub]](https://github.com/facebookresearch/hot3d)
- **HOI4D** — 4D hand-object interaction dataset (includes egocentric views).  
  [[Website]](https://hoi4d.github.io/)
- **TACO** — tool-use/action-centric dataset.  
  [[Website]](https://taco2024.github.io/)

---

### Human → Robot “Robotized Video” Datasets

- **H2R-1M** — human videos with robot arms composited/rendered into scenes.  
  [[Dataset]](https://huggingface.co/datasets/yaoxu789/H2R-1M) [[Paper]](https://arxiv.org/abs/2505.11920)

---

### Human Embodiment / Hand-Action Supervision Datasets

- **EgoDex dataset** (paired with hand pose annotations; used for human-action pretraining).  
  [[Project]](https://embodiedfoundation.github.io/egodex) [[Code]](https://github.com/apple/ml-egodex)
- **EgoMimic sample datasets** (human + robot episodes in robomimic HDF5 format).  
  [[Dataset]](https://huggingface.co/datasets/gatech/EgoMimic) [[Paper]](https://arxiv.org/abs/2410.24221)
- **MotionTrans dataset** (VR human tasks + robot tasks for cotraining).  
  [[Dataset]](https://huggingface.co/datasets/michaelyuanqwq/motiontrans) [[Paper]](https://arxiv.org/abs/2509.17759)

---

### Humanoid Manipulation Benchmarks & Datasets

- **EgoVLA** (Isaac Lab simulation benchmark for humanoid bimanual manipulation).  
  [[Benchmark]](https://github.com/quincy-u/Ego_Humanoid_Manipulation_Benchmark) [[Paper]](https://arxiv.org/abs/2507.12440)

> If you have **real humanoid manipulation datasets** (e.g., Unitree / H1 / G1 + dexterous hands, teleop logs, whole-body manipulation), please open a PR and add them here.



