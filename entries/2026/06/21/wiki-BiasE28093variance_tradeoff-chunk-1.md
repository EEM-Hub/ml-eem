---
source: chunks/wiki-BiasE28093variance_tradeoff-chunk-1.md
source_url: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff
---

## Bias-Variance Tradeoff

The bias-variance tradeoff is a fundamental concept in supervised learning that describes how a model's complexity affects its ability to fit training data versus generalize to unseen data. As model flexibility increases (more tunable parameters), bias decreases but variance increases. The total generalization error decomposes into three terms: bias, variance, and irreducible error (noise inherent to the problem).

## Key Concepts

- **Bias** — error from erroneous assumptions in the learning algorithm; high bias causes underfitting, where the model misses relevant relationships between features and targets.
- **Variance** — error from sensitivity to small fluctuations in the training set; high variance causes overfitting, where the model captures noise rather than signal.
- **Irreducible error** — noise inherent in the problem itself; cannot be reduced by any model.
- **Bias-variance decomposition** — expected generalization error = bias² + variance + irreducible error.
- **Model complexity is not simply parameter count** — a model f(x) = a·sin(bx) has only two parameters but can interpolate arbitrarily many points via high-frequency oscillation, producing both high bias and high variance.
- **Complex models do not necessarily have high variance** — high variance models are complex in some sense, but the reverse is a common fallacy.
- **Accuracy vs. precision analogy** — bias corresponds to accuracy (systematic offset from truth), variance corresponds to precision (spread of predictions across different training sets).
- **Regularization** (e.g., shrinkage) explicitly smooths a model to control the tradeoff by limiting how much neighboring observations influence predictions.

## Commands and Syntax

No specific commands. The core mathematical relationship is:

```
Expected Error = Bias² + Variance + Irreducible Error
```

The RBF (radial basis function) example illustrates the tradeoff via a "spread" hyperparameter:
- **Large spread** (e.g., 5): high bias, low variance — smooth but poor fit
- **Small spread** (e.g., 0.1): low bias, high variance — close fit on training data but wildly different across trials

## Relationships

- **Overfitting / Underfitting** — bias-variance tradeoff is the theoretical framework explaining why these occur; high variance → overfitting, high bias → underfitting.
- **Model Selection** — choosing model complexity is fundamentally about navigating this tradeoff.
- **Regularization** — techniques like L1/L2 regularization, shrinkage, and dropout are direct interventions to shift the bias-variance balance toward lower variance at the cost of slightly higher bias.
- **Generalization Error** — the decomposition provides a formal way to analyze why a model fails to generalize.
- **Ensemble Methods** — bagging reduces variance (e.g., random forests); boosting reduces bias (e.g., gradient boosting).
- **Cross-Validation** — empirical method for estimating the bias-variance balance without the formal decomposition.
- **Double Descent** — modern deep learning challenges the classical U-shaped tradeoff curve; very overparameterized models can have low bias AND low variance.

## Exam-Relevant Points

- The bias-variance decomposition splits expected generalization error into exactly three terms: bias², variance, and irreducible error.
- High bias → underfitting; high variance → overfitting. Know both directions.
- Increasing model complexity decreases bias but increases variance (classical regime).
- Number of parameters is a **poor** measure of model complexity — know the sin(bx) counterexample.
- It is a **fallacy** to assume complex models must have high variance.
- Regularization trades increased bias for decreased variance to improve generalization.
- The ideal model minimizes total error (the sum), not bias or variance independently — the minimum total error occurs at an intermediate complexity.
- The tradeoff is specific to **supervised learning** problems.
- Know the four quadrants: (high bias, low variance), (high bias, high variance), (low bias, low variance), (low bias, high variance) — only low bias + low variance is desirable.
