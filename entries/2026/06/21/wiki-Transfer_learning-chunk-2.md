---
source: chunks/wiki-Transfer_learning-chunk-2.md
source_url: https://en.wikipedia.org/wiki/Transfer_learning
---

## Transfer Learning — Key References and Historical Development

This page collects the foundational and survey references for transfer learning in machine learning. The bibliography traces the field from its origins in 1976 through modern deep learning applications, covering theoretical foundations, survey papers, and domain-specific applications.

## Key Concepts

- **Transfer learning origins**: The concept dates back to Bozinovski & Fulgosi (1976), who studied pattern similarity and transfer in perceptron training — the first paper on transfer learning in neural networks.
- **"Teaching space"** (Bozinovski, 1981): An early representation concept for adaptive pattern classification that formalized how learned representations could transfer.
- **Discriminability-based transfer** (Pratt, 1992): One of the first formal methods for transferring knowledge between neural networks, presented at NIPS.
- **Multitask learning** (Caruana): A related paradigm where learning multiple tasks simultaneously improves generalization, covered in *Learning to Learn* (Thrun & Pratt).
- **Theoretical models of learning to learn** (Baxter): Formal frameworks for meta-learning and transfer, also in *Learning to Learn*.
- **Pan & Yang (2010) survey**: The most-cited survey on transfer learning, published in IEEE TKDE — defines taxonomy and categorization of transfer learning approaches.
- **Zhuang et al. (2019)**: A comprehensive updated survey reflecting the deep learning era of transfer learning.
- **Andrew Ng (NIPS 2016)**: Highlighted transfer learning as a key driver of practical AI applications in his influential tutorial "Nuts and bolts of building AI applications using Deep Learning."
- **Rethinking pre-training and self-training** (Zoph, 2020): Challenges assumptions about when pre-training helps, finding self-training can outperform transfer in some settings.

## Commands and Syntax

No commands or configuration syntax — this is a reference bibliography. Key citation identifiers for lookup:

- **Pan & Yang survey**: `doi:10.1109/TKDE.2009.191`
- **Zhuang et al. survey**: `arXiv:1911.02685`
- **Thrun & Pratt textbook**: ISBN `978-1-4615-5529-2`
- **Bozinovski 2020 retrospective**: Informatica 44: 291–302

## Relationships

- **Multitask learning**: Closely related paradigm; Caruana's chapter in *Learning to Learn* treats it as a form of inductive transfer.
- **Meta-learning / learning to learn**: Baxter's theoretical models provide the formal underpinning for why transfer works.
- **Deep learning and pre-training**: Zoph (2020) connects transfer learning to the pre-training vs. self-training debate central to modern NLP and vision.
- **Domain adaptation**: Multiple references (Arief-Ang et al., Lin & Jung) address transferring across domains — sensor data, EEG/emotion classification.
- **Reinforcement learning**: Karimpanal & Bouffanais (2019) extend transfer to RL via self-organizing maps; Banerjee & Stone (2007) address general game learning via knowledge transfer.
- **Bayesian methods**: Niculescu-Mizil & Caruana (2007) on Bayesian network structure learning; Rajat et al. (2006) on constructing informative priors via transfer.
- **Markov Logic Networks**: Mihalkova et al. (2007) show transfer by mapping and revising relational structures.

## Exam-Relevant Points

- **1976 is the origin year** for transfer learning in neural networks (Bozinovski & Fulgosi) — not a 2010s invention.
- **Pan & Yang (2010)** is the canonical survey reference — know its taxonomy (inductive, transductive, unsupervised transfer).
- **Andrew Ng's assertion** (NIPS 2016): transfer learning will be the next driver of ML commercial success after supervised learning.
- **Transfer is not always beneficial**: Zoph (2020) showed pre-training can hurt when strong data augmentation and self-training are available ("negative transfer" risk).
- **Cross-domain transfer** applies broadly: text classification (Do & Ng, 2005), handwritten character recognition across scripts (Maitra et al., 2015), biological signal processing EEG/EMG (Bird et al., 2020), room occupancy prediction (Arief-Ang et al.), cancer subtype discovery (Hajiramezanali et al., 2018).
- **Thrun & Pratt's *Learning to Learn*** (2012 edition, originally 1998) is the foundational textbook for the field.
- **Conditional transfer learning** (Lin & Jung, 2017): Addresses when and how to selectively transfer, important for avoiding negative transfer in domains like brain-computer interfaces.
