---
source: chunks/wiki-Gradient_descent-chunk-3.md
source_url: https://en.wikipedia.org/wiki/Gradient_descent
---

## Gradient Descent for Solving Linear Systems

This page covers how gradient descent (steepest descent) can be reformulated to solve systems of linear equations **Ax = b** by casting them as quadratic minimization problems. It details the objective functions, gradient derivations, optimal step-size formulas, algorithmic pseudocode, and the geometric reasons steepest descent converges slowly compared to conjugate gradient methods.

## Key Concepts

- **Quadratic reformulation**: The linear system **Ax - b = 0** is solved by minimizing a quadratic objective function rather than solving the equation directly.
- **Symmetric positive-definite (SPD) case**: When **A** is real symmetric and positive-definite, the objective is f(**x**) = **x**^T **A** **x** - 2**x**^T **b**, with gradient nabla f(**x**) = 2(**Ax** - **b**).
- **General (non-SPD) case**: For a general real matrix **A**, the problem becomes linear least squares: minimize f(**x**) = ||**Ax** - **b**||^2, with gradient nabla f(**x**) = 2**A**^T(**Ax** - **b**).
- **Analytical line search**: For quadratic objectives, the optimal step size eta can be computed in closed form on every iteration — no numerical line search is needed.
- **Optimal step size formula (SPD case)**: eta = (**r**^T **r**) / (**r**^T **A** **r**), where **r** = **b** - **Ax** is the residual.
- **Residual orthogonality**: Consecutive residual vectors are orthogonal: <**r**_{k+1}, **r**_k> = 0. This is a direct consequence of exact line search in the steepest descent direction.
- **Zig-zag convergence**: Orthogonality of successive residuals forces the path to alternate between directions aligned with the extreme axes of elongated level sets, producing a characteristic zig-zag pattern.
- **Condition number dependence**: The number of gradient descent iterations is proportional to the spectral condition number kappa(**A**) = lambda_max / lambda_min of **A**^T**A**. Poorly conditioned systems converge very slowly.
- **Conjugate gradient is superior**: Conjugate gradient convergence depends on sqrt(kappa(**A**)), making it much faster. Steepest descent is rarely used for linear systems in practice.

## Commands and Syntax

**Simple steepest descent algorithm (SPD matrix):**
```
r := b - Ax
repeat:
    eta := (r^T r) / (r^T A r)
    x := x + eta * r
    if r^T r is sufficiently small, exit
    r := r - eta * A r
end repeat
return x
```

Key implementation note: The traditional algorithm computes **r** := **b** - **Ax** once before the loop, then updates the residual incrementally as **r** := **r** - eta * **Ar** inside the loop. This avoids a redundant matrix-vector multiplication per iteration (only one multiply by **A** per iteration instead of two).

## Relationships

- **Conjugate gradient method**: The primary alternative for solving linear systems iteratively; converges in sqrt(kappa) iterations vs. kappa for steepest descent.
- **Preconditioning**: Both steepest descent and conjugate gradient benefit from preconditioning; steepest descent may require fewer assumptions on the preconditioner.
- **Linear least squares**: The general-case formulation connects gradient descent to least-squares regression and the normal equations (**A**^T**A****x** = **A**^T**b**).
- **Wiener filter**: Steepest descent is applied to adaptive filtering problems (shown in the referenced figure).
- **Line search**: The analytical step-size computation is a special case of line search that exploits the quadratic structure of the objective.
- **Condition number / eigenvalues**: Convergence analysis ties directly to spectral properties of the system matrix.

## Exam-Relevant Points

- The quadratic objective for SPD **A** is f(**x**) = **x**^T**A****x** - 2**x**^T**b**; for general **A** it is f(**x**) = ||**Ax** - **b**||^2. Know both formulations and their gradients.
- The optimal step size for SPD steepest descent is eta = (**r**^T**r**) / (**r**^T**A****r**) — be able to derive this from the line search condition.
- Successive residuals are orthogonal in steepest descent with exact line search. This is a frequently tested property.
- Steepest descent convergence is O(kappa), conjugate gradient is O(sqrt(kappa)). This is the central reason conjugate gradient is preferred.
- The zig-zag behavior arises because residual orthogonality forces each step to alternate between the principal axes of the elliptical level sets, especially when the condition number is large.
- The incremental residual update **r** := **r** - eta * **Ar** is an optimization that halves the matrix-vector products per iteration.
- Steepest descent requires **A** to be SPD for the quadratic reformulation to have a unique minimum; for general **A**, the least-squares formulation effectively works with **A**^T**A** (which is always positive semi-definite).
