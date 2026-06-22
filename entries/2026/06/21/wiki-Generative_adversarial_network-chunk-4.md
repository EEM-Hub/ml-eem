---
source: chunks/wiki-Generative_adversarial_network-chunk-4.md
source_url: https://en.wikipedia.org/wiki/Generative_adversarial_network
---

## GAN Variants: Architectures, Objectives, and Multi-Player Extensions

This page catalogs the major variants of Generative Adversarial Networks, organized by what they modify relative to the original GAN framework: conditioning on additional inputs, swapping network architectures, changing loss functions, or adding extra players to the adversarial game.

## Key Concepts

- **Conditional GAN (cGAN)**: Extends the standard GAN by providing class labels to both generator and discriminator, so the generator produces a different distribution μ_G(c) for each class label c. Trivial extension noted in the original GAN paper.
- **DCGAN**: Uses only convolution-deconvolution layers (fully convolutional networks) for both generator and discriminator — no fully connected layers.
- **SAGAN**: Adds residually-connected self-attention modules to DCGAN, enabling the model to capture long-range spatial dependencies.
- **VAEGAN**: Uses a variational autoencoder as the generator.
- **TransGAN**: Pure transformer architecture for both generator and discriminator — no convolutions at all.
- **Flow-GAN**: Uses a flow-based generative model as the generator, enabling tractable likelihood computation.
- **Wasserstein GAN (WGAN)**: Replaces the standard GAN objective with the Wasserstein distance. The discriminator (called "critic") outputs unbounded real values with a Lipschitz constraint rather than probabilities. Designed to address mode collapse.
- **Adversarial Autoencoder (AAE)**: An autoencoder with a discriminator trained to match the latent distribution to a reference distribution (e.g., Gaussian). More autoencoder than GAN.
- **InfoGAN**: Decomposes the latent vector into incompressible noise z and an informative label c. Maximizes mutual information I(c, G(z,c)) via a variational lower bound using an auxiliary network Q. Three-player game (generator, Q, discriminator).
- **BiGAN (Bidirectional GAN)**: Adds an encoder E: Ω_X → Ω_Z alongside the generator G: Ω_Z → Ω_X. The discriminator receives (image, latent) pairs and must distinguish real-encoded pairs from generated-noise pairs. Enables learned inference.
- **CycleGAN**: Performs unpaired domain translation (e.g., horses ↔ zebras) using two generators and two discriminators plus a cycle-consistency loss that enforces G_Y(G_X(x)) ≈ x and G_X(G_Y(y)) ≈ y. Four-player game.

## Commands and Syntax

No CLI commands. Key mathematical formulations:

- **Standard GAN objective**: min_G max_D { E[ln D(x)] + E[ln(1 - D(G(z)))] }
- **Non-saturating generator loss** (recommended for faster convergence): L_G = E[ln D(x)] (maximize discriminator's belief that generated samples are real)
- **Hinge loss GAN**: L_D uses clamped terms min(0, -1+D(x)) and min(0, -1-D(x)); L_G = -E[D(x)]
- **Least squares GAN**: Replaces log loss with squared error; recommended parameters a=-1, b=1, c=0
- **WGAN objective**: L = E[D(x_generated)] - E[D(x_real)], with Lipschitz constraint ||D||_L ≤ K
- **InfoGAN objective**: L(G,Q,D) = L_GAN(G,D) - λ·Î(G,Q), where Î is the variational mutual information lower bound
- **CycleGAN objective**: L = L_GAN(G_X, D_X) + L_GAN(G_Y, D_Y) + λ·L_cycle(G_X, G_Y)

## Relationships

- **Conditional GAN → InfoGAN**: InfoGAN is the unsupervised analog of conditional GAN — it discovers latent labels rather than requiring them
- **Standard GAN → WGAN**: WGAN replaces the divergence measure (JS divergence → Wasserstein distance) and relaxes the discriminator from outputting probabilities to outputting real values
- **GAN → BiGAN**: BiGAN adds an inference pathway, connecting GANs to autoencoders and enabling semi-supervised learning, interpretability, and neural machine translation
- **BiGAN / AAE → Autoencoders**: Both create encoder-decoder pairs trained adversarially rather than with reconstruction loss alone
- **Alternative objectives** (hinge, least squares, non-saturating) are drop-in replacements for the original loss — they change training dynamics but not the architecture
- **CycleGAN → Image-to-image translation**: Extends paired translation methods (like pix2pix) to the unpaired setting via cycle consistency

## Exam-Relevant Points

- The original GAN paper itself proposed the conditional GAN extension — labels are simply provided to both G and D
- The **non-saturating loss** (L_G = E[ln D(x)]) was recommended in the original paper for faster convergence, addressing vanishing gradients when G is poor
- **WGAN** constrains the discriminator's Lipschitz norm and claims to eliminate mode collapse entirely ("In no experiment did we see evidence of mode collapse")
- **InfoGAN** uses **Variational Mutual Information Maximization** — it maximizes a lower bound on mutual information because I(c, G(z,c)) is intractable
- InfoGAN is a **3-player, 2-team** game: generator + Q network vs. discriminator
- **BiGAN** is also a **3-player, 2-team** game: generator + encoder vs. discriminator; the discriminator operates on (image, latent) pairs
- **CycleGAN** is a **4-player, 2-team** game with cycle-consistency loss enforcing round-trip reconstruction
- DCGAN's key constraint: **fully convolutional** — no fully connected layers
- SAGAN adds **self-attention** to DCGAN via residual connections
- BiGAN applications: semi-supervised learning, interpretable ML, neural machine translation
- By 2017, conditional GANs could generate all 1000 ImageNet classes
- **Least squares GAN** recommended parameters: a=-1, b=1, c=0
