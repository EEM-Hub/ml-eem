---
source: chunks/wiki-Machine_learning-chunk-5.md
source_url: https://en.wikipedia.org/wiki/Machine_learning
---

## Machine Learning: Applications, Limitations, and Model Assessment

This page provides a broad survey of ML application domains, discusses key limitations and failure modes of ML systems, and covers standard model evaluation techniques. It serves as a high-level map connecting ML to real-world use cases while cataloging the known risks and assessment methods.

## Key Concepts

- **Breadth of ML applications**: ML spans dozens of domains including healthcare, finance (fraud detection, investment), NLP, computer vision, robotics, agriculture, climate science, cheminformatics, and recommender systems.
- **Netflix Prize (2006–2009)**: Landmark competition where an ensemble model achieved 10%+ improvement over Netflix's Cinematch algorithm; afterward Netflix shifted from ratings to behavioral signals for recommendations.
- **Black box problem**: ML models can be opaque even to their designers — the internal decision logic is not interpretable. The UK House of Lords stated that systems with substantial impact on individuals must provide satisfactory explanations.
- **Explainable AI (XAI)**: Also called Interpretable AI or Explainable Machine Learning (XML). Aims to make AI decisions understandable to humans; may implement a "right to explanation."
- **Overfitting**: Fitting an overly complex model to training data noise rather than the true signal. Mitigated by penalizing model complexity (regularization).
- **Model collapse**: Degradation when models train on uncurated synthetic data or outputs of prior model versions. Also called "AI inbreeding," "Habsburg AI," or "model autophagy disorder (MAD)."
- **Hallucinations**: AI-generated content containing false information presented as fact. Especially relevant to LLMs. Symbolic AI models generally do not hallucinate.
- **Spurious correlations**: Models can learn unintended patterns (e.g., associating color with class rather than shape), leading to brittle real-world performance.
- **Adversarial vulnerability**: Inputs can be deliberately crafted to cause misclassification — sometimes by changing a single pixel. Related field: adversarial machine learning.
- **Backdoor attacks**: Third-party trained models can contain hidden backdoors that alter classification on chosen inputs, even when white-box access is available.
- **Common failure causes**: Lack of suitable data, data bias, privacy issues, poorly chosen tasks/algorithms, wrong tools/people, insufficient resources, evaluation problems.

## Commands and Syntax

No specific commands on this page, but key model assessment procedures are described:

- **Holdout method**: Split data into training (typically 2/3) and test (1/3) sets; evaluate on the test set.
- **K-fold cross-validation**: Partition data into K subsets; run K experiments, each using 1 fold for evaluation and K-1 for training.
- **Bootstrap**: Sample n instances *with replacement* from the dataset to assess model accuracy.

**Key evaluation metrics:**
- **Accuracy** — overall correctness
- **Sensitivity (True Positive Rate / TPR)** — proportion of actual positives correctly identified
- **Specificity (True Negative Rate / TNR)** — proportion of actual negatives correctly identified
- **False Positive Rate (FPR)** and **False Negative Rate (FNR)**
- **ROC curve** and **AUC (Area Under the ROC Curve)** — higher AUC = better model; provides threshold-independent assessment

## Relationships

- **Ensemble methods** — The Netflix Prize was won using ensemble averaging, connecting to topics on bagging, boosting, and model stacking.
- **Regularization / bias-variance tradeoff** — Directly related to overfitting; penalizing complexity trades off fit against generalization.
- **Adversarial machine learning** — A subfield addressing robustness, connecting to security, computer vision, and model deployment.
- **Synthetic data and generative models** — Model collapse connects to training data sourcing, data augmentation, and generative AI.
- **NLP and large language models** — Hallucinations are particularly prominent in LLM-based systems.
- **Ethics and AI governance** — Black box concerns, explainability, and automated decision-making tie to fairness, accountability, and regulation.
- **Cross-validation and hyperparameter tuning** — Model assessment methods connect to model selection and optimization workflows.

## Exam-Relevant Points

- **Holdout split convention**: 2/3 training, 1/3 test.
- **K-fold cross-validation**: K experiments, each with 1 fold held out; all data used for both training and testing across folds.
- **Bootstrap sampling**: Samples *with replacement* (this detail is commonly tested).
- **Sensitivity = TPR; Specificity = TNR** — know the definitions and that they are ratios.
- **AUC interpretation**: Higher AUC = better model; ROC plots TPR vs FPR across thresholds.
- **Overfitting mitigation**: Penalize model complexity (regularization).
- **Model collapse definition**: Degradation from training on synthetic/self-generated data.
- **Hallucination**: False information presented as fact by AI; symbolic AI generally does not hallucinate; term is criticized as anthropomorphizing.
- **Adversarial examples**: Small, deliberate input perturbations (even single-pixel changes) can fool classifiers.
- **Backdoor attacks**: Can be inserted undetectably into classifiers, even with white-box transparency.
- **XAI**: Contrasts with black-box models; aims to make decisions interpretable; may implement the social right to explanation.
- **Netflix Prize**: Ensemble model; $1M prize; 10% improvement threshold; ratings later found inferior to behavioral signals for recommendations.
