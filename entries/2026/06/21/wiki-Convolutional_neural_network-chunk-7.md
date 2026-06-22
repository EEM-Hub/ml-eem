---
source: chunks/wiki-Convolutional_neural_network-chunk-7.md
source_url: https://en.wikipedia.org/wiki/Convolutional_neural_network
---

## Convolutional Neural Networks — Foundational References and History

This page compiles the key references cited in the Wikipedia article on Convolutional Neural Networks (CNNs). While it is a bibliography rather than expository content, the citations themselves map the intellectual lineage and application breadth of CNNs, from neuroscience origins through modern deep learning.

## Key Concepts

- **Biological inspiration**: CNNs trace to Hubel & Wiesel's 1959/1968 discovery of receptive fields in cat and monkey striate cortex — neurons respond to stimuli in localized regions, with simple and complex cell hierarchies (refs 19, 37, 38)
- **Neocognitron (1980)**: Fukushima's self-organizing neural network for shift-invariant pattern recognition was the direct precursor to modern CNNs (refs 18, 20, 39)
- **Time-Delay Neural Networks (TDNN)**: Waibel (1987) applied weight-sharing (convolution) to speech/phoneme recognition — one of the first practical 1D convolutional architectures (refs 42, 43)
- **Backpropagation on CNNs**: LeCun et al. (1989) applied backpropagation to handwritten zip code recognition using convolutional layers, establishing the modern CNN training paradigm (refs 2, 47, 48)
- **Shift-invariant networks**: Zhang (1988, 1990) introduced shift-invariant pattern recognition neural networks with local space-invariant interconnections (refs 14, 15)
- **Deep learning definition**: LeCun, Bengio, Hinton (2015) — the landmark *Nature* review paper defining deep learning as representation learning with multiple levels of abstraction (ref 1)
- **Translation invariance vs. equivariance**: Mouton et al. (2020) studied stride and translation invariance properties — CNNs achieve approximate, not exact, translation invariance (ref 16)
- **Vanishing/exploding gradients**: Key training challenges for deep CNNs addressed in refs 3, 4
- **Dilated (atrous) convolutions**: Yu & Koltun (2016) introduced dilated convolutions for multi-scale context aggregation without losing resolution (ref 29); Chen et al. (2017) extended this for semantic segmentation (ref 30)
- **Depthwise separable convolutions**: Chollet (2017) — Xception architecture factoring standard convolutions into depthwise and pointwise operations for efficiency (ref 24)
- **Deconvolution/transposed convolutions**: Zeiler et al. (2011) for feature learning; Dumoulin & Visin (2018) guide to convolution arithmetic; Odena et al. (2016) identified checkerboard artifacts in deconvolution (refs 33, 34, 35)

## Commands and Syntax

No commands or configuration syntax — this is a reference bibliography. However, the key architectural papers define the building blocks used in frameworks:

- **LeNet-5** (LeCun): conv → pool → conv → pool → FC → output (ref 32)
- **Multi-column DNN** (Ciresan et al. 2012): multiple parallel CNN columns with averaged outputs, achieved near-human performance on MNIST (ref 28)
- **AlexNet** (Krizhevsky): deep CNN with ReLU, dropout, GPU training for ImageNet classification (ref 26)

## Relationships

- **Neuroscience → Architecture**: Hubel/Wiesel receptive fields → Fukushima's Neocognitron → LeCun's CNNs — a direct lineage from biology to engineering
- **Speech → Vision**: TDNNs (1D convolution for speech, Waibel 1987) preceded LeCun's 2D convolution for images (1989) — weight sharing is the common principle
- **CNNs → Application domains**: Computer vision (refs 5, 21, 25, 26, 28), speech recognition (refs 27, 42, 43, 46), NLP (ref 11), music recommendation (ref 10), finance/stock prediction (ref 13), medical imaging (refs 12, 49, 50), drug discovery (ref 17), manufacturing (ref 5)
- **Activation functions**: Ramachandran et al. (2017) — automated search for activation functions (Swish) complementing standard ReLU (ref 41)
- **Hardware efficiency**: Residue number system approaches to reduce CNN hardware costs (refs 6, 9)

## Exam-Relevant Points

- **1959/1968**: Hubel & Wiesel — receptive fields in visual cortex (Nobel Prize work, biological foundation of CNNs)
- **1980**: Fukushima — Neocognitron (first neural network with convolutional structure, unsupervised)
- **1987**: Waibel — TDNN (first use of weight sharing / 1D convolution for speech)
- **1988**: Zhang — shift-invariant pattern recognition network
- **1989**: LeCun — backpropagation applied to CNNs for handwritten digit recognition
- **2012**: Ciresan — multi-column DNNs achieved near-human performance on benchmarks
- **2012**: Krizhevsky (AlexNet) — breakthrough on ImageNet, catalyzed the deep learning revolution
- **2015**: LeCun, Bengio, Hinton — *Nature* deep learning review (most-cited reference in the field)
- **Convolution in CNNs** is technically cross-correlation, not mathematical convolution (ref 8: "the notion of convolution or correlation used in the models")
- **CNNs are not perfectly translation-invariant** — stride and pooling provide approximate invariance only (ref 16)
- **Dilated convolutions** expand receptive field without increasing parameters or reducing resolution
- **Depthwise separable convolutions** (Xception) factor computation for efficiency — key to mobile architectures
- **Checkerboard artifacts** are a known failure mode of transposed convolutions (deconvolution); resize-convolution is the fix (ref 35, Distill)
- **Data augmentation** (e.g., reverberant speech augmentation) is critical for robust CNN training (ref 46)
