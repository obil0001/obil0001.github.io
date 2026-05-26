---
layout: post
title: Autonomous Surface Vessel
description: Systems engineering and autonomous navigation stack for a student competition autonomous boat, integrating mechanical design, embedded systems, and ROS-based perception and waypoint navigation
skills:
  - Systems Engineering
  - Autonomous Navigation (ROS)
  - Embedded Systems
  - Sensor Fusion
  - Structural & Hull Design
  - Electronics Integration

main-image: /asv_main.png
---

---
# Objectives
Design and build a fully autonomous surface vessel capable of navigating complex courses without human intervention, integrating mechanical resilience with real-time perception and autonomous decision-making to compete in a student engineering challenge.

## Outcomes and Contributions
I led the systems engineering lifecycle from concept through to final integration and competition deployment. The ASV successfully navigated autonomous waypoint missions, detected and avoided dynamic obstacles, and completed multiple competition runs. My contributions spanned the full stack: hull design and hydrodynamic optimization, embedded systems architecture, sensor fusion algorithms, and ROS autonomy software integration.

### Systems Architecture
The ASV operates as a distributed embedded system centered on a Jetson Nano compute module running a custom ROS navigation stack. The architecture isolates three primary domains: **Mechanical** (hull and propulsion), **Electronics** (power distribution, sensor interface, motor controllers), and **Software** (perception, planning, and control). 

We designed the hull for stability and hydrodynamic efficiency, using FEA to optimize the keel and ballast geometry for the expected payload and sea state conditions. The frame structure was fabricated from aluminum for weight efficiency and corrosion resistance. Propulsion is managed through a brushless thruster with integrated electronics, selected to provide sufficient authority for course correction across expected water conditions.

### Embedded Systems & Sensor Fusion
The vessel integrates a multi-modal sensor suite: GPS/RTK for global localization, an IMU for attitude estimation, a forward-facing LiDAR for obstacle detection and local mapping, and secondary camera systems for target recognition during competition tasks.

Sensor fusion is performed using an extended Kalman filter that combines GPS velocity, IMU angular rates, and compass heading to produce a robust state estimate even during GPS dropout periods common in competition venues. The LiDAR point cloud is processed in real-time to build a local occupancy grid, enabling reactive obstacle avoidance without pre-mapped knowledge of the course.

Power distribution is managed through a redundant battery architecture with integrated battery management systems (BMS) ensuring safe operation and voltage regulation across the 12V, 5V, and 3.3V rails needed by thrusters, compute, and sensors respectively.

### Autonomous Navigation Stack
Navigation is implemented using ROS Navigation framework running Dijkstra-based global path planning and Dynamic Window Approach (DWA) local trajectory planning. The mission planner accepts a sequence of GPS waypoints, then autonomously executes course corrections accounting for current drift and wind disturbance.

The autonomy layer interfaces with lower-level thruster controllers via CAN bus, converting planned linear and angular velocities into motor commands. During competition, the vessel ran fully autonomous for 15+ minute missions across courses requiring precision waypoint navigation and dynamic obstacle avoidance.

### Technical Highlights
- Real-time sensor fusion achieving 0.5m localization accuracy
- LiDAR-based obstacle detection operating at 10 Hz with <100ms latency
- ROS-based architecture enabling rapid mission re-configuration
- 4+ hour endurance with optimized battery thermal management
- Autonomous operation verified in both calm and moderately rough water conditions

{% include image-gallery.html images="/asv_render.png, /asv_electronics.png" height="400" %}
