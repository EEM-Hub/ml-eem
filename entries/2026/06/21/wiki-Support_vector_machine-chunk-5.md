---
source: chunks/wiki-Support_vector_machine-chunk-5.md
source_url: https://en.wikipedia.org/wiki/Support_vector_machine
---

## SVM Extensions, Variants, and Implementation

This page covers the major extensions of support vector machines beyond standard binary classification — including multiclass methods, transductive SVMs for semi-supervised learning, structured SVMs, support vector regression, and Bayesian SVMs — along with practical implementation algorithms and toolkits.

## Key Concepts

- **Multiclass SVM** reduces a multi-label problem into multiple binary classification subproblems; the dominant strategies are **one-versus-all** (OVA) and **one-versus-one** (OVO).
- **One-versus-all**: builds one classifier per class (class vs. rest); classification uses winner-takes-all on calibrated output scores.
- **One-versus-one**: builds one classifier per pair of classes; classification uses max-wins voting (each classifier casts one vote for its predicted class).
- Other multiclass strategies: **DAGSVM** (directed acyclic graph), **error-correcting output codes**, and **Crammer-Singer** (single unified optimization instead of decomposition).
- **Transductive SVMs** (introduced by Vapnik, 1998) extend SVMs to **semi-supervised learning** — the learner receives both labeled training data and unlabeled test data, and jointly optimizes labels for the test set along with the separating hyperplane.
- **Structured SVM** generalizes SVM to predict complex structured outputs (parse trees, sequences, taxonomies) rather than scalar labels.
- **Support Vector Regression (SVR)** (Vapnik et al., 1996) uses an **epsilon-insensitive loss**: predictions within ε of the true value incur zero cost. Like classification SVMs, the model depends only on a subset of training points (support vectors). Slack variables handle infeasible cases.
- **Least-Squares SVM (LS-SVM)** is a variant proposed by Suykens and Vandewalle.
- **Bayesian SVM** (Polson & Scott, 2011) interprets the SVM as a graphical model via data augmentation, enabling flexible feature modeling, automatic hyperparameter tuning, and predictive uncertainty quantification. Scalable versions (VI and SVI) developed by Wenzel in 2017.
- **Data preprocessing** (standardization) is critical for SVM accuracy — common methods include min-max scaling, decimal scaling, and Z-score (subtract mean, divide by variance per feature).

## Commands and Syntax

- **SVR primal formulation**: minimize ½‖w‖² subject to |yᵢ − ⟨w, xᵢ⟩ − b| ≤ ε for all training samples.
- **Transductive SVM primal**: minimize ½‖w‖² subject to yᵢ(w · xᵢ − b) ≥ 1 for labeled data AND y*ⱼ(w · x*ⱼ − b) ≥ 1 for unlabeled test data, with y*ⱼ ∈ {−1, 1} as decision variables.
- **Key toolkits**: LIBSVM, LIBLINEAR, scikit-learn, MATLAB, SAS, SVMlight, kernlab (R), Shogun, Weka, Shark, OpenCV.
- **Key algorithms**: PEGASOS (sub-gradient descent for linear SVM), LIBLINEAR (coordinate descent — convergence iterations linear in data read time with Q-linear convergence), Platt's SMO (sequential minimal optimization — breaks QP into 2D analytic sub-problems), interior-point methods (solve KKT conditions directly).

## Relationships

- **Multiclass SVM** builds on binary classification SVM as a primitive and connects to multiclass classification theory and error-correcting codes.
- **Transductive SVM** connects SVM to **semi-supervised learning** and transductive inference.
- **SVR** is the regression analogue of classification SVM; shares the same kernel trick and support-vector sparsity property. Closely related to **logistic regression** in the linear case (same optimizer family).
- **Bayesian SVM** bridges SVMs with **probabilistic graphical models**, Bayesian inference, and posterior predictive distributions.
- **Structured SVM** connects to structured prediction, sequence labeling, and parsing.
- **Kernel methods** link SVMs to kernel machines, Fisher kernels, polynomial kernels, and RBF networks.
- **Platt scaling** is used to calibrate SVM outputs into probabilities (important for OVA multiclass).
- **Relevance vector machines** are the probabilistic sparse-kernel counterpart to SVMs.

## Exam-Relevant Points

- **OVA vs. OVO tradeoffs**: OVA builds K classifiers (one per class) and requires calibrated scores; OVO builds K(K−1)/2 classifiers and uses voting. Know which uses winner-takes-all vs. max-wins.
- **Transductive SVM** optimizes over both the hyperplane parameters AND the unlabeled test labels simultaneously — the test labels y* are decision variables in the optimization.
- **SVR epsilon-insensitive tube**: training points within ε of the prediction contribute zero loss; only points outside the tube are support vectors. As ε increases, fewer support vectors and less sensitivity to errors.
- **SMO algorithm**: decomposes QP into 2-dimensional sub-problems solved analytically; no numerical optimizer or large matrix storage needed; better scaling for difficult problems.
- **LIBLINEAR**: each iteration is linear in data read time with Q-linear convergence — extremely fast for linear SVMs.
- **Preprocessing matters**: standardization (Z-score: subtract mean, divide by variance per feature) is highly recommended before SVM training.
- **Crammer-Singer** method is notable for casting multiclass SVM as a single optimization problem rather than decomposing into binary sub-problems.
- **Bayesian SVM** enables automatic hyperparameter tuning and uncertainty quantification — distinguishes it from standard SVMs that require cross-validation for hyperparameters.
