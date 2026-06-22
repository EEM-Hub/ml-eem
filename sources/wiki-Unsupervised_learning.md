---
source: https://en.wikipedia.org/wiki/Unsupervised_learning
fetched: 2026-06-21
---

Paradigm in machine learning that uses no classification labels 
| Part of a series on |
| --- |
| Machine learninganddata mining |
| ParadigmsSupervised learningUnsupervised learningSemi-supervised learningSelf-supervised learningReinforcement learningMeta-learningOnline learningBatch learningCurriculum learningRule-based learningNeuro-symbolic AINeuromorphic engineeringQuantum machine learning |
| ProblemsClassificationGenerative modelingRegressionClusteringDimensionality reductionDensity estimationAnomaly detectionData cleaningAutoMLAssociation rulesSemantic analysisStructured predictionFeature engineeringFeature learningLearning to rankGrammar inductionOntology learningMultimodal learning |
| Supervised learning(classification•regression)Apprenticeship learningDecision treesEnsemblesBaggingBoostingRandom forestk-NNLinear regressionNaive BayesArtificial neural networksLogistic regressionPerceptronRelevance vector machine (RVM)Support vector machine (SVM) |
| ClusteringBIRCHCUREHierarchicalk-meansFuzzyExpectation–maximization (EM)DBSCANOPTICSMean shift |
| Dimensionality reductionFactor analysisCCAICALDANMFPCAPGDt-SNESDL |
| Structured predictionGraphical modelsBayes netConditional random fieldHidden Markov |
| Anomaly detectionRANSACk-NNLocal outlier factorIsolation forest |
| Neural networksAutoencoderDeep learningFeedforward neural networkRecurrent neural networkLSTMGRUESNreservoir computingBoltzmann machineRestrictedGANDiffusion modelSOMConvolutional neural networkU-NetLeNetAlexNetDeepDreamNeural fieldNeural radiance fieldPhysics-informed neural networksTransformerVisionMambaSpiking neural networkMemtransistorElectrochemical RAM(ECRAM) |
| Reinforcement learningQ-learningPolicy gradientSARSATemporal difference (TD)Multi-agentSelf-play |
| Learning with humansActive learningCrowdsourcingHuman-in-the-loopMechanistic interpretabilityRLHF |
| Model diagnosticsCoefficient of determinationConfusion matrixLearning curveROC curve |
| Mathematical foundationsKernel machinesBias–variance tradeoffComputational learning theoryEmpirical risk minimizationOccam learningPAC learningStatistical learningVC theoryTopological deep learning |
| Journals and conferencesAAAICVPRECCVECML PKDDEMNLPICCVNeurIPSICMLICLRIJCAIMLJMLR |
| Related articlesGlossary of artificial intelligenceList of datasets for machine-learning researchList of datasets in computer vision and image processingOutline of machine learning |
| vte |

 

**Unsupervised learning** is a framework in [machine learning](./Machine_learning) where, in contrast to [supervised learning](./Supervised_learning), algorithms learn patterns exclusively from unlabeled data.[[1]](./Unsupervised_learning#cite_note-WeiWu-1) Other frameworks in the spectrum of supervisions include [weak- or semi-supervision](./Weak_supervision), where a small portion of the data is tagged, and [self-supervision](./Self-supervised_learning). Some researchers consider self-supervised learning a form of unsupervised learning.[[2]](./Unsupervised_learning#cite_note-2)

 

Conceptually, unsupervised learning divides into the aspects of data, training, algorithm, and downstream applications. Typically, the dataset is harvested cheaply "in the wild", such as massive [text corpus](./Text_corpus) obtained by [web crawling](./Web_crawler), with only minor filtering (such as [Common Crawl](./Common_Crawl)). This compares favorably to supervised learning, where the dataset (such as the [ImageNet1000](./ImageNet)) is typically constructed manually, which is much more expensive.

 

There are algorithms designed specifically for unsupervised learning, such as [clustering algorithms](./Cluster_analysis) like [k-means](./K-means_clustering), [dimensionality reduction](./Dimensionality_reduction) techniques like [principal component analysis (PCA)](./Principal_component_analysis), [Boltzmann machine learning](./Boltzmann_machine), and [autoencoders](./Autoencoder). After the rise of deep learning, most large-scale unsupervised learning has been done by training general-purpose neural network architectures by [gradient descent](./Gradient_descent), adapted to performing unsupervised learning by designing an appropriate training procedure.

 

Sometimes a trained model can be used as-is, but more often they are modified for downstream applications. For example, the generative pretraining method trains a model to generate a textual dataset, before finetuning it for other applications, such as text classification.[[3]](./Unsupervised_learning#cite_note-gpt1paper-3)[[4]](./Unsupervised_learning#cite_note-4) As another example, autoencoders are trained to produce [good features](./Feature_learning), which can then be used as a module for other models, such as in a [latent diffusion model](./Latent_diffusion_model).

 

## Tasks

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/9/90/Task-guidance.png/330px-Task-guidance.png)](./File:Task-guidance.png)Tendency for a task to employ supervised vs. unsupervised methods. Task names straddling circle boundaries is intentional. It shows that the classical division of imaginative tasks (left) employing unsupervised methods is blurred in today's learning schemes.

Tasks are often categorized as [discriminative](./Discriminative_model) (recognition) or [generative](./Generative_model) (imagination).  Often but not always, discriminative tasks use supervised methods and generative tasks use unsupervised (see [Venn diagram](./Venn_diagram)); however, the separation is very hazy.  For example, object recognition favors supervised learning but unsupervised learning can also cluster objects into groups.  Furthermore, as progress marches onward, some tasks employ both methods, and some tasks swing from one to another.  For example, image recognition started off as heavily supervised, but became hybrid by employing unsupervised pre-training, and then moved towards supervision again with the advent of [dropout](./Dilution_(neural_networks)), [ReLU](./Rectifier_(neural_networks)), and [adaptive learning rates](./Learning_rate).

 

A typical generative task is as follows. At each step, a datapoint is sampled from the dataset, and part of the data is removed, and the model must infer the removed part. This is particularly clear for the [denoising autoencoders](./Autoencoder) and [BERT](./BERT_(language_model)).

 

 

 

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

 

## Probabilistic methods

 

Two of the main methods used in unsupervised learning are [principal component](./Principal_component_analysis) and [cluster analysis](./Cluster_analysis). Cluster analysis is used in unsupervised learning to group, or segment, datasets with shared attributes in order to extrapolate algorithmic relationships.[[11]](./Unsupervised_learning#cite_note-tds-ul-11) Cluster analysis is a branch of [machine learning](./Machine_learning) that groups the data that has not been [labelled](./Labeled_data), classified or categorized. Instead of responding to feedback, cluster analysis identifies commonalities in the data and reacts based on the presence or absence of such commonalities in each new piece of data. This approach helps detect anomalous data points that do not fit into either group.

 

A central application of unsupervised learning is in the field of [density estimation](./Density_estimation) in [statistics](./Statistics),[[12]](./Unsupervised_learning#cite_note-JordanBishop2004-12) though unsupervised learning encompasses many other domains involving summarizing and explaining data features. It can be contrasted with supervised learning by saying that whereas supervised learning intends to infer a [conditional probability distribution](./Conditional_probability_distribution)  conditioned on the label  of input data; unsupervised learning intends to infer an [a priori probability](./A_priori_probability) distribution .

 

### Approaches

 

Some of the most common algorithms used in unsupervised learning include: (1) Clustering, (2) Anomaly detection, (3) Approaches for learning latent variable models. Each approach uses several methods as follows:

 
- [Clustering](./Data_clustering) methods include: [hierarchical clustering](./Hierarchical_clustering),[[13]](./Unsupervised_learning#cite_note-Hastie-13) [k-means](./K-means),[[14]](./Unsupervised_learning#cite_note-tds-kmeans-14) [mixture models](./Mixture_models), [model-based clustering](./Model-based_clustering), [DBSCAN](./DBSCAN), and [OPTICS algorithm](./OPTICS_algorithm)
- [Anomaly detection](./Anomaly_detection) methods include: [local outlier factor](./Local_outlier_factor), and [isolation forest](./Isolation_forest)
- Approaches for learning [latent variable models](./Latent_variable_model) such as [expectation–maximization algorithm](./Expectation–maximization_algorithm) (EM), [method of moments](./Method_of_moments_(statistics)), and [blind signal separation](./Blind_signal_separation) techniques (principal component analysis, [independent component analysis](./Independent_component_analysis), [non-negative matrix factorization](./Non-negative_matrix_factorization), [singular value decomposition](./Singular_value_decomposition))

 

### Method of moments

 

One of the statistical approaches for unsupervised learning is the [method of moments](./Method_of_moments_(statistics)). In the method of moments, the unknown parameters (of interest) in the model are related to the moments of one or more random variables, and thus, these unknown parameters can be estimated given the moments. The moments are usually estimated from samples empirically. The basic moments are first and second order moments. For a random vector, the first order moment is the [mean](./Mean) vector, and the second order moment is the [covariance matrix](./Covariance_matrix) (when the mean is zero). Higher order moments are usually represented using [tensors](./Tensors) which are the generalization of matrices to higher orders as multi-dimensional arrays.

 

In particular, the method of moments is shown to be effective in learning the parameters of [latent variable models](./Latent_variable_model). Latent variable models are statistical models where in addition to the observed variables, a set of latent variables also exists which is not observed. A highly practical example of latent variable models in machine learning is the [topic modeling](./Topic_modeling) which is a statistical model for generating the words (observed variables) in the document based on the topic (latent variable) of the document. In the topic modeling, the words in the document are generated according to different statistical parameters when the topic of the document is changed. It is shown that method of moments (tensor decomposition techniques) consistently recover the parameters of a large class of latent variable models under some assumptions.[[15]](./Unsupervised_learning#cite_note-TensorLVMs-15)

 

The [Expectation–maximization algorithm](./Expectation–maximization_algorithm) (EM) is also one of the most practical methods for learning latent variable models. However, it can get stuck in local optima, and it is not guaranteed that the algorithm will converge to the true unknown parameters of the model. In contrast, for the method of moments, the global convergence is guaranteed under some conditions.

 

## See also

 
- [Automated machine learning](./Automated_machine_learning)
- [Cluster analysis](./Cluster_analysis)
- [Model-based clustering](./Model-based_clustering)
- [Anomaly detection](./Anomaly_detection)
- [Expectation–maximization algorithm](./Expectation–maximization_algorithm)
- [Generative topographic map](./Generative_topographic_map)
- [Meta-learning (computer science)](./Meta-learning_(computer_science))
- [Multivariate analysis](./Multivariate_analysis)
- [Radial basis function network](./Radial_basis_function_network)
- [Weak supervision](./Weak_supervision)

 

## References

  
1. [↑](./Unsupervised_learning#cite_ref-WeiWu_1-0) Wu, Wei. ["Unsupervised Learning"](https://na.uni-tuebingen.de/ex/ml_seminar_ss2022/Unsupervised_Learning%20Final.pdf) (PDF). [Archived](https://web.archive.org/web/20240414213810/https://na.uni-tuebingen.de/ex/ml_seminar_ss2022/Unsupervised_Learning%20Final.pdf) (PDF) from the original on 14 April 2024. Retrieved 26 April 2024.
2. [↑](./Unsupervised_learning#cite_ref-2) Liu, Xiao; Zhang, Fanjin; Hou, Zhenyu; Mian, Li; Wang, Zhaoyu; Zhang, Jing; Tang, Jie (2021). "Self-supervised Learning: Generative or Contrastive". *IEEE Transactions on Knowledge and Data Engineering*: 1. [arXiv](./ArXiv_(identifier)):[2006.08218](https://arxiv.org/abs/2006.08218). [doi](./Doi_(identifier)):[10.1109/TKDE.2021.3090866](https://doi.org/10.1109%2FTKDE.2021.3090866). [ISSN](./ISSN_(identifier)) [1041-4347](https://search.worldcat.org/issn/1041-4347).
3. [↑](./Unsupervised_learning#cite_ref-gpt1paper_3-0) Radford, Alec; Narasimhan, Karthik; Salimans, Tim; Sutskever, Ilya (11 June 2018). ["Improving Language Understanding by Generative Pre-Training"](https://cdn.openai.com/research-covers/language-unsupervised/language_understanding_paper.pdf) (PDF). [OpenAI](./OpenAI). p. 12. [Archived](https://web.archive.org/web/20210126024542/https://cdn.openai.com/research-covers/language-unsupervised/language_understanding_paper.pdf) (PDF) from the original on 26 January 2021. Retrieved 23 January 2021.
4. [↑](./Unsupervised_learning#cite_ref-4) Li, Zhuohan; Wallace, Eric; Shen, Sheng; Lin, Kevin; Keutzer, Kurt; Klein, Dan; Gonzalez, Joey (2020-11-21). ["Train Big, Then Compress: Rethinking Model Size for Efficient Training and Inference of Transformers"](https://proceedings.mlr.press/v119/li20m.html). *Proceedings of the 37th International Conference on Machine Learning*. PMLR: 5958–5968.
5. [↑](./Unsupervised_learning#cite_ref-Hinton2010_5-0) Hinton, G. (2012). ["A Practical Guide to Training Restricted Boltzmann Machines"](http://www.cs.utoronto.ca/~hinton/absps/guideTR.pdf) (PDF). *Neural Networks: Tricks of the Trade*. Lecture Notes in Computer Science. Vol. 7700. Springer. pp. 599–619. [doi](./Doi_(identifier)):[10.1007/978-3-642-35289-8_32](https://doi.org/10.1007%2F978-3-642-35289-8_32). [ISBN](./ISBN_(identifier)) [978-3-642-35289-8](./Special:BookSources/978-3-642-35289-8). [Archived](https://web.archive.org/web/20220903215809/http://www.cs.utoronto.ca/~hinton/absps/guideTR.pdf) (PDF) from the original on 2022-09-03. Retrieved 2022-11-03.
6. [↑](./Unsupervised_learning#cite_ref-HintonMlss2009_6-0) ["Deep Belief Nets"](https://videolectures.net/mlss09uk_hinton_dbn) (video). September 2009. [Archived](https://web.archive.org/web/20220308022539/http://videolectures.net/mlss09uk_hinton_dbn/) from the original on 2022-03-08. Retrieved 2022-03-27.
7. [↑](./Unsupervised_learning#cite_ref-nc95_7-0) [Peter, Dayan](./Peter_Dayan); [Hinton, Geoffrey E.](./Geoffrey_Hinton); [Neal, Radford M.](./Radford_M._Neal); [Zemel, Richard S.](./Richard_Zemel) (1995). "The Helmholtz machine". *Neural Computation*. **7** (5): 889–904. [doi](./Doi_(identifier)):[10.1162/neco.1995.7.5.889](https://doi.org/10.1162%2Fneco.1995.7.5.889). [hdl](./Hdl_(identifier)):[21.11116/0000-0002-D6D3-E](https://hdl.handle.net/21.11116%2F0000-0002-D6D3-E). [PMID](./PMID_(identifier)) [7584891](https://pubmed.ncbi.nlm.nih.gov/7584891). [S2CID](./S2CID_(identifier)) [1890561](https://api.semanticscholar.org/CorpusID:1890561). [![Closed access icon](//upload.wikimedia.org/wikipedia/commons/thumb/0/0e/Closed_Access_logo_transparent.svg/20px-Closed_Access_logo_transparent.svg.png)](./Paywall)
8. [↑](./Unsupervised_learning#cite_ref-Buhmann_8-0) Buhmann, J.; Kuhnel, H. (1992). "Unsupervised and supervised data clustering with competitive neural networks". *[Proceedings 1992] IJCNN International Joint Conference on Neural Networks*. Vol. 4. IEEE. pp. 796–801. [doi](./Doi_(identifier)):[10.1109/ijcnn.1992.227220](https://doi.org/10.1109%2Fijcnn.1992.227220). [ISBN](./ISBN_(identifier)) [0780305590](./Special:BookSources/0780305590). [S2CID](./S2CID_(identifier)) [62651220](https://api.semanticscholar.org/CorpusID:62651220).
9. [↑](./Unsupervised_learning#cite_ref-Comesana_9-0) Comesaña-Campos, Alberto; Bouza-Rodríguez, José Benito (June 2016). "An application of Hebbian learning in the design process decision-making". *Journal of Intelligent Manufacturing*. **27** (3): 487–506. [doi](./Doi_(identifier)):[10.1007/s10845-014-0881-z](https://doi.org/10.1007%2Fs10845-014-0881-z). [ISSN](./ISSN_(identifier)) [0956-5515](https://search.worldcat.org/issn/0956-5515). [S2CID](./S2CID_(identifier)) [207171436](https://api.semanticscholar.org/CorpusID:207171436).
10. [↑](./Unsupervised_learning#cite_ref-Carpenter_10-0) Carpenter, G.A. & Grossberg, S. (1988). ["The ART of adaptive pattern recognition by a self-organizing neural network"](https://web.archive.org/web/20180516131553/http://www.cns.bu.edu/Profiles/Grossberg/CarGro1988Computer.pdf) (PDF). *Computer*. **21** (3): 77–88. [doi](./Doi_(identifier)):[10.1109/2.33](https://doi.org/10.1109%2F2.33). [S2CID](./S2CID_(identifier)) [14625094](https://api.semanticscholar.org/CorpusID:14625094). Archived from [the original](http://www.cns.bu.edu/Profiles/Grossberg/CarGro1988Computer.pdf) (PDF) on 2018-05-16. Retrieved 2013-09-16.
11. [↑](./Unsupervised_learning#cite_ref-tds-ul_11-0) Roman, Victor (2019-04-21). ["Unsupervised Machine Learning: Clustering Analysis"](https://towardsdatascience.com/unsupervised-machine-learning-clustering-analysis-d40f2b34ae7e). *Medium*. [Archived](https://web.archive.org/web/20200821132257/https://towardsdatascience.com/unsupervised-machine-learning-clustering-analysis-d40f2b34ae7e) from the original on 2020-08-21. Retrieved 2019-10-01.
12. [↑](./Unsupervised_learning#cite_ref-JordanBishop2004_12-0) Jordan, Michael I.; Bishop, Christopher M. (2004). "7. Intelligent Systems §Neural Networks". In Tucker, Allen B. (ed.). [*Computer Science Handbook*](https://www.taylorfrancis.com/books/mono/10.1201/9780203494455/computer-science-handbook-allen-tucker) (2nd ed.). Chapman & Hall/CRC Press. [doi](./Doi_(identifier)):[10.1201/9780203494455](https://doi.org/10.1201%2F9780203494455). [ISBN](./ISBN_(identifier)) [1-58488-360-X](./Special:BookSources/1-58488-360-X). [Archived](https://web.archive.org/web/20221103234201/https://www.taylorfrancis.com/books/mono/10.1201/9780203494455/computer-science-handbook-allen-tucker) from the original on 2022-11-03. Retrieved 2022-11-03.
13. [↑](./Unsupervised_learning#cite_ref-Hastie_13-0) [Hastie, Tibshirani & Friedman 2009](./Unsupervised_learning#CITEREFHastieTibshiraniFriedman2009), pp. 485–586
14. [↑](./Unsupervised_learning#cite_ref-tds-kmeans_14-0) Garbade, Dr Michael J. (2018-09-12). ["Understanding K-means Clustering in Machine Learning"](https://towardsdatascience.com/understanding-k-means-clustering-in-machine-learning-6a6e67336aa1). *Medium*. [Archived](https://web.archive.org/web/20190528183913/https://towardsdatascience.com/understanding-k-means-clustering-in-machine-learning-6a6e67336aa1) from the original on 2019-05-28. Retrieved 2019-10-31.
15. [↑](./Unsupervised_learning#cite_ref-TensorLVMs_15-0) Anandkumar, Animashree; Ge, Rong; Hsu, Daniel; Kakade, Sham; Telgarsky, Matus (2014). ["Tensor Decompositions for Learning Latent Variable Models"](http://www.jmlr.org/papers/volume15/anandkumar14b/anandkumar14b.pdf) (PDF). *Journal of Machine Learning Research*. **15**: 2773–2832. [arXiv](./ArXiv_(identifier)):[1210.7559](https://arxiv.org/abs/1210.7559). [Bibcode](./Bibcode_(identifier)):[2012arXiv1210.7559A](https://ui.adsabs.harvard.edu/abs/2012arXiv1210.7559A). [Archived](https://web.archive.org/web/20150320201108/http://jmlr.org/papers/volume15/anandkumar14b/anandkumar14b.pdf) (PDF) from the original on 2015-03-20. Retrieved 2015-04-10.

 

## Further reading

  
- Bousquet, O.; [von Luxburg, U.](./Ulrike_von_Luxburg); Raetsch, G., eds. (2004). [*Advanced Lectures on Machine Learning*](https://archive.org/details/springer_10.1007-b100712). Springer. [ISBN](./ISBN_(identifier)) [978-3540231226](./Special:BookSources/978-3540231226).
- [Duda, Richard O.](./Richard_O._Duda); [Hart, Peter E.](./Peter_E._Hart); Stork, David G. (2001). "Unsupervised Learning and Clustering". [*Pattern classification*](./Pattern_classification) (2nd ed.). Wiley. [ISBN](./ISBN_(identifier)) [0-471-05669-3](./Special:BookSources/0-471-05669-3).
- [Hastie, Trevor](./Trevor_Hastie); [Tibshirani, Robert](./Robert_Tibshirani); Friedman, Jerome (2009). ["Unsupervised Learning"](https://link.springer.com/chapter/10.1007/978-0-387-84858-7_14). *The Elements of Statistical Learning: Data mining, Inference, and Prediction*. Springer. pp. 485–586. [doi](./Doi_(identifier)):[10.1007/978-0-387-84858-7_14](https://doi.org/10.1007%2F978-0-387-84858-7_14). [ISBN](./ISBN_(identifier)) [978-0-387-84857-0](./Special:BookSources/978-0-387-84857-0). [Archived](https://web.archive.org/web/20221103234204/https://link.springer.com/chapter/10.1007/978-0-387-84858-7_14) from the original on 2022-11-03. Retrieved 2022-11-03.
- [Hinton, Geoffrey](./Geoffrey_Hinton); [Sejnowski, Terrence J.](./Terrence_J._Sejnowski), eds. (1999). *Unsupervised Learning: Foundations of Neural Computation*. [MIT Press](./MIT_Press). [ISBN](./ISBN_(identifier)) [0-262-58168-X](./Special:BookSources/0-262-58168-X).

  
| vteDifferentiable computing |
| --- |
| General | Differentiable programmingInformation geometryStatistical manifoldAutomatic differentiationNeuromorphic computingPattern recognitionRicci calculusComputational learning theoryInductive bias |
| Hardware | IPUTPUVPUMemristorSpiNNaker |
| Software libraries | TensorFlowPyTorchKerasscikit-learnTheanoJAXFlux.jlMindSpore |
| PortalsComputer programmingTechnology |

 
| Authority control databases | GND |
| --- | --- |