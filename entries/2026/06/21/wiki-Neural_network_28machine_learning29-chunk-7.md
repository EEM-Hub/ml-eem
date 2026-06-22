---
source: chunks/wiki-Neural_network_28machine_learning29-chunk-7.md
source_url: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29
---

## Feedforward Neural Network Architecture

This page covers the structural anatomy of feedforward artificial neural networks, illustrating how inputs are transformed into outputs through weighted connections and activation functions. It progresses from single-layer to multi-layer topologies and includes specialized architectures like CMAC.

## Key Concepts

- **Feedforward architecture**: Information flows in one direction only — from input nodes, through any hidden layers, to output nodes. No cycles or feedback loops exist in the graph.
- **Single-layer feedforward network**: Has *p* inputs and *q* outputs with no hidden layer. Each output is computed as y_q = K · (Σ_i (x_i · w_iq) − b_q), where K is the activation function, w_iq are weights, and b_q is the bias.
- **Two-layer feedforward network**: Adds one or more hidden layers between input and output, enabling the network to learn non-linear mappings (universal approximation).
- **Weights (w_iq)**: Learnable parameters connecting input i to output q; encode the strength and direction of each connection.
- **Bias (b_q)**: A per-output offset subtracted before the activation function is applied; shifts the activation threshold.
- **Activation function (K)**: A (typically non-linear) function applied to the weighted sum to produce the output. Without it, the network collapses to a linear transformation regardless of depth.
- **CMAC (Cerebellar Model Articulation Controller)**: A specialized neural network with a parallel pipeline structure capable of converging in a single training step — useful for real-time control applications.

## Commands and Syntax

- **Single-layer output computation**:
  ```
  y_q = K · ( Σ_i (x_i · w_iq) − b_q )
  ```
  - Sum each input x_i multiplied by its corresponding weight w_iq
  - Subtract the bias b_q
  - Apply the activation function K to produce output y_q

No CLI commands or configuration syntax are presented on this page; it is conceptual/mathematical.

## Relationships

- **ADALINE**: A single-layer network using a linear activation, foundational predecessor to modern architectures.
- **Autoencoders**: Multi-layer feedforward networks trained to reconstruct their input, used for dimensionality reduction and feature learning.
- **Support Vector Machines**: An alternative supervised learning model; feedforward nets and SVMs are often compared on classification benchmarks.
- **Spiking Neural Networks**: A biologically closer alternative where timing of spikes encodes information, unlike the rate-coded activations in standard feedforward nets.
- **Evolutionary/Genetic Algorithms**: Alternative optimization methods sometimes used to train or design neural network architectures (neuroevolution).
- **Catastrophic Interference**: A key failure mode of feedforward networks where learning new tasks destroys previously learned representations.
- **Parallel Distributed Processing (PDP)**: The theoretical framework from which modern connectionist feedforward models emerged.

## Exam-Relevant Points

- The single-layer feedforward equation y_q = K · (Σ_i (x_i · w_iq) − b_q) — know each component and its role.
- A single-layer network (no hidden layer) can only learn linearly separable functions; hidden layers are required for non-linear decision boundaries.
- In a feedforward network the dependency graph is a DAG (directed acyclic graph) — no recurrence.
- The number of learnable parameters in a single fully-connected layer is (p × q) weights + q biases.
- CMAC's one-step convergence property distinguishes it from iterative gradient-based training.
- The activation function K is what gives multi-layer networks their representational power; without non-linearity, stacking layers adds no capacity.
