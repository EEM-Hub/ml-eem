---
source: chunks/wiki-Support_vector_machine-chunk-2.md
source_url: https://en.wikipedia.org/wiki/Support_vector_machine
---

## Linear SVM and Nonlinear Kernels

This page covers the mathematical formulation of Support Vector Machines, starting with the linear case (hard-margin and soft-margin) and extending to nonlinear classification via the kernel trick. It details how SVMs find the maximum-margin hyperplane separating two classes, and how kernels allow this to work in transformed feature spaces.

## Key Concepts

- **SVM objective**: Find the hyperplane `w^T x - b = 0` that maximizes the margin (distance) between two classes labeled +1 and -1.
- **Margin**: The region between the two parallel hyperplanes `w^T x - b = 1` and `w^T x - b = -1`. The geometric width of the margin is `2 / ||w||`.
- **Support vectors**: The training points that lie exactly on the margin boundary. The maximum-margin hyperplane is completely determined by these points alone.
- **Hard-margin SVM**: Assumes data is linearly separable. Minimizes `(1/2)||w||^2` subject to `y_i(w^T x_i - b) >= 1` for all i. No misclassifications are permitted.
- **Soft-margin SVM**: Handles non-separable data by introducing slack variables `zeta_i >= 0` and hinge loss `max(0, 1 - y_i(w^T x_i - b))`. Minimizes `||w||^2 + C * sum(zeta_i)`.
- **Regularization parameter C**: Controls the trade-off between maximizing the margin and minimizing classification errors. Large C approximates hard-margin behavior; small C allows more violations for a wider margin.
- **Hinge loss**: Zero when a point is correctly classified beyond the margin; grows linearly with distance from the margin for violations.
- **Kernel trick**: Replaces dot products with kernel functions `k(x_i, x_j) = phi(x_i) . phi(x_j)`, enabling nonlinear decision boundaries without explicitly computing the high-dimensional transformation.
- **Classifier decision function**: `x -> sgn(w^T x - b)` for linear; `x -> sgn(sum_i alpha_i y_i k(x_i, x) - b)` for kernelized.

## Commands and Syntax

**Hard-margin optimization problem:**
```
minimize    (1/2) ||w||^2
subject to  y_i (w^T x_i - b) >= 1,  for all i in {1, ..., n}
```

**Soft-margin optimization problem:**
```
minimize    ||w||^2 + C * sum(zeta_i)
subject to  y_i (w^T x_i - b) >= 1 - zeta_i,  zeta_i >= 0,  for all i
```

**Common kernel functions:**
| Kernel | Formula |
|--------|---------|
| Linear | `k(x_i, x_j) = x_i . x_j` |
| Polynomial (homogeneous) | `k(x_i, x_j) = (x_i . x_j)^d` |
| Polynomial (inhomogeneous) | `k(x_i, x_j) = (x_i . x_j + r)^d` |
| Gaussian RBF | `k(x_i, x_j) = exp(-gamma * ||x_i - x_j||^2)`, gamma > 0 |
| Sigmoid | `k(x_i, x_j) = tanh(kappa * x_i . x_j + c)`, valid for some kappa > 0, c < 0 |

**Kernel-based weight vector:**
```
w = sum_i alpha_i * y_i * phi(x_i)
w . phi(x) = sum_i alpha_i * y_i * k(x_i, x)
```

## Relationships

- **Convex optimization**: Both hard- and soft-margin SVM are convex quadratic programs, solvable via their Lagrangian dual (where the kernel trick is naturally derived).
- **Hinge loss**: The soft-margin SVM uses hinge loss, connecting it to empirical risk minimization frameworks. Contrast with logistic regression (log loss) and perceptron (zero-one loss approximation).
- **Regularization**: The `||w||^2` term acts as L2 regularization; the C parameter plays the same role as inverse regularization strength (compare with `lambda` in ridge regression).
- **Kernel methods**: SVMs are part of the broader family of kernel methods (kernel PCA, kernel ridge regression). Kernels must satisfy Mercer's condition (positive semi-definiteness).
- **Feature spaces**: The kernel trick maps data to high- (possibly infinite-) dimensional spaces, connecting to the theory of Reproducing Kernel Hilbert Spaces (RKHS).
- **Generalization error**: Working in higher-dimensional feature spaces increases generalization error, but SVMs can still perform well with sufficient samples (connects to VC dimension and structural risk minimization).

## Exam-Relevant Points

- The margin width is `2 / ||w||` — maximizing the margin means minimizing `||w||`.
- Support vectors are the only training points that influence the decision boundary; all other points could be removed without changing the result.
- Hard-margin SVM requires linearly separable data; soft-margin SVM does not.
- The parameter C controls the margin-error trade-off: large C penalizes misclassifications heavily (narrower margin, fewer errors); small C allows more slack (wider margin, more errors).
- Slack variables `zeta_i` measure how much each point violates the margin constraint.
- The kernel trick avoids explicit computation of `phi(x)` — only dot products in the transformed space are needed, computed via `k(x_i, x_j)`.
- The RBF kernel can map to an infinite-dimensional feature space.
- The sigmoid kernel is only a valid kernel for certain parameter values (not universally).
- The bias term convention varies across literature: some use `w^T x - b = 0`, others `w^T x + b = 0` — watch for sign differences.
- Historical note: Vapnik proposed the linear SVM in 1963; the kernelized version was introduced by Boser, Guyon, and Vapnik in 1992.
