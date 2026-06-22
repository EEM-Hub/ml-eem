---
source: chunks/wiki-Neural_network_28machine_learning29-chunk-1.md
source_url: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29
---

## Neural Networks in Machine Learning

Neural networks (NNs) are computational models inspired by biological neural networks in the brain. They consist of interconnected artificial neurons organized in layers, trained on large datasets using compute-intensive processes (typically GPU-accelerated). This page covers the foundational structure, key architectural variants, and broad applications of neural networks.

## Key Concepts

- **Artificial neuron**: A computational unit that receives input signals, processes them through a non-linear **activation function**, and outputs a real number to connected neurons.
- **Weights**: Parameters on edges (connections) between neurons that determine signal strength; adjusted during training.
- **Layers**: Neurons are organized into an **input layer**, one or more **hidden layers**, and an **output layer**. Each layer transforms its inputs.
- **Deep neural network**: A network with at least two hidden layers, capable of learning hierarchical representations.
- **Training**: A compute-intensive optimization process that adjusts weights; accelerated by GPUs and dependent on large datasets.
- **False positives**: Weak or spurious weight associations can cause incorrect classifications (e.g., a shell shape triggering a sea urchin detection).

## Commands and Syntax

Not applicable — this is a conceptual/theoretical topic. No CLI commands or configuration syntax are described.

## Relationships

- **Convolutional Neural Networks (CNNs)**: Architectural variant optimized for computer vision tasks.
- **Recurrent Neural Networks (RNNs)**: Variant for sequential data (speech, time series); includes LSTM and GRU subtypes.
- **Transformers**: Attention-based architecture enabling long-range dependency modeling; foundation for large language models (LLMs).
- **Activation functions**: Core mathematical component determining neuron output behavior.
- **Supervised / Unsupervised / Reinforcement learning**: Neural networks serve as the computational backbone for all major ML paradigms.
- **Related architectures**: Autoencoders, GANs, Diffusion models, Boltzmann machines, Spiking neural networks, Physics-informed neural networks (PINNs).

## Exam-Relevant Points

- A neural network is "deep" if it has **at least two hidden layers**.
- Neuron output is computed by a **non-linear activation function** applied to the **sum of weighted inputs**.
- **Weights** are the learnable parameters adjusted during training.
- **CNNs** → computer vision; **RNNs** → sequential data; **Transformers** → long-range dependencies and LLMs.
- Training requires both **large datasets** and **GPU acceleration**.
- Signals flow from input layer → hidden layers → output layer (feedforward path).
- Weak weight associations can produce **false positives** — understanding this is key to model evaluation and error analysis.
