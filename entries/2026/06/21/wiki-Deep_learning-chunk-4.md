---
source: chunks/wiki-Deep_learning-chunk-4.md
source_url: https://en.wikipedia.org/wiki/Deep_learning
---

## Deep Learning Applications Across Domains

This page catalogs the major application areas where deep learning has achieved significant practical impact, spanning speech recognition, computer vision, NLP, drug discovery, scientific computing, and numerous other fields. It serves as a survey of where deep learning architectures (DNNs, CNNs, RNNs/LSTMs, Transformers, GNNs, PINNs) have been deployed successfully.

## Key Concepts

- **Automatic Speech Recognition (ASR)** was the first major convincing success of deep learning; LSTM RNNs can handle "very deep learning" tasks involving multi-second intervals with thousands of discrete time steps (~10ms each)
- **TIMIT dataset**: 630 speakers, 8 American English dialects, 10 sentences each — standard small-scale benchmark for phone-sequence recognition; phone error rate (PER) dropped from ~26% (random RNN) to ~16.5% (hierarchical convolutional deep maxout networks)
- **DNN progress in speech** accelerated across 8 areas: scale-up training, sequence discriminative training, deep feature processing, DNN adaptation, multi-task/transfer learning, CNN design for speech, LSTM variants, and tensor/generative-discriminative models
- **Image recognition** became "superhuman" — first for traffic signs (2011), then human faces (2014)
- **Word embedding** (e.g., word2vec) transforms atomic words into vector-space positions relative to other words; serves as an input layer enabling compositional vector grammars in RNNs
- **Sentence embedding** generalizes word embedding to entire sentences
- **Google Neural Machine Translation (GNMT)** uses end-to-end LSTM, translates whole sentences (not phrases), encodes sentence semantics, uses English as pivot between most language pairs
- **AlphaFold** (2020) achieved unprecedented accuracy in protein structure prediction from amino acid sequences
- **GNoME** (Google DeepMind, Nov 2023) discovered 2M+ new materials using deep learning for crystal structure stability prediction, validated at 71% success rate via robotic experiments
- **Physics-Informed Neural Networks (PINNs)** embed physical laws (e.g., Navier-Stokes) directly into neural network architecture, eliminating need for mesh generation in CFD
- **Deep BSDE method** combines deep learning with backward stochastic differential equations to solve high-dimensional PDEs in financial mathematics, overcoming the curse of dimensionality
- **Neural Joint Entropy Estimator (NJEE)** uses DNNs as classifiers to estimate entropy of stochastic processes; uses softmax output layer sized to alphabet of target variable; requires continuously differentiable activation functions for universal approximation theorem
- **GraphCast** predicts weather up to 10 days globally in under a minute, matching state-of-the-art traditional PDE-based systems
- **Epigenetic clock** using DNNs trained on 6,000+ blood samples and 1,000 CpG sites predicts biological age; detects accelerated aging in IBD, frontotemporal dementia, ovarian cancer, obesity

## Commands and Syntax

No specific commands or configuration syntax — this is a survey of applications rather than a how-to guide.

## Relationships

- **Architecture dependencies**: ASR relies heavily on LSTMs and Transformers; image recognition on CNNs and DNNs; NLP on word/sentence embeddings, LSTMs, and Transformers; drug discovery on GNNs; scientific computing on PINNs
- **Multi-task and transfer learning** connect speech recognition advances to other domains
- **Recommender systems** use latent factor models with deep learning for content-based and collaborative filtering (hybrid approach)
- **Drug discovery** connects to toxicology through off-target effect prediction (Tox21 dataset)
- **Medical image analysis** connects to both image recognition (CNNs) and bioinformatics
- **PINNs and Deep BSDE** bridge deep learning with traditional numerical methods for PDEs, connecting ML to physics simulation and computational finance
- **Materials science (GNoME)** connects to the Materials Project database for downstream research

## Exam-Relevant Points

- LSTM was competitive with traditional speech recognizers; the key innovation was forget gates
- TIMIT benchmark: know the progression from ~26% PER (random RNN) down to ~16.5% (hierarchical convolutional deep maxout)
- Deep learning surpassed human performance in image recognition: traffic signs (2011), faces (2014)
- Word2vec is a representational layer that maps words to vector-space positions; compositional vector grammar = PCFG implemented by RNN
- GNMT translates whole sentences, not phrase-by-phrase; uses English as intermediate pivot language
- AlphaFold (2020) — protein structure prediction from amino acid sequence with accuracy far beyond prior computational methods
- AtomNet — structure-based rational drug design (applied to Ebola, multiple sclerosis)
- GNNs first used for molecular property prediction in toxicology in 2017; generative NNs produced experimentally validated molecules (in mice) by 2019
- PINNs eliminate mesh generation requirements of conventional CFD
- Deep BSDE overcomes curse of dimensionality in high-dimensional financial PDEs
- NJEE is a strongly consistent entropy estimator, outperforms alternatives for large alphabet sizes
- GraphCast matches traditional weather prediction accuracy but runs in under a minute vs. hours for PDE solvers
- All major commercial speech systems (Cortana, Alexa, Google Now, Siri, Baidu) use deep learning
