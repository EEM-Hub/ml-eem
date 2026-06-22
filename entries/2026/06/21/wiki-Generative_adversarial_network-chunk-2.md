---
source: chunks/wiki-Generative_adversarial_network-chunk-2.md
source_url: https://en.wikipedia.org/wiki/Generative_adversarial_network
---

## Mathematical Foundations of the GAN Game

This page covers the rigorous mathematical theory underlying Generative Adversarial Networks, including their measure-theoretic formulation, the structure of generator and discriminator strategy sets, equilibrium concepts from game theory, and the two main theorems from the original GAN paper proving that the optimal discriminator computes the Jensen–Shannon divergence and that the unique equilibrium occurs when the generator perfectly replicates the reference distribution.

## Key Concepts

- **Measure-theoretic formulation**: A GAN game is defined on a probability space (Ω, B, μ_ref) equipped with a σ-algebra. The generator's strategy set is all probability measures μ_G on (Ω, B); the discriminator's strategy set is the set of Markov kernels mapping (Ω, B) → P([0,1]).
- **Optimal discriminator is deterministic**: By Jensen's inequality, the optimal discriminator reply is always a deterministic function D: Ω → [0,1], so restricting to deterministic discriminators loses no generality.
- **Generator as pushforward**: In practice, μ_G = μ_Z ∘ G⁻¹ — sample z from a simple distribution (Gaussian or uniform), then push through a learned function G. This is the "reparameterization trick," independently developed by Kingma & Welling (VAE) and Rezende et al.
- **Three equilibrium concepts**: (1) Sequential equilibrium with generator moving first (minimax), (2) sequential equilibrium with discriminator moving first (maximin), (3) Nash equilibrium (simultaneous moves). For the original GAN game, all three exist and coincide; for general GAN variants, they may not.
- **Minimax theorem caveat**: Because both strategy sets are infinite-dimensional, the classical minimax theorem does not directly apply; move order matters in principle.
- **Optimal discriminator theorem**: For fixed μ_G, the optimal D*(x) equals the Radon–Nikodym derivative dμ_ref / d(μ_ref + μ_G), and the resulting objective value equals 2·D_JS(μ_ref; μ_G) − 2·ln 2.
- **Optimal D* as likelihood ratio**: D*(x)/(1 − D*(x)) = dμ_ref/dμ_G(x), i.e., the odds ratio. Equivalently, D*(x) = σ(ln μ_ref(dx) − ln μ_G(dx)), where σ is the logistic function.
- **Bayesian interpretation**: If the prior probability of an image coming from the reference vs. generator is 1/2 each, then D*(x) is exactly the posterior probability that x came from the reference distribution.
- **Unique equilibrium point**: The unique equilibrium has μ̂_G = μ_ref (generator perfectly mimics the data) and μ̂_D(x) = 1/2 for all x (discriminator cannot distinguish), with L = −2 ln 2.
- **Cross-entropy decomposition**: The GAN objective integrates the negative cross-entropy between Bernoulli variables with parameters ρ_ref(x) and D(x), decomposable as −H(ρ_ref(x)) − D_KL(ρ_ref(x) ‖ D(x)).

## Commands and Syntax

No software commands. Key mathematical formulations:

- **GAN objective**: L(G, D) = E_{x∼μ_ref}[ln D(x)] + E_{z∼μ_Z}[ln(1 − D(G(z)))]
- **Minimax game**: min_G max_D L(G, D)
- **Optimal discriminator**: D*(x) = dμ_ref / d(μ_ref + μ_G) = ρ_ref(x)
- **Optimal objective value**: L(μ_G, D*) = 2·D_JS(μ_ref ‖ μ_G) − 2·ln 2
- **Equilibrium value**: L(μ̂_G, μ̂_D) = −2·ln 2
- **Density decomposition**: Define μ = μ_ref + μ_G, then ρ_ref = dμ_ref/dμ and ρ_G = dμ_G/dμ, with ρ_ref + ρ_G = 1

## Relationships

- **Jensen–Shannon divergence**: The GAN objective, after discriminator optimization, reduces to the JS divergence between μ_ref and μ_G — this is why the original GAN implicitly minimizes JS divergence.
- **KL divergence and cross-entropy**: The proof decomposes the objective via binary cross-entropy and KL divergence between Bernoulli variables.
- **Radon–Nikodym derivative**: Central to expressing the optimal discriminator; connects to density ratios in statistics.
- **Variational autoencoders (VAEs)**: Share the reparameterization trick with GANs; developed concurrently by Kingma & Welling.
- **Nash equilibrium / minimax theorem**: Game-theoretic framework; the minimax theorem's inapplicability to infinite strategy sets is why GAN convergence theory is nontrivial.
- **Logistic function**: The optimal discriminator's output is the logistic transform of the log-likelihood ratio — directly connects to logistic regression and binary classification.
- **f-GAN and other divergence-based GANs**: The equilibrium equivalence proven here for the original GAN does not necessarily hold for generalized GAN objectives.

## Exam-Relevant Points

- The optimal discriminator for a fixed generator computes D*(x) = μ_ref(x) / (μ_ref(x) + μ_G(x)); memorize this form.
- At the unique equilibrium: generator matches the data distribution exactly (μ̂_G = μ_ref), discriminator outputs 1/2 everywhere, and the objective value is −2 ln 2.
- The original GAN implicitly minimizes the Jensen–Shannon divergence (not KL divergence) between the generated and real data distributions.
- The optimal discriminator is always deterministic — stochastic discriminators cannot improve the objective (proven via Jensen's inequality).
- The generator distribution is implemented as a pushforward measure: sample z from a simple prior, apply G to get G(z).
- Sequential (minimax/maximin) and Nash equilibria all coincide for the original GAN game, but this is **not** guaranteed for general GAN variants.
- The minimax theorem requires finite strategy sets; since GAN strategy sets are infinite, move order matters in general — a common exam distinction.
- The reparameterization trick was independently discovered for GANs and VAEs in the same year (2013–2014), enabling stochastic backpropagation through sampling.
