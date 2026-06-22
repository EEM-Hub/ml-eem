---
source: chunks/wiki-Machine_learning-chunk-4.md
source_url: https://en.wikipedia.org/wiki/Machine_learning
---

## Machine Learning Models: Types, Training, and Selection

This page provides a comprehensive survey of the major model families used in machine learning, covering their structure, learning mechanisms, and typical applications. It spans from neural networks and decision trees through probabilistic and evolutionary approaches, and concludes with training considerations including overfitting, bias, and federated learning.

## Key Concepts

- A **machine learning model** is a mathematical model trained on data to make predictions or classifications on new data; training iteratively adjusts internal parameters to minimize prediction errors.
- The term "model" can refer to a general class (e.g., "neural networks"), a specific architecture, or a fully trained instance with tuned parameters.
- **Model selection** is the process of choosing the best model type for a given task.
- **Artificial Neural Networks (ANNs)**: Interconnected nodes ("artificial neurons") loosely inspired by biological brains. Signals flow through weighted edges; weights adjust during learning. Layers perform transformations; input flows from input layer to output layer.
- **Deep learning**: ANNs with multiple hidden layers, successful in computer vision and speech recognition.
- **Decision trees**: Predictive models mapping observations (branches) to target values (leaves). Classification trees output discrete labels; regression trees output continuous values.
- **Random Forest Regression (RFR)**: Ensemble method building multiple decision trees on bootstrapped samples, averaging predictions to reduce overfitting and bias. Works on single-output and multi-regressor tasks.
- **Support-Vector Machines (SVMs)**: Supervised learning method for classification/regression. Non-probabilistic binary linear classifier that can perform non-linear classification via the **kernel trick** (mapping inputs to high-dimensional feature spaces).
- **Regression analysis**: Estimating relationships between input variables and features. Includes linear regression, ridge regression (regularization to mitigate overfitting), polynomial regression, logistic regression, kernel regression, and multivariate linear regression.
- **Bayesian networks**: Probabilistic graphical models using directed acyclic graphs (DAGs) to represent conditional independence among random variables. Dynamic Bayesian networks handle sequences; influence diagrams handle decision problems under uncertainty.
- **Gaussian processes**: Stochastic processes where every finite collection of random variables has a multivariate normal distribution. Uses a covariance function (kernel) to model point relationships. Popular as surrogate models in Bayesian optimization for hyperparameter tuning.
- **Genetic algorithms**: Search heuristics mimicking natural selection via mutation and crossover. Prominent in ML during the 1980s–1990s.
- **Belief functions (Dempster–Shafer theory)**: Framework for reasoning under uncertainty with connections to probability and possibility theory. Leverages ensemble fusion to handle decision boundaries, low samples, and ambiguous classes, but computational complexity scales with the number of propositions.
- **Rule-based machine learning (RBML)**: Automatically discovers interpretable rules from data. Includes learning classifier systems, association rule learning, and artificial immune systems. Valued for interpretability in healthcare, fraud detection, cybersecurity.
- **Overfitting**: A trained model fits training data too closely, performing poorly on new data. Regularization (e.g., ridge regression) is a common mitigation.
- **Algorithmic bias**: Biased or non-evaluated training data can produce skewed predictions with detrimental societal outcomes.
- **Federated learning**: Decentralized training across user devices, preserving privacy by not sending data to a central server (e.g., Google Gboard).

## Commands and Syntax

No specific commands or configuration syntax are described in this page — it is a conceptual overview. However, key procedural knowledge includes:

- **Training workflow**: Collect large, representative sample data → train model (iterative parameter adjustment) → evaluate for overfitting and bias → deploy.
- **Kernel trick** (SVMs/kernel regression): Implicitly map inputs to higher-dimensional feature spaces to enable non-linear classification without explicit transformation.
- **Bootstrapped sampling** (Random Forests): Each tree is trained on a random subset of training data drawn with replacement.
- **Bayesian inference**: Compute posterior probabilities of unobserved variables given observed evidence using the network's DAG structure.
- **Gaussian process prediction**: Given observed input-output pairs, compute distribution of unobserved outputs using covariance between observed and new points.

## Relationships

- **Model selection** is the meta-task of choosing among all model types listed here.
- **ANNs → Deep learning**: Deep learning is a subset of ANNs (multiple hidden layers).
- **Decision trees → Random forests**: RFR is an ensemble extension of decision trees.
- **SVMs ↔ Kernel regression**: Both use the kernel trick for non-linear problems.
- **Regression analysis** underpins many other models (e.g., logistic regression used in classification).
- **Bayesian networks ↔ Gaussian processes**: Both are probabilistic models; GPs are used in Bayesian optimization for hyperparameter tuning of other models.
- **Genetic algorithms ↔ ML**: Bidirectional relationship — GAs used as learning algorithms, ML used to improve GA performance.
- **Belief functions ↔ Ensemble methods**: Belief function approaches typically leverage ensemble fusion.
- **Training considerations** (overfitting, bias, federated learning) apply across all model types.
- **Supervised learning** is the umbrella for SVMs, regression, decision trees; **unsupervised** and **reinforcement** learning use different model families.

## Exam-Relevant Points

- A machine learning model is a mathematical model whose internal parameters are iteratively adjusted during training to minimize prediction errors.
- **Classification trees** produce discrete labels; **regression trees** produce continuous values.
- **Random forests** use bootstrapped sampling and averaging across multiple trees to reduce overfitting — this is an **ensemble method**.
- **SVMs** are non-probabilistic, binary, linear classifiers by default; the **kernel trick** enables non-linear classification by implicit mapping to higher dimensions. **Platt scaling** enables probabilistic classification with SVMs.
- **Ridge regression** adds regularization to linear regression to mitigate overfitting and bias.
- **Logistic regression** is used for statistical classification despite the name "regression."
- **Bayesian networks** use **directed acyclic graphs (DAGs)** and model **conditional independence**; **dynamic Bayesian networks** handle sequential data.
- **Gaussian processes** rely on a pre-defined **covariance function (kernel)** and are commonly used as **surrogate models in Bayesian optimization** for hyperparameter tuning.
- **Federated learning** decentralizes training to user devices, maintaining privacy — no raw data sent to a central server.
- **Algorithmic bias** results from training on biased or inadequately prepared data and is a growing focus of ML ethics.
- **Belief function** computational complexity depends on the number of propositions (classes) and can be much higher than standard ML approaches.
- **Rule-based ML** provides **interpretable** models, distinguishing it from black-box approaches like deep learning.
- **Genetic algorithms** use **mutation** and **crossover** operators, inspired by natural selection.
- **Multivariate linear regression** handles multiple dependent variables simultaneously, useful when outputs are interdependent.
