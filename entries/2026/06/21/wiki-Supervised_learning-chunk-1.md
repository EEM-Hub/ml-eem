---
source: chunks/wiki-Supervised_learning-chunk-1.md
source_url: https://en.wikipedia.org/wiki/Supervised_learning
---

## Supervised Learning: Paradigm, Algorithms, and Design Considerations

Supervised learning (SL) is a machine learning paradigm where an algorithm learns to map inputs to outputs using labeled training data — input-output pairs provided by a "supervisor." The trained model's goal is to generalize accurately to new, unseen data. It is the foundation for classification (predicting categories) and regression (predicting continuous values) tasks.

## Key Concepts

- **Labeled data**: Each training example includes both the input and the correct output (the supervisory signal).
- **Generalization**: The model's ability to perform well on unseen data; measured by **generalization error**.
- **Classification vs. Regression**: Classification predicts discrete categories (spam/not spam); regression predicts continuous values (house prices).
- **Bias-variance tradeoff**: Bias = systematic error from model assumptions; variance = sensitivity to training set differences. Prediction error ≈ bias + variance. Flexible models have low bias but high variance; rigid models have high bias but low variance.
- **Curse of dimensionality**: High-dimensional input spaces make learning harder; many irrelevant features increase variance. Addressed via **feature selection** and **dimensionality reduction**.
- **Overfitting**: Fitting training data too closely, including noise. Can occur from stochastic noise (measurement error) or **deterministic noise** (target function complexity exceeding model capacity).
- **No Free Lunch Theorem**: No single algorithm is best for all problems — algorithm choice is problem-dependent.
- **Noise in output values**: Errors in labels from human or sensor mistakes. Mitigated by **early stopping**, **anomaly detection**, and noisy example removal.

## Commands and Syntax

No specific CLI commands. The standard supervised learning workflow is procedural:

1. **Determine training sample type** — define the unit of data (e.g., character, word, sentence).
2. **Gather training set** — collect representative input-output pairs from experts or measurements.
3. **Engineer input features** — transform raw inputs into feature vectors; balance information content against dimensionality.
4. **Select model and algorithm** — choose structure (SVM, decision tree, neural network, etc.).
5. **Train and tune** — run the algorithm; optimize **hyperparameters** using a **validation set** or **cross-validation**.
6. **Evaluate on test set** — measure performance on held-out data separate from training.

## Relationships

- **Unsupervised learning**: Contrasting paradigm — works with unlabeled data to find patterns/structure rather than mapping inputs to known outputs.
- **Feature engineering / Feature selection / Dimensionality reduction**: Preprocessing steps that directly impact supervised learning performance.
- **Cross-validation**: Key technique for both algorithm selection and hyperparameter tuning.
- **Regularization**: Technique to handle redundant features and prevent overfitting (connects to bias-variance tradeoff).
- **Training / Validation / Test splits**: The three-way data partition is fundamental to the supervised learning workflow.
- **Specific algorithms** (SVMs, decision trees, neural networks, logistic regression, etc.) are implementations within this paradigm.

## Exam-Relevant Points

- **Bias-variance tradeoff**: High bias → underfitting, high variance → overfitting. Prediction error = bias + variance. Know that flexible models reduce bias but increase variance.
- **No Free Lunch Theorem**: No universally best algorithm — must evaluate empirically per problem.
- **Overfitting from noise**: Both stochastic noise (measurement error) and deterministic noise (model capacity < function complexity) cause overfitting. Both favor higher-bias, lower-variance estimators.
- **Curse of dimensionality**: More features ≠ better performance; irrelevant features confuse learners and increase variance.
- **Algorithm selection considerations**: (1) Data heterogeneity — decision trees handle mixed types well; SVMs/neural nets require scaled numerical features. (2) Redundant features — cause numerical instability in linear/distance methods; fix with regularization. (3) Feature interactions — linear models miss complex interactions unless manually specified; trees and neural nets discover them automatically.
- **Practical advice**: Given fixed resources, collecting more/better training data often outperforms tuning algorithms.
- **Core algorithms to know**: SVM, linear regression, logistic regression, naive Bayes, LDA, decision trees, k-NN, neural networks (MLP), similarity learning.
- **The six-step supervised learning procedure**: sample type → gather data → feature representation → algorithm choice → train/tune → evaluate on test set.
