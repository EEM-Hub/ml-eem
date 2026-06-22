---
source: chunks/wiki-Overfitting-chunk-2.md
source_url: https://en.wikipedia.org/wiki/Overfitting
---

## Underfitting, Benign Overfitting, and Model Complexity

This page covers underfitting as the inverse of overfitting in machine learning, where a model is too simplistic to capture data patterns. It also introduces the concept of benign overfitting, where overparameterized models generalize well despite perfectly fitting noisy training data.

## Key Concepts

- **Underfitting** occurs when a model is too simple to capture the underlying structure in the data, resulting in **high bias and low variance**
- This is the inverse of overfitting, which exhibits **low bias and high variance**
- An underfitted model will inaccurately represent data points and produce poor predictions on unseen data (high generalization error)
- The **bias-variance tradeoff** is the analytical framework for diagnosing underfitting vs. overfitting by decomposing error into bias error, variance error, and irreducible error
- Underfitted models miss **important replicable structure** in data — they fail to identify effects actually supported by the data
- In underfitted models, parameter estimator bias is often substantial, sampling variance is underestimated, and confidence interval coverage is poor
- **Benign overfitting**: a model achieves perfect training accuracy (even on noisy data) yet still generalizes well to unseen data — particularly observed in deep neural networks
- Benign overfitting requires **overparameterization**: the number of unimportant directions in parameter space must significantly exceed the sample size

## Commands and Syntax

No specific commands. Remediation strategies for underfitting:

1. **Increase model complexity** — add features, increase parameters, use a more flexible model (but avoid swinging into overfitting)
2. **Switch algorithms** — e.g., replace linear regression with a neural network for nonlinear data
3. **Increase training data** — more data helps the model capture underlying patterns
4. **Regularization** — controls model complexity; can prevent both overfitting (penalizing large weights) and underfitting (tuning the regularization strength)
5. **Ensemble methods** — combine multiple models to better capture patterns
6. **Feature engineering** — create new, more relevant features from existing ones

## Relationships

- **Bias-variance tradeoff** — the core diagnostic framework; underfitting sits on the high-bias end
- **Overfitting** — the opposite problem (low bias, high variance); remediation for one can cause the other
- **Generalization error** — underfitting leads to high generalization error because the model fails to learn the true data distribution
- **Regularization** — connects both underfitting and overfitting; too much regularization causes underfitting, too little causes overfitting
- **Ensemble methods** — a remedy for underfitting that aggregates multiple weak models
- **Feature engineering / Feature selection** — directly affects model expressiveness and thus the underfitting-overfitting balance
- **Double descent** — related to benign overfitting; test error can decrease again after the interpolation threshold in overparameterized models
- **VC dimension** — theoretical measure of model capacity; models with insufficient VC dimension for the task will underfit
- **Overparameterization** — essential condition for benign overfitting; connects to modern deep learning theory

## Exam-Relevant Points

- Underfitting = **high bias, low variance**; overfitting = **low bias, high variance** — know which is which
- The six remediation strategies for underfitting: increase complexity, change algorithm, more data, regularization, ensemble methods, feature engineering
- Regularization is a **dual-purpose tool**: prevents overfitting (primary use) but tuning it too aggressively causes underfitting
- Benign overfitting requires **overparameterization** — specifically, unimportant parameter-space directions must greatly exceed sample size
- Underfitted models produce **biased parameter estimates** and **underestimated sampling variance**, leading to poor confidence intervals
- Increasing training data helps underfitting (model sees more patterns) — contrast with overfitting where more data is also helpful but for a different reason (reduces variance)
- The bias-variance tradeoff decomposes total error into three components: **bias error**, **variance error**, and **irreducible error**
