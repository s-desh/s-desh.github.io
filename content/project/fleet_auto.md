---
title: "Fleet Autonomy for Lely Discovery Collector"
# author: "Francesco"
# authorAvatarPath: "/avatar.jpeg"
date: "2024-06-27"
summary: "at TU Delft"
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
This was a project for the Multidisciplinary course at TU Delft, delivered by our team. The client problem was inspired by the Lely Discovery Collector barn-cleaning robot.

**Problem**  
Automate barn cleaning with reliable **localization**, **obstacle avoidance** (cows, humans, walls), and **multi-robot coordination**, reducing user burden for route planning and enabling cooperation between multiple robots.

**Contributions**  
- **Two-phase workflow:** Developed a system with a single **mapping** robot for map generation followed by coverage using all robots that use local planners to avoid dynamic obstacles.

- **Central planner (resource-aware):** Formulates a routing/coverage problem. Implemented in MiniZinc and solved with OR-Tools CP-SAT for faster valid/optimal solutions.

- **Robot stack (ROS):** `navigator` node follows global paths via **move_base**, `mapping_node` launches **slam_toolbox**, `communications_node` bridges ROS↔︎server over **MQTT** for coordination between multiple robots.

- **Interfaces:** Developed desktop planning UI to define waypoints/resources and visualize maps/states, a mobile GUI for monitoring, teleop, and E-stop.

**Results**  
- **Core wins:** Central planner↔︎robot comms established, **resource-aware route planning**, **reactive local planning** around dynamic obstacles, **robust localization** with LiDAR and usable UIs.
 
- **Perception:** 2D→3D target localization mean error ≈ **±2 cm** (passed).

**Languages and tools used:** ROS (move_base, slam_toolbox), C++, Python, MQTT, pygame, NumPy.

*My contributions were primarily designing and implementing the behavior architecture that included integrating mapping, obstacle detection and navigation with a state machine. This project was a good lesson on system design with multiple robots involved.*
