---
source: chunks/wiki-Convolutional_neural_network-chunk-3.md
source_url: https://en.wikipedia.org/wiki/Convolutional_neural_network
---

## CNN Building Blocks: Layer Types and Architecture

This page covers the core layer types that compose a Convolutional Neural Network (CNN) architecture. Each layer transforms an input volume into an output volume through a differentiable function. The five fundamental layers — convolutional, pooling, ReLU, fully connected, and loss — are stacked to form complete CNN architectures that progressively extract features and produce classification or regression outputs.

## Key Concepts

- **Convolutional layer**: The core CNN building block. Learnable filters (kernels) slide across the input, computing dot products to produce 2D activation maps. Stacking all filter activation maps along the depth dimension forms the output volume.
- **Local connectivity**: Neurons connect only to a small spatial region (receptive field) of the input, but always extend through the full depth. This exploits spatial correlation and avoids impractical full connectivity.
- **Parameter sharing**: All neurons in a single depth slice share the same weights and bias, reducing free parameters and contributing to **translation invariance**. When this assumption is inappropriate (e.g., centered faces), a **locally connected layer** with independent weights per spatial location is used instead.
- **Three hyperparameters** control convolutional output size: **depth** (number of filters), **stride** (step size), and **padding** (zero-padding on borders). "Same" padding preserves spatial dimensions.
- **Pooling layer**: Non-linear downsampling that reduces spatial dimensions while retaining important information. Reduces parameters, memory, computation, and helps control overfitting.
- **Max pooling** outperforms average pooling in practice. A common configuration is 2x2 filters with stride 2, which discards 75% of activations.
- **Channel max pooling (CMP)**: Pools along the channel dimension rather than spatially, reducing channel count while preserving spatial dimensions. Useful for fine-grained classification.
- **ReLU**: f(x) = max(0, x). A non-saturating activation function that introduces nonlinearity, trains faster than tanh or sigmoid, and enables training of deeper networks (Glorot et al., 2011).
- **Fully connected layer**: Every neuron connects to all activations in the previous layer. Computes an affine transformation (matrix multiply + bias). Used for final classification after convolutional/pooling stages.
- **Loss layer**: Penalizes deviation between predicted and true labels. Choice depends on the task.

## Commands and Syntax

**Output size formula for convolutional layer:**

```
output_size = (W - K + 2P) / S + 1
```
Where: W = input size, K = kernel size, P = padding, S = stride. Result must be an integer.

**"Same" padding** (preserves spatial size when S=1):
```
P = (K - 1) / 2
```

**Max pooling operation** (2x2, stride 2):
```
f(X,Y)(S) = max(a,b=0..1) S[2X+a, 2Y+b]
```

**Loss functions by task:**
| Task | Loss Function |
|------|--------------|
| Single-class classification (K mutually exclusive) | Softmax loss |
| Multi-label (K independent probabilities in [0,1]) | Sigmoid cross-entropy |
| Regression to real-valued labels | Euclidean loss |

## Relationships

- **Convolutional layers → Pooling layers → Fully connected layers → Loss layer** form the typical CNN pipeline
- ReLU activation is typically applied after each convolutional layer, before pooling
- Pooling provides **local** translation invariance; only global pooling provides global invariance
- Fully connected layers bridge the gap between CNN feature extraction and traditional neural network classification
- Parameter sharing in convolutional layers is what distinguishes them from locally connected layers
- Modern trend: smaller filters and discarding pooling layers altogether in favor of strided convolutions

## Exam-Relevant Points

- **Output size formula**: (W - K + 2P) / S + 1 — must produce an integer; know how to compute this
- **Parameter sharing** reduces free parameters and provides translation invariance — know when it's used and when it's relaxed (locally connected layers)
- **Max pooling 2x2 with stride 2** discards 75% of activations — the stride causes downsampling, not the pooling operation itself
- **ReLU** = max(0, x); preferred because it trains faster without significant accuracy loss; enables deeper networks
- **Softmax** for mutually exclusive classes, **sigmoid cross-entropy** for independent multi-label, **Euclidean** for regression
- Pooling reduces spatial size, parameters, memory, and computation — also helps control **overfitting**
- Without stride > 1, pooling does **not** perform downsampling
- Channel max pooling changes channel count but preserves spatial dimensions — opposite of standard spatial pooling
- **Locally connected layers** are used when different spatial locations should learn different features (e.g., centered face images)
