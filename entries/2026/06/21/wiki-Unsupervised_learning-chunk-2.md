---
source: chunks/wiki-Unsupervised_learning-chunk-2.md
source_url: https://en.wikipedia.org/wiki/Unsupervised_learning
---

## Unsupervised Neural Network Architectures

This page provides a comprehensive survey of unsupervised neural network architectures, tracing their evolution from physics-inspired Hopfield networks through Boltzmann machines, Restricted Boltzmann Machines (RBMs), Helmholtz machines, autoencoders, and Variational Autoencoders (VAEs). It covers their training methods, energy-based formulations, network topologies, and a detailed comparison of their properties.

## Key Concepts

- **Unsupervised training** involves a network mimicking input data and using the error in its output to correct weights/biases — no labeled targets are provided.
- **Energy function** is a macroscopic measure of network activation state; in Boltzmann machines it serves as the cost function. Probability of a state is p(a) = e^{-E(a)} / Z, where Z is the partition function summing over all possible activation patterns.
- **Harmony** (Smolensky's term) is -E; networks seek low energy / high harmony.
- **Hopfield networks** are inspired by ferromagnetism — neurons are binary, connections are symmetric, enabling convergence to stable patterns. Used as Content Addressable Memories (CAMs).
- **Boltzmann machines** are stochastic Hopfield nets with hidden and visible layers; symmetric weights allow energy-based analysis but lateral connections make training difficult.
- **Restricted Boltzmann Machines (RBMs)** remove lateral (within-layer) connections to make learning tractable; trained via Contrastive Divergence with Gibbs Sampling.
- **Stacked RBMs / Deep Belief Networks** add hierarchical layers; each RBM layer is trained greedily one at a time, enabling unsupervised pre-training followed by supervised fine-tuning.
- **Helmholtz machines** use asymmetric weights with separate recognition (forward) and generative (backward) networks; trained with Wake-Sleep algorithm. Early inspiration for VAEs.
- **Autoencoders** are feedforward 3-layer networks learning compressed internal representations; deterministic, so less robust than VAEs.
- **Variational Autoencoders (VAEs)** apply variational inference to autoencoders; the middle layer encodes means and variances of Gaussian distributions, enabling stochastic sampling and robust generation. Loss = reconstruction error - KL divergence.
- **Sigmoid Belief Networks** (Neal, 1992) are sparsely connected directed acyclic graphs of binary stochastic neurons; suffer from the "Explaining Away" problem.
- **Hebbian learning** — "neurons that fire together wire together" — reinforces connections based on coincident activation, not error signals.
- **Self-Organizing Maps (SOMs)** create topographic mappings where nearby locations represent similar inputs.
- **Adaptive Resonance Theory (ART)** allows variable cluster counts controlled by a vigilance parameter.

## Commands and Syntax

No specific software commands. Key mathematical formulations:

- **Boltzmann distribution**: `p ∝ e^{-E/kT}` (physics); `p = e^{-E} / Z` (RBM)
- **Partition function**: `Z = Σ_{all patterns} e^{-E(pattern)}`
- **Hopfield energy**: `E = -½ Σ_{i,j} w_ij s_i s_j + Σ_i θ_i s_i`
- **Hopfield learning rule**: `Δw_ij = s_i * s_j` (for +1/-1 neurons)
- **Boltzmann learning rule**: `Δw_ij = ε * (p_ij - p'_ij)` (derived from minimizing KL divergence)
- **RBM training (Contrastive Divergence)**: `Δw_ij = ε * (<v_i h_j>_data - <v_i h_j>_equilibrium)`
- **Sigmoid Belief Net learning**: `Δw_ij ∝ s_j * (s_i - p_i)` where `p_i = σ(weighted inputs)`
- **VAE loss**: minimize (reconstruction error - KL divergence)

## Relationships

- **Backpropagation** is dominant in supervised learning but also used in autoencoders/VAEs for reconstruction error.
- **Contrastive Divergence** is the practical training algorithm for RBMs.
- **Gibbs Sampling** is used within Contrastive Divergence for approximating equilibrium distributions.
- **Variational Inference** connects to VAEs and is an alternative to exact posterior computation.
- **Maximum Likelihood / MAP** are objective functions used across several unsupervised architectures.
- **Wake-Sleep algorithm** is specific to Helmholtz machines.
- **Deep Belief Networks** bridge RBMs (top layers) and Sigmoid Belief Networks (lower layers).
- **LSTMs** (1995, Hochreiter & Schmidhuber) are used as neurons in autoencoder architectures for language tasks.
- **Convolutional neural networks** (Fukushima's neocognitron, 1980) are mostly supervised but historically connected.
- Evolution path: Hopfield → Boltzmann → RBM → Stacked RBM/DBN; Helmholtz → Autoencoder → VAE.

## Exam-Relevant Points

- **Hopfield nets** use deterministic binary neurons and symmetric weights; guaranteed to converge to stable states; used as CAMs.
- **Boltzmann machines** add stochastic neurons to Hopfield nets; lateral connections make them hard to train.
- **RBMs restrict** Boltzmann machines by removing lateral connections within layers, making training tractable via Contrastive Divergence.
- **Stacked RBMs** are trained greedily one layer at a time with no backpropagation; optimal depth was found to be 3-4 layers (as of 2009).
- **Deep Belief Networks** have an undirected RBM at the top and directed sigmoid belief network layers below.
- **Helmholtz machines** are the first networks to do both recognition and generation; use separate forward/backward weight sets (asymmetric).
- **VAE middle layer** encodes parameters (mean, variance) of Gaussian distributions, not fixed values — enabling stochastic generation via the reparameterization trick.
- **VAE training** uses reparameterized hidden states to enable backpropagation through stochastic nodes.
- **Partition function Z** sums over all possible activation patterns and is generally intractable to compute exactly.
- **Smolensky's Harmony Theory** (1986) described RBMs with Boltzmann energy but lacked a practical training scheme; Hinton provided one in the mid-2000s.
- **Explaining Away** (Judea Pearl) is a key challenge for Sigmoid Belief Networks; variational methods sidestep it with a surrogate posterior.
- **Hebbian learning** is purely coincidence-based (no error signal); STDP extends it with temporal information.
- **ART networks** use a vigilance parameter to control cluster granularity; number of clusters varies with problem size.
- Key historical dates: Hopfield net (1982), Boltzmann machine (1983), Harmony Theory/RBM (1986), LSTM (1995), Helmholtz machine (1995), VAE (2013).
