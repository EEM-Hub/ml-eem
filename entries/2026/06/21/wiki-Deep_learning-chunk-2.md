---
source: chunks/wiki-Deep_learning-chunk-2.md
source_url: https://en.wikipedia.org/wiki/Deep_learning
---

## History of Deep Learning: Key Milestones and Architectural Evolution

This page traces the historical development of deep learning from its earliest precursors in the 1920s through the "deep learning revolution" of the 2010s. It covers the invention and evolution of foundational architectures (feedforward networks, RNNs, CNNs, LSTMs, GANs, ResNets), the development of critical training algorithms (backpropagation, stochastic gradient descent), and the hardware advances (GPUs) that enabled modern deep learning at scale.

## Key Concepts

- **Two fundamental ANN types**: Feedforward neural networks (FNN/MLP) have no cycles; recurrent neural networks (RNN) have cycles in connectivity, enabling sequence processing.
- **Ising model (1920s)**: Non-learning RNN-like architecture by Lenz and Ising; made adaptive by Amari in 1972; republished by Hopfield in 1982.
- **Perceptron (1958)**: Rosenblatt's 3-layer MLP (input, random hidden, output). His 1962 book described 4-layer variants with learned weights.
- **Group Method of Data Handling (GMDH, 1965)**: First working deep learning algorithm by Ivakhnenko and Lapa. A 1971 paper trained an 8-layer network. Used polynomial activation functions — first "gates"/multiplicative units.
- **First SGD-trained deep MLP (1967)**: Amari published a 5-layer MLP trained by stochastic gradient descent that learned internal representations for non-linearly separable classes.
- **ReLU activation (1969)**: Introduced by Kunihiko Fukushima. Now the most popular activation function for deep learning.
- **Neocognitron (1979)**: Fukushima's CNN architecture with convolutional and downsampling layers — precursor to modern CNNs, but not trained by backpropagation.
- **Backpropagation**: Chain rule application to differentiable networks. Kelley (1960) had a continuous precursor; Linnainmaa's 1970 thesis gave the modern form; Werbos applied it to neural networks (1982); Rumelhart et al. popularized it (1986).
- **Vanishing gradient problem**: Identified and analyzed by Sepp Hochreiter (1991 thesis), motivating residual connections and LSTM.
- **LSTM (1995)**: Long Short-Term Memory by Hochreiter, solving long credit assignment paths. The modern form with "forget gate" came in 1999.
- **Neural history compressor (1991)**: Schmidhuber's hierarchy of RNNs using predictive coding and self-supervised pre-training. In 1993, solved a task requiring >1000 unfolded layers. The "P" in ChatGPT refers to this pre-training concept.
- **Adversarial networks (1991)**: Schmidhuber's "artificial curiosity" — two networks in a zero-sum game. Principle reused in GANs (2014).
- **Deep belief networks (2006)**: Hinton et al. used layer-wise pre-training with restricted Boltzmann machines, optionally fine-tuned with backpropagation.
- **AlexNet (2012)**: Krizhevsky, Sutskever, and Hinton won ImageNet by a large margin over shallow methods — widely considered the start of the deep learning revolution in computer vision.
- **ResNet (2015)**: Residual neural networks solved the "degradation problem" of very deep networks (20-30+ layers). Highway networks appeared earlier the same year.
- **GANs (2014)**: Goodfellow et al. dominated generative modeling 2014–2018; eclipsed by diffusion models (DALL-E 2, Stable Diffusion, 2022).
- **GPU acceleration**: Critical enabler. Raina, Madhavan, and Ng (2009) demonstrated 70x faster training with GPUs. DanNet (2011) achieved superhuman visual recognition using GPU-trained CNNs.

## Commands and Syntax

No commands or configuration syntax — this is a historical overview. However, key architectural patterns referenced:

- **Layer-wise pre-training**: Train one layer (e.g., RBM) at a time, freeze, stack, then optionally fine-tune end-to-end with backpropagation.
- **Connectionist Temporal Classification (CTC)**: Combined with stacked LSTMs (Graves et al., 2006) for sequence labeling tasks like handwriting recognition.
- **Progressive training**: Used in Progressive GAN / StyleGAN — grow generator from small to large scale in a pyramidal fashion.

## Relationships

- **ReLU** is the standard activation function across CNNs, MLPs, and most modern deep networks.
- **Backpropagation** is the universal training algorithm; its limitations (vanishing gradients) motivated **LSTM**, **ResNets**, and **Highway Networks**.
- **CNNs** evolved from Neocognitron → LeNet → AlexNet → VGG → Inception → ResNet for vision tasks.
- **RNNs** evolved from Ising model → Amari → Jordan/Elman networks → neural history compressor → LSTM for sequence tasks.
- **Self-supervised pre-training** (neural history compressor, 1991) → deep belief networks (2006) → modern pre-training in transformers (GPT).
- **Adversarial training** (1991 artificial curiosity) → GANs (2014) → diffusion models (2022) for generative modeling.
- **Speech recognition** drove early industrial deep learning adoption; transitioned from GMM-HMM → DNNs → LSTMs.
- **Computer vision** drove the deep learning revolution; transitioned from handcrafted features/SVMs → CNNs.

## Exam-Relevant Points

- **GMDH (1965)** by Ivakhnenko is considered the first working deep learning algorithm; 8-layer network demonstrated in 1971.
- **Amari (1967)** published the first deep MLP trained by stochastic gradient descent.
- **Fukushima (1969)** introduced ReLU; **(1979)** introduced the Neocognitron (first CNN architecture).
- **Linnainmaa (1970)** published the modern form of backpropagation in his master's thesis; **Werbos (1982)** applied it to neural networks; **Rumelhart et al. (1986)** popularized it.
- **Hochreiter (1991)** identified the vanishing gradient problem; **LSTM (1995)** with forget gate **(1999)** became the standard RNN.
- **Hinton et al. (2006)** introduced deep belief networks with layer-wise RBM pre-training.
- **AlexNet (2012)** by Krizhevsky, Sutskever, and Hinton is the landmark ImageNet result that catalyzed the deep learning revolution.
- **ResNet (2015)** by He et al. solved the degradation problem for very deep networks using skip connections.
- **Bengio, Hinton, and LeCun** received the **2018 Turing Award** for deep learning contributions.
- **LeNet-5 (1998)** by LeCun was used by banks for check digit recognition — an early industrial CNN application.
- CNNs processed 10-20% of US checks by the early 2000s (per LeCun).
- LSTM-based speech recognition improved Google's accuracy by **49% in 2015**.
- Diffusion models eclipsed GANs for generative modeling from ~2022 onward.
