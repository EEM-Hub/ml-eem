---
source: sources/wiki-Unsupervised_learning.md
source_url: https://en.wikipedia.org/wiki/Unsupervised_learning
chunk: 1/3
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

 

 

 


