---
source: chunks/wiki-Backpropagation-chunk-4.md
source_url: https://en.wikipedia.org/wiki/Backpropagation
---

## Backpropagation: Mathematical Derivation of Gradient Descent

This page presents the full mathematical derivation of how backpropagation computes the gradient of the loss function with respect to each weight in a neural network. It walks through the chain rule decomposition step by step, covering both output-layer and hidden-layer neurons, and arrives at the weight update rule used in gradient descent.

## Key Concepts

- **Loss function**: E = L(t, y), where t is the target output and y is the actual output of the network (squared error case: ½(t - y)²)
- **Neuron output**: o_j = φ(net_j), where net_j = Σ w_kj · o_k is the weighted sum of inputs and φ is the activation function
- **Activation function requirements**: Must be non-linear and differentiable (ReLU is a practical exception — non-differentiable at 0 but widely used since AlexNet)
- **Logistic sigmoid**: φ(z) = 1/(1 + e^(-z)), with the convenient derivative φ'(z) = φ(z)(1 - φ(z))
- **Chain rule decomposition**: ∂E/∂w_ij is factored into three terms: (∂E/∂o_j) · (∂o_j/∂net_j) · (∂net_j/∂w_ij)
- **The δ (delta) term**: δ_j = (∂E/∂o_j) · (∂o_j/∂net_j) encapsulates the error signal at neuron j; the full gradient is simply ∂E/∂w_ij = o_i · δ_j
- **Output neuron δ**: δ_j = (o_j - t_j) · φ'(net_j) — computed directly from the loss derivative
- **Hidden neuron δ (recursive)**: δ_j = (Σ w_jℓ · δ_ℓ) · φ'(net_j) — error propagates backward from downstream neurons, which is the core mechanism that gives backpropagation its name
- **Weight indexing convention**: w_ij denotes the weight from unit i to unit j (reversed from some other notations)
- **∂net_j/∂w_ij simplifies to o_i**: Only the term involving w_ij survives differentiation of the weighted sum

## Commands and Syntax

**Weight update rule (gradient descent):**
```
Δw_ij = -η · (∂E/∂w_ij) = -η · o_i · δ_j
```

**Delta computation for output neurons (logistic + squared error):**
```
δ_j = (o_j - t_j) · o_j · (1 - o_j)
```

**Delta computation for hidden neurons (logistic activation):**
```
δ_j = (Σ_ℓ w_jℓ · δ_ℓ) · o_j · (1 - o_j)
```

**Forward pass (neuron output):**
```
net_j = Σ_k w_kj · o_k
o_j = φ(net_j)
```

## Relationships

- **Gradient descent**: Backpropagation is the algorithm that makes gradient descent feasible for multi-layer networks by providing an efficient way to compute ∂E/∂w for every weight
- **Activation functions**: The derivation requires differentiability of φ; the specific form of φ' appears directly in the δ computation (logistic, tanh, ReLU each yield different δ expressions)
- **Chain rule / total derivative**: The mathematical backbone — the recursive δ formula arises from applying the total derivative through the network graph
- **Loss functions**: The choice of loss (squared error, cross-entropy, etc.) only affects the ∂E/∂o_j term at the output layer; the rest of the derivation is loss-agnostic
- **Learning rate (η)**: Controls the step size; too large causes overshooting, too small causes slow convergence
- **AlexNet / ReLU**: ReLU's non-differentiability at 0 violates the theoretical requirement but works in practice (subgradient or convention of setting f'(0) = 0)

## Exam-Relevant Points

- The gradient ∂E/∂w_ij factors cleanly into **o_i · δ_j** — know this compact form
- The δ for **output neurons** uses the loss derivative directly; the δ for **hidden neurons** uses a weighted sum of downstream δ values — this recursive structure is the essence of "back" propagation
- The negative sign in Δw_ij = -η · ∂E/∂w_ij ensures the update **decreases** the error regardless of the sign of the gradient
- The logistic sigmoid's derivative φ'(z) = φ(z)(1 - φ(z)) = o_j(1 - o_j) is a classic exam formula
- Backpropagation **requires differentiable activation functions** in theory, but ReLU (non-differentiable at exactly 0) is the dominant choice in practice
- If a neuron in the next layer is not connected to neuron j, its contribution to the δ sum vanishes (partial derivative is zero)
- The derivation assumes **one output neuron**; multiple outputs generalize by summing over output dimensions
