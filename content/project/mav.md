---
title: "Vision based obstacle avoidance for MAV"
# author: "Francesco"
# authorAvatarPath: "/avatar.jpeg"
date: "2024-03-20"
summary: "Bechmarking obstacle avoidance methods for Parrot Bepop drone."
# description: "Master Thesis"
# toc: true
# readTime: true
autonumber: true
math: true
tags: ["learning", "control", "aerial-robotics"]
showTags: false
hideBackToTop: false
fediverse: "@username@instance.url"
image: "/images/canny_edge.png"
---

**Overview**  
Enable autonomous obstacle avoidance for a Parrot Bebop MAV in TU Delft’s Cyberzoo using monocular vision under tight onboard compute and variable lighting/scene conditions. The system must pick safe headings and fly reliably around pillars, trees, carpets, and “mysterious” obstacles.

| Canny edge algorithm | Monodepth |
|---|---|
| <img src="/images/canny_edge.png" alt="Edge detection result" width="424"> | <img src="/images/monodepth.png" alt="Depth estimation" width="450"> |


**Contributions**

- Benchmarked monocular obstacle-avoidance methods - optic flow, edge detection, monocular depth and color segmentation on Parrot
Bebop drone.

- Implemented floor/obstacle segmentation with a simple state machine and achieved stable avoidance in controlled flights.

**Results**
- **Worked in practice:** The colour/floor method successfully avoided most Cyberzoo obstacles, while edge/optic-flow and ML/depth variants were constrained by sensitivity, data/compute, or deployment limits.

- **Limits & insights:** Obstacles sharing floor colour reduce detectability, flying lower leverages ground effect and improved reliability and overall compute cost is low for the colour method, enabling onboard execution.

**Languages and tools used:** C, Python

*In the end, the simplest method worked the best.*