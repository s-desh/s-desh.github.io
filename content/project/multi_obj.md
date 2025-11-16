---
title: "Multi-object tracking"
# author: "Francesco"
# authorAvatarPath: "/avatar.jpeg"
date: "2024-01-30"
summary: "Pedestrian tracking using LiDAR and camera sensors."
# description: "Master Thesis"
# toc: true
# readTime: true
autonumber: true
math: true
tags: ["learning", "control", "aerial-robotics"]
showTags: false
hideBackToTop: false
fediverse: "@username@instance.url"
---


**Problem**  
Track pedestrians on the ground plane (BEV 2D) from a moving vehicle using multi-sensor inputs (camera, LiDAR). The goal was to produce stable pedestrian trajectories over time despite noisy detections, occlusions, and ego-motion.

**Contributions**
- Designed a ground-plane projection method that uses the bottom-midpoint of 2D boxes, calibrated extrinsics, and ego pose to obtain reliable pedestrian footpoints in BEV.

- Implemented and tuned a constant-velocity Kalman filter with dataset-matched process and measurement covariances for stable trajectory estimation.

- Added a pragmatic pre/post-processing stack with NMS, ~35 m range cutoff, confidence thresholds, and outlier filtering, and evaluated with HOTA to diagnose that detector quality is the primary performance bottleneck.

**Result**  
Achieved stable BEV trajectories on cleaner sequences with consistently high association quality and minimal ID switches.

**Languages and tools used:** Python, Open3D

*Hail the Kalman filter.*
