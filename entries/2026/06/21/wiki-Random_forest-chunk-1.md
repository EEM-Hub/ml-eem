---
source: chunks/wiki-Random_forest-chunk-1.md
source_url: https://en.wikipedia.org/wiki/Random_forest
---

## Random Forests: Ensemble Decision Tree Methods

Random forests (also called random decision forests) are an ensemble learning method that constructs a multitude of decision trees during training and aggregates their outputs — using majority vote for classification or averaging for regression. The method corrects for individual decision trees' tendency to overfit by combining many decorrelated trees trained on different bootstrap samples of the data.

## Key Concepts

- **Ensemble method**: Combines multiple decision trees to reduce variance without substantially increasing bias
- **Bagging (Bootstrap Aggregating)**: Each tree is trained on a random sample drawn *with replacement* from the training set; this decorrelates trees that would otherwise select the same dominant features
- **Feature bagging (Random Subspace Method)**: At each split, only a random subset of features is considered — prevents strong predictors from dominating every tree and further decorrelates the ensemble
- **Default feature subset sizes**: Classification uses sqrt(p) features per split; regression uses p/3 features per split (where p = total features)
- **Overfitting resistance**: Unlike single deep trees (low bias, high variance), averaging many decorrelated trees reduces variance while only slightly increasing bias
- **Out-of-bag (OOB) error**: Each training sample is left out of ~37% of bootstrap samples; predictions on those held-out samples estimate generalization error without a separate validation set
- **Prediction uncertainty**: Standard deviation across individual tree predictions provides an uncertainty estimate
- **Number of trees (B)**: Typically hundreds to thousands; error levels off after sufficient trees are fit; can be tuned via cross-validation or OOB error
- **ExtraTrees (Extremely Randomized Trees)**: Variant that (1) trains each tree on the full dataset (no bootstrap) and (2) selects random cut-points rather than locally optimal ones, then picks the best among them
- **High-dimensional adaptations**: Prefiltering noisy features, Enriched Random Forest (weighted feature sampling), Tree-Weighted Random Forest (weighted tree voting)

## Commands and Syntax

```python
# scikit-learn: Random Forest Classifier
from sklearn.ensemble import RandomForestClassifier
clf = RandomForestClassifier(
    n_estimators=100,      # number of trees (B)
    max_features='sqrt',   # features per split: 'sqrt' for classification
    oob_score=True,        # enable out-of-bag error estimate
    random_state=42
)
clf.fit(X_train, y_train)
predictions = clf.predict(X_test)
print(clf.oob_score_)     # OOB accuracy estimate

# scikit-learn: Random Forest Regressor
from sklearn.ensemble import RandomForestRegressor
reg = RandomForestRegressor(
    n_estimators=100,
    max_features=1/3,      # p/3 for regression (or 'sqrt', integer, float)
    min_samples_leaf=5,    # recommended default minimum node size
    oob_score=True
)

# scikit-learn: ExtraTrees
from sklearn.ensemble import ExtraTreesClassifier
et = ExtraTreesClassifier(
    n_estimators=100,
    max_features='sqrt'    # default for classification; use n_features for regression
)
```

**Bagging algorithm pseudocode:**
1. For b = 1 to B:
   - Sample n examples with replacement from (X, Y) → (X_b, Y_b)
   - Train decision tree f_b on (X_b, Y_b)
2. Predict: average f_b(x') for regression, or majority vote for classification

## Relationships

- **Decision Trees**: Random forests are built from decision trees; they address the overfitting problem inherent in deep individual trees
- **Bootstrap Aggregating (Bagging)**: Random forests extend bagging by adding feature randomization at each split
- **Random Subspace Method**: The feature bagging component, originally proposed by Ho (1998)
- **Bias-Variance Tradeoff**: Random forests trade a small increase in bias for a large decrease in variance relative to single trees
- **CART**: Breiman's random forest formulation uses CART-like tree construction combined with randomized node optimization
- **Boosting**: Alternative ensemble strategy (e.g., AdaBoost, Gradient Boosting) that builds trees sequentially rather than independently; boosting reduces bias while random forests reduce variance
- **ExtraTrees**: A further-randomized variant — no bootstrap sampling, random cut-points instead of optimal splits
- **Variable Importance / Permutation Importance**: Key diagnostic tool introduced alongside random forests for feature selection and model interpretation

## Exam-Relevant Points

- Random forests output **majority vote** (classification) or **mean prediction** (regression) across all trees
- Feature subset size defaults: **sqrt(p) for classification, p/3 for regression**
- Bagging samples **with replacement** — each bootstrap sample is the same size as the original dataset
- OOB error is a valid generalization error estimate that **does not require a separate test set**
- Random forests reduce **variance** (not bias) compared to individual decision trees
- Trees must be **decorrelated** for the ensemble to be effective — feature bagging achieves this
- ExtraTrees differences from standard RF: **(1) no bootstrap — uses full training set, (2) random cut-points instead of optimal splits**
- ExtraTrees default features per split: **sqrt(p) for classification, p (all features) for regression**
- Training and test error **plateau** after enough trees; more trees do not cause overfitting
- The generalization error bound depends on **tree strength** (individual accuracy) and **tree correlation** (lower is better)
- Key contributors: Salzberg & Heath (1993, first proposal), **Tin Kam Ho** (1995, random subspace), **Leo Breiman** (2001, modern formulation with bagging + feature randomization + OOB error + permutation importance)
- "Random Forests" is a **registered trademark** (originally Breiman/Cutler, now owned by Minitab, Inc.)
