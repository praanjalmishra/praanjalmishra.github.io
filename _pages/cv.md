---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

[Download CV as PDF]({{ base_path }}/files/cv_pranjal_ETHz.pdf)

Education
======
* **M.Sc. in Computational Science & Engineering**, ETH Zürich, Sep 2023 – Aug 2026
  * Specialization: Robotics & Computer Vision
  * GPA: 5.4 / 6.0
* **B.Tech. in Metallurgical & Materials Engineering**, Indian Institute of Technology Roorkee, July 2017 – June 2021
  * Minor: Computer Science & Engineering
  * GPA: 8.8 / 10 (Rank 3)

Work experience
======
* **Aug 2024 – Aug 2026: Research Assistant (Robotic Systems)**
  * [SCAI Lab](https://scai.ethz.ch/), D-HEST, ETH Zürich, supervised by Dr. Diego Paez-Granados
  * Built and deployed real-time perception-to-control pipelines in ROS 2 (C++/Python) on NVIDIA Jetson edge hardware, including sensor calibration, multi-sensor fusion, and reproducible Docker-based deployment across robotic platforms
  * Contributed to [ROS4HC (ROS for Healthcare)](https://github.com/SCAI-Lab/ros4healthcare), an open-source framework that standardizes physiological/biological sensor integration into ROS 2
  * Led markerless motion capture and data processing for pediatric gait disorder research with the ETH AIT Lab, owning the multi-view 3D reconstruction pipeline and its clinical-scale data workflows

* **July 2021 – Aug 2023: Simulation Engineer, Research & Development**
  * [Sterlite Technologies Limited](https://www.stl.tech/), Aurangabad, India
  * Built finite-element multiphase flow and FSI models (COMSOL) to analyse failure modes in an industrial process
  * Validated models against production data and ran sensitivity studies to identify key process variables
  * Turned results into process changes with operations teams; the work contributed to two patents

Skills
======
* **Programming:** C/C++, Python, Bash, MATLAB
* **Robotics & Real-Time Systems:** ROS 1/2, Jetson embedded deployment, Docker, Gazebo, Isaac Sim, Unity
* **Perception & 3D Geometry:** RGB-D sensing, multi-view stereo, camera/sensor calibration, ICP, OpenCV, Open3D, PCL
* **Sensor Fusion & State Estimation:** Multi-LiDAR fusion, IMU-based state estimation, multi-sensor pipelines
* **ML Frameworks & Deployment:** PyTorch, TensorFlow, model quantization
* **Testing & Debugging:** Git, CI-style workflows, logging, profiling, system debugging
* **Web/API:** React, Dash, FastAPI, REST API integration

Projects
======
See the [Projects]({{ base_path }}/portfolio/) page.

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
