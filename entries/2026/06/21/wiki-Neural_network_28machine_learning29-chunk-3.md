---
source: chunks/wiki-Neural_network_28machine_learning29-chunk-3.md
source_url: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29
---

## Neural Network Elements: Neurons, Structure, and Connectivity

This page covers the fundamental building blocks of artificial neural networks — the artificial neuron, how neurons are organized into layered networks, and the primary connection patterns (feedforward, convolutional, recurrent). It traces the origin of these concepts from biological inspiration to mathematically-driven designs.

## Key Concepts

- **Artificial neuron**: Takes one or more numerical inputs, applies weights to each, sums them, adds a bias term, then passes the result through a nonlinear activation function to produce a single output. Small outputs may be zeroed out.
- **Computation formula**: output = activation_function(Σ(weight_i × input_i) + bias)
- **Network as graph**: A neural network forms a **directed, weighted graph**, with weights on both nodes and edges.
- **Layered architecture**: Nodes are arranged in layers. Bottom layers handle raw data; intermediate layers progressively increase abstraction (pixels → edges → objects); top layers produce final results.
- **Fully connected layers**: Every neuron in one layer connects to every neuron in the next layer (the traditional pattern).
- **Convolutional layers**: Each neuron connects to only a **subset** of neurons in the previous layer (e.g., a local region of an image).
- **Feedforward networks**: Information flows in one direction only — from input to output — forming a directed acyclic graph (DAG). No connections to same-layer or previous-layer neurons.
- **Recurrent networks**: Allow connections between neurons in the same or previous layers, enabling cycles and temporal/sequential processing.
- **Biological analogy**: Neuron connections are analogous to axon-synapse-dendrite pathways in biological neural systems, though modern designs prioritize mathematical performance over biological fidelity.

## Commands and Syntax

No commands or configuration syntax on this page — it is conceptual/theoretical.

## Relationships

- **Activation functions**: Directly determine neuron output behavior (ReLU, sigmoid, tanh, etc.)
- **Convolutional neural networks (CNNs)**: A major architecture class defined by their use of convolutional (local connectivity) layers.
- **Feedforward neural networks**: The default architecture for most standard tasks; contrasts with recurrent networks.
- **Recurrent neural networks (RNNs)**: Enable sequence modeling by allowing backward/lateral connections.
- **Weight function / bias**: Core parameters adjusted during training (connects to backpropagation and optimization topics).
- **Directed acyclic graphs**: The mathematical structure underlying feedforward networks; cycles distinguish recurrent networks.

## Exam-Relevant Points

- A neuron computes: **weighted sum of inputs + bias → activation function → output**. Know all three components.
- Distinguish **fully connected** (dense) layers from **convolutional** layers: full connectivity vs. local/subset connectivity.
- **Feedforward = DAG = no cycles**; **Recurrent = cycles allowed** (connections to same or prior layers). This is a common exam distinction.
- Layers provide **hierarchical abstraction**: raw input → low-level features → high-level features → output.
- Neural networks are modeled as **directed, weighted graphs** — weights exist on both nodes (biases) and edges (connection weights).
- Single-layer and unlayered networks exist but are less common than multi-layer architectures.
