---
source: sources/wiki-Generative_adversarial_network.md
source_url: https://en.wikipedia.org/wiki/Generative_adversarial_network
chunk: 1/7
---

Deep learning method Not to be confused with [Adversarial machine learning](./Adversarial_machine_learning), [GaN](./GaN), or [Generic Access Network](./Generic_Access_Network). 

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/8/83/Generative_adversarial_network.svg/250px-Generative_adversarial_network.svg.png)](./File:Generative_adversarial_network.svg)An illustration of how a GAN works 
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

 

A **generative adversarial network** (**GAN**) is a class of [machine learning](./Machine_learning) frameworks and a prominent framework for approaching [generative artificial intelligence](./Generative_artificial_intelligence). The concept was initially developed by [Ian Goodfellow](./Ian_Goodfellow) and his colleagues in June 2014.[[1]](./Generative_adversarial_network#cite_note-GANnips-1) In a GAN, two [neural networks](./Neural_network) compete with each other in the form of a [zero-sum game](./Zero-sum_game), where one agent's gain is another agent's loss.

 

Given a training set, this technique learns to generate new data with the same statistics as the training set. For example, a GAN trained on photographs can generate new photographs that look at least superficially authentic to human observers, having many realistic characteristics. Though originally proposed as a form of [generative model](./Generative_model) for [unsupervised learning](./Unsupervised_learning), GANs have also proved useful for [semi-supervised learning](./Semi-supervised_learning),[[2]](./Generative_adversarial_network#cite_note-ITT_GANs-2) fully [supervised learning](./Supervised_learning),[[3]](./Generative_adversarial_network#cite_note-3) and [reinforcement learning](./Reinforcement_learning).[[4]](./Generative_adversarial_network#cite_note-4)

 

The core idea of a GAN is based on the "indirect" training through the discriminator, another neural network that can tell how "realistic" the input seems, which itself is also being updated dynamically.[[5]](./Generative_adversarial_network#cite_note-5) This means that the generator is not trained to minimize the distance to a specific image, but rather to fool the discriminator. This enables the model to learn in an unsupervised manner.

 

GANs are similar to [mimicry](./Mimicry) in [evolutionary biology](./Evolutionary_biology), with an [evolutionary arms race](./Evolutionary_arms_race) between both networks.

 

## Definition

 

### Mathematical

The original GAN is defined as the following [game](./Game_theory):[[1]](./Generative_adversarial_network#cite_note-GANnips-1)

 

Each [probability space](./Probability_space)     ( Ω Ω  ,  μ μ   ref   )   {\displaystyle (\Omega ,\mu _{\text{ref}})}  ![{\displaystyle (\Omega ,\mu _{\text{ref}})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b34df6941a14695eaf4145d9113f594c7aa8ca5c) defines a GAN game.

 

There are 2 players: generator and discriminator.

 

The generator's [strategy set](./Strategy_(game_theory)) is       P   ( Ω Ω  )   {\displaystyle {\mathcal {P}}(\Omega )}  ![{\displaystyle {\mathcal {P}}(\Omega )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b95df45bc7d7faec1a5b88437d4b26b8a16ad108), the set of all probability measures      μ μ   G     {\displaystyle \mu _{G}}  ![{\displaystyle \mu _{G}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/dda577f83b0f673b3c59652dfcd8c195b965030f) on     Ω Ω    {\displaystyle \Omega }  ![{\displaystyle \Omega }](https://wikimedia.org/api/rest_v1/media/math/render/svg/24b0d5ca6f381068d756f6337c08e0af9d1eeb6f).

 

The discriminator's strategy set is the set of [Markov kernels](./Markov_kernel)      μ μ   D   : Ω Ω  → →    P   [ 0 , 1 ]   {\displaystyle \mu _{D}:\Omega \to {\mathcal {P}}[0,1]}  ![{\displaystyle \mu _{D}:\Omega \to {\mathcal {P}}[0,1]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/dce97271df1c30e57ae96f72c566661f1bae9dad), where       P   [ 0 , 1 ]   {\displaystyle {\mathcal {P}}[0,1]}  ![{\displaystyle {\mathcal {P}}[0,1]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/23bc6194efec9e3aaf67b5270e6b8cbc3834d99e) is the set of probability measures on     [ 0 , 1 ]   {\displaystyle [0,1]}  ![{\displaystyle [0,1]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/738f7d23bb2d9642bab520020873cccbef49768d).

 

The GAN game is a [zero-sum game](./Zero-sum_game), with objective function    L (  μ μ   G   ,  μ μ   D   ) :=  E  x ∼ ∼   μ μ   ref   , y ∼ ∼   μ μ   D   ( x )   ⁡ ⁡  [ ln ⁡ ⁡  y ] +  E  x ∼ ∼   μ μ   G   , y ∼ ∼   μ μ   D   ( x )   ⁡ ⁡  [ ln ⁡ ⁡  ( 1 − −  y ) ] .   {\displaystyle L(\mu _{G},\mu _{D}):=\operatorname {E} _{x\sim \mu _{\text{ref}},y\sim \mu _{D}(x)}[\ln y]+\operatorname {E} _{x\sim \mu _{G},y\sim \mu _{D}(x)}[\ln(1-y)].}  ![{\displaystyle L(\mu _{G},\mu _{D}):=\operatorname {E} _{x\sim \mu _{\text{ref}},y\sim \mu _{D}(x)}[\ln y]+\operatorname {E} _{x\sim \mu _{G},y\sim \mu _{D}(x)}[\ln(1-y)].}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8699f270ae2bc55554c5854efa24a5812f38ec85)
The generator aims to minimize the objective, and the discriminator aims to maximize the objective.

 

The generator's task is to approach      μ μ   G   ≈ ≈   μ μ   ref     {\displaystyle \mu _{G}\approx \mu _{\text{ref}}}  ![{\displaystyle \mu _{G}\approx \mu _{\text{ref}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2c9f7c06f78d82aaa7be749a2e9407be06756836), that is, to match its own output distribution as closely as possible to the reference distribution. The discriminator's task is to output a value close to 1 when the input appears to be from the reference distribution, and to output a value close to 0 when the input looks like it came from the generator distribution.

 

### In practice

 

The [*generative* network](./Generative_model) generates candidates while the [*discriminative* network](./Discriminative_model) evaluates them.[[1]](./Generative_adversarial_network#cite_note-GANnips-1) This creates a contest based on data distributions, where the generator learns to map from a [latent space](./Latent_space) to the true data distribution, aiming to produce candidates that the discriminator cannot distinguish from real data. The discriminator's goal is to correctly identify these candidates, but as the generator improves, its task becomes more challenging, increasing the discriminator's error rate.[[1]](./Generative_adversarial_network#cite_note-GANnips-1)[[6]](./Generative_adversarial_network#cite_note-6)

 

A known dataset serves as the initial training data for the discriminator. Training involves presenting it with samples from the training dataset until it achieves acceptable accuracy. The generator is trained based on whether it succeeds in fooling the discriminator. Typically, the generator is seeded with randomized input that is sampled from a predefined [latent space](./Latent_space) (e.g. a [multivariate normal distribution](./Multivariate_normal_distribution)). Thereafter, candidates synthesized by the generator are evaluated by the discriminator. Independent [backpropagation](./Backpropagation) procedures are applied to both networks so that the generator produces better samples, while the discriminator becomes more skilled at flagging synthetic samples.[[7]](./Generative_adversarial_network#cite_note-OpenAI_com-7) When used for image generation, the generator is typically a [deconvolutional neural network](./Deconvolutional_neural_network), and the discriminator is a [convolutional neural network](./Convolutional_neural_network).

 

### Relation to other statistical machine learning methods

 

GANs are **implicit generative models**,[[8]](./Generative_adversarial_network#cite_note-8) which means that they do not explicitly model the likelihood function nor provide a means for finding the latent variable corresponding to a given sample, unlike alternatives such as [flow-based generative model](./Flow-based_generative_model).

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/b/bb/Types_of_deep_generative_models.png/250px-Types_of_deep_generative_models.png)](./File:Types_of_deep_generative_models.png)Main types of deep generative models that perform maximum likelihood estimation[[9]](./Generative_adversarial_network#cite_note-:5-9) 

Compared to fully visible belief networks such as [WaveNet](./WaveNet) and PixelRNN and autoregressive models in general, GANs can generate one complete sample in one pass, rather than multiple passes through the network.

 

Compared to [Boltzmann machines](./Boltzmann_machine) and linear [ICA](./Independent_component_analysis), there is no restriction on the type of function used by the network.

 

Since neural networks are [universal approximators](./Universal_approximation_theorem), GANs are [asymptotically consistent](./Asymptotic_theory_(statistics)#Consistency). [Variational autoencoders](./Variational_autoencoders) might be universal approximators, but it is not proven as of 2017.[[9]](./Generative_adversarial_network#cite_note-:5-9)

 


