---
source: chunks/wiki-Random_forest-chunk-2.md
source_url: https://en.wikipedia.org/wiki/Random_forest
---

## Random Forest Properties: Variable Importance, Neighbor Interpretation, and Variants

This page covers three key aspects of random forests beyond basic construction: methods for measuring feature importance (permutation and impurity-based), the theoretical relationship between random forests and k-nearest neighbors, unsupervised learning applications, and variant architectures that replace decision trees with linear base estimators.

## Key Concepts

- **Permutation importance**: Measures a feature's importance by permuting its values in out-of-bag (OOB) samples and computing the increase in OOB error; the score is normalized by the standard deviation of the differences across all trees.
- **Mean decrease in impurity (MDI)**: Measures importance by summing how much each feature decreases impurity (e.g., Gini, entropy, MSE) at split nodes, weighted by the fraction of samples reaching each node, averaged across all trees.
- **MDI is the default** in both scikit-learn and R's `randomForest` package, but has known biases — it favors high-cardinality features and uses training statistics rather than test-set performance.
- **Permutation importance drawbacks**: Biased toward features with more distinct values; penalizes large groups of correlated features; can fail entirely with collinear features unless groups are permuted together.
- **Weighted neighborhood interpretation**: Both random forests and k-NN can be formalized as weighted neighborhood schemes where predictions are weighted sums over training points. A forest's weight function averages the individual tree weight functions.
- **Adaptive neighborhoods**: Unlike k-NN's fixed-shape neighborhoods, random forest neighborhoods adapt to the local importance of each feature (Lin and Jeon, 2002).
- **Unsupervised random forests**: A dissimilarity measure can be constructed by training a forest to distinguish observed data from synthetic reference data. This handles mixed types, is invariant to monotonic transformations, and is robust to outliers.
- **Linear base estimators**: Decision trees can be replaced by multinomial logistic regression or naive Bayes classifiers; when the true relationship is linear, these base learners can match ensemble accuracy.

## Commands and Syntax

- **R permutation importance**: Available via the `randomForest` R package; importance is computed using OOB samples by default.
- **scikit-learn MDI importance**: Default `feature_importances_` attribute on `RandomForestClassifier`/`RandomForestRegressor`. Be aware this reports training-based impurity decrease, not test-set relevance.
- **Impurity measures used at split nodes**:
  - Classification: Gini coefficient, entropy
  - Regression: Mean squared error
- **Normalized importance**: Divide each feature's raw importance by the sum across all features so that importances sum to 1.

## Relationships

- **Out-of-bag error**: Permutation importance relies on OOB error estimation; if bagging is not used, an independent test set is needed instead.
- **k-Nearest Neighbors**: Random forests generalize k-NN by learning adaptive, data-dependent neighborhoods rather than using fixed Euclidean distance.
- **Decision trees**: Both importance methods operate at the individual tree level (split nodes for MDI, OOB predictions for permutation) and aggregate across the forest.
- **Ensemble methods**: The variant discussion connects random forests to broader ensemble theory — any base learner (not just trees) can be bagged with random feature subsets.
- **Unsupervised learning / clustering**: Random forest dissimilarity extends the supervised framework to unlabeled data, connecting to clustering and dimensionality reduction.

## Exam-Relevant Points

- **Permutation importance** permutes one feature at a time in OOB samples and measures the increase in error; it is model-agnostic in principle but was introduced specifically for random forests by Breiman.
- **MDI importance** sums impurity decreases at all nodes where a feature is used for splitting, weighted by the proportion of samples at each node — it is biased toward high-cardinality features and reflects training fit, not generalization.
- **Correlated features** are a known failure mode for both methods: permutation importance undervalues features in large correlated groups; the fix is to permute correlated groups together.
- **Random forests define an implicit similarity measure**: two points are "neighbors" if they land in the same leaf across many trees — this neighborhood shape adapts to local feature relevance, unlike k-NN's fixed metric.
- **The forest prediction formula** is a weighted average: y_hat = sum over all training points of (averaged weight across trees) times y_i — making the forest interpretable as a single adaptive kernel smoother.
- **Unsupervised random forest dissimilarity** works by discriminating real data from synthetic data drawn from a reference distribution, producing a distance matrix usable for clustering.
- **Non-tree base learners** (logistic regression, naive Bayes) can replace decision trees in the random forest framework; they perform comparably when the underlying relationship is linear.
