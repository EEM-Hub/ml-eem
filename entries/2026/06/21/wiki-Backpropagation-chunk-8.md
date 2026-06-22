---
source: chunks/wiki-Backpropagation-chunk-8.md
source_url: https://en.wikipedia.org/wiki/Backpropagation
---

## Backpropagation — References and AI Taxonomy

This page provides the reference bibliography, external learning resources, and a broad taxonomic index for the Wikipedia article on **backpropagation**. While it contains no primary explanatory content, it maps backpropagation's position within the wider AI landscape and points to authoritative sources for deeper study.

## Key Concepts

- **Backpropagation** is categorized under core AI *concepts* alongside gradient descent, SGD, attention, convolution, normalization, activation functions, and weight initialization.
- It is distinct from but closely related to: **gradient descent** (the optimization it enables), **SGD** and **quasi-Newton methods** (specific optimizers), and **loss functions** (which backpropagation differentiates through).
- Backpropagation sits in the training pipeline between **loss functions** (which define the objective) and **weight initialization / regularization** (which constrain learning).
- The taxonomy places backpropagation as foundational to **deep learning**, which in turn underpins **language models (LLMs)**, **generative AI**, and **neural network architectures** (Transformers, CNNs, RNNs, etc.).

## Commands and Syntax

No commands or configuration syntax appear on this page. Key textbook references for algorithmic detail:

- Goodfellow, Bengio & Courville — *Deep Learning*, Chapter 6.5 (pp. 200–220): formal treatment of backprop and automatic differentiation.
- Nielsen — *Neural Networks and Deep Learning*, Chapter 2: intuitive, code-oriented walkthrough.
- Rojas — *Neural Networks: A Systematic Introduction*, Chapter 7: mathematical derivation.
- Karpathy — CS231n Lecture 4: computational graph perspective with worked examples.

## Relationships

- **Upstream**: Loss functions, forward pass computation, activation functions (sigmoid, ReLU, softmax).
- **Downstream**: All gradient-based optimizers (SGD, Adam, quasi-Newton, conjugate gradient) depend on gradients computed by backpropagation.
- **Architectures it trains**: MLPs, CNNs, RNNs/LSTMs/GRUs, Transformers, VAEs, GANs, autoencoders, residual networks.
- **Historical lineage**: Seppo Linnainmaa (automatic differentiation, 1970), Paul Werbos (application to neural nets, 1974), Rumelhart/Hinton/Williams (popularization, 1986).
- **Key people** listed: Geoffrey Hinton, Yann LeCun, Yoshua Bengio, Ian Goodfellow, Andrej Karpathy, Jürgen Schmidhuber.

## Exam-Relevant Points

- Backpropagation is an application of the **chain rule** for computing gradients — it is *not* an optimizer itself, but the algorithm that provides gradients to optimizers.
- It is classified alongside **attention**, **convolution**, and **normalization** as a core neural network *mechanism*, not an architecture or application.
- The canonical textbook treatment is Goodfellow et al. Chapter 6.5 — expect exam questions to reference this framing.
- Backpropagation is prerequisite knowledge for understanding **all** modern neural network architectures listed in the taxonomy (Transformers, CNNs, RNNs, GANs, etc.).
- The distinction between backpropagation (gradient computation) and gradient descent (parameter update) is a common exam topic.
