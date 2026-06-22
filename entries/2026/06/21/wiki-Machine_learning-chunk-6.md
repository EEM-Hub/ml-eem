---
source: chunks/wiki-Machine_learning-chunk-6.md
source_url: https://en.wikipedia.org/wiki/Machine_learning
---

## ML Ethics, Hardware Platforms, and Software Ecosystem

This page covers three distinct areas of the machine learning landscape: the ethical considerations surrounding ML systems (bias, fairness, financial incentives), the hardware infrastructure that powers ML workloads (GPUs, TPUs, neuromorphic computing, embedded systems), and a comprehensive catalog of open-source and proprietary ML software frameworks, along with key academic journals and conferences.

## Key Concepts

- **Algorithmic bias** arises when ML systems are trained on historically biased data, causing them to reproduce and digitize existing societal prejudices (racial, gender, socioeconomic)
- **Bias propagation path**: biased training data → biased model → biased decisions at scale, with examples in hiring (Amazon-style resume screening), criminal justice (ProPublica recidivism study), healthcare admissions (St. George's Medical School 1988), and image recognition (Google Photos gorilla misclassification 2015)
- **Language model bias**: models trained on human language corpora inevitably absorb human biases embedded in that language (demonstrated by Microsoft Tay chatbot 2016)
- **Diversity gap in AI**: only 16.1% of AI faculty are female; among new US AI PhD graduates, 45% white, 22.4% Asian, 3.2% Hispanic, 2.4% African American — this lack of representation contributes to bias vulnerability
- **Fairness in ML** is an active subfield focused on reducing bias and ensuring ML serves human good
- **Financial incentive conflicts**: particularly in healthcare, where ML systems may optimize for revenue generation (unnecessary tests/medications) rather than patient outcomes
- **GPU dominance**: by 2019, GPUs displaced CPUs as the primary training hardware for large-scale commercial cloud AI
- **Compute scaling**: OpenAI found a 300,000x increase in compute from AlexNet (2012) to AlphaZero (2017), with a doubling-time of 3.4 months
- **TPUs (Tensor Processing Units)**: Google-designed ASIC hardware optimized for tensor computations, using matrix multiplication units and high-bandwidth memory; introduced 2016
- **Neuromorphic computing**: hardware designed to emulate biological neural network structure; includes physical neural networks using memristors to simulate synapses
- **Embedded ML (TinyML)**: deploying models on resource-constrained devices (wearables, edge devices, microcontrollers) to reduce latency, improve privacy, and eliminate cloud dependency
- **Model optimization techniques for embedded**: pruning, quantization, knowledge distillation, low-rank factorization, neural architecture search, parameter sharing

## Commands and Syntax

No commands in this section. Key optimization techniques for embedded ML deployment:

- **Pruning** — remove redundant weights/neurons
- **Quantization** — reduce numerical precision (e.g., FP32 → INT8)
- **Knowledge distillation** — train smaller "student" model to mimic larger "teacher" model
- **Low-rank factorization** — decompose weight matrices into lower-rank approximations
- **Neural architecture search (NAS)** — automated search for efficient network architectures
- **Parameter sharing** — reuse weights across layers or components

## Relationships

- **Algorithmic bias** ↔ **Fairness (ML)**: fairness is the corrective discipline addressing bias
- **Ethics** ↔ **AI Safety / AI Alignment**: ethical concerns extend to existential risk from superintelligence and autonomous weapons
- **Deep neural networks** → **Hardware acceleration**: DNNs drove the demand for specialized hardware (GPUs → TPUs → neuromorphic)
- **Embedded ML** ↔ **Privacy/Security**: on-device inference directly addresses data privacy concerns from the ethics domain
- **Embedded ML** ↔ **Model compression**: pruning, quantization, and distillation are enabling techniques
- **TPUs** ↔ **Cloud AI**: TPUs are tightly coupled with Google Cloud infrastructure
- **Open-source frameworks** (TensorFlow, PyTorch, scikit-learn, JAX) form the dominant software ecosystem; PyTorch and TensorFlow are the primary deep learning frameworks
- **Key journals**: JMLR, Nature Machine Intelligence, Neural Computation
- **Key conferences**: NeurIPS, ICML, ICLR, KDD, AAAI, ACL

## Exam-Relevant Points

- **St. George's Medical School (1988)**: early documented case of algorithmic discrimination — computer program denied ~60 candidates based on gender or non-European names
- **Compute doubling time**: 3.4 months for largest DL projects (AlexNet to AlphaZero era), representing a 300,000x increase
- **TPUs introduced in 2016** by Google, optimized for tensor/matrix operations, used for AlphaFold and LLMs
- **GPU displaced CPU by 2019** as dominant training hardware for large-scale commercial AI
- **ProPublica finding**: ML recidivism algorithm falsely flagged Black defendants as high risk at twice the rate of white defendants
- **Microsoft Tay (2016)**: chatbot that learned racist/sexist language from Twitter data — demonstrates unfiltered training data risks
- **Embedded ML optimization techniques** (pruning, quantization, knowledge distillation, low-rank factorization, NAS, parameter sharing) — know all six
- **Physical neural networks** use memristors to emulate synaptic function in hardware
- **16.1%** of AI faculty are female (CRA 2021) — key diversity statistic
- **Neuromorphic computing** can be software-based simulation OR specialized hardware
- **Key open-source frameworks to know**: TensorFlow (Google), PyTorch (Meta), scikit-learn, Keras, JAX, XGBoost, LightGBM, CatBoost, Apache Spark MLlib, Caffe, MXNet
- **Proprietary ML platforms**: AWS ML, Azure ML, Google Cloud Vertex AI, IBM Watson Studio, Oracle Data Mining
