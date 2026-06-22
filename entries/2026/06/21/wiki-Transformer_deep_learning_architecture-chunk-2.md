---
source: chunks/wiki-Transformer_deep_learning_architecture-chunk-2.md
source_url: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)
---

## Transformer Architecture: History and Training Methods

This page traces the evolution of sequence modeling from early recurrent neural networks through the development of the transformer architecture, and covers the key training methods used for transformer models. It contextualizes how attention mechanisms emerged as replacements for recurrence, enabling parallelization and sparking the modern AI boom.

## Key Concepts

- **Vanishing gradient problem**: Plain RNNs (e.g., Elman networks, 1990) could not propagate information effectively over long sequences, limiting practical sequence modeling.
- **LSTM (1997)**: Introduced multiplicative gating units to mitigate vanishing gradients; became the standard for long-sequence modeling until 2017. Still sequential — cannot parallelize across tokens.
- **GRU vs LSTM**: GRUs were shown to be neither better nor worse than LSTMs for seq2seq tasks.
- **Seq2seq bottleneck**: Early encoder-decoder models compressed the entire input into a fixed-size vector, degrading quality on long inputs. Evidence: reversing input sentences improved translation quality.
- **Attention mechanism**: The "RNN search" model added attention to seq2seq, allowing the decoder to reference all encoder states rather than just the final fixed-size vector.
- **Decomposable attention (2016)**: Applied self-attention to feedforward networks (not RNNs), achieving SOTA on textual entailment with 10x fewer parameters — demonstrated attention could work without recurrence.
- **Transformer (2017-06-12)**: "Attention Is All You Need" — 100M-parameter encoder-decoder model. Removed recurrence entirely, processing all tokens in parallel via multi-head dot-product attention. Quadratic computation cost in context window size (vs. linear for RNNs).
- **Fast weight controllers (1992)**: A precursor where a slow network generates keys/values for a fast network; later shown equivalent to the unnormalized linear transformer.
- **Pre-LN vs Post-LN**: Applying layer normalization before (not after) attention and feedforward layers stabilizes training and removes the need for learning rate warmup.

## Commands and Syntax

No CLI commands. Key formulas and procedures:

- **Masked language modeling loss**:
  `Loss = -Σ (over masked tokens t) ln(P(t | context))`

- **Learning rate warmup** (original paper recommendation): Linearly scale learning rate from 0 to max over ~2% of total training steps, then decay.

- **Three language modeling task types**:
  - **Masked**: Random tokens hidden, model predicts them (BERT)
  - **Autoregressive**: Predict next token sequentially from left to right (GPT)
  - **PrefixLM**: Given a prefix as context, predict continuation tokens (T5)

## Relationships

- **RNN → LSTM → Seq2seq → Attention → Transformer**: A clear evolutionary chain where each step solved a limitation of the previous.
- **Encoder-only (BERT)** vs **Decoder-only (GPT)** vs **Encoder-decoder (original Transformer, T5)**: Three architectural variants emerged from the base transformer for different task types.
- **Self-supervised pretraining → supervised fine-tuning**: The dominant two-phase training paradigm for transformers, using large unlabeled corpora (e.g., The Pile) then task-specific data.
- **Vision Transformer (ViT)**: Extended transformers beyond NLP to computer vision; in turn stimulated new CNN research.
- **Multimodal transformers**: Applied to speech, robotics, image/video generation (DALL-E, Stable Diffusion 3, Sora) within days of the original paper.
- **Google Translate evolution**: Statistical MT (10 years) → RNN seq2seq (2016, 9 months) → transformer-encoder + RNN-decoder (2020).

## Exam-Relevant Points

- The transformer has **quadratic** computational cost in context window size; RNNs are linear but sequential.
- LSTM uses **multiplicative gating units** (conceptually distinct from additive attention).
- The original transformer paper was published **2017-06-12** with a **100M-parameter** encoder-decoder model.
- **Parallelizability** (due to removing recurrence and using independent attention heads) was the key practical advantage driving transformer adoption.
- **Pre-LN Transformer** (layer norm before attention/FFN) is more commonly used than the original post-LN; it removes the need for learning rate warmup.
- **Masked LM ≠ masked attention**: "Masked" in "masked language modeling" (training task, e.g., BERT) is different from "masked attention" (causal masking in the architecture). Similarly, "prefixLM" (training task) ≠ "prefix language model" (architecture variant).
- BERT = encoder-only (masked task); GPT = decoder-only (autoregressive task); T5 = encoder-decoder (prefixLM task).
- The pretrain-finetune paradigm uses **self-supervised** pretraining on unlabeled data, then **supervised** fine-tuning on labeled task-specific data.
- Decoder-only transformers were being used to generate text (fictitious Wikipedia articles) even before "Attention Is All You Need" was formally published.
