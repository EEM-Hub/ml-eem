---
source: chunks/wiki-Generative_adversarial_network-chunk-6.md
source_url: https://en.wikipedia.org/wiki/Generative_adversarial_network
---

## Generative Adversarial Networks: Key Literature and Research Landscape

This page compiles the foundational and extended references for GANs, covering the original paper by Goodfellow et al. (2014) through major architectural variants, training techniques, evaluation metrics, and application domains. The bibliography maps the evolution of GAN research from 2014 to 2024.

## Key Concepts

- **Foundational paper**: Goodfellow et al. (2014), "Generative Adversarial Nets," NIPS 2014 — the most-cited reference across the article, establishing the generator-discriminator adversarial training framework
- **Training stability** is a major research thread: Salimans et al. (2016) "Improved Techniques for Training GANs," Mescheder et al. (2018) on convergence, and the Two Time-Scale Update Rule (TTUR) by Heusel et al. (2017)
- **Nash equilibrium**: Farnia & Ozdaglar (2020) showed GANs do not always have Nash equilibria — a theoretical result with practical implications for training
- **Loss function variants**: Wasserstein distance (Arjovsky & Bottou, 2017; Weng 2019 "From GAN to WGAN"), Least Squares GAN (Mao et al., 2017), Geometric GAN (Lim & Ye, 2017)
- **Evaluation metrics**: Fréchet Inception Distance (FID) introduced via TTUR paper; Learned Perceptual Image Patch Similarity (LPIPS) by Zhang et al. (2018); comprehensive survey of pros/cons by Borji (2019)
- **Progressive training**: Karras et al. (2017) introduced progressive growing of GANs for stable high-resolution synthesis
- **Data efficiency**: Differentiable Augmentation (Zhao et al., 2020), Training with Limited Data / ADA (Karras et al., 2020), SinGAN from a single image (Shaham et al., 2019)
- **The GAN Zoo**: Hindupur's catalog documents the massive proliferation of GAN variants

## Commands and Syntax

No specific commands in a references page, but key papers to retrieve for deeper study:

```
# Foundational reading order
arxiv: 1406.2661  # Original GAN paper (Goodfellow 2014)
arxiv: 1606.03498  # Improved Techniques (Salimans 2016)
arxiv: 1701.00160  # NIPS 2016 Tutorial (Goodfellow 2017)
arxiv: 1904.08994  # From GAN to WGAN (Weng 2019) — excellent survey
arxiv: 1710.10196  # Progressive Growing (Karras 2017)
arxiv: 1812.04948  # StyleGAN (Karras 2019)
arxiv: 1809.11096  # BigGAN (Brock 2018)
```

## Relationships

- **Related generative models**: VAE (Kingma & Welling, 2014, arxiv:1312.6114), Flow-GAN (Grover et al., 2017) combining normalizing flows with adversarial training, Adversarial Autoencoders (Makhzani et al., 2016)
- **Architectural lineage**: DCGAN (Radford et al., 2016) → SAGAN with self-attention (Zhang et al., 2019) → BigGAN at scale (Brock et al., 2018) → StyleGAN/StyleGAN2/StyleGAN3 (Karras et al., 2019–2021) → TransGAN using pure transformers (Jiang et al., 2021)
- **Conditional generation**: AC-GAN (Odena et al., 2017), pix2pix for paired image translation (Isola et al., 2017), CycleGAN for unpaired translation (Zhu et al., 2017)
- **Representation learning**: BiGAN/ALI for bidirectional mapping (Donahue 2016; Dumoulin 2016), InfoGAN for disentangled representations (Chen et al., 2016)
- **Applications to reinforcement learning**: Generative Adversarial Imitation Learning (Ho & Ermon, 2016), Domain Adversarial RL (Li et al., 2021)
- **Scientific applications**: CosmoGAN for dark matter maps, CaloGAN for particle physics simulation, turbulence super-resolution

## Exam-Relevant Points

- **Original GAN paper**: Goodfellow, Pouget-Abadie, Mirza, Xu, Warde-Farley, Ozair, Courville, Bengio — NIPS 2014. Know all authors for foundational attribution questions.
- **FID (Fréchet Inception Distance)** was introduced in the TTUR paper (Heusel et al., 2017) — not a standalone metrics paper
- **StyleGAN progression**: StyleGAN (2019) → StyleGAN2 (2020, "Analyzing and Improving Image Quality") → StyleGAN3 (2021, "Alias-Free") — all by Karras et al. at NVIDIA
- **DCGAN** (Radford, Metz, Chintala 2016) established convolutional architecture best practices for GANs — know this as the bridge from fully-connected to convolutional GANs
- **CycleGAN** = unpaired image translation; **pix2pix** = paired image translation — both from the Berkeley group (Zhu, Isola, Efros et al.)
- **Mode collapse** solutions span multiple papers: PacGAN (Lin et al., 2018), progressive training, curriculum learning (CuGAN)
- **GANs do not always have Nash equilibria** (Farnia & Ozdaglar, ICML 2020) — important theoretical limitation
- **Wasserstein GAN** addresses training instability through the Earth Mover's distance; Arjovsky & Bottou (2017) provided the theoretical motivation
- **BigGAN** (Brock et al., 2018) demonstrated that scaling up (large batch sizes, more parameters) dramatically improves sample quality — key scaling result
- **Scientific simulation** is a major application domain: particle physics (CaloGAN), cosmology (CosmoGAN), fluid dynamics — GANs provide orders-of-magnitude speedup over traditional Monte Carlo simulation
