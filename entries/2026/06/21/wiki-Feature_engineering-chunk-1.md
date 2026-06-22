---
source: chunks/wiki-Feature_engineering-chunk-1.md
source_url: https://en.wikipedia.org/wiki/Feature_engineering
---

## Feature Engineering: Transforming Raw Data for ML Models

Feature engineering is a preprocessing step in supervised machine learning and statistical modeling that transforms raw data into more effective model inputs. Each input comprises several attributes (features), and well-engineered features significantly enhance predictive accuracy. The principles extend beyond ML into physics (e.g., dimensionless numbers like Reynolds number) and other scientific domains where constructing meaningful derived quantities improves analysis.

## Key Concepts

- **Feature engineering** = selecting, creating, transforming, and extracting data features from raw data to improve model performance
- **Feature creation** — constructing new features from existing data (e.g., ratios, aggregations, interactions)
- **Feature transformation** — modifying features including imputing missing/invalid values
- **Feature selection** — choosing the most relevant features based on importance scores and correlation matrices; reduces overfitting by preventing models from becoming too specific to training data
- **Feature explosion** — when identified features become too numerous for effective model estimation; caused by feature templates or non-linear feature combinations
- **Techniques to limit feature explosion**: regularization, kernel methods, feature selection
- **Dimensionality reduction** methods used in feature engineering: PCA (Principal Components Analysis), ICA (Independent Component Analysis), LDA (Linear Discriminant Analysis)
- Features vary in significance, but even relatively insignificant features may contribute to a model
- **Non-Negative Matrix Factorization (NMF)** and variants (NMTF, NTF/NTD) — matrix decomposition methods for feature engineering that yield part-based representations with natural clustering properties
- **MCMD (Multi-view Classification based on Consensus Matrix Decomposition)** — mines common clustering schemes across multiple datasets; handles missing data, identifies outliers, works with high-dimensional data
- **Feature store** — centralized repository for storing, organizing, versioning, and serving features for both model training and inference

## Commands and Syntax

No formal commands per se, but key open-source tools for automated feature engineering:

- **featuretools** (Python) — transforms time series and relational data into feature matrices
- **tsfresh** (Python) — feature extraction on time series; uses hypothesis testing for quality evaluation
- **tsflex** (Python) — fast, memory-efficient time series feature extraction (faster than tsfresh, seglearn, tsfel)
- **getML community** (C/C++ with Python interface) — automated feature engineering on time series and relational data; shown to be 60x+ faster than alternatives
- **seglearn** — scikit-learn extension for multivariate sequential time series
- **tsfel** — Python package for time series feature extraction
- **kats** — Python toolkit for time series analysis
- **OneBM (One-Button Machine)** — combines feature transformations and selection on relational data

**Automated feature engineering approaches:**
- **Multi-relational Decision Tree Learning (MRDTL)** — extends decision trees to relational databases using selection graphs as decision nodes; tuple ID propagation reduces redundant operations
- **Deep Feature Synthesis (DFS)** — uses simpler compositional methods; beat 615 of 906 human teams in a competition

## Relationships

- **Supervised learning / Statistical modeling** — feature engineering is a prerequisite preprocessing step
- **Feature selection** — closely related but distinct; focuses on choosing among existing features rather than creating new ones
- **Feature learning / Feature extraction** — related approaches; feature learning (e.g., deep learning) can automate representation discovery
- **Deep learning** — serves as an alternative to manual feature engineering by learning representations from raw data, though still requires careful preprocessing and architecture choices
- **Dimensionality reduction** (PCA, ICA, LDA) — used within feature engineering to reduce feature space
- **Clustering** — feature engineering via matrix decomposition directly supports clustering tasks
- **Regularization and kernel methods** — techniques that address feature explosion
- **Feature stores** — infrastructure for operationalizing features; can be standalone or part of ML platforms
- **Overfitting** — feature selection helps prevent it; too many features increase the risk
- **AutoML** — automated feature engineering is a component of the broader AutoML movement

## Exam-Relevant Points

- Feature engineering is a **preprocessing step** that occurs before model training, not during
- **Feature explosion** = too many features for effective estimation; solved by regularization, kernel methods, or feature selection
- **NMF** with non-negativity constraints yields **part-based representations** with natural clustering properties
- **PCA, ICA, LDA** are dimensionality reduction techniques used in feature engineering — know which is supervised (LDA) vs unsupervised (PCA, ICA)
- **Deep Feature Synthesis** outperformed most human teams (beat 615/906) in automated feature engineering
- **Feature stores** serve dual purposes: training (data scientists) and inference (production applications)
- Deep learning can **replace** manual feature engineering but still requires preprocessing, architecture selection, and hyperparameter tuning
- Feature selection prevents **overfitting** by reducing model specificity to training data
- **MRDTL** extends decision trees to work across relational database tables
- Feature engineering requires **domain expertise** and is often time-consuming and error-prone — this is a key motivation for automation
- Even features with low individual significance may contribute to model performance — don't discard features without analysis
