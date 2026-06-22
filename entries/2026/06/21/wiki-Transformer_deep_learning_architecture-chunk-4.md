---
source: chunks/wiki-Transformer_deep_learning_architecture-chunk-4.md
source_url: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)
---

## Full Transformer Architecture: Sublayers, Residual Connections, and Variants

This page details the internal structure of the transformer architecture, covering the sublayer composition of encoder and decoder layers, the role of residual connections and layer normalization, pseudocode for a complete forward pass, and the taxonomy of transformer variants (encoder-only, decoder-only, encoder-decoder, prefixLM).

## Key Concepts

- **Encoder layer sublayers (2):** self-attention, feedforward network.
- **Decoder layer sublayers (3):** causally masked self-attention, cross-attention (attending to encoder output), feedforward network.
- **Residual connections:** Each sublayer output is added to its input (`x ↦ F(x) + x`), preventing vanishing gradients and stabilizing training.
- **Layer normalization (LayerNorm):** Applied individually to each vector (per-token), providing numerical stability. Two conventions exist:
  - **Post-LN (original 2017):** `LayerNorm(x + Sublayer(x))` — harder to train, requires learning rate warm-up and careful hyperparameter tuning.
  - **Pre-LN (proposed 2018):** `x + Sublayer(x_normalized)` where `x_normalized = LayerNorm(x)` — easier to train, no warm-up needed, faster convergence.
- **Feedforward and LayerNorm** are applied independently to each position/vector (no cross-token interaction).
- **Final LayerNorm** is applied after all encoder/decoder layers (in pre-LN convention).

## Commands and Syntax

**Pre-LN Encoder-Decoder Forward Pass (pseudocode):**

1. **Encoder:** tokenize → embed + positional embedding → for each layer: (LayerNorm → self-attention + residual) → (LayerNorm → FFN + residual) → final LayerNorm
2. **Decoder:** tokenize → embed + positional embedding → for each layer: (LayerNorm → masked self-attention + residual) → (LayerNorm → cross-attention over encoder output + residual) → (LayerNorm → FFN + residual) → final LayerNorm → unembed to output distributions

Key detail in cross-attention: `layer.multihead_attention(z_d, z_e, z_e)` — queries come from decoder, keys and values come from encoder output.

## Relationships

- **Residual connections** originate from ResNet; essential for deep transformer stacking.
- **Layer normalization** is distinct from batch normalization; it normalizes across features within a single example rather than across a batch.
- **Encoder-only models** (e.g., BERT): used for text embedding and representation learning; less common now since encoder-decoder models can subsume this.
- **Decoder-only models** (e.g., GPT series, Chinchilla): no cross-attention (nothing to cross-attend to); only causally masked self-attention + FFN. Dominant architecture for modern LLMs and text generation.
- **Encoder-decoder models** (e.g., T5): full original architecture with possible minor improvements (activation functions, pre-LN).
- **PrefixLM:** Decoder-only with a modified mask — prefix tokens attend bidirectionally (like an encoder), subsequent tokens attend causally. Rarely used in practice but theoretically interesting.
- **Hybrid models:** e.g., Google Translate (2020) used transformer encoder + RNN decoder for speed, since transformer decoders didn't improve quality enough to justify the latency cost.

## Exam-Relevant Points

- Encoder has **2 sublayers** per layer; decoder has **3 sublayers** per layer — know which sublayer is which.
- In decoder-only models, the cross-attention sublayer is **removed entirely**, leaving only 2 sublayers (masked self-attention + FFN).
- **Pre-LN vs. Post-LN:** pre-LN normalizes *before* the sublayer; post-LN normalizes *after* the residual addition. Pre-LN is easier to train (no warm-up needed). The original 2017 paper used post-LN.
- Residual connection formula: `x ↦ F(x) + x` — the identity shortcut preserves gradient flow.
- In cross-attention, **queries come from the decoder** and **keys/values come from the encoder** — this is how the decoder "reads" the encoded input.
- BERT = encoder-only; GPT = decoder-only; T5 = encoder-decoder.
- PrefixLM uses a block mask where prefix positions attend bidirectionally and generated positions attend causally.
- Google Translate's hybrid (transformer encoder + RNN decoder) illustrates that architectural choices are driven by quality-vs-latency tradeoffs, not theoretical purity.
