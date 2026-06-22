---
source: https://en.wikipedia.org/wiki/Feature_engineering
fetched: 2026-06-21
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

 

## References

  
1. [↑](./Feature_engineering#cite_ref-1) Hastie, Trevor; Tibshirani, Robert; Friedman, Jerome H. (2009). [*The Elements of Statistical Learning: Data Mining, Inference, and Prediction*](https://books.google.com/books?id=eBSgoAEACAAJ). Springer. [ISBN](./ISBN_(identifier)) [978-0-387-84884-6](./Special:BookSources/978-0-387-84884-6).
2. [1](./Feature_engineering#cite_ref-auto1_2-0) [2](./Feature_engineering#cite_ref-auto1_2-1) [3](./Feature_engineering#cite_ref-auto1_2-2) Sharma, Shubham; Nayak, Richi; Bhaskar, Ashish (2024-05-01). ["Multi-view feature engineering for day-to-day joint clustering of multiple traffic datasets"](https://doi.org/10.1016%2Fj.trc.2024.104607). *Transportation Research Part C: Emerging Technologies*. **162** 104607. [Bibcode](./Bibcode_(identifier)):[2024TRPC..16204607S](https://ui.adsabs.harvard.edu/abs/2024TRPC..16204607S). [doi](./Doi_(identifier)):[10.1016/j.trc.2024.104607](https://doi.org/10.1016%2Fj.trc.2024.104607). [ISSN](./ISSN_(identifier)) [0968-090X](https://search.worldcat.org/issn/0968-090X).
3. [↑](./Feature_engineering#cite_ref-3) Shalev-Shwartz, Shai; Ben-David, Shai (2014). *Understanding Machine Learning: From Theory to Algorithms*. Cambridge: Cambridge University Press. [ISBN](./ISBN_(identifier)) [978-1-107-05713-5](./Special:BookSources/978-1-107-05713-5).
4. [↑](./Feature_engineering#cite_ref-4) Murphy, Kevin P. (2022). *Probabilistic Machine Learning*. Cambridge, Massachusetts: The MIT Press (Copyright 2022 Massachusetts Institute of Technology, this work is subject to a Creative Commons CC-BY-NC-ND license). [ISBN](./ISBN_(identifier)) [978-0-262-04682-4](./Special:BookSources/978-0-262-04682-4).
5. [↑](./Feature_engineering#cite_ref-5) MacQueron C (2021). [SOLID-LIQUID MIXING IN STIRRED TANKS: Modeling, Validation, Design Optimization and Suspension Quality Prediction](https://www.researchgate.net/publication/353947052) (Report). [doi](./Doi_(identifier)):[10.13140/RG.2.2.11074.84164/1](https://doi.org/10.13140%2FRG.2.2.11074.84164%2F1).
6. [↑](./Feature_engineering#cite_ref-6) Lee, Daniel D.; Seung, H. Sebastian (1999). ["Learning the parts of objects by non-negative matrix factorization"](https://www.nature.com/articles/44565). *Nature*. **401** (6755): 788–791. [Bibcode](./Bibcode_(identifier)):[1999Natur.401..788L](https://ui.adsabs.harvard.edu/abs/1999Natur.401..788L). [doi](./Doi_(identifier)):[10.1038/44565](https://doi.org/10.1038%2F44565). [ISSN](./ISSN_(identifier)) [1476-4687](https://search.worldcat.org/issn/1476-4687). [PMID](./PMID_(identifier)) [10548103](https://pubmed.ncbi.nlm.nih.gov/10548103).
7. [↑](./Feature_engineering#cite_ref-7) Wang, Hua; Nie, Feiping; Huang, Heng; Ding, Chris (2011). ["Nonnegative Matrix Tri-factorization Based High-Order Co-clustering and Its Fast Implementation"](https://dx.doi.org/10.1109/icdm.2011.109). *2011 IEEE 11th International Conference on Data Mining*. IEEE. pp. 774–783. [doi](./Doi_(identifier)):[10.1109/icdm.2011.109](https://doi.org/10.1109%2Ficdm.2011.109). [ISBN](./ISBN_(identifier)) [978-1-4577-2075-8](./Special:BookSources/978-1-4577-2075-8).
8. [↑](./Feature_engineering#cite_ref-8) Lim, Lek-Heng; Comon, Pierre (2009-04-12). "Nonnegative approximations of nonnegative tensors". [arXiv](./ArXiv_(identifier)):[0903.4530](https://arxiv.org/abs/0903.4530) [[cs.NA](https://arxiv.org/archive/cs.NA)].
9. [↑](./Feature_engineering#cite_ref-9) Nayak, Richi; Luong, Khanh (2023). "Multi-aspect Learning". *Intelligent Systems Reference Library*. **242**. [doi](./Doi_(identifier)):[10.1007/978-3-031-33560-0](https://doi.org/10.1007%2F978-3-031-33560-0). [ISBN](./ISBN_(identifier)) [978-3-031-33559-4](./Special:BookSources/978-3-031-33559-4). [ISSN](./ISSN_(identifier)) [1868-4394](https://search.worldcat.org/issn/1868-4394).
10. [↑](./Feature_engineering#cite_ref-10) ["Feature engineering - Machine Learning Lens"](https://docs.aws.amazon.com/wellarchitected/latest/machine-learning-lens/feature-engineering.html). *docs.aws.amazon.com*. Retrieved 2024-03-01.
11. [↑](./Feature_engineering#cite_ref-11) ["Feature Engineering"](http://www.cs.princeton.edu/courses/archive/spring10/cos424/slides/18-feat.pdf) (PDF). 2010-04-22. Retrieved 12 November 2015.
12. [↑](./Feature_engineering#cite_ref-12) ["Feature engineering and selection"](http://www.cs.berkeley.edu/~jordan/courses/294-fall09/lectures/feature/slides.pdf) (PDF). Alexandre Bouchard-Côté. October 1, 2009. Retrieved 12 November 2015.
13. [↑](./Feature_engineering#cite_ref-13) ["Feature engineering in Machine Learning"](https://web.archive.org/web/20160304112056/https://ufal.mff.cuni.cz/~zabokrtsky/courses/npfl104/html/feature_engineering.pdf) (PDF). Zdenek Zabokrtsky. Archived from [the original](https://ufal.mff.cuni.cz/~zabokrtsky/courses/npfl104/html/feature_engineering.pdf) (PDF) on 4 March 2016. Retrieved 12 November 2015.
14. [1](./Feature_engineering#cite_ref-:0_14-0) [2](./Feature_engineering#cite_ref-:0_14-1) Knobbe AJ, Siebes A, Van Der Wallen D (1999). ["Multi-relational Decision Tree Induction"](https://link.springer.com/content/pdf/10.1007/978-3-540-48247-5_46.pdf) (PDF). *Principles of Data Mining and Knowledge Discovery*. Lecture Notes in Computer Science. Vol. 1704. pp. 378–383. [doi](./Doi_(identifier)):[10.1007/978-3-540-48247-5_46](https://doi.org/10.1007%2F978-3-540-48247-5_46). [ISBN](./ISBN_(identifier)) [978-3-540-66490-1](./Special:BookSources/978-3-540-66490-1).
15. [↑](./Feature_engineering#cite_ref-15) ["Its all about the features"](https://reality.ai/it-is-all-about-the-features/). *Reality AI Blog*. September 2017.
16. [↑](./Feature_engineering#cite_ref-16) Yin X, Han J, Yang J, Yu PS (2004). "CrossMine: Efficient classification across multiple database relations". *Proceedings. 20th International Conference on Data Engineering*. pp. 399–410. [doi](./Doi_(identifier)):[10.1109/ICDE.2004.1320014](https://doi.org/10.1109%2FICDE.2004.1320014). [ISBN](./ISBN_(identifier)) [0-7695-2065-0](./Special:BookSources/0-7695-2065-0). [S2CID](./S2CID_(identifier)) [1183403](https://api.semanticscholar.org/CorpusID:1183403).
17. [↑](./Feature_engineering#cite_ref-17) Frank R, Moser F, Ester M (2007). "A Method for Multi-relational Classification Using Single and Multi-feature Aggregation Functions". *Knowledge Discovery in Databases: PKDD 2007*. Lecture Notes in Computer Science. Vol. 4702. pp. 430–437. [doi](./Doi_(identifier)):[10.1007/978-3-540-74976-9_43](https://doi.org/10.1007%2F978-3-540-74976-9_43). [ISBN](./ISBN_(identifier)) [978-3-540-74975-2](./Special:BookSources/978-3-540-74975-2).
18. [↑](./Feature_engineering#cite_ref-18) ["What is Featuretools?"](https://featuretools.alteryx.com/en/stable/). Retrieved September 7, 2022.
19. [↑](./Feature_engineering#cite_ref-19) ["Featuretools - An open source python framework for automated feature engineering"](https://web.archive.org/web/20190818175732/https://www.featuretools.com/). Archived from [the original](https://www.featuretools.com/) on August 18, 2019. Retrieved September 7, 2022.
20. [↑](./Feature_engineering#cite_ref-20) ["github: alteryx/featuretools"](https://github.com/alteryx/featuretools). *[GitHub](./GitHub)*. Retrieved September 7, 2022.
21. [↑](./Feature_engineering#cite_ref-21) Sharma, Shubham, [*mcmd: Multi-view Classification framework based on Consensus Matrix Decomposition developed by Shubham Sharma at QUT*](https://github.com/ashishbhaskar/MCMD), retrieved 2024-04-14
22. [1](./Feature_engineering#cite_ref-auto2_22-0) [2](./Feature_engineering#cite_ref-auto2_22-1) Thanh Lam, Hoang; Thiebaut, Johann-Michael; Sinn, Mathieu; Chen, Bei; Mai, Tiep; Alkan, Oznur (2017-06-01). "One button machine for automating feature engineering in relational databases". [arXiv](./ArXiv_(identifier)):[1706.00327](https://arxiv.org/abs/1706.00327) [[cs.DB](https://arxiv.org/archive/cs.DB)].
23. [↑](./Feature_engineering#cite_ref-23) ["getML documentation"](https://docs.getml.com/latest/). Retrieved September 7, 2022.
24. [1](./Feature_engineering#cite_ref-auto_24-0) [2](./Feature_engineering#cite_ref-auto_24-1) [3](./Feature_engineering#cite_ref-auto_24-2) ["github: getml/getml-community"](https://github.com/getml/getml-community). *[GitHub](./GitHub)*. Retrieved September 7, 2022.
25. [↑](./Feature_engineering#cite_ref-25) ["tsfresh documentation"](https://tsfresh.readthedocs.io/en/latest). Retrieved September 7, 2022.
26. [↑](./Feature_engineering#cite_ref-26) ["Time Series FeatuRe Extraction on basis of Scalable Hypothesis tests (tsfresh – A Python package)"](https://www.researchgate.net/publication/324948288). Retrieved September 7, 2022.
27. [↑](./Feature_engineering#cite_ref-27) ["predict-idlab/tsflex"](https://github.com/predict-idlab/tsflex). *[GitHub](./GitHub)*. Retrieved September 7, 2022.
28. [↑](./Feature_engineering#cite_ref-28) Van Der Donckt, Jonas; Van Der Donckt, Jeroen; Deprost, Emiel; Van Hoecke, Sofie (2022). ["tsflex: Flexible time series processing & feature extraction"](https://www.sciencedirect.com/science/article/pii/S2352711021001904). *SoftwareX*. **17** 100971. [arXiv](./ArXiv_(identifier)):[2111.12429](https://arxiv.org/abs/2111.12429). [Bibcode](./Bibcode_(identifier)):[2022SoftX..1700971V](https://ui.adsabs.harvard.edu/abs/2022SoftX..1700971V). [doi](./Doi_(identifier)):[10.1016/j.softx.2021.100971](https://doi.org/10.1016%2Fj.softx.2021.100971). [S2CID](./S2CID_(identifier)) [244527198](https://api.semanticscholar.org/CorpusID:244527198). Retrieved September 7, 2022.
29. [↑](./Feature_engineering#cite_ref-29) ["seglearn user guide"](https://dmbee.github.io/seglearn/user_guide.html). Retrieved September 7, 2022.
30. [↑](./Feature_engineering#cite_ref-30) ["Welcome to TSFEL documentation!"](https://tsfel.readthedocs.io/en/latest/). Retrieved September 7, 2022.
31. [↑](./Feature_engineering#cite_ref-31) ["github: facebookresearch/Kats"](https://github.com/facebookresearch/Kats). *[GitHub](./GitHub)*. Retrieved September 7, 2022.
32. [↑](./Feature_engineering#cite_ref-32) ["Automating big-data analysis"](https://news.mit.edu/2015/automating-big-data-analysis-1016). 16 October 2015.
33. [↑](./Feature_engineering#cite_ref-33) Kanter, James Max; Veeramachaneni, Kalyan (2015). "Deep feature synthesis: Towards automating data science endeavors". *2015 IEEE International Conference on Data Science and Advanced Analytics (DSAA)*. pp. 1–10. [doi](./Doi_(identifier)):[10.1109/DSAA.2015.7344858](https://doi.org/10.1109%2FDSAA.2015.7344858). [ISBN](./ISBN_(identifier)) [978-1-4673-8272-4](./Special:BookSources/978-1-4673-8272-4). [S2CID](./S2CID_(identifier)) [206610380](https://api.semanticscholar.org/CorpusID:206610380).
34. [↑](./Feature_engineering#cite_ref-34) ["What is a feature store"](https://www.featurestore.org/what-is-a-feature-store). Retrieved 2022-04-19.
35. [↑](./Feature_engineering#cite_ref-35) ["An Introduction to Feature Stores"](https://phaseai.com/resources/intro-to-feature-stores). Retrieved 2021-04-15.
36. [↑](./Feature_engineering#cite_ref-36) ["Feature Engineering in Machine Learning"](https://www.section.io/engineering-education/feature-engineering-in-machine-learning/). *Engineering Education (EngEd) Program | Section*. Retrieved 2023-03-21.
37. [↑](./Feature_engineering#cite_ref-37) explorium_admin (2021-10-25). ["5 Reasons Why Feature Engineering is Challenging"](https://www.explorium.ai/blog/5-reasons-why-feature-engineering-is-challenging/). *Explorium*. Retrieved 2023-03-21.
38. [↑](./Feature_engineering#cite_ref-38) Spiegelhalter, D. J. (2019). *The art of statistics: learning from data*. [London] UK. [ISBN](./ISBN_(identifier)) [978-0-241-39863-0](./Special:BookSources/978-0-241-39863-0). [OCLC](./OCLC_(identifier)) [1064776283](https://search.worldcat.org/oclc/1064776283).`{{cite book}}`:  CS1 maint: location missing publisher ([link](./Category:CS1_maint:_location_missing_publisher))
39. [↑](./Feature_engineering#cite_ref-39) Sarker IH (November 2021). ["Deep Learning: A Comprehensive Overview on Techniques, Taxonomy, Applications and Research Directions"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8372231). *SN Computer Science*. **2** (6) 420. [doi](./Doi_(identifier)):[10.1007/s42979-021-00815-1](https://doi.org/10.1007%2Fs42979-021-00815-1). [PMC](./PMC_(identifier)) [8372231](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8372231). [PMID](./PMID_(identifier)) [34426802](https://pubmed.ncbi.nlm.nih.gov/34426802).
40. [↑](./Feature_engineering#cite_ref-40) Bengio, Yoshua (2012), ["Practical Recommendations for Gradient-Based Training of Deep Architectures"](https://dx.doi.org/10.1007/978-3-642-35289-8_26), *Neural Networks: Tricks of the Trade*, Lecture Notes in Computer Science, vol. 7700, Berlin, Heidelberg: Springer Berlin Heidelberg, pp. 437–478, [arXiv](./ArXiv_(identifier)):[1206.5533](https://arxiv.org/abs/1206.5533), [doi](./Doi_(identifier)):[10.1007/978-3-642-35289-8_26](https://doi.org/10.1007%2F978-3-642-35289-8_26), [ISBN](./ISBN_(identifier)) [978-3-642-35288-1](./Special:BookSources/978-3-642-35288-1), [S2CID](./S2CID_(identifier)) [10808461](https://api.semanticscholar.org/CorpusID:10808461), retrieved 2023-03-21

 

## Further reading

  
- Boehmke B, Greenwell B (2019). "Feature & Target Engineering". *Hands-On Machine Learning with R*. Chapman & Hall. pp. 41–75. [ISBN](./ISBN_(identifier)) [978-1-138-49568-5](./Special:BookSources/978-1-138-49568-5).
- Zheng A, Casari A (2018). *Feature Engineering for Machine Learning: Principles and Techniques for Data Scientists*. O'Reilly. [ISBN](./ISBN_(identifier)) [978-1-4919-5324-2](./Special:BookSources/978-1-4919-5324-2).
- Zumel N, Mount (2020). "Data Engineering and Data Shaping". *Practical Data Science with R* (2nd ed.). Manning. pp. 113–160. [ISBN](./ISBN_(identifier)) [978-1-61729-587-4](./Special:BookSources/978-1-61729-587-4).
- Abououf, M., Singh, S., Mizouni, R., Otrok, H. (2024), "Feature engineering and deep learning-based approach for event detection in Medical Internet of Things (MIoT)", *Internet of Things*, **26** 101191, Elsevier BV, [doi](./Doi_(identifier)):[10.1016/j.iot.2024.101191](https://doi.org/10.1016%2Fj.iot.2024.101191)
- Chicco D, Oneto L, Tavazzi E (December 2022). ["Eleven quick tips for data cleaning and feature engineering"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9754225). *PLOS Computational Biology*. **18** (12) e1010718. [Bibcode](./Bibcode_(identifier)):[2022PLSCB..18E0718C](https://ui.adsabs.harvard.edu/abs/2022PLSCB..18E0718C). [doi](./Doi_(identifier)):[10.1371/journal.pcbi.1010718](https://doi.org/10.1371%2Fjournal.pcbi.1010718). [PMC](./PMC_(identifier)) [9754225](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9754225). [PMID](./PMID_(identifier)) [36520712](https://pubmed.ncbi.nlm.nih.gov/36520712). [S2CID](./S2CID_(identifier)) [254733288](https://api.semanticscholar.org/CorpusID:254733288).