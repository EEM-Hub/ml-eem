---
source: chunks/wiki-Deep_learning-chunk-3.md
source_url: https://en.wikipedia.org/wiki/Deep_learning
---

## Neural Networks, Deep Neural Networks, and Deep Learning Hardware

This page covers the fundamentals of artificial neural networks (ANNs), the architecture and challenges of deep neural networks (DNNs), and the specialized hardware that has evolved to support deep learning workloads. It spans from biological inspiration through architectural variants to the computational infrastructure required for training at scale.

## Key Concepts

- **Artificial Neural Networks (ANNs)**: Computing systems inspired by biological neural networks; composed of connected artificial neurons organized in layers that learn from examples rather than explicit programming.
- **Neurons, synapses, weights**: Neurons have state (typically real numbers between 0 and 1); synapses transmit signals between neurons; weights modulate signal strength and are adjusted during learning.
- **Layer organization**: Signals flow from input layer to output layer, with intermediate layers performing different transformations on inputs.
- **Deep Neural Network (DNN)**: An ANN with multiple layers between input and output, enabling compositional modeling of complex non-linear relationships.
- **Compositional modeling**: Extra layers allow features to be composed from lower-layer primitives, potentially requiring fewer units than an equivalent shallow network.
- **Feedforward vs. Recurrent**: Feedforward networks have unidirectional data flow (input to output); recurrent neural networks (RNNs) allow data to flow in any direction, suited for sequential tasks like language modeling.
- **Convolutional Neural Networks (CNNs)**: Specialized for computer vision; also applied to acoustic modeling for speech recognition.
- **Long Short-Term Memory (LSTM)**: Particularly effective variant of RNNs for language modeling tasks.
- **Overfitting in DNNs**: Additional layers of abstraction allow modeling of rare dependencies in training data, making DNNs especially prone to overfitting.
- **Regularization methods**: L2 (weight decay), L1 (sparsity), dropout (randomly omitting hidden units), unit pruning, and data augmentation (cropping, rotating) all combat overfitting.
- **Hyperparameter challenges**: Size (layers and units per layer), learning rate, and initial weights must be tuned; exhaustive grid search is often infeasible.
- **CMAC (Cerebellar Model Articulation Controller)**: Alternative neural network that converges in one step, requires no learning rate or randomized initial weights, with linear training complexity.

## Commands and Syntax

No specific CLI commands or configuration syntax are described in this source. The content is conceptual/architectural.

## Relationships

- **Backpropagation**: The key training algorithm for neural networks, deviating from biological inspiration by passing error information backward through layers.
- **Convolutional Neural Networks**: Subtype of DNN specialized for spatial data (vision, acoustic modeling).
- **Recurrent Neural Networks / LSTM**: Subtype of DNN for sequential data (language, time series).
- **Regularization**: Connects to optimization theory (L1/L2 norms) and practical training techniques (dropout, data augmentation).
- **Hardware acceleration**: GPUs, TPUs, NPUs, and emerging photonic/semiconductor technologies are co-evolving with network architectures to enable training at scale.
- **Hyperparameter optimization**: Grid search and batching strategies connect to computational cost management.

## Exam-Relevant Points

- A DNN is specifically defined as an ANN with **multiple layers between input and output** — not just any multi-layer network.
- DNNs are **feedforward by default**; recurrent architectures are a distinct category.
- **Dropout** regularization works by randomly omitting hidden units during training to prevent co-adaptation on rare dependencies.
- **L2 regularization = weight decay**; **L1 regularization = sparsity**. Know the distinction.
- Sparse multivariate polynomials are **exponentially easier** to approximate with deep networks than shallow ones — a key theoretical justification for depth.
- **GPUs displaced CPUs** as dominant training hardware by 2019 for large-scale commercial AI.
- OpenAI found a **300,000x increase** in compute from AlexNet (2012) to AlphaZero (2017), with a **3.4-month doubling time**.
- **TPUs** (Google), **NPUs** (Huawei), and **Cerebras WSE-2** are purpose-built deep learning processors.
- **Photonic hardware accelerators** offer two advantages over electronic: (1) massively parallel data transfer via wavelength division multiplexing, and (2) extremely high data modulation speeds — capable of trillions of multiply-accumulate operations per second.
- **CNNs** are associated with computer vision; **RNNs/LSTMs** are associated with language modeling — know which architecture maps to which domain.
- **Data augmentation** (cropping, rotating) is a regularization strategy that increases effective training set size.
- **Batching** (computing gradients on multiple examples at once) is a key trick for speeding up training computation.
