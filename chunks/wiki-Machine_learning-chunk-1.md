---
source: sources/wiki-Machine_learning.md
source_url: https://en.wikipedia.org/wiki/Machine_learning
chunk: 1/8
---

Subset of artificial intelligence For the journal, see [*Machine Learning* (journal)](./Machine_Learning_(journal)). "Statistical learning" redirects here. For statistical learning in linguistics, see [Statistical learning in language acquisition](./Statistical_learning_in_language_acquisition). 

 

 
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

 
| Part ofa serieson |
| --- |
| Artificial intelligence (AI) |
| Major goalsArtificial general intelligenceIntelligent agentRecursive self-improvementPlanningComputer visionGeneral game playingKnowledge representationNatural language processingRoboticsAI safety |
| ApproachesMachine learningSymbolicDeep learningBayesian networksEvolutionary algorithmsNeuro-symbolic AISystems integrationOpen-sourceAI data centers |
| ApplicationsBioinformaticsDeepfakeEarth sciencesFinanceGenerative AIArtAudioMusicGovernmentHealthcareIndustrySoftware developmentTranslationMilitaryPhysicsProjects |
| PhilosophyAI alignmentArtificial consciousnessThe bitter lessonChinese roomFriendly AIEthicsExistential riskTuring testUncanny valleyHuman–AI interaction |
| HistoryTimelineProgressAI winterAI boomAI bubble |
| ControversiesDeepfake pornographyTaylor Swift deepfake pornography controversyGrok sexual deepfake scandalGoogle Gemini image generation controversyIt's the Most Terrible Time of the YearPause Giant AI ExperimentsRemoval of Sam Altman from OpenAIStatement on AI RiskTay (chatbot)Théâtre D'opéra SpatialVoiceverse NFT plagiarism scandal |
| GlossaryGlossary |
| vte |

 

**Machine learning** (**ML**) is a field of study in [artificial intelligence](./Artificial_intelligence) concerned with the development and study of [statistical algorithms](./Computational_statistics) that can learn from  [data](./Data) and [generalize](./Generalize) to unseen data, and thus perform [tasks](./Task_(computing)) without being explicitly [programmed](./Computer_program).[[1]](./Machine_learning#cite_note-1) Advances in the field of [deep learning](./Deep_learning) have allowed [neural networks](./Neural_network_(machine_learning)), a class of statistical algorithms, to surpass many previous machine learning approaches in performance.

 

[Statistics](./Statistics) and [mathematical optimisation](./Mathematical_optimisation) methods compose the foundations of machine learning. [Data mining](./Data_mining) is a related field of study, focusing on [exploratory data analysis](./Exploratory_data_analysis) (EDA) through [unsupervised learning](./Unsupervised_learning).[[3]](./Machine_learning#cite_note-3)[[4]](./Machine_learning#cite_note-Friedman-1998-4)

 

From a theoretical viewpoint, [probably approximately correct learning](./Probably_approximately_correct_learning) provides a mathematical and statistical framework for describing machine learning. Most traditional machine learning and deep learning algorithms can be described as [empirical risk minimisation](./Empirical_risk_minimisation) under this framework.

  

## History

 For a chronological guide, see [Timeline of machine learning](./Timeline_of_machine_learning). 

The term *machine learning* was coined in 1959 by [Arthur Samuel](./Arthur_Samuel_(computer_scientist)), an [IBM](./IBM) employee and pioneer in the field of [computer gaming](./Computer_gaming) and [artificial intelligence](./Artificial_intelligence).[[5]](./Machine_learning#cite_note-Samuel-5)[[6]](./Machine_learning#cite_note-Kohavi-6) The synonym *self-teaching computers* was also used during this time period.[[7]](./Machine_learning#cite_note-cyberthreat-7)[[8]](./Machine_learning#cite_note-8)

 

The earliest machine learning program was introduced in the 1950s, when Samuel invented a [computer program](./Computer_program) that calculated the chance of winning in [checkers](./Checkers) for each side, but the history of machine learning is rooted in decades of efforts to study human cognitive processes.[[9]](./Machine_learning#cite_note-WhatIs-9) In 1949, Canadian psychologist [Donald Hebb](./Donald_O._Hebb) published the book *[The Organization of Behavior](./Organization_of_Behavior)*, in which he introduced a theoretical neural structure formed by certain interactions among [nerve cells](./Nerve_cells).[[10]](./Machine_learning#cite_note-10) The [Hebbian theory](./Hebbian_theory) of [neuron](./Neuron) interaction set the groundwork for how many machine learning algorithms work, with connected [artificial neurons](./Artificial_neuron) changing the strength of their connections based on data.[[9]](./Machine_learning#cite_note-WhatIs-9) Other researchers who have studied human [cognitive systems](./Cognitive_systems_engineering) contributed to the modern machine learning technologies as well, including  [Walter Pitts](./Walter_Pitts) and [Warren McCulloch](./Warren_Sturgis_McCulloch), who proposed the first mathematical model of neural networks including [algorithms](./Algorithm) that mirror human thought processes.[[9]](./Machine_learning#cite_note-WhatIs-9)[*[verification needed](./Wikipedia:Verifiability)*]

 

By the early 1960s, an experimental "learning machine" with [punched tape](./Punched_tape) memory, called Cybertron, had been developed by [Raytheon Company](./Raytheon_Company) to analyse [sonar](./Sonar) signals, [electrocardiograms](./Electrocardiography), and speech patterns using rudimentary [reinforcement learning](./Reinforcement_learning). It was repetitively "trained" by a human operator/teacher to recognise patterns and equipped with a "[goof](./Goof)" button to cause it to reevaluate incorrect decisions.[[11]](./Machine_learning#cite_note-11)[*[importance?](./Wikipedia:What_Wikipedia_is_not#Encyclopedic_content)*] A representative book[*[citation needed](./Wikipedia:Citation_needed)*] on research into machine learning during the 1960s was [Nils Nilsson](./Nils_John_Nilsson)'s book "Learning Machines", dealing mostly with machine learning for pattern [classification](./Classification).[[12]](./Machine_learning#cite_note-12) Interest related to [pattern recognition](./Pattern_recognition) continued into the 1970s, as described by Duda and Hart in 1973.[[13]](./Machine_learning#cite_note-13) In 1981, a report was given on using teaching strategies so that an [artificial neural network](./Artificial_neural_network) learns to recognise 40 characters (26 letters, 10 digits, and 4 special symbols) from a computer terminal.[[14]](./Machine_learning#cite_note-14)

 

[Tom M. Mitchell](./Tom_M._Mitchell) provided a widely quoted,[*[citation needed](./Wikipedia:Citation_needed)*] more formal definition of the algorithms studied in the machine learning field: "A computer program is said to learn from experience *E* with respect to some class of tasks *T* and performance measure *P* if its performance at tasks in *T*, as measured by *P*,  improves with experience *E*."[[15]](./Machine_learning#cite_note-Mitchell-1997-15) This definition of the tasks in which machine learning is concerned is fundamentally [operational](./Operational_definition) rather than defining the field in cognitive terms. This follows [Alan Turing](./Alan_Turing)'s proposal in his paper "[Computing Machinery and Intelligence](./Computing_Machinery_and_Intelligence)", in which the question, "Can machines think?", is replaced by asking whether machines can convincingly [imitate a human](./Turing_test) in its responses to human-posed questions.[[16]](./Machine_learning#cite_note-16)[[17]](./Machine_learning#cite_note-17)

 Modern&#x2D;day Machine Learning algorithms are broken into 3 algorithm types: Supervised Learning Algorithms, Unsupervised Learning Algorithms, and Reinforcement Learning Algorithms.<ref&#x3E;{{Cite web |date=2023&#x2D;08&#x2D;17 |title=Machine Learning Algorithms |url=https://www.geeksforgeeks.org/machine&#x2D;learning/machine&#x2D;learning&#x2D;algorithms/ |access&#x2D;date=2025&#x2D;09&#x2D;03 |website=GeeksforGeeks |language=en&#x2D;US}}</ref&#x3E;

* Current Supervised Learning Algorithms have objectives of classification and regression.
* Current Unsupervised Learning Algorithms have objectives of clustering, dimensionality reduction, and association rule.
* Current Reinforcement Learning Algorithms focus on decisions that must be made with respect to some previous, unknown time and are broken down to either be studies of model&#x2D;based methods or model&#x2D;free methods. 

In 2014 [Ian Goodfellow](./Ian_Goodfellow) and others introduced [generative adversarial networks](./Generative_adversarial_network) (GANs) which could produce realistic synthetic data.[[18]](./Machine_learning#cite_note-18) By 2016 [AlphaGo](./AlphaGo) had won against top human players in [Go](./Go_(game)) using [reinforcement learning](./Reinforcement_learning) techniques.[[19]](./Machine_learning#cite_note-19)

 


