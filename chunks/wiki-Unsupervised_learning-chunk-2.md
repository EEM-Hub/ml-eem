---
source: sources/wiki-Unsupervised_learning.md
source_url: https://en.wikipedia.org/wiki/Unsupervised_learning
chunk: 2/3
---

## Neural network architectures

 

### Training

 

During the learning phase, an unsupervised network tries to mimic the data it is given and uses the error in its mimicked output to correct itself (i.e. correct its weights and biases). Sometimes the error is expressed as a low probability that the erroneous output occurs, or it might be expressed as an unstable high energy state in the network.

 

In contrast to supervised methods' dominant use of [backpropagation](./Backpropagation), unsupervised learning also employs other methods  including: Hopfield learning rule, Boltzmann learning rule, [Contrastive Divergence](./Contrastive_Divergence), [Wake Sleep](./Wake-sleep_algorithm), [Variational Inference](./Variational_Inference), [Maximum Likelihood](./Maximum_Likelihood), [Maximum A Posteriori](./Maximum_A_Posteriori), [Gibbs Sampling](./Gibbs_Sampling), and backpropagating reconstruction errors or hidden state reparameterizations. See the table below for more details.

 

### Energy

 

An energy function is a macroscopic measure of a network's activation state.  In Boltzmann machines, it plays the role of the Cost function.  This analogy with physics is inspired by Ludwig Boltzmann's analysis of a gas' macroscopic energy from the microscopic probabilities of particle motion     p ∝ ∝   e  − −  E  /  k T     {\displaystyle p\propto e^{-E/kT}}  ![{\displaystyle p\propto e^{-E/kT}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b9696fac92eaa5fede297c17fa8bb086945efd8e), where k is the Boltzmann constant and T is temperature. In the [RBM](./Restricted_Boltzmann_machine) network the relation is     p =  e  − −  E    /  Z   {\displaystyle p=e^{-E}/Z}  ![{\displaystyle p=e^{-E}/Z}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7c5acd1a54ea1654f16ad3b413693ab78c72319a),[[5]](./Unsupervised_learning#cite_note-Hinton2010-5) where     p   {\displaystyle p}  ![{\displaystyle p}](https://wikimedia.org/api/rest_v1/media/math/render/svg/81eac1e205430d1f40810df36a0edffdc367af36) and     E   {\displaystyle E}  ![{\displaystyle E}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4232c9de2ee3eec0a9c0a19b15ab92daa6223f9b) vary over every possible activation pattern and       Z =  ∑ ∑     All Patterns      e  − −  E (  pattern  )       {\displaystyle \textstyle {Z=\sum _{\scriptscriptstyle {\text{All Patterns}}}e^{-E({\text{pattern}})}}}  ![{\displaystyle \textstyle {Z=\sum _{\scriptscriptstyle {\text{All Patterns}}}e^{-E({\text{pattern}})}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b2d124436452bf4f7c46be05f2a4ec154e266c2d). To be more precise,     p ( a ) =  e  − −  E ( a )    /  Z   {\displaystyle p(a)=e^{-E(a)}/Z}  ![{\displaystyle p(a)=e^{-E(a)}/Z}](https://wikimedia.org/api/rest_v1/media/math/render/svg/749ebbae5c41727f56fbb5fbee29d6f792ccfa4f), where     a   {\displaystyle a}  ![{\displaystyle a}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ffd2487510aa438433a2579450ab2b3d557e5edc) is an activation pattern of all neurons (visible and hidden). Hence, some early neural networks bear the name Boltzmann Machine.  Paul Smolensky calls     − −  E    {\displaystyle -E\,}  ![{\displaystyle -E\,}](https://wikimedia.org/api/rest_v1/media/math/render/svg/27723660512942ff84ce2d85df2509299c698147) the *Harmony*. A network seeks low energy which is high Harmony.

 

### Networks

 

This table shows connection diagrams of various unsupervised networks, the details of which will be given in the section Comparison of Networks.  Circles are neurons and edges between them are connection weights.  As network design changes, features are added on to enable new capabilities or removed to make learning faster.  For instance, neurons change between deterministic (Hopfield) and stochastic (Boltzmann) to allow robust output, weights are removed within a layer (RBM) to hasten learning, or connections are allowed to become asymmetric (Helmholtz).

 
| Hopfield | Boltzmann | RBM | Stacked Boltzmann |
| --- | --- | --- | --- |
| A network based on magnetic domains in iron with a single self-connected layer.  It can be used as a content addressable memory. | Network is separated into 2 layers (hidden vs. visible), but still using symmetric 2-way weights.  Following Boltzmann's thermodynamics, individual  probabilities give rise to macroscopic energies. | Restricted Boltzmann Machine.  This is a Boltzmann machine where lateral connections within a layer are prohibited to make analysis tractable. | This network has multiple RBM's to encode a hierarchy of hidden features.  After a single RBM is trained, another blue hidden layer (see left RBM) is added, and the top 2 layers are trained as a red & blue RBM.  Thus the middle layers of an RBM acts as hidden or visible, depending on the training phase it is in. |

 
| Helmholtz | Autoencoder | VAE |
| --- | --- | --- |
| Instead of the bidirectional symmetric connection of the stacked Boltzmann machines, we have separate one-way connections to form a loop.  It does both generation and discrimination. | A feed forward network that aims to find a good middle layer representation of its input world.  This network is deterministic, so it is not as robust as its successor the VAE. | Applies Variational Inference to the Autoencoder.  The middle layer is a set of means & variances for Gaussian distributions.  The stochastic nature allows for more robust imagination than the deterministic autoencoder. |

 

Of the networks bearing people's names, only Hopfield worked directly with neural networks. Boltzmann and Helmholtz came before artificial neural networks, but their work in physics and physiology inspired the analytical methods that were used.

 

### History

 
| 1974 | Ising magnetic model proposed byWA Little[de]for cognition |
| --- | --- |
| 1980 | Kunihiko Fukushimaintroduces theneocognitron, which is later called aconvolutional neural network. It is mostly used in SL, but deserves a mention here. |
| 1982 | Ising variant Hopfield net described asCAMsand classifiers by John Hopfield. |
| 1983 | Ising variant Boltzmann machine with probabilistic neurons described byHinton&Sejnowskifollowing Sherington & Kirkpatrick's 1975 work. |
| 1986 | Paul Smolenskypublishes Harmony Theory, which is an RBM with practically the same Boltzmann energy function. Smolensky did not give a practical training scheme. Hinton did in mid-2000s. |
| 1995 | HochreiterandSchmidhuberintroduce theLSTMneuron for languages. |
| 1995 | Dayan & Hinton introduces Helmholtz machine |
| 2013 | Kingma, Rezende, & co. introduced Variational Autoencoders as Bayesian graphical probability network, with neural nets as components. |

 

### Specific networks

 

Here, we highlight some characteristics of select networks.  The details of each are given in the comparison table below.

   [Hopfield Network](./Hopfield_Network) Ferromagnetism inspired Hopfield networks.  A neuron corresponds to an iron domain with binary magnetic moments Up and Down, and neural connections correspond to the domain's influence on each other.  Symmetric connections enable a global energy formulation. During inference the network updates each state using the standard activation step function. Symmetric weights and the right energy functions guarantees convergence to a stable activation pattern.  Asymmetric weights are difficult to analyze.  Hopfield nets are used as Content Addressable Memories (CAM). [Boltzmann Machine](./Boltzmann_Machine) These are stochastic Hopfield nets. Their state value is sampled from this [pdf](./Probability_density_function) as follows: suppose a binary neuron fires with the Bernoulli probability p(1) = 1/3 and rests with p(0) = 2/3. One samples from it by taking a *uniformly* distributed random number y, and plugging it into the inverted [cumulative distribution function](./Cumulative_distribution_function), which in this case is the step function thresholded at 2/3. The inverse function = { 0 if x <= 2/3, 1 if x > 2/3 }. Sigmoid Belief Net Introduced by Radford Neal in 1992, this network applies ideas from probabilistic graphical models to neural networks.  A key difference is that nodes in graphical models have pre-assigned meanings, whereas Belief Net neurons' features are determined after training. The network is a sparsely connected directed acyclic graph composed of binary stochastic neurons.  The learning rule comes from Maximum Likelihood on p(X):  Δwij     ∝ ∝    {\displaystyle \propto }  ![{\displaystyle \propto }](https://wikimedia.org/api/rest_v1/media/math/render/svg/0e3a55007ba2f092d6cafe6d33598e0608b81150) sj * (si - pi), where pi = 1 / ( 1 + eweighted inputs into neuron i ).  sj's are activations from an unbiased sample of the posterior distribution and this is problematic due to the Explaining Away problem raised by Judea Perl.  [Variational Bayesian methods](./Variational_Bayesian_methods) uses a surrogate posterior and blatantly disregard this complexity. [Deep Belief Network](./Deep_Belief_Network) Introduced by Hinton, this network is a hybrid of RBM and Sigmoid Belief Network.  The top 2 layers is an RBM and the second layer downwards form a sigmoid belief network.  One trains it by the [stacked RBM](./Stacked_Restricted_Boltzmann_Machine) method and then throw away the recognition weights below the top RBM.  As of 2009, 3-4 layers seems to be the optimal depth.[[6]](./Unsupervised_learning#cite_note-HintonMlss2009-6) [Helmholtz machine](./Helmholtz_machine) These are early inspirations for the Variational Auto Encoders. Its 2 networks combined into one—forward weights operates recognition and backward weights implements imagination. It is perhaps the first network to do both. Helmholtz did not work in machine learning but he inspired the view of "statistical inference engine whose function is to infer probable causes of sensory input".[[7]](./Unsupervised_learning#cite_note-nc95-7) the stochastic binary neuron outputs a probability that its state is 0 or 1. The data input is normally not considered a layer, but in the Helmholtz machine generation mode, the data layer receives input from the middle layer and has separate weights for this purpose, so it is considered a layer. Hence this network has 3 layers. [Variational autoencoder](./Variational_autoencoder) These are inspired by Helmholtz machines and combines probability network with neural networks. An Autoencoder is a 3-layer CAM network, where the middle layer is supposed to be some internal representation of input patterns. The encoder neural network is a probability distribution qφ(z given x) and the decoder network is pθ(x given z). The weights are named phi & theta rather than W and V as in Helmholtz—a cosmetic difference. These 2 networks here can be fully connected, or use another NN scheme.  

### Comparison of networks

 
|  | Hopfield | Boltzmann | RBM | Stacked RBM | Helmholtz | Autoencoder | VAE |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Usage & notables | CAM, traveling salesman problem | CAM. The freedom of connections makes this network difficult to analyze. | pattern recognition. used in MNIST digits and speech. | recognition & imagination.   trained with unsupervised pre-training and/or supervised fine tuning. | imagination, mimicry | language: creative writing, translation.  vision: enhancing blurry images | generate realistic data |
| Neuron | deterministic binary state. Activation = { 0 (or -1) if x is negative, 1 otherwise } | stochastic binary Hopfield neuron | ← same. (extended to real-valued in mid 2000s) | ← same | ← same | language: LSTM. vision: local receptive fields. usually real valued relu activation. | middle layer neurons encode means & variances for Gaussians.  In run mode (inference), the output of the middle layer are sampled values from the Gaussians. |
| Connections | 1-layer with symmetric weights. No self-connections. | 2-layers. 1-hidden & 1-visible. symmetric weights. | ← same.no lateral connections within a layer. | top layer is undirected, symmetric.  other layers are 2-way, asymmetric. | 3-layers: asymmetric weights. 2 networks combined into 1. | 3-layers. The input is considered a layer even though it has no inbound weights. recurrent layers for NLP. feedforward convolutions for vision. input & output have the same neuron counts. | 3-layers: input, encoder, distribution sampler decoder. the sampler is not considered a layer |
| Inference & energy | Energy is given by Gibbs probability measure:E=−12∑i,jwijsisj+∑iθisi{\displaystyle E=-{\frac {1}{2}}\sum _{i,j}{w_{ij}{s_{i}}{s_{j}}}+\sum _{i}{\theta _{i}}{s_{i}}} | ← same | ← same |  | minimize KL divergence | inference is only feed-forward. previous UL networks ran forwards AND backwards | minimize error = reconstruction error - KLD |
| Training | Δwij= si*sj, for +1/-1 neuron | Δwij= e*(pij- p'ij). This is derived from minimizing KLD. e = learning rate, p' = predicted and p = actual distribution. | Δwij= e*( < vihj>data- < vihj>equilibrium).  This is a form of contrastive divergence w/ Gibbs Sampling.  "<>" are expectations. | ← similar. train 1-layer at a time.  approximate equilibrium state with a 3-segment pass.  no back propagation. | wake-sleep 2 phase training | back propagate the reconstruction error | reparameterize hidden state for backprop |
| Strength | resembles physical systems so it inherits their equations | ← same. hidden neurons act as internal representatation of the external world | faster more practical training scheme than Boltzmann machines | trains quickly.  gives hierarchical layer of features | mildly anatomical. analyzable w/ information theory & statistical mechanics |  |  |
| Weakness |  | hard to train due to lateral connections | equilibrium requires too many iterations | integer & real-valued neurons are more complicated. |  |  |  |

 

### Hebbian Learning, ART, SOM

 

The classical example of unsupervised learning in the study of neural networks is [Donald Hebb](./Donald_Hebb)'s principle, that is, neurons that fire together wire together.[[8]](./Unsupervised_learning#cite_note-Buhmann-8) In [Hebbian learning](./Hebbian_learning), the connection is reinforced irrespective of an error, but is exclusively a function of the coincidence between action potentials between the two neurons.[[9]](./Unsupervised_learning#cite_note-Comesana-9) A similar version that modifies synaptic weights takes into account the time between the action potentials ([spike-timing-dependent plasticity](./Spike-timing-dependent_plasticity) or STDP). Hebbian Learning has been hypothesized to underlie a range of cognitive functions, such as [pattern recognition](./Pattern_recognition) and experiential learning.

 

Among [neural network](./Artificial_neural_network) models, the [self-organizing map](./Self-organizing_map) (SOM) and [adaptive resonance theory](./Adaptive_resonance_theory) (ART) are commonly used in unsupervised learning algorithms. The SOM is a topographic organization in which nearby locations in the map represent inputs with similar properties. The ART model allows the number of clusters to vary with problem size and lets the user control the degree of similarity between members of the same clusters by means of a user-defined constant called the vigilance parameter. ART networks are used for many pattern recognition tasks, such as [automatic target recognition](./Automatic_target_recognition) and seismic signal processing.[[10]](./Unsupervised_learning#cite_note-Carpenter-10)

 


