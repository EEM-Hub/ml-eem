---
source: chunks/wiki-Computer_vision-chunk-5.md
source_url: https://en.wikipedia.org/wiki/Computer_vision
---

## Computer Vision: Foundational References and Key Literature

This page is a bibliography/references section from a Wikipedia article on Computer Vision. It catalogs the seminal textbooks, landmark papers, and key publications that define the field. While purely a reference list, it reveals the intellectual lineage of computer vision — from classical algorithmic approaches through the deep learning revolution — and identifies the most influential authors and venues.

## Key Concepts

- **Foundational textbooks** span from Ballard & Brown (1982) through Szeliski (2010) and Davies (2018), showing the field's evolution from geometric/algorithmic methods to learning-based approaches
- **Deep learning transformed CV**: LeCun, Bengio & Hinton's 2015 Nature paper ("Deep Learning") is a landmark reference establishing CNNs as the dominant paradigm
- **ImageNet Large Scale Visual Recognition Challenge (ILSVRC)**: Russakovsky et al. (2015) — the benchmark that catalyzed the deep learning revolution in CV via large-scale image classification competitions
- **Core CV sub-problems** referenced: object detection, image segmentation, optical flow estimation, 3D shape synthesis, action localization, stereo vision, scene recognition
- **FlowNet 2.0** (Ilg et al., 2016): demonstrates deep networks applied to optical flow, a classical CV problem
- **Machine vision vs. computer vision**: industrial/manufacturing applications (machine vision) are distinguished from broader research (computer vision), per Steger et al. (2018) and NASA (Turek, 2011)
- **MIT Summer Vision Project** (Papert, 1966): historically significant as one of the earliest formal CV research efforts, famously underestimating the difficulty of the problem
- **CNNs (Convolutional Neural Networks)**: used across CV, speech recognition, bioinformatics, and time series analysis (Chervyakov et al., 2020)
- **Vision Processing Units (VPUs)**: specialized hardware (e.g., Movidius Myriad 2) emerging for real-time CV/AR/VR workloads

## Commands and Syntax

No commands or configuration syntax — this is a bibliography. However, key benchmark/dataset references include:
- **ImageNet (ILSVRC)**: The standard large-scale image classification benchmark (1000 classes, ~1.2M training images)
- **CVPR, ICCV, ECCV**: Premier computer vision conferences where most cited work appears
- **trackdem** (R package): Automated particle tracking from video for ecological population counting (Bruijning et al., 2018)

## Relationships

- **Deep Learning**: CV is one of the primary application domains driving deep learning research (LeCun et al., 2015)
- **Robotics**: Stereo vision for navigation (Murray & Jennings, 1997), tactile sensing (Ando et al., 2020; Choi & Tahara, 2020)
- **Medical Imaging**: Deep learning-enabled medical CV (Esteva et al., 2021; Li et al., 2023) — radiology, pathology, dermatology
- **Agriculture**: Plant species identification (Wäldchen & Mäder, 2017), crop disease detection (strawberry quality, tomato leaf counting)
- **Autonomous Vehicles/Safety**: Drowsiness detection systems (Garg, 2020; Hasan & Kashevnik, 2021)
- **3D Vision**: Multi-view depth maps and shape synthesis using generative networks (Soltani et al., 2017)
- **Ecology**: Automated organism tracking and counting from video (Bruijning et al., 2018)
- **Military and Defense**: Growing market for CV applications in military AI systems

## Exam-Relevant Points

- **1966 MIT Summer Vision Project** (Seymour Papert) is a classic historical reference — it proposed solving vision "in a summer," illustrating early underestimation of CV's difficulty
- **ImageNet/ILSVRC** (Russakovsky et al., 2015) is the benchmark that triggered the deep learning revolution in CV when AlexNet won in 2012
- **LeCun, Bengio, Hinton (2015)** Nature paper is the canonical deep learning survey — know these three names as "Godfathers of Deep Learning"
- **Distinction between computer vision and machine vision**: CV = broader scientific field; machine vision = industrial/manufacturing application focus
- **Key CV tasks**: image classification, object detection, semantic segmentation, optical flow, 3D reconstruction, action recognition, scene understanding
- **CNNs are the dominant architecture** for CV tasks, though Vision Transformers are emerging (referenced in agricultural disease detection, 2024)
- **Application domains to know**: medical imaging, autonomous driving, agriculture, robotics, ecology, manufacturing/quality inspection, military/defense
- **Hardware trend**: Vision Processing Units (VPUs) like Movidius Myriad 2 represent specialized silicon for CV workloads, distinct from CPUs and GPUs
