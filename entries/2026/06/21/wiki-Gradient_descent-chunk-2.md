---
source: chunks/wiki-Gradient_descent-chunk-2.md
source_url: https://en.wikipedia.org/wiki/Gradient_descent
---

## Gradient Descent: Core Algorithm and Convergence

Gradient descent is the foundational iterative optimization algorithm in machine learning. It finds local minima of differentiable functions by repeatedly stepping in the direction of the negative gradient. This page covers the mathematical formulation, convergence guarantees, step size selection strategies, and the relationship between descent direction and convergence rate.

## Key Concepts

- **Update rule**: x_{n+1} = x_n - η_n ∇f(x_n), where η is the learning rate (step size) and ∇f is the gradient
- The negative gradient gives the direction of **steepest descent** — the direction in which f decreases fastest
- The negative gradient at any point is **orthogonal to the contour line** (level set) passing through that point
- The update produces a **monotonically decreasing sequence** of function values: f(x_0) ≥ f(x_1) ≥ f(x_2) ≥ ...
- The step size η can **vary at every iteration** (η_n)
- **Too small** a learning rate causes slow convergence; **too large** causes overshoot and divergence
- For **convex functions**, all local minima are global minima, so gradient descent converges to the global solution
- Convergence to a local minimum is guaranteed under assumptions such as f being convex and ∇f being Lipschitz continuous
- The descent direction need not be the gradient itself — any direction with **positive inner product** with the negative gradient will reduce f (for small enough η)
- The guaranteed decrease depends on a **tradeoff**: the angle between descent direction and negative gradient vs. how fast the gradient changes along that direction

## Commands and Syntax

**Standard gradient descent update:**
```
x_{n+1} = x_n - η ∇f(x_n)
```

**Generalized update with arbitrary descent direction p:**
```
a_{n+1} = a_n - η_n * p_n
```
Requires cos(θ_n) > 0, where θ_n is the angle between p_n and -∇f(a_n).

**Barzilai-Borwein adaptive step size:**
```
η_n = | (x_n - x_{n-1})^T [∇f(x_n) - ∇f(x_{n-1})] | / ‖∇f(x_n) - ∇f(x_{n-1})‖²
```

**Step size selection strategies:**
1. Use line search (Wolfe conditions or backtracking line search) with p_n = ∇f(a_n)
2. Use the Hessian ∇²f to approximate gradient variation, then optimize step/direction jointly
3. Use the Lipschitz constant L of ∇f to bound gradient variation: ‖∇f(a-tηp) - ∇f(a)‖ ≤ Ltη‖p‖
4. Build a custom model of gradient variation for the specific f

## Relationships

- **Learning rate / step size**: Central hyperparameter governing convergence speed and stability
- **Line search** (Wolfe conditions, backtracking): Methods for adaptively choosing η at each step
- **Convexity**: Determines whether local minima are global; stronger convergence guarantees
- **Lipschitz continuity** of ∇f: Key assumption for proving convergence rates
- **Hessian (second-order methods)**: Enables better step size/direction estimation (connects to Newton's method)
- **Saddle points**: Gradient descent can get stuck at saddle points, not just local minima
- **Barzilai-Borwein method**: Adaptive step size using successive gradient differences
- **Stochastic gradient descent (SGD)**: Practical variant using approximate gradients from mini-batches
- **Momentum, Adam, etc.**: Extensions that modify the descent direction p_n beyond the raw gradient

## Exam-Relevant Points

- The update rule x_{n+1} = x_n - η∇f(x_n) and each term's role (know this cold)
- The gradient is orthogonal to contour lines — frequently tested geometric fact
- For **convex** f, gradient descent converges to the **global** minimum
- Convergence requires f differentiable and typically ∇f Lipschitz continuous
- Step size too large → divergence; too small → slow convergence
- Barzilai-Borwein uses consecutive gradient differences to set η adaptively (no line search needed)
- Wolfe conditions provide sufficient conditions on step size for guaranteed convergence
- Any direction with positive inner product with -∇f is a valid descent direction (not just the gradient itself)
- The monotonic decrease property: f(x_0) ≥ f(x_1) ≥ f(x_2) ≥ ... holds for sufficiently small η
- Gradient descent can converge to local minima or saddle points in non-convex problems
