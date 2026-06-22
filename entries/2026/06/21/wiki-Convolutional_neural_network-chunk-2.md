---
source: chunks/wiki-Convolutional_neural_network-chunk-2.md
source_url: https://en.wikipedia.org/wiki/Convolutional_neural_network
---

## History and Distinguishing Features of Convolutional Neural Networks (CNNs)

This page covers the historical development of CNNs from their neuroscience origins in the 1950s through GPU-accelerated breakthroughs in the 2010s, and explains the key architectural features that distinguish CNNs from standard multilayer perceptrons.

## Key Concepts

- **Receptive fields**: Hubel and Wiesel (1950s–60s) discovered that neurons in the cat visual cortex respond to small, specific regions of the visual field; neighboring neurons have overlapping receptive fields
- **Simple cells** respond maximally to straight edges at particular orientations; **complex cells** have larger receptive fields and are position-insensitive
- **Neocognitron** (Fukushima, 1980): introduced two foundational layer types — S-layers (shared-weight convolutional layers) and C-layers (downsampling/pooling layers with inhibition)
- **ReLU activation**: first introduced by Fukushima in 1969, not used in the neocognitron itself, but later became the dominant activation function for CNNs and deep networks
- **Convolution vs. correlation**: modern CNNs actually compute correlation and call it convolution — reversing weights doesn't affect the learned function
- **Max pooling**: introduced by Yamaguchi et al. (1990) for speech recognition; propagates the maximum value in a region rather than averaging
- **LeNet-5** (LeCun et al., 1995): 7-layer CNN for handwritten digit recognition on 32×32 images; deployed commercially in bank check reading systems
- **Curse of dimensionality in MLPs**: a 1000×1000 RGB image yields 3 million weights per fully-connected neuron — computationally intractable
- **Translational equivariance** (from weight sharing with stride 1) vs. **translational invariance** (from pooling) — these are distinct properties

## Commands and Syntax

No specific commands or configuration syntax — this is conceptual/architectural content.

## Relationships

- **Neuroscience → CNN architecture**: receptive fields, simple/complex cell hierarchy directly inspired the convolutional/pooling layer design
- **Neocognitron → modern CNNs**: S-layers became convolutional layers; C-layers became pooling layers; backpropagation replaced local unsupervised training
- **TDNN → 1D CNNs**: time delay neural networks are 1D CNNs with weight sharing along the time axis; first to combine shared weights with backpropagation training
- **GPU computing → CNN breakthroughs**: practical CNN success required GPU acceleration (4–60× speedups over CPU); AlexNet's 2012 ImageNet win was a catalytic event for the AI boom
- **CNNs vs. MLPs**: CNNs solve the MLP dimensionality problem through local connectivity, weight sharing, and pooling

## Exam-Relevant Points

- **Fukushima (1969)**: introduced both the concept of homogeneous weight sharing across a layer AND the ReLU activation function — two separate contributions
- **Neocognitron (1980)** introduced S-layers (convolutional) and C-layers (pooling) — know both layer types and their functions
- **TDNN (Waibel, 1987)**: first CNN to combine weight sharing with gradient descent/backpropagation training
- **LeCun et al. (1989)**: first to use backpropagation to learn convolution kernels directly from images (not hand-designed)
- **Max pooling (1990)**: Yamaguchi et al. introduced it; Weng et al. (1993, cresceptron) brought it to vision
- **LeNet-5 (1995)**: 7-layer network, 32×32 input, deployed in real banking systems
- **AlexNet (2012)**: GPU-trained CNN that won ImageNet LSVRC, catalyzed the AI boom
- **Weight sharing** provides translational equivariance; **pooling** provides translational invariance — distinguish these two properties
- **Four distinguishing features of CNNs**: 3D neuron volumes, local connectivity, shared weights, and pooling
- CNNs were invented in the 1980s but practical breakthroughs required GPU implementations starting in the 2000s (20× speedup in 2004, 60× by 2011)
