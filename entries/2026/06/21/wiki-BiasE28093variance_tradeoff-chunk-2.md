---
source: chunks/wiki-BiasE28093variance_tradeoff-chunk-2.md
source_url: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff
---

## Bias–Variance Decomposition of Mean Squared Error

This page presents the formal mathematical decomposition of mean squared error (MSE) into three additive components: squared bias, variance, and irreducible error. It covers the setup (supervised learning with noisy labels), states the decomposition theorem, defines each term precisely, and provides the full step-by-step derivation proving the result.

## Key Concepts

- **Data-generating assumption**: Labels follow y = f(x) + ε, where ε is zero-mean noise with variance σ². The true function f(x) is deterministic but unknown.
- **Goal**: Find an estimator f̂(x; D) trained on dataset D that minimizes MSE on unseen points, not just training points.
- **The decomposition**: For a fixed test point x, the expected MSE decomposes as:
  - **MSE(x) = Bias²[f̂(x)] + Var[f̂(x)] + σ²**
- **Bias**: The difference between the expected prediction E_D[f̂(x; D)] and the true function f(x). Measures systematic error from model assumptions (e.g., fitting a linear model to nonlinear data).
- **Variance**: How much the prediction f̂(x; D) fluctuates as the training set D changes. Measures sensitivity to the particular training sample drawn.
- **Irreducible error (σ²)**: The noise variance inherent in the data. No model can reduce error below this floor.
- **All three terms are non-negative**, so σ² is a hard lower bound on achievable MSE.
- **Expectations are taken over**: (1) random training sets D sampled from P(x, y), and (2) the noise ε in the test label. Training sets can be generated via bootstrapping.
- **Complexity tradeoff**: More complex models capture more structure (lower bias) but become more sensitive to the specific training set (higher variance).

## Commands and Syntax

No commands per se, but the key mathematical definitions:

- **Bias**: Bias_D[f̂(x; D)] ≜ E_D[f̂(x; D)] − f(x)
- **Variance**: Var_D[f̂(x; D)] ≜ E_D[(E_D[f̂(x; D)] − f̂(x; D))²]
- **Irreducible error**: σ² = E_y[(y − f(x))²]
- **Full MSE** (over x): MSE = E_x{Bias_D[f̂(x; D)]² + Var_D[f̂(x; D)]} + σ²

## Derivation Outline

1. Substitute y = f(x) + ε into (y − f̂)² and expand the square into three terms.
2. The cross-term E[(f(x) − f̂(x))·ε] vanishes because ε is independent of x and has zero mean.
3. The third term E[ε²] = σ².
4. Add and subtract E[f̂(x)] inside the remaining squared term, expand, and show the cross-term vanishes because f(x) is deterministic (not random).
5. Identify the remaining pieces as Bias² and Var.

## Relationships

- **Mean Squared Error**: The decomposition is specific to the MSE loss function; other loss functions (e.g., 0-1 loss for classification) have different decompositions.
- **Bias–Variance Tradeoff**: This decomposition is the mathematical foundation for the tradeoff — it proves that bias and variance are the only two controllable error sources.
- **Model Complexity / Regularization**: Regularization reduces variance at the cost of increased bias. The decomposition quantifies this tradeoff.
- **Supervised Learning Algorithms**: Applies to any estimator (linear regression, decision trees, neural networks, k-NN, etc.).
- **Bootstrapping**: One practical method for approximating the expectation over training sets D.
- **Overfitting/Underfitting**: Overfitting corresponds to low bias / high variance; underfitting to high bias / low variance.

## Exam-Relevant Points

- The decomposition is **MSE = Bias² + Variance + σ²** — note the bias is *squared*.
- The irreducible error σ² is a **lower bound** on achievable MSE, independent of model choice.
- The cross-term between (f − f̂) and ε vanishes due to **independence of noise from inputs** and **zero-mean noise** — both assumptions are required.
- f(x) is **deterministic** (not random), which is why E[f(x)] = f(x). The randomness comes from the training set D and noise ε.
- Increasing model complexity **decreases bias** but **increases variance** — and vice versa.
- The expectation is over **random draws of the training set D**, not over a single fixed dataset.
- This decomposition applies **pointwise** (at a fixed x); the overall MSE integrates over the input distribution P(x).
