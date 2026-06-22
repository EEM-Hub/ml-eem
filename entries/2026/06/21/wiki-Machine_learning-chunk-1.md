---
source: chunks/wiki-Machine_learning-chunk-1.md
source_url: https://en.wikipedia.org/wiki/Machine_learning
---

## Machine Learning: Overview and Foundations

This page provides a comprehensive introduction to machine learning (ML) as a field of artificial intelligence. It covers the definition, historical development, major paradigms, problem types, algorithm families, and the theoretical foundations that underpin the discipline.

## Key Concepts

- **Machine learning** is a field of AI concerned with developing statistical algorithms that can learn from data and generalize to unseen data, performing tasks without explicit programming.
- **Deep learning** (neural networks) has surpassed many earlier ML approaches in performance.
- **Foundations**: Statistics and mathematical optimization compose the foundations of ML.
- **Data mining** is a related field focusing on exploratory data analysis (EDA) through unsupervised learning.
- **PAC learning** (Probably Approximately Correct) provides the mathematical/statistical framework for describing ML.
- Most traditional ML and deep learning algorithms can be described as **empirical risk minimization** under the PAC framework.
- **Tom Mitchell's definition**: "A computer program learns from experience *E* with respect to task *T* and performance measure *P* if its performance at *T*, measured by *P*, improves with *E*." — This is an operational definition, not a cognitive one.
- The term "machine learning" was coined in **1959 by Arthur Samuel** (IBM).

## Three Major Paradigms

- **Supervised learning**: Learns from labeled data. Objectives: classification and regression.
  - Key algorithms: Decision trees, Ensembles (Bagging, Boosting, Random Forest), k-NN, Linear regression, Naive Bayes, Neural networks, Logistic regression, Perceptron, RVM, SVM
- **Unsupervised learning**: Learns from unlabeled data. Objectives: clustering, dimensionality reduction, association rules.
  - Clustering: BIRCH, CURE, Hierarchical, k-means, Fuzzy, EM, DBSCAN, OPTICS, Mean shift
  - Dimensionality reduction: Factor analysis, CCA, ICA, LDA, NMF, PCA, PGD, t-SNE, SDL
- **Reinforcement learning**: Learns through interaction with an environment, making sequential decisions. Model-based or model-free methods.
  - Key algorithms: Q-learning, Policy gradient, SARSA, Temporal difference (TD), Multi-agent, Self-play

## Additional Paradigms and Problem Types

- **Semi-supervised, self-supervised, meta-learning, online learning, batch learning, curriculum learning, rule-based learning**
- **Problem types**: Classification, generative modeling, regression, clustering, dimensionality reduction, density estimation, anomaly detection, data cleaning, AutoML, association rules, structured prediction, feature engineering/learning, learning to rank, grammar induction, ontology learning, multimodal learning

## Neural Network Architectures

- Autoencoder, Feedforward, RNN, LSTM, GRU, ESN/reservoir computing, Boltzmann machine, GAN, Diffusion model, SOM, CNN (U-Net, LeNet, AlexNet), Transformer, Vision Transformer, Mamba, Spiking neural network

## Historical Milestones

- **1949**: Donald Hebb's *The Organization of Behavior* — Hebbian learning theory
- **1950s**: Arthur Samuel's checkers program; McCulloch-Pitts neuron model
- **1959**: Term "machine learning" coined
- **1960s**: Cybertron (Raytheon) — early learning machine with reinforcement learning; Nilsson's *Learning Machines*
- **2014**: Ian Goodfellow introduces GANs
- **2016**: AlphaGo defeats top human Go players using reinforcement learning

## Commands and Syntax

No specific commands or configuration syntax — this is a conceptual overview page.

## Relationships

- **Parent field**: Artificial intelligence
- **Foundational disciplines**: Statistics, mathematical optimization, computational learning theory
- **Related field**: Data mining (unsupervised/EDA focus)
- **Key sub-field**: Deep learning (neural networks as a class of statistical algorithms)
- **Theoretical framework**: PAC learning, empirical risk minimization, VC theory, bias-variance tradeoff
- **Connects to**: Computer vision, NLP, robotics, game playing, AI safety/alignment

## Exam-Relevant Points

- **Mitchell's formal definition** of machine learning (experience E, task T, performance P) — frequently tested
- **Three major paradigm categories**: supervised (classification, regression), unsupervised (clustering, dimensionality reduction, association rules), reinforcement learning (model-based vs. model-free)
- ML is founded on **statistics and mathematical optimization**
- **PAC learning** and **empirical risk minimization** are the theoretical frameworks
- **Data mining** is related but distinct — focuses on exploratory data analysis via unsupervised learning
- **Arthur Samuel** coined the term in **1959**
- **Hebbian learning** (1949) is the biological inspiration for how connected artificial neurons adjust connection strengths
- **GANs** (2014, Goodfellow) and **AlphaGo** (2016, reinforcement learning) are landmark modern achievements
- Know the major algorithm families per paradigm (SVM, k-NN, Random Forest for supervised; k-means, DBSCAN, PCA for unsupervised; Q-learning, SARSA, TD for RL)
- Anomaly detection algorithms: RANSAC, k-NN, Local Outlier Factor, Isolation Forest
