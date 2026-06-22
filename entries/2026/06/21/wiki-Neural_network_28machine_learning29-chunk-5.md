---
source: chunks/wiki-Neural_network_28machine_learning29-chunk-5.md
source_url: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29
---

## Neural Network Types, Design, and Theoretical Properties

This page covers the major categories of artificial neural networks (Transformers, CNNs, GANs), approaches to network design including automated architecture search, and foundational theoretical properties: computational power, capacity, convergence behavior, and generalization/statistical methods.

## Key Concepts

- **Static vs. Dynamic NNs**: Static networks have fixed units, layers, weights, and topology; dynamic networks evolve through learning. Learning can be supervised or unsupervised.
- **Transformers**: Use attention mechanisms to compare every token against every other token in the input. Enabled chatbots, code generators, and mainstream AI applications.
- **Convolutional Neural Networks (CNNs)**: Feedforward networks using kernels and regularization; typically applied to visual and 2D data.
- **Generative Adversarial Networks (GANs)**: Pit networks against each other — one generates content, the other discriminates real from fake — driving each other to improve.
- **Neural Architecture Search (NAS)**: Automates network design by proposing candidate models, evaluating them, and feeding results back. Implementations include AutoML and AutoKeras.
- **Hyperparameters**: Design choices that are set by the practitioner, not learned during training (e.g., learning rate, number of layers).
- **Universal Approximation Theorem**: Proves the multilayer perceptron can approximate any function, but does not specify how many neurons, what topology, or what weights are needed.
- **Turing Completeness**: A recurrent network with rational-valued weights has universal Turing machine power; irrational weights yield super-Turing power (though the latter claim has failed verification).
- **Capacity**: A network's ability to model any given function. Measured by information capacity and VC dimension. VC dimension for arbitrary inputs is half the information capacity of a perceptron.
- **Convergence Challenges**: Networks may get stuck in local minima, fail to converge from distant starting points, become computationally impractical at scale, or cross saddle points that block the solution.
- **Spectral Bias (Frequency Principle)**: NNs with small parameter counts fit target functions from low to high frequencies; deeper networks are more biased toward low frequencies.
- **Infinite-Width Limit**: As network width approaches infinity, behavior is well-described by first-order Taylor expansion, inheriting convergence properties of affine (linear) models.
- **Overfitting**: Occurs in over-specified systems where capacity far exceeds need. Addressed by cross-validation (to select hyperparameters) and regularization (Bayesian priors over simpler models, or minimizing empirical + structural risk).
- **Confidence Analysis**: Supervised networks using MSE cost can estimate variance from validation-set MSE, then compute confidence intervals assuming normal distribution. Valid only while output distribution is unchanged and network is unmodified.
- **Softmax Activation**: Generalizes the logistic function; outputs interpretable as posterior probabilities for classification, providing a certainty measure.

## Commands and Syntax

- **Softmax function**: y_i = e^(x_i) / sum_j(e^(x_j)) — converts raw output scores into a probability distribution over classes.
- **scikit-learn**: Provides functions for building deep networks from scratch.
- **AutoKeras / AutoML**: Tools for automated neural architecture search.

## Relationships

- **Attention mechanism** is the core innovation linking Transformers to their dominance in NLP and generative AI.
- **Regularization** connects to Bayesian inference, statistical learning theory, and overfitting prevention.
- **VC dimension** links capacity theory to measure theory and statistical learning bounds.
- **Cross-validation** ties generalization to hyperparameter selection and model evaluation.
- **Universal approximation theorem** underpins the theoretical justification for multilayer perceptrons across all function-fitting tasks.
- **Softmax** connects neural network outputs to probabilistic classification and the logistic function.
- **NAS/AutoML** represents the intersection of meta-learning and network design, removing manual architecture decisions.

## Exam-Relevant Points

- The universal approximation theorem applies to multilayer perceptrons but does not specify the required architecture or parameters.
- Recurrent networks with rational weights are Turing-complete; irrational weights theoretically yield super-Turing power.
- VC dimension for arbitrary inputs equals half the information capacity of a perceptron.
- Hyperparameters are not learned — they are set before training begins.
- Overfitting countermeasures: cross-validation for hyperparameter tuning, regularization to penalize complexity (Bayesian priors or structural risk minimization).
- Softmax converts outputs to posterior probabilities, enabling confidence-based classification.
- Spectral bias: small-parameter NNs learn low frequencies first; deeper networks amplify this bias.
- Infinite-width networks behave like linear models (first-order Taylor expansion).
- MSE-based confidence intervals on validation data are valid only if the output distribution remains constant and the network is unchanged.
- GANs use adversarial training between generator and discriminator networks.
- CNNs use kernels and regularization, primarily for visual/2D data.
- Transformers use token-to-token attention over the full input sequence.
