---
source: chunks/wiki-Random_forest-chunk-4.md
source_url: https://en.wikipedia.org/wiki/Random_forest
---

## Random Forest Disadvantages and Limitations

This section covers the key trade-offs when using random forests, primarily the loss of interpretability compared to single decision trees, and specific scenarios where random forests may not improve performance over simpler models.

## Key Concepts

- Random forests sacrifice the **intrinsic interpretability** of individual decision trees in exchange for higher accuracy.
- Decision trees belong to a small family of **easily interpretable** ML models, alongside linear models, rule-based models, and attention-based models.
- Interpretability allows developers to **verify learned information** and gives end-users **trust and confidence** in model decisions.
- Following the decision path of one tree is trivial; following paths across tens or hundreds of trees is much harder.
- **Model compression** techniques can transform a random forest into a minimal "born-again" decision tree that faithfully reproduces the same decision function — recovering interpretability without sacrificing the ensemble's learned behavior.
- Random forests **may not improve accuracy** over a single decision tree when features are **linearly correlated** with the target variable.
- Random forests also struggle with problems involving **multiple categorical variables**.

## Commands and Syntax

No commands or configuration syntax described in this section.

## Relationships

- **Decision Trees**: Random forests are ensembles of decision trees; the interpretability trade-off is defined relative to single decision trees.
- **Interpretability**: Core tension — random forests gain accuracy but lose the transparency that makes decision trees valuable.
- **Rule-Based Models / Attention-Based Models**: Cited as peer members of the "easily interpretable" model family.
- **Ensemble Learning**: Random forests are an instance of ensemble methods; this limitation section applies broadly to ensemble approaches.
- **Boosting / Gradient Boosting**: Listed as related ensemble techniques that represent alternative approaches to combining weak learners.
- **Non-Parametric Statistics**: Random forests are non-parametric; they share properties and assumptions with this broader statistical family.
- **Linear Models**: When the true relationship is linear, simpler models may match or exceed random forest performance.

## Exam-Relevant Points

- The primary disadvantage of random forests vs. decision trees is **loss of interpretability**, not loss of accuracy.
- Know the four families of interpretable models: decision trees, linear models, rule-based models, attention-based models.
- "Born-again" decision trees are a compression technique that recovers interpretability from a random forest while preserving its decision function.
- Random forests do **not** help when features have a **linear correlation** with the target — a single tree or linear model may suffice.
- Random forests underperform with **multiple categorical variables**.
- Interpretability matters for two distinct stakeholders: **developers** (model validation) and **end-users** (trust and confidence).
