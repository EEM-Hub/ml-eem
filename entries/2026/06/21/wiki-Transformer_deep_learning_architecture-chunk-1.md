---
source: chunks/wiki-Transformer_deep_learning_architecture-chunk-1.md
source_url: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)
---

## Transformer Architecture (Deep Learning)

The transformer is a family of neural network architectures introduced in the 2017 paper "Attention Is All You Need" by Google researchers. It replaces recurrence with a parallel multi-head attention mechanism, enabling faster training and forming the foundation for modern large language models (LLMs), vision models, and multimodal systems.

## Key Concepts

- **Multi-head attention mechanism**: The core innovation — each token attends to all other (unmasked) tokens in parallel across multiple attention heads, amplifying important signals and diminishing less relevant ones.
- **Token and embedding pipeline**: Text is tokenized into numerical representations, then each token is mapped to a vector via a word embedding lookup table.
- **Positional encoding**: Because self-attention is permutation-invariant (order-agnostic), transformers must inject positional information — either through fixed positional encodings or learned positional embeddings — so token order affects output.
- **Context window**: Defines the scope within which tokens are contextualized with each other via attention.
- **No recurrent units**: Unlike RNNs/LSTMs, transformers have no sequential recurrence, enabling significantly more parallelism and shorter training times.
- **Three architectural variants**:
  - **Encoder-only** — optimized for representation learning (e.g., BERT)
  - **Decoder-only** — optimized for autoregressive generation (e.g., GPT)
  - **Encoder-decoder** — optimized for conditional sequence-to-sequence tasks (e.g., original transformer, T5)
- **Pre-LN vs. Post-LN**: The original 2017 transformer used post-layer-normalization; many modern implementations use pre-layer-normalization for more stable training.

## Commands and Syntax

No CLI commands apply. The core mathematical operation is scaled dot-product attention:

```
Attention(Q, K, V) = softmax(QK^T / √d_k) V
```

Where Q (queries), K (keys), V (values) are linear projections of the input, and d_k is the key dimension (scaling factor prevents vanishing gradients in softmax).

Multi-head attention runs this operation h times in parallel with different learned projections, then concatenates and projects:

```
MultiHead(Q, K, V) = Concat(head_1, ..., head_h) W^O
where head_i = Attention(Q W_i^Q, K W_i^K, V W_i^V)
```

## Relationships

- **Predecessors**: Replaces recurrent architectures (RNNs, LSTMs, GRUs) that processed sequences sequentially — transformer parallelism was the key improvement.
- **Attention mechanism**: Builds on earlier attention work (Bahdanau attention for machine translation), but makes attention the *sole* mechanism rather than an add-on to recurrence.
- **Downstream models**: Foundation for GPT family (decoder-only), BERT (encoder-only), T5 (encoder-decoder), Vision Transformers (ViT), Whisper (audio), and multimodal models.
- **Training paradigms**: Enables transfer learning and pre-training at scale — models are pre-trained on large corpora, then fine-tuned or prompted for specific tasks.
- **Competing architectures**: State-space models (e.g., Mamba) have emerged as alternatives that handle long sequences with linear rather than quadratic complexity.
- **Application domains**: NLP, computer vision, reinforcement learning, audio processing, robotics, game-playing (chess), disaster response, multimodal learning.

## Exam-Relevant Points

- The transformer was introduced in "Attention Is All You Need" (2017) by Google researchers.
- Self-attention is permutation-invariant — positional encoding is required to preserve sequence order.
- Transformers require less training time than RNNs/LSTMs because they eliminate sequential recurrence and process all positions in parallel.
- The three variant families (encoder-only, decoder-only, encoder-decoder) map to distinct task categories: representation, generation, and sequence-to-sequence.
- BERT = encoder-only (bidirectional); GPT = decoder-only (autoregressive/causal).
- Multi-head attention allows the model to attend to information from different representation subspaces at different positions simultaneously.
- The original application was machine translation; transformers have since generalized to virtually all deep learning domains.
- The context window determines the maximum number of tokens that can attend to each other — a fundamental constraint on transformer capability.
