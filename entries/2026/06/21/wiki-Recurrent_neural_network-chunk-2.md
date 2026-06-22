---
source: chunks/wiki-Recurrent_neural_network-chunk-2.md
source_url: https://en.wikipedia.org/wiki/Recurrent_neural_network
---

## RNN Configurations and Data Flow Architectures

This page covers the major structural configurations of recurrent neural networks — how individual RNN units are composed into larger architectures. An RNN model is factored into **configuration** (how multiple RNNs are wired together in a data flow) and **architecture** (the internal design of each RNN unit, e.g., LSTM, GRU). The configurations range from the standard single-layer RNN to stacked, bidirectional, encoder-decoder, and multi-dimensional variants.

## Key Concepts

- **Standard RNN** is a function f_θ: (x_t, h_t) → (y_t, h_{t+1}) mapping an input and hidden state to an output and updated hidden state. The hidden vector h_t acts as "memory" — a partial record of all prior inputs.
- **Unfolding** the RNN across time steps produces a diagram that resembles layers, but these are time steps, not depth layers. This is a common source of confusion.
- **Stacked (Deep) RNN** chains multiple RNN layers vertically: layer k's output sequence becomes layer k+1's input sequence. Each layer has its own parameters θ_k and hidden state h_{k,t}. No conceptual limit to depth.
- **Bidirectional RNN (biRNN)** runs two RNNs — one forward, one backward — over the same sequence. Outputs are concatenated at each position: (y_t, y'_t). This lets each token be processed in context of both past and future.
- **Encoder-decoder (seq2seq)** connects two RNNs front-to-back: the encoder compresses an input sequence into hidden vectors, and the decoder generates an output sequence from those vectors. Optionally includes an attention mechanism.
- **PixelRNN** extends RNNs to 2D data (e.g., images). The **diagonal BiLSTM** variant processes a grid using two LSTMs — one from top-left to bottom-right, one from top-right to bottom-left — where each cell depends on hidden/cell states from above and to the side.

## Commands and Syntax

No CLI commands. Key mathematical formulations:

- **Standard RNN**: f_θ: (x_t, h_t) → (y_t, h_{t+1})
- **Stacked RNN layer k**: f_{θ_k}: (x_{k-1,t}, h_{k,t}) → (x_{k,t}, h_{k,t+1})
- **Bidirectional output**: concatenation of forward and backward outputs at each timestep — ((y_0, y'_0), (y_1, y'_1), ..., (y_N, y'_N))
- **Diagonal BiLSTM**: x_{i,j} depends on (h_{i-1,j}, c_{i-1,j}) and (h_{i,j-1}, c_{i,j-1})

## Relationships

- **Architecture vs. Configuration**: Configuration is the data flow wiring; architecture (LSTM, GRU, etc.) is the internal cell design. These are orthogonal — any configuration can use any architecture.
- **ELMo** (2018) is a stacked bidirectional LSTM that takes character-level inputs and produces word-level embeddings — a concrete application of stacked + bidirectional configuration.
- **Encoder-decoder RNNs** were state-of-the-art for neural machine translation (2014–2017) and were a direct precursor to the **Transformer** architecture.
- **Attention mechanism** was added to encoder-decoder RNNs to address the bottleneck of compressing all input information into a fixed-size vector.
- **PixelRNN** connects RNNs to image generation / autoregressive modeling over 2D grids.

## Exam-Relevant Points

- The distinction between configuration (data flow) and architecture (cell design) is fundamental — be able to name configurations (standard, stacked, bidirectional, encoder-decoder) separately from architectures (LSTM, GRU, vanilla).
- The hidden state h_t is the RNN's memory mechanism; it carries information forward across time steps.
- Unfolded RNN diagrams show **time steps**, not depth layers — a common exam trap.
- Stacked RNNs add depth by feeding one layer's output as the next layer's input; each layer has independent parameters.
- Bidirectional RNNs **concatenate** forward and backward outputs — they do not average or add them.
- Encoder-decoder with attention was the bridge from RNN-era to Transformer-era NMT.
- ELMo = stacked bidirectional LSTM; know it as an example of combining stacking + bidirectionality.
- PixelRNN's diagonal BiLSTM conditions each pixel on states from above **and** to the left (or right), enabling 2D autoregressive generation.
