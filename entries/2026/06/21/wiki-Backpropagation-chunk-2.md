---
source: chunks/wiki-Backpropagation-chunk-2.md
source_url: https://en.wikipedia.org/wiki/Backpropagation
---

## Backpropagation as Matrix Multiplication

This page presents the matrix multiplication view of backpropagation in feedforward networks. It shows how the chain rule decomposes the loss gradient into a product of weight matrices and activation derivatives, evaluated right-to-left, and why this backward ordering is computationally superior to forward computation.

## Key Concepts

- **Forward pass caching**: During the forward pass, both activations a^l and activation derivatives (f^l)' (evaluated at z^l) must be cached for use in the backward pass.
- **Chain rule as matrix product**: The derivative of the loss w.r.t. inputs is a product of alternating terms: activation derivatives (diagonal matrices) and weight matrices, evaluated from output layer back to input.
- **Delta (δ^l) — the error signal**: A vector of length equal to the number of nodes in layer l, where each component represents the "cost attributable to that node." Defined as the gradient of the cost w.r.t. the pre-activation inputs at level l.
- **Recursive delta computation**: δ^(l-1) = (f^(l-1))' ∘ (W^l)^T · δ^l — each layer's error is computed from the next layer's error via one matrix-vector multiply and one elementwise multiply.
- **Weight gradient formula**: ∇_{W^l} C = δ^l · (a^(l-1))^T — an outer product of the error at layer l and the activations from layer l-1.
- **Gradient vs. derivative convention**: The gradient ∇_x C is the transpose of the derivative dC/dx, so the matrix product reverses order and transposes each weight matrix.
- **da^L/dz^L is a diagonal matrix**: The activation function derivative at the output layer produces a diagonal matrix (elementwise operation).

## Commands and Syntax

No software commands. Key mathematical procedures:

1. **Forward pass**: Compute z^l = W^l · a^(l-1), then a^l = f^l(z^l) for each layer. Cache a^l and (f^l)'.
2. **Initialize error**: δ^L = (f^L)' ∘ ∇_{a^L} C
3. **Backward recursion**: For l = L-1 down to 1: δ^l = (f^l)' ∘ (W^(l+1))^T · δ^(l+1)
4. **Weight gradients**: For each layer l: ∇_{W^l} C = δ^l · (a^(l-1))^T

## Relationships

- **Automatic differentiation**: Backpropagation is a special case of reverse-mode automatic differentiation (reverse accumulation). The adjoint graph formulation generalizes backpropagation beyond simple feedforward networks.
- **Chain rule**: The entire derivation rests on recursive application of the multivariate chain rule, with total derivatives at each node.
- **Loss functions**: The formulation assumes a scalar loss C(y, ŷ), which provides the initial gradient ∇_{a^L} C that seeds the backward pass.
- **Activation functions**: Their derivatives appear as elementwise (Hadamard product ∘) operations in the chain, converting between z-space and a-space at each layer.
- **Forward-mode differentiation**: Explicitly contrasted — forward mode multiplies matrices by matrices (tracking all paths), while backward mode multiplies vectors by matrices (much cheaper).

## Exam-Relevant Points

- **Why backward, not forward**: Backward propagation multiplies a *vector* by a matrix at each step (O(n^2) per layer). Forward propagation multiplies a *matrix* by a matrix (O(n^3) per layer) because it tracks all possible paths of change through the network. This is the core computational advantage.
- **Two efficiency gains of backprop**: (1) Recursive δ computation avoids redundant multiplication of layers already computed. (2) Right-to-left evaluation keeps the running quantity as a vector, not a matrix.
- **The weight gradient requires an extra step**: It is not just a sub-expression of the chain — it's an outer product δ^l · (a^(l-1))^T, which is why activations must be cached during the forward pass.
- **δ^l is a vector, not a matrix**: Its length equals the number of nodes in layer l. This is what makes backward multiplication efficient.
- **Transpose relationship**: The gradient expression uses (W^l)^T (transposed weights) and reverses multiplication order compared to the derivative expression — same entries, different arrangement.
- **Applicability constraint**: This clean matrix multiplication formulation applies to feedforward networks with no skip connections and a scalar loss function. More general architectures require the adjoint graph / reverse-mode AD framework.
