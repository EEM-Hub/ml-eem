---
source: sources/wiki-Gradient_descent.md
source_url: https://en.wikipedia.org/wiki/Gradient_descent
chunk: 1/6
---

Optimization algorithm For the analytical method called "steepest descent", see [Method of steepest descent](./Method_of_steepest_descent). Gradient descent in 2D 

**Gradient descent** is a method for unconstrained [mathematical optimization](./Mathematical_optimization). It is a [first-order](./Category:First_order_methods) [iterative](./Iterative_algorithm) [algorithm](./Algorithm) for minimizing a [differentiable](./Differentiable_function) [multivariate function](./Multivariate_function).

 
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

 

The idea is to take repeated steps in the opposite direction of the [gradient](./Gradient) (or approximate gradient) of the function at the current point, because this is the direction of steepest descent. Conversely, stepping in the direction of the gradient will lead to a trajectory that maximizes that function; the procedure is then known as *gradient ascent*.
Gradient descent should not be confused with [local search](./Local_search_(optimization)) algorithms, although both are [iterative methods](./Iterative_method) for [optimization](./Global_optimization).

 

Gradient descent is particularly useful in [machine learning](./Machine_learning) and [artificial intelligence](./Artificial_intelligence) for minimizing the cost or loss function.[[1]](./Gradient_descent#cite_note-auto-1)

 

Gradient descent is generally attributed to [Augustin-Louis Cauchy](./Augustin-Louis_Cauchy), who first suggested it in 1847.[[2]](./Gradient_descent#cite_note-2) [Jacques Hadamard](./Jacques_Hadamard) independently proposed a similar method in 1907.[[3]](./Gradient_descent#cite_note-3)[[4]](./Gradient_descent#cite_note-4) Its convergence properties for non-linear optimization problems were first studied by [Haskell Curry](./Haskell_Curry) in 1944,[[5]](./Gradient_descent#cite_note-5) with the method becoming increasingly well-studied and used in the following decades.[[6]](./Gradient_descent#cite_note-BP-6)[[7]](./Gradient_descent#cite_note-AK82-7)

 

A simple extension of gradient descent, [stochastic gradient descent](./Stochastic_gradient_descent), serves as the most basic algorithm used for training most [deep networks](./Deep_neural_network) today.

 


