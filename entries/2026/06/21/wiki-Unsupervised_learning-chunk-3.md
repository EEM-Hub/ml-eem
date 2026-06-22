---
source: chunks/wiki-Unsupervised_learning-chunk-3.md
source_url: https://en.wikipedia.org/wiki/Unsupervised_learning
---

## Unsupervised Learning: Probabilistic Methods and Approaches

This page covers the probabilistic foundations of unsupervised learning, including its core algorithms (clustering, anomaly detection, latent variable models), the method of moments for parameter estimation, and the contrast between unsupervised and supervised learning in terms of probability distributions.

## Key Concepts

- **Unsupervised learning** infers an *a priori* probability distribution p(x), unlike supervised learning which infers a *conditional* distribution p(x|y) conditioned on labels.
- **Cluster analysis** groups unlabeled data by identifying commonalities, without responding to feedback — it reacts based on presence or absence of shared attributes.
- **Density estimation** is a central statistical application of unsupervised learning.
- **Principal component analysis (PCA)** and **cluster analysis** are the two main methods used in unsupervised learning.
- **Latent variable models** include both observed variables and unobserved (latent) variables — e.g., topic modeling where words are observed and topic is latent.
- **Method of moments** relates unknown model parameters to moments of random variables (mean vector = first order, covariance matrix = second order); higher-order moments use tensors.
- **Method of moments vs. EM**: Method of moments guarantees global convergence under certain conditions; EM can get stuck in local optima.
- **Tensor decomposition techniques** consistently recover parameters of a large class of latent variable models under some assumptions.

## Commands and Syntax

No specific commands — this is a theoretical/conceptual page. However, the algorithmic taxonomy is important:

- **Clustering methods**: hierarchical clustering, k-means, mixture models, model-based clustering, DBSCAN, OPTICS
- **Anomaly detection methods**: local outlier factor, isolation forest
- **Latent variable model approaches**: EM algorithm, method of moments, blind signal separation (PCA, ICA, NMF, SVD)

## Relationships

- **Supervised learning** — contrasted by the type of distribution inferred (conditional vs. a priori)
- **PCA / SVD / ICA / NMF** — blind signal separation techniques that fall under latent variable model learning
- **EM algorithm** — practical but locally optimal alternative to method of moments
- **Topic modeling** — key practical application of latent variable models
- **Density estimation** — core statistical application connecting unsupervised learning to statistics
- **Cluster analysis** — overlaps with anomaly detection (detecting points that don't fit any group)
- **Tensors** — generalization of matrices used to represent higher-order moments in method of moments

## Exam-Relevant Points

- Unsupervised learning estimates p(x); supervised learning estimates p(x|y) — know this distinction precisely.
- Three main algorithmic categories: clustering, anomaly detection, latent variable models — be able to list methods under each.
- Method of moments provides **global convergence guarantees** under certain conditions; EM does **not** (can get stuck in local optima). This is a classic comparison question.
- First-order moment = mean vector; second-order moment = covariance matrix (when mean is zero); higher-order = tensors.
- Know the specific clustering algorithms: hierarchical, k-means, mixture models, model-based, DBSCAN, OPTICS.
- Know anomaly detection methods: local outlier factor, isolation forest.
- Topic modeling is the canonical example of a latent variable model (words = observed, topic = latent).
- Tensor decomposition is the mathematical backbone of method of moments for latent variable models.
