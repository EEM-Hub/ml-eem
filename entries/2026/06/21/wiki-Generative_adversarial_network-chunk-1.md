---
source: chunks/wiki-Generative_adversarial_network-chunk-1.md
source_url: https://en.wikipedia.org/wiki/Generative_adversarial_network
---

## Generative Adversarial Networks (GANs)

GANs are a class of deep learning frameworks for generative AI, introduced by Ian Goodfellow et al. in 2014. Two neural networks — a generator and a discriminator — compete in a zero-sum game: the generator learns to produce synthetic data indistinguishable from real data, while the discriminator learns to tell real from fake. This adversarial training process enables unsupervised learning of complex data distributions.

## Key Concepts

- **Two-player zero-sum game**: The generator minimizes and the discriminator maximizes the same objective function — one's gain is the other's loss.
- **Generator**: Maps from a latent space (e.g., multivariate normal distribution) to the data distribution; aims to produce outputs the discriminator classifies as real. Typically implemented as a deconvolutional neural network for image tasks.
- **Discriminator**: Evaluates whether inputs come from real data or the generator; outputs values near 1 for real, near 0 for generated. Typically implemented as a convolutional neural network for image tasks.
- **Implicit generative model**: GANs do not explicitly model the likelihood function or provide a way to find the latent variable for a given sample (unlike flow-based models or VAEs).
- **Training dynamics**: Independent backpropagation is applied to both networks — the generator improves at fooling the discriminator, the discriminator improves at detecting fakes, creating an evolutionary arms race.
- **Latent space**: The generator is seeded with randomized input sampled from a predefined latent distribution.
- **Single-pass generation**: Unlike autoregressive models (WaveNet, PixelRNN), GANs generate a complete sample in one forward pass.
- **Asymptotic consistency**: Because neural networks are universal approximators, GANs are asymptotically consistent estimators of the data distribution.
- **Learning paradigm flexibility**: Originally proposed for unsupervised learning, but also applicable to semi-supervised, fully supervised, and reinforcement learning settings.

## Commands and Syntax

**Objective function (mathematical formulation):**

```
L(μ_G, μ_D) = E_{x ~ μ_ref, y ~ μ_D(x)}[ln y] + E_{x ~ μ_G, y ~ μ_D(x)}[ln(1 - y)]
```

- Generator minimizes L; discriminator maximizes L.
- μ_ref = reference (real) data distribution
- μ_G = generator's output distribution
- μ_D = discriminator's output (probability of "real")
- At equilibrium, μ_G ≈ μ_ref

**Training procedure:**
1. Train discriminator on real data samples until acceptable accuracy
2. Generator produces candidates from random latent vectors
3. Discriminator evaluates generator's candidates
4. Apply backpropagation independently to both networks
5. Iterate until generator outputs are indistinguishable from real data

## Relationships

- **Generative models taxonomy**: GANs are one of several deep generative model families alongside variational autoencoders (VAEs), flow-based models, diffusion models, and autoregressive models.
- **vs. Flow-based models**: Flow-based models are explicit generative models that provide tractable likelihood and invertible mappings; GANs are implicit and do not.
- **vs. VAEs**: VAEs provide a latent encoding mechanism and explicit likelihood bound; GANs lack this but may produce sharper outputs. VAE universality was unproven as of 2017.
- **vs. Autoregressive models** (WaveNet, PixelRNN): These generate sequentially token-by-token; GANs generate complete samples in one pass.
- **vs. Boltzmann machines / ICA**: GANs place no restrictions on the function class of the networks.
- **vs. Diffusion models**: Diffusion models have largely supplanted GANs for image generation in practice due to more stable training and better mode coverage.
- **Game theory**: GAN training is formally a minimax game from game theory.
- **Backpropagation**: Both networks are trained via standard backpropagation.

## Exam-Relevant Points

- GANs consist of exactly **two networks**: generator and discriminator, trained adversarially.
- The objective is a **minimax (zero-sum) game** — generator minimizes, discriminator maximizes the same loss.
- GANs are **implicit generative models** — they do not explicitly model the likelihood.
- The generator maps from a **latent space** to data space; the discriminator maps from data space to a probability of being real.
- GANs generate complete samples in **one forward pass** (contrast with autoregressive models).
- Originally proposed for **unsupervised learning** but applicable to semi-supervised, supervised, and reinforcement learning.
- Introduced by **Ian Goodfellow et al., 2014**.
- For image generation: generator = **deconvolutional** network; discriminator = **convolutional** network.
- GANs are **asymptotically consistent** due to the universal approximation theorem.
- Key training challenge: balancing generator and discriminator so neither dominates (mode collapse, training instability).
