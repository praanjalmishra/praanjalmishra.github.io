---
title: "Multi-Camera 3D Human Pose & Body Model Reconstruction Pipeline"
excerpt: "Multi-view RGB/IR pipeline that reconstructs 3D body pose and SMPL-X shape for clinical gait research. SCAI Lab × AIT Lab, ETH Zürich, 2026."
collection: portfolio
---

**SCAI Lab × AIT Lab, ETH Zürich** · Jan 2026 – Aug 2026

* Built a multi-view perception pipeline that reconstructs 3D body pose and shape from synchronized RGB/IR stereo point clouds. Stages: camera calibration, 2D keypoint detection, multi-view triangulation, and SMPL-X mesh fitting, with ICP-based scan-to-mesh validation.
* Developed a segmentation-driven subject isolation stage (instance segmentation → cross-view mask matching → SAM2-guided refinement) so body models fit reliably in cluttered clinical scenes with several people.
* Engineered scalable batch workflows to run the pipeline reproducibly over large clinical recordings covering many subjects and sessions.
* Built a real-time visualizer: a FastAPI backend serves fitted gait body models and ground-reaction-force (GRF) data, time-synchronized, to a web frontend for biomechanical review.
