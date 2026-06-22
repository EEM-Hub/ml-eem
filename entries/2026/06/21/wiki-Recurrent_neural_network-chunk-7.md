---
source: chunks/wiki-Recurrent_neural_network-chunk-7.md
source_url: https://en.wikipedia.org/wiki/Recurrent_neural_network
---

## Recurrent Neural Networks — Reference Index and Taxonomy

This page is a navigational index and further-reading list from a broader article on Recurrent Neural Networks (RNNs). It contains no primary instructional content but provides a useful taxonomy of how RNNs fit within the broader AI/ML landscape, along with key references for deeper study.

## Key Concepts

- **RNNs** are classified under **Neural network architectures** alongside LSTMs, GRUs, Echo State Networks, Transformers, CNNs, and others.
- RNNs appear in the broader AI taxonomy as a core **application** of deep learning and artificial neural networks.
- Related architectural variants listed: **LSTM** (Long Short-Term Memory), **GRU** (Gated Recurrent Unit), **Echo State Network**, and the **Neural Turing Machine** / **Differentiable Neural Computer** (which extend recurrent ideas with external memory).
- Key foundational concepts that underpin RNNs include: **backpropagation**, **gradient descent** (and SGD), **activation functions** (sigmoid, softmax, rectifier), **gating**, **attention**, **regularization**, and **loss functions**.
- **Autoregression** is listed as a core AI concept — RNNs are a primary architecture for autoregressive sequence modeling.

## Commands and Syntax

No commands or configuration syntax are present on this page.

## Relationships

- **RNNs → LSTM/GRU**: LSTM and GRU are gated variants of RNNs designed to address vanishing gradient problems.
- **RNNs → Transformers**: Transformers largely replaced RNNs for sequence tasks by using attention instead of recurrence; both appear as peer architectures.
- **RNNs → Mamba**: Mamba (state-space models) is listed as a newer architecture that competes with both RNNs and Transformers for sequence modeling.
- **RNNs → Echo State Networks**: A reservoir computing approach to RNNs where only output weights are trained.
- **Key people**: Jürgen Schmidhuber (LSTM co-inventor, maintains an RNN paper list at IDSIA), Sepp Hochreiter (LSTM, listed via Schmidhuber's group), Geoffrey Hinton, Yoshua Bengio, Alex Graves (sequence transduction with RNNs), John Hopfield (Hopfield networks, a precursor recurrent architecture).
- **RNNs → Language Models**: RNNs were the dominant architecture for language models and NMT before Transformers.
- **Foundational concepts**: Backpropagation through time (BPTT) is an extension of backpropagation for recurrent architectures; gradient descent and its variants (SGD, quasi-Newton) are the optimization methods used to train RNNs.

## Exam-Relevant Points

- **RNN architectural family**: Know that LSTM, GRU, and Echo State Networks are all variants/extensions of the basic RNN architecture.
- **Key reference**: Mandic & Chambers (2001) covers RNN prediction — learning algorithms, architectures, and stability — a foundational text.
- **Taxonomy placement**: RNNs sit under Neural Network Architectures, distinct from CNNs (spatial), Transformers (attention-based), and GANs (generative adversarial).
- **Historical context**: RNN research is strongly associated with Schmidhuber's group at IDSIA (Dalle Molle Institute for Artificial Intelligence Research) and the development of LSTM.
- **Successor architectures**: Transformers and Mamba are the primary architectures that have displaced RNNs in many sequence tasks — understanding why (parallelism, long-range dependencies) is exam-relevant.
- **Gating** is listed as a standalone concept — it is the key mechanism that distinguishes LSTM and GRU from vanilla RNNs.
