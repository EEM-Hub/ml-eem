---
source: chunks/wiki-Transformer_deep_learning_architecture-chunk-8.md
source_url: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)
---

## Transformer Architecture: Key References and Ecosystem Map

This page is a reference and navigation appendix from the Transformer architecture article. It provides a curated reading list of seminal and recent papers on transformer internals, plus comprehensive taxonomy tables mapping the transformer's place within Google AI, the broader AI/ML landscape, and the large language model ecosystem. While light on original content, it serves as a roadmap for deeper study.

## Key Concepts

- **"Attention Is All You Need"** (Vaswani et al., 2017) is the foundational transformer paper; the architecture is covered by US Patent 10,452,978, assigned to Google LLC (issued 2019-10-22).
- The transformer sits within Google's neural network lineage: Inception (2014) → WaveNet (2016) → MobileNet (2017) → **Transformer (2017)** → EfficientNet (2019) → Gato (2022).
- Downstream Google models built on transformers: BERT (2018), XLNet (2019), T5 (2019), LaMDA (2021), PaLM (2022), Gemini (2023), Gemma (2024).
- The transformer is the foundation for virtually all modern LLM families: GPT series, Claude, Gemini, Llama, Mistral/Mixtral, Qwen, DeepSeek, and others.
- Related architectures in the broader neural network taxonomy: RNN/LSTM/GRU (recurrent), CNN (convolutional), Vision Transformer (ViT), Mamba (state-space), autoencoders/VAEs, GANs, and Graph Neural Networks.

## Commands and Syntax

No commands or configuration syntax on this page. However, it references key resources for implementation:

- **The Annotated Transformer** (Harvard NLP, 2018) — line-by-line PyTorch implementation walkthrough of the original paper.
- **"Formal Algorithms for Transformers"** (Phuong & Hutter, 2022, arXiv:2207.09238) — pseudocode-level formal specification of transformer algorithms.
- **"A Primer on the Inner Workings of Transformer-based Language Models"** (Ferrando et al., 2024, arXiv:2405.00208) — mechanistic interpretability primer.
- **"The Big LLM Architecture Comparison"** (Raschka, 2026) — comparative analysis of modern LLM architectures from DeepSeek V3 to GLM-5.

## Relationships

- **Training paradigms**: Self-supervised learning → fine-tuning → instruction tuning → RLHF/Constitutional AI form the modern LLM training pipeline built on top of the transformer.
- **Core mechanisms**: Attention, KV cache, context window, tokenization, word embeddings, autoregression, and mixture of experts (MoE) are the key sub-components of transformer-based systems.
- **Inference stack**: Transformers are deployed via inference engines (vLLM, llama.cpp, TensorRT-LLM, SGLang) on specialized hardware (GPU/CUDA, TPU, AI accelerators with high-bandwidth memory).
- **Application layer**: Transformers power chatbots (ChatGPT, Claude, Gemini), coding agents (OpenAI Codex, vibe coding), RAG systems, and multi-agent protocols (MCP, Agent2Agent).
- **Scaling laws**: Neural scaling laws, knowledge distillation, speculative decoding, and model compression are techniques for managing transformer scale.

## Exam-Relevant Points

- The transformer patent (US 10,452,978) lists **8 inventors**: Shazeer, Gomez, Kaiser, Uszkoreit, Jones, Parmar, Polosukhin, and Vaswani — matching the "Attention Is All You Need" author list.
- Know the **chronological progression** of Google's key models: BERT (2018) → T5 (2019) → LaMDA (2021) → Chinchilla (2022) → PaLM (2022) → Gemini (2023) → Gemma (2024).
- **Encoder-only vs. decoder-only vs. encoder-decoder**: BERT is encoder-only, GPT series is decoder-only, T5 is encoder-decoder — all are transformer variants.
- The transformer displaced RNNs/LSTMs as the dominant sequence modeling architecture starting in 2017.
- Key people to associate with transformers: **Ashish Vaswani** and **Noam Shazeer** (original architecture), **Geoffrey Hinton**, **Yann LeCun**, **Yoshua Bengio** (deep learning foundations), **Ilya Sutskever** (scaling), **Andrej Karpathy** (education/popularization).
- Modern LLM techniques built on transformers: **MoE** (mixture of experts), **KV cache** optimization, **speculative decoding**, **PagedAttention**, and **multimodality** are all active areas likely to appear on exams.
