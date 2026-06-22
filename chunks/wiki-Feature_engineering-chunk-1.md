---
source: sources/wiki-Feature_engineering.md
source_url: https://en.wikipedia.org/wiki/Feature_engineering
chunk: 1/2
---

Extracting features from raw data for machine learning 
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

|  | This article needs to beupdated.Please help update this article to reflect recent events or newly available information.(February 2024) |
| --- | --- |

 

**Feature engineering** is a preprocessing step in [supervised machine learning](./Supervised_machine_learning) and [statistical modeling](./Statistical_modeling)[[1]](./Feature_engineering#cite_note-1) which transforms raw data into a more effective set of inputs. Each input comprises several attributes, known as features. By providing models with relevant information, feature engineering significantly enhances their predictive accuracy and decision-making capability.[[2]](./Feature_engineering#cite_note-auto1-2)[[3]](./Feature_engineering#cite_note-3)[[4]](./Feature_engineering#cite_note-4)

 

Beyond machine learning, the principles of feature engineering are applied in various scientific fields, including physics. For example, physicists construct [dimensionless numbers](./Dimensionless_quantity) such as the [Reynolds number](./Reynolds_number) in [fluid dynamics](./Fluid_dynamics), the [Nusselt number](./Nusselt_number) in [heat transfer](./Heat_transfer), and the [Archimedes number](./Archimedes_number) in [sedimentation](./Sedimentation). They also develop first approximations of solutions, such as analytical solutions for the [strength of materials](./Strength_of_materials) in mechanics.[[5]](./Feature_engineering#cite_note-5)

 

## Clustering

 

One of the applications of feature engineering has been clustering of feature-objects or sample-objects in a dataset. Especially, feature engineering based on [matrix decomposition](./Matrix_decomposition) has been extensively used for data clustering under non-negativity constraints on the feature coefficients. These include *Non-Negative Matrix Factorization* (NMF),[[6]](./Feature_engineering#cite_note-6) *Non-Negative Matrix-Tri Factorization* (NMTF),[[7]](./Feature_engineering#cite_note-7) *Non-Negative Tensor Decomposition/Factorization* (NTF/NTD),[[8]](./Feature_engineering#cite_note-8) etc. The non-negativity constraints on coefficients of the feature vectors mined by the above-stated algorithms yields a part-based representation, and different factor matrices exhibit natural clustering properties. Several extensions of the above-stated feature engineering methods have been reported in literature, including *orthogonality-constrained factorization* for hard clustering, and *manifold learning* to overcome inherent issues with these algorithms.

 

Other classes of feature engineering algorithms include leveraging a common hidden structure across multiple inter-related datasets to obtain a consensus (common) clustering scheme. An example is *Multi-view Classification based on Consensus Matrix Decomposition* (MCMD),[[2]](./Feature_engineering#cite_note-auto1-2) which mines a common clustering scheme across multiple datasets. MCMD is designed to output two types of class labels (scale-variant and scale-invariant clustering), and:

 
- is [computationally robust](./Robustness_(computer_science)) to missing information,
- can obtain shape- and scale-based outliers,
- and can handle high-dimensional data effectively.

 

Coupled matrix and tensor decompositions are popular in multi-view feature engineering.[[9]](./Feature_engineering#cite_note-9)

 

## Predictive modelling

 

Feature engineering in [machine learning](./Machine_learning) and [statistical modeling](./Statistical_modeling) involves selecting, creating, transforming, and extracting data features. Key components include feature creation from existing data, transforming and imputing missing or invalid features, reducing data dimensionality through methods like [Principal Components Analysis](./Principal_component_analysis) (PCA), [Independent Component Analysis](./Independent_component_analysis) (ICA), and [Linear Discriminant Analysis](./Linear_discriminant_analysis) (LDA), and selecting the most relevant features for model training based on importance scores and [correlation matrices](./Correlation_matrices).[[10]](./Feature_engineering#cite_note-10)

 

Features vary in significance.[[11]](./Feature_engineering#cite_note-11) Even relatively insignificant features may contribute to a model. [Feature selection](./Feature_selection) can reduce the number of features to prevent a model from becoming too specific to the training data set (overfitting).[[12]](./Feature_engineering#cite_note-12)

 

Feature explosion occurs when the number of identified features is too large for effective model estimation or optimization. Common causes include:

 
- Feature templates - implementing feature templates instead of coding new features
- Feature combinations - combinations that cannot be represented by a linear system

 

Feature explosion can be limited via techniques such as [regularization](./Regularization_(mathematics)), [kernel methods](./Kernel_method), and [feature selection](./Feature_selection).[[13]](./Feature_engineering#cite_note-13)

 

## Automation

 

Automation of feature engineering is a research topic that dates back to the 1990s.[[14]](./Feature_engineering#cite_note-:0-14) Machine learning software that incorporates [automated feature engineering](./Automated_feature_engineering) has been commercially available since 2016.[[15]](./Feature_engineering#cite_note-15) Related academic literature can be roughly separated into two types:

 
- Multi-relational Decision Tree Learning (MRDTL) uses a supervised algorithm that is similar to a [decision tree](./Decision_tree).
- Deep Feature Synthesis uses simpler methods.[*[citation needed](./Wikipedia:Citation_needed)*]

 

### Multi-relational Decision Tree Learning (MRDTL)

 

Multi-relational Decision Tree Learning (MRDTL) extends traditional decision tree methods to [relational databases](./Relational_database), handling complex data relationships across tables. It innovatively uses selection graphs as [decision nodes](./Decision_node), refined systematically until a specific termination criterion is reached.[[14]](./Feature_engineering#cite_note-:0-14)

 

Most MRDTL studies base implementations on relational databases, which results in many redundant operations. These redundancies can be reduced by using techniques such as tuple id propagation.[[16]](./Feature_engineering#cite_note-16)[[17]](./Feature_engineering#cite_note-17)

 

### Open-source implementations

 

There are a number of open-source libraries and tools that automate feature engineering on relational data and time series:

 
- **featuretools** is a [Python](./Python_(programming_language)) library for transforming time series and relational data into feature matrices for machine learning.[[18]](./Feature_engineering#cite_note-18)[[19]](./Feature_engineering#cite_note-19)[[20]](./Feature_engineering#cite_note-20)
- **MCMD:** An open-source feature engineering algorithm for joint clustering of multiple datasets.[[21]](./Feature_engineering#cite_note-21)[[2]](./Feature_engineering#cite_note-auto1-2)
- **OneBM** or One-Button Machine combines feature transformations and feature selection on relational data with feature selection techniques.[[22]](./Feature_engineering#cite_note-auto2-22) 

OneBM helps data scientists reduce data exploration time allowing them to try and error many ideas in short time. On the other hand, it enables non-experts, who are not familiar with data science, to quickly extract value from their data with a little effort, time, and cost.[[22]](./Feature_engineering#cite_note-auto2-22)

- **getML community** is an open source tool for automated feature engineering on time series and relational data.[[23]](./Feature_engineering#cite_note-23)[[24]](./Feature_engineering#cite_note-auto-24) It is implemented in [C](./C_(programming_language))/[C++](./C++) with a Python interface.[[24]](./Feature_engineering#cite_note-auto-24) It has been shown to be at least 60 times faster than tsflex, tsfresh, tsfel, featuretools or kats.[[24]](./Feature_engineering#cite_note-auto-24)
- **tsfresh** is a Python library for feature extraction on time series data.[[25]](./Feature_engineering#cite_note-25) It evaluates the quality of the features using hypothesis testing.[[26]](./Feature_engineering#cite_note-26)
- **tsflex** is an open source Python library for extracting features from time series data.[[27]](./Feature_engineering#cite_note-27) Despite being 100% written in Python, it has been shown to be faster and more memory efficient than tsfresh, seglearn or tsfel.[[28]](./Feature_engineering#cite_note-28)
- **seglearn** is an extension for multivariate, sequential time series data to the [scikit-learn](./Scikit-learn) Python library.[[29]](./Feature_engineering#cite_note-29)
- **tsfel** is a Python package for feature extraction on time series data.[[30]](./Feature_engineering#cite_note-30)
- **kats** is a Python toolkit for analyzing time series data.[[31]](./Feature_engineering#cite_note-31)

 

### Deep feature synthesis

 

The deep feature synthesis (DFS) algorithm beat 615 of 906 human teams in a competition.[[32]](./Feature_engineering#cite_note-32)[[33]](./Feature_engineering#cite_note-33)

 

## Feature stores

 

The [feature store](./Feature_store) is where the features are stored and organized for the explicit purpose of being used to either train models (by data scientists) or make predictions (by applications that have a trained model). It is a central location where you can either create or update groups of features created from multiple different data sources, or create and update new datasets from those feature groups for training models or for use in applications that do not want to compute the features but just retrieve them when it needs them to make predictions.[[34]](./Feature_engineering#cite_note-34)

 

A feature store includes the ability to store code used to generate features, apply the code to raw data, and serve those features to models upon request. Useful capabilities include feature versioning and policies governing the circumstances under which features can be used.[[35]](./Feature_engineering#cite_note-35)

 

Feature stores can be standalone software tools or built into machine learning platforms.

 

## Alternatives

 

Feature engineering can be a time-consuming and error-prone process, as it requires domain expertise and often involves trial and error.[[36]](./Feature_engineering#cite_note-36)[[37]](./Feature_engineering#cite_note-37) [Deep learning algorithms](./Deep_learning) may be used to process a large raw dataset without having to resort to feature engineering.[[38]](./Feature_engineering#cite_note-38) However, deep learning algorithms still require careful preprocessing and cleaning of the input data.[[39]](./Feature_engineering#cite_note-39) In addition, choosing the right architecture, hyperparameters, and optimization algorithm for a deep neural network can be a challenging and iterative process.[[40]](./Feature_engineering#cite_note-40)

 

## See also

 
- [Covariate](./Covariate)
- [Data transformation](./Data_transformation_(statistics))
- [Feature extraction](./Feature_extraction)
- [Feature learning](./Feature_learning)
- [Hashing trick](./Hashing_trick)
- [Instrumental variables estimation](./Instrumental_variables_estimation)
- [Kernel method](./Kernel_method)
- [List of datasets for machine learning research](./List_of_datasets_for_machine_learning_research)
- [Scale co-occurrence matrix](./Scale_co-occurrence_matrix)
- [Space mapping](./Space_mapping)

 


