---
title: "Robotics Intern"
# author: "Francesco"
# authorAvatarPath: "/avatar.jpeg"
date: "2024-06-27"
summary: "Mainblades (3 months)"
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
Mainblades does aircraft inspections autonomously with drones. During my internship, I built a library to represent the obstacle map with SDFs (Signed Distance Fields), this enables using gradient based path planning algorithms, generating smoother trajectories.

| Point cloud reconstruction | SDF from point cloud |
|---|---|
| <img src="/images/747400_model.png" alt="Point cloud reconstruction" width="360"> | <img src="/images/747400_sdf.png" alt="SDF from point cloud" width="360"> |



**Highlights**

- Built SDFGen to convert LiDAR point clouds and reconstructed aircraft models into SDFs (signed distance fields) maps.

- Developed sdfgen\_live (ROS) to integrate live LiDAR/rosbag data during flight and publish an SDF map for online planners while supporting initialization from prior maps for faster startup.

- Validated with static reconstructed aircraft models (B747/B777), flight rosbags, and hardware-in-the-loop on a DJI M300 and achieved 2 Hz SDF generation onboard.

**Languages and tools used:** C++, ROS