---
title: "ROS 2 Real-Time Perception-to-Control for Non-Holonomic Wheelchairs"
excerpt: "Dual-LiDAR perception, FAST-LIO state estimation and reactive crowd navigation for powered wheelchairs on NVIDIA Jetson. SCAI Lab, ETH Zürich, 2025."
collection: portfolio
header:
  teaser: projects/wheelchair-autonomy/pipeline.png
---

**SCAI Lab, ETH Zürich** · [GitHub](https://github.com/SCAI-Lab/rds-ros2/tree/ros2-port)

## Problem
A powered wheelchair moving through crowds has to perceive people around it and react to them in real time, on embedded hardware, while respecting non-holonomic kinematics: it can’t move sideways. Collision avoidance has to be safe for the occupant and still leave room for them to stay in control.

## Overview
<figure>
  <img src="/images/projects/wheelchair-autonomy/pipeline.png" alt="Pipeline diagram: 2x Livox MID360 LiDAR and IMU feed a PC merger node and FAST-LIO-MULTI; static obstacle cloud and M-Detector dynamic tracks feed the RDS planner, which corrects the user's joystick command and sends it to the WHILL driver">
  <figcaption>Perception and autonomy stack on an NVIDIA Jetson: 2× Livox MID360 + IMU → point-cloud merger and FAST-LIO-MULTI → static obstacle cloud and M-Detector dynamic tracks → RDS planner corrects the user's joystick command → WHILL driver.</figcaption>
</figure>

1. **Sensing**: Two Livox MID-360 LiDARs (360°, built-in IMU) on a WHILL wheelchair with an NVIDIA Jetson.
2. **State estimation**: FAST-LIO-MULTI fuses IMU and LiDAR data for real-time odometry.
3. **Point-cloud preprocessing**: pc_utils converts, filters, and merges both LiDAR clouds into one obstacle cloud, removing the wheelchair's body.
4. **Pedestrian detection**: M-detector tracks moving agents (position, radius, velocity) from raw Livox data.
5. **Shared-control collision avoidance**: RDS uses an RVO2-based planner to adjust joystick commands into the nearest collision-free velocity, published on /cmd_vel at ~10 Hz.
6. **Motor control**: pywhill_ros sends /cmd_vel to the WHILL motors over serial, with systemd handling automatic startup.

<!-- TODO: add one or two headline numbers, e.g. end-to-end latency on Jetson, control-loop rate, or number of collision-free runs in crowd tests. -->

<!-- TODO: on-vehicle demo video (mp4 in images/projects/wheelchair-autonomy/ or a YouTube embed). -->

