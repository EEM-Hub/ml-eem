---
source: sources/wiki-Transfer_learning.md
source_url: https://en.wikipedia.org/wiki/Transfer_learning
chunk: 1/2
---

Machine learning technique Not to be confused with [Transfer of learning](./Transfer_of_learning) or [knowledge transfer](./Knowledge_transfer). [![](//upload.wikimedia.org/wikipedia/commons/thumb/6/6f/Transfer_learning.svg/250px-Transfer_learning.svg.png)](./File:Transfer_learning.svg)Illustration of transfer learning 
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

 

**Transfer learning** (**TL**) is a technique in [machine learning](./Machine_learning) (ML) in which knowledge learned from a task is re-used in order to boost performance on a related task.[[1]](./Transfer_learning#cite_note-1) For example, for [image classification](./Computer_vision), knowledge gained while learning to [recognize](./Computer_vision#Recognition) cars could be applied when trying to recognize trucks. This topic is related to the psychological literature on [transfer of learning](./Transfer_of_learning), although practical ties between the two fields are limited. Reusing or transferring information from previously learned tasks to new tasks has the potential to significantly improve learning efficiency.[[2]](./Transfer_learning#cite_note-2)

 

Since transfer learning makes use of training with multiple objective functions it is related to [cost-sensitive machine learning](./Cost-sensitive_machine_learning) and [multi-objective optimization](./Multi-objective_optimization).[[3]](./Transfer_learning#cite_note-3)

 

## History

 Potential overusage of publications by Lorien Pratt, maybe by COI editor. Not a balanced view on the history of this topic, needs a broader range of sources. (see https://en.wikipedia.org/w/index.php?title=Transfer_learning&#x26;diff=684692020&#x26;oldid=646958283) 

In 1976, Bozinovski and Fulgosi published a paper addressing transfer learning in [neural network](./Neural_network) training.[[4]](./Transfer_learning#cite_note-4)[[5]](./Transfer_learning#cite_note-5) The paper gives a mathematical and geometrical model of the topic. In 1981, a report considered the application of transfer learning to a dataset of images representing letters of computer terminals, experimentally demonstrating positive and negative transfer learning.[[6]](./Transfer_learning#cite_note-6)

 

In 1992, [Lorien Pratt](./Lorien_Pratt) formulated the discriminability-based transfer (DBT) algorithm.[[7]](./Transfer_learning#cite_note-7)

 

By 1998, the field had advanced to include [multi-task learning](./Multi-task_learning),[[8]](./Transfer_learning#cite_note-8) along with more formal theoretical foundations.[[9]](./Transfer_learning#cite_note-9) Influential publications on transfer learning include the book *Learning to Learn* in 1998,[[10]](./Transfer_learning#cite_note-FOOTNOTEThrunPratt2012-10) a 2009 survey[[11]](./Transfer_learning#cite_note-11) and a 2019 survey.[[12]](./Transfer_learning#cite_note-12)

 

[Ng](./Andrew_Ng) said in his NIPS 2016 tutorial[[13]](./Transfer_learning#cite_note-13)[[14]](./Transfer_learning#cite_note-14) that TL would become the next driver of [machine learning](./Machine_learning) commercial success after [supervised learning](./Supervised_learning).

 

In the 2020 paper, "Rethinking Pre-Training and self-training",[[15]](./Transfer_learning#cite_note-15) Zoph et al. reported that pre-training can hurt accuracy, and advocate self-training instead.

 

## Definition

 

The definition of transfer learning is given in terms of domains and tasks. A domain       D     {\displaystyle {\mathcal {D}}}  ![{\displaystyle {\mathcal {D}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3277962e1959c3241fb1b70c7f0ac6dcefebd966) consists of: a [feature space](./Feature_space)       X     {\displaystyle {\mathcal {X}}}  ![{\displaystyle {\mathcal {X}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8c7e5461c5286852df4ef652fca7e4b0b63030e9) and a [marginal probability distribution](./Marginal_probability_distribution)     P ( X )   {\displaystyle P(X)}  ![{\displaystyle P(X)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/bf94167ebc67db1573e6be9e261cd0518e49e160), where     X = {  x  1   , . . . ,  x  n   } ∈ ∈    X     {\displaystyle X=\{x_{1},...,x_{n}\}\in {\mathcal {X}}}  ![{\displaystyle X=\{x_{1},...,x_{n}\}\in {\mathcal {X}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f366e8a442318d54e0a28b94f25e2756293014e4). Given a specific domain,       D   = {   X   , P ( X ) }   {\displaystyle {\mathcal {D}}=\{{\mathcal {X}},P(X)\}}  ![{\displaystyle {\mathcal {D}}=\{{\mathcal {X}},P(X)\}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/62b90afd89582dbf0e6672baa0708912628f9958), a task consists of two components: a label space       Y     {\displaystyle {\mathcal {Y}}}  ![{\displaystyle {\mathcal {Y}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8935ef8cf454efa0b58363386c33f16a48ec36ca) and an objective predictive function     f :   X   → →    Y     {\displaystyle f:{\mathcal {X}}\rightarrow {\mathcal {Y}}}  ![{\displaystyle f:{\mathcal {X}}\rightarrow {\mathcal {Y}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/24d657a1f4e3818257adc8c92ba313329ca7c4d1). The function     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) is used to predict the corresponding label     f ( x )   {\displaystyle f(x)}  ![{\displaystyle f(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/202945cce41ecebb6f643f31d119c514bec7a074) of a new instance     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4). This task, denoted by       T   = {   Y   , f ( x ) }   {\displaystyle {\mathcal {T}}=\{{\mathcal {Y}},f(x)\}}  ![{\displaystyle {\mathcal {T}}=\{{\mathcal {Y}},f(x)\}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/28815172a512bcdbb9f8184d63515a7bc4822fc5), is learned from the training data consisting of pairs     {  x  i   ,  y  i   }   {\displaystyle \{x_{i},y_{i}\}}  ![{\displaystyle \{x_{i},y_{i}\}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3c5044f20cfba071b7d4e92dc651c2b39ac0207b), where      x  i   ∈ ∈    X     {\displaystyle x_{i}\in {\mathcal {X}}}  ![{\displaystyle x_{i}\in {\mathcal {X}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/09d1f60c993f578ec3d8c08e521b87931d0feac8) and      y  i   ∈ ∈    Y     {\displaystyle y_{i}\in {\mathcal {Y}}}  ![{\displaystyle y_{i}\in {\mathcal {Y}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a7ab4d7fbffa36a1428d869b75f25508da3997e1).[[16]](./Transfer_learning#cite_note-Lin,_Jung_2017-16)

 

Given a source domain        D    S     {\displaystyle {\mathcal {D}}_{S}}  ![{\displaystyle {\mathcal {D}}_{S}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/73b93b620f34fe7db50f7f7525417ae5534d9b65) and learning task        T    S     {\displaystyle {\mathcal {T}}_{S}}  ![{\displaystyle {\mathcal {T}}_{S}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fd1420bea4f3d0b24470564614856f43f0f4b2a3), a target domain        D    T     {\displaystyle {\mathcal {D}}_{T}}  ![{\displaystyle {\mathcal {D}}_{T}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/13423a952f04fe320974a72ba018efc6c4e867e8) and learning task        T    T     {\displaystyle {\mathcal {T}}_{T}}  ![{\displaystyle {\mathcal {T}}_{T}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/27876915db93885f6db8689624b9dcfe88b2f3a0), where        D    S   ≠ ≠     D    T     {\displaystyle {\mathcal {D}}_{S}\neq {\mathcal {D}}_{T}}  ![{\displaystyle {\mathcal {D}}_{S}\neq {\mathcal {D}}_{T}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4bf039e3293649209545fe31ae5d6098aacbbd2a), or        T    S   ≠ ≠     T    T     {\displaystyle {\mathcal {T}}_{S}\neq {\mathcal {T}}_{T}}  ![{\displaystyle {\mathcal {T}}_{S}\neq {\mathcal {T}}_{T}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8b782c4e0cbf99cc00f83cac1148f4b7384f02de), transfer learning aims to help improve the learning of the target predictive function      f  T   ( ⋅ ⋅  )   {\displaystyle f_{T}(\cdot )}  ![{\displaystyle f_{T}(\cdot )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0af4f92ff9d7d2a44bc4dca321b8ccd5f0f806eb) in        D    T     {\displaystyle {\mathcal {D}}_{T}}  ![{\displaystyle {\mathcal {D}}_{T}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/13423a952f04fe320974a72ba018efc6c4e867e8) using the knowledge in        D    S     {\displaystyle {\mathcal {D}}_{S}}  ![{\displaystyle {\mathcal {D}}_{S}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/73b93b620f34fe7db50f7f7525417ae5534d9b65) and        T    S     {\displaystyle {\mathcal {T}}_{S}}  ![{\displaystyle {\mathcal {T}}_{S}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fd1420bea4f3d0b24470564614856f43f0f4b2a3).[[16]](./Transfer_learning#cite_note-Lin,_Jung_2017-16)

 

## Applications

 

Algorithms for transfer learning are available in [Markov logic networks](./Markov_logic_network)[[17]](./Transfer_learning#cite_note-17) and [Bayesian networks](./Bayesian_networks).[[18]](./Transfer_learning#cite_note-18) Transfer learning has been applied to cancer subtype discovery,[[19]](./Transfer_learning#cite_note-:bmdl-19) building utilization,[[20]](./Transfer_learning#cite_note-20)[[21]](./Transfer_learning#cite_note-21) [general game playing](./General_game_playing),[[22]](./Transfer_learning#cite_note-22) [text classification](./Document_classification),[[23]](./Transfer_learning#cite_note-23)[[24]](./Transfer_learning#cite_note-24) digit recognition,[[25]](./Transfer_learning#cite_note-25) medical imaging and [spam filtering](./E-mail_filtering).[[26]](./Transfer_learning#cite_note-26)

 

In 2020, it was discovered that, due to their similar physical natures, transfer learning is possible between [electromyographic](./Electromyographic) (EMG) signals from the muscles and classifying the behaviors of [electroencephalographic](./Electroencephalographic) (EEG) brainwaves, from the [gesture recognition](./Gesture_recognition) domain to the mental state recognition domain. It was noted that this relationship worked in both directions, showing that EEG brainwaves can likewise be used to classify EMG signals.[[27]](./Transfer_learning#cite_note-27) The experiments noted that the accuracy of [neural networks](./Artificial_neural_network) and [convolutional neural networks](./Convolutional_neural_network) were improved[[28]](./Transfer_learning#cite_note-28) through transfer learning both prior to any learning (compared to standard random weight distribution) and at the end of the learning process (asymptote). That is, results are improved by exposure to another domain. Moreover, the end-user of a pre-trained model can change the structure of fully-connected layers to improve performance.[[29]](./Transfer_learning#cite_note-29)

 

## See also

 
- [Crossover (genetic algorithm)](./Crossover_(genetic_algorithm))
- [Domain adaptation](./Domain_adaptation)
- [General game playing](./General_game_playing)
- [Multi-task learning](./Multi-task_learning)
- [Multitask optimization](./Multitask_optimization)
- [Transfer of learning](./Transfer_of_learning) in [educational psychology](./Educational_psychology)
- [Zero-shot learning](./Zero-shot_learning)
- [Feature learning](./Feature_learning)
- [external validity](./External_validity)

 


