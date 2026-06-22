---
source: chunks/wiki-Backpropagation-chunk-5.md
source_url: https://en.wikipedia.org/wiki/Backpropagation
---

## Backpropagation: Second-Order Methods, Loss Functions, Limitations, and History

This page covers advanced aspects of the backpropagation algorithm beyond the basic first-order gradient computation. It details second-order gradient descent using the Hessian matrix, the formal requirements for loss functions used in backpropagation, known limitations of gradient-based learning, and the full historical development of backpropagation from its precursors in optimal control theory through modern deep learning.

## Key Concepts

- **Second-order gradient descent** uses the Hessian matrix (matrix of second-order partial derivatives) to achieve faster convergence than first-order methods, especially on complex error surfaces.
- The **Levenberg–Marquardt algorithm** is a key second-order method that may find solutions with smaller network architectures where first-order methods fail.
- The Hessian can be **approximated by the Fisher information matrix**, reducing computational cost.
- **Second-order backpropagation** propagates second derivatives backward through layers, involving both first and second derivatives of activation functions (f' and f'') and a Kronecker delta term.
- Arbitrary-order derivatives can be computed via backpropagation in arbitrary computational graphs, though expressions grow more complex at higher orders.
- **Loss function requirements for backpropagation**: (1) must be expressible as an average over individual training examples: E = (1/n) Σ E_x; (2) must be expressible as a function of the network's outputs.
- The standard loss function is **mean squared error (MSE)**: E = (1/2n) Σ ||y(x) - y'(x)||².
- **Limitations**: gradient descent finds local minima, not guaranteed global minima; has trouble crossing plateaus; requires known activation function derivatives at design time; input normalization is not required but improves performance.
- The non-convexity problem, long considered a major drawback, was argued by Yann LeCun et al. to be non-critical in many practical problems.

## Commands and Syntax

- **Forward pass at layer l**: x_i^(l) is the pre-activation, a_i^(l) = f(x_i^(l)) is the activation, x_i^(l+1) = Σ_j W_ij a_j^(l)
- **First-order backpropagation**: ∂L/∂a_j^(l) = Σ_j W_ij · ∂L/∂x_i^(l+1); ∂L/∂x_j^(l) = f'(x_j^(l)) · ∂L/∂a_j^(l)
- **Second-order backpropagation**: ∂²L/∂a_{j1}∂a_{j2} = Σ W_{i1,j1} W_{i2,j2} · ∂²L/∂x_{i1}∂x_{i2}; ∂²L/∂x_{j1}∂x_{j2} = f'(x_{j1})f'(x_{j2}) · ∂²L/∂a_{j1}∂a_{j2} + δ_{j1,j2} f''(x_{j1}) · ∂L/∂a_{j1}
- **MSE loss**: E(y, y') = (1/2) ||y - y'||²

## Relationships

- **Hessian matrix**: provides the curvature information used in second-order methods
- **Fisher information matrix**: practical approximation to the Hessian for neural networks
- **Levenberg–Marquardt algorithm**: the primary second-order optimization method discussed
- **Optimal control theory / adjoint state method**: continuous-time precursor to backpropagation (Pontryagin et al., 1950s)
- **Automatic differentiation (reverse mode)**: the mathematical framework underlying modern backpropagation (Linnainmaa, 1970)
- **Chain rule**: the fundamental calculus principle that backpropagation implements efficiently
- **Backpropagation through time (BPTT)**: extension for recurrent networks
- **Backpropagation through structure**: extension for structured/tree-shaped architectures
- **Stochastic gradient descent**: the optimization framework in which backpropagation computes gradients
- **Convex optimization**: backpropagation's error surfaces are non-convex, distinguishing neural network optimization from convex problems

## Exam-Relevant Points

- The Levenberg–Marquardt algorithm uses second-order (Hessian) information and converges faster than first-order gradient descent on complex error landscapes.
- The Fisher information matrix is used to approximate the Hessian.
- Two requirements for a loss function to be used with backpropagation: (1) decomposable as an average over individual examples, (2) expressible as a function of network outputs.
- Gradient descent with backpropagation finds local minima only — no guarantee of a global minimum. LeCun et al. argued this is often acceptable in practice.
- Input normalization is not required by backpropagation but can improve performance.
- Activation function derivatives must be known at network design time.
- **Historical timeline**: Leibniz chain rule (1676) → optimal control precursors (1950s–1960s) → Linnainmaa's reverse-mode autodiff (1970) → Werbos applied to MLPs (1982) → Rumelhart/Hinton/Williams popularized in Nature (1986) → early successes: NETtalk (1987), ALVINN autonomous driving (1989), LeNet (1989), TD-Gammon (1992) → GPU-driven resurgence (2010s) → photonic implementation at Stanford (2023).
- Seppo Linnainmaa (1970) published the first modern backpropagation as reverse-mode automatic differentiation.
- Paul Werbos (1982) first applied backpropagation to multilayer perceptrons in the standard modern way.
- Rumelhart, Hinton, and Williams (1986 Nature paper) popularized backpropagation and triggered the 1980s neural network resurgence.
- Shun'ichi Amari (1967) published the first multilayer perceptron trained by stochastic gradient descent (5 layers, 2 learnable).
- The second-order backpropagation formula includes a **Kronecker delta term** (δ_{j1,j2}) multiplied by f''—this term only appears when j1 = j2, reflecting the diagonal structure of the second derivative of the activation function.
