---
source: chunks/wiki-Convolutional_neural_network-chunk-4.md
source_url: https://en.wikipedia.org/wiki/Convolutional_neural_network
---

## CNN Hyperparameters, Regularization, and Translation Equivariance

This page covers the key hyperparameters that control CNN learning, regularization methods to prevent overfitting, the nuances of translation equivariance/invariance in CNNs, and the concept of hierarchical coordinate frames for spatial reasoning.

## Key Concepts

- **Padding**: Adding 0-valued pixels to image borders so edge pixels participate in multiple receptive fields rather than being undervalued. Typical padding is one less than the kernel dimension (e.g., 2-pixel pad for 3x3 kernels).
- **Stride**: The number of pixels the convolution window shifts per iteration. Stride of 2 means each kernel is offset by 2 pixels from its predecessor.
- **Number of filters**: Layers near input have fewer filters; deeper layers have more. The product of feature values and pixel positions is kept roughly constant across layers to equalize computation.
- **Filter/kernel size**: Ranges from 1x1 to 7x7 in practice. AlexNet used 3x3, 5x5, 11x11; InceptionV3 used 1x1, 3x3, 5x5. Must balance granularity to avoid overfitting.
- **Pooling**: Max pooling with 2x2 is typical. Drastically downsamples input. Non-overlapping windows generally perform best. Greater pooling risks information loss.
- **Dilation**: Skips pixels within a kernel to expand receptive field without increasing parameters. Dilation of 2 on a 3x3 kernel covers a 5x5 area but processes only 9 pixels.
- **Translation equivariance vs. invariance**: Convolution/pooling layers without stride >1 are equivariant to translations. Stride >1 violates Nyquist-Shannon sampling theorem, causing aliasing. Fully connected layers break translation invariance even if prior layers are equivariant.
- **Dropout**: Each node dropped with probability 1-p during training (typically p=0.5; higher for input nodes). At test time, outputs weighted by p to approximate ensemble of 2^n sub-networks.
- **DropConnect**: Generalizes dropout by dropping individual connections (weights) rather than entire output units, creating dynamic sparsity on weights.
- **Stochastic pooling**: Replaces deterministic pooling with random selection according to multinomial distribution over activations. Hyperparameter-free; equivalent to max pooling over locally deformed copies.
- **Weight decay**: L2 regularization penalizes squared magnitude of weights (prefers diffuse weight vectors); L1 regularization produces sparse weights. Elastic net combines both.
- **Max norm constraints**: Clamps weight vector L2 norm to an upper bound c (typically 3-4) after each parameter update via projected gradient descent.
- **Early stopping**: Halt training before overfitting occurs; simplest but sacrifices potential learning.
- **Hierarchical coordinate frames**: Represent features along with their pose relative to the retina, enabling recognition from novel viewpoints by enforcing consistency of part poses.

## Commands and Syntax

No specific commands; this section is conceptual. Key formulas and conventions:

- **Dropout probability**: nodes kept with probability `p`, dropped with `1-p`. Test-time output scaled by `p`.
- **Weight decay (L2)**: adds `alpha * ||w||^2` to the loss
- **Weight decay (L1)**: adds `alpha * ||w||_1` to the loss
- **Max norm constraint**: after update, clamp `||w||_2 < c` (c ~ 3-4)
- **Dilation arithmetic**: dilation `d` on kernel size `k` expands effective size to `k + (k-1)(d-1)`

## Relationships

- **Padding/Stride/Kernel size** jointly determine output spatial dimensions of each convolutional layer
- **Pooling** interacts with stride to affect translation equivariance; both relate to the Nyquist-Shannon sampling theorem and aliasing
- **Regularization methods** (dropout, DropConnect, weight decay, early stopping, data augmentation) all address overfitting but at different levels — nodes, connections, weights, or training data
- **Stochastic pooling** connects to data augmentation (elastic deformations) conceptually
- **Capsule neural networks** are proposed as a solution to translation invariance limitations, relating to hierarchical coordinate frames
- **Anti-aliasing filters** and **spatial transformer networks** are partial solutions to equivariance/invariance problems
- **Number of filters** ties to network capacity and relates to overfitting risk, connecting regularization back to architecture design

## Exam-Relevant Points

- Padding of 1 pixel on each side is standard for 3x3 kernels to preserve spatial dimensions
- Stride >1 can break translation equivariance due to aliasing (Nyquist violation)
- Dropout uses p=0.5 for hidden layers, higher for input layers; at test time multiply outputs by p
- DropConnect drops weights (connections), not neurons — it is a generalization of dropout
- L2 regularization encourages using all inputs a little; L1 encourages sparse inputs (using a few inputs a lot)
- Elastic net regularization = L1 + L2 combined
- Max pooling with 2x2 non-overlapping windows is the standard; larger pooling risks unacceptable information loss
- Fully connected layers break translation invariance even when convolutional layers preserve equivariance
- Global average pooling at the last layer is one solution for complete translation invariance
- Dilation of 2 on a 3x3 kernel creates an effective 5x5 receptive field while processing only 9 pixels
- The number of feature maps controls capacity and should balance with available training data and task complexity
- Stochastic pooling is hyperparameter-free and combinable with dropout and data augmentation
- Data augmentation (cropping, rotation, rescaling) is used since the mid-1990s to combat overfitting
