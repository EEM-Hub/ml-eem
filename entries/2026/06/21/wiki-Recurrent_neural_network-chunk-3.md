---
source: chunks/wiki-Recurrent_neural_network-chunk-3.md
source_url: https://en.wikipedia.org/wiki/Recurrent_neural_network
---

## Recurrent Neural Network Architectures

This page catalogs the major architectural variants of recurrent neural networks (RNNs), from the most general fully connected topology through specialized designs like LSTM and GRU that solve specific training problems, to augmented architectures like Neural Turing Machines that couple RNNs with external memory.

## Key Concepts

- **Fully Recurrent Neural Network (FRNN):** Every neuron's output connects to every neuron's input. The most general RNN topology — all other architectures are special cases with some weights set to zero.
- **Hopfield Network:** An RNN with equally sized cross-layer connections. Requires stationary (non-sequential) inputs. Guarantees convergence. When trained with Hebbian learning, acts as robust content-addressable memory.
- **Elman Network (Simple Recurrent Network):** Three-layer network with context units that store a copy of the previous hidden state via fixed weight-one connections. Enables sequence prediction beyond standard MLP capability.
- **Jordan Network:** Like Elman, but context units receive input from the output layer (not hidden layer) and have self-recurrent connections. Context units are called the "state layer."
- **LSTM (Long Short-Term Memory):** Most widely used RNN architecture. Designed to solve the vanishing gradient problem using "forget gates." Allows error to flow backward through unlimited virtual layers, enabling learning over thousands or millions of time steps. Can recognize context-sensitive languages (unlike HMM-based models). "Deep LSTM" stacks multiple LSTM layers.
- **GRU (Gated Recurrent Unit):** Simplified LSTM (introduced 2014) with fewer parameters — lacks an output gate. Performance is comparable to LSTM on music modeling and speech signal tasks; no clear winner between the two.
- **Bidirectional Associative Memory (BAM):** Hopfield variant storing associative data as vectors. Two-layer network where either layer can serve as input. Uses matrix and its transpose for bidirectionality. Prefers bipolar over binary encoding.
- **Echo State Network (ESN):** Sparsely connected random hidden layer where only output weights are trainable. Good at reproducing time series. Spiking neuron variant is called a liquid state machine.
- **Recursive Neural Network:** Applies the same weights recursively over a differentiable graph structure in topological order. RNNs are the special case where the graph is a linear chain. Applied to NLP; tensor-based variant is the recursive neural tensor network.
- **Neural Turing Machine (NTM):** RNN coupled to external memory, analogous to a Turing machine but differentiable end-to-end and trainable with gradient descent.
- **Differentiable Neural Computer (DNC):** Extension of NTM with fuzzy memory addressing and chronological recording.
- **Neural Network Pushdown Automata (NNPDA):** Like NTMs but with differentiable analog stacks instead of tapes; complexity similar to context-free grammar recognizers.
- **RNNs are Turing complete** — they can run arbitrary programs on arbitrary input sequences.

## Commands and Syntax

**Elman network equations:**
- Hidden state: `h_t = σ_h(W_h · x_t + U_h · h_{t-1} + b_h)`
- Output: `y_t = σ_y(W_y · h_t + b_y)`

**Jordan network equations:**
- Hidden state: `h_t = σ_h(W_h · x_t + U_h · s_t + b_h)`
- Output: `y_t = σ_y(W_y · h_t + b_y)`
- State: `s_t = σ_s(W_{s,s} · s_{t-1} + W_{s,y} · y_{t-1} + b_s)`

**Variable definitions:** `x_t` = input vector, `h_t` = hidden layer vector, `s_t` = state vector, `y_t` = output vector, `W`, `U`, `b` = parameter matrices/vector, `σ` = activation function.

## Relationships

- **Vanishing gradient problem** → directly motivated LSTM and GRU designs
- **Hebbian learning** → training method that gives Hopfield networks content-addressable memory properties
- **Multilayer perceptron** → Elman/Jordan networks extend MLPs with temporal state
- **Hidden Markov models** → LSTM surpasses HMMs by recognizing context-sensitive (not just regular) languages
- **Turing machines / Von Neumann architecture** → NTMs and DNCs are differentiable analogs
- **Context-free grammars** → NNPDAs match this complexity class via analog stacks
- **Spiking neural networks** → liquid state machines are the spiking variant of echo state networks
- **Automatic differentiation (reverse mode)** → training method for recursive neural networks
- **GRU vs LSTM** → GRU is a simplification of LSTM; empirically similar performance, no clear winner

## Exam-Relevant Points

- LSTM was designed specifically to solve the **vanishing gradient problem**; forget gates are the key mechanism.
- GRU has **fewer parameters** than LSTM because it lacks an output gate; performance is empirically comparable.
- Hopfield networks require **stationary inputs** (not sequences) and guarantee convergence.
- Elman networks feed **hidden layer → context units**; Jordan networks feed **output layer → context units** (state layer).
- Both Elman and Jordan networks are called **Simple Recurrent Networks (SRN)**.
- A fully recurrent network is the most general topology — all others are special cases with zero-weighted connections.
- RNNs are **Turing complete**.
- Echo state networks only train the **output weights**; the hidden layer is random and fixed.
- Neural Turing Machines are **differentiable end-to-end**, enabling gradient descent training.
- LSTM can learn dependencies across **thousands or millions of time steps**.
- Recursive neural networks operate over **graph structures in topological order**; a linear-chain graph is the RNN special case.
- DNCs extend NTMs with **fuzzy memory addressing** and **chronological records**.
