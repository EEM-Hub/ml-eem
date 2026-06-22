---
source: chunks/wiki-Gradient_descent-chunk-4.md
source_url: https://en.wikipedia.org/wiki/Gradient_descent
---

## Gradient Descent: Nonlinear Systems, Modifications, and Extensions

This page covers how gradient descent solves systems of nonlinear equations by reformulating them as an optimization problem, then discusses theoretical properties, convergence issues, and key modifications (momentum, Nesterov acceleration) that improve performance.

## Key Concepts

- **Solving nonlinear systems via optimization**: Given a system G(x) = 0, define the objective f(x) = ½ G^T(x) G(x) (sum of squared residuals), then minimize f using gradient descent. A solution to the system corresponds to f(x) = 0.
- **Gradient computation uses the Jacobian**: The gradient of f is ∇f = J_G^T · G, where J_G is the Jacobian matrix of the system G. This connects gradient descent to Newton-type methods.
- **Learning rate selection**: A suitable step size η must satisfy f(x^(k+1)) ≤ f(x^(k)); line search algorithms or manual tuning (e.g., η = 0.001) are used to ensure descent.
- **Works in any dimension**: Gradient descent generalizes to arbitrary (even infinite-dimensional) spaces via the Fréchet derivative; justified by the Cauchy-Schwarz inequality (descent is steepest when the update is colinear with the gradient).
- **Convergence issues**: Slow convergence when curvature varies across directions (ill-conditioning); can get stuck at saddle points; exhibits zig-zag patterns on elongated landscapes.
- **Preconditioning**: Reshapes the function's level sets to be more circular, curing slow convergence from ill-conditioning, but is computationally expensive to construct.
- **Gradient flow interpretation**: Gradient descent is Euler's method applied to the ODE x'(t) = -∇f(x(t)), connecting optimization to dynamical systems and optimal control theory.

## Commands and Syntax

**Gradient descent update rule:**
```
x^(k+1) = x^(k) - η_k · ∇f(x^(k))
```

**For nonlinear systems (G(x) = 0):**
```
f(x) = ½ G^T(x) G(x)
∇f(x) = J_G(x)^T · G(x)
x^(k+1) = x^(k) - η_k · J_G(x^(k))^T · G(x^(k))
```

**Momentum (heavy ball) update:**
```
x^(k+1) = x^(k) - η · ∇f(x^(k)) + β · (x^(k) - x^(k-1))
```

## Relationships

- **Jacobian matrix**: Required to compute ∇f for nonlinear system solving; connects to Newton's method and quasi-Newton methods.
- **Line search**: Used to select the step size η at each iteration.
- **Newton's method / BFGS / L-BFGS**: Higher-order alternatives that converge in fewer iterations but at higher per-iteration cost; BFGS multiplies the gradient by an approximation of the inverse Hessian.
- **Nesterov accelerated gradient (NAG)**: Improves convergence from O(k^-1) to O(k^-2) for convex, Lipschitz-smooth objectives.
- **Stochastic gradient descent (SGD)**: Stochastic variant; momentum techniques from heavy ball method are standard in SGD for neural network training (backpropagation).
- **Proximal gradient method**: Extension for constrained/non-smooth problems; accelerated variant is the fast proximal gradient method (FPGM).
- **Mirror descent**: Gradient descent is a special case using squared Euclidean distance as the Bregman divergence.
- **Conjugate gradient method**: Heavy ball method achieves asymptotically the same convergence bound for unconstrained quadratic minimization.
- **Projected gradient descent**: Handles constraints by projecting onto the feasible set after each gradient step; special case of the forward-backward algorithm.

## Exam-Relevant Points

- **Objective for nonlinear systems**: f(x) = ½ ||G(x)||² — know how to construct this from a system of equations and compute its gradient via the Jacobian.
- **Convergence rates**: Standard gradient descent achieves O(k^-1) error; Nesterov acceleration achieves O(k^-2), which is optimal for first-order methods. OGM further halves the constant factor.
- **Momentum breaks zig-zag**: The heavy ball method uses a linear combination of the current gradient and the previous update to dampen oscillation.
- **Key optimizers**: Adam, DiffGrad, Yogi, AdaBelief are all modifications of gradient descent using momentum and/or adaptive learning rates.
- **Preconditioning**: Transforms the problem geometry to make level sets more isotropic; trades computational cost for faster convergence.
- **Constraint handling**: Projected gradient descent works when projection onto the constraint set is efficiently computable.
- **Saddle points**: Gradient descent can slow down near saddle points — a known limitation for non-convex optimization.
- **Memory considerations**: For extremely large problems, L-BFGS is preferred over full BFGS or steepest descent due to memory efficiency.
- **Strong vs. non-strong convexity**: The O(k^-2) Nesterov rate applies when f is convex with Lipschitz gradient but not necessarily strongly convex.
