---
source: chunks/wiki-Deep_learning-chunk-6.md
source_url: https://en.wikipedia.org/wiki/Deep_learning
---

## Deep Learning: Foundational References and Historical Milestones

This page is the bibliography for the deep learning Wikipedia article. While purely a reference list, it maps the seminal papers, key researchers, and chronological development of deep learning — from early neural network theory through modern architectures. The references themselves constitute a reading list of the field's most important works.

## Key Concepts

- **Deep learning** is defined as "layer-wise learning of feature hierarchies" (Schulz & Behnke, 2012) — networks with multiple processing layers that learn representations at increasing levels of abstraction
- **Universal approximation theorem**: A single hidden layer with sufficient width can approximate any continuous function (Cybenko 1989, Hornik 1991), but depth provides exponentially more efficient representations
- **Representation learning**: Deep networks automatically discover representations needed for detection or classification, eliminating manual feature engineering (Bengio et al., 2013)
- **Vanishing/exploding gradient problem**: Identified by Hochreiter (1991) as the core difficulty in training deep networks — gradients diminish or blow up through many layers
- **Greedy layer-wise pretraining**: Bengio et al. (2007) showed training one layer at a time could initialize deep networks effectively, a breakthrough that reignited deep learning research
- **Deep belief networks** (Hinton, 2009): Generative models composed of stacked restricted Boltzmann machines, trained greedily layer by layer

## Commands and Syntax

No commands or configuration syntax — this is a bibliography. However, the key papers to obtain for study:

- **LeCun, Bengio, Hinton (2015)** — *Nature* review paper: the single most-cited overview of deep learning
- **Schmidhuber (2015)** — *Neural Networks* survey: comprehensive historical overview with 85–117 pages of detail
- **Bengio (2009)** — *Foundations and Trends*: "Learning Deep Architectures for AI" — foundational tutorial
- **Deng & Yu (2014)** — "Deep Learning: Methods and Applications" — practical methods focus
- **Goodfellow, Bengio, Courville** — *Deep Learning* textbook (implied by multiple Bengio citations)

## Relationships

- **Backpropagation history**: Chain rule (Leibniz, 1676) → gradient methods (Kelley, 1960) → automatic differentiation (Linnainmaa, 1970) → backprop applied to neural nets (Werbos, 1982; Rumelhart, Hinton & Williams, 1986)
- **CNN lineage**: Neocognitron (Fukushima, 1979–1980) → shift-invariant networks (Zhang, 1988) → LeNet for zip codes (LeCun, 1989) → LeNet-5 for documents (LeCun et al., 1998) → AlexNet/ImageNet breakthrough (Krizhevsky et al., 2012)
- **RNN lineage**: Jordan networks (1986) → Elman networks (1990) → sequence chunkers (Schmidhuber, 1991) → LSTM (Hochreiter & Schmidhuber, 1995/1997) → forget gates (Gers et al., 1999)
- **Associative memory lineage**: Nakano's Associatron (1971–1972) → Amari's self-organizing nets (1972) → Hopfield networks (1982) → Boltzmann machines → Deep belief networks
- **Early deep networks**: Ivakhnenko's Group Method of Data Handling (1965–1971) is cited as the first working deep learning algorithm with 8+ layers

## Exam-Relevant Points

- The term "deep learning" was introduced by **Rina Dechter (1986)** in the context of constraint satisfaction, later adopted for neural networks
- **Ivakhnenko & Lapa (1965–1971)**: Created the first deep learning networks using the Group Method of Data Handling (GMDH) — networks with multiple hidden layers trained layer by layer
- **Rosenblatt's Perceptron (1958)**: First trainable neural network; single-layer limitation later exposed by Minsky & Papert
- **Backpropagation**: Werbos (1974/1982) first applied it to neural networks; Rumelhart, Hinton & Williams (1986) popularized it
- **Krizhevsky et al. (2012)**: AlexNet winning ImageNet is widely considered the event that triggered the modern deep learning revolution
- **AlphaGo (2017)**: Defeated world champion Ke Jie, demonstrating deep RL capabilities
- **Key researchers to know**: LeCun, Bengio, Hinton (the "godfathers" — 2018 Turing Award), Schmidhuber, Hochreiter, Fukushima, Ivakhnenko, Rosenblatt, Werbos
- **Stochastic gradient descent** traces to Robbins & Monro (1951) — "A Stochastic Approximation Method"
- **Activation functions**: Swish/searching for activation functions (Ramachandran et al., 2017) showed learned activations can outperform hand-designed ones
- **Universal approximation** requires either sufficient width (Cybenko/Hornik) or sufficient depth (Lu et al., 2017 showed width matters too — narrow networks lose expressive power)
