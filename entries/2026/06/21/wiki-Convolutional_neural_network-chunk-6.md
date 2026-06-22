---
source: chunks/wiki-Convolutional_neural_network-chunk-6.md
source_url: https://en.wikipedia.org/wiki/Convolutional_neural_network
---

## Convolutional Neural Networks — Supplementary Notes

This fragment contains only footnotes from a larger CNN article, not primary content. The notes clarify three minor points: the generality of "spatial position" beyond images, the etymology of "convolutional layer," and a pointer to categorical data.

## Key Concepts

- **Spatial position is domain-general**: CNNs are most associated with image data, but "spatial position" in a convolutional layer can correspond to points in the **time domain** (e.g., audio), the **frequency domain** (e.g., spectrograms), or other mathematical spaces. This underscores that convolution is not image-specific.
- **Name origin**: The "convolutional layer" is named for the mathematical **convolution operation** it performs — sliding a kernel across the input and computing element-wise products.
- **Categorical data**: CNN outputs for classification tasks produce categorical predictions — discrete class labels rather than continuous values.

## Commands and Syntax

None present in this fragment.

## Relationships

- **Time domain / Frequency domain**: CNNs applied to audio or signal data operate over these domains rather than 2D spatial grids, connecting CNNs to signal processing and 1D convolutions.
- **Mathematical spaces**: Convolutions generalize to arbitrary structured domains (graphs, manifolds), linking to graph neural networks and geometric deep learning.
- **Categorical data**: Connects to softmax output layers, cross-entropy loss, and classification task formulation.

## Exam-Relevant Points

- CNNs are **not limited to image data** — they apply wherever local spatial/temporal structure exists (audio, time series, text).
- The convolution operation (kernel sliding + element-wise product + sum) is the defining characteristic that gives the layer its name.
- Classification CNNs produce **categorical outputs**, typically via a softmax layer.

---

**Note:** This source contained only footnotes. For comprehensive CNN coverage, the primary article sections (architecture, pooling, backpropagation, applications) would be needed.
