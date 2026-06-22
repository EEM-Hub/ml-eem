---
source: chunks/wiki-Support_vector_machine-chunk-6.md
source_url: https://en.wikipedia.org/wiki/Support_vector_machine
---

## Support Vector Machines: Foundational Literature and Key References

This page compiles the seminal and influential references for Support Vector Machines (SVMs), covering the original formulation by Cortes and Vapnik (1995), extensions to kernels, multiclass methods, regression, Bayesian variants, optimization algorithms, and applications across text classification, medical imaging, and remote sensing.

## Key Concepts

- **SVM origin**: Cortes & Vapnik (1995) introduced soft-margin support-vector networks; Boser, Guyon & Vapnik (1992) proposed the kernel trick for optimal margin classifiers
- **Kernel method foundation**: Aizerman, Braverman & Rozonoer (1964) established the theoretical foundations of the potential function method, which underpins the kernel trick
- **Margin geometry**: The SVM margin equals 2/||w||, derived from the separating hyperplane formulation
- **Multiclass SVM strategies**: One-vs-one, one-vs-all, DAG-SVM (Platt et al. 2000), error-correcting output codes (Dietterich & Bakiri 1995), and direct multiclass formulations (Crammer & Singer 2001; Lee, Lin & Wahba 2004; GenSVM by Van den Burg & Groenen 2016)
- **Support Vector Regression (SVR)**: Drucker et al. (1997) introduced SVR; Smola & Schölkopf (2004) wrote the canonical tutorial; Suykens & Vandewalle (1999) proposed Least Squares SVM
- **Support Vector Clustering**: Ben-Hur, Horn, Siegelmann & Vapnik (2001) extended SVMs to unsupervised clustering
- **Bayesian SVMs**: Polson & Scott (2011) introduced data augmentation for SVMs; Wenzel et al. (2017) developed Bayesian nonlinear SVMs for big data
- **Transductive SVMs**: Joachims (1999) applied transductive inference for semi-supervised text classification
- **Loss function equivalence**: Rosasco et al. (2004) analyzed relationships between different loss functions; Collobert & Bengio (2004) showed links between perceptrons, MLPs, and SVMs

## Commands and Syntax

- **scikit-learn**: `sklearn.svm` module provides SVC, SVR, LinearSVC implementations (reference 7)
- **LIBLINEAR**: Library for large-scale linear classification (Fan et al. 2008) — used as the backend for `LinearSVC` in scikit-learn
- **LIBSVM**: Implied by Hsu, Chang & Lin (2003) practical guide — standard library for kernel SVM training
- **Practical guide workflow** (Hsu et al. 2003): scale features, use RBF kernel as default, grid-search C and gamma via cross-validation
- **Pegasos** (Shalev-Shwartz et al. 2007): Primal Estimated sub-GrAdient SOlver — stochastic gradient descent for SVM, O(1/t) convergence
- **SMO** (Platt 1998): Sequential Minimal Optimization — decomposes the QP into minimal 2-variable subproblems
- **Dual Coordinate Descent** (Hsieh et al. 2008): Efficient solver for large-scale linear SVMs

## Relationships

- **SVM vs. Logistic Regression**: Huang et al. (2014) compared SVMs and logistic regression for medical prediction (hypertension)
- **SVM vs. Neural Networks**: CNNs (Maitra et al. 2015) have superseded SVMs for tasks like handwriting recognition; Collobert & Bengio showed structural links between perceptrons, MLPs, and SVMs
- **SVM vs. Optimal Perceptron**: Opper et al. (1990) analyzed generalization ability of the optimal perceptron, a precursor concept
- **Structured prediction**: Tsochantaridis et al. extended SVMs to structured/interdependent output spaces, bridging classification and sequence labeling
- **PAC-Bayes theory**: Jin & Wang (2012) provided dimensionality-dependent margin bounds connecting SVM generalization to learning theory
- **Feature preprocessing**: Mohamad & Usman (2013) and Fennell et al. (2019) showed that standardization and feature space decomposition significantly affect SVM (and other algorithm) performance

## Exam-Relevant Points

- **Cortes & Vapnik (1995)** is THE foundational SVM paper — know the authors and year
- **Boser, Guyon & Vapnik (1992)** introduced the kernel trick to SVMs — predates the soft-margin paper
- **Margin = 2/||w||** — the geometric margin formula is fundamental to understanding the SVM objective
- **SMO (Platt 1998)** and **Pegasos (Shalev-Shwartz et al. 2007)** are the two most important SVM training algorithms to know
- **Multiclass**: One-vs-one generally outperforms one-vs-all (Hsu & Lin 2002; Duan & Keerthi 2005)
- **LIBLINEAR** is preferred for large-scale linear problems; kernel SVMs use LIBSVM or SMO-based solvers
- **SVR** uses an epsilon-insensitive loss function (Drucker et al. 1997; Smola & Schölkopf 2004 tutorial)
- **Feature scaling is critical** for SVM performance — always standardize before training
- **Applications to know**: text categorization (Joachims 1998), medical imaging (Gaonkar & Davatzikos 2013), NLP/semantic parsing (Pradhan et al. 2004), remote sensing (Maity 2016)
- **Transductive SVM** (Joachims 1999) bridges supervised and semi-supervised learning — uses unlabeled test data during training
