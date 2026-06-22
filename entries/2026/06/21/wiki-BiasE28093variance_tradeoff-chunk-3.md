---
source: chunks/wiki-BiasE28093variance_tradeoff-chunk-3.md
source_url: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff
---

## Bias-Variance Tradeoff: Approaches and Applications

This page covers practical strategies for managing the bias-variance tradeoff across ML algorithms, plus how the decomposition applies in regression, classification, reinforcement learning, Monte Carlo methods, and human cognition.

## Key Concepts

- **Dimensionality reduction and feature selection** decrease variance by simplifying models; adding features decreases bias but increases variance.
- **Larger training sets** tend to decrease variance.
- **Regularization** (e.g., LASSO, ridge regression) introduces bias to reduce variance, often yielding superior MSE compared to unbiased OLS.
- **Ensemble methods** resolve the tradeoff: boosting combines high-bias (weak) learners to reduce bias; bagging combines strong learners to reduce variance.
- **k-NN closed-form decomposition**: bias is monotone rising with k; variance (σ²/k) drops as k increases. The 1-NN bias vanishes as training set size approaches infinity.
- In **classification** under 0-1 loss, the variance term becomes dependent on the target label (unlike regression).
- As training data increases, variance decreases — so larger datasets favor lower-bias (more complex) models.
- In **reinforcement learning**, suboptimality decomposes into asymptotic bias (algorithm-dependent) and overfitting (data-dependent), analogous to the classical tradeoff.
- **MCMC methods** are only asymptotically unbiased; a controlled bias is sometimes accepted to dramatically reduce variance and overall estimation error.
- **Human cognition** resolves the dilemma by adopting high-bias/low-variance heuristics, which generalize better given sparse, noisy experience (Gigerenzer).

## Commands and Syntax

No CLI commands. Key mathematical relationship for k-NN:

```
E[(y - f̂(x))² | X=x] = (f(x) - (1/k)Σf(Nᵢ(x)))² + σ²/k + σ²
                          \_________bias²_________/   \var/  \noise/
```

- First term (bias²): monotone rising function of k
- Second term (variance): σ²/k, decreases with k
- Third term: irreducible noise σ²

## Relationships

- **Regularization techniques**: LASSO, ridge regression — operationalize the tradeoff in regression
- **Ensemble methods**: boosting (reduces bias), bagging (reduces variance) — direct resolution strategies
- **Cross-validation / model validation**: used to tune models to optimize the tradeoff
- **Double descent**: modern phenomenon where very large models can escape the classical U-shaped test error curve
- **Hyperparameter optimization**: the mechanism by which algorithm-specific knobs (k, tree depth, hidden units, regularization strength) are tuned
- **Feature selection / dimensionality reduction**: variance-reducing preprocessing
- **Supervised learning**: the overarching framework in which the tradeoff operates

## Exam-Relevant Points

- **Per-algorithm knobs**: know which direction each parameter moves bias vs. variance — k in k-NN (high k = high bias, low variance), tree depth (deeper = lower bias, higher variance), hidden units in neural nets (more = lower bias, higher variance classically), regularization strength (stronger = higher bias, lower variance).
- **Boosting vs. bagging**: boosting reduces bias; bagging reduces variance. Know which ensemble addresses which problem.
- **Regularization vs. OLS**: regularized solutions are biased but can have lower MSE than unbiased OLS due to variance reduction.
- **k-NN decomposition**: be able to identify bias² and variance terms in the formula; know that 1-NN bias vanishes with infinite training data.
- **Classification caveat**: bias-variance decomposition under 0-1 loss differs from regression — the variance term depends on the true label.
- **More data favors complex models**: with large training sets, prefer lower-bias methods; with small data, minimizing variance is more important.
- **RL analogy**: suboptimality = asymptotic bias + overfitting; asymptotic bias is algorithm-dependent, overfitting is data-dependent.
- **Mixture models and ensemble learning** are cited as general resolution strategies for the tradeoff.
- **Cross-validation** is the standard method for tuning the tradeoff empirically.
