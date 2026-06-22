---
source: chunks/wiki-Deep_learning-chunk-7.md
source_url: https://en.wikipedia.org/wiki/Deep_learning
---

## Deep Learning — Reference Landscape and Taxonomic Context

This page provides the recommended further reading for the Wikipedia article on deep learning, along with comprehensive navigation templates that situate deep learning within the broader taxonomies of generative AI and artificial intelligence. It serves as a map of the field's key texts, related concepts, models, architectures, and notable contributors.

## Key Concepts

- **Deep learning** is positioned as a core concept within both generative AI and the broader artificial intelligence field
- The field is organized into concept layers: foundational techniques (backpropagation, gradient descent, attention, convolution) → architectures (transformer, CNN, RNN, LSTM, GAN, VAE) → applications (language models, image generation, speech, video) → products (coding tools, agents)
- **Generative AI** is categorized by modality: text, image, video, speech, and music — each with distinct model families
- Key architectural paradigms include: transformers, variational autoencoders (VAE), generative adversarial networks (GAN), and diffusion models (latent diffusion)
- Core training concepts: self-supervised learning, RLHF, reinforcement learning, autoregression, prompt engineering, retrieval-augmented generation (RAG)
- Neural network architectures are classified as: recurrent (RNN, LSTM, GRU), convolutional (CNN), attention-based (Transformer, ViT), state-space (Mamba), and generative (VAE, GAN)

## Commands and Syntax

No commands or configuration syntax — this is a reference/taxonomy page. The key textbooks cited are:

- **Bishop & Bishop (2024)** — *Deep Learning: Foundations and Concepts* (Springer) — modern comprehensive treatment
- **Chollet & Watson (2025)** — *Deep Learning with Python* (Manning) — practical/applied, Keras-focused
- **Prince (2023)** — *Understanding Deep Learning* (MIT Press) — conceptual clarity focus
- **Goodfellow, Bengio & Courville (2016)** — *Deep Learning* (MIT Press) — the canonical introductory textbook

## Relationships

- **Deep learning → Generative AI**: Deep learning is the foundational technique enabling all generative AI models (LLMs, diffusion models, GANs)
- **Deep learning → Neural network architectures**: Specific architectures (Transformer, CNN, RNN/LSTM, VAE, GAN) are the building blocks of deep learning systems
- **Training techniques → Deep learning**: Backpropagation, SGD, attention, normalization, activation functions, and regularization are the core algorithmic components
- **Deep learning → Applications**: Powers language models (LLMs), computer vision, speech recognition/synthesis, autonomous systems, and reasoning systems
- **Foundation model → Fine-tuning → RLHF**: The modern training pipeline for deployable models
- **Model Context Protocol (MCP)** and **Agent2Agent protocol**: Emerging interaction standards for AI agent systems
- **Prompt engineering** and **RAG**: Key techniques for leveraging pre-trained deep learning models without retraining

## Exam-Relevant Points

- Know the four canonical deep learning textbooks and their authors (especially Goodfellow/Bengio/Courville 2016 as the foundational reference)
- **Transformer** architecture is the basis for both LLMs and vision transformers (ViT) — understand it spans modalities
- Distinguish between generative model families: **autoregressive** (GPT-style), **diffusion** (Stable Diffusion), **adversarial** (GAN), **variational** (VAE)
- Key people to associate with deep learning's development: **Geoffrey Hinton**, **Yann LeCun**, **Yoshua Bengio** (the "three godfathers"), **Jürgen Schmidhuber** (LSTM lineage), **Ian Goodfellow** (GANs), **Ashish Vaswani** (Transformer), **François Chollet** (Keras/practical DL)
- **RLHF** (Reinforcement Learning from Human Feedback) is the key technique connecting base language models to aligned/deployable chatbots
- **Self-supervised learning** is the dominant pre-training paradigm for modern deep learning (as opposed to supervised or unsupervised)
- Neural architecture taxonomy: **MLP** (feedforward) → **CNN** (spatial) → **RNN/LSTM/GRU** (sequential) → **Transformer** (attention-based, now dominant) → **Mamba** (state-space, emerging alternative)
- The **latent diffusion model** is the specific architecture behind modern image/video generation (not raw diffusion)
- **Retrieval-augmented generation (RAG)** bridges deep learning models with external knowledge bases — a key deployment pattern
