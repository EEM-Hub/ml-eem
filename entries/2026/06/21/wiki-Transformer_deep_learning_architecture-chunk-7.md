---
source: chunks/wiki-Transformer_deep_learning_architecture-chunk-7.md
source_url: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)
---

## Transformer Architecture: Foundational Literature and Key References

This page contains the bibliography for the Transformer deep learning architecture, spanning from early connectionist models (1980s) through the original "Attention Is All You Need" paper (2017) to modern applications (2024+). The references trace the intellectual lineage of self-attention, sequence modeling, and the explosion of Transformer-based models across NLP, vision, speech, and reinforcement learning.

## Key Concepts

- **The foundational paper**: Vaswani et al. (2017), "Attention Is All You Need," published at NeurIPS 30 — the single most-cited reference, establishing the Transformer architecture
- **Attention mechanisms predate the Transformer**: Bahdanau et al. (2014) and Luong et al. (2015) introduced attention for neural machine translation in RNN-based encoder-decoder models
- **Predecessor architectures**: LSTMs (Hochreiter & Schmidhuber, 1997) and GRUs (Cho et al., 2014) were the dominant sequence models before Transformers
- **Sequence-to-sequence learning**: Sutskever, Vinyals & Le (2014) established the encoder-decoder paradigm that Transformers later replaced
- **Fast weights and linear attention**: Schmidhuber (1992) proposed fast-weight memories; Katharopoulos et al. (2020) and Schlag et al. (2021) showed linear Transformers are equivalent to fast-weight programmers
- **BERT**: Devlin et al. (2018) introduced bidirectional pre-training using masked language modeling — deployed in nearly every English Google Search query by 2020
- **GPT lineage**: OpenAI's GPT-1 (2018, unsupervised pre-training), GPT-2 (2019, "Better Language Models"), leading to ChatGPT (2022)
- **T5**: Raffel et al. (2020) unified NLP tasks as text-to-text with "Exploring the Limits of Transfer Learning"
- **Vision Transformer (ViT)**: Dosovitskiy et al. (2021), "An Image is Worth 16x16 Words" — extended Transformers to image recognition
- **Conformer**: Gulati et al. (2020) combined convolutions with Transformers for speech recognition
- **Decision Transformer**: Chen et al. (2021) cast reinforcement learning as sequence modeling
- **UL2**: Tay et al. (2023) unified language learning paradigms (masked, causal, prefix LM)
- **Performers**: Choromanski et al. (2020) proposed linear-complexity attention via random feature approximation
- **RWKV**: Peng et al. (2023) reinvented RNNs for the Transformer era with linear complexity

## Commands and Syntax

No commands or configuration syntax — this is a bibliography. However, key implementation resources referenced include:

- **Tensor2Tensor**: Google's open-source library for Transformer research (Kaiser, 2017; Vaswani et al., 2018)
- **Hugging Face Transformers**: Wolf et al. (2020) — the standard library for pre-trained Transformer models
- **OpenAI's finetune-transformer-lm**: Original GPT-1 codebase (GitHub, 2018)
- **Keras NLP**: GPT2Backbone model API for Keras-based implementations

## Relationships

- **Attention evolution**: Connectionist models (1982) → fast weights (1992) → additive attention (Bahdanau, 2014) → multiplicative attention (Luong, 2015) → self-attention (Vaswani, 2017)
- **Sequence modeling evolution**: RNNs → LSTMs (1997) → GRUs (2014) → Seq2Seq with attention → Transformers (2017) → RWKV (2023, linear RNN revival)
- **Pre-training paradigms**: Masked LM (BERT) vs. Causal LM (GPT) vs. Text-to-Text (T5) vs. Unified (UL2)
- **Cross-domain transfer**: NLP origin → Vision (ViT) → Speech (Conformer, Whisper) → RL (Decision Transformer) → Image generation (Rectified Flow Transformers) → Disaster detection → Chess
- **Efficiency line**: Standard O(n²) attention → Performers (linear) → Linear Transformers → RWKV

## Exam-Relevant Points

- The Transformer was introduced in **Vaswani et al., 2017** at **NeurIPS** — know the 8 authors and that all were at Google
- **Bahdanau attention (2014)** is the precursor — additive attention for NMT, predating the Transformer by 3 years
- **BERT (2018)** uses **masked language modeling** (bidirectional); **GPT (2018)** uses **causal language modeling** (autoregressive, left-to-right) — published the same year with opposite pre-training strategies
- **T5 (2020)** frames every NLP task as text-to-text, enabling unified fine-tuning
- The **Illustrated Transformer** (Alammar) is the canonical pedagogical resource
- **Layer normalization placement** matters: Xiong et al. (2020) studied Pre-LN vs. Post-LN in Transformer architecture
- **ViT** divides images into **16×16 patches** treated as tokens — the title itself is exam-worthy
- **Hugging Face Transformers** (Wolf et al., 2020) is the de facto standard library for working with pre-trained models
- **Linear Transformers** (Katharopoulos, 2020) reduce attention from O(n²) to O(n) and are equivalent to **fast-weight programmers** (Schmidhuber, 1992)
- **Weight tying**: Press & Wolf (2017) showed that sharing input/output embeddings improves language models
- **ChatGPT launched November 30, 2022** — built on GPT-3.5 with RLHF
