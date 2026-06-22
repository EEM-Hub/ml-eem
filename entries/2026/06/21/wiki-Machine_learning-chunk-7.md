---
source: chunks/wiki-Machine_learning-chunk-7.md
source_url: https://en.wikipedia.org/wiki/Machine_learning
---

## Machine Learning: Foundational References and Key Literature

This page is the references section of the Wikipedia article on Machine Learning. While primarily a bibliography, it reveals the foundational texts, seminal papers, and key researchers that define the field. These references span from the 1950s origins through modern deep learning, mapping the intellectual lineage of ML.

## Key Concepts

- **Arthur Samuel (1959)** coined the term "machine learning" using the game of checkers as a testbed; the famous "without being explicitly programmed" phrasing is a later paraphrase, not a direct quote
- **ML and pattern recognition** are described as "two facets of the same field" (Bishop, 2006)
- **ML and statistics** are deeply intertwined — Friedman (1998) and Breiman (2001) explored the relationship and tension between statistical modeling and ML approaches (the "two cultures")
- **Compression and learning** are formally linked — language models can exceed PNG/FLAC in lossless compression; "language modeling is compression" (Delétang et al., 2023)
- **Representation learning** is the study of learning useful data representations automatically, reviewed comprehensively by Bengio, Courville & Vincent (2013)
- **Self-supervised learning** learns representations from unlabeled data using pretext tasks (Misra & van der Maaten, 2020; Jaiswal et al., 2021)
- **Reinforcement learning** is grounded in Markov Decision Processes (van Otterlo & Wiering, 2012); Bozinovski (1982) solved delayed reinforcement learning with the Crossbar Adaptive Array
- **GANs** introduced by Goodfellow et al. (2014) at NeurIPS
- **AlphaGo** — Silver et al. (2016) demonstrated deep neural networks + tree search mastering Go

## Commands and Syntax

No commands in this section (it is a bibliography). However, the key textbooks referenced serve as canonical resources:

```
# Foundational ML Textbooks (by citation frequency and influence)
Bishop (2006)    — Pattern Recognition and Machine Learning (Springer)
Mitchell (1997)  — Machine Learning (McGraw Hill) — defines ML formally
Russell & Norvig — Artificial Intelligence: A Modern Approach (multiple editions)
Mohri et al.     — Foundations of Machine Learning (MIT Press)
Alpaydin (2010)  — Introduction to Machine Learning (MIT Press)
James et al.     — An Introduction to Statistical Learning (Springer, free online)
Bengio (2009)    — Learning Deep Architectures for AI (Now Publishers)
```

## Relationships

- **ML ↔ Statistics**: Breiman's "two cultures" paper (2001) frames the divide between data-modeling (statistics) and algorithmic-modeling (ML) approaches
- **ML ↔ Pattern Recognition**: Treated as essentially the same field (Bishop, 2006)
- **ML ↔ Data Mining**: Friedman (1998) explored what connects them
- **ML ↔ Data Compression**: Multiple references establish formal equivalence — prediction quality equals compression quality (Mahoney; Delétang et al., 2023)
- **ML ↔ Neuroscience**: Hebb's learning rule (Milner, 1993) and neural network foundations (Jordan & Bishop, 2004) bridge biological and artificial learning
- **ML ↔ Optimization**: Le Roux, Bengio & Fitzgibbon (2012) in "Optimization for Machine Learning" (MIT Press)
- **Supervised → Unsupervised → Self-supervised → Reinforcement**: The learning paradigms form a spectrum from fully labeled to fully autonomous

## Exam-Relevant Points

- **Arthur Samuel (1959)** — coined "machine learning"; the checkers paper is the canonical origin citation
- **Tom Mitchell's (1997) formal definition**: a computer program learns from experience E w.r.t. task T and performance measure P if performance improves with experience
- **Bishop's textbook (2006)** is the standard reference linking ML and pattern recognition
- **Breiman's "Two Cultures" (2001)** — landmark paper on the split between statistical and algorithmic modeling philosophies
- **The compression-learning connection** — prediction and compression are formally equivalent; this is a frequently tested theoretical insight
- **Learning paradigms**: supervised, unsupervised, self-supervised, semi-supervised (weak supervision — Ratner et al.), and reinforcement learning each have distinct canonical references
- **Feature learning hierarchy**: handcrafted features (bag of keypoints, Csurka 2004) → dictionary learning (K-SVD, Aharon 2006) → deep representation learning (Bengio 2009, 2013) traces the field's evolution
- **Key milestones by year**: Turing (1950), Samuel (1959), Nilsson (1965), Duda & Hart (1973), Bozinovski (1981-82), Mitchell (1997), Goodfellow GANs (2014), AlphaGo (2016)
