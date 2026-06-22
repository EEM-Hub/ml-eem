---
source: chunks/wiki-Supervised_learning-chunk-2.md
source_url: https://en.wikipedia.org/wiki/Supervised_learning
---

## Supervised Learning: Algorithms, Risk Minimization, and Generalization

This page covers the mathematical foundations of how supervised learning algorithms work, from the formal problem setup (feature vectors, labels, hypothesis spaces) through the two core strategies for choosing a model — empirical risk minimization and structural risk minimization — and extends into generative vs. discriminative training, generalizations of the supervised learning paradigm, and a catalog of approaches and algorithms.

## Key Concepts

- **Supervised learning setup**: Given N training examples {(x₁,y₁), ..., (xₙ,yₙ)} where xᵢ is a feature vector and yᵢ is a label, the goal is to find a function g: X → Y from the hypothesis space G
- **Scoring function**: An alternative representation where f: X × Y → ℝ assigns scores, and g(x) = argmaxᵧ f(x,y)
- **Hypothesis space (G)**: The set of all candidate functions the algorithm considers
- **Probabilistic models**: g can take the form of a conditional probability model P(y|x) (discriminative) or a joint probability model P(x,y) (generative)
- **Loss function**: L: Y × Y → ℝ≥0 measures how far a prediction ŷ is from the true label yᵢ
- **Risk R(g)**: The expected loss of function g; estimated from training data as empirical risk: R_emp(g) = (1/N) Σᵢ L(yᵢ, g(xᵢ))
- **i.i.d. assumption**: Training pairs (xᵢ, yᵢ) are assumed to be independent and identically distributed
- **Empirical risk minimization (ERM)**: Find g that minimizes empirical risk directly; equivalent to maximum likelihood estimation when loss is negative log-likelihood
- **Overfitting**: ERM with large hypothesis spaces or small training sets leads to memorization — high variance, poor generalization
- **Structural risk minimization (SRM)**: Adds a regularization penalty C(g) to control the bias-variance tradeoff: J(g) = R_emp(g) + λC(g)
- **Regularization norms**: L₂ norm (Σ βⱼ²) — ridge; L₁ norm (Σ|βⱼ|) — lasso/sparsity; L₀ "norm" — count of non-zero weights
- **λ parameter**: Controls bias-variance tradeoff; λ=0 gives pure ERM (low bias, high variance); large λ gives high bias, low variance; chosen via cross-validation
- **Bayesian interpretation**: The regularization penalty corresponds to the negative log prior −log P(g), making J(g) the posterior probability of g
- **Discriminative training**: Learns to distinguish between output values directly (e.g., logistic regression)
- **Generative training**: Models the joint distribution P(x,y) — explains how data was generated; often simpler and sometimes has closed-form solutions (e.g., naive Bayes, LDA)

## Commands and Syntax

No CLI commands; the key formulas serve as the "syntax" of supervised learning:

- **Prediction via scoring**: `g(x) = argmaxᵧ f(x,y)`
- **Empirical risk**: `R_emp(g) = (1/N) Σᵢ L(yᵢ, g(xᵢ))`
- **Regularized objective**: `J(g) = R_emp(g) + λC(g)`
- **Linear model form**: `g(x) = Σⱼ βⱼxⱼ`
- **Negative log-likelihood loss**: `L(y, ŷ) = −log P(y|x)`

## Relationships

- **Feature vectors** are the input representation fed to supervised learning algorithms
- **Cross-validation** is used to select the regularization parameter λ
- **Maximum likelihood estimation** is a special case of ERM with negative log-likelihood loss
- **Occam's razor** is the philosophical principle behind structural risk minimization — prefer simpler models
- **Posterior probability** connects regularized learning to Bayesian inference
- **Naive Bayes and LDA** are joint probability (generative) models; **logistic regression** is a conditional (discriminative) model
- **Semi-supervised learning, active learning, structured prediction, and learning to rank** are generalizations that extend the standard supervised learning framework
- Connects to a broad taxonomy of algorithms: neural networks, SVMs, decision trees, random forests, boosting, Gaussian processes, k-NN, and many more

## Exam-Relevant Points

- **ERM with negative log-likelihood loss is equivalent to maximum likelihood estimation** — a frequently tested equivalence
- **λ=0 in SRM reduces to pure ERM** (low bias, high variance); large λ gives high bias, low variance
- **L₂ regularization** = ridge regression; **L₁ regularization** = lasso (induces sparsity); **L₀** = number of non-zero weights
- **The Bayesian interpretation of regularization**: penalty = negative log prior; regularized objective = posterior
- **Generative models** (naive Bayes, LDA) model P(x,y); **discriminative models** (logistic regression) model P(y|x) directly
- **Generative models can have closed-form solutions**; discriminative models generally require iterative optimization
- **Overfitting** occurs when the hypothesis space is too large relative to training set size — ERM memorizes rather than generalizes
- **Cross-validation** is the standard method for selecting λ empirically
- The i.i.d. assumption underlies the validity of empirical risk as an estimate of true risk
- **Semi-supervised learning** uses both labeled and unlabeled data; **active learning** interactively queries for labels
