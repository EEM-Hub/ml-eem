---
source: sources/wiki-Neural_network_28machine_learning29.md
source_url: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29
chunk: 1/10
---

Computational model used in machine learning This article is about the computational models used for artificial intelligence. For other uses, see [Neural network (disambiguation)](./Neural_network_(disambiguation)). 
|  | This article needs to beupdated.Please help update this article to reflect recent events or newly available information.(May 2026) |
| --- | --- |

 

 

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/4/46/Colored_neural_network.svg/250px-Colored_neural_network.svg.png)](./File:Colored_neural_network.svg)A neural network is an interconnected group of nodes, inspired by a simplification of [neurons](./Neuron) in a [brain](./Brain). Here, each blue/green circular node in the hidden and output layers represents an [artificial neuron](./Artificial_neuron) and each red circular node in the far left layer represents an input data value. An arrow represents a connection from the output of one neuron (or data node) to the input of another. 
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

 

In [machine learning](./Machine_learning), a **neural network** (**NN**) or **neural net**, is a [computational model](./Computational_model) inspired by the structure and functions of [biological neural networks](./Biological_neural_networks).[[1]](./Neural_network_(machine_learning)#cite_note-1)[[2]](./Neural_network_(machine_learning)#cite_note-2)

 

A neural network consists of connected units or nodes called *[artificial neurons](./Artificial_neuron)*, which loosely model the [neurons](./Neuron) in the brain. Artificial neuron models that mimic biological neurons more closely have also been recently investigated and shown to significantly improve performance. These are connected by *edges*, which model the [synapses](./Synapse) in the brain. Each artificial neuron receives signals from connected neurons, then processes them and sends a signal to other connected neurons. The "signal" is a [real number](./Real_number), and the output of each neuron is computed by some non-linear function of the totality of its inputs, called the *[activation function](./Activation_function)*. The strength of the signal at each connection is determined by a *weight*, which adjusts as part of the training process.

 

Groups of neurons are aggregated into layers. Each layer performs a transformation on its inputs. Signals travel from the first layer (the *input layer*) to the last layer (the *output layer*), typically passing through multiple intermediate layers (*[hidden layers](./Hidden_layer)*). A network is typically called a deep neural network if it has at least two hidden layers. Deep neural networks are capable of learning sophisticated hierarchical representations.[*[citation needed](./Wikipedia:Citation_needed)*][[3]](./Neural_network_(machine_learning)#cite_note-3)

 

Training neural networks is a compute-intensive process, accelerated by  the use of [graphics processing units](./Graphics_processing_units) (GPUs), and large [datasets](./Datasets?action=edit&redlink=1).

 

Architectural innovations such as [convolutional neural networks](./Convolutional_neural_network) (CNNs) significantly improved performance in [computer vision](./Computer_vision) tasks, while [recurrent neural networks](./Recurrent_neural_network) (RNNs) enabled modeling of sequential data such as speech and time-series information. [Transformer architectures](./Transformer_(deep_learning_architecture)) introduced attention mechanisms that allow neural networks to model long-range dependencies in data and have the basis of [large language models](./Large_language_models).[[4]](./Neural_network_(machine_learning)#cite_note-:63-4)[*[AI-generated?](./Wikipedia:Large_language_models)*]

 

Artificial neural networks are used for a myriad of tasks including chatbots, large-scale text, image, and video generation, and robotics.

  [![](//upload.wikimedia.org/wikipedia/commons/thumb/0/0c/Simplified_neural_network_training_example.svg/330px-Simplified_neural_network_training_example.svg.png)](./File:Simplified_neural_network_training_example.svg)Simplified example of training a neural network in object detection: The network is trained by multiple images that are known to depict [starfish](./Starfish) and [sea urchins](./Sea_urchin), which are correlated with "nodes" that represent visual [features](./Feature_(computer_vision)). The starfish match with a ringed texture and a star outline, whereas most sea urchins match with a striped texture and oval shape. However, the instance of a ring textured sea urchin creates a weakly weighted association between them.[![](//upload.wikimedia.org/wikipedia/commons/thumb/b/b7/Simplified_neural_network_example.svg/330px-Simplified_neural_network_example.svg.png)](./File:Simplified_neural_network_example.svg)Subsequent run of the network on an input image:[[5]](./Neural_network_(machine_learning)#cite_note-5) The network correctly detects the starfish. However, the weakly weighted association between ringed texture and sea urchin also confers a weak signal to the latter from one of two intermediate nodes. In addition, a shell that was not included in the training gives a weak signal for the oval shape, also resulting in a weak signal for the sea urchin output. These weak signals may result in a [false positive](./False_positive) result for sea urchin.
In reality, textures and outlines would not be represented by single nodes, but rather by associated weight patterns of multiple nodes. 


