---
source: chunks/wiki-Backpropagation-chunk-6.md
source_url: https://en.wikipedia.org/wiki/Backpropagation
---

## Backpropagation: Mathematical Notation and Derivation Notes

This page collects clarifying annotations from a detailed treatment of the backpropagation algorithm (primarily following Nielsen, 2015). The notes address notation conventions, the role of matrix multiplication in layer-to-layer transformations, the nature of derivatives in the chain rule decomposition, and the use of linear neurons as a pedagogical simplification.

## Key Concepts

- **Loss function notation**: Use $C$ for the cost/loss function so that $L$ remains available to denote the number of layers in the network.
- **Weight matrix convention**: Left-multiplying by $W^l$ converts the output activations of layer $l-1$ into the input values (pre-activations) of layer $l$. Columns index input coordinates; rows index output coordinates.
- **Loss derivative is a covector**: The derivative of a scalar-valued loss function with respect to a vector of parameters is a covector (row vector / linear functional), not a column vector.
- **Activation function derivative**: Since activation functions apply element-wise, their Jacobian is a diagonal matrix. This is equivalently represented as a Hadamard (element-wise) product $\odot$ with the vector of per-node derivatives — mathematically identical but more efficient in implementation.
- **Derivative of a linear map**: $(Wx)' = W$. Matrix multiplication is linear, so its derivative with respect to the input is just the matrix itself.
- **Linear neuron approximation**: Although real networks use nonlinear activations, the error surface is locally approximable by a paraboloid, justifying the use of linear neurons for pedagogical derivations.
- **Multi-output error**: When multiple output neurons exist, the error is the squared norm of the difference vector (i.e., sum of squared per-output errors).
- **Weight subscript convention** (Rumelhart, Hinton & Williams 1986): $w_{ij}$ denotes the weight from unit $i$ to unit $j$.

## Commands and Syntax

No CLI commands apply. Key mathematical expressions:

- **Forward pass through layer $l$**: $z^l = W^l a^{l-1} + b^l$, then $a^l = f^l(z^l)$
- **Hadamard product form of activation derivative**: $(f^l)' \odot \delta^l$ replaces $\text{diag}((f^l)') \cdot \delta^l$
- **Linearity of matrix derivative**: $(Wx)' = W$

## Relationships

- **Chain rule / Computational graphs**: Backpropagation is the chain rule applied through the computational graph layer by layer; the covector nature of the loss derivative determines how gradients propagate backward.
- **Hadamard product vs. diagonal matrix**: Connects linear algebra representation (diagonal Jacobian) to efficient vectorized implementation (element-wise multiply) — foundational for understanding framework internals (NumPy, PyTorch).
- **Covectors and dual spaces**: The note that the loss derivative is a covector links backpropagation to differential geometry and the distinction between gradients and vectors in parameter space.
- **Error surfaces and optimization**: The paraboloid approximation connects to second-order methods (Newton's method, natural gradient) and explains why gradient descent works locally even on complex loss landscapes.

## Exam-Relevant Points

- **Weight matrix dimensions and convention**: Know that $W^l$ has rows = neurons in layer $l$, columns = neurons in layer $l-1$. The subscript convention $w_{ij}$ (from $i$ to $j$) follows Rumelhart et al. — some sources reverse this, so watch for convention differences on exams.
- **Hadamard product equivalence**: Be able to explain why element-wise multiplication by activation derivatives is equivalent to multiplication by a diagonal matrix, and why the former is preferred computationally.
- **Loss derivative is a covector**: This is a common conceptual exam question — the gradient of a scalar function is a row vector (dual space), not a column vector.
- **Multi-output error = squared norm**: $E = \|y - \hat{y}\|^2 = \sum_k (y_k - \hat{y}_k)^2$.
- **Linear approximation justification**: Be prepared to explain why studying linear networks is relevant — the local error surface of any smooth network is approximately quadratic (Taylor expansion).
