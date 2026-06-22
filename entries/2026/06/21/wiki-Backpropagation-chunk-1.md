---
source: chunks/wiki-Backpropagation-chunk-1.md
source_url: https://en.wikipedia.org/wiki/Backpropagation
---

## Backpropagation: Gradient Computation for Neural Network Training

Backpropagation is the foundational algorithm for computing gradients in neural networks. It efficiently applies the chain rule to calculate how each weight in the network contributes to the overall loss, propagating derivative information backward from the output layer to the input layer. While strictly a gradient computation method, the term is often used loosely to refer to the entire training process including the weight update step.

## Key Concepts

- **Core definition**: Backpropagation is an efficient application of the chain rule to compute the gradient of a loss function with respect to all network weights for a single input-output pair.
- **Direction of computation**: Derivatives propagate backward, one layer at a time, from output layer to input layer — hence "backpropagation."
- **Efficiency mechanism**: Avoids redundant computation in two ways: (1) does not recompute derivatives for later layers when computing gradients at earlier layers, (2) directly computes gradients of weights w.r.t. the loss rather than computing unnecessary intermediate derivatives of hidden layer activations.
- **Key intermediate quantity**: delta (the gradient of the weighted input at each layer) is the only data needed to compute weight gradients at that layer; it is computed recursively from the next layer's delta.
- **Distinction from optimization**: Backpropagation only computes the gradient. The gradient is then used by an optimizer (SGD, Adam, etc.) to update weights.
- **Alternative names**: "Reverse mode of automatic differentiation," "reverse accumulation."
- **Training vs. evaluation distinction**: During training, input-output pairs are fixed while weights vary; during evaluation, weights are fixed while inputs vary.
- **Network as composition**: g(x) = f^L(W^L f^{L-1}(W^{L-1} ... f^1(W^1 x)...)) — nested function composition and matrix multiplication.

## Commands and Syntax

**Mathematical notation used in the algorithm:**

| Symbol | Meaning |
|--------|---------|
| `x` | Input feature vector |
| `y` | Target output (e.g., one-hot encoded class label) |
| `C` | Loss/cost function (cross-entropy for classification, squared error for regression) |
| `L` | Number of layers |
| `W^l` | Weight matrix between layer l-1 and layer l |
| `w_jk^l` | Weight from node k in layer l-1 to node j in layer l |
| `f^l` | Activation function at layer l |
| `a_j^l` | Activation of node j in layer l |
| `delta^l` | Gradient of the weighted input at layer l (key intermediate quantity) |

**Common activation functions**: sigmoid, tanh, ReLU, Swish, Mish

**Common output-layer activations**: logistic (binary classification), softmax (multi-class classification)

**Common loss functions**: cross-entropy/log loss (classification), squared error loss (regression)

## Relationships

- **Chain rule** (calculus): The mathematical foundation that backpropagation applies efficiently.
- **Stochastic gradient descent (SGD)**: The most basic optimizer that uses backpropagation's computed gradients to update weights.
- **Adam optimizer**: A more advanced optimizer that uses backpropagation gradients as an intermediate step.
- **Automatic differentiation**: Backpropagation is a specific instance of reverse-mode automatic differentiation applied to neural networks.
- **Feedforward neural networks**: The primary architecture backpropagation was designed for; can be expressed via matrix multiplication.
- **Loss functions**: Backpropagation requires the loss function (and activation functions) to be differentiable and efficiently evaluable.
- **Activation functions**: The choice of activation function affects gradient flow; ReLU addresses vanishing gradient problems that plagued sigmoid/tanh.

## Exam-Relevant Points

- Backpropagation is **only** the gradient computation algorithm — it is not an optimizer and does not specify how weights are updated.
- It works by computing gradients **backward** from output to input layer, which is what makes it efficient compared to computing each weight's gradient independently.
- Bias terms are not treated specially — they correspond to a weight with a fixed input of 1.
- The algorithm is agnostic to the specific loss function and activation functions, as long as they and their derivatives can be evaluated efficiently.
- Cross-entropy is the standard loss for classification; squared error loss is standard for regression.
- Softmax is used at the output layer for multi-class classification; logistic function for binary classification.
- ReLU has largely replaced sigmoid as the default hidden-layer activation function.
- The key insight for efficiency: delta^l (gradient of weighted input at layer l) can be computed recursively from delta^(l+1), and delta^l is sufficient to compute all weight gradients at layer l.
- During training, inputs are fixed and weights vary; during inference/evaluation, weights are fixed and inputs vary.
