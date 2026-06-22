---
source: chunks/wiki-Recurrent_neural_network-chunk-1.md
source_url: https://en.wikipedia.org/wiki/Recurrent_neural_network
---

## Recurrent Neural Networks (RNNs): Architecture and Sequential Data Processing

Recurrent neural networks (RNNs) are a class of artificial neural networks designed specifically for processing sequential data — text, speech, and time series — where element order matters. Unlike feedforward networks that process inputs independently, RNNs use recurrent connections that feed a neuron's output at one time step back as input at the next, enabling them to capture temporal dependencies. While historically dominant for sequence tasks, RNNs have been largely supplanted by transformers for many applications, though they remain relevant where computational efficiency or real-time processing is critical.

## Key Concepts

- **Recurrent unit**: The fundamental building block; maintains a **hidden state** (a form of memory) updated at each time step based on current input and the previous hidden state.
- **Vanishing gradient problem**: Traditional RNNs struggle to learn long-range dependencies because gradients diminish during backpropagation through many time steps.
- **LSTM (Long Short-Term Memory)**: Invented by Hochreiter and Schmidhuber (1995/1997); became the standard RNN variant by using gating mechanisms to preserve long-term dependencies. The default RNN architecture choice for most of the deep learning era.
- **GRU (Gated Recurrent Unit)**: A more computationally efficient alternative to LSTM with fewer parameters.
- **Bidirectional RNN (BRNN)**: Uses two RNNs processing the same input in opposite directions (forward and backward), often combined with LSTM to form bidirectional LSTM.
- **Encoder-decoder / Seq2seq**: Architecture using two RNNs (typically LSTMs) for sequence transduction (e.g., machine translation). Originated ~2014 and was instrumental in developing attention mechanisms.
- A fully cross-coupled recurrent network is equivalent to an infinitely deep feedforward network (Rosenblatt, 1961).
- Modern RNN networks are mainly based on two architectures: LSTM and BRNN.

## Commands and Syntax

No CLI commands or configuration syntax apply directly. Key architectural patterns:

- **Unrolling**: An RNN is conceptually "unfolded in time" for training, creating a layer per time step — a 1993 neural history compressor required >1000 such layers.
- **Seq2seq pattern**: Encoder RNN processes input sequence into a fixed representation; decoder RNN generates output sequence from that representation.

## Relationships

- **Feedforward neural networks**: RNNs extend feedforward networks by adding recurrent connections; feedforward networks lack temporal memory.
- **LSTM / GRU**: Specialized RNN variants that solve the vanishing gradient problem with gating mechanisms.
- **Transformers**: Replaced RNNs as the dominant sequence architecture by using self-attention instead of recurrence, offering better parallelization and long-range dependency handling.
- **Attention mechanisms**: Developed in the context of RNN-based seq2seq models; became the core of transformers.
- **CNNs**: LSTM combined with CNNs improved tasks like automatic image captioning.
- **Statistical mechanics / Ising model**: RNNs have a parallel origin in statistical mechanics — the Hopfield network connects to the Sherrington-Kirkpatrick spin glass model.
- **Recursive neural networks**: Distinct from recurrent neural networks despite the similar name (recursive networks operate on tree structures).

## Exam-Relevant Points

- RNNs process sequential data by maintaining a hidden state updated at each time step — this is the core differentiator from feedforward networks.
- The **vanishing gradient problem** is the fundamental limitation of vanilla RNNs; LSTM was specifically designed to address it (1995/1997).
- **LSTM** is the standard/default RNN architecture for long-term dependencies; **GRU** is the lightweight alternative.
- **Bidirectional RNNs** process input in both forward and backward directions — critical for tasks where future context matters (e.g., speech recognition, NLP).
- **Seq2seq** (encoder-decoder) architecture uses two RNNs and was state-of-the-art for machine translation before transformers.
- Transformers have largely replaced RNNs for NLP due to superior parallelizability and long-range dependency handling, but RNNs remain preferred for real-time processing and computationally constrained environments.
- Key application domains: handwriting recognition, speech recognition, NLP, neural machine translation, image captioning (with CNNs), text-to-speech.
- Historical lineage: neuroscience (Cajal's recurrent circuits, 1901) and statistical mechanics (Ising model, 1920s) both contributed to RNN development.
- Hopfield network (1982) connected recurrent neural networks to statistical mechanics (spin glass theory).
- The seq2seq papers of 2014 were instrumental in the development of attention mechanisms, which led directly to the transformer architecture.
