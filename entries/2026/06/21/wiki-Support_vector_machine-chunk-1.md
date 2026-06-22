---
source: chunks/wiki-Support_vector_machine-chunk-1.md
source_url: https://en.wikipedia.org/wiki/Support_vector_machine
---

## Support Vector Machines (SVMs)

Support vector machines are supervised max-margin models used for classification and regression. Developed at AT&T Bell Laboratories by Vapnik and Chervonenkis, SVMs find the optimal separating hyperplane that maximizes the margin between classes. They can handle non-linear classification via the kernel trick, which implicitly maps inputs into high-dimensional feature spaces where linear separation becomes possible.

## Key Concepts

- **Maximum-margin hyperplane**: The hyperplane that maximizes the distance to the nearest training data point of any class; larger margins correlate with lower generalization error and reduced overfitting.
- **Support vectors**: The data points closest to the decision boundary that define the margin and determine the hyperplane's position.
- **Kernel trick**: A method to perform non-linear classification by computing dot products in a high-dimensional feature space without explicitly performing the mapping, using a kernel function k(x, y).
- **Soft margin**: Allows some misclassifications to handle noisy or non-separable data; controlled by a regularization parameter C.
- **Epsilon-sensitive loss**: For regression tasks (SVR), predictions within epsilon of the true value incur no penalty.
- **Linear separability**: SVMs natively solve linearly separable problems; the kernel trick extends this to non-linear boundaries.
- **Max-margin principle**: Among all valid separating hyperplanes, choose the one with the largest functional margin to minimize generalization error.
- **Support vector clustering**: An unsupervised variant (Siegelmann & Vapnik) that applies SVM statistics to unlabeled data for cluster discovery.

## Commands and Syntax

Common kernel functions used with SVMs:
- **Linear**: k(x, y) = x · y (no transformation)
- **Polynomial**: k(x, y) = (x · y + c)^d
- **RBF/Gaussian**: k(x, y) = exp(-gamma ||x - y||²)
- **Sigmoid**: k(x, y) = tanh(alpha * x · y + c)

Decision function form: sum_i(alpha_i * k(x_i, x)) = constant, where alpha_i are learned parameters and x_i are support vectors from the training data.

Scikit-learn example:
```python
from sklearn.svm import SVC
clf = SVC(kernel='rbf', C=1.0, gamma='scale')
clf.fit(X_train, y_train)
predictions = clf.predict(X_test)
```

## Relationships

- **VC theory / Statistical learning theory**: SVMs are grounded in Vapnik-Chervonenkis theory, which provides generalization bounds based on margin and VC dimension.
- **Kernel methods**: SVMs are the canonical application of kernel methods; the same kernels apply to kernel PCA, kernel ridge regression, etc.
- **Logistic regression / linear regression**: Competing linear models; SVMs do not necessarily outperform them in predictive accuracy but offer max-margin guarantees.
- **Perceptron**: The SVM can be viewed as the "perceptron of optimal stability" — the perceptron that maximizes margin.
- **Structured prediction**: SVMs extend to structured output spaces (structured SVMs) for tasks like sequence labeling.
- **Clustering (unsupervised)**: Support vector clustering adapts the SVM framework for unsupervised grouping.
- **Neural networks**: Both are supervised classifiers; SVMs dominated before the deep learning era and remain preferred for small-to-medium datasets with clear margin structure.

## Exam-Relevant Points

- SVMs were invented by Vapnik and Chervonenkis in 1964; the kernel trick extension was proposed by Boser, Guyon, and Vapnik in 1992; the soft margin formulation was published by Cortes and Vapnik in 1995.
- The kernel trick avoids explicitly computing high-dimensional feature mappings — it only requires pairwise dot products via the kernel function.
- Larger margins lead to lower generalization error — this is the core inductive bias of SVMs.
- SVMs are resilient to noisy data due to the max-margin formulation and soft margin slack variables.
- SVMs work for both classification (SVC) and regression (SVR, with epsilon-insensitive loss).
- The decision boundary depends only on support vectors, not on all training points — this makes SVMs memory-efficient at prediction time.
- SVMs do not clearly outperform other linear models like logistic regression in predictive performance — their strength is theoretical guarantees and flexibility via kernels.
- Applications include text categorization, image classification, handwriting recognition, protein classification, and satellite data analysis.
