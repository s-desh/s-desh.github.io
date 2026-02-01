---
title: "Whole-body control of an aerial manipulator with reinforcement learning"
# author: "Francesco"
# authorAvatarPath: "/avatar.jpeg"
date: "2025-08-27"
summary: "Controlling a flying arm to perform pose-control and manipulation."
# description: "Master Thesis"
# toc: true
# readTime: true
autonumber: true
math: true
tags: ["learning", "control", "aerial-robotics"]
showTags: false
hideBackToTop: false
fediverse: "@username@instance.url"
image: "/images/osprey_flying.png"
---
This was my master thesis (MSc Robotics) project spanning 9 months. Click [here](https://repository.tudelft.nl/record/uuid:c4d15d40-3b3e-463b-894f-f99955419197) to access the full thesis document.

**Overview**   

Model-based methods of control need an accurate transition model and aren't robust to disturbances from the environment, especially when contact is involved. RL is a promising alternative, where the transition / dynamics model is learned by simulating interactions, including disturbances and model mismatch. The goal was to develop a control architecture using RL, to **control the end-effector pose of an aerial manipulator**, and demonstrating robustness via real-world experiments.

| Pose control with 140 g payload | Pushing a 590 g box |
|---|---|
| <img src="/images/real-world-140g.png" alt="Point cloud reconstruction" width="424"> | <img src="/images/object_push.png" alt="SDF from point cloud" width="360"> |

**Contributions**  

- Developed a hybrid control architecture, using a PPO-based trained policy for high level commands followed by traditional controllers for low-level tracking, balancing the tradeoff between control authority and sim-to-real transfer.

- Developed a high fidelity simulation environment in **NVIDIA Isaac Lab** for training, by modelling low-level controllers, drone physics, actuators behavior and filters.

- Developed a training regime that involved iterating on reward functions, observation/action space, utilizing techniques like domain randomization and curriculum learning, to successfully perform end-effector pose control with minimal sim-to-real gap.

- For hardware (powered by Raspberry Pi 5), wrote the control pipeline with ([Agilicious](https://github.com/uzh-rpg/agilicious)) flight controller for drone control (RL + Acceleration/Attitude + INDI) and interfaces with dynamixel actuators for arm control (RL + PID). The policy used ONNX runtime + C++ for inference.


**Results**  
- Successfully trained and deployed in real-world. ([Video](https://youtu.be/J3yqEvS4G_c)) 

- The policy is able to accurately (5.3 cm, 8.8 ° error) perform end-effector pose control achieving 6-DoF commanded poses, with inferece time of 0.18 ms.

- Can successfully track poses, while carrying payloads upto 140 g.

- Same policy can handle external disturbances and push a box weighing 590 g.


**Languages and tools used:** C++, Python, ROS, Isaac Sim, Gazebo

*Working on this was incredibly rewarding.*