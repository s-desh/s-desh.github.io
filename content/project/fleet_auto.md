---
title: "Fleet Autonomy for Lely Discovery Collector"
# author: "Francesco"
# authorAvatarPath: "/avatar.jpeg"
date: "2024-06-27"
summary: "Controlling a fleet of mobile manipulators for area coverage and manure detection."
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

**Overview**  
The goal was to automate barn cleaning with reliable **localization**, **obstacle avoidance** (cows, humans, walls), and **multi-robot coordination**, for maximum coverage and manure detection.

**Contributions**  
- Developed a system with a single exploration and mapping robot for map generation followed by coverage using all robots that use local planners to avoid dynamic obstacles.

- A central planner formulates a routing/coverage problem. Implemented in MiniZinc and solved with OR-Tools CP-SAT for faster valid/optimal solutions.

- The implemented ROS stack uses, `navigator` node to follow global paths via **move_base**, `mapping_node` to launch **slam_toolbox**, `communications_node` bridging ROS and local server over **MQTT** for coordination between multiple robots.

- Developed desktop planning UI to define waypoints/resources and visualize maps/states, a mobile GUI for monitoring, teleop, and E-stop.

**Results**  

- Successfully implemented and coordinated 3 mobile manipulators to navigate a barn with **resource-aware route planning**, **reactive local planning** around dynamic obstacles and robust localization with LiDAR.

- Awarded the most robust solution.

**Languages and tools used:** ROS (move_base, slam_toolbox), C++, Python, MQTT, pygame, NumPy.

*My contributions were, designing and implementing the behavior architecture that included integrating mapping, obstacle detection and navigation with a state machine.*
