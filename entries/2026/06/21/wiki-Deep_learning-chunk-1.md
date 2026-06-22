---
source: chunks/wiki-Deep_learning-chunk-1.md
source_url: https://en.wikipedia.org/wiki/Deep_learning
---

## Deep Learning: Foundations, Architectures, and Theory

Deep learning is a branch of machine learning that uses multilayered neural networks to perform classification, regression, and representation learning. This page covers the definition of "deep" (multiple layers, from three to thousands), the key architectural families, the theoretical foundations (universal approximation, probabilistic interpretation), and how deep learning automates feature extraction compared to traditional hand-crafted feature engineering.

## Key Concepts

- **Deep learning** uses multilayered neural networks; "deep" refers to the number of layers (three to hundreds/thousands) through which data is transformed.
- **Credit Assignment Path (CAP) depth** measures the chain of transformations from input to output. Deep learning generally means CAP depth > 2.
- **Automatic feature learning**: Unlike traditional ML that relies on hand-crafted feature engineering, deep learning discovers useful feature representations from data automatically through its layered hierarchy.
- **Hierarchical abstraction**: Each layer transforms data into progressively more abstract representations (e.g., pixels → edges → shapes → objects).
- **Learning paradigms**: Deep learning methods can be supervised, semi-supervised, or unsupervised.
- **Universal Approximation Theorem**: A network with CAP depth of 2 can emulate any function, but deeper models extract better features in practice.
- **Probabilistic interpretation**: Treats activation nonlinearities as cumulative distribution functions; led to the introduction of dropout as a regularizer.
- Neural networks are inspired by biological systems but are not intended as accurate models of brain function.

## Commands and Syntax

No specific commands or configuration syntax are covered in this source document (it is a conceptual overview, not a tooling page).

## Relationships

- **Parent field**: Machine learning — deep learning is a subfield focused on multi-layer representations.
- **Core architectures**: Fully connected networks, deep belief networks (DBNs), recurrent neural networks (RNNs), convolutional neural networks (CNNs), generative adversarial networks (GANs), transformers, neural radiance fields (NeRFs).
- **Application domains**: Computer vision, speech recognition, NLP, machine translation, bioinformatics, drug design, medical imaging, climate science, game playing.
- **Theoretical foundations**: Universal approximation theorem (Cybenko 1989, Hornik 1991, Lu et al. for bounded-width deep nets), Bayesian/probabilistic inference.
- **Key techniques it enabled**: Representation learning, dropout regularization, greedy layer-by-layer pretraining.
- **Contrast with traditional ML**: Eliminates hand-crafted feature engineering but still requires architecture tuning (layer count, layer size).

## Exam-Relevant Points

- "Deep" means multiple layers (CAP depth > 2), not a specific threshold — there is no universally agreed-upon boundary between shallow and deep learning.
- CAP depth of 2 is sufficient for universal approximation, but deeper networks extract better features in practice.
- Lu et al. proved that for ReLU networks, the width must be **strictly larger than the input dimension** to be a universal approximator; width ≤ input dimension fails.
- The term "deep learning" was introduced to ML by **Rina Dechter in 1986** and to neural networks by Igor Aizenberg et al. in 2000.
- Cybenko (1989) proved universal approximation for sigmoid activations; Hornik (1991) generalized it to multi-layer feedforward architectures.
- Universal approximation also holds for unbounded activations like **ReLU** (rectified linear unit, originated by Fukushima).
- Deep belief networks are an example of deep structures trainable in an **unsupervised** manner — important because unlabeled data is far more abundant than labeled data.
- The **probabilistic interpretation** of neural networks led to **dropout** as a regularization technique.
- For RNNs, CAP depth is potentially **unlimited** because signals can propagate through a layer more than once.
