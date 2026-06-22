---
source: chunks/wiki-Transformer_deep_learning_architecture-chunk-3.md
source_url: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)
---

## Transformer Architecture: Core Components and Mechanisms

This page provides a detailed technical walkthrough of the original transformer architecture as described in "Attention Is All You Need." It covers the full data pipeline from raw text to output probabilities: tokenization, embedding, positional encoding, the encoder-decoder structure, feedforward networks, and the scaled dot-product attention mechanism.

## Key Concepts

- **Four primary components** of all transformers: tokenizer, embedding layer, transformer layers (attention + feedforward), and un-embedding layer.
- **Tokenization** is a three-step process: preprocessing/pretokenization (splitting text into coarse segments), tokenization (segmenting into vocabulary tokens), and integer ID assignment.
- **Subword tokenization**: tokens are not necessarily full words; common algorithms are **Byte Pair Encoding (BPE)** and **Unigram Language Model (ULM)**.
- **Vocabulary size** is the key hyperparameter during vocabularization — small vocabularies produce many small tokens per word; large vocabularies can dedicate tokens to full words.
- **[UNK] token**: a special vocabulary token used as a stand-in for any string not in the vocabulary.
- **Embedding**: converts integer token IDs into dense vectors via a lookup table (equivalent to multiplying a one-hot vector by an embedding matrix M). The vector dimension is called **hidden size / embedding size (d_emb)**, written as d_model in the original paper.
- **Un-embedding**: converts final vector representations back to a probability distribution over tokens via a linear layer + softmax: `UnEmbed(x) = softmax(xW + b)`. The matrix shape is (d_emb, |V|).
- **Weight tying**: using the transpose of the embedding matrix as the un-embedding matrix to halve embedding parameters and prevent training divergence.
- **Positional encoding**: provides token position information using sinusoidal functions. Key property: shifts are linear transformations, enabling the model to attend by relative position.
- **Encoder-decoder architecture**: encoder layers process all input tokens together via self-attention; decoder layers use both cross-attention (to encoder output) and self-attention (over generated tokens so far).
- **Feedforward network (FFN)**: 2-layer MLP applied per position. Intermediate size is typically 4x the embedding size (d_ffn = 4 * d_emb). Contains most of the parameters in a transformer.
- **Scaled dot-product attention**: each attention head learns three weight matrices — W^Q (query), W^K (key), W^V (value). Attention is non-symmetric: token i attending to token j does not imply j attends to i.
- **Scaling factor**: attention scores are divided by sqrt(d_k) to stabilize gradients during training.

## Commands and Syntax

**Core attention formula:**
```
Attention(Q, K, V) = softmax(QK^T / sqrt(d_k)) * V
```

**Query/Key/Value computation:**
```
Q = X_query * W^Q
K = X_key * W^K
V = X_value * W^V
```

**Feedforward network:**
```
FFN(x) = phi(x * W^(1) + b^(1)) * W^(2) + b^(2)
```
where phi is the activation function (ReLU in the original).

**Un-embedding:**
```
UnEmbed(x) = softmax(x * W + b)
```

**Positional encoding (sinusoidal):**
```
f(t)_{2k} = sin(t / r^k)
f(t)_{2k+1} = cos(t / r^k)
where r = N^(2/d), N = 10000 (original paper)
```

**Key software implementations for tokenization:**
- `tokenizers` (Hugging Face, Python/Rust)
- `sentencepiece` (Python/C++, can process entire sentences as pretokens)

## Relationships

- **Tokenization** connects to information retrieval and NLP history — modern "tokenization" was historically called "pretokenization" in older systems.
- **Positional encoding** enables the transformer to emulate **convolutional neural network** behavior through learned relative-position attention, bridging the gap between attention-based and convolution-based language models.
- **Encoder-decoder** architecture descends from earlier **seq2seq** models but replaces recurrence with attention.
- **Embedding/un-embedding** are near-inverses; weight tying formally links them.
- **FFN layers** are where most parameters reside, contrasting with attention layers which handle token interaction — this split between "memory" (FFN) and "communication" (attention) is a recurring theme in transformer analysis.
- **BPE** tokenization is shared with data compression origins (byte pair encoding).

## Exam-Relevant Points

- The attention scaling factor is **1/sqrt(d_k)**, not 1/d_k — this specific choice stabilizes gradients.
- FFN intermediate size is conventionally **4x the embedding size** in GPT-2 and BERT families.
- The original transformer used **ReLU** activation in feedforward layers.
- Positional encoding uses **N = 10000** in the original paper.
- The sinusoidal positional encoding's key property: **position shifts can be represented as linear transformations** (matrix multiplications), enabling relative position attention.
- **Weight tying** means using the transpose of the embedding matrix for un-embedding — reduces parameters and prevents divergence.
- Attention is **non-symmetric**: high attention from i to j does not imply high attention from j to i, because W^Q and W^K are different matrices.
- The un-embedding matrix has shape **(d_emb, |V|)** — maps from embedding dimension to vocabulary size.
- Encoder uses **self-attention only**; decoder uses both **self-attention and cross-attention**.
- Softmax is applied row-wise to the attention score matrix to normalize weights per query token.
- All vectors are **row vectors** by convention in the original paper (multiply weight matrices on the right).
