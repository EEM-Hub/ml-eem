---
source: chunks/wiki-Generative_adversarial_network-chunk-3.md
source_url: https://en.wikipedia.org/wiki/Generative_adversarial_network
---

## GAN Training Challenges and Evaluation Metrics

This page covers the key practical difficulties encountered when training Generative Adversarial Networks — unstable convergence, mode collapse, and vanishing gradients — along with mitigation strategies and the standard metrics used to evaluate GAN output quality.

## Key Concepts

- **Unstable convergence**: The GAN minimax game has a unique global equilibrium when both generator and discriminator have unrestricted strategy sets, but in practice neural networks restrict both to a vanishingly small proportion of possible strategies, so equilibrium is no longer guaranteed.
- **Mode collapse**: The generator learns to produce only a subset of the target distribution's modes (e.g., only one digit from MNIST). The discriminator correctly labels these as real but imposes no penalty for missing modes. Root cause is debated — weak discriminator vs. poor objective function. Remains an open problem even in state-of-the-art architectures (BigGAN, 2019).
- **"Helvetica scenario"**: Goodfellow's original term for mode collapse.
- **Two Time-Scale Update Rule (TTUR)**: Sets the generator's learning rate lower than the discriminator's. Provably converges to a stationary local Nash equilibrium under mild assumptions (extends to Adam optimizer). However, a local Nash equilibrium does not preclude mode collapse.
- **Vanishing gradient in GANs**: If the discriminator learns too fast, it perfectly separates real from generated samples. The generator's loss gradient approaches zero regardless of parameter changes, so the generator cannot learn. This is distinct from the general vanishing gradient problem in deep networks.
- **Wasserstein GAN (WGAN)**: An important architectural solution to the vanishing gradient problem in GANs, using the Wasserstein (Earth Mover's) distance instead of JS divergence.
- **Curriculum learning for GANs**: Starting with easier tasks (low-resolution or simple images) and gradually increasing difficulty stabilizes convergence.

## Commands and Syntax

No CLI commands. Key mathematical formulations:

- Generator distribution: `μ_Z ∘ G_θ^{-1}` where `G_θ` is the generator network and `μ_Z` is a simple prior (uniform/normal)
- Discriminator: `D_ζ` parameterized by `ζ`
- Generator gradient: `∇_θ L(G_θ, D_ζ)` — vanishes when discriminator is too strong

**Evaluation metrics:**
- **Inception Score (IS)**: Measures variety of generator outputs using an Inception-v3 classifier. Higher = more diverse and recognizable outputs.
- **Fréchet Inception Distance (FID)**: Measures similarity between generated and reference distributions in Inception-v3 feature space. Lower = better.
- **LPIPS (Learned Perceptual Image Patch Similarity)**: A featurizer `f_θ` is fine-tuned on human perceptual difference judgments so that `‖f_θ(x) - f_θ(x')‖ ≈ perceptual_difference(x, x')`. Used to measure perceptual quality.

## Relationships

- **Gradient descent** — standard optimization approach that often fails for GANs due to the adversarial game dynamics
- **Wasserstein GAN** — key architectural response to vanishing gradient; uses Earth Mover's distance
- **Mode collapse** — a broader topic with its own research area
- **Inception-v3** — backbone architecture used in both IS and FID evaluation
- **Curriculum learning** — borrowed from supervised learning to stabilize GAN training
- **Adam optimizer** — commonly used with TTUR for GAN training
- **Objective function design** — one of two competing explanations for mode collapse

## Exam-Relevant Points

- The GAN equilibrium is guaranteed only with unrestricted strategy sets; neural network parameterization restricts strategies to a vanishingly small subset
- Mode collapse = generator produces limited modes; vanishing gradient = generator cannot learn at all. These are opposite failure modes caused by the discriminator being too weak vs. too strong, respectively
- TTUR (lower generator LR, higher discriminator LR) converges to local Nash equilibrium but does NOT prevent mode collapse
- FID measures distance between generated and real distributions (lower is better); IS measures output diversity and quality (higher is better) — both typically use Inception-v3
- LPIPS is fine-tuned on human perceptual judgments, unlike IS/FID which use pretrained classifiers directly
- BigGAN (2019, state-of-the-art at the time) could not fully solve mode collapse — authors allowed it to occur in later training stages
- Wasserstein GAN is the key named solution to the vanishing gradient problem in GANs
