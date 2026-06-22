---
source: chunks/wiki-Computer_vision-chunk-1.md
source_url: https://en.wikipedia.org/wiki/Computer_vision
---

## Computer Vision: Foundations, History, and Subdisciplines

Computer vision is the interdisciplinary field concerned with enabling computers to extract high-level understanding from digital images and video. It spans acquiring, processing, analyzing, and understanding visual data to produce numerical or symbolic information that can drive decisions and actions. The field sits at the intersection of AI, engineering, geometry, physics, and statistics.

## Key Concepts

- **Core goal**: Transform visual images into structured descriptions of the world that can elicit appropriate action — "disentangling symbolic information from image data"
- **Image data forms**: Video sequences, multi-camera views, 3D scanner output, LiDaR point clouds, medical imaging
- **Computer vision vs. machine vision**: Machine vision is a systems engineering discipline (factory automation context); the two terms have converged over time
- **Computer vision vs. digital image processing**: CV aims to extract 3D structure and achieve full scene understanding, not just process pixel data
- **Subdisciplines**: Scene reconstruction, object detection, event detection, activity recognition, video tracking, object recognition, 3D pose estimation, motion estimation, visual servoing, 3D scene modeling, image restoration

## Commands and Syntax

Not applicable — this is a conceptual overview page, not a tools/API reference.

## Relationships

- **Parent field**: Artificial intelligence — CV originated in AI labs in the 1960s as a stepping stone to robot intelligence
- **Foundational disciplines**: Geometry, physics, statistics, learning theory — all contribute models for interpreting image data
- **Overlapping fields**: Digital image processing (pixel-level operations), computer graphics (converged in the late 1990s with image-based rendering, morphing, stitching), photogrammetry (bundle adjustment theory fed into camera calibration)
- **Key enabling technique**: Deep learning — has surpassed prior methods on classification, segmentation, and optical flow benchmarks
- **Downstream applications**: Robotics, autonomous vehicles, medical imaging, factory automation, augmented reality

## Exam-Relevant Points

- CV began in the late 1960s at AI-pioneering universities; the 1966 MIT summer project famously underestimated the difficulty of "describing what a camera sees"
- **1970s contributions**: Edge detection, line labeling, optical flow, motion estimation
- **1980s contributions**: Scale-space theory, shape-from-shading/texture/focus, active contour models (snakes), regularization and Markov random fields as unifying optimization frameworks
- **1990s contributions**: Camera calibration via projective geometry, sparse and dense 3D reconstruction, graph cuts for image segmentation, Eigenface for statistical face recognition, convergence with computer graphics (image stitching, light-field rendering)
- **Modern era**: Feature-based methods combined with machine learning; deep learning now dominates benchmarks for classification, segmentation, and optical flow
- Know the distinction: **computer vision** (scientific/theoretical) vs. **machine vision** (systems engineering/industrial)
- Optical flow and motion estimation appeared early (1970s) and remain active research areas
