---
source: chunks/wiki-Backpropagation-chunk-3.md
source_url: https://en.wikipedia.org/wiki/Backpropagation
---

## Backpropagation: Intuition and Learning as Optimization

This page covers the foundational intuition behind the backpropagation algorithm, framing neural network training as an optimization problem. It walks through a minimal example (two inputs, one output, no hidden layers, linear activation) to show how the error between predicted and target outputs defines a loss surface over the weight space, and how gradient descent navigates that surface to find optimal weights.

## Key Concepts

- **Backpropagation's purpose**: Train multi-layered neural networks to learn internal representations that map arbitrary inputs to outputs.
- **Learning as optimization**: Finding weights that minimize a loss function measuring discrepancy between predicted output *y* and target output *t*.
- **Loss functions**: Squared error `L(t,y) = (t - y)²` for regression; categorical cross-entropy for classification.
- **Output depends on weights**: For a linear neuron, `y = x₁w₁ + x₂w₂`. The error is therefore a function of the weights, not just the output.
- **Error surface geometry**: For a single training case with two weights, the loss function forms a parabolic cylinder. The minimum lies along a line (e.g., `w₁ = -w₂`), meaning multiple weight combinations can achieve zero error on one example.
- **Non-uniqueness**: A single training example may yield infinitely many weight solutions; additional training data or constraints are needed to converge to a unique solution.
- **Gradient descent**: The standard algorithm for finding weights that minimize error — backpropagation computes the steepest descent direction of the loss with respect to current weights.

## Commands and Syntax

- **Linear neuron output**: `y = x₁w₁ + x₂w₂`
- **Squared error loss**: `E = (t - y)²`
- **Concrete example**: Training case `(x₁=1, x₂=1, t=0)` yields `E = (w₁ + w₂)²`
- **Weight update rule** (conceptual): Modify weights along the steepest descent direction of the loss function (gradient descent).

## Relationships

- **Supervised learning**: Backpropagation is the core training algorithm for supervised learning with neural networks.
- **Loss functions**: Choice of loss function (squared error vs. cross-entropy) depends on the task type (regression vs. classification).
- **Gradient descent**: Backpropagation computes gradients; gradient descent uses them to update weights. They are complementary — backpropagation without gradient descent (or another optimizer) doesn't update anything.
- **Activation functions**: This example uses linear activation for simplicity; real networks use nonlinear activations, which is what makes backpropagation through hidden layers both necessary and nontrivial.
- **Optimization theory**: The entire training process is framed as finding a minimum of the error surface — connects to broader optimization concepts (convexity, local minima, saddle points).

## Exam-Relevant Points

- Backpropagation computes the **gradient of the loss function with respect to weights**, enabling gradient descent to update weights efficiently.
- The loss function for **regression** is typically squared error; for **classification**, categorical cross-entropy.
- A single training example can yield **infinitely many optimal weight configurations** — additional data or regularization constraints are needed for a unique solution.
- Weights are initialized **randomly** before training begins.
- The error surface for a linear neuron with two weights and one training case is a **parabolic cylinder**, not a simple parabola — the distinction matters because it illustrates the underdetermined nature of the problem.
- The key insight: learning reduces to **optimization** — finding weights that minimize the discrepancy between network output and target output across training examples.
