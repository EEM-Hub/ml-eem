---
source: chunks/wiki-Feature_engineering-chunk-2.md
source_url: https://en.wikipedia.org/wiki/Feature_engineering
---

## Feature Engineering — Key References and Literature

This page contains the references and further reading for the Wikipedia article on Feature Engineering. While it lacks expository content, the cited works collectively map the landscape of feature engineering: foundational textbooks, automated feature engineering tools, multi-relational learning, time series feature extraction, feature stores, and the relationship between feature engineering and deep learning.

## Key Concepts

- **Feature engineering** is the process of using domain knowledge to create, transform, or select input variables (features) that improve machine learning model performance.
- **Automated feature engineering** is an active area with tools like Featuretools (deep feature synthesis), getML (multi-relational), and One Button Machine (relational databases).
- **Non-negative matrix factorization (NMF)** is a dimensionality reduction technique relevant to feature construction (Lee & Seung, 1999).
- **Multi-relational feature engineering** addresses learning across multiple database tables/relations, using aggregation functions and cross-mine approaches.
- **Time series feature extraction** has dedicated libraries: tsfresh, tsflex, seglearn, TSFEL, and Facebook's Kats.
- **Feature stores** are infrastructure components for managing, sharing, and serving ML features in production.
- **Deep learning reduces but does not eliminate** the need for feature engineering — Bengio (2012) and Sarker (2021) discuss how deep architectures learn representations but still benefit from input engineering.

## Commands and Syntax

No commands appear in this references page. Key tools referenced include:

- **Featuretools** (`pip install featuretools`) — open-source Python framework for automated feature engineering via deep feature synthesis (github: alteryx/featuretools)
- **getML** — automated feature engineering for relational data (docs.getml.com)
- **tsfresh** — time series feature extraction based on scalable hypothesis tests (tsfresh.readthedocs.io)
- **tsflex** — flexible time series processing and feature extraction (github: predict-idlab/tsflex)
- **TSFEL** — time series feature extraction library (tsfel.readthedocs.io)
- **Kats** — Facebook's time series analysis toolkit (github: facebookresearch/Kats)
- **MCMD** — multi-view classification framework based on consensus matrix decomposition (github: ashishbhaskar/MCMD)

## Relationships

- **Data preprocessing / data cleaning** — feature engineering is downstream of cleaning (Chicco et al., 2022, "Eleven quick tips for data cleaning and feature engineering")
- **Model selection** — feature quality directly affects which models are viable; tree-based models handle raw features differently than linear models
- **Dimensionality reduction** — NMF, PCA, and tensor factorizations are feature engineering techniques that connect to linear algebra
- **Deep learning** — representation learning automates some feature engineering but manual engineering remains valuable for structured/tabular data
- **Database systems** — multi-relational feature engineering bridges relational databases and ML pipelines
- **MLOps / feature stores** — operational infrastructure for serving engineered features in production systems

## Exam-Relevant Points

- **Deep Feature Synthesis (DFS)** is the algorithm behind Featuretools — automatically generates features from relational datasets by stacking transformation and aggregation primitives (Kanter & Veeramachaneni, 2015).
- **Feature stores** provide a centralized repository for feature definitions, enabling reuse across models and consistency between training and serving.
- **Multi-relational learning** methods (CrossMine, multi-relational decision trees) handle features spread across multiple joined tables without flattening into a single table first.
- **Canonical textbooks**: Hastie/Tibshirani/Friedman (*Elements of Statistical Learning*), Shalev-Shwartz/Ben-David (*Understanding ML*), Murphy (*Probabilistic ML*) — know these as foundational references.
- **Feature engineering remains a bottleneck** even with automation — domain knowledge is critical for creating meaningful features (5 challenges noted by Explorium, 2021).
- **Time series feature extraction** is a specialized subfield with multiple competing libraries, each using different statistical hypothesis testing approaches.
