---
source: chunks/wiki-Neural_network_28machine_learning29-chunk-4.md
source_url: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29
---

## Neural Network Training and Learning Methods

This page covers the complete training/learning pipeline for neural networks, from the core optimization loop (loss functions, backpropagation, weight updates) through hyperparameter configuration, learning paradigms (supervised, unsupervised, reinforcement, self-supervised), and alternative training approaches (neuroevolution, stochastic networks, topological deep learning).

## Key Concepts

- **Training** adjusts network weights to minimize observed errors on sample data; it occurs before deployment and does not continue afterward (unlike biological brains)
- **Empirical risk minimization** adjusts weights to minimize the difference between predicted and known outputs across training samples
- **Loss function** measures the degree of error; desirable properties include convexity, differentiability, and robustness; in probabilistic models, posterior probability can serve as an inverse cost
- **Backpropagation** calculates the gradient of the loss function with respect to weights, propagating error from output nodes back through the network to input nodes
- **Hyperparameters** are configuration values set before training (learning rate, batch size, number of layers/nodes); they strongly influence performance and are tuned between training runs
- **Learning rate** controls the size of corrective steps — high rates train faster with lower accuracy; low rates train slower with potentially greater accuracy; adaptive learning rates adjust dynamically
- **Momentum** balances the current gradient against the previous weight change; values near 0 emphasize the gradient, values near 1 emphasize the prior change
- **Training convergence** — learning ends when additional observations no longer usefully reduce the cost; cost approaches but typically does not reach zero
- **Stochastic neural networks** introduce random variations (stochastic transfer functions or weights) to escape local minima; Bayesian neural networks are stochastic networks trained with a Bayesian approach
- **Neuroevolution** uses evolutionary computation to create network topologies and weights; competitive with gradient descent and less prone to getting stuck in dead ends

## Commands and Syntax

- **Self-learning crossbar algorithm** (pseudocode):
  ```
  In situation s perform action a;
  Receive consequence situation s';
  Compute emotion of being in consequence situation v(s');
  Update crossbar memory w'(a,s) = w(a,s) + v(s');
  ```

- **Weight update methods**: stochastic gradient descent (SGD), extreme learning machines, "no-prop" networks, training without backtracking
- **Hyperparameter optimization**: adjusting hyperparameters between training runs (also called hyperparameter tuning)
- **Training modes**:
  - **Stochastic**: adjust weights after each individual sample (introduces noise, avoids local minima)
  - **Batch**: adjust weights based on accumulated errors over a full batch (faster, more stable descent)
  - **Mini-batch**: compromise using small randomly-selected subsets of data

## Relationships

- **Mathematical optimization & statistical estimation** — most learning models are direct applications of these fields
- **Supervised learning** — paired input/output training; uses mean-squared error; applies to classification and regression (pattern recognition, function approximation, sequential data like handwriting/speech/gesture recognition)
- **Unsupervised learning** — no labeled outputs; cost function reflects a priori assumptions; applies to clustering, statistical distribution estimation, compression, and filtering
- **Self-supervised learning (SSL)** — generates supervisory signals from the data itself via augmentation/transformation; two-step process (pretext task with pseudo-labels, then supervised/unsupervised fine-tuning); used in audio processing and speech recognition
- **Reinforcement learning** — agent takes actions in an environment, receives observations and costs; modeled as a Markov decision process (MDP); explores vs. exploits; combined with dynamic programming yields neurodynamic programming (applications: vehicle routing, games, natural resource management, medicine)
- **Topological deep learning (TDL)** — integrates algebraic, differential, and geometric topology with deep networks for high-order data (introduced 2017)
- **Other optimization methods**: evolutionary methods, gene expression programming, simulated annealing, expectation-maximization, non-parametric methods, particle swarm optimization

## Exam-Relevant Points

- Backpropagation computes the **gradient of the loss function with respect to weights**, not the error itself — the gradient determines how to adjust weights
- Loss functions should exhibit **convexity, differentiability, and robustness**
- **High learning rate** = faster training, lower accuracy; **low learning rate** = slower training, higher potential accuracy — this is a fundamental tradeoff
- The four major learning paradigms: **supervised, unsupervised, reinforcement, self-supervised**
- Supervised learning uses labeled pairs; unsupervised has no labels; self-supervised generates its own labels from data augmentation; reinforcement learning uses reward signals from environment interaction
- Reinforcement learning is formally modeled as a **Markov decision process (MDP)** with state transitions governed by probability distributions
- **Mini-batch gradient descent** is the standard compromise between stochastic (per-sample) and batch (full-dataset) updates
- Stochastic training reduces risk of getting stuck in **local minima** due to the noise it introduces
- Neural networks require training to be completed **before deployment** — they do not learn continuously after deployment (in the standard paradigm)
- **Hyperparameter tuning** occurs between training runs, not during them; hyperparameters include learning rate, batch size, and network architecture parameters
