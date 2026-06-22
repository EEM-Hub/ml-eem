---
source: chunks/wiki-Support_vector_machine-chunk-3.md
source_url: https://en.wikipedia.org/wiki/Support_vector_machine
---

## Computing the SVM Classifier: Optimization Formulations and Algorithms

This page covers the mathematical machinery for solving the Support Vector Machine classification problem. It presents the soft-margin SVM objective function, derives both the primal and dual optimization formulations, explains the kernel trick for nonlinear classification, and describes modern solving methods (sub-gradient descent and coordinate descent).

## Key Concepts

- **Soft-margin SVM objective**: Minimizes the sum of hinge losses plus a regularization term: `(1/n) Σ max(0, 1 - yᵢ(wᵀxᵢ - b)) + λ‖w‖²`. The first term penalizes misclassifications; the second controls model complexity.
- **Slack variables (ζᵢ)**: Introduced to convert the hinge loss into a differentiable constrained optimization problem. Each ζᵢ = max(0, 1 - yᵢ(wᵀxᵢ - b)) measures how much a point violates the margin.
- **Primal formulation**: Minimize `(1/n) Σ ζᵢ + λ‖w‖²` subject to `yᵢ(wᵀxᵢ - b) ≥ 1 - ζᵢ` and `ζᵢ ≥ 0` for all i.
- **Dual formulation**: Maximize `Σ cᵢ - (1/2) Σᵢ Σⱼ yᵢcᵢ(xᵢᵀxⱼ)yⱼcⱼ` subject to `Σ cᵢyᵢ = 0` and `0 ≤ cᵢ ≤ 1/(2nλ)`. This is a quadratic programming problem with linear constraints.
- **Weight vector from dual variables**: `w = Σ cᵢyᵢxᵢ` — the weight vector is a linear combination of training points, weighted by the dual coefficients.
- **Support vectors**: Points where `cᵢ > 0`. Points correctly classified beyond the margin have `cᵢ = 0`; points on the margin boundary have `0 < cᵢ < 1/(2nλ)`.
- **Bias recovery**: Find a support vector on the margin boundary and solve `b = wᵀxᵢ - yᵢ` (exploiting the fact that `yᵢ⁻¹ = yᵢ` since labels are ±1).
- **Kernel trick**: Replace dot products `xᵢᵀxⱼ` with `k(xᵢ, xⱼ) = φ(xᵢ)·φ(xⱼ)` in the dual. This allows learning nonlinear decision boundaries without explicitly computing the transformation φ.
- **Kernelized prediction**: `z ↦ sgn(Σ cᵢyᵢk(xᵢ, z) - b)` — classification depends only on kernel evaluations between the new point and support vectors.
- **λ as margin/misclassification tradeoff**: Sufficiently small λ yields the hard-margin classifier (if data is linearly separable).

## Commands and Syntax

No CLI commands; this is a mathematical formulation topic. Key algorithmic procedures:

- **Quadratic programming (QP)**: Solve the dual by feeding the quadratic objective with linear constraints into a QP solver.
- **Sub-gradient descent**: Work directly on the primal objective `f(w, b)`. At each step, take a step in the direction of a sub-gradient (since the hinge loss is not differentiable everywhere). Iteration count does not necessarily scale with n.
- **Coordinate descent**: Work from the dual. Iteratively adjust each `cᵢ` in the direction of `∂f/∂cᵢ`, then project back onto the feasible set. Extremely fast in practice, especially in high-dimensional feature spaces.

## Relationships

- **Quadratic programming**: The dual is a QP problem; classical SVM solvers (e.g., SMO) exploit this structure.
- **Kernel methods**: The kernel trick generalizes SVMs to nonlinear classification. Common kernels (RBF, polynomial) plug directly into the dual formulation.
- **Convex optimization**: The SVM objective is convex, guaranteeing a global optimum. Sub-gradient methods leverage this property.
- **Lagrangian duality**: The dual formulation is derived via the Lagrangian dual of the primal constrained problem; strong duality holds.
- **Stochastic gradient descent (SGD)**: Sub-gradient methods for SVM are closely related to SGD approaches used throughout deep learning.
- **Regularization**: The λ‖w‖² term connects to ridge regression and the broader concept of L2 regularization.

## Exam-Relevant Points

- The soft-margin SVM reduces to the hard-margin SVM when λ is sufficiently small and data is linearly separable.
- The dual formulation involves only dot products between data points, which is what enables the kernel trick.
- `w` is expressible as a linear combination of support vectors only (`w = Σ cᵢyᵢxᵢ`); most `cᵢ = 0`.
- The constraint `Σ cᵢyᵢ = 0` and the box constraint `0 ≤ cᵢ ≤ 1/(2nλ)` define the feasible region of the dual.
- Bias `b` is recovered from any support vector on the margin boundary, not from all training points.
- Sub-gradient descent is preferred for large n (many training examples); coordinate descent is preferred for high-dimensional feature spaces.
- The kernel trick avoids explicit computation in the transformed feature space — only kernel evaluations `k(xᵢ, xⱼ)` are needed.
- The kernelized classifier's prediction depends only on support vectors, making it sparse in terms of the training data.
- The SVM objective is convex, so any local minimum is the global minimum.
