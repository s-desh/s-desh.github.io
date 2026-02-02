---
title: "Multi-agent search-and-rescue system"
# author: "Francesco"
# authorAvatarPath: "/avatar.jpeg"
date: "2024-01-18"
summary: "Multi-drone path planning with global / local planners for search and rescue simulation."
# description: "Master Thesis"
# toc: true
# readTime: true
autonumber: true
math: true
tags: ["learning", "control", "aerial-robotics"]
showTags: false
hideBackToTop: false
fediverse: "@username@instance.url"
image: "/images/rrt_local.png"
---

**Overview**  
This projects simulates rescue drones cooperatively scanning unknown forests. A BFS global planner divides the area amongst drones followed by RRT* local planner to avoid obstacles. We simulate 3 drones covering 900m² and 200 trees in PyBullet.


| 2D Local path plan with RRT* | 
|---|
| <img src="/images/rrt_local.png" alt="RRT generated path" width="300"> |


**Contributions**  

- Developed a simulation environment using PyBullet to simulate drones exploring and navigating a forest.

- A global planner, divides the area amongst the available drones, creates zones to explore and a local planner navigates around obstacles (trees), with RRT*.

- Compared planning times for increasing map sizes and found an exponential increase, motivating the use of smaller local maps.


**Languages and tools used:** Python, PyBullet
