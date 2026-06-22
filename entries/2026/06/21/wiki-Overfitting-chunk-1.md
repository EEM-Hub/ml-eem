---
source: chunks/wiki-Overfitting-chunk-1.md
source_url: https://en.wikipedia.org/wiki/Overfitting
---

## Overfitting in Machine Learning and Statistical Modeling

Overfitting occurs when a model learns the noise in training data rather than the underlying pattern, resulting in excellent training performance but poor generalization to unseen data. This page covers the definition, causes, consequences, and remedies of overfitting (and its counterpart, underfitting) across both statistical inference and machine learning contexts.

## Key Concepts

- **Overfitting**: A model corresponds too closely to training data and fails to generalize; it extracts residual variation (noise) as if it were genuine structure
- **Underfitting**: A model is too simple to capture the underlying data structure (e.g., fitting a linear model to nonlinear data)
- **Core tradeoff**: Balancing model complexity against generalization ability — the bias-variance tradeoff
- **Parameter count rule**: If parameters >= observations, the model can perfectly memorize training data but will fail on new data
- **Shrinkage**: Even well-fitted models tend to perform worse on new datasets than on training data; the coefficient of determination shrinks on unseen data
- **Occam's razor / Principle of Parsimony**: Simpler models are a priori more probable; added complexity must be justified by sufficient improvement in fit
- **Model complexity is not just parameter count**: The expressivity of each parameter matters (e.g., a neural net parameter vs. a linear regression parameter are not equivalent)
- **Freedman's paradox**: With many explanatory variables unrelated to the target, some will be falsely found statistically significant, leading to overfitting
- **One in ten rule**: Guideline of ~10 observations per independent variable for logistic/Cox regression to avoid overfitting
- **Overfitting is more likely when**: training runs too long, training examples are rare, or there is little theoretical guidance for model selection

## Commands and Syntax

No specific CLI commands. Key diagnostic procedures:

- **Train/validation split**: Monitor training error vs. validation error across training cycles; overfitting occurs when validation error increases while training error decreases
- **Cross-validation**: Test model on held-out folds to estimate generalization performance
- **Learning curves**: Plot training and validation error as a function of training iterations to identify the optimal stopping point (where validation error reaches its global minimum)

## Relationships

- **Bias-variance tradeoff**: Overfitting increases variance (high sensitivity to training data), underfitting increases bias (systematic error). Optimal model balances both
- **Regularization** (L1/L2, dropout, pruning): Directly penalizes model complexity to reduce overfitting
- **Early stopping**: Halts training when validation error begins increasing — prevents the model from memorizing noise
- **Model selection** (AIC, BIC, cross-validation): Formal criteria for choosing among candidate models while accounting for complexity
- **Bayesian priors**: Encode prior beliefs about parameter values, effectively regularizing the model
- **Generative models and copyright**: Overfitted generative models can reproduce training instances verbatim, raising privacy (PII) and copyright concerns (Stable Diffusion, GitHub Copilot litigation)

## Exam-Relevant Points

- **Definition precision**: Overfitting = extracting noise as if it were signal; underfitting = model too simple to capture structure
- **Diagnostic signature**: Training error decreasing while validation error increasing indicates overfitting
- **Remedies list**: Cross-validation, regularization, early stopping, pruning, Bayesian priors, dropout, model comparison
- **One in ten rule**: ~10 observations per predictor variable in logistic/Cox regression
- **Freedman's paradox**: Spurious significance with many irrelevant predictors
- **Parameters >= observations**: Model can perfectly memorize data but will generalize poorly
- **Complexity comparison**: Cannot compare model complexity solely by parameter count; must consider parameter expressivity
- **Consequences of overfitting**: Poor generalization, increased data collection cost, reduced portability/reproducibility, potential leakage of training data (privacy/copyright risk)
- **Dropout**: Randomly removes inputs during training to improve robustness
- **Pruning**: Identifies sparse optimal network structure, reducing overfitting and computational cost simultaneously
