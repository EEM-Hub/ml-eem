---
source: chunks/wiki-Machine_learning-chunk-3.md
source_url: https://en.wikipedia.org/wiki/Machine_learning
---

## Machine Learning Approaches and Learning Paradigms

This page covers the major categories of machine learning approaches, organized by the type of feedback or signal available to the learning system. It spans the three classical paradigms — supervised, unsupervised, and reinforcement learning — plus hybrid and specialized methods such as semi-supervised learning, self-learning, feature learning, anomaly detection, and association rule learning.

## Key Concepts

- **Three classical paradigms**: Supervised (labelled data with teacher signal), Unsupervised (no labels, discovers structure), Reinforcement (agent maximizes cumulative reward through environment interaction)
- **No Free Lunch**: No single algorithm works for all problems — each has advantages and limitations
- **Supervised learning** uses training data consisting of input-output pairs (feature vectors in a matrix), optimizing an objective/loss function iteratively to learn a general input-to-output mapping
- **Classification** restricts outputs to a limited set of values; **Regression** allows any numerical output within a range
- **Similarity learning** is related to classification/regression but learns a similarity function between objects (used in ranking, recommender systems, face verification)
- **Unsupervised learning** central applications: clustering, dimensionality reduction, density estimation
- **Clustering** groups observations by similarity metrics, evaluated by internal compactness and separation
- **Self-supervised learning** is a special case of unsupervised learning that generates supervisory signals from the data itself
- **Dimensionality reduction** reduces the feature set; PCA is the most popular method. The **manifold hypothesis** proposes high-dimensional data lies along low-dimensional manifolds
- **Semi-supervised learning** uses a mix of labelled and unlabelled data; small amounts of labelled data combined with large unlabelled sets can greatly improve accuracy
- **Weakly supervised learning** uses noisy, limited, or imprecise labels that are cheaper to obtain
- **Reinforcement learning** environments are typically modelled as **Markov Decision Processes (MDPs)**; algorithms often use dynamic programming and do not require exact mathematical models
- **Feature learning** (representation learning) discovers useful data representations automatically, replacing manual feature engineering; can be supervised (neural nets, MLPs) or unsupervised (autoencoders, ICA, matrix factorization)
- **Deep learning** discovers hierarchical features — higher-level abstract features built from lower-level ones
- **Sparse dictionary learning** represents examples as sparse linear combinations of basis functions; is strongly NP-hard; k-SVD is a popular heuristic
- **Anomaly detection** identifies rare items/events differing significantly from majority data; three categories: unsupervised, supervised, semi-supervised
- **Association rule learning** discovers relationships between variables in large databases (e.g., market basket analysis: {onions, potatoes} => {burger})
- **Learning classifier systems (LCS)** combine genetic algorithms with supervised/reinforcement/unsupervised learning to build context-dependent rule sets
- **Inductive logic programming (ILP)** uses logic programming to derive hypothesized programs that entail all positive and no negative examples
- **Self-learning** (1982, crossbar adaptive array) uses internal emotion as reward signal, with no external reinforcement input

## Commands and Syntax

No CLI commands or configuration syntax on this page. Key mathematical/algorithmic procedures:

- **Self-learning update rule**: `w'(a,s) = w(a,s) + v(s')` — updates memory matrix by adding the emotional valuation of the consequence situation
- **Association rule format**: `{onions, potatoes} => {burger}` — antecedent implies consequent, discovered via interestingness measures
- **PCA**: Projects higher-dimensional data (e.g., 3D) to lower-dimensional space (e.g., 2D) by extracting principal variables
- **Sparse dictionary learning**: Represent input x as sparse linear combination of dictionary basis functions; solve via k-SVD heuristic

## Relationships

- **Supervised learning** connects to: active learning, classification, regression, similarity learning, neural networks, SVMs, loss functions, feature vectors
- **Unsupervised learning** connects to: clustering, dimensionality reduction (PCA, manifold learning), density estimation, self-supervised learning, autoencoders
- **Reinforcement learning** connects to: Markov decision processes, dynamic programming, game theory, control theory, multi-agent systems, autonomous vehicles
- **Semi-supervised learning** bridges supervised and unsupervised; weakly supervised is a pragmatic variant
- **Feature learning** spans both supervised (neural nets, MLPs) and unsupervised (autoencoders, ICA); deep learning is a multi-level variant
- **Anomaly detection** uses techniques from all three paradigms (supervised, unsupervised, semi-supervised)
- **Association rules** connect to data mining, market basket analysis, sequence mining, inductive logic programming
- **ILP** connects to logic programming, bioinformatics, NLP, and inductive programming (functional programs)

## Exam-Relevant Points

- The three classical ML paradigms are defined by their feedback signal: labelled data (supervised), no labels (unsupervised), reward signal (reinforcement)
- **Classification vs. Regression**: classification has discrete outputs, regression has continuous numerical outputs
- **Self-supervised learning** is a subset of unsupervised learning, not a separate paradigm
- **Semi-supervised learning** improves accuracy by combining small labelled sets with large unlabelled data
- **Manifold hypothesis**: high-dimensional data lies on low-dimensional manifolds — foundational assumption for many dimensionality reduction techniques
- **RL environments** are modelled as **MDPs**; RL algorithms do NOT require exact mathematical models of the MDP
- **Sparse dictionary learning** is **strongly NP-hard**; k-SVD is the standard heuristic
- **Anomaly detection** has three technique categories matching the three paradigms; supervised anomaly detection faces inherently **unbalanced** class distributions
- **Association rule learning** does NOT consider item order (contrast with sequence mining)
- **No Free Lunch theorem** applies: no single algorithm is universally best
- Feature learning replaces **manual feature engineering** — a key motivation for deep learning
- **Deep learning** = hierarchical feature learning with multiple levels of abstraction
- **Inductive** in ILP refers to **philosophical induction** (theory from observations), not mathematical induction (proof over well-ordered sets)
