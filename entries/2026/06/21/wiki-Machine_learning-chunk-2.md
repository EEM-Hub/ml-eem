---
source: chunks/wiki-Machine_learning-chunk-2.md
source_url: https://en.wikipedia.org/wiki/Machine_learning
---

## Machine Learning: Interdisciplinary Relationships and Learning Theory

This page covers how machine learning relates to adjacent fields — artificial intelligence, data compression, data mining, statistics, and statistical physics — as well as the theoretical foundations of ML, including generalization, computational learning theory, and the bias-variance tradeoff.

## Key Concepts

- **Deep learning ⊂ Machine learning ⊂ Artificial intelligence** — a strict containment hierarchy.
- ML emerged from AI research but became its own field in the 1990s, shifting from symbolic/knowledge-based approaches to statistical and probabilistic methods.
- **Connectionism** — the neural network research tradition continued outside mainstream AI/CS by Hopfield, Rumelhart, and Hinton; backpropagation was reinvented in the mid-1980s.
- **ML vs. Data Mining**: ML focuses on prediction from known properties; data mining focuses on discovery of previously unknown properties. They share methods but differ in goals and evaluation.
- **ML vs. Statistics**: Statistics draws population inferences from samples; ML finds generalizable predictive patterns. Statistics requires a priori model selection; ML lets data shape the model.
- **Leo Breiman's two paradigms**: the *data model* (traditional statistics) vs. the *algorithmic model* (ML algorithms like Random Forest).
- **Compression-prediction equivalence**: An optimal predictor of sequence probabilities can be used for optimal compression (via arithmetic coding), and vice versa. This equivalence is used to benchmark "general intelligence" (AIXI theory, Hutter Prize).
- **Generalization**: The ability of a trained model to perform accurately on new, unseen examples drawn from the same unknown distribution.
- **Bias-variance decomposition**: A framework for quantifying generalization error — underfitting (hypothesis too simple) vs. overfitting (hypothesis too complex).
- **Computational learning theory**: Analyzes ML algorithms via the PAC (Probably Approximately Correct) learning model; results are typically probabilistic bounds, not guarantees.
- **Polynomial time feasibility**: Positive results show a function class is learnable in polynomial time; negative results show certain classes are not.

## Commands and Syntax

No commands or configuration syntax in this section — it is conceptual/theoretical.

## Relationships

- **AI → ML → Deep Learning**: Historical lineage; ML diverged from symbolic AI in the 1980s–90s.
- **Statistics ↔ ML**: Shared methods (regression, classification), but different goals. The subfield *statistical learning* bridges both.
- **Statistical Physics → ML**: Techniques from disordered systems analysis apply to deep neural network weight spaces and medical diagnostics.
- **Data Mining ↔ ML**: ML methods used for KDD preprocessing; unsupervised learning overlaps with data mining goals.
- **Optimization ↔ ML**: Learning problems are formulated as minimization of loss functions over training data.
- **Data Compression ↔ ML**: k-means clustering for lossy compression; LLMs demonstrated as lossless compressors (DeepMind Chinchilla 70B outperformed PNG and FLAC on benchmarks, though training data overlap is a concern).
- **Information Retrieval / Pattern Recognition**: These fields absorbed statistical ML research when it fell out of favor in AI during the expert systems era (~1980s).

## Exam-Relevant Points

- Know the containment: deep learning ⊂ ML ⊂ AI.
- Expert systems dominated AI by 1980, pushing statistical approaches out of mainstream AI.
- Backpropagation was reinvented in the mid-1980s by connectionism researchers (Hinton, Rumelhart, Hopfield).
- ML shifted to statistical/probabilistic methods in the 1990s, away from symbolic AI.
- ML predicts from *known* properties; data mining discovers *unknown* properties — this is the key distinction.
- Statistics requires a priori model selection; ML does not — data shapes the model.
- Breiman's two cultures: data model vs. algorithmic model.
- Generalization error is bounded probabilistically, not deterministically, because training sets are finite.
- Model complexity must match underlying function complexity: too simple → underfitting; too complex → overfitting.
- PAC learning is the theoretical framework for computational learning theory.
- Compression and prediction are formally equivalent — optimal compressor ↔ optimal predictor.
- LLMs can act as data compressors, but benchmark validity depends on training/test data separation.
