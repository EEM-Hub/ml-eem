---
source: sources/wiki-BiasE28093variance_tradeoff.md
source_url: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff
chunk: 1/4
---

Property of a model [![](//upload.wikimedia.org/wikipedia/commons/thumb/9/9f/Bias_and_variance_contributing_to_total_error.svg/250px-Bias_and_variance_contributing_to_total_error.svg.png)](./File:Bias_and_variance_contributing_to_total_error.svg)Bias and variance as function of model complexity 
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

 

In [statistics](./Statistics) and [machine learning](./Machine_learning), the **bias–variance tradeoff** describes the relationship between a model's complexity, the accuracy of its predictions, and how well it can make predictions on previously unseen data that were not used to train the model. In general, as the number of tunable parameters in a model increases, it becomes more flexible, and can better fit a training data set. That is, the model has lower error or lower [bias](./Bias_of_an_estimator). However, for more flexible models, there will tend to be greater **variance** to the model fit each time we take a set of [samples](./Sample_(statistics)) to create a new training data set. It is said that there is greater [variance](./Variance) in the model's [estimated](./Estimation_theory) [parameters](./Statistical_parameter).

 

The **bias–variance dilemma** or **bias–variance problem** is the conflict in trying to simultaneously minimize these two sources of [error](./Errors_and_residuals_in_statistics) that prevent [supervised learning](./Supervised_learning) algorithms from generalizing beyond their [training set](./Training_set):[[1]](./Bias–variance_tradeoff#cite_note-:0-1)[[2]](./Bias–variance_tradeoff#cite_note-:1-2)

 
- The [*bias*](./Bias_of_an_estimator) error is an error from erroneous assumptions in the learning [algorithm](./Algorithm). High bias can cause an algorithm to miss the relevant relations between features and target outputs ([underfitting](./Overfitting#Underfitting)).
- The *[variance](./Variance)* is an error from sensitivity to small fluctuations in the training set. High variance may result from an algorithm modeling the random [noise](./Noise_(signal_processing)) in the training data ([overfitting](./Overfitting)).

 

The **bias–variance decomposition** is a way of analyzing a learning algorithm's [expected](./Expected_value) [generalization error](./Generalization_error) with respect to a particular problem as a sum of three terms, the bias, variance, and a quantity called the *irreducible error*, resulting from noise in the problem itself.

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/6/64/Test_function_and_noisy_data.png/250px-Test_function_and_noisy_data.png)](./File:Test_function_and_noisy_data.png)Function and noisy data[![](//upload.wikimedia.org/wikipedia/commons/thumb/9/91/Radial_basis_function_fit%2C_spread%3D5.png/250px-Radial_basis_function_fit%2C_spread%3D5.png)](./File:Radial_basis_function_fit,_spread=5.png)Spread=5[![](//upload.wikimedia.org/wikipedia/commons/thumb/6/63/Radial_basis_function_fit%2C_spread%3D1.png/250px-Radial_basis_function_fit%2C_spread%3D1.png)](./File:Radial_basis_function_fit,_spread=1.png)Spread=1[![](//upload.wikimedia.org/wikipedia/commons/thumb/3/3f/Radial_basis_function_fit%2C_spread%3D0.1.png/250px-Radial_basis_function_fit%2C_spread%3D0.1.png)](./File:Radial_basis_function_fit,_spread=0.1.png)Spread=0.1A function (red) is approximated using [radial basis functions](./Radial_basis_functions) (blue). Several trials are shown in each graph. For each trial, a few noisy data points are provided as a training set (top). For a wide spread (image 2) the bias is high: the RBFs cannot fully approximate the function (especially the central dip), but the variance between different trials is low. As spread decreases (image 3 and 4) the bias decreases: the blue curves more closely approximate the red. However, depending on the noise in different trials the variance between trials increases. In the lowermost image the approximated values for x=0 varies wildly depending on where the data points were located. 

## Motivation

 See also: [Accuracy and precision](./Accuracy_and_precision)
- [![High bias, low variance](//upload.wikimedia.org/wikipedia/commons/thumb/a/a2/Truen_bad_prec_ok.png/120px-Truen_bad_prec_ok.png)](./File:Truen_bad_prec_ok.png)High bias, low variance
- [![High bias, high variance](//upload.wikimedia.org/wikipedia/commons/thumb/f/fd/Truen_bad_prec_bad.png/120px-Truen_bad_prec_bad.png)](./File:Truen_bad_prec_bad.png)High bias, high variance
- [![Low bias, low variance](//upload.wikimedia.org/wikipedia/commons/thumb/2/2a/En_low_bias_low_variance.png/120px-En_low_bias_low_variance.png)](./File:En_low_bias_low_variance.png)Low bias, low variance
- [![Low bias, high variance](//upload.wikimedia.org/wikipedia/commons/thumb/d/dc/Truen_ok_prec_bad.png/120px-Truen_ok_prec_bad.png)](./File:Truen_ok_prec_bad.png)Low bias, high variance

 

The bias–variance tradeoff is a central problem in supervised learning. Ideally, one wants to [choose a model](./Model_selection) that both accurately captures the regularities in its training data, but also [generalizes](./Generalization) well to unseen data. Unfortunately, it is typically impossible to do both simultaneously. High-variance learning methods may be able to represent their training set well but are at risk of overfitting to noisy or unrepresentative training data. In contrast, algorithms with high bias typically produce simpler models that may fail to capture important regularities (i.e. underfit) in the data.

 

It is an often made [fallacy](./Affirming_the_consequent)[[3]](./Bias–variance_tradeoff#cite_note-nealThesis2019-3)[[4]](./Bias–variance_tradeoff#cite_note-neal2018-4) to assume that complex models must have high variance. High variance models are "complex" in some sense, but the reverse need not be true.[[5]](./Bias–variance_tradeoff#cite_note-5) In addition, one has to be careful how to define complexity. In particular, the number of parameters used to describe the model is a poor measure of complexity. The model      f  a , b   ( x ) = a sin ⁡ ⁡  ( b x )   {\displaystyle f_{a,b}(x)=a\sin(bx)}  ![{\displaystyle f_{a,b}(x)=a\sin(bx)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/14ef53fa675be7cb7d9171699294ad22879fe078) has only two parameters (    a , b   {\displaystyle a,b}  ![{\displaystyle a,b}](https://wikimedia.org/api/rest_v1/media/math/render/svg/181523deba732fda302fd176275a0739121d3bc8)) but it can interpolate any number of points by oscillating with a high enough frequency, resulting in both a high bias and high variance.[[6]](./Bias–variance_tradeoff#cite_note-6)

 

An analogy can be made to the relationship between [accuracy and precision](./Accuracy_and_precision). Accuracy is one way of quantifying bias and can intuitively be improved by selecting from only [local](./Sample_space) information. Consequently, a sample will appear accurate (i.e. have low bias) under the aforementioned selection conditions, but may result in underfitting. In other words, [test data](./Training,_validation,_and_test_data_sets) may not agree as closely with training data, which would indicate imprecision and therefore inflated variance. A graphical example would be a straight line fit to data exhibiting quadratic behavior overall. Precision is a description of variance and generally can only be improved by selecting information from a comparatively larger space. The option to select many data points over a broad sample space is the ideal condition for any analysis. However, intrinsic constraints (whether physical, theoretical, computational, etc.) will always play a limiting role. The limiting case where only a finite number of data points are selected over a broad sample space may result in improved precision and lower variance overall, but may also result in an overreliance on the training data (overfitting). This means that test data would also not agree as closely with the training data, but in this case the reason is inaccuracy or high bias. To borrow from the previous example, the graphical representation would appear as a high-order polynomial fit to the same data exhibiting quadratic behavior. Note that error in each case is measured the same way, but the reason ascribed to the error is different depending on the balance between bias and variance. To mitigate how much information is used from neighboring observations, a model can be [smoothed](./Smoothing) via explicit [regularization](./Regularization_(mathematics)), such as [shrinkage](./Shrinkage_(statistics)).

 


