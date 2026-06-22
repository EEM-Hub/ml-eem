---
source: chunks/wiki-Computer_vision-chunk-6.md
source_url: https://en.wikipedia.org/wiki/Computer_vision
---

## Computer Vision — Foundational Reading and Resources

This page provides a curated bibliography of seminal and reference texts in computer vision, spanning from the field's theoretical foundations in the early 1980s through modern algorithmic approaches. It also lists key external resources, conferences, and a taxonomy of computer vision sub-disciplines.

## Key Concepts

- **Foundational texts**: David Marr's *Vision* (1982) established the computational theory of vision; Rosenfeld & Kak's *Digital Picture Processing* (1982) formalized digital image analysis
- **Geometric vision**: Hartley & Zisserman's *Multiple View Geometry* (2003) is the standard reference for multi-view 3D reconstruction; Faugeras (1993) covers 3D CV from a geometric viewpoint
- **Scale-space theory**: Lindeberg (1994) formalized multi-scale image representation, foundational to feature detection (SIFT, etc.)
- **Robot vision**: Horn (1986) bridged CV and robotics; Fairhurst (1988) focused on CV for robotic systems
- **Algorithmic CV**: Szeliski (2010) is the modern comprehensive reference covering algorithms and applications end-to-end
- **Signal processing perspective**: Granlund & Knutsson (1995) treat CV through signal processing foundations
- **Mathematical models**: Paragios, Chen & Faugeras (2005) provide the mathematical framework handbook
- **Historical context**: Dobson (2023) documents the birth and evolution of the field

## Commands and Syntax

No commands or configuration syntax — this is a reference/bibliography page.

## Relationships

- **3D Reconstruction**: connects to structure from motion, simultaneous localization and mapping (SLAM), Gaussian splatting, neural radiance fields (NeRF), visual hull methods
- **Feature Detection & Extraction**: scale-space theory underpins feature detectors used in object recognition and image matching
- **Differentiable Computing**: modern CV heavily relies on differentiable programming frameworks (PyTorch, TensorFlow, JAX) for deep learning-based vision
- **Application Domains**: autonomous vehicles, medical image computing, augmented reality, face recognition, OCR, video surveillance, remote sensing
- **Hardware Acceleration**: GPU/TPU/IPU computing enables real-time CV; NVIDIA GPU containers widely adopted for research
- **Key Conferences**: BMVC (British Machine Vision Conference), MIUA; USC Iris maintains comprehensive CV conference listings

## Exam-Relevant Points

- **David Marr's *Vision* (1982)** is considered the foundational theoretical work establishing computational approaches to visual perception
- **Hartley & Zisserman (2003)** is the definitive reference for **multiple view geometry** — essential for understanding epipolar geometry, fundamental matrices, and 3D reconstruction from images
- **Scale-space theory** (Lindeberg, 1994) provides the mathematical basis for multi-scale feature detection algorithms
- The CV taxonomy includes: **3D reconstruction**, **object recognition**, **segmentation**, **motion analysis**, **feature detection**, and **image restoration** as major sub-areas
- Modern CV intersects with **differentiable computing** — frameworks like PyTorch and TensorFlow are standard tools
- Key application areas to know: **SLAM**, **autonomous vehicles**, **medical imaging**, **OCR**, **pose estimation**, **activity recognition**
- The field evolved from **digital image processing** (1980s) → **geometric/mathematical vision** (1990s) → **algorithmic/learning-based vision** (2000s–present)
