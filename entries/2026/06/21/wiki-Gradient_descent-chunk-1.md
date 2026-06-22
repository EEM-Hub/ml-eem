---
source: chunks/wiki-Gradient_descent-chunk-1.md
source_url: https://en.wikipedia.org/wiki/Gradient_descent
---

## Gradient Descent Optimization Algorithm

Gradient descent is a first-order iterative optimization algorithm for minimizing differentiable multivariate functions. It works by taking repeated steps in the opposite direction of the gradient at the current point, which is the direction of steepest descent. It is the foundational optimization method in machine learning and deep learning for minimizing cost/loss functions.

## Key Concepts

- **Core mechanism**: Move iteratively in the direction opposite to the gradient (negative gradient direction) to find a function's minimum
- **First-order method**: Uses only the gradient (first derivative), not higher-order derivatives like the Hessian
- **Gradient ascent**: The converse — stepping *in* the direction of the gradient to maximize a function
- **Unconstrained optimization**: Gradient descent applies to problems without constraints on the variable space
- **Requires differentiability**: The target function must be differentiable to compute gradients
- **Not the same as local search**: Though both are iterative optimization methods, they are distinct algorithm families
- **Historical origin**: Attributed to Augustin-Louis Cauchy (1847); independently proposed by Jacques Hadamard (1907); convergence properties for nonlinear problems first studied by Haskell Curry (1944)

## Commands and Syntax

No specific commands — this is a conceptual/mathematical topic. The core update rule is:

```
θ_{t+1} = θ_t - α · ∇f(θ_t)
```

Where `α` is the learning rate (step size) and `∇f(θ_t)` is the gradient of the objective function at the current parameters.

## Relationships

- **Stochastic Gradient Descent (SGD)**: A simple extension of gradient descent; the most basic algorithm for training deep networks today
- **Mathematical optimization**: Gradient descent is one method within the broader field of optimization
- **Loss/cost functions**: The primary use in ML is minimizing these objective functions
- **Machine learning training**: Serves as the backbone for model parameter updates during training
- **Method of steepest descent**: A distinct analytical method (not to be confused with gradient descent despite the name overlap)
- **Deep neural networks**: SGD and its variants are the standard training algorithms
- **First-order methods**: Part of a family that includes momentum, Adam, RMSProp, and other gradient-based optimizers

## Exam-Relevant Points

- Gradient descent moves in the **negative gradient direction** (steepest descent); gradient ascent moves in the positive gradient direction
- It is a **first-order** method (uses gradients only, not second derivatives)
- The function must be **differentiable** for gradient descent to apply
- Gradient descent is for **unconstrained** optimization
- **Stochastic gradient descent** is the foundational training algorithm for deep networks
- Do not confuse gradient descent with **local search** algorithms — they are distinct categories
- Cauchy (1847) is the standard attribution for the method's origin
