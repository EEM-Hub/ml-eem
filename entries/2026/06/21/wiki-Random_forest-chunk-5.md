---
source: chunks/wiki-Random_forest-chunk-5.md
source_url: https://en.wikipedia.org/wiki/Random_forest
---

## Random Forests: Ensemble Learning with Decision Trees

This page covers the references and scholarly foundation for Random Forests, an ensemble learning method that constructs multiple decision trees during training and outputs the mode (classification) or mean (regression) of individual trees. The references span the algorithm's origins, theoretical properties, variants, feature importance methods, and applications.

## Key Concepts

- **Origins**: Tin Kam Ho introduced "Random Decision Forests" (1995) and the "Random Subspace Method" (1998), establishing the idea of constructing ensembles of decision trees using random feature subsets
- **Breiman's formalization**: Leo Breiman's 2001 paper "Random Forests" in *Machine Learning* is the canonical reference — it formalized bagging + random feature selection and is among the most-cited papers of the 21st century (Nature, 2025)
- **Precursors**: Kleinberg's "Stochastic Discrimination" (1990, 1996, 2000) and Amit & Geman's randomized trees (1997) laid theoretical groundwork before Breiman's synthesis
- **Trademark**: "Random Forests" is a registered U.S. trademark (registration #3185828, 2006) held by Health Care Productivity, Inc.
- **Extremely Randomized Trees (Extra-Trees)**: Geurts et al. (2006) introduced a variant that randomizes both feature selection and split thresholds, further reducing variance
- **Feature importance bias**: Default impurity-based importance measures are biased toward multi-valued/high-cardinality attributes (Deng et al., 2011; Strobl et al., 2007). Permutation importance (Altmann et al., 2010) provides a corrected alternative
- **Correlated features**: Feature ranking is unreliable when features are correlated (Tolosi & Lengauer, 2011)
- **Consistency**: Breiman & Ghahramani (2004) and Arlot & Genuer (2014) studied consistency properties of simplified random forest models
- **Kernel interpretation**: Random forests implicitly define a kernel (weighted nearest-neighbor method) — shown by Lin & Jeon (2006) and Scornet (2015)
- **Unsupervised learning**: Shi & Horvath (2006) extended random forests to unsupervised settings using synthetic data generation and proximity matrices
- **Interpretability**: Sagi & Rokach (2020) proposed transforming decision forests into single interpretable trees; Vidal & Schiffer (2020) introduced "Born-Again Tree Ensembles"

## Commands and Syntax

- **R package**: `randomForest` — documented by Liaw (2012), the standard R implementation of Breiman's algorithm
- **scikit-learn**: Permutation importance available via `sklearn.inspection.permutation_importance` (referenced in scikit-learn docs)

## Relationships

- **Bagging**: Random forests extend bagging (bootstrap aggregating) by adding random feature selection at each split
- **Boosting**: Dietterich (2000) compared bagging, boosting, and randomization for decision tree ensembles — these are complementary ensemble strategies
- **CART**: Breiman's Classification and Regression Trees (CART) is the base learner typically used within random forests
- **Kernel methods**: Random forests can be viewed through the lens of kernel methods and adaptive nearest neighbors
- **Variants**: Feature-weighted random forests, Enriched Random Forests, Random Multinomial Logit, and Reinforcement Learning Trees extend the basic framework for specific domains (genomics, high-dimensional data, sequential decision-making)

## Exam-Relevant Points

- **Breiman (2001)** is the foundational citation for random forests — know the paper, journal (*Machine Learning*), and key contributions (OOB error, variable importance)
- **Two sources of randomness**: (1) bootstrap sampling of training data (bagging), (2) random subset of features considered at each split
- **Impurity-based feature importance is biased** toward features with more categories or higher cardinality — permutation importance is the recommended alternative
- **OOB (Out-of-Bag) error** provides an internal estimate of generalization error without needing a separate validation set
- **Extra-Trees** differ from standard random forests by also randomizing the split threshold (not just the feature subset)
- **Random forests are equivalent to adaptive nearest-neighbor methods** (Lin & Jeon, 2006) — they implicitly define a data-adaptive kernel
- **Unsupervised random forests** use synthetic class labels to learn proximity/similarity without labeled data
- **Key textbook references**: Hastie, Tibshirani & Friedman — *Elements of Statistical Learning* (2008); James, Witten, Hastie & Tibshirani — *Introduction to Statistical Learning* (2013)
- **Consistency** of random forests has been proven only for simplified models, not the full Breiman algorithm in general settings
