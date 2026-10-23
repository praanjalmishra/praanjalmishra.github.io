---
title: "Multi-Camera 3D Human Pose & Body Model Reconstruction Pipeline"
excerpt: "Multi-view RGB/IR pipeline that reconstructs 3D body pose and SMPL-X shape for clinical gait research. SCAI Lab × AIT Lab, ETH Zürich .<br/><video src='/images/projects/multicam-pose/mesh-reconstruction.mp4' style='aspect-ratio: 1280 / 720; width: 480px' autoplay loop muted playsinline preload='metadata'></video>"
collection: portfolio
header:
  teaser: projects/multicam-pose/capture-system.jpeg
---

**SCAI Lab × AIT Lab, ETH Zürich**


<figure>
  <img src="/images/projects/multicam-pose/capture-system.jpeg" alt="Multi-camera RGB/IR volumetric capture stage with camera rigs mounted around a green-screen room">
  <figcaption>AIT Lab's Multi-camera RGB/IR volumetric capture stage.</figcaption>
</figure>

## Problem
Clinical gait research needs accurate 3D body pose and shape for every subject and session. Markerless reconstruction is hard in real clinical recordings: several people share the scene and occlude each other, so a body model can easily latch onto the wrong person. The goal was to get reliable per-subject SMPL-X fits from the multi-camera stage, time-aligned with ground-reaction-force (GRF) measurements for biomechanical analysis.

## Pipeline
Input: synchronized RGB/IR stereo views and point clouds from the capture stage.

1. **Camera calibration**: intrinsics and extrinsics for all camera rigs.
2. **2D keypoint detection**: per-view body keypoints.
3. **Multi-view triangulation**: lift 2D detections to 3D keypoints.
4. **Subject isolation**: instance segmentation → cross-view mask matching → SAM2-guided refinement, so only the target subject reaches fitting in multi-person scenes.
5. **SMPL-X fitting**: fit the body model to the 3D keypoints and stereo point clouds, validated by ICP-based scan-to-mesh alignment.
6. **Batch processing**: scalable, reproducible workflows that run the full pipeline over large clinical recordings covering many subjects and sessions.

## Results
<figure class="half">
  <video src="/images/projects/multicam-pose/3d-keypoints.mp4" style="aspect-ratio: 1280 / 720" autoplay loop muted playsinline preload="metadata" aria-label="Triangulated 3D keypoint skeleton of a walking subject"></video>
  <video src="/images/projects/multicam-pose/mesh-reconstruction.mp4" style="aspect-ratio: 1280 / 720" autoplay loop muted playsinline preload="metadata" aria-label="Fitted SMPL-X mesh of the same walking subject"></video>
  <figcaption>Left: triangulated 3D keypoints. Right: fitted SMPL-X mesh for the same walking sequence.</figcaption>
</figure>

<!-- TODO: add one or two headline numbers, e.g. MPJPE vs. marker-based mocap, ICP scan-to-mesh error (mm), or number of subjects/sessions processed. -->

## Gait viewer with GRF sync
A real-time visualizer for biomechanical review: a FastAPI backend serves the fitted gait body models and GRF data, time-synchronized, to the viewer frontend. Left/right GRF curves and the pressure heatmap update with playback, so force events can be checked directly against the reconstructed motion.

<figure>
  <img src="/images/projects/multicam-pose/viewer-grf-1.png" alt="aitviewer showing 3D keypoints with left/right GRF plot and pressure heatmap panels">
  <figcaption>aitviewer interface: playback controls, left/right GRF plot (N) and plantar-pressure heatmap.</figcaption>
</figure>

<figure>
  <video src="/images/projects/multicam-pose/viewer-grf.mp4" poster="/images/projects/multicam-pose/viewer-grf-1.png" style="aspect-ratio: 1600 / 900" autoplay loop muted playsinline preload="metadata" aria-label="aitviewer playing a gait sequence of 3D keypoints in sync with left and right ground-reaction-force curves and a pressure heatmap"></video>
  <figcaption>aitviewer: 3D keypoints played back in sync with left/right GRF (N) and the pressure heatmap.</figcaption>
</figure>

