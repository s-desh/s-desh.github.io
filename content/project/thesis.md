---
title: "Whole-body control of an aerial manipulator with reinforcement learning"
# author: "Francesco"
# authorAvatarPath: "/avatar.jpeg"
date: "2025-08-27"
summary: "Master Thesis"
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
This was my master thesis (MSc Robotics) project spanning 9 months. Click [here](https://repository.tudelft.nl/record/uuid:c4d15d40-3b3e-463b-894f-f99955419197) to access the full thesis document.

**Problem**   
In short, the objective was to control the end-effector of an aerial manipualtor for pose-control and object manipulation. Previous work does this in a decoupled manner (sperate control of drone and manipulator), while my thesis involved implementing whole-body control leveraging reinforcement learning. The case for RL is that it learns the dynamics and handles external disturbances with minimal compute (on deployment) without needing a model, while model-based controllers (MPC, MPPI) rely on the accuracy of dervied model, which can be a non-trivial task when contact is involved.

| Aerial Manipulator | Pose control carrying 140 g |
|---|---|
| <img src="/images/osprey_flying.png" alt="Point cloud reconstruction" width="424"> | <img src="/images/real-world-140g-posecontrol.png" alt="SDF from point cloud" width="600"> |


**Contributions**  

- **Train in simulation** (**Isaac Lab**): Built a simulation environment modelling filters, low-level controllers and the aerial manipulator to train for end-effector pose control.

- **Reward shaping**: Iterated on reward functions for position/orientation accuracy, plus penalties to smooth actions and limit magnitudes to reduce oscillations.

- **Control abstraction**: Built a hybrid control architecture with low-level controllers (attitude/acceleration + INDI for the drone, PID for the arm) to track actions from RL trained policy.

- **Deployment pipeline**: Developed a end-to-end pipeline, from training to deployment. All deployment code was written in C++ and ONNX runtime was used for policy execution on a Raspberry Pi 5. 

**Results**  
- Successfully trained and deployed in real-world. ([Video](https://www.youtube.com/watch?v=07ZGCPQzmG0)) 

- The policy is able to accurately (5.3 cm, 8.8 ° error) perform end-effector pose control achieving 6-DoF commanded poses, with inferece time of **0.18** ms.

- Can successfully track poses, while carrying payloads upto **140 g**.

- Same policy can handle external disturbances and push a box weighing 590 g.


**Languages and tools used:** C++, Python, ROS, Isaac Sim, Gazebo

*Working on this, I got to stretch my abilities, test my patience and perseverance, making it rewarding and incredibly satisfying, especially after successful real-world experiments.*