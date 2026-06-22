---
source: chunks/wiki-Transfer_learning-chunk-1.md
source_url: https://en.wikipedia.org/wiki/Transfer_learning
---

## Transfer Learning in Machine Learning

Transfer learning (TL) is a machine learning technique where knowledge learned from one task (the **source**) is reused to improve performance on a different but related task (the **target**). For example, a model trained to recognize cars can transfer that knowledge to help recognize trucks. The technique addresses the practical problem of limited labeled data by leveraging pre-existing learned representations, and has been identified as a major driver of ML commercial success.

## Key Concepts

- **Formal definition**: Transfer learning involves a source domain D_S with task T_S and a target domain D_T with task T_T, where either the domains or tasks differ. The goal is to improve learning of the target predictive function f_T using knowledge from D_S and T_S.
- **Domain**: Consists of a feature space X and a marginal probability distribution P(X).
- **Task**: Consists of a label space Y and an objective predictive function f: X → Y, learned from training pairs {x_i, y_i}.
- **Positive transfer**: When source domain knowledge improves target task performance.
- **Negative transfer**: When source domain knowledge hurts target task performance (demonstrated as early as 1981).
- **Pre-training can hurt**: Zoph et al. (2020) showed pre-training can reduce accuracy in some cases, advocating self-training as an alternative.
- Related to **cost-sensitive machine learning** and **multi-objective optimization** due to its use of multiple objective functions.

## Commands and Syntax

No specific commands or CLI tools — transfer learning is a conceptual technique implemented within ML frameworks. Typical workflow:

1. **Pre-train** a model on a large source dataset (or use a pre-trained model like ImageNet-trained CNNs).
2. **Freeze or fine-tune** earlier layers that capture general features.
3. **Replace/retrain** final fully-connected layers for the target task.
4. **Evaluate** for positive vs. negative transfer.

## Relationships

- **Multi-task learning**: Closely related; both involve learning across tasks, but multi-task learning trains on all tasks simultaneously rather than sequentially transferring.
- **Domain adaptation**: A sub-problem of transfer learning focused specifically on when source and target domains differ but the task is the same.
- **Zero-shot learning**: An extreme case where no target-domain labeled data is available.
- **Feature learning**: Transfer learning often works by transferring learned feature representations.
- **Self-supervised learning / Self-training**: Competing approaches that can sometimes outperform transfer learning (per Zoph et al. 2020).
- **Neural networks / CNNs**: The most common architectures used for transfer learning, particularly in computer vision.
- **Pre-training**: The mechanism by which source knowledge is captured before transfer.

## Exam-Relevant Points

- Transfer learning requires either D_S ≠ D_T (different domains) or T_S ≠ T_T (different tasks) — if both are identical, it is not transfer learning.
- The technique dates back to **1976** (Bozinovski and Fulgosi), not the deep learning era.
- Both **positive and negative transfer** can occur — transferring from an unrelated domain can degrade performance.
- Andrew Ng (NIPS 2016) predicted transfer learning would be the next major driver of ML commercial success after supervised learning.
- Transfer learning is applicable across diverse domains: computer vision, NLP (text classification), medical imaging, game playing, spam filtering, and even cross-modal (EMG ↔ EEG signals).
- Pre-training is not always beneficial — self-training can outperform it (Zoph et al., 2020).
- End users can modify fully-connected layers of pre-trained models to improve target task performance.
- Algorithms exist for transfer learning in both **Markov logic networks** and **Bayesian networks**, not just neural networks.
