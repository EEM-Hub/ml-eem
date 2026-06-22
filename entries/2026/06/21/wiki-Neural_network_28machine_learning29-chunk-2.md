---
source: chunks/wiki-Neural_network_28machine_learning29-chunk-2.md
source_url: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29
---

## History of Artificial Neural Networks

This page traces the historical development of neural networks from their mathematical foundations in the early 1800s through modern transformer architectures. It covers the key milestones, researchers, and architectural innovations that shaped the field of deep learning over more than two centuries.

## Key Concepts

- **Linear regression as proto-neural-network**: The simplest feedforward neural network is a linear network using least squares — a technique dating to Legendre (1805) and Gauss (1795) for planetary motion prediction.
- **Connectionism vs. von Neumann model**: Neural networks originated from efforts to model biological information processing; unlike von Neumann computing, connectionism does not separate memory and processing.
- **McCulloch-Pitts neuron (1943)**: First non-learning computational model for neural networks, capable of representing logical functions. Split research into biological modeling and AI branches.
- **Hebbian learning (1949)**: Learning hypothesis based on neural plasticity — "neurons that fire together wire together." Used in perceptrons and Hopfield networks.
- **Perceptron (1958)**: Frank Rosenblatt's single-layer learning network; sparked the "Golden Age of AI" but limited to linearly separable problems.
- **AI Winter trigger**: Minsky and Papert's *Perceptrons* (1969) proved single-layer perceptrons couldn't solve XOR, deflating research funding (though this was irrelevant for existing deep networks).
- **Group Method of Data Handling (1965)**: Ivakhnenko and Lapa's first working deep learning algorithm (Soviet Union); an 8-layer network was trained by 1971 using layer-by-layer regression with validation-based pruning.
- **ReLU activation (1969)**: Introduced by Kunihiko Fukushima; became the most common activation function in modern deep learning.
- **Transfer learning (1976)**: Concept introduced, later becoming critical for modern ML practice.
- **Backpropagation lineage**: Chain rule (Leibniz, 1673) → control theory precursor (Kelley, 1960) → modern automatic differentiation (Linnainmaa, 1970) → applied to neural networks (Werbos, 1982) → popularized (Rumelhart et al., 1986).
- **Vanishing gradient problem (1991)**: Identified by Sepp Hochreiter; solved by LSTM (Hochreiter & Schmidhuber), with the forget gate added in 1999 completing the standard LSTM architecture.
- **Convolutional Neural Networks**: Neocognitron (Fukushima, 1979) → TDNN for phonemes (Waibel, 1987) → LeNet for handwriting (LeCun, 1989) → LeNet-5 for bank checks (1998).
- **GANs (2014)**: Two networks in a zero-sum game — generator vs. discriminator. Reached peak quality with StyleGAN (2018). Concept traces to Schmidhuber's "artificial curiosity" (1991). Later eclipsed by **diffusion models** (2015+).
- **Residual networks (2015)**: Solved the "degradation" problem in very deep networks (20-30+ layers). Highway networks (May 2015) and ResNets (December 2015) were introduced the same year.
- **Transformer architecture (2017)**: "Attention Is All You Need" — uses self-attention with quadratic computation cost in context window size. Became the dominant architecture for NLP and the basis for GPT, Gemini, Grok, DeepSeek, Qwen.

## Commands and Syntax

No commands or configuration syntax — this is a historical/conceptual reference page.

## Relationships

- **Feedforward networks** → evolved into **multilayer perceptrons** → enabled by **backpropagation** → scaled by **GPUs and distributed computing**
- **Perceptrons** → limitations exposed by Minsky/Papert → research stagnation → revived by backpropagation in the 1980s
- **CNNs** (neocognitron → LeNet) branch: specialized for spatial/image data; key techniques include convolution, weight sharing, max pooling
- **RNNs** (Hopfield → Jordan/Elman → LSTM) branch: specialized for sequential data; vanishing gradient problem was the central challenge
- **LSTM** → seq2seq → attention mechanisms → **transformers** (architectural evolution for sequence modeling)
- **GANs** → superseded by **diffusion models** for generative tasks (DALL-E 2, Stable Diffusion)
- **Self-supervised pre-training** (1991, Schmidhuber) → became foundation of modern LLMs (the "P" in GPT)
- Statistical mechanics influenced both Hopfield networks and Boltzmann machines

## Exam-Relevant Points

- **Gauss/Legendre (1795/1805)**: Least squares method — mathematical foundation for the simplest neural network
- **McCulloch & Pitts (1943)**: First computational neural network model (non-learning)
- **Rosenblatt (1958)**: Perceptron — first implemented learning neural network
- **Minsky & Papert (1969)**: *Perceptrons* book — XOR limitation, triggered AI winter
- **Ivakhnenko & Lapa (1965)**: GMDH — first working deep learning algorithm
- **Fukushima (1969)**: ReLU activation function; **(1979)**: Neocognitron — first CNN architecture with max pooling
- **Linnainmaa (1970)**: Modern backpropagation (automatic differentiation)
- **Amari (1967)**: First deep MLP trained by stochastic gradient descent
- **Hochreiter (1991)**: Identified vanishing gradient problem; **(1997)**: LSTM with Schmidhuber; forget gate added **1999**
- **LeCun (1989)**: LeNet — CNN for handwritten digit recognition
- **AlexNet (2012)**: Krizhevsky, Sutskever, Hinton — won ImageNet, catalyzed modern deep learning era
- **Goodfellow (2014)**: GANs (concept traces to Schmidhuber's "artificial curiosity," 1991)
- **Transformers (2017)**: "Attention Is All You Need" — quadratic computation in context window size; basis for all major LLMs
- **Highway networks (May 2015) and ResNets (Dec 2015)**: Solved degradation in very deep networks
- **Diffusion models (2015)**: Eventually eclipsed GANs for image generation
- The **LSTM forget gate (1999)** completed the architecture that became the default RNN choice
- **Self-supervised pre-training** originated with Schmidhuber's neural history compressor (1991), predating its use in GPT by decades
