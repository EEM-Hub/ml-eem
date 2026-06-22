---
source: chunks/wiki-Recurrent_neural_network-chunk-4.md
source_url: https://en.wikipedia.org/wiki/Recurrent_neural_network
---

## Training Methods for Recurrent Neural Networks

This page covers the primary techniques used to train recurrent neural networks (RNNs), including teacher forcing for sequence generation, gradient descent variants (BPTT and RTRL), connectionist temporal classification (CTC) for variable-timing sequences, and global optimization methods such as genetic algorithms.

## Key Concepts

- **Teacher forcing**: During training, the decoder receives the *ground-truth* output sequence as input for generating the next token, rather than its own (potentially erroneous) predictions. This prevents error compounding where an early mistake causes all subsequent outputs to diverge.
- **Autoregression**: An RNN trained as a conditional generative model of sequences, producing one token at a time conditioned on prior tokens.
- **Backpropagation Through Time (BPTT)**: The standard gradient descent method for RNNs; a special case of general backpropagation unrolled across time steps. Time complexity is O(number of weights) per step but requires storing all forward activations within the time horizon.
- **Real-Time Recurrent Learning (RTRL)**: An online variant using forward-mode automatic differentiation. Local in time (updates are continual) but not local in space. Time complexity is O(hidden units × weights) per step — more expensive than BPTT.
- **Local in space**: Weight updates depend only on information in connected units; update complexity is linear in weight vector dimensionality.
- **Local in time**: Updates are online, depending only on the most recent time step rather than a stored history.
- **Vanishing gradient problem**: Error gradients decay exponentially with the length of the time lag between relevant events, making it difficult for standard RNNs to learn long-range dependencies.
- **LSTM**: Addresses the vanishing gradient problem using a BPTT/RTRL hybrid learning method with gated memory cells.
- **IndRNN (Independently Recurrent Neural Network)**: Solves vanishing/exploding gradients by restricting each neuron's recurrence to its own past state; cross-neuron information is handled in subsequent layers.
- **Causal Recursive Backpropagation (CRBP)**: An online algorithm combining BPTT and RTRL for locally recurrent networks; can minimize the global error term.
- **Connectionist Temporal Classification (CTC)**: A specialized loss function for sequence modeling where input-output alignment timing is variable (e.g., speech recognition).
- **Global optimization for RNNs**: Treats weight training as a non-linear global optimization problem; genetic algorithms are the most common approach for unstructured networks.

## Commands and Syntax

No specific commands; conceptual training procedures:

- **Teacher forcing procedure**: At decoder step k, feed ground-truth tokens (y₁, ..., yₖ) to predict ŷₖ₊₁, rather than feeding predicted tokens (ŷ₁, ..., ŷₖ).
- **Genetic algorithm for RNN training**:
  1. Encode network weights as a chromosome (one gene per weight link)
  2. For each chromosome: assign weights → forward-propagate training set → compute mean-squared error
  3. Fitness function = reciprocal of MSE
  4. Evolve population until stopping criterion: learned percentage threshold, MSE minimum, or max generations reached

## Relationships

- **Seq2seq models**: Teacher forcing is a core training technique for encoder-decoder (seq2seq) architectures used in machine translation.
- **LSTM / GRU**: Directly motivated by the vanishing gradient problem in standard RNN gradient descent; LSTM uses hybrid BPTT/RTRL.
- **Attention mechanisms**: Complement teacher forcing in encoder-decoder models (shown in the referenced diagram).
- **Backpropagation**: BPTT is a special case; understanding general backpropagation is prerequisite.
- **Activation functions**: Must be differentiable for gradient descent to work in RNNs.
- **Automatic differentiation**: RTRL is an instance of forward-mode AD with stacked tangent vectors.
- **Genetic algorithms / simulated annealing / particle swarm optimization**: Alternative training paradigms when gradient-based methods are insufficient.

## Exam-Relevant Points

- Teacher forcing feeds *ground-truth outputs* (not model predictions) to the decoder during training to prevent error accumulation.
- BPTT is O(weights) per time step but requires storing all activations; RTRL is O(hidden × weights) per step but is online (no storage of history).
- BPTT is local in space but not in time; RTRL is local in time but not in space. Biological neural networks appear local in both.
- The vanishing gradient problem causes error gradients to decay *exponentially* with the time lag — this is the core motivation for LSTM and IndRNN architectures.
- CTC is specifically designed for problems where the alignment between input and output sequences is unknown or variable (e.g., speech-to-text).
- In genetic algorithm training of RNNs, the fitness function is the *reciprocal* of mean-squared error (goal is to *maximize* fitness = *minimize* error).
- Stopping criteria for GA-based training: learned percentage of training data, MSE threshold, or maximum generations.
- CRBP unifies BPTT and RTRL for locally recurrent networks and can minimize the global error term, improving stability.
