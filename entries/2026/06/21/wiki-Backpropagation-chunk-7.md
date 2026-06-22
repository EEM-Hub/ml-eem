---
source: chunks/wiki-Backpropagation-chunk-7.md
source_url: https://en.wikipedia.org/wiki/Backpropagation
---

## Backpropagation: Key References and Historical Bibliography

This page is the references section of the Wikipedia article on Backpropagation, listing the primary sources that document the algorithm's development, theoretical foundations, and applications. It provides a comprehensive bibliography tracing backpropagation from its mathematical origins through its modern use in deep learning.

## Key Concepts

- **Backpropagation is not the full learning algorithm** — it only computes the gradient; a separate algorithm (e.g., SGD) performs the actual parameter updates (Goodfellow et al., 2016, p. 200).
- **Backpropagation is a special case of reverse mode automatic differentiation** (Goodfellow et al., 2016, pp. 217–218).
- **Cost function assumptions for backpropagation**: (1) cost must be expressible as an average over individual training examples, and (2) cost must be a function of the network's outputs (Nielsen, 2015).
- **Second-order optimization methods** (e.g., Levenberg–Marquardt, natural gradient) offer alternatives to first-order gradient descent for backpropagation training (Tan & Lim, 2019; Martens, 2020; Wiliamowski & Yu, 2010).
- **Activation function research**: Swish (Ramachandran et al., 2017) and Mish (Misra, 2019) are notable learned/designed activation functions discovered through search.

## Commands and Syntax

No commands or configuration syntax — this is a bibliography. However, the references point to key mathematical formulations:
- **Chain rule** (Leibniz, 1676) — the foundational calculus operation underlying backpropagation.
- **Stochastic approximation** (Robbins & Monro, 1951) — the statistical foundation for SGD.
- **Reverse mode differentiation** (Linnainmaa, 1970) — the algorithmic differentiation technique that backpropagation implements.

## Relationships

- **Optimal control theory**: Kelley (1960) and Bryson (1961–62) developed gradient methods for optimal control that are precursors to backpropagation; Dreyfus (1962, 1973) connected these to computational solutions.
- **Automatic differentiation**: Linnainmaa (1970, 1976) formalized reverse mode AD; Griewank (2012) traces its invention history.
- **Neural network learning**: Werbos (1974, 1982) first applied backpropagation to neural networks; Rumelhart, Hinton & Williams (1986) popularized it; Parker (1985) and LeCun (1987) independently developed similar approaches.
- **Deep learning**: LeCun, Bengio & Hinton (2015) and Schmidhuber (2015, 2022) provide historical overviews connecting backpropagation to modern deep learning.
- **Applications**: ALVINN autonomous driving (Pomerleau, 1988), TD-Gammon reinforcement learning (Sutton & Barto, 2018), language modeling (Chang et al., 2006; Fitz & Chang, 2019).
- **Hardware**: Photonic chips for energy-efficient backpropagation training (IEEE Spectrum, 2023).

## Exam-Relevant Points

- **Backpropagation ≠ learning algorithm**: It only computes gradients. Learning requires a separate optimizer (SGD, Adam, etc.).
- **Backpropagation = reverse mode automatic differentiation** (special case).
- **Historical priority**: Kelley (1960) and Bryson (1961) first described the gradient computation; Linnainmaa (1970) formalized reverse mode AD; Werbos (1974/1982) applied it to neural networks; Rumelhart, Hinton & Williams (1986) popularized it for the ML community.
- **Two cost function requirements**: (1) decomposable as average over individual examples, (2) must be a function of network outputs.
- **Nobel Prize in Physics 2024** was awarded in connection with neural network research (Hinton recognized).
- **Backpropagation Through Time (BPTT)**: Werbos (1990) described how to apply backpropagation to recurrent networks.
- **Second-order methods** (Levenberg–Marquardt, natural gradient) can improve convergence over basic gradient descent but at higher computational cost.
- **Robbins-Monro (1951)** stochastic approximation is the theoretical foundation for stochastic gradient descent.
