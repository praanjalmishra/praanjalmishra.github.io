---
title: "ArtiTwinSplat: Interactable Digital Twin Reconstruction from RGB-D Videos"
excerpt: "Master's thesis: photorealistic, interactable digital twins of articulated scenes with 3D Gaussian Splatting. CVG Lab, ETH Zürich, 2025–2026.<br/><video src='/images/projects/artitwinsplat/teaser.mp4' poster='/images/projects/artitwinsplat/teaser.jpg' style='aspect-ratio: 960 / 720; width: 480px' autoplay loop muted playsinline preload='metadata'></video>"
collection: portfolio
header:
  teaser: projects/artitwinsplat/teaser.jpg
---

**Master's Thesis, CVG Lab ETH Zürich** · [arXiv](https://arxiv.org/abs/2606.24628)

## Tech stack
3D Gaussian Splatting · Nerfstudio · PyTorch · RGB-D reconstruction · Camera localization

<figure>
  <video src="/images/projects/artitwinsplat/teaser.mp4" poster="/images/projects/artitwinsplat/teaser.jpg" style="aspect-ratio: 960 / 720" autoplay loop muted playsinline aria-label="ArtiTwinSplat teaser: reconstructed digital twin of an articulated scene"></video>
  <figcaption>Interactable digital twin reconstructed from a single RGB-D video.</figcaption>
</figure>

## Problem
Digital twins built with 3D Gaussian Splatting look photorealistic but are static: doors, drawers and other articulated parts can't be moved. Robots need digital twins where they can interact with, and which can be built from ordinary RGB-D captures.

## Overview
<figure>
  <img src="/images/projects/artitwinsplat/pipeline.png" alt="ArtiTwinSplat pipeline overview">
  <figcaption>Pipeline overview: RGB-D video → static and dynamic Gaussians → articulation estimation → interactable twin.</figcaption>
</figure>

* A photorealistic, interactable 3D scene reconstruction pipeline based on 3D Gaussian Splatting (3DGS), extended to dynamic articulated scenes via **disentangled background/object Gaussians**.
* **4D RANSAC-based mobility fitting** and an unsupervised RGB-D reconstruction framework to extract joint articulation priors for estimating object motion.
* An extension of **Nerfstudio's WebRTC-based viewer** that renders dynamic, articulated Gaussian Splat scenes live, so the digital twin can be viewed remotely in real time.

## Results
<figure>
  <video src="/images/projects/artitwinsplat/input.mp4" style="aspect-ratio: 1440 / 1080" autoplay loop muted playsinline aria-label="Input RGB-D capture"></video>
  <video src="/images/projects/artitwinsplat/result.mp4" style="aspect-ratio: 1920 / 2160" autoplay loop muted playsinline aria-label="Reconstructed articulated digital twin"></video>
  <figcaption>Top: input RGB-D capture. Bottom: reconstructed twin with the articulated part moved.</figcaption>
</figure>

<!-- TODO: add one or two headline numbers, e.g. PSNR/SSIM vs. baseline, or joint-axis error in degrees. -->

<!-- TODO: demo video. Upload to YouTube (unlisted is fine) and replace VIDEO_ID:
<div style="position:relative;padding-bottom:56.25%;height:0;overflow:hidden;">
  <iframe src="https://www.youtube.com/embed/VIDEO_ID" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" allowfullscreen></iframe>
</div>
-->

## My role
Master's thesis project and first author of the workshop paper. <!-- TODO: say which parts you designed and implemented yourself, and who supervised. -->



Presented as a lightning talk and poster at the **ICRA 2026 Workshop on AI-Driven Automation and Robotic System Integration with Digital Twins**, Vienna.
