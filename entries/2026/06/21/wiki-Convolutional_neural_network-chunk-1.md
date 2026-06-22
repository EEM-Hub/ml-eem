---
source: chunks/wiki-Convolutional_neural_network-chunk-1.md
source_url: https://en.wikipedia.org/wiki/Convolutional_neural_network
---

## Convolutional Neural Networks (CNNs)

A convolutional neural network (CNN) is a type of feedforward neural network that learns features through filter (kernel) optimization. CNNs apply convolution operations to extract hierarchical features from input data, most commonly images. They are the de-facto standard for deep learning-based computer vision and image processing, though transformers have begun replacing them in some applications. CNNs are also called shift invariant or space invariant artificial neural networks due to their shared-weight architecture.

## Key Concepts

- **Convolution operation**: A dot product (Frobenius inner product) of a convolution kernel with the layer's input matrix, generating a feature map that feeds into the next layer
- **Shared weights**: Multiple neurons share the same filter, dramatically reducing parameters compared to fully connected networks (e.g., 25 weights for a 5×5 kernel vs. 10,000 for a 100×100 fully connected layer)
- **Translation equivariance**: Convolution kernels sliding along input produce feature maps that are equivariant to translation; however, CNNs are typically *not* translation invariant due to downsampling (pooling)
- **Receptive field**: Each neuron receives input from only a restricted area of the previous layer; deeper layers have progressively larger effective receptive fields
- **Feature hierarchy**: Lower layers extract local features from narrow context windows; higher layers extract features from wider context windows
- **Regularization via architecture**: Shared weights and reduced connectivity inherently help prevent vanishing/exploding gradients and overfitting compared to fully connected networks
- **Biological inspiration**: Connectivity pattern mirrors the visual cortex, where cortical neurons respond to stimuli only in restricted, partially overlapping regions of the visual field
- **Automated feature learning**: CNNs learn optimal filters through training rather than relying on hand-engineered features

## Architecture Layers

- **Input tensor shape**: `(batch) × (height) × (width) × (channels)`
- **Convolutional layers**: Apply learned filters to produce feature maps (activation maps); activation function is commonly ReLU
- **Depthwise separable convolution**: Splits into depthwise convolution (spatial, per-channel) followed by pointwise convolution (1×1 kernels) for faster processing
- **Dilated (atrous) convolution**: Expands receptive field without increasing parameters by interleaving visible and blind regions; supports multiple dilation ratios in a single layer
- **Pooling layers**: Reduce spatial dimensions by combining neuron clusters; *max pooling* takes the maximum value, *average pooling* takes the mean; local pooling uses small tiles (e.g., 2×2), global pooling acts on entire feature maps
- **Fully connected layers**: Traditional MLP layers connecting every neuron; used at the end for classification after flattening
- **Deconvolutional layers**: Transpose of convolutional layers (matrix transpose multiplication); used in image generation
- **Unpooling layers**: Expand spatial dimensions (reverse of pooling); max-unpooling copies entries multiple times
- **Notable architectures**: LeNet (1995), AlexNet (2012)

## Commands and Syntax

No CLI commands per se, but key configuration parameters for CNN layers:

- **Kernel/filter size**: e.g., 5×5, 3×3 — determines receptive field per layer
- **Stride**: Step size of kernel sliding across input
- **Dilation rate**: Controls spacing in dilated convolutions
- **Pooling size**: e.g., 2×2 for local pooling
- **Number of filters**: Determines feature map channels in output
- **Checkerboard artifact fix**: When using deconvolution for image generation, use upscale-then-convolve instead of default transposed convolution

## Relationships

- **Feedforward neural networks**: CNNs are a specialized subtype; fully connected feedforward nets are prone to overfitting on large inputs
- **Deep learning**: CNNs are a core deep learning architecture
- **Transformers (Vision Transformers)**: Newer alternative that has replaced CNNs in some computer vision tasks
- **Backpropagation**: Training mechanism; shared weights mitigate vanishing/exploding gradient problems
- **Matched filters**: CNN convolution operation is closely related to matched filtering in signal processing
- **Multilayer perceptrons (MLP)**: The fully connected layers in a CNN are equivalent to a traditional MLP
- **Regularization techniques**: Weight decay, dropout, skip connections complement CNN's inherent regularization from weight sharing

## Exam-Relevant Points

- CNNs produce translation-**equivariant** feature maps, but are typically NOT translation-**invariant** due to downsampling — a common misconception
- Weight sharing reduces parameters dramatically: 5×5 kernel = 25 weights vs. 10,000 for fully connected on 100×100 input
- Max pooling vs. average pooling: max takes the maximum of a local cluster, average takes the mean
- Depthwise separable convolution = depthwise (per-channel spatial) + pointwise (1×1) — used to reduce computation
- Dilated convolution increases receptive field without adding parameters
- Deconvolutional layers can create checkerboard artifacts; fix is upscale-then-convolve
- CNNs learn filters automatically (vs. hand-engineered features in traditional CV)
- Biological inspiration: receptive fields in the visual cortex
- Applications span: computer vision, NLP, recommender systems, medical imaging, brain-computer interfaces, financial time series
