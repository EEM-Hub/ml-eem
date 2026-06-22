---
source: sources/wiki-Support_vector_machine.md
source_url: https://en.wikipedia.org/wiki/Support_vector_machine
chunk: 1/7
---

Set of methods for supervised statistical learning 
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

 

In [machine learning](./Machine_learning), **support vector machines** (**SVMs**, also **support vector networks**[[1]](./Support_vector_machine#cite_note-CorinnaCortes-1)) are [supervised](./Supervised_learning) [max-margin](./Maximum-margin_hyperplane) models with associated learning [algorithms](./Algorithm) that analyze data for [classification](./Statistical_classification) and [regression analysis](./Regression_analysis). Developed at [AT&T Bell Laboratories](./AT&T_Bell_Laboratories),[[1]](./Support_vector_machine#cite_note-CorinnaCortes-1)[[2]](./Support_vector_machine#cite_note-2) SVMs are one of the most studied models, being based on statistical learning frameworks of [VC theory](./VC_theory) proposed by [Vapnik](./Vladimir_Vapnik) (1982, 1995) and [Chervonenkis](./Alexey_Chervonenkis) (1974).

 

In addition to performing [linear classification](./Linear_classifier), SVMs can efficiently perform non-linear classification using the [*kernel trick*](./Kernel_method#Mathematics:_the_kernel_trick), representing the data only through a set of pairwise similarity comparisons between the original data points using a kernel function, which transforms them into coordinates in a higher-dimensional [feature space](./Feature_space). Thus, SVMs use the kernel trick to implicitly map their inputs into high-dimensional feature spaces, where linear classification can be performed.[[3]](./Support_vector_machine#cite_note-3)  Being max-margin models, SVMs are resilient to noisy data (e.g., misclassified examples). SVMs can also be used for [regression](./Regression_analysis) tasks, where the objective becomes     ϵ ϵ    {\displaystyle \epsilon }  ![{\displaystyle \epsilon }](https://wikimedia.org/api/rest_v1/media/math/render/svg/c3837cad72483d97bcdde49c85d3b7b859fb3fd2)-sensitive.

 

The support vector clustering[[4]](./Support_vector_machine#cite_note-HavaSiegelmann-4) algorithm, created by [Hava Siegelmann](./Hava_Siegelmann) and [Vladimir Vapnik](./Vladimir_Vapnik), applies the statistics of support vectors, developed in the support vector machines algorithm, to categorize unlabeled data.[*[citation needed](./Wikipedia:Citation_needed)*] These data sets require [unsupervised learning](./Unsupervised_learning) approaches, which attempt to find natural [clustering of the data](./Cluster_analysis) into groups, and then to map new data according to these clusters.

 

The popularity of SVMs is likely due to their amenability to theoretical analysis, and their flexibility in being applied to a wide variety of tasks, including [structured prediction](./Structured_prediction) problems. It is not clear that SVMs have better predictive performance than other linear models, such as [logistic regression](./Logistic_regression) and [linear regression](./Linear_regression).[[5]](./Support_vector_machine#cite_note-5)

 

## Motivation

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/b/b5/Svm_separating_hyperplanes_%28SVG%29.svg/250px-Svm_separating_hyperplanes_%28SVG%29.svg.png)](./File:Svm_separating_hyperplanes_(SVG).svg)H1 does not separate the classes. H2 does, but only with a small margin.  H3 separates them with the maximal margin. 

[Classifying data](./Statistical_classification) is a common task in [machine learning](./Machine_learning).
Suppose some given data points each belong to one of two classes, and the goal is to decide which class a *new* [data point](./Data_point) will be in. In the case of support vector machines, a data point is viewed as a     p   {\displaystyle p}  ![{\displaystyle p}](https://wikimedia.org/api/rest_v1/media/math/render/svg/81eac1e205430d1f40810df36a0edffdc367af36)-dimensional vector (a list of     p   {\displaystyle p}  ![{\displaystyle p}](https://wikimedia.org/api/rest_v1/media/math/render/svg/81eac1e205430d1f40810df36a0edffdc367af36) numbers), and we want to know whether we can separate such points with a     ( p − −  1 )   {\displaystyle (p-1)}  ![{\displaystyle (p-1)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ac90749c06d21ccfffb53161ea2ef2a9d7ef4e7e)-dimensional [hyperplane](./Hyperplane). This is called a [linear classifier](./Linear_classifier). There are many hyperplanes that might classify the data. One reasonable choice as the best hyperplane is the one that represents the largest separation, or [margin](./Margin_(machine_learning)), between the two classes. So we choose the hyperplane so that the distance from it to the nearest data point on each side is maximized. If such a hyperplane exists, it is known as the *[maximum-margin hyperplane](./Maximum-margin_hyperplane)* and the linear classifier it defines is known as a *maximum-[margin classifier](./Margin_classifier)*; or equivalently, the *[perceptron of optimal stability](./Perceptron#Convergence)*.[[6]](./Support_vector_machine#cite_note-6)

 

More formally, a support vector machine constructs a [hyperplane](./Hyperplane) or set of hyperplanes in a high or infinite-dimensional space, which can be used for [classification](./Statistical_classification), [regression](./Regression_analysis), or other tasks like outlier detection.[[7]](./Support_vector_machine#cite_note-7) Intuitively, a good separation is achieved by the hyperplane that has the largest distance to the nearest training-data point of any class (so-called functional margin), since in general the larger the margin, the lower the [generalization error](./Generalization_error) of the classifier.[[8]](./Support_vector_machine#cite_note-8) A lower [generalization error](./Generalization_error) means that the implementer is less likely to experience [overfitting](./Overfitting).

 

Whereas the original problem may be stated in a finite-dimensional space, it often happens that the sets to discriminate are not [linearly separable](./Linear_separability) in that space. For this reason, it was proposed[[9]](./Support_vector_machine#cite_note-ReferenceA-9) that the original finite-dimensional space be mapped into a much higher-dimensional space, presumably making the separation easier in that space. To keep the computational load reasonable, the mappings used by SVM schemes are designed to ensure that [dot products](./Dot_product) of pairs of input data vectors may be computed easily in terms of the variables in the original space, by defining them in terms of a [kernel function](./Positive-definite_kernel)     k ( x , y )   {\displaystyle k(x,y)}  ![{\displaystyle k(x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7d18e060406f195657b2151490ca3d491f7a7ce0) selected to suit the problem.[[10]](./Support_vector_machine#cite_note-10) The hyperplanes in the higher-dimensional space are defined as the set of points whose dot product with a vector in that space is constant, where such a set of vectors is an orthogonal (and thus minimal) set of vectors that defines a hyperplane. The vectors defining the hyperplanes can be chosen to be linear combinations with parameters      α α   i     {\displaystyle \alpha _{i}}  ![{\displaystyle \alpha _{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3b1fb627423abe4988b7ed88d4920bf1ec074790) of images of [feature vectors](./Feature_vector)      x  i     {\displaystyle x_{i}}  ![{\displaystyle x_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e87000dd6142b81d041896a30fe58f0c3acb2158) that occur in the data base. With this choice of a hyperplane, the points     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4) in the [feature space](./Feature_space) that are mapped into the hyperplane are defined by the relation       ∑ ∑   i    α α   i   k (  x  i   , x ) =  constant  .    {\displaystyle \textstyle \sum _{i}\alpha _{i}k(x_{i},x)={\text{constant}}.}  ![{\displaystyle \textstyle \sum _{i}\alpha _{i}k(x_{i},x)={\text{constant}}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a6f34ab5c46f89828183543c7ec44942e5cc3cff)  Note that if     k ( x , y )   {\displaystyle k(x,y)}  ![{\displaystyle k(x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7d18e060406f195657b2151490ca3d491f7a7ce0) becomes small as     y   {\displaystyle y}  ![{\displaystyle y}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b8a6208ec717213d4317e666f1ae872e00620a0d) grows further away from     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4), each term in the sum measures the degree of closeness of the test point     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4) to the corresponding data base point      x  i     {\displaystyle x_{i}}  ![{\displaystyle x_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e87000dd6142b81d041896a30fe58f0c3acb2158). In this way, the sum of kernels above can be used to measure the relative nearness of each test point to the data points originating in one or the other of the sets to be discriminated. Note the fact that the set of points     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4) mapped into any hyperplane can be quite convoluted as a result, allowing much more complex discrimination between sets that are not convex at all in the original space.

 

## Applications

 

SVMs can be used to solve various real-world problems:

 
- SVMs are helpful in [text and hypertext categorization](./Text_categorization), as their application can significantly reduce the need for labeled training instances in both the standard inductive and [transductive](./Transduction_(machine_learning)) settings.[[11]](./Support_vector_machine#cite_note-11) Some methods for [shallow semantic parsing](./Shallow_semantic_parsing) are based on support vector machines.[[12]](./Support_vector_machine#cite_note-12)
- [Classification of images](./Image_classification) can also be performed using SVMs. Experimental results show that SVMs achieve significantly higher search accuracy than traditional query refinement schemes after just three to four rounds of relevance feedback. This is also true for [image segmentation](./Image_segmentation) systems, including those using a modified version SVM that uses the privileged approach as suggested by Vapnik.[[13]](./Support_vector_machine#cite_note-13)[[14]](./Support_vector_machine#cite_note-14)
- Classification of satellite data like [SAR](./Synthetic-aperture_radar) data using supervised SVM.[[15]](./Support_vector_machine#cite_note-15)
- Hand-written characters can be [recognized](./Handwriting_recognition) using SVM.[[16]](./Support_vector_machine#cite_note-16)[[17]](./Support_vector_machine#cite_note-17)
- The SVM algorithm has been widely applied in the biological and other sciences.  They have been used to classify proteins with up to 90% of the compounds classified correctly. [Permutation tests](./Permutation_test) based on SVM weights have been suggested as a mechanism for interpretation of SVM models.[[18]](./Support_vector_machine#cite_note-18)[[19]](./Support_vector_machine#cite_note-19) Support vector machine weights have also been used to interpret SVM models in the past.[[20]](./Support_vector_machine#cite_note-20) Posthoc interpretation of support vector machine models in order to identify features used by the model to make predictions is a relatively new area of research with special significance in the biological sciences.

 

## History

 

The original SVM algorithm was invented by [Vladimir N. Vapnik](./Vladimir_N._Vapnik) and [Alexey Ya. Chervonenkis](./Alexey_Chervonenkis) in 1964.[*[citation needed](./Wikipedia:Citation_needed)*] In 1992, Bernhard Boser, [Isabelle Guyon](./Isabelle_Guyon) and [Vladimir Vapnik](./Vladimir_Vapnik) suggested a way to create nonlinear classifiers by applying the [kernel trick](./Kernel_trick) to maximum-margin hyperplanes.[[9]](./Support_vector_machine#cite_note-ReferenceA-9) The "soft margin" incarnation, as is commonly used in software packages, was proposed by [Corinna Cortes](./Corinna_Cortes) and Vapnik in 1993 and published in 1995.[[1]](./Support_vector_machine#cite_note-CorinnaCortes-1)

 


