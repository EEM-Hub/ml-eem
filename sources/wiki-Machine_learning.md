---
source: https://en.wikipedia.org/wiki/Machine_learning
fetched: 2026-06-21
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

 

## Relationships to other fields

 

### Artificial intelligence

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/b/bb/AI-ML-DL.svg/250px-AI-ML-DL.svg.png)](./File:AI-ML-DL.svg)[Deep learning](./Deep_learning) is a subset of machine learning, which is itself a subset of [artificial intelligence](./Artificial_intelligence).[[20]](./Machine_learning#cite_note-journalimcms.org-20) 

As a scientific endeavour, machine learning grew out of the quest for [artificial intelligence](./Artificial_intelligence) (AI). In the early days of AI as an [academic discipline](./Discipline_(academia)), some researchers were interested in having machines learn from data. They attempted to approach the problem with various symbolic methods, as well as what were then termed "[neural networks](./Artificial_neural_network)"; these were mostly [perceptrons](./Perceptron) and [other models](./ADALINE) that were later found to be reinventions of the [generalised linear models](./Generalised_linear_model) of statistics.[[21]](./Machine_learning#cite_note-21) [Probabilistic reasoning](./Probabilistic_reasoning) was also employed, especially in [automated medical diagnosis](./Automated_medical_diagnosis).[[22]](./Machine_learning#cite_note-aima-22): 488 

 

However, an increasing emphasis on the [logical, knowledge-based approach](./Symbolic_AI) caused a rift between AI and machine learning. Probabilistic systems were plagued by theoretical and practical problems of data acquisition and representation.[[22]](./Machine_learning#cite_note-aima-22): 488  By 1980, [expert systems](./Expert_system) had come to dominate AI, and statistics was out of favour.[[23]](./Machine_learning#cite_note-changing-23) Work on symbolic/knowledge-based learning continued within AI, leading to [inductive logic programming](./Inductive_logic_programming) (ILP), but the more statistical line of research was now outside the field of AI proper, in [pattern recognition](./Pattern_recognition) and [information retrieval](./Information_retrieval).[[22]](./Machine_learning#cite_note-aima-22): 708–710, 755  Neural network research was abandoned by AI and [computer science](./Computer_science) around the same time. This subfield, termed "[connectionism](./Connectionism)", was continued by researchers from other disciplines, including [John Hopfield](./John_Hopfield), [David Rumelhart](./David_Rumelhart), and [Geoffrey Hinton](./Geoffrey_Hinton). Their main success came in the mid-1980s with the reinvention of [backpropagation](./Backpropagation).[[22]](./Machine_learning#cite_note-aima-22): 25 

 

Machine learning (ML), reorganised and recognised as its own field, started to flourish in the 1990s. The field changed its goal from achieving artificial intelligence to tackling solvable problems of a practical nature. It shifted focus away from the [symbolic approaches](./Symbolic_artificial_intelligence) it had inherited from AI, and toward methods and models borrowed from statistics, [fuzzy logic](./Fuzzy_logic), and [probability theory](./Probability_theory).[[23]](./Machine_learning#cite_note-changing-23)

 

### Data compression

 This section is an excerpt from [Data compression § Machine learning](./Data_compression#Machine_learning).[[edit](https://en.wikipedia.org/w/index.php?title=Data_compression&action=edit)] 

There is a close connection between machine learning and compression. A system that predicts the [posterior probabilities](./Posterior_probabilities) of a sequence given its entire history can be used for optimal data compression (by using [arithmetic coding](./Arithmetic_coding) on the output distribution). Conversely, an optimal compressor can be used for prediction (by finding the symbol that compresses best, given the previous history). This equivalence has been used as a justification for using data compression as a benchmark for "general intelligence".[[24]](./Machine_learning#cite_note-Data_compression_Mahoney-24)[[25]](./Machine_learning#cite_note-Data_compression_Market_Efficiency-25)[[26]](./Machine_learning#cite_note-Data_compression_Ben-Gal-26)

 

An alternative view can show compression algorithms implicitly map strings into implicit [feature space vectors](./Feature_space_vector), and compression-based similarity measures compute similarity within these feature spaces. For each compressor C(.) we define an associated vector space ℵ, such that C(.) maps an input string x, corresponding to the vector norm ||~x||. An exhaustive examination of the feature spaces underlying all compression algorithms is precluded by space; instead, feature vectors chooses to examine three representative lossless compression methods, LZW, LZ77, and PPM.[[27]](./Machine_learning#cite_note-Data_compression_ScullyBrodley-27)

 

According to [AIXI](./AIXI) theory, a connection more directly explained in [Hutter Prize](./Hutter_Prize), the best possible compression of x is the smallest possible software that generates x. For example, in that model, a zip file's compressed size includes both the zip file and the unzipping software, since you can not unzip it without both, but there may be an even smaller combined form.

 

Examples of AI-powered audio/video compression software include [NVIDIA Maxine](./NVIDIA_Maxine), AIVC.[[28]](./Machine_learning#cite_note-28) Examples of software that can perform AI-powered image compression include [OpenCV](./OpenCV), [TensorFlow](./TensorFlow), [MATLAB](./MATLAB)'s Image Processing Toolbox (IPT) and High-Fidelity Generative Image Compression.[[29]](./Machine_learning#cite_note-29)

 

In [unsupervised machine learning](./Unsupervised_machine_learning), [k-means clustering](./K-means_clustering) can be utilized to compress data by grouping similar data points into clusters. This technique simplifies handling extensive datasets that lack predefined labels and finds widespread use in fields such as [image compression](./Image_compression).[[30]](./Machine_learning#cite_note-30)

 

Data compression aims to reduce the size of data files, enhancing storage efficiency and speeding up data transmission. K-means clustering, an unsupervised machine learning algorithm, is employed to partition a dataset into a specified number of clusters, k, each represented by the [centroid](./Centroid) of its points. This process condenses extensive datasets into a more compact set of representative points. Particularly beneficial in [image](./Image_processing) and [signal processing](./Signal_processing), k-means clustering aids in data reduction by replacing groups of data points with their centroids, thereby preserving the core information of the original data while significantly decreasing the required storage space.[[31]](./Machine_learning#cite_note-31)

 

[Large language models](./Large_language_model) (LLMs) are also efficient lossless data compressors on some data sets, as demonstrated by [DeepMind](./DeepMind)'s research with the Chinchilla 70B model. Developed by DeepMind, Chinchilla 70B effectively compressed data, outperforming conventional methods such as [Portable Network Graphics](./Portable_Network_Graphics) (PNG) for images and [Free Lossless Audio Codec](./Free_Lossless_Audio_Codec) (FLAC) for audio. It achieved compression of image and audio data to 43.4% and 16.4% of their original sizes, respectively. There is, however, some reason to be concerned that the data set used for testing overlaps the LLM training data set, making it possible that the Chinchilla 70B model is only an efficient compression tool on data it has already been trained on.[[32]](./Machine_learning#cite_note-32)[[33]](./Machine_learning#cite_note-33)

   

### Data mining

 

Machine learning and [data mining](./Data_mining) often employ the same methods and overlap significantly, but while machine learning focuses on prediction based on *known* properties learned from the training data, data mining focuses on the [discovery](./Discovery_(observation)) of previously *unknown* properties in the data (this is the analysis step of [knowledge discovery](./Knowledge_discovery) in databases). Data mining uses many machine learning methods, but with different goals; on the other hand, machine learning also employs data mining methods as "[unsupervised learning](./Unsupervised_learning)" or as a preprocessing step to improve learner accuracy. Much of the confusion between these two research communities (which often have separate conferences and separate journals, [[ECML PKDD]] being a major exception) comes from the basic assumptions they work with: in machine learning, performance is usually evaluated with respect to the ability to *reproduce known* knowledge, while in knowledge discovery and data mining (KDD) the key task is the discovery of previously *unknown* knowledge. Evaluated with respect to known knowledge, an uninformed (unsupervised) method will easily be outperformed by other supervised methods, while in a typical KDD task, supervised methods cannot be used due to the unavailability of training data.[*[citation needed](./Wikipedia:Citation_needed)*]

 

Machine learning also has intimate ties to [optimization](./Optimization): Many learning problems are formulated as minimisation of some [loss function](./Loss_function) on a training set of examples. Loss functions express the discrepancy between the predictions of the model being trained and the actual problem instances (for example, in classification, one wants to assign a [label](./Labeled_data) to instances, and models are trained to correctly predict the preassigned labels of a set of examples).[[34]](./Machine_learning#cite_note-34)

 

### Generalization

 

Characterizing the generalisation of various learning algorithms is an active topic of current research, especially for [deep learning](./Deep_learning) algorithms.[*[citation needed](./Wikipedia:Citation_needed)*]

 

### Statistics

 

Machine learning and [statistics](./Statistics) are closely related fields in terms of methods, but distinct in their principal goal: statistics draws population [inferences](./Statistical_inference) from a [sample](./Sample_(statistics)), while machine learning finds generalisable predictive patterns.[[35]](./Machine_learning#cite_note-35)

 

Conventional statistical analyses require the a priori selection of a model most suitable for the study data set. In addition, only significant or theoretically relevant variables based on previous experience are included for analysis. In contrast, machine learning is not built on a pre-structured model; rather, the data shape the model by detecting underlying patterns. The more variables (input) used to train the model, the more accurate the ultimate model will be.[[36]](./Machine_learning#cite_note-36)

 

[Leo Breiman](./Leo_Breiman) distinguished two statistical modelling paradigms: the data model and the algorithmic model,[[37]](./Machine_learning#cite_note-Cornell-University-Library-2001-37) wherein "algorithmic model" means more or less the machine learning algorithms like [Random forest](./Random_forest).[*[clarification needed](./Wikipedia:Please_clarify)*]

 

Some statisticians have adopted methods from machine learning, producing the field of *statistical learning*.[[38]](./Machine_learning#cite_note-islr-38)

 

### Statistical physics

 

Analytical and computational techniques derived from deep-rooted physics of disordered systems can be extended to large-scale problems, including machine learning, e.g., to analyse the weight space of [deep neural networks](./Deep_neural_network).[[39]](./Machine_learning#cite_note-SP_1-39) Statistical physics is thus finding applications in the area of [medical diagnostics](./Medical_diagnostics).[[40]](./Machine_learning#cite_note-SP_2-40)[*[clarification needed](./Wikipedia:Please_clarify)*]

 

##  Theory

 Main articles: [Computational learning theory](./Computational_learning_theory) and [Statistical learning theory](./Statistical_learning_theory) 

A core objective of a learner is to generalise from its experience.[[2]](./Machine_learning#cite_note-bishop2006-2)[[41]](./Machine_learning#cite_note-Mohri-2012-41) Generalisation in this context is the ability of a learning machine to perform accurately on new, unseen examples/tasks after having experienced a learning data set. The training examples come from some generally unknown probability distribution (considered representative of the space of occurrences) and the learner has to build a general model about this space that enables it to produce sufficiently accurate predictions in new cases.

 

The computational analysis of machine learning algorithms and their performance is a branch of [theoretical computer science](./Theoretical_computer_science) known as [computational learning theory](./Computational_learning_theory) via the [probably approximately correct learning](./Probably_approximately_correct_learning) model.[*[clarification needed](./Wikipedia:Please_clarify)*] Because training sets are finite and the future is uncertain, learning theory usually does not yield guarantees of the performance of algorithms. Instead, probabilistic bounds on the performance are quite common. The [bias–variance decomposition](./Bias–variance_decomposition) is one way to quantify generalisation [error](./Errors_and_residuals).[*[citation needed](./Wikipedia:Citation_needed)*]

 

For the best performance in the context of generalisation, the complexity of the hypothesis should match the complexity of the function underlying the data. If the hypothesis is less complex than the function, then the model has underfitted the data. If the complexity of the model is increased in response, then the training error decreases. But if the hypothesis is too complex, then the model is subject to [overfitting](./Overfitting) and generalisation will be poorer.[[42]](./Machine_learning#cite_note-alpaydin-42)

 

In addition to performance bounds, learning theorists study the time complexity and feasibility of learning. In computational learning theory, a computation is considered feasible if it can be done in [polynomial time](./Time_complexity#Polynomial_time). There are two kinds of [time complexity](./Time_complexity) results: Positive results show that a certain class of functions can be learned in polynomial time. Negative results show that certain classes cannot be learned in polynomial time.[*[citation needed](./Wikipedia:Citation_needed)*]

 

## Approaches

 

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/4/4d/Supervised_and_unsupervised_learning.png/330px-Supervised_and_unsupervised_learning.png)](./File:Supervised_and_unsupervised_learning.png)In [supervised learning](./Supervised_learning), the training data is labelled with the expected answers, while in [unsupervised learning](./Unsupervised_learning), the model identifies patterns or structures in unlabelled data. 

Machine learning approaches are traditionally divided into three broad categories, which correspond to learning paradigms, depending on the nature of the "signal" or "feedback" available to the learning system:

 
- [Supervised learning](./Supervised_learning): The computer is presented with example inputs and their desired outputs, given by a "teacher", and the goal is to learn a general rule that [maps](./Map_(mathematics)) inputs to outputs.
- [Unsupervised learning](./Unsupervised_learning): No labels are given to the learning algorithm, leaving it on its own to find structure in its input. Unsupervised learning can be a goal in itself (discovering hidden patterns in data) or a means towards an end ([feature learning](./Feature_learning)).
- [Reinforcement learning](./Reinforcement_learning): A computer program interacts with a dynamic environment in which it must perform a certain goal (such as [driving a vehicle](./Autonomous_car) or playing a game against an opponent). As it navigates its problem space, the program is provided rewards as feedback, which it tries to maximize, thus resulting in the program learning from experience.[[2]](./Machine_learning#cite_note-bishop2006-2)

 

Although each algorithm has advantages and limitations, no single algorithm works for all problems.[[43]](./Machine_learning#cite_note-43)[[44]](./Machine_learning#cite_note-44)[[45]](./Machine_learning#cite_note-45)

 

### Supervised learning

 Main article: [Supervised learning](./Supervised_learning) [![](//upload.wikimedia.org/wikipedia/commons/thumb/2/2a/Svm_max_sep_hyperplane_with_margin.png/250px-Svm_max_sep_hyperplane_with_margin.png)](./File:Svm_max_sep_hyperplane_with_margin.png)A [support-vector machine](./Support-vector_machine) is a supervised learning model that divides the data into regions separated by a [linear boundary](./Linear_classifier). Here, the linear boundary divides the black circles from the white. 

Supervised learning algorithms build a mathematical model of a set of data that contains both the inputs and the desired outputs.[[46]](./Machine_learning#cite_note-46) The data, known as [training data](./Training_data), consists of a set of training examples. Each training example has one or more inputs and the desired output, also known as a supervisory signal. In the mathematical model, each training example is represented by an [array](./Array_data_structure) or vector, sometimes called a [feature vector](./Feature_vector), and the training data is represented by a [matrix](./Matrix_(mathematics)). Through [iterative optimisation](./Mathematical_optimization#Computational_optimization_techniques) of an [objective function](./Loss_function), supervised learning algorithms learn a function that can be used to predict the output associated with new inputs.[[47]](./Machine_learning#cite_note-47) An optimal function allows the algorithm to correctly determine the output for inputs that were not a part of the training data. An algorithm that improves the accuracy of its outputs or predictions over time is said to have learned to perform that task.[[15]](./Machine_learning#cite_note-Mitchell-1997-15)

 

Types of supervised-learning algorithms include [active learning](./Active_learning_(machine_learning)), [classification](./Statistical_classification) and [regression](./Regression_analysis).[[48]](./Machine_learning#cite_note-Alpaydin-2010-48) Classification algorithms are used when the outputs are restricted to a limited set of values, while regression algorithms are used when the outputs can take any numerical value within a range. For example, in a classification algorithm that filters emails, the input is an incoming email, and the output is the folder in which to file the email. In contrast, regression is used for tasks such as predicting a person's height based on factors like age and genetics or forecasting future temperatures based on historical data.[[49]](./Machine_learning#cite_note-49)

 

[Similarity learning](./Similarity_learning) is an area of supervised machine learning closely related to regression and classification, but the goal is to learn from examples using a similarity function that measures how similar or related two objects are. It has applications in [ranking](./Ranking), [recommendation systems](./Recommender_system), visual identity tracking, face verification, and speaker verification.

 

### Unsupervised learning

 Main article: [Unsupervised learning](./Unsupervised_learning)See also: [Cluster analysis](./Cluster_analysis) 

Unsupervised learning algorithms find structures in data that has not been labelled, classified or categorised. Instead of responding to feedback, unsupervised learning algorithms identify commonalities in the data and react based on the presence or absence of such commonalities in each new piece of data. Central applications of unsupervised machine learning include clustering, [dimensionality reduction](./Dimensionality_reduction),[[4]](./Machine_learning#cite_note-Friedman-1998-4) and [density estimation](./Density_estimation).[[50]](./Machine_learning#cite_note-JordanBishop2004-50)

 

Cluster analysis is the assignment of a set of observations into subsets (called *clusters*) so that observations within the same cluster are similar according to one or more predesignated criteria, while observations drawn from different clusters are dissimilar. Different clustering techniques make different assumptions on the structure of the data, often defined by some *similarity metric* and evaluated, for example, by *internal compactness*, or the similarity between members of the same cluster, and *separation*, the difference between clusters. Other methods are based on *estimated density* and *graph connectivity*.

 

A special type of unsupervised learning called [self-supervised learning](./Self-supervised_learning) involves training a model by generating the supervisory signal from the data itself.[[51]](./Machine_learning#cite_note-51)[[52]](./Machine_learning#cite_note-52)

 

#### Dimensionality reduction

 

[Dimensionality reduction](./Dimensionality_reduction) is a process of reducing the number of random variables under consideration by obtaining a set of principal variables.[[53]](./Machine_learning#cite_note-53) In other words, it is a process of reducing the dimension of the [feature](./Feature_(machine_learning)) set, also called the "number of features". Most of the dimensionality reduction techniques can be considered as either feature elimination or [extraction](./Feature_extraction). One of the popular methods of dimensionality reduction is [principal component analysis](./Principal_component_analysis) (PCA). PCA involves changing higher-dimensional data (e.g., 3D) to a smaller space (e.g., 2D).
The [manifold hypothesis](./Manifold_hypothesis) proposes that high-dimensional data sets lie along low-dimensional [manifolds](./Manifold), and many dimensionality reduction techniques make this assumption, leading to the areas of [manifold learning](./Manifold_learning) and [manifold regularisation](./Manifold_regularisation).

 

### Semi-supervised learning

 Main article: [Semi-supervised learning](./Semi-supervised_learning) 

Semi-supervised learning falls between [unsupervised learning](./Unsupervised_learning) (without any labelled training data) and [supervised learning](./Supervised_learning) (with completely labelled training data). Some of the training examples are missing training labels, yet many machine-learning researchers have found that unlabelled data, when used in conjunction with a small amount of labelled data, can produce a considerable improvement in learning accuracy.

 

In [weakly supervised learning](./Weak_supervision), the training labels are noisy, limited, or imprecise; however, these labels are often cheaper to obtain, resulting in larger effective training sets.[[54]](./Machine_learning#cite_note-54)

 

### Reinforcement learning

 Main article: [Reinforcement learning](./Reinforcement_learning) [![](//upload.wikimedia.org/wikipedia/commons/thumb/1/1b/Reinforcement_learning_diagram.svg/250px-Reinforcement_learning_diagram.svg.png)](./File:Reinforcement_learning_diagram.svg)In reinforcement learning, an agent takes actions in an environment: these produce a reward or a representation of the state, which is fed back to the agent. 

Reinforcement learning is an area of machine learning concerned with how [software agents](./Software_agent) ought to take [actions](./Action_selection) in an environment to maximise some notion of cumulative reward. Due to its generality, the field is studied in many other disciplines, such as [game theory](./Game_theory), [control theory](./Control_theory), [operations research](./Operations_research), [information theory](./Information_theory), [simulation-based optimisation](./Simulation-based_optimisation), [multi-agent systems](./Multi-agent_system), [swarm intelligence](./Swarm_intelligence), [statistics](./Statistics) and [genetic algorithms](./Genetic_algorithm). In reinforcement learning, the environment is typically represented as a [Markov decision process](./Markov_decision_process) (MDP). Many reinforcement learning algorithms use [dynamic programming](./Dynamic_programming) techniques.[[55]](./Machine_learning#cite_note-55) Reinforcement learning algorithms do not assume knowledge of an exact mathematical model of the MDP and are used when exact models are infeasible. Reinforcement learning algorithms are used in autonomous vehicles or in learning to play a game against a human opponent.

 

### Other types

 

Other approaches have been developed which do not fit neatly into this three-fold categorisation, and sometimes more than one is used by the same machine learning system. For example, [topic modelling](./Topic_model), [meta-learning](./Meta-learning_(computer_science)).[[56]](./Machine_learning#cite_note-56)

 

#### Self-learning

 

Self-learning, as a machine learning paradigm, was introduced in 1982 along with a neural network capable of self-learning, named *crossbar adaptive array* (CAA).[[57]](./Machine_learning#cite_note-57)[[58]](./Machine_learning#cite_note-58) It gives a solution to the problem learning without any external reward, by introducing emotion as an internal reward. Emotion is used as a state evaluation of a self-learning agent. The CAA self-learning algorithm computes, in a crossbar fashion, both decisions about actions and emotions (feelings) about consequence situations. The system is driven by the interaction between cognition and emotion.[[59]](./Machine_learning#cite_note-59)
The self-learning algorithm updates a memory matrix W =||w(a,s)|| such that in each iteration executes the following machine learning routine: 

 
1. in situation *s* act *a*
2. receive a consequence situation *s*'
3. compute emotion of being in the consequence situation *v(s')*
4. update crossbar memory  *w'(a,s) = w(a,s) + v(s')*

 

It is a system with only one input, situation, and only one output, action (or behaviour) a. There is neither a separate reinforcement input nor an advice input from the environment. The backpropagated value (secondary reinforcement) is the emotion toward the consequence situation. The CAA exists in two environments, one is the behavioural environment where it behaves, and the other is the genetic environment, wherefrom it initially and only once receives initial emotions about situations to be encountered in the behavioural environment. After receiving the genome (species) vector from the genetic environment, the CAA learns a goal-seeking behaviour in an environment that contains both desirable and undesirable situations.[[60]](./Machine_learning#cite_note-60)

 

#### Feature learning

 Main article: [Feature learning](./Feature_learning) 

Several learning algorithms aim at discovering better representations of the inputs provided during training.[[61]](./Machine_learning#cite_note-pami-61) Classic examples include [principal component analysis](./Principal_component_analysis) and cluster analysis. Feature learning algorithms, also called representation learning algorithms, often attempt to preserve the information in their input but also transform it in a way that makes it useful, often as a pre-processing step before performing classification or predictions. This technique allows reconstruction of the inputs coming from the unknown data-generating distribution, while not being necessarily faithful to configurations that are implausible under that distribution. This replaces manual [feature engineering](./Feature_engineering), and allows a machine to both learn the features and use them to perform a specific task.

 

Feature learning can be either supervised or unsupervised. In supervised feature learning, features are learned using labelled input data. Examples include [artificial neural networks](./Artificial_neural_network), [multilayer perceptrons](./Multilayer_perceptron), and supervised [dictionary learning](./Dictionary_learning). In unsupervised feature learning, features are learned with unlabelled input data.  Examples include dictionary learning, [independent component analysis](./Independent_component_analysis), [autoencoders](./Autoencoder), [matrix factorisation](./Matrix_decomposition)[[62]](./Machine_learning#cite_note-62) and various forms of [clustering](./Cluster_analysis).[[63]](./Machine_learning#cite_note-coates2011-63)[[64]](./Machine_learning#cite_note-64)[[65]](./Machine_learning#cite_note-jurafsky-65)

 

[Manifold learning](./Manifold_learning) algorithms attempt to do so under the constraint that the learned representation is low-dimensional. [Sparse coding](./Sparse_coding) algorithms attempt to do so under the constraint that the learned representation is sparse, meaning that the mathematical model has many zeros. [Multilinear subspace learning](./Multilinear_subspace_learning) algorithms aim to learn low-dimensional representations directly from [tensor](./Tensor) representations for multidimensional data, without reshaping them into higher-dimensional vectors.[[66]](./Machine_learning#cite_note-66) [Deep learning](./Deep_learning) algorithms discover multiple levels of representation, or a hierarchy of features, with higher-level, more abstract features defined in terms of (or generating) lower-level features. It has been argued that an intelligent machine learns a representation that disentangles the underlying factors of variation that explain the observed data.[[67]](./Machine_learning#cite_note-67)

 

Feature learning is motivated by the fact that machine learning tasks such as classification often require input that is mathematically and computationally convenient to process. However, real-world data such as images, video, and sensory data have not yielded attempts to algorithmically define specific features. An alternative is to discover such features or representations through examination, without relying on explicit algorithms.

 

#### Sparse dictionary learning

 Main article: [Sparse dictionary learning](./Sparse_dictionary_learning) 

Sparse dictionary learning is a feature learning method where a training example is represented as a linear combination of [basis functions](./Basis_function) and assumed to be a [sparse matrix](./Sparse_matrix). The method is [strongly NP-hard](./Strongly_NP-hard) and difficult to solve approximately.[[68]](./Machine_learning#cite_note-68) A popular [heuristic](./Heuristic) method for sparse dictionary learning is the [*k*-SVD](./K-SVD) algorithm. Sparse dictionary learning has been applied in several contexts. In classification, the problem is to determine the class to which a previously unseen training example belongs. For a dictionary where each class has already been built, a new training example is associated with the class that is best sparsely represented by the corresponding dictionary. Sparse dictionary learning has also been applied in [image denoising](./Image_denoising). The key idea is that a clean image patch can be sparsely represented by an image dictionary, but the noise cannot.[[69]](./Machine_learning#cite_note-69)

 

#### Anomaly detection

 Main article: [Anomaly detection](./Anomaly_detection) 

In [data mining](./Data_mining), anomaly detection, also known as outlier detection, is the identification of rare items, events or observations that raise suspicions by differing significantly from the majority of the data.[[70]](./Machine_learning#cite_note-Zimek-2017-70) Typically, the anomalous items represent an issue such as [bank fraud](./Bank_fraud), a structural defect, medical problems or errors in a text. Anomalies are referred to as [outliers](./Outlier), novelties, noise, deviations and exceptions.[[71]](./Machine_learning#cite_note-71)

 

In particular, in the context of abuse and network intrusion detection, the interesting objects are often not rare, but unexpected bursts of inactivity. This pattern does not adhere to the common statistical definition of an outlier as a rare object. Many outlier detection methods (in particular, unsupervised algorithms) will fail on such data unless aggregated appropriately. Instead, a cluster analysis algorithm may be able to detect the micro-clusters formed by these patterns.[[72]](./Machine_learning#cite_note-72)

 

Three broad categories of anomaly detection techniques exist.[[73]](./Machine_learning#cite_note-ChandolaSurvey-73) Unsupervised anomaly detection techniques detect anomalies in an unlabelled test data set under the assumption that the majority of the instances in the data set are normal, by looking for instances that seem to fit the least to the remainder of the data set. Supervised anomaly detection techniques require a data set that has been labelled as "normal" and "abnormal" and involves training a classifier (the key difference from many other statistical classification problems is the inherently unbalanced nature of outlier detection). Semi-supervised anomaly detection techniques construct a model representing normal behaviour from a given normal training data set and then test the likelihood of a test instance being generated by the model.

 

#### Robot learning

 

[Robot learning](./Robot_learning) is inspired by a multitude of machine learning methods, starting from supervised learning, reinforcement learning,[[74]](./Machine_learning#cite_note-74)[[75]](./Machine_learning#cite_note-75) and finally [meta-learning](./Meta-learning_(computer_science)) (e.g. MAML).

 

#### Association rules

 Main article: [Association rule learning](./Association_rule_learning)See also: [Inductive logic programming](./Inductive_logic_programming) 

Association rule learning is a [rule-based machine learning](./Rule-based_machine_learning) method for discovering relationships between variables in large databases. It is intended to identify strong rules discovered in databases using some measure of "interestingness".[[76]](./Machine_learning#cite_note-piatetsky-76)

 

Rule-based machine learning is a general term for any machine learning method that identifies, learns, or evolves "rules" to store, manipulate or apply knowledge. The defining characteristic of a rule-based machine learning algorithm is the identification and utilisation of a set of relational rules that collectively represent the knowledge captured by the system. This is in contrast to other machine learning algorithms that commonly identify a singular model that can be universally applied to any instance in order to make a prediction.[[77]](./Machine_learning#cite_note-77) Rule-based machine learning approaches include [learning classifier systems](./Learning_classifier_system), association rule learning, and [artificial immune systems](./Artificial_immune_system).

 

Based on the concept of strong rules, [Rakesh Agrawal](./Rakesh_Agrawal_(computer_scientist)), [Tomasz Imieliński](./Tomasz_Imieliński) and Arun Swami introduced association rules for discovering regularities between products in large-scale transaction data recorded by [point-of-sale](./Point-of-sale) (POS) systems in supermarkets.[[78]](./Machine_learning#cite_note-mining-78) For example, the rule     {  o n i o n s , p o t a t o e s  } ⇒ ⇒  {  b u r g e r  }   {\displaystyle \{\mathrm {onions,potatoes} \}\Rightarrow \{\mathrm {burger} \}}  ![{\displaystyle \{\mathrm {onions,potatoes} \}\Rightarrow \{\mathrm {burger} \}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2e6daa2c8e553e87e411d6e0ec66ae596c3c9381) found in the sales data of a supermarket would indicate that if a customer buys onions and potatoes together, they are likely to also buy hamburger meat. Such information can be used as the basis for decisions about marketing activities such as promotional [pricing](./Pricing) or [product placements](./Product_placement). In addition to [market basket analysis](./Market_basket_analysis), association rules are employed today in application areas including [Web usage mining](./Web_usage_mining), [intrusion detection](./Intrusion_detection), [continuous production](./Continuous_production), and [bioinformatics](./Bioinformatics). In contrast with [sequence mining](./Sequence_mining), association rule learning typically does not consider the order of items either within a transaction or across transactions.

 

[Learning classifier systems](./Learning_classifier_system) (LCS) are a family of rule-based machine learning algorithms that combine a discovery component, typically a [genetic algorithm](./Genetic_algorithm), with a learning component, performing either [supervised learning](./Supervised_learning), [reinforcement learning](./Reinforcement_learning), or [unsupervised learning](./Unsupervised_learning). They seek to identify a set of context-dependent rules that collectively store and apply knowledge in a [piecewise](./Piecewise) manner to make predictions.[[79]](./Machine_learning#cite_note-79)

 

[Inductive logic programming](./Inductive_logic_programming) (ILP) is an approach to rule learning using [logic programming](./Logic_programming) as a uniform representation for input examples, background knowledge, and hypotheses. Given an encoding of the known background knowledge and a set of examples represented as a logical database of facts, an ILP system will derive a hypothesized logic program that [entails](./Entailment) all positive and no negative examples. [Inductive programming](./Inductive_programming) is a related field that considers any kind of programming language for representing hypotheses (and not only logic programming), such as [functional programs](./Functional_programming).

 

Inductive logic programming is particularly useful in [bioinformatics](./Bioinformatics) and [natural language processing](./Natural_language_processing). [Gordon Plotkin](./Gordon_Plotkin) and [Ehud Shapiro](./Ehud_Shapiro) laid the initial theoretical foundation for inductive machine learning in a logical setting.[[80]](./Machine_learning#cite_note-80)[[81]](./Machine_learning#cite_note-81)[[82]](./Machine_learning#cite_note-82) Shapiro built their first implementation (Model Inference System) in 1981: a [Prolog](./Prolog) program that inductively inferred logic programs from positive and negative examples.[[83]](./Machine_learning#cite_note-83) The term *inductive* here refers to [philosophical](./Inductive_reasoning) induction, suggesting a theory to explain observed facts, rather than [mathematical induction](./Mathematical_induction), proving a property for all members of a well-ordered set.

 

## Models

 

A **machine learning model** is a type of [mathematical model](./Mathematical_model) that, once "trained" on a given dataset, can be used to make predictions or classifications on new data. During training, a learning algorithm iteratively adjusts the model's internal parameters to minimise errors in its predictions.[[84]](./Machine_learning#cite_note-84) By extension, the term "model" can refer to several levels of specificity, from a general class of models and their associated learning algorithms to a fully trained model with all its internal parameters tuned.[[85]](./Machine_learning#cite_note-85)

 

Various types of models have been used and researched for machine learning systems, picking the best model for a task is called [model selection](./Model_selection).

 

### Artificial neural networks

 Main article: [Artificial neural network](./Artificial_neural_network)See also: [Deep learning](./Deep_learning) [![](//upload.wikimedia.org/wikipedia/commons/thumb/4/46/Colored_neural_network.svg/250px-Colored_neural_network.svg.png)](./File:Colored_neural_network.svg)An artificial neural network is an interconnected group of nodes, akin to the vast network of [neurons](./Neuron) in a [brain](./Brain). Here, each circular node represents an [artificial neuron](./Artificial_neuron) and an arrow represents a connection from the output of one artificial neuron to the input of another. 

Artificial neural networks (ANNs), or [connectionist](./Connectionism) systems, are computing systems vaguely inspired by the [biological neural networks](./Biological_neural_network) that constitute animal [brains](./Brain). Such systems "learn" to perform tasks by considering examples, generally without being programmed with any task-specific rules.

 

An ANN is a model based on a collection of connected units or nodes called "[artificial neurons](./Artificial_neuron)", which loosely model the [neurons](./Neuron) in a biological brain. Each connection, like the [synapses](./Synapse) in a biological brain, can transmit information, a "signal", from one artificial neuron to another. An artificial neuron that receives a signal can process it and then signal additional artificial neurons connected to it. In common ANN implementations, the signal at a connection between artificial neurons is a [real number](./Real_number), and the output of each artificial neuron is computed by some non-linear function of the sum of its inputs. The connections between artificial neurons are called "edges". Artificial neurons and edges typically have a [weight](./Weight_(mathematics)) that adjusts as learning proceeds. The weight increases or decreases the strength of the signal at a connection. Artificial neurons may have a threshold such that the signal is only sent if the aggregate signal crosses that threshold. Typically, artificial neurons are aggregated into layers. Different layers may perform different kinds of transformations on their inputs. Signals travel from the first layer (the input layer) to the last layer (the output layer), possibly after traversing the layers multiple times.

 

The original goal of the ANN approach was to solve problems in the same way that a [human brain](./Human_brain) would. However, over time, attention moved to performing specific tasks, leading to deviations from [biology](./Biology). Artificial neural networks have been used on a variety of tasks, including [computer vision](./Computer_vision), [speech recognition](./Speech_recognition), [machine translation](./Machine_translation), [social network](./Social_network) filtering, [playing board and video games](./General_game_playing) and [medical diagnosis](./Medical_diagnosis).

 

[Deep learning](./Deep_learning) consists of multiple hidden layers in an artificial neural network. This approach tries to model the way the human brain processes light and sound into vision and hearing. Some successful applications of deep learning are computer vision and speech recognition.[[86]](./Machine_learning#cite_note-86)

 

### Decision trees

 Main article: [Decision tree learning](./Decision_tree_learning) [![](//upload.wikimedia.org/wikipedia/commons/thumb/e/eb/Decision_Tree.jpg/330px-Decision_Tree.jpg)](./File:Decision_Tree.jpg)A decision tree showing survival probability of passengers on the [Titanic](./Titanic) 

Decision tree learning uses a [decision tree](./Decision_tree) as a [predictive model](./Predictive_modeling) to go from observations about an item (represented in the branches) to conclusions about the item's target value (represented in the leaves). It is one of the predictive modelling approaches used in statistics, data mining, and machine learning. Tree models where the target variable can take a discrete set of values are called classification trees; in these tree structures, [leaves](./Leaf_node) represent class labels, and branches represent [conjunctions](./Logical_conjunction) of features that lead to those class labels. Decision trees where the target variable can take continuous values (typically [real numbers](./Real_numbers)) are called regression trees. In decision analysis, a decision tree can be used to visually and explicitly represent decisions and [decision making](./Decision_making). In data mining, a decision tree describes data, but the resulting classification tree can be an input for decision-making.

 

### Random forest regression

 

[Random forest regression](./Random_forest) (RFR) falls under the umbrella of decision [tree-based models](./Tree-based_models). RFR is an ensemble learning method that builds multiple decision trees and averages their predictions to improve accuracy and to avoid overfitting. To build decision trees, RFR uses bootstrapped sampling; for instance, each decision tree is trained on random data from the training set. This random selection of RFR for training enables the model to reduce biased predictions and achieve a higher degree of accuracy. RFR generates independent decision trees, and it can work on single-output data as well as multiple regressor tasks. This makes RFR compatible to be use in various applications.[[87]](./Machine_learning#cite_note-87)[[88]](./Machine_learning#cite_note-88)

 

### Support-vector machines

 Main article: [Support-vector machine](./Support-vector_machine) 

Support-vector machines (SVMs), also known as support-vector networks, are a set of related [supervised learning](./Supervised_learning) methods used for classification and regression. Given a set of training examples, each marked as belonging to one of two categories, an SVM training algorithm builds a model that predicts whether a new example falls into one category.[[89]](./Machine_learning#cite_note-CorinnaCortes-89) An SVM training algorithm is a non-[probabilistic](./Probabilistic_classification), [binary](./Binary_classifier), [linear classifier](./Linear_classifier), although methods such as [Platt scaling](./Platt_scaling) exist to use SVM in a probabilistic classification setting. In addition to performing linear classification, SVMs can efficiently perform a non-linear classification using what is called the [kernel trick](./Kernel_trick), implicitly mapping their inputs into high-dimensional feature spaces.

 

### Regression analysis

 Main article: [Regression analysis](./Regression_analysis) [![](//upload.wikimedia.org/wikipedia/commons/thumb/3/3a/Linear_regression.svg/330px-Linear_regression.svg.png)](./File:Linear_regression.svg)Illustration of linear regression on a data set 

Regression analysis encompasses a large variety of statistical methods to estimate the relationship between input variables and their associated features. Its most common form is [linear regression](./Linear_regression), where a single line is drawn to best fit the given data according to a mathematical criterion such as [ordinary least squares](./Ordinary_least_squares). The latter is often extended by [regularisation](./Regularization_(mathematics)) methods to mitigate overfitting and bias, as in [ridge regression](./Ridge_regression). When dealing with non-linear problems, go-to models include [polynomial regression](./Polynomial_regression) (for example, used for trendline fitting in Microsoft Excel[[90]](./Machine_learning#cite_note-90)), [logistic regression](./Logistic_regression) (often used in [statistical classification](./Statistical_classification)) or even [kernel regression](./Kernel_regression), which introduces non-linearity by taking advantage of the [kernel trick](./Kernel_trick) to implicitly map input variables to higher-dimensional space.

 

[Multivariate linear regression](./General_linear_model) extends the concept of linear regression to handle multiple dependent variables simultaneously. This approach estimates the relationships between a set of input variables and several output variables by fitting a [multidimensional](./Multidimensional_system) linear model. It is particularly useful in scenarios where outputs are interdependent or share underlying patterns, such as predicting multiple economic indicators or reconstructing images,[[91]](./Machine_learning#cite_note-91) which are inherently multi-dimensional.

 

### Bayesian networks

 Main article: [Bayesian network](./Bayesian_network) [![](//upload.wikimedia.org/wikipedia/commons/thumb/f/fd/SimpleBayesNetNodes.svg/250px-SimpleBayesNetNodes.svg.png)](./File:SimpleBayesNetNodes.svg)A simple Bayesian network. Rain influences whether the sprinkler is activated, and both rain and the sprinkler influence whether the grass is wet. 

A Bayesian network, belief network, or directed acyclic graphical model is a probabilistic [graphical model](./Graphical_model) that represents a set of [random variables](./Random_variables) and their [conditional independence](./Conditional_independence) with a [directed acyclic graph](./Directed_acyclic_graph) (DAG). For example, a Bayesian network could represent the probabilistic relationships between diseases and symptoms. Given symptoms, the network can be used to compute the probabilities of the presence of various diseases. Efficient algorithms exist that perform [inference](./Bayesian_inference) and learning. Bayesian networks that model sequences of variables, like [speech signals](./Speech_recognition) or [protein sequences](./Peptide_sequence), are called [dynamic Bayesian networks](./Dynamic_Bayesian_network). Generalisations of Bayesian networks that can represent and solve decision problems under uncertainty are called [influence diagrams](./Influence_diagram).

 

### Gaussian processes

 Main article: [Gaussian processes](./Gaussian_processes) [![](//upload.wikimedia.org/wikipedia/commons/thumb/a/a7/Regressions_sine_demo.svg/250px-Regressions_sine_demo.svg.png)](./File:Regressions_sine_demo.svg)An example of Gaussian Process Regression (prediction) compared with other regression models[[92]](./Machine_learning#cite_note-92) 

A Gaussian process is a [stochastic process](./Stochastic_process) in which every finite collection of the random variables in the process has a [multivariate normal distribution](./Multivariate_normal_distribution), and it relies on a pre-defined [covariance function](./Covariance_function), or kernel, that models how pairs of points relate to each other depending on their locations.

 

Given a set of observed points, or input–output examples, the distribution of the (unobserved) output of a new point as a function of its input data can be directly computed by looking at the observed points and the covariances between those points and the new, unobserved point.

 

Gaussian processes are popular surrogate models in [Bayesian optimisation](./Bayesian_optimisation) used to do [hyperparameter optimisation](./Hyperparameter_optimisation).

 

### Genetic algorithms

 Main article: [Genetic algorithm](./Genetic_algorithm) 

A genetic algorithm (GA) is a [search algorithm](./Search_algorithm) and [heuristic](./Heuristic_(computer_science)) technique that mimics the process of [natural selection](./Natural_selection), using methods such as [mutation](./Mutation_(genetic_algorithm)) and [crossover](./Crossover_(genetic_algorithm)) to generate new [genotypes](./Chromosome_(genetic_algorithm)) in the hope of finding good solutions to a given problem. In machine learning, genetic algorithms were used in the 1980s and 1990s.[[93]](./Machine_learning#cite_note-93)[[94]](./Machine_learning#cite_note-94) Conversely, machine learning techniques have been used to improve the performance of genetic and [evolutionary algorithms](./Evolutionary_algorithm).[[95]](./Machine_learning#cite_note-95)

 

### Belief functions

 Main article: [Dempster–Shafer theory](./Dempster–Shafer_theory) 

The theory of belief functions, also referred to as evidence theory or Dempster–Shafer theory, is a general framework for reasoning with uncertainty, with understood connections to other frameworks such as [probability](./Probability), [possibility](./Possibility_theory) and  [imprecise probability theories](./Imprecise_probability). These theoretical frameworks can be thought of as a kind of learner and have some analogous properties of how evidence is combined (e.g.,  Dempster's rule of combination), just like how in a [pmf](./Probability_mass_function)-based Bayesian approach would combine probabilities.[[96]](./Machine_learning#cite_note-96) However, there are many caveats to these beliefs functions when compared to Bayesian approaches to incorporate ignorance and [uncertainty quantification](./Uncertainty_quantification). These belief function approaches that are implemented within the machine learning domain typically leverage a fusion approach of various [ensemble methods](./Ensemble_methods) to better handle the learner's [decision boundary](./Decision_boundary), low samples, and ambiguous class issues that standard machine learning approach tend to have difficulty resolving.[[97]](./Machine_learning#cite_note-YoosefzadehNajafabadi-2021-97)[[6]](./Machine_learning#cite_note-Kohavi-6) However, the computational complexity of these algorithms is dependent on the number of propositions (classes), and can lead to a much higher computation time when compared to other machine learning approaches.

 

### Rule-based models

 Main article: [Rule-based machine learning](./Rule-based_machine_learning) 

Rule-based machine learning (RBML) is a branch of machine learning that automatically discovers and learns 'rules' from data. It provides interpretable models, making it useful for decision-making in fields like healthcare, fraud detection, and cybersecurity. Key RBML techniques includes [learning classifier systems](./Learning_classifier_system),[[98]](./Machine_learning#cite_note-98) [association rule learning](./Association_rule_learning),[[99]](./Machine_learning#cite_note-99) [artificial immune systems](./Artificial_immune_system),[[100]](./Machine_learning#cite_note-100) and other similar models. These methods extract patterns from data and evolve rules over time.

 

### Training models

 

Typically, machine learning models require a high quantity of reliable data to perform accurate predictions. When training a machine learning model, machine learning engineers need to target and collect a large and representative [sample](./Sample_(statistics)) of data. Data from the training set can be as varied as a [corpus of text](./Corpus_of_text), a collection of images, [sensor](./Sensor) data, and data collected from individual users of a service. [Overfitting](./Overfitting) is something to watch out for when training a machine learning model. Trained models derived from biased or non-evaluated data can result in skewed or undesired predictions. Biased models may result in detrimental outcomes, thereby furthering the negative impacts on society or objectives. [Algorithmic bias](./Algorithmic_bias) is a potential result of data not being fully prepared for training. Machine learning ethics is becoming a field of study and, notably, becoming integrated within machine learning engineering teams.

 

#### Federated learning

 Main article: [Federated learning](./Federated_learning) 

Federated learning is an adapted form of [distributed artificial intelligence](./Distributed_artificial_intelligence) to train machine learning models that decentralises the training process, allowing for users' privacy to be maintained by not needing to send their data to a centralised server. This also increases efficiency by decentralising the training process to many devices. For example, [Gboard](./Gboard) uses federated machine learning to train search query prediction models on users' mobile phones without having to send individual searches back to [Google](./Google).[[101]](./Machine_learning#cite_note-101)

 

## Applications

 

There are many applications for machine learning, including:

  
- [Agriculture](./Precision_agriculture)
- [Anatomy](./Computational_anatomy)
- [Adaptive website](./Adaptive_website)
- [Affective computing](./Affective_computing)
- [Astronomy](./Astroinformatics)
- [Automated decision-making](./Automated_decision-making)
- [Banking](./Banking)
- [Behaviorism](./Behaviorism)
- [Bioinformatics](./Bioinformatics)
- [Brain–machine interfaces](./Brain–computer_interface)
- [Cheminformatics](./Cheminformatics)
- [Citizen Science](./Citizen_Science)
- [Climate Science](./Climate_Science)
- [Computer networks](./Network_simulation)
- [Computer vision](./Computer_vision)
- [Credit-card fraud](./Credit-card_fraud) detection
- [Data quality](./Data_quality)
- [DNA sequence](./DNA_sequence) classification
- [Economics](./Computational_economics)
- [Financial data analysis](./Data_analysis)[[102]](./Machine_learning#cite_note-102)
- [General game playing](./General_game_playing)
- [Handwriting recognition](./Handwriting_recognition)
- [Healthcare](./Artificial_intelligence_in_healthcare)
- [Information retrieval](./Information_retrieval)
- [Insurance](./Insurance)
- [Internet fraud](./Internet_fraud) detection
- [Investment management](./Investment_management)[[103]](./Machine_learning#cite_note-103)
- [Knowledge graph embedding](./Knowledge_graph_embedding)
- [Linguistics](./Computational_linguistics)
- [Machine learning control](./Machine_learning_control)
- [Machine perception](./Machine_perception)
- [Machine translation](./Machine_translation)
- [Material Engineering](./Material_Engineering)
- [Marketing](./Marketing)
- [Medical diagnosis](./Automated_medical_diagnosis)
- [Natural language processing](./Natural_language_processing)
- [Natural language understanding](./Natural-language_understanding)
- [Online advertising](./Online_advertising)
- [Optimisation](./Optimisation)
- [Recommender systems](./Recommender_system)
- [Robot locomotion](./Robot_locomotion)
- [Search engines](./Search_engines)
- [Sentiment analysis](./Sentiment_analysis)
- [Sequence mining](./Sequence_mining)
- [Software engineering](./Software_engineering)
- [Speech recognition](./Speech_recognition)
- [Structural health monitoring](./Structural_health_monitoring)
- [Syntactic pattern recognition](./Syntactic_pattern_recognition)
- [Telecommunications](./Telecommunications)
- [Theorem proving](./Automated_theorem_proving)
- [Time-series forecasting](./Time_series)
- [Tomographic reconstruction](./Tomographic_reconstruction)[[104]](./Machine_learning#cite_note-104)
- [User behaviour analytics](./User_behaviour_analytics)

  

In 2006, the media-services provider [Netflix](./Netflix) held the first "[Netflix Prize](./Netflix_Prize)" competition to find a program to better predict user preferences and improve the accuracy of its existing Cinematch movie recommendation algorithm by at least 10%. A joint team made up of researchers from [AT&T Labs](./AT&T_Labs)-Research in collaboration with the teams Big Chaos and Pragmatic Theory built an [ensemble model](./Ensemble_Averaging) to win the Grand Prize in 2009 for $1 million.[[105]](./Machine_learning#cite_note-105) Shortly after the prize was awarded, Netflix realised that viewers' ratings were not the best indicators of their viewing patterns ("everything is a recommendation") and they changed their recommendation engine accordingly.[[106]](./Machine_learning#cite_note-106) In 2010, an article in *[The Wall Street Journal](./The_Wall_Street_Journal)* noted the use of machine learning by Rebellion Research to predict the [2008 financial crisis](./2008_financial_crisis).[[107]](./Machine_learning#cite_note-107) In 2012, co-founder of [Sun Microsystems](./Sun_Microsystems), [Vinod Khosla](./Vinod_Khosla), predicted that 80% of medical doctors jobs would be lost in the next two decades to automated machine learning medical diagnostic software.[[108]](./Machine_learning#cite_note-108) In 2014, it was reported that a machine learning algorithm had been applied in the field of art history to study fine art paintings and that it may have revealed previously unrecognised influences among artists.[[109]](./Machine_learning#cite_note-109) In 2019 [Springer Nature](./Springer_Nature) published the first research book created using machine learning.[[110]](./Machine_learning#cite_note-110) In 2020, machine learning technology was used to help make diagnoses and aid researchers in developing a cure for COVID-19.[[111]](./Machine_learning#cite_note-111) Machine learning was recently applied to predict the pro-environmental behaviour of travellers.[[112]](./Machine_learning#cite_note-112) Recently, machine learning technology was also applied to optimise smartphone's performance and thermal behaviour based on the user's interaction with the phone.[[113]](./Machine_learning#cite_note-113)[[114]](./Machine_learning#cite_note-114)[[115]](./Machine_learning#cite_note-115) When applied correctly, machine learning algorithms (MLAs) can utilise a wide range of company characteristics to predict stock returns without [overfitting](./Overfitting). By employing effective feature engineering and combining forecasts, MLAs can generate results that far surpass those obtained from basic linear techniques like [OLS](./Ordinary_least_squares).[[116]](./Machine_learning#cite_note-116)

 

Recent advancements in machine learning have extended into the field of quantum chemistry, where novel algorithms now enable the prediction of solvent effects on chemical reactions, thereby offering new tools for chemists to tailor experimental conditions for optimal outcomes.[[117]](./Machine_learning#cite_note-117)

 

Machine Learning is becoming a useful tool to investigate and predict evacuation decision-making in large-scale and small-scale disasters. Different solutions have been tested to predict if and when householders decide to evacuate during wildfires and hurricanes.[[118]](./Machine_learning#cite_note-118)[[119]](./Machine_learning#cite_note-119)[[120]](./Machine_learning#cite_note-120) Other applications have been focusing on pre evacuation decisions in building fires.[[121]](./Machine_learning#cite_note-121)[[122]](./Machine_learning#cite_note-122)

 

## Limitations

 

Although machine learning has been transformative in some fields, machine-learning programs often fail to deliver expected results.[[123]](./Machine_learning#cite_note-123)[[124]](./Machine_learning#cite_note-124)[[125]](./Machine_learning#cite_note-125) Reasons for this are numerous: lack of (suitable) data, lack of access to the data, data bias, privacy problems, badly chosen tasks and algorithms, wrong tools and people, lack of resources, and evaluation problems.[[126]](./Machine_learning#cite_note-126)

 

The "[black box theory](./Black_box)" poses another yet significant challenge. Black box refers to a situation where the algorithm producing an output is entirely opaque, meaning that even the designers of an application cannot audit the pattern that the machine extracted from the data.[[127]](./Machine_learning#cite_note-Babuta-2018-127) The House of Lords Select Committee, which claimed that such an "intelligence system" that could have a "substantial impact on an individual's life" would not be considered acceptable unless it provided "a full and satisfactory explanation for the decisions" it makes.[[127]](./Machine_learning#cite_note-Babuta-2018-127)

 

In 2018, a self-driving car from [Uber](./Uber) failed to detect a pedestrian, who was killed after a collision.[[128]](./Machine_learning#cite_note-128) Attempts to use machine learning in healthcare with the [IBM Watson](./Watson_(computer)) system failed to deliver even after years of time and billions of dollars invested.[[129]](./Machine_learning#cite_note-129)[[130]](./Machine_learning#cite_note-130) Microsoft's [Bing Chat](./Bing_Chat) chatbot has been reported to produce hostile and offensive response against its users.[[131]](./Machine_learning#cite_note-131)

 

Machine learning has been used as a strategy to update the evidence related to a systematic review and increased reviewer burden related to the growth of biomedical literature. While it has improved with training sets, it has not yet developed sufficiently to reduce the workload burden without limiting the necessary sensitivity for the findings research itself.[[132]](./Machine_learning#cite_note-132)

 

### Explainability

 Main article: [Explainable artificial intelligence](./Explainable_artificial_intelligence) 

Explainable AI (XAI), or Interpretable AI, or Explainable Machine Learning (XML), is artificial intelligence (AI) in which humans can understand the decisions or predictions made by the AI.[[133]](./Machine_learning#cite_note-133) It contrasts with the "black box" concept in machine learning where even its designers cannot explain why an AI arrived at a specific decision.[[134]](./Machine_learning#cite_note-134) By refining the mental models of users of AI-powered systems and dismantling their misconceptions, XAI promises to help users perform more effectively. XAI may be an implementation of the social right to explanation.

 

### Overfitting

 Main article: [Overfitting](./Overfitting) [![](//upload.wikimedia.org/wikipedia/commons/thumb/6/68/Overfitted_Data.png/250px-Overfitted_Data.png)](./File:Overfitted_Data.png)The blue line could be an example of overfitting a linear function due to random noise. 

Settling on a bad, overly complex theory [gerrymandered](./Gerrymandering) to fit all the past training data is known as overfitting. Many systems attempt to reduce overfitting by rewarding a theory in accordance with how well it fits the data but penalising the theory in accordance with how complex the theory is.[[135]](./Machine_learning#cite_note-FOOTNOTEDomingos2015Chapter_6,_Chapter_7-135)

 

### Model collapse

 This section is an excerpt from [Model collapse](./Model_collapse).[[edit](https://en.wikipedia.org/w/index.php?title=Model_collapse&action=edit)] 

[Model collapse](./Model_collapse), also known by other names such as "AI [inbreeding](./Inbreeding)",[[136]](./Machine_learning#cite_note-136)[[137]](./Machine_learning#cite_note-137) "AI [cannibalism](./Cannibalism)",[[138]](./Machine_learning#cite_note-138)[[139]](./Machine_learning#cite_note-139) "[Habsburg](./House_of_Habsburg#Habsburg_inbreeding_and_extinction_of_the_male_lines) AI",[[140]](./Machine_learning#cite_note-140) and "model [autophagy](./Autophagy) disorder" or "MAD"[[141]](./Machine_learning#cite_note-141)[[142]](./Machine_learning#cite_note-142)[[143]](./Machine_learning#cite_note-143) is a phenomenon noted in [artificial intelligence](./Artificial_intelligence) studies, where machine learning models gradually degrade due to errors coming from uncurated [synthetic data](./Synthetic_data), or due to training on the outputs of another model such as prior versions of itself. It is unclear to what extent the phenomenon threatens the long-term development of such models, and some techniques have been proposed to mitigate the effect.

   

### Hallucinations

 This section is an excerpt from [Hallucination (artificial intelligence)](./Hallucination_(artificial_intelligence)).[[edit](https://en.wikipedia.org/w/index.php?title=Hallucination_(artificial_intelligence)&action=edit)] A video of the [Glenfinnan Viaduct](./Glenfinnan_Viaduct) in Scotland generated by [Sora](./Sora_(text-to-video_model)), incorrectly showing: a [second track](./Double-track_railway), trains [traveling on the right instead of the left](./Left-_and_right-hand_traffic#Rail_traffic), a second chimney on its interpretation of the train [*The Jacobite*](./The_Jacobite_(steam_train)), inconsistent carriage lengths, unnatural amounts of visual noise, and a carriage bending along its length as it rounds the turn.[![](//upload.wikimedia.org/wikipedia/commons/thumb/e/ed/Glenfinnan_Viaduct_-_2022_%28cropped%29.jpg/330px-Glenfinnan_Viaduct_-_2022_%28cropped%29.jpg)](./File:Glenfinnan_Viaduct_-_2022_(cropped).jpg)The real Glenfinnan Viaduct with *The Jacobite* on it 

In the field of [artificial intelligence](./Artificial_intelligence) (AI), a [hallucination](./Hallucination_(artificial_intelligence)) or artificial hallucination (also called bullshitting,[[144]](./Machine_learning#cite_note-Hallucination_(artificial_intelligence)_Hicks_Humphries_Slater_2024-144)[[145]](./Machine_learning#cite_note-145) confabulation,[[146]](./Machine_learning#cite_note-Hallucination_(artificial_intelligence)_ars_making_things_up-146) or delusion[[147]](./Machine_learning#cite_note-147)) is a response generated by AI that contains false or [misleading information](./Misleading_information) presented as [fact](./Fact).[[148]](./Machine_learning#cite_note-148) The term draws a loose analogy with human psychology, where a [hallucination](./Hallucination) typically involves false *[percepts](./Percept#Process_and_terminology)*.

 

For example, a [chatbot](./Chatbot) powered by [large language models](./Large_language_model) (LLMs), like [ChatGPT](./ChatGPT), may embed plausible-sounding random falsehoods within its generated content. Detecting and mitigating errors and hallucinations pose significant challenges for practical deployment and reliability of LLMs in high-stakes scenarios, such as chip design, supply chain logistics, and medical diagnostics.[[149]](./Machine_learning#cite_note-Hallucination_(artificial_intelligence)_nyt-149)[[150]](./Machine_learning#cite_note-Hallucination_(artificial_intelligence)_de_Wynter-2023-150)[[151]](./Machine_learning#cite_note-Hallucination_(artificial_intelligence)_cnbc_several_errors-151) Some software engineers and statisticians have criticized the specific term "AI hallucination" for unreasonably [anthropomorphizing computers](./Anthropomorphism#In_computing).[[152]](./Machine_learning#cite_note-Hallucination_(artificial_intelligence)_sigplan-152)[[153]](./Machine_learning#cite_note-Hallucination_(artificial_intelligence)_salon-153) [Symbolic artificial intelligence](./Symbolic_artificial_intelligence) models generally do not produce hallucinations, unlike large language models.[[154]](./Machine_learning#cite_note-Hallucination_(artificial_intelligence)_Garcez-154)

   

### Other limitations and vulnerabilities

  WHAT IS THE TECHNICAL TERM THAT DESCRIBES THIS LIMITATION?  

Learners can also be disappointed by "learning the wrong lesson". A toy example is that an image classifier trained only on pictures of brown horses and black cats might conclude that all brown patches are likely to be horses.[[155]](./Machine_learning#cite_note-FOOTNOTEDomingos2015286-155) A real-world example is that, unlike humans, current image classifiers often do not primarily make judgments from the spatial relationship between components of the picture, and they learn relationships between pixels that humans are oblivious to, but that still correlate with images of certain types of real objects. Modifying these patterns on a legitimate image can result in "adversarial" images that the system misclassifies.[[156]](./Machine_learning#cite_note-156)[[157]](./Machine_learning#cite_note-157)

  WHAT IS THE TECHNICAL TERM THAT DESCRIBES THIS LIMITATION?   

Adversarial vulnerabilities can also result in nonlinear systems or from non-pattern perturbations. For some systems, it is possible to change the output by only changing a single adversarially chosen pixel.[[158]](./Machine_learning#cite_note-TD_1-158) Machine learning models are often vulnerable to manipulation or evasion via [adversarial machine learning](./Adversarial_machine_learning).[[159]](./Machine_learning#cite_note-159)

 

Researchers have demonstrated how [backdoors](./Backdoor_(computing)) can be placed undetectably into classifying (e.g., for categories "spam" and "not spam" of posts) machine learning models that are often developed or trained by third parties. Parties can change the classification of any input, including in cases for which a type of [data/software transparency](./Algorithmic_transparency) is provided, possibly including [white-box access](./White-box_testing).[[160]](./Machine_learning#cite_note-160)[[161]](./Machine_learning#cite_note-161)[[162]](./Machine_learning#cite_note-162)

 

## Model assessments

 

Classification of machine learning models can be validated by accuracy estimation techniques like the [holdout](./Test_set) method, which splits the data into a training and test set (conventionally 2/3 training set and 1/3 test set designation) and evaluates the performance of the training model on the test set. In comparison, the K-fold-[cross-validation](./Cross-validation_(statistics)) method randomly partitions the data into K subsets and then K experiments are performed each considering 1 subset for evaluation and the remaining K-1 subsets for training the model. In addition to the holdout and cross-validation methods, [bootstrap](./Bootstrapping_(statistics)), which samples n instances with replacement from the dataset, can be used to assess model accuracy.[[163]](./Machine_learning#cite_note-163)

 

In addition to overall accuracy, investigators frequently report [sensitivity and specificity](./Sensitivity_and_specificity), meaning true positive rate (TPR) and true negative rate (TNR), respectively. Similarly, investigators sometimes report the [false positive rate](./False_positive_rate) (FPR) as well as the [false negative rate](./False_negative_rate) (FNR). However, these rates are ratios that fail to reveal their numerators and denominators. [Receiver operating characteristic](./Receiver_operating_characteristic) (ROC), along with the accompanying Area Under the ROC Curve (AUC), offer additional tools for classification model assessment. Higher AUC is associated with a better performing model.[[164]](./Machine_learning#cite_note-164)

 

## Ethics

 This section is an excerpt from [Ethics of artificial intelligence](./Ethics_of_artificial_intelligence).[[edit](https://en.wikipedia.org/w/index.php?title=Ethics_of_artificial_intelligence&action=edit)] 

The [ethics](./Ethics) of [artificial intelligence](./Artificial_intelligence) covers a broad range of topics within AI that are considered to have particular ethical stakes.[[165]](./Machine_learning#cite_note-Ethics_of_artificial_intelligence_Muller-2020-165) This includes [algorithmic biases](./Algorithmic_bias), [fairness](./Fairness_(machine_learning)), [accountability](./Accountability), transparency, privacy, and [regulation](./Regulation_of_artificial_intelligence), particularly where systems influence or automate human decision-making. It also covers various emerging or potential future challenges such as [machine ethics](./Machine_ethics) (how to make machines that behave ethically), [lethal autonomous weapon systems](./Lethal_autonomous_weapon), [arms race](./Artificial_intelligence_arms_race) dynamics, [AI safety](./AI_safety) and [alignment](./AI_alignment), [technological unemployment](./Technological_unemployment), AI-enabled [misinformation](./Misinformation),[[166]](./Machine_learning#cite_note-Ethics_of_artificial_intelligence_:4-166) how to treat certain AI systems if they have a [moral status](./Moral_status) (AI welfare and rights), [artificial superintelligence](./Artificial_superintelligence) and [existential risks](./Existential_risk_from_artificial_general_intelligence).[[165]](./Machine_learning#cite_note-Ethics_of_artificial_intelligence_Muller-2020-165)

 

Some application areas may also have particularly important ethical implications, like [healthcare](./Artificial_intelligence_in_healthcare), education, criminal justice, or the military.

   

### Bias

 Main article: [Algorithmic bias](./Algorithmic_bias) 

Different machine learning approaches can suffer from different data biases. A machine learning system trained specifically on current customers may not be able to predict the needs of new customer groups that are not represented in the training data. When trained on human-made data, machine learning is likely to pick up the constitutional and unconscious biases already present in society.[[167]](./Machine_learning#cite_note-Garcia-2016-167)

 

Systems that are trained on datasets collected with biases may exhibit these biases upon use (algorithmic bias), thus digitising cultural prejudices.[[168]](./Machine_learning#cite_note-168) For example, in 1988, the UK's [Commission for Racial Equality](./Commission_for_Racial_Equality) found that [St. George's Medical School](./St_George's,_University_of_London) had been using a computer program trained from data of previous admissions staff and this program had denied nearly 60 candidates who were found to either be women or have non-European-sounding names.[[167]](./Machine_learning#cite_note-Garcia-2016-167) Using job hiring data from a firm with racist hiring policies may lead to a machine learning system duplicating the bias by scoring job applicants by similarity to previous successful applicants.[[169]](./Machine_learning#cite_note-Edionwe_Outline-169)[[170]](./Machine_learning#cite_note-Jeffries_Outline-170) Another example includes predictive policing company [Geolitica](./Geolitica)'s predictive algorithm that resulted in "disproportionately high levels of over-policing in low-income and minority communities" after being trained with historical crime data.[[171]](./Machine_learning#cite_note-Silva-2018-171)

 

While responsible [collection of data](./Data_collection) and documentation of algorithmic rules used by a system is considered a critical part of machine learning, some researchers blame the lack of participation and representation of minority populations in the field of AI for machine learning's vulnerability to biases.[[172]](./Machine_learning#cite_note-172) In fact, according to research carried out by the Computing Research Association in 2021, "female faculty make up just 16.1%" of all faculty members who focus on AI among several universities around the world.[[173]](./Machine_learning#cite_note-Zhang-173) Furthermore, among the group of "new U.S. resident AI PhD graduates," 45% identified as white, 22.4% as Asian, 3.2% as Hispanic, and 2.4% as African American, which further demonstrates a lack of diversity in the field of AI.[[173]](./Machine_learning#cite_note-Zhang-173)

 

Language models learned from data have been shown to contain human-like biases.[[174]](./Machine_learning#cite_note-174)[[175]](./Machine_learning#cite_note-175) Because human languages contain biases, machines trained on language *[corpora](./Text_corpus)* will necessarily also learn these biases.[[176]](./Machine_learning#cite_note-176)[[177]](./Machine_learning#cite_note-177) In 2016, Microsoft tested [Tay](./Tay_(chatbot)), a [chatbot](./Chatbot) that learned from Twitter, and it quickly picked up racist and sexist language.[[178]](./Machine_learning#cite_note-178)

 

In an experiment carried out by [ProPublica](./ProPublica), an [investigative journalism](./Investigative_journalism) organisation, a machine learning algorithm's insight into the recidivism rates among prisoners falsely flagged "black defendants high risk twice as often as white defendants".[[171]](./Machine_learning#cite_note-Silva-2018-171) In 2015, Google Photos once tagged a couple of black people as gorillas, which caused controversy. The gorilla label was subsequently removed, and in 2023, it still cannot recognise gorillas.[[179]](./Machine_learning#cite_note-179) Similar issues with recognising non-white people have been found in many other systems.[[180]](./Machine_learning#cite_note-180)

 

Because of such challenges, the effective use of machine learning may take longer to be adopted in other domains.[[181]](./Machine_learning#cite_note-181) Concern for [fairness](./Fairness_(machine_learning)) in machine learning, that is, reducing bias in machine learning and propelling its use for human good, is increasingly expressed by artificial intelligence scientists, including [Fei-Fei Li](./Fei-Fei_Li), who said that "[t]here's nothing artificial about AI. It's inspired by people, it's created by people, and—most importantly—it impacts people. It is a powerful tool we are only just beginning to understand, and that is a profound responsibility."[[182]](./Machine_learning#cite_note-182)

 

### Financial incentives

 

There are concerns among health care professionals that these systems might not be designed in the public's interest but as income-generating machines. This is especially true in the United States, where there is a long-standing ethical dilemma of improving health care, but also increasing profits. For example, the algorithms could be designed to provide patients with unnecessary tests or medication in which the algorithm's proprietary owners hold stakes. There is potential for machine learning in health care to provide professionals with an additional tool to diagnose, medicate, and plan recovery paths for patients, but this requires these biases to be mitigated.[[183]](./Machine_learning#cite_note-183)

 

## Hardware

 

Since the 2010s, advances in both machine learning algorithms and computer hardware have led to more efficient methods for training [deep neural networks](./Deep_neural_network) (a particular narrow subdomain of machine learning) that contain many layers of nonlinear hidden units.[[184]](./Machine_learning#cite_note-184) By 2019, graphics processing units ([GPUs](./GPU)), often with AI-specific enhancements, had displaced CPUs as the dominant method of training large-scale commercial cloud AI.[[185]](./Machine_learning#cite_note-185) [OpenAI](./OpenAI) estimated the hardware compute used in the largest deep learning projects from [AlexNet](./AlexNet) (2012) to [AlphaZero](./AlphaZero) (2017), and found a 300,000-fold increase in the amount of compute required, with a doubling-time trendline of 3.4 months.[[186]](./Machine_learning#cite_note-186)[[187]](./Machine_learning#cite_note-187)

 

### Tensor Processing Units (TPUs)

 

[Tensor Processing Units (TPUs)](./Tensor_Processing_Unit) are specialised hardware accelerators developed by [Google](./Google) specifically for machine learning workloads. Unlike general-purpose [GPUs](./Graphics_processing_unit) and [FPGAs](./Field-programmable_gate_array), TPUs are optimised for tensor computations, making them particularly efficient for deep learning tasks such as training and inference. They are widely used in Google Cloud AI services and large-scale machine learning models like Google's DeepMind AlphaFold and large language models. TPUs leverage [matrix multiplication](./Computational_complexity_of_matrix_multiplication) units and high-bandwidth memory to accelerate computations while maintaining energy efficiency.[[188]](./Machine_learning#cite_note-188) Since their introduction in 2016, TPUs have become a key component of AI infrastructure, especially in cloud-based environments.

 

### Neuromorphic computing

 

[Neuromorphic computing](./Neuromorphic_computing) refers to a class of computing systems designed to emulate the structure and functionality of biological neural networks. These systems may be implemented through software-based simulations on conventional hardware or through specialised hardware architectures.[[189]](./Machine_learning#cite_note-189)

 

#### Physical neural networks

 

A [physical neural network](./Physical_neural_network) is a specific type of neuromorphic hardware that relies on electrically adjustable materials, such as memristors, to emulate the function of [neural synapses](./Chemical_synapse). The term "physical neural network" highlights the use of physical hardware for computation, as opposed to software-based implementations. It broadly refers to artificial neural networks that use materials with adjustable resistance to replicate neural synapses.[[190]](./Machine_learning#cite_note-190)[[191]](./Machine_learning#cite_note-191)

 

### Embedded machine learning

 

Embedded machine learning is a sub-field of machine learning where models are deployed on [embedded systems](./Embedded_systems) with limited computing resources, such as [wearable computers](./Wearable_computer), [edge devices](./Edge_device) and [microcontrollers](./Microcontrollers).[[192]](./Machine_learning#cite_note-192)[[193]](./Machine_learning#cite_note-193)[[194]](./Machine_learning#cite_note-194)[[195]](./Machine_learning#cite_note-195) Running models directly on these devices eliminates the need to transfer and store data on cloud servers for further processing, thereby reducing the risk of data breaches, privacy leaks and theft of intellectual property, personal data and business secrets. Embedded machine learning can be achieved through various techniques, such as [hardware acceleration](./Hardware_acceleration),[[196]](./Machine_learning#cite_note-196)[[197]](./Machine_learning#cite_note-197) [approximate computing](./Approximate_computing),[[198]](./Machine_learning#cite_note-198) and model optimization.[[199]](./Machine_learning#cite_note-199)[[200]](./Machine_learning#cite_note-200) Common optimization techniques include [pruning](./Pruning_(artificial_neural_network)), [quantisation](./Model_compression#Quantization), [knowledge distillation](./Knowledge_distillation), low-rank factorisation, network architecture search, and parameter sharing.

 

## Software

 See also: [Comparison of machine learning software](./Comparison_of_machine_learning_software) 

### Free and open-source software

 See also: [Lists of open-source artificial intelligence software](./Lists_of_open-source_artificial_intelligence_software)  
- [Mahout](./Apache_Mahout)
- [Apache OpenNLP](./Apache_OpenNLP)
- [Apache SINGA](./Apache_SINGA)
- [Spark MLlib](./Apache_Spark#MLlib_Machine_Learning_Library)
- [Apache SystemDS](./Apache_SystemDS)
- [Caffe](./Caffe_(software))
- [CatBoost](./CatBoost)
- [Deeplearning4j](./Deeplearning4j)
- [DeepSpeed](./DeepSpeed)
- [Dlib](./Dlib)
- [ELKI](./ELKI)
- [Flux.jl](./Flux.jl)
- [Gensim](./Gensim)
- [Google JAX](./Google_JAX)
- [H2O](./H2O_(software))
- [Infer.NET](./Infer.NET)
- [JASP](./JASP)
- [Jubatus](./Jubatus)
- [Keras](./Keras)
- [Kubeflow](./Kubeflow)
- [LIBSVM](./LIBSVM)
- [LightGBM](./LightGBM)
- [Mallet](./Mallet_(software_project))
- [Microsoft Cognitive Toolkit](./Microsoft_Cognitive_Toolkit)
- [MindSpore](./MindSpore)
- [ML.NET](./ML.NET)
- [mlpack](./Mlpack)
- [MXNet](./MXNet)
- [OpenNN](./OpenNN)
- [Orange](./Orange_(software))
- [ROOT](./ROOT) (TMVA with ROOT)
- [scikit-learn](./Scikit-learn)
- [Shogun](./Shogun_(toolbox))
- [TensorFlow](./TensorFlow)
- [Theano](./Theano_(software))
- [Torch](./Torch_(machine_learning)) / [PyTorch](./PyTorch) / [PyTorch Lightning](./PyTorch_Lightning)
- [Vowpal Wabbit](./Vowpal_Wabbit)
- [Weka](./Weka_(machine_learning)) / [MOA](./MOA_(Massive_Online_Analysis))
- [XGBoost](./XGBoost)
- [Yooreeka](./Yooreeka)

  

### Proprietary software with free and open-source editions

 
- [KNIME](./KNIME)
- [RapidMiner](./RapidMiner)

 

### Proprietary software

  
- [Amazon Machine Learning](./Amazon_Machine_Learning)
- [Angoss](./Angoss) KnowledgeSTUDIO
- [Azure Machine Learning](./Azure_Machine_Learning)
- [IBM Watson Studio](./IBM_Watson_Studio)
- [Google Cloud Vertex AI](./Google_Cloud_Platform#Cloud_AI)
- [Google Prediction API](./Google_APIs)
- [IBM SPSS Modeller](./SPSS_Modeler)
- [KXEN Modeller](./KXEN_Inc.)
- [LIONsolver](./LIONsolver)
- [Mathematica](./Mathematica)
- [MATLAB](./MATLAB)
- [Neural Designer](./Neural_Designer)
- [NeuroSolutions](./NeuroSolutions)
- [Oracle Data Mining](./Oracle_Data_Mining)
- [Oracle AI Platform Cloud Service](./Oracle_Cloud#Infrastructure_as_a_Service_(IaaS)_and_Platform_as_a_Service_(PaaS))
- [PolyAnalyst](./PolyAnalyst)
- [RCASE](./RCASE)
- [SAS Enterprise Miner](./SAS_(software)#Components)
- [SequenceL](./SequenceL)
- [Splunk](./Splunk)
- [STATISTICA](./STATISTICA) Data Miner

  

## Journals

 
- [Journal of Machine Learning Research](./Journal_of_Machine_Learning_Research)
- [Machine Learning](./Machine_Learning_(journal))
- [Nature Machine Intelligence](./Nature_Machine_Intelligence)
- [Neural Computation](./Neural_Computation_(journal))
- [IEEE Transactions on Pattern Analysis and Machine Intelligence](./IEEE_Transactions_on_Pattern_Analysis_and_Machine_Intelligence)

 

## Conferences

 
- [AAAI Conference on Artificial Intelligence](./AAAI_Conference_on_Artificial_Intelligence)
- [Association for Computational Linguistics (**ACL**)](./Association_for_Computational_Linguistics)
- [European Conference on Machine Learning and Principles and Practice of Knowledge Discovery in Databases (**ECML PKDD**)](./European_Conference_on_Machine_Learning_and_Principles_and_Practice_of_Knowledge_Discovery_in_Databases)
- [International Conference on Computational Intelligence Methods for Bioinformatics and Biostatistics (**CIBB**)](./International_Conference_on_Computational_Intelligence_Methods_for_Bioinformatics_and_Biostatistics)
- [International Conference on Machine Learning (**ICML**)](./International_Conference_on_Machine_Learning)
- [International Conference on Learning Representations (**ICLR**)](./International_Conference_on_Learning_Representations)
- [International Conference on Intelligent Robots and Systems (**IROS**)](./International_Conference_on_Intelligent_Robots_and_Systems)
- [Conference on Knowledge Discovery and Data Mining (**KDD**)](./Conference_on_Knowledge_Discovery_and_Data_Mining)
- [Conference on Neural Information Processing Systems (**NeurIPS**)](./Conference_on_Neural_Information_Processing_Systems)

 

## See also

 
- [Automated machine learning](./Automated_machine_learning) – Process of automating the application of machine learning
- [Big data](./Big_data) – Extremely large or complex datasets
- [Deep learning](./Deep_learning) — branch of ML concerned with [artificial neural networks](./Artificial_neural_network)
- [Differentiable programming](./Differentiable_programming) – Programming paradigm
- [Google Colab](./Google_Colab) – no setup [online IDE](./Online_integrated_development_environment) for machine learning in [Python](./List_of_Python_software#Machine_learning_and_deep_learning) and [Julia](./List_of_Julia_software_and_tools#Machine_learning_and_artificial_intelligence)
- [List of datasets for machine-learning research](./List_of_datasets_for_machine-learning_research)
- [List of machine learning algorithms](./Outline_of_machine_learning#Machine_learning_algorithms) and [List of algorithms for machine learning and statistical classification](./List_of_algorithms#Machine_learning_and_statistical_classification)
- [M-theory (learning framework)](./M-theory_(learning_framework)) – Framework in machine learning
- [Machine unlearning](./Machine_unlearning) – Field of study in artificial intelligence
- [Outline of machine learning](./Outline_of_machine_learning)
- [Solomonoff's theory of inductive inference](./Solomonoff's_theory_of_inductive_inference) – Mathematical theory
- [TinyML](./TinyML) — Machine learning on low-power [embedded systems](./Embedded_system)

 

## References

 
1. [↑](./Machine_learning#cite_ref-1) The definition "without being explicitly programmed" is often attributed to [Arthur Samuel](./Arthur_Samuel_(computer_scientist)), who coined the term "machine learning" in 1959, but the phrase is not found verbatim in this publication, and may be a [paraphrase](./Paraphrase) that appeared later. Refer to "Paraphrasing Arthur Samuel (1959), the question is: How can computers learn to solve problems without being explicitly programmed?" in Koza, John R.; Bennett, Forrest H.; Andre, David; Keane, Martin A. (1996). "Automated Design of Both the Topology and Sizing of Analog Electrical Circuits Using Genetic Programming". *Artificial Intelligence in Design '96*. Artificial Intelligence in Design '96. Dordrecht, Netherlands: Springer Netherlands. pp. 151–170. [doi](./Doi_(identifier)):[10.1007/978-94-009-0279-4_9](https://doi.org/10.1007%2F978-94-009-0279-4_9). [ISBN](./ISBN_(identifier)) [978-94-010-6610-5](./Special:BookSources/978-94-010-6610-5).
2. [1](./Machine_learning#cite_ref-bishop2006_2-0) [2](./Machine_learning#cite_ref-bishop2006_2-1) [3](./Machine_learning#cite_ref-bishop2006_2-2) [Bishop, C. M.](./Christopher_M._Bishop) (2006), *Pattern Recognition and Machine Learning*, Springer, [ISBN](./ISBN_(identifier)) [978-0-387-31073-2](./Special:BookSources/978-0-387-31073-2)
3. [↑](./Machine_learning#cite_ref-3) Machine learning and pattern recognition "can be viewed as two facets of the same field".[[2]](./Machine_learning#cite_note-bishop2006-2): vii 
4. [1](./Machine_learning#cite_ref-Friedman-1998_4-0) [2](./Machine_learning#cite_ref-Friedman-1998_4-1) [Friedman, Jerome H.](./Jerome_H._Friedman) (1998). "Data Mining and Statistics: What's the connection?". *Computing Science and Statistics*. **29** (1): 3–9.
5. [↑](./Machine_learning#cite_ref-Samuel_5-0) Samuel, Arthur (1959). "Some Studies in Machine Learning Using the Game of Checkers". *IBM Journal of Research and Development*. **3** (3): 210–229. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.368.2254](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.368.2254). [doi](./Doi_(identifier)):[10.1147/rd.33.0210](https://doi.org/10.1147%2Frd.33.0210). [S2CID](./S2CID_(identifier)) [2126705](https://api.semanticscholar.org/CorpusID:2126705).
6. [1](./Machine_learning#cite_ref-Kohavi_6-0) [2](./Machine_learning#cite_ref-Kohavi_6-1) R. Kohavi and F. Provost, "Glossary of terms", Machine Learning, vol. 30, no. 2–3, pp. 271–274, 1998.
7. [↑](./Machine_learning#cite_ref-cyberthreat_7-0) Gerovitch, Slava (9 April 2015). ["How the Computer Got Its Revenge on the Soviet Union"](https://web.archive.org/web/20210922175839/https://nautil.us/issue/23/Dominoes/how-the-computer-got-its-revenge-on-the-soviet-union). *Nautilus*. Archived from [the original](https://nautil.us/issue/23/dominoes/how-the-computer-got-its-revenge-on-the-soviet-union) on 22 September 2021. Retrieved 19 September 2021.
8. [↑](./Machine_learning#cite_ref-8) Lindsay, Richard P. (September 1964). "The Impact of Automation On Public Administration". *Western Political Quarterly*. **17** (3): 78–81. [doi](./Doi_(identifier)):[10.1177/106591296401700364](https://doi.org/10.1177%2F106591296401700364).
9. [1](./Machine_learning#cite_ref-WhatIs_9-0) [2](./Machine_learning#cite_ref-WhatIs_9-1) [3](./Machine_learning#cite_ref-WhatIs_9-2) ["History and Evolution of Machine Learning: A Timeline"](https://www.techtarget.com/whatis/A-Timeline-of-Machine-Learning-History). *WhatIs*. [Archived](https://web.archive.org/web/20231208220935/https://www.techtarget.com/whatis/A-Timeline-of-Machine-Learning-History) from the original on 8 December 2023. Retrieved 8 December 2023.
10. [↑](./Machine_learning#cite_ref-10) Milner, Peter M. (1993). ["The Mind and Donald O. Hebb"](https://cmor-faculty.rice.edu/~cox/worthing/milnersciam.pdf) (PDF). *Scientific American*. **268** (1): 124–129. [Bibcode](./Bibcode_(identifier)):[1993SciAm.268a.124M](https://ui.adsabs.harvard.edu/abs/1993SciAm.268a.124M). [doi](./Doi_(identifier)):[10.1038/scientificamerican0193-124](https://doi.org/10.1038%2Fscientificamerican0193-124). [ISSN](./ISSN_(identifier)) [0036-8733](https://search.worldcat.org/issn/0036-8733). [JSTOR](./JSTOR_(identifier)) [24941344](https://www.jstor.org/stable/24941344). [PMID](./PMID_(identifier)) [8418480](https://pubmed.ncbi.nlm.nih.gov/8418480).
11. [↑](./Machine_learning#cite_ref-11) "Science: The Goof Button", [Time](./Time_(magazine)), 18 August 1961.
12. [↑](./Machine_learning#cite_ref-12) Nilsson, Nils J. (1965). *Learning Machines*. McGraw-Hill.
13. [↑](./Machine_learning#cite_ref-13) Duda, Richard O.; Hart, Peter E. (1973). *Pattern Recognition and Scene Analysis*. Wiley Interscience.
14. [↑](./Machine_learning#cite_ref-14) S. Bozinovski, "Teaching space: A representation concept for adaptive pattern classification" COINS Technical Report No. 81-28, Computer and Information Science Department, University of Massachusetts at Amherst, MA, 1981. [https://web.cs.umass.edu/publication/docs/1981/UM-CS-1981-028.pdf](https://web.cs.umass.edu/publication/docs/1981/UM-CS-1981-028.pdf) [Archived](https://web.archive.org/web/20210225070218/https://web.cs.umass.edu/publication/docs/1981/UM-CS-1981-028.pdf) 25 February 2021 at the [Wayback Machine](./Wayback_Machine)
15. [1](./Machine_learning#cite_ref-Mitchell-1997_15-0) [2](./Machine_learning#cite_ref-Mitchell-1997_15-1) Mitchell, T. (1997). *Machine Learning*. McGraw Hill. p. 2. [ISBN](./ISBN_(identifier)) [978-0-07-042807-2](./Special:BookSources/978-0-07-042807-2).
16. [↑](./Machine_learning#cite_ref-16) Turing, Alan (October 1950). ["Computing Machinery and Intelligence"](https://courses.cs.umbc.edu/471/papers/turing.pdf) (PDF). *Mind*. **59** (236).
17. [↑](./Machine_learning#cite_ref-17) [Harnad, Stevan](./Stevan_Harnad) (2008), ["The Annotation Game: On Turing (1950) on Computing, Machinery, and Intelligence"](https://web.archive.org/web/20120309113922/http://eprints.ecs.soton.ac.uk/12954/), in Epstein, Robert; Peters, Grace (eds.), *The Turing Test Sourcebook: Philosophical and Methodological Issues in the Quest for the Thinking Computer*, Kluwer, pp. 23–66, [ISBN](./ISBN_(identifier)) [978-1-4020-6708-2](./Special:BookSources/978-1-4020-6708-2), archived from [the original](http://eprints.ecs.soton.ac.uk/12954/) on 9 March 2012, retrieved 11 December 2012
18. [↑](./Machine_learning#cite_ref-18) Goodfellow, Ian; Pouget-Abadie, Jean; Mirza, Mehdi (2014). [*Generative adversarial nets*](https://proceedings.neurips.cc/paper_files/paper/2014/file/f033ed80deb0234979a61f95710dbe25-Paper.pdf) (PDF). Advances in Neural Information Processing Systems 27 (2014).
19. [↑](./Machine_learning#cite_ref-19) Silver, David; Huang, Aja; Maddison, Christopher J. (2016). "Mastering the game of Go with deep neural networks and tree search". *Nature*. **529** (7587): 484–489. [Bibcode](./Bibcode_(identifier)):[2016Natur.529..484S](https://ui.adsabs.harvard.edu/abs/2016Natur.529..484S). [doi](./Doi_(identifier)):[10.1038/nature16961](https://doi.org/10.1038%2Fnature16961). [PMID](./PMID_(identifier)) [26819042](https://pubmed.ncbi.nlm.nih.gov/26819042).
20. [↑](./Machine_learning#cite_ref-journalimcms.org_20-0) Sindhu V, Nivedha S, Prakash M (February 2020). ["An Empirical Science Research on Bioinformatics in Machine Learning"](https://doi.org/10.26782%2Fjmcms.spl.7%2F2020.02.00006). *Journal of Mechanics of Continua and Mathematical Sciences* (7). [doi](./Doi_(identifier)):[10.26782/jmcms.spl.7/2020.02.00006](https://doi.org/10.26782%2Fjmcms.spl.7%2F2020.02.00006).
21. [↑](./Machine_learning#cite_ref-21) Sarle, Warren S. (1994). "Neural Networks and statistical models". *SUGI 19: proceedings of the Nineteenth Annual SAS Users Group International Conference*. SAS Institute. pp. 1538–50. [ISBN](./ISBN_(identifier)) [978-1-55544-611-6](./Special:BookSources/978-1-55544-611-6). [OCLC](./OCLC_(identifier)) [35546178](https://search.worldcat.org/oclc/35546178).
22. [1](./Machine_learning#cite_ref-aima_22-0) [2](./Machine_learning#cite_ref-aima_22-1) [3](./Machine_learning#cite_ref-aima_22-2) [4](./Machine_learning#cite_ref-aima_22-3) [Russell, Stuart](./Stuart_J._Russell); [Norvig, Peter](./Peter_Norvig) (2003) [1995]. *[Artificial Intelligence: A Modern Approach](./Artificial_Intelligence:_A_Modern_Approach)* (2nd ed.). Prentice Hall. [ISBN](./ISBN_(identifier)) [978-0137903955](./Special:BookSources/978-0137903955).
23. [1](./Machine_learning#cite_ref-changing_23-0) [2](./Machine_learning#cite_ref-changing_23-1) Langley, Pat (2011). ["The changing science of machine learning"](https://doi.org/10.1007%2Fs10994-011-5242-y). *[Machine Learning](./Machine_Learning_(journal))*. **82** (3): 275–9. [doi](./Doi_(identifier)):[10.1007/s10994-011-5242-y](https://doi.org/10.1007%2Fs10994-011-5242-y).
24. [↑](./Machine_learning#cite_ref-Data_compression_Mahoney_24-0) Mahoney, Matt. ["Rationale for a Large Text Compression Benchmark"](https://web.archive.org/web/20060818205830/http://cs.fit.edu/~mmahoney/compression/rationale.html). Florida Institute of Technology. Archived from [the original](http://cs.fit.edu/~mmahoney/compression/rationale.html) on 18 August 2006. Retrieved 5 March 2013.
25. [↑](./Machine_learning#cite_ref-Data_compression_Market_Efficiency_25-0) Shmilovici A.; Kahiri Y.; Ben-Gal I.; Hauser S. (2009). ["Measuring the Efficiency of the Intraday Forex Market with a Universal Data Compression Algorithm"](http://www.eng.tau.ac.il/~bengal/28.pdf) (PDF). *Computational Economics*. **33** (2): 131–154. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.627.3751](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.627.3751). [doi](./Doi_(identifier)):[10.1007/s10614-008-9153-3](https://doi.org/10.1007%2Fs10614-008-9153-3). [S2CID](./S2CID_(identifier)) [17234503](https://api.semanticscholar.org/CorpusID:17234503). [Archived](https://web.archive.org/web/20090709143601/http://www.eng.tau.ac.il/~bengal/28.pdf) (PDF) from the original on 9 July 2009.
26. [↑](./Machine_learning#cite_ref-Data_compression_Ben-Gal_26-0) Ben-Gal, I. (2008). ["On the Use of Data Compression Measures to Analyze Robust Designs"](https://web.archive.org/web/20200926205659/http://www.eng.tau.ac.il/~bengal/Journal%20Paper.pdf) (PDF). *IEEE Transactions on Reliability*. **54** (3): 381–388. [doi](./Doi_(identifier)):[10.1109/TR.2005.853280](https://doi.org/10.1109%2FTR.2005.853280). [S2CID](./S2CID_(identifier)) [9376086](https://api.semanticscholar.org/CorpusID:9376086). Archived from [the original](http://www.eng.tau.ac.il/~bengal/Journal%20Paper.pdf) (PDF) on 26 September 2020. Retrieved 6 April 2016.
27. [↑](./Machine_learning#cite_ref-Data_compression_ScullyBrodley_27-0) D. Scully; [Carla E. Brodley](./Carla_Brodley) (2006). "Compression and Machine Learning: A New Perspective on Feature Space Vectors". *Data Compression Conference (DCC'06)*. p. 332. [doi](./Doi_(identifier)):[10.1109/DCC.2006.13](https://doi.org/10.1109%2FDCC.2006.13). [ISBN](./ISBN_(identifier)) [0-7695-2545-8](./Special:BookSources/0-7695-2545-8). [S2CID](./S2CID_(identifier)) [12311412](https://api.semanticscholar.org/CorpusID:12311412).
28. [↑](./Machine_learning#cite_ref-28) Gary Adcock (5 January 2023). ["What Is AI Video Compression?"](https://massive.io/file-transfer/what-is-ai-video-compression/). *massive.io*. [Archived](https://web.archive.org/web/20230406081640/https://massive.io/file-transfer/what-is-ai-video-compression/) from the original on 6 April 2023. Retrieved 6 April 2023.
29. [↑](./Machine_learning#cite_ref-29) Mentzer, Fabian; Toderici, George; Tschannen, Michael; Agustsson, Eirikur (2020). "High-Fidelity Generative Image Compression". [arXiv](./ArXiv_(identifier)):[2006.09965](https://arxiv.org/abs/2006.09965) [[eess.IV](https://arxiv.org/archive/eess.IV)].
30. [↑](./Machine_learning#cite_ref-30) ["What is Unsupervised Learning? | IBM"](https://www.ibm.com/topics/unsupervised-learning). *www.ibm.com*. 23 September 2021. [Archived](https://web.archive.org/web/20240205083041/https://www.ibm.com/topics/unsupervised-learning) from the original on 5 February 2024. Retrieved 5 February 2024.
31. [↑](./Machine_learning#cite_ref-31) ["Differentially private clustering for large-scale datasets"](https://blog.research.google/2023/05/differentially-private-clustering-for.html). *blog.research.google*. 25 May 2023. [Archived](https://web.archive.org/web/20240316115422/https://blog.research.google/2023/05/differentially-private-clustering-for.html) from the original on 16 March 2024. Retrieved 16 March 2024.
32. [↑](./Machine_learning#cite_ref-32) Edwards, Benj (28 September 2023). ["AI language models can exceed PNG and FLAC in lossless compression, says study"](https://arstechnica.com/information-technology/2023/09/ai-language-models-can-exceed-png-and-flac-in-lossless-compression-says-study/). *Ars Technica*. [Archived](https://web.archive.org/web/20240307200529/https://arstechnica.com/information-technology/2023/09/ai-language-models-can-exceed-png-and-flac-in-lossless-compression-says-study/) from the original on 7 March 2024. Retrieved 7 March 2024.
33. [↑](./Machine_learning#cite_ref-33) Delétang, Grégoire; Ruoss, Anian; Duquenne, Paul-Ambroise; Catt, Elliot; Genewein, Tim; Mattern, Christopher; Grau-Moya, Jordi; Li Kevin Wenliang; Aitchison, Matthew; Orseau, Laurent; Hutter, Marcus; Veness, Joel (2023). "Language Modeling is Compression". [arXiv](./ArXiv_(identifier)):[2309.10668](https://arxiv.org/abs/2309.10668) [[cs.LG](https://arxiv.org/archive/cs.LG)].
34. [↑](./Machine_learning#cite_ref-34) Le Roux, Nicolas; Bengio, Yoshua; Fitzgibbon, Andrew (2012). ["Improving First and Second-Order Methods by Modeling Uncertainty"](https://books.google.com/books?id=JPQx7s2L1A8C&q=%22Improving+First+and+Second-Order+Methods+by+Modeling+Uncertainty&pg=PA403). In Sra, Suvrit; Nowozin, Sebastian; Wright, Stephen J. (eds.). *Optimization for Machine Learning*. MIT Press. p. 404. [ISBN](./ISBN_(identifier)) [978-0-262-01646-9](./Special:BookSources/978-0-262-01646-9). [Archived](https://web.archive.org/web/20230117053335/https://books.google.com/books?id=JPQx7s2L1A8C&q=%22Improving+First+and+Second-Order+Methods+by+Modeling+Uncertainty&pg=PA403) from the original on 17 January 2023. Retrieved 12 November 2020.
35. [↑](./Machine_learning#cite_ref-35) Bzdok, Danilo; [Altman, Naomi](./Naomi_Altman); Krzywinski, Martin (2018). ["Statistics versus Machine Learning"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6082636). *[Nature Methods](./Nature_Methods)*. **15** (4): 233–234. [doi](./Doi_(identifier)):[10.1038/nmeth.4642](https://doi.org/10.1038%2Fnmeth.4642). [PMC](./PMC_(identifier)) [6082636](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6082636). [PMID](./PMID_(identifier)) [30100822](https://pubmed.ncbi.nlm.nih.gov/30100822).
36. [↑](./Machine_learning#cite_ref-36) Hung et al. Algorithms to Measure Surgeon Performance and Anticipate Clinical Outcomes in Robotic Surgery. JAMA Surg. 2018
37. [↑](./Machine_learning#cite_ref-Cornell-University-Library-2001_37-0) Cornell University Library (August 2001). ["Breiman: Statistical Modeling: The Two Cultures (with comments and a rejoinder by the author)"](http://projecteuclid.org/download/pdf_1/euclid.ss/1009213726). *Statistical Science*. **16** (3). [doi](./Doi_(identifier)):[10.1214/ss/1009213726](https://doi.org/10.1214%2Fss%2F1009213726). [S2CID](./S2CID_(identifier)) [62729017](https://api.semanticscholar.org/CorpusID:62729017). [Archived](https://web.archive.org/web/20170626042637/http://projecteuclid.org/download/pdf_1/euclid.ss/1009213726) from the original on 26 June 2017. Retrieved 8 August 2015.
38. [↑](./Machine_learning#cite_ref-islr_38-0) Gareth James; Daniela Witten; Trevor Hastie; Robert Tibshirani (2013). [*An Introduction to Statistical Learning*](http://www-bcf.usc.edu/~gareth/ISL/). Springer. p. vii. [Archived](https://web.archive.org/web/20190623150237/http://www-bcf.usc.edu/~gareth/ISL/) from the original on 23 June 2019. Retrieved 25 October 2014.
39. [↑](./Machine_learning#cite_ref-SP_1_39-0) Ramezanpour, A.; Beam, A.L.; Chen, J.H.; Mashaghi, A. (17 November 2020). ["Statistical Physics for Medical Diagnostics: Learning, Inference, and Optimization Algorithms"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7699346). *Diagnostics*. **10** (11): 972. [doi](./Doi_(identifier)):[10.3390/diagnostics10110972](https://doi.org/10.3390%2Fdiagnostics10110972). [PMC](./PMC_(identifier)) [7699346](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7699346). [PMID](./PMID_(identifier)) [33228143](https://pubmed.ncbi.nlm.nih.gov/33228143).
40. [↑](./Machine_learning#cite_ref-SP_2_40-0) Mashaghi, A.; Ramezanpour, A. (16 March 2018). "Statistical physics of medical diagnostics: Study of a probabilistic model". *[Physical Review E](./Physical_Review_E)*. **97** (3–1) 032118. [arXiv](./ArXiv_(identifier)):[1803.10019](https://arxiv.org/abs/1803.10019). [Bibcode](./Bibcode_(identifier)):[2018PhRvE..97c2118M](https://ui.adsabs.harvard.edu/abs/2018PhRvE..97c2118M). [doi](./Doi_(identifier)):[10.1103/PhysRevE.97.032118](https://doi.org/10.1103%2FPhysRevE.97.032118). [PMID](./PMID_(identifier)) [29776109](https://pubmed.ncbi.nlm.nih.gov/29776109). [S2CID](./S2CID_(identifier)) [4955393](https://api.semanticscholar.org/CorpusID:4955393).
41. [↑](./Machine_learning#cite_ref-Mohri-2012_41-0) [Mohri, Mehryar](./Mehryar_Mohri); Rostamizadeh, Afshin; Talwalkar, Ameet (2012). *Foundations of Machine Learning*. US, Massachusetts: MIT Press. [ISBN](./ISBN_(identifier)) [9780262018258](./Special:BookSources/9780262018258).
42. [↑](./Machine_learning#cite_ref-alpaydin_42-0) Alpaydin, Ethem (2010). [*Introduction to Machine Learning*](https://archive.org/details/introductiontoma00alpa_0). London: The MIT Press. [ISBN](./ISBN_(identifier)) [978-0-262-01243-0](./Special:BookSources/978-0-262-01243-0). Retrieved 4 February 2017.
43. [↑](./Machine_learning#cite_ref-43) Jordan, M. I.; Mitchell, T. M. (17 July 2015). "Machine learning: Trends, perspectives, and prospects". *Science*. **349** (6245): 255–260. [Bibcode](./Bibcode_(identifier)):[2015Sci...349..255J](https://ui.adsabs.harvard.edu/abs/2015Sci...349..255J). [doi](./Doi_(identifier)):[10.1126/science.aaa8415](https://doi.org/10.1126%2Fscience.aaa8415). [PMID](./PMID_(identifier)) [26185243](https://pubmed.ncbi.nlm.nih.gov/26185243). [S2CID](./S2CID_(identifier)) [677218](https://api.semanticscholar.org/CorpusID:677218).
44. [↑](./Machine_learning#cite_ref-44) El Naqa, Issam; Murphy, Martin J. (2015). "What is Machine Learning?". *Machine Learning in Radiation Oncology*. pp. 3–11. [doi](./Doi_(identifier)):[10.1007/978-3-319-18305-3_1](https://doi.org/10.1007%2F978-3-319-18305-3_1). [ISBN](./ISBN_(identifier)) [978-3-319-18304-6](./Special:BookSources/978-3-319-18304-6). [S2CID](./S2CID_(identifier)) [178586107](https://api.semanticscholar.org/CorpusID:178586107).
45. [↑](./Machine_learning#cite_ref-45) Okolie, Jude A.; Savage, Shauna; Ogbaga, Chukwuma C.; Gunes, Burcu (June 2022). ["Assessing the potential of machine learning methods to study the removal of pharmaceuticals from wastewater using biochar or activated carbon"](https://doi.org/10.1016%2Fj.totert.2022.100001). *Total Environment Research Themes*. **1–2** 100001. [Bibcode](./Bibcode_(identifier)):[2022TERT....100001O](https://ui.adsabs.harvard.edu/abs/2022TERT....100001O). [doi](./Doi_(identifier)):[10.1016/j.totert.2022.100001](https://doi.org/10.1016%2Fj.totert.2022.100001). [S2CID](./S2CID_(identifier)) [249022386](https://api.semanticscholar.org/CorpusID:249022386).
46. [↑](./Machine_learning#cite_ref-46) Russell, Stuart J.; Norvig, Peter (2010). [*Artificial Intelligence: A Modern Approach*](./Artificial_Intelligence:_A_Modern_Approach) (Third ed.). Prentice Hall. [ISBN](./ISBN_(identifier)) [978-0-13-604259-4](./Special:BookSources/978-0-13-604259-4).
47. [↑](./Machine_learning#cite_ref-47) Mohri, Mehryar; Rostamizadeh, Afshin; Talwalkar, Ameet (2012). *Foundations of Machine Learning*. The MIT Press. [ISBN](./ISBN_(identifier)) [978-0-262-01825-8](./Special:BookSources/978-0-262-01825-8).
48. [↑](./Machine_learning#cite_ref-Alpaydin-2010_48-0) Alpaydin, Ethem (2010). [*Introduction to Machine Learning*](https://books.google.com/books?id=7f5bBAAAQBAJ). MIT Press. p. 9. [ISBN](./ISBN_(identifier)) [978-0-262-01243-0](./Special:BookSources/978-0-262-01243-0). [Archived](https://web.archive.org/web/20230117053338/https://books.google.com/books?id=7f5bBAAAQBAJ) from the original on 17 January 2023. Retrieved 25 November 2018.
49. [↑](./Machine_learning#cite_ref-49) De Sa, Christopher (Spring 2022). ["Lecture 2 Notes: Supervised Learning"](https://www.cs.cornell.edu/courses/cs4780/2022sp/notes/LectureNotes02.html). *Cornell: Computer Science*. Retrieved 1 July 2024.
50. [↑](./Machine_learning#cite_ref-JordanBishop2004_50-0) Jordan, Michael I.; Bishop, Christopher M. (2004). "Neural Networks". In Allen B. Tucker (ed.). *Computer Science Handbook, Second Edition (Section VII: Intelligent Systems)*. Boca Raton, Florida: Chapman & Hall/CRC Press LLC. [ISBN](./ISBN_(identifier)) [978-1-58488-360-9](./Special:BookSources/978-1-58488-360-9).
51. [↑](./Machine_learning#cite_ref-51) Misra, Ishan; Maaten, Laurens van der (2020). [*Self-Supervised Learning of Pretext-Invariant Representations*](https://openaccess.thecvf.com/content_CVPR_2020/html/Misra_Self-Supervised_Learning_of_Pretext-Invariant_Representations_CVPR_2020_paper.html). 2020 IEEE/CVF Conference on Computer Vision and Pattern Recognition. Seattle, WA, US: [IEEE](./Institute_of_Electrical_and_Electronics_Engineers). pp. 6707–6717. [arXiv](./ArXiv_(identifier)):[1912.01991](https://arxiv.org/abs/1912.01991). [doi](./Doi_(identifier)):[10.1109/CVPR42600.2020.00674](https://doi.org/10.1109%2FCVPR42600.2020.00674).
52. [↑](./Machine_learning#cite_ref-52) Jaiswal, Ashish; Babu, Ashwin Ramesh; Zadeh, Mohammad Zaki; Banerjee, Debapriya; Makedon, Fillia (March 2021). ["A Survey on Contrastive Self-Supervised Learning"](https://doi.org/10.3390%2Ftechnologies9010002). *Technologies*. **9** (1): 2. [arXiv](./ArXiv_(identifier)):[2011.00362](https://arxiv.org/abs/2011.00362). [doi](./Doi_(identifier)):[10.3390/technologies9010002](https://doi.org/10.3390%2Ftechnologies9010002). [ISSN](./ISSN_(identifier)) [2227-7080](https://search.worldcat.org/issn/2227-7080).
53. [↑](./Machine_learning#cite_ref-53) Roweis, Sam T.; Saul, Lawrence K. (22 December 2000). "Nonlinear Dimensionality Reduction by Locally Linear Embedding". *Science*. **290** (5500): 2323–2326. [Bibcode](./Bibcode_(identifier)):[2000Sci...290.2323R](https://ui.adsabs.harvard.edu/abs/2000Sci...290.2323R). [doi](./Doi_(identifier)):[10.1126/science.290.5500.2323](https://doi.org/10.1126%2Fscience.290.5500.2323). [PMID](./PMID_(identifier)) [11125150](https://pubmed.ncbi.nlm.nih.gov/11125150).
54. [↑](./Machine_learning#cite_ref-54) Alex Ratner; Stephen Bach; Paroma Varma; Chris. ["Weak Supervision: The New Programming Paradigm for Machine Learning"](https://web.archive.org/web/20190606043931/https://hazyresearch.github.io/snorkel/blog/ws_blog_post.html). *hazyresearch.github.io*. referencing work by many other members of Hazy Research. Archived from [the original](https://hazyresearch.github.io/snorkel/blog/ws_blog_post.html) on 6 June 2019. Retrieved 6 June 2019.
55. [↑](./Machine_learning#cite_ref-55) van Otterlo, M.; Wiering, M. (2012). "Reinforcement Learning and Markov Decision Processes". *Reinforcement Learning*. Adaptation, Learning, and Optimization. Vol. 12. pp. 3–42. [doi](./Doi_(identifier)):[10.1007/978-3-642-27645-3_1](https://doi.org/10.1007%2F978-3-642-27645-3_1). [ISBN](./ISBN_(identifier)) [978-3-642-27644-6](./Special:BookSources/978-3-642-27644-6).
56. [↑](./Machine_learning#cite_ref-56) Pavel Brazdil; Christophe Giraud Carrier; Carlos Soares; Ricardo Vilalta (2009). *Metalearning: Applications to Data Mining* (Fourth ed.). [Springer Science+Business Media](./Springer_Science+Business_Media). pp. 10–14, *passim*. [ISBN](./ISBN_(identifier)) [978-3-540-73262-4](./Special:BookSources/978-3-540-73262-4).
57. [↑](./Machine_learning#cite_ref-57) Bozinovski, S. (1982). "A self-learning system using secondary reinforcement". In Trappl, Robert (ed.). *Cybernetics and Systems Research: Proceedings of the Sixth European Meeting on Cybernetics and Systems Research*. North-Holland. pp. 397–402. [ISBN](./ISBN_(identifier)) [978-0-444-86488-8](./Special:BookSources/978-0-444-86488-8).
58. [↑](./Machine_learning#cite_ref-58) Bozinovski, S. (1999). "Crossbar Adaptive Array: The first connectionist network that solved the delayed reinforcement learning problem". *Artificial Neural Nets and Genetic Algorithms*. pp. 320–325. [doi](./Doi_(identifier)):[10.1007/978-3-7091-6384-9_54](https://doi.org/10.1007%2F978-3-7091-6384-9_54). [ISBN](./ISBN_(identifier)) [978-3-211-83364-3](./Special:BookSources/978-3-211-83364-3).
59. [↑](./Machine_learning#cite_ref-59) Bozinovski, Stevo (2014). ["Modeling Mechanisms of Cognition-emotion Interaction in Artificial Neural Networks, since 1981"](https://doi.org/10.1016%2Fj.procs.2014.11.111). *Procedia Computer Science*. **41**: 255–263. [doi](./Doi_(identifier)):[10.1016/j.procs.2014.11.111](https://doi.org/10.1016%2Fj.procs.2014.11.111).
60. [↑](./Machine_learning#cite_ref-60) Bozinovski, Stevo; Bozinovska, Liljana (2001). "Self-Learning Agents: A Connectionist Theory of Emotion Based on Crossbar Value Judgment". *Cybernetics and Systems*. **32** (6): 637–669. [doi](./Doi_(identifier)):[10.1080/01969720118145](https://doi.org/10.1080%2F01969720118145).
61. [↑](./Machine_learning#cite_ref-pami_61-0) Y. Bengio; A. Courville; P. Vincent (2013). "Representation Learning: A Review and New Perspectives". *IEEE Transactions on Pattern Analysis and Machine Intelligence*. **35** (8): 1798–1828. [arXiv](./ArXiv_(identifier)):[1206.5538](https://arxiv.org/abs/1206.5538). [Bibcode](./Bibcode_(identifier)):[2013ITPAM..35.1798B](https://ui.adsabs.harvard.edu/abs/2013ITPAM..35.1798B). [doi](./Doi_(identifier)):[10.1109/tpami.2013.50](https://doi.org/10.1109%2Ftpami.2013.50). [PMID](./PMID_(identifier)) [23787338](https://pubmed.ncbi.nlm.nih.gov/23787338). [S2CID](./S2CID_(identifier)) [393948](https://api.semanticscholar.org/CorpusID:393948).
62. [↑](./Machine_learning#cite_ref-62) Nathan Srebro; Jason D. M. Rennie; Tommi S. Jaakkola (2004). *Maximum-Margin Matrix Factorization*. [NIPS](./Conference_on_Neural_Information_Processing_Systems).
63. [↑](./Machine_learning#cite_ref-coates2011_63-0) Coates, Adam; Lee, Honglak; Ng, Andrew Y. (2011). [*An analysis of single-layer networks in unsupervised feature learning*](https://web.archive.org/web/20170813153615/http://machinelearning.wustl.edu/mlpapers/paper_files/AISTATS2011_CoatesNL11.pdf) (PDF). Int'l Conf. on AI and Statistics (AISTATS). Archived from [the original](http://machinelearning.wustl.edu/mlpapers/paper_files/AISTATS2011_CoatesNL11.pdf) (PDF) on 13 August 2017. Retrieved 25 November 2018.
64. [↑](./Machine_learning#cite_ref-64) Csurka, Gabriella; Dance, Christopher C.; Fan, Lixin; Willamowski, Jutta; Bray, Cédric (2004). [*Visual categorization with bags of keypoints*](https://www.cs.cmu.edu/~efros/courses/LBMV07/Papers/csurka-eccv-04.pdf) (PDF). ECCV Workshop on Statistical Learning in Computer Vision. [Archived](https://web.archive.org/web/20190713040210/http://www.cs.cmu.edu/~efros/courses/LBMV07/Papers/csurka-eccv-04.pdf) (PDF) from the original on 13 July 2019. Retrieved 29 August 2019.
65. [↑](./Machine_learning#cite_ref-jurafsky_65-0) Daniel Jurafsky; James H. Martin (2009). *Speech and Language Processing*. Pearson Education International. pp. 145–146.
66. [↑](./Machine_learning#cite_ref-66) Lu, Haiping; Plataniotis, K.N.; Venetsanopoulos, A.N. (2011). ["A Survey of Multilinear Subspace Learning for Tensor Data"](http://www.dsp.utoronto.ca/~haiping/Publication/SurveyMSL_PR2011.pdf) (PDF). *Pattern Recognition*. **44** (7): 1540–1551. [Bibcode](./Bibcode_(identifier)):[2011PatRe..44.1540L](https://ui.adsabs.harvard.edu/abs/2011PatRe..44.1540L). [doi](./Doi_(identifier)):[10.1016/j.patcog.2011.01.004](https://doi.org/10.1016%2Fj.patcog.2011.01.004). [Archived](https://web.archive.org/web/20190710225429/http://www.dsp.utoronto.ca/~haiping/Publication/SurveyMSL_PR2011.pdf) (PDF) from the original on 10 July 2019. Retrieved 4 September 2015.
67. [↑](./Machine_learning#cite_ref-67) [Yoshua Bengio](./Yoshua_Bengio) (2009). [*Learning Deep Architectures for AI*](https://books.google.com/books?id=cq5ewg7FniMC&pg=PA3). Now Publishers Inc. pp. 1–3. [ISBN](./ISBN_(identifier)) [978-1-60198-294-0](./Special:BookSources/978-1-60198-294-0). [Archived](https://web.archive.org/web/20230117053339/https://books.google.com/books?id=cq5ewg7FniMC&pg=PA3) from the original on 17 January 2023. Retrieved 15 February 2016.
68. [↑](./Machine_learning#cite_ref-68) Tillmann, A. M. (2015). "On the Computational Intractability of Exact and Approximate Dictionary Learning". *IEEE Signal Processing Letters*. **22** (1): 45–49. [arXiv](./ArXiv_(identifier)):[1405.6664](https://arxiv.org/abs/1405.6664). [Bibcode](./Bibcode_(identifier)):[2015ISPL...22...45T](https://ui.adsabs.harvard.edu/abs/2015ISPL...22...45T). [doi](./Doi_(identifier)):[10.1109/LSP.2014.2345761](https://doi.org/10.1109%2FLSP.2014.2345761). [S2CID](./S2CID_(identifier)) [13342762](https://api.semanticscholar.org/CorpusID:13342762).
69. [↑](./Machine_learning#cite_ref-69) [Aharon, M](./Michal_Aharon), M Elad, and A Bruckstein. 2006. "[K-SVD: An Algorithm for Designing Overcomplete Dictionaries for Sparse Representation](http://sites.fas.harvard.edu/~cs278/papers/ksvd.pdf) [Archived](https://web.archive.org/web/20181123142158/http://sites.fas.harvard.edu/~cs278/papers/ksvd.pdf) 2018-11-23 at the [Wayback Machine](./Wayback_Machine)." Signal Processing, IEEE Transactions on 54 (11): 4311–4322
70. [↑](./Machine_learning#cite_ref-Zimek-2017_70-0) Zimek, Arthur; Schubert, Erich (2017), "Outlier Detection", *Encyclopedia of Database Systems*, Springer New York, pp. 1–5, [doi](./Doi_(identifier)):[10.1007/978-1-4899-7993-3_80719-1](https://doi.org/10.1007%2F978-1-4899-7993-3_80719-1), [ISBN](./ISBN_(identifier)) [978-1-4899-7993-3](./Special:BookSources/978-1-4899-7993-3)
71. [↑](./Machine_learning#cite_ref-71) Hodge, V. J.; Austin, J. (2004). ["A Survey of Outlier Detection Methodologies"](http://eprints.whiterose.ac.uk/767/1/hodgevj4.pdf) (PDF). *Artificial Intelligence Review*. **22** (2): 85–126. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.318.4023](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.318.4023). [doi](./Doi_(identifier)):[10.1007/s10462-004-4304-y](https://doi.org/10.1007%2Fs10462-004-4304-y). [S2CID](./S2CID_(identifier)) [59941878](https://api.semanticscholar.org/CorpusID:59941878). [Archived](https://web.archive.org/web/20150622042146/http://eprints.whiterose.ac.uk/767/1/hodgevj4.pdf) (PDF) from the original on 22 June 2015. Retrieved 25 November 2018.
72. [↑](./Machine_learning#cite_ref-72) Dokas, Paul; Ertoz, Levent; Kumar, Vipin; Lazarevic, Aleksandar; Srivastava, Jaideep; Tan, Pang-Ning (2002). ["Data mining for network intrusion detection"](https://www-users.cse.umn.edu/~lazar027/MINDS/papers/nsf_ngdm_2002.pdf) (PDF). *Proceedings NSF Workshop on Next Generation Data Mining*. [Archived](https://web.archive.org/web/20150923211542/http://www.csee.umbc.edu/~kolari1/Mining/ngdm/dokas.pdf) (PDF) from the original on 23 September 2015. Retrieved 26 March 2023.
73. [↑](./Machine_learning#cite_ref-ChandolaSurvey_73-0) Chandola, V.; Banerjee, A.; Kumar, V. (2009). "Anomaly detection: A survey". *[ACM Computing Surveys](./ACM_Computing_Surveys)*. **41** (3): 1–58. [doi](./Doi_(identifier)):[10.1145/1541880.1541882](https://doi.org/10.1145%2F1541880.1541882). [S2CID](./S2CID_(identifier)) [207172599](https://api.semanticscholar.org/CorpusID:207172599).
74. [↑](./Machine_learning#cite_ref-74) Fleer, S.; Moringen, A.; Klatzky, R. L.; Ritter, H. (2020). ["Learning efficient haptic shape exploration with a rigid tactile sensor array, S. Fleer, A. Moringen, R. Klatzky, H. Ritter"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6940144). *PLOS ONE*. **15** (1) e0226880. [arXiv](./ArXiv_(identifier)):[1902.07501](https://arxiv.org/abs/1902.07501). [doi](./Doi_(identifier)):[10.1371/journal.pone.0226880](https://doi.org/10.1371%2Fjournal.pone.0226880). [PMC](./PMC_(identifier)) [6940144](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6940144). [PMID](./PMID_(identifier)) [31896135](https://pubmed.ncbi.nlm.nih.gov/31896135).
75. [↑](./Machine_learning#cite_ref-75) Moringen, Alexandra; Fleer, Sascha; Walck, Guillaume; Ritter, Helge (2020), Nisky, Ilana; Hartcher-O'Brien, Jess; Wiertlewski, Michaël; Smeets, Jeroen (eds.), "Attention-Based Robot Learning of Haptic Interaction", *Haptics: Science, Technology, Applications*, Lecture Notes in Computer Science, vol. 12272, Cham: Springer International Publishing, pp. 462–470, [doi](./Doi_(identifier)):[10.1007/978-3-030-58147-3_51](https://doi.org/10.1007%2F978-3-030-58147-3_51), [ISBN](./ISBN_(identifier)) [978-3-030-58146-6](./Special:BookSources/978-3-030-58146-6), [S2CID](./S2CID_(identifier)) [220069113](https://api.semanticscholar.org/CorpusID:220069113)`{{citation}}`:  CS1 maint: work parameter with ISBN ([link](./Category:CS1_maint:_work_parameter_with_ISBN))
76. [↑](./Machine_learning#cite_ref-piatetsky_76-0) Piatetsky-Shapiro, Gregory (1991), *Discovery, analysis, and presentation of strong rules*, in Piatetsky-Shapiro, Gregory; and Frawley, William J.; eds., *Knowledge Discovery in Databases*, AAAI/MIT Press, Cambridge, MA.
77. [↑](./Machine_learning#cite_ref-77) Bassel, George W.; Glaab, Enrico; Marquez, Julietta; Holdsworth, Michael J.; Bacardit, Jaume (1 September 2011). ["Functional Network Construction in Arabidopsis Using Rule-Based Machine Learning on Large-Scale Data Sets"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3203449). *The Plant Cell*. **23** (9): 3101–3116. [Bibcode](./Bibcode_(identifier)):[2011PlanC..23.3101B](https://ui.adsabs.harvard.edu/abs/2011PlanC..23.3101B). [doi](./Doi_(identifier)):[10.1105/tpc.111.088153](https://doi.org/10.1105%2Ftpc.111.088153). [ISSN](./ISSN_(identifier)) [1532-298X](https://search.worldcat.org/issn/1532-298X). [PMC](./PMC_(identifier)) [3203449](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3203449). [PMID](./PMID_(identifier)) [21896882](https://pubmed.ncbi.nlm.nih.gov/21896882).
78. [↑](./Machine_learning#cite_ref-mining_78-0) Agrawal, R.; Imieliński, T.; Swami, A. (1993). "Mining association rules between sets of items in large databases". *Proceedings of the 1993 ACM SIGMOD international conference on Management of data - SIGMOD '93*. p. 207. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.40.6984](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.40.6984). [doi](./Doi_(identifier)):[10.1145/170035.170072](https://doi.org/10.1145%2F170035.170072). [ISBN](./ISBN_(identifier)) [978-0-89791-592-2](./Special:BookSources/978-0-89791-592-2). [S2CID](./S2CID_(identifier)) [490415](https://api.semanticscholar.org/CorpusID:490415).
79. [↑](./Machine_learning#cite_ref-79) Urbanowicz, Ryan J.; Moore, Jason H. (22 September 2009). ["Learning Classifier Systems: A Complete Introduction, Review, and Roadmap"](https://doi.org/10.1155%2F2009%2F736398). *Journal of Artificial Evolution and Applications*. **2009**: 1–25. [doi](./Doi_(identifier)):[10.1155/2009/736398](https://doi.org/10.1155%2F2009%2F736398). [ISSN](./ISSN_(identifier)) [1687-6229](https://search.worldcat.org/issn/1687-6229).
80. [↑](./Machine_learning#cite_ref-80) Plotkin G.D. [Automatic Methods of Inductive Inference](https://www.era.lib.ed.ac.uk/bitstream/handle/1842/6656/Plotkin1972.pdf;sequence=1) [Archived](https://web.archive.org/web/20171222051034/https://www.era.lib.ed.ac.uk/bitstream/handle/1842/6656/Plotkin1972.pdf;sequence=1) 22 December 2017 at the [Wayback Machine](./Wayback_Machine), PhD thesis, University of Edinburgh, 1970.
81. [↑](./Machine_learning#cite_ref-81) Shapiro, Ehud Y. [Inductive inference of theories from facts](http://ftp.cs.yale.edu/publications/techreports/tr192.pdf) [Archived](https://web.archive.org/web/20210821071609/http://ftp.cs.yale.edu/publications/techreports/tr192.pdf) 21 August 2021 at the [Wayback Machine](./Wayback_Machine), Research Report 192, Yale University, Department of Computer Science, 1981. Reprinted in J.-L. Lassez, G. Plotkin (Eds.), Computational Logic, The MIT Press, Cambridge, MA, 1991, pp. 199–254.
82. [↑](./Machine_learning#cite_ref-82) Shapiro, Ehud Y. (1983). *Algorithmic program debugging*. Cambridge, Mass: MIT Press. [ISBN](./ISBN_(identifier)) [0-262-19218-7](./Special:BookSources/0-262-19218-7)
83. [↑](./Machine_learning#cite_ref-83) Shapiro, Ehud Y. "[The model inference system](http://dl.acm.org/citation.cfm?id=1623364) [Archived](https://web.archive.org/web/20230406011006/https://dl.acm.org/citation.cfm?id=1623364) 2023-04-06 at the [Wayback Machine](./Wayback_Machine)." Proceedings of the 7th international joint conference on Artificial intelligence-Volume 2. Morgan Kaufmann Publishers Inc., 1981.
84. [↑](./Machine_learning#cite_ref-84) Burkov, Andriy (2019). *The hundred-page machine learning book*. Polen: Andriy Burkov. [ISBN](./ISBN_(identifier)) [978-1-9995795-0-0](./Special:BookSources/978-1-9995795-0-0).
85. [↑](./Machine_learning#cite_ref-85) Russell, Stuart J.; Norvig, Peter (2021). *Artificial intelligence: a modern approach*. Pearson series in artificial intelligence (Fourth ed.). Hoboken: Pearson. [ISBN](./ISBN_(identifier)) [978-0-13-461099-3](./Special:BookSources/978-0-13-461099-3).
86. [↑](./Machine_learning#cite_ref-86) Honglak Lee, Roger Grosse, Rajesh Ranganath, Andrew Y. Ng. "[Convolutional Deep Belief Networks for Scalable Unsupervised Learning of Hierarchical Representations](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.149.802&rep=rep1&type=pdf) [Archived](https://web.archive.org/web/20171018182235/http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.149.802&rep=rep1&type=pdf) 2017-10-18 at the [Wayback Machine](./Wayback_Machine)" Proceedings of the 26th Annual International Conference on Machine Learning, 2009.
87. [↑](./Machine_learning#cite_ref-87) ["RandomForestRegressor"](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html). *scikit-learn*. Retrieved 12 February 2025.
88. [↑](./Machine_learning#cite_ref-88) ["What Is Random Forest? | IBM"](https://www.ibm.com/think/topics/random-forest). *www.ibm.com*. 20 October 2021. Retrieved 12 February 2025.
89. [↑](./Machine_learning#cite_ref-CorinnaCortes_89-0) [Cortes, Corinna](./Corinna_Cortes); Vapnik, Vladimir N. (1995). ["Support-vector networks"](https://doi.org/10.1007%2FBF00994018). *[Machine Learning](./Machine_Learning_(journal))*. **20** (3): 273–297. [doi](./Doi_(identifier)):[10.1007/BF00994018](https://doi.org/10.1007%2FBF00994018).
90. [↑](./Machine_learning#cite_ref-90) Stevenson, Christopher. ["Tutorial: Polynomial Regression in Excel"](https://facultystaff.richmond.edu/~cstevens/301/Excel4.html). *facultystaff.richmond.edu*. [Archived](https://web.archive.org/web/20130602200850/https://facultystaff.richmond.edu/~cstevens/301/Excel4.html) from the original on 2 June 2013. Retrieved 22 January 2017.
91. [↑](./Machine_learning#cite_ref-91) Wanta, Damian; Smolik, Aleksander; Smolik, Waldemar T.; Midura, Mateusz; Wróblewski, Przemysław (2025). ["Image reconstruction using machine-learned pseudoinverse in electrical capacitance tomography"](https://doi.org/10.1016%2Fj.engappai.2024.109888). *Engineering Applications of Artificial Intelligence*. **142** 109888. [doi](./Doi_(identifier)):[10.1016/j.engappai.2024.109888](https://doi.org/10.1016%2Fj.engappai.2024.109888).
92. [↑](./Machine_learning#cite_ref-92) The documentation for [scikit-learn](./Scikit-learn) also has similar [examples](http://scikit-learn.org/stable/auto_examples/gaussian_process/plot_compare_gpr_krr.html) [Archived](https://web.archive.org/web/20221102184805/https://scikit-learn.org/stable/auto_examples/gaussian_process/plot_compare_gpr_krr.html) 2 November 2022 at the [Wayback Machine](./Wayback_Machine).
93. [↑](./Machine_learning#cite_ref-93) Goldberg, David E.; Holland, John H. (1988). ["Genetic algorithms and machine learning"](https://deepblue.lib.umich.edu/bitstream/2027.42/46947/1/10994_2005_Article_422926.pdf) (PDF). *[Machine Learning](./Machine_Learning_(journal))*. **3** (2): 95–99. [doi](./Doi_(identifier)):[10.1007/bf00113892](https://doi.org/10.1007%2Fbf00113892). [S2CID](./S2CID_(identifier)) [35506513](https://api.semanticscholar.org/CorpusID:35506513). [Archived](https://web.archive.org/web/20110516025803/http://deepblue.lib.umich.edu/bitstream/2027.42/46947/1/10994_2005_Article_422926.pdf) (PDF) from the original on 16 May 2011. Retrieved 3 September 2019.
94. [↑](./Machine_learning#cite_ref-94) Michie, D.; Spiegelhalter, D. J.; Taylor, C. C. (1994). "Machine Learning, Neural and Statistical Classification". *Ellis Horwood Series in Artificial Intelligence*. [Bibcode](./Bibcode_(identifier)):[1994mlns.book.....M](https://ui.adsabs.harvard.edu/abs/1994mlns.book.....M).
95. [↑](./Machine_learning#cite_ref-95) Zhang, Jun; Zhan, Zhi-hui; Lin, Ying; Chen, Ni; Gong, Yue-jiao; Zhong, Jing-hui; Chung, Henry S.H.; Li, Yun; Shi, Yu-hui (2011). "Evolutionary Computation Meets Machine Learning: A Survey". *IEEE Computational Intelligence Magazine*. **6** (4): 68–75. [Bibcode](./Bibcode_(identifier)):[2011ICIM....6d..68Z](https://ui.adsabs.harvard.edu/abs/2011ICIM....6d..68Z). [doi](./Doi_(identifier)):[10.1109/mci.2011.942584](https://doi.org/10.1109%2Fmci.2011.942584). [S2CID](./S2CID_(identifier)) [6760276](https://api.semanticscholar.org/CorpusID:6760276).
96. [↑](./Machine_learning#cite_ref-96) Verbert, K.; Babuška, R.; De Schutter, B. (April 2017). ["Bayesian and Dempster–Shafer reasoning for knowledge-based fault diagnosis–A comparative study"](http://resolver.tudelft.nl/uuid:7e099e57-34b9-4fd1-aadc-b1dacb661cee). *Engineering Applications of Artificial Intelligence*. **60**: 136–150. [doi](./Doi_(identifier)):[10.1016/j.engappai.2017.01.011](https://doi.org/10.1016%2Fj.engappai.2017.01.011).
97. [↑](./Machine_learning#cite_ref-YoosefzadehNajafabadi-2021_97-0) Yoosefzadeh-Najafabadi, Mohsen; Hugh, Earl; Tulpan, Dan; Sulik, John; Eskandari, Milad (2021). ["Application of Machine Learning Algorithms in Plant Breeding: Predicting Yield From Hyperspectral Reflectance in Soybean?"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7835636). *Front. Plant Sci*. **11** 624273. [Bibcode](./Bibcode_(identifier)):[2021FrPS...1124273Y](https://ui.adsabs.harvard.edu/abs/2021FrPS...1124273Y). [doi](./Doi_(identifier)):[10.3389/fpls.2020.624273](https://doi.org/10.3389%2Ffpls.2020.624273). [PMC](./PMC_(identifier)) [7835636](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7835636). [PMID](./PMID_(identifier)) [33510761](https://pubmed.ncbi.nlm.nih.gov/33510761).
98. [↑](./Machine_learning#cite_ref-98) Urbanowicz, Ryan J.; Moore, Jason H. (22 September 2009). ["Learning Classifier Systems: A Complete Introduction, Review, and Roadmap"](https://doi.org/10.1155%2F2009%2F736398). *Journal of Artificial Evolution and Applications*. **2009**: 1–25. [doi](./Doi_(identifier)):[10.1155/2009/736398](https://doi.org/10.1155%2F2009%2F736398). [ISSN](./ISSN_(identifier)) [1687-6229](https://search.worldcat.org/issn/1687-6229).
99. [↑](./Machine_learning#cite_ref-99) Zhang, C. and Zhang, S., 2002. *[Association rule mining: models and algorithms](https://books.google.com/books?id=VqSoCAAAQBAJ)*. Springer-Verlag.
100. [↑](./Machine_learning#cite_ref-100) De Castro, Leandro Nunes, and Jonathan Timmis. *[Artificial immune systems: a new computational intelligence approach](https://books.google.com/books?id=aMFP7p8DtaQC&q=%22rule-based%22)*. Springer Science & Business Media, 2002.
101. [↑](./Machine_learning#cite_ref-101) ["Federated Learning: Collaborative Machine Learning without Centralized Training Data"](http://ai.googleblog.com/2017/04/federated-learning-collaborative.html). *Google AI Blog*. 6 April 2017. [Archived](https://web.archive.org/web/20190607054623/https://ai.googleblog.com/2017/04/federated-learning-collaborative.html) from the original on 7 June 2019. Retrieved 8 June 2019.
102. [↑](./Machine_learning#cite_ref-102) Machine learning is included in the [CFA Curriculum](./Chartered_Financial_Analyst_(CFA)#Curriculum); see: [](https://www.cfainstitute.org/) {{Webarchive|url=[https://www.cfainstitute.org/](https://www.cfainstitute.org/)
103. [↑](./Machine_learning#cite_ref-103) Marcos M. López de Prado (2010). [*Machine Learning for Asset Managers*](https://www.cambridge.org/core/books/machine-learning-for-asset-managers/6D9211305EA2E425D33A9F38D0AE3545). [Cambridge University Press](./Cambridge_University_Press). [ISBN](./ISBN_(identifier)) [9781108883658](./Special:BookSources/9781108883658)
104. [↑](./Machine_learning#cite_ref-104) Ivanenko, Mikhail; Smolik, Waldemar T.; Wanta, Damian; Midura, Mateusz; Wróblewski, Przemysław; Hou, Xiaohan; Yan, Xiaoheng (2023). ["Image Reconstruction Using Supervised Learning in Wearable Electrical Impedance Tomography of the Thorax"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10538128). *Sensors*. **23** (18): 7774. [Bibcode](./Bibcode_(identifier)):[2023Senso..23.7774I](https://ui.adsabs.harvard.edu/abs/2023Senso..23.7774I). [doi](./Doi_(identifier)):[10.3390/s23187774](https://doi.org/10.3390%2Fs23187774). [PMC](./PMC_(identifier)) [10538128](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10538128). [PMID](./PMID_(identifier)) [37765831](https://pubmed.ncbi.nlm.nih.gov/37765831).
105. [↑](./Machine_learning#cite_ref-105) ["BelKor Home Page"](https://web.archive.org/web/20151110062742/http://www2.research.att.com/~volinsky/netflix/) research.att.com
106. [↑](./Machine_learning#cite_ref-106) ["The Netflix Tech Blog: Netflix Recommendations: Beyond the 5 stars (Part 1)"](https://web.archive.org/web/20160531002916/http://techblog.netflix.com/2012/04/netflix-recommendations-beyond-5-stars.html). 6 April 2012. Archived from [the original](http://techblog.netflix.com/2012/04/netflix-recommendations-beyond-5-stars.html) on 31 May 2016. Retrieved 8 August 2015.
107. [↑](./Machine_learning#cite_ref-107) Scott Patterson (13 July 2010). ["Letting the Machines Decide"](https://www.wsj.com/articles/SB10001424052748703834604575365310813948080). [The Wall Street Journal](./The_Wall_Street_Journal). [Archived](https://web.archive.org/web/20180624151019/https://www.wsj.com/articles/SB10001424052748703834604575365310813948080) from the original on 24 June 2018. Retrieved 24 June 2018.
108. [↑](./Machine_learning#cite_ref-108) Vinod Khosla (10 January 2012). ["Do We Need Doctors or Algorithms?"](https://techcrunch.com/2012/01/10/doctors-or-algorithms/). Tech Crunch. [Archived](https://web.archive.org/web/20180618175811/https://techcrunch.com/2012/01/10/doctors-or-algorithms/) from the original on 18 June 2018. Retrieved 20 October 2016.
109. [↑](./Machine_learning#cite_ref-109) [When A Machine Learning Algorithm Studied Fine Art Paintings, It Saw Things Art Historians Had Never Noticed](https://medium.com/the-physics-arxiv-blog/when-a-machine-learning-algorithm-studied-fine-art-paintings-it-saw-things-art-historians-had-never-b8e4e7bf7d3e) [Archived](https://web.archive.org/web/20160604072143/https://medium.com/the-physics-arxiv-blog/when-a-machine-learning-algorithm-studied-fine-art-paintings-it-saw-things-art-historians-had-never-b8e4e7bf7d3e) 4 June 2016 at the [Wayback Machine](./Wayback_Machine), *The Physics at [ArXiv](./ArXiv) blog*
110. [↑](./Machine_learning#cite_ref-110) Vincent, James (10 April 2019). ["The first AI-generated textbook shows what robot writers are actually good at"](https://www.theverge.com/2019/4/10/18304558/ai-writing-academic-research-book-springer-nature-artificial-intelligence). *The Verge*. [Archived](https://web.archive.org/web/20190505200409/https://www.theverge.com/2019/4/10/18304558/ai-writing-academic-research-book-springer-nature-artificial-intelligence) from the original on 5 May 2019. Retrieved 5 May 2019.
111. [↑](./Machine_learning#cite_ref-111) Vaishya, Raju; Javaid, Mohd; Khan, Ibrahim Haleem; Haleem, Abid (1 July 2020). ["Artificial Intelligence (AI) applications for COVID-19 pandemic"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7195043). *Diabetes & Metabolic Syndrome: Clinical Research & Reviews*. **14** (4): 337–339. [doi](./Doi_(identifier)):[10.1016/j.dsx.2020.04.012](https://doi.org/10.1016%2Fj.dsx.2020.04.012). [PMC](./PMC_(identifier)) [7195043](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7195043). [PMID](./PMID_(identifier)) [32305024](https://pubmed.ncbi.nlm.nih.gov/32305024).
112. [↑](./Machine_learning#cite_ref-112) Rezapouraghdam, Hamed; Akhshik, Arash; Ramkissoon, Haywantee (10 March 2021). ["Application of machine learning to predict visitors' green behavior in marine protected areas: evidence from Cyprus"](https://doi.org/10.1080%2F09669582.2021.1887878). *Journal of Sustainable Tourism*. **31** (11): 2479–2505. [doi](./Doi_(identifier)):[10.1080/09669582.2021.1887878](https://doi.org/10.1080%2F09669582.2021.1887878). [hdl](./Hdl_(identifier)):[10037/24073](https://hdl.handle.net/10037%2F24073).
113. [↑](./Machine_learning#cite_ref-113) Dey, Somdip; Singh, Amit Kumar; Wang, Xiaohang; McDonald-Maier, Klaus (15 June 2020). ["User Interaction Aware Reinforcement Learning for Power and Thermal Efficiency of CPU-GPU Mobile MPSoCs"](https://ieeexplore.ieee.org/document/9116294). [*2020 Design, Automation & Test in Europe Conference & Exhibition (DATE)*](http://repository.essex.ac.uk/27546/1/User%20Interaction%20Aware%20Reinforcement%20Learning.pdf) (PDF). pp. 1728–1733. [doi](./Doi_(identifier)):[10.23919/DATE48585.2020.9116294](https://doi.org/10.23919%2FDATE48585.2020.9116294). [ISBN](./ISBN_(identifier)) [978-3-9819263-4-7](./Special:BookSources/978-3-9819263-4-7). [S2CID](./S2CID_(identifier)) [219858480](https://api.semanticscholar.org/CorpusID:219858480). [Archived](https://web.archive.org/web/20211213192526/https://ieeexplore.ieee.org/document/9116294/) from the original on 13 December 2021. Retrieved 20 January 2022.
114. [↑](./Machine_learning#cite_ref-114) Quested, Tony. ["Smartphones get smarter with Essex innovation"](https://www.businessweekly.co.uk/news/academia-research/smartphones-get-smarter-essex-innovation). *Business Weekly*. [Archived](https://web.archive.org/web/20210624200126/https://www.businessweekly.co.uk/news/academia-research/smartphones-get-smarter-essex-innovation) from the original on 24 June 2021. Retrieved 17 June 2021.
115. [↑](./Machine_learning#cite_ref-115) Williams, Rhiannon (21 July 2020). ["Future smartphones 'will prolong their own battery life by monitoring owners' behaviour'"](https://inews.co.uk/news/technology/future-smartphones-prolong-battery-life-monitoring-behaviour-558689). *[i](./I_(British_newspaper))*. [Archived](https://web.archive.org/web/20210624201153/https://inews.co.uk/news/technology/future-smartphones-prolong-battery-life-monitoring-behaviour-558689) from the original on 24 June 2021. Retrieved 17 June 2021.
116. [↑](./Machine_learning#cite_ref-116) Rasekhschaffe, Keywan Christian; Jones, Robert C. (July 2019). "Machine Learning for Stock Selection". *Financial Analysts Journal*. **75** (3): 70–88. [doi](./Doi_(identifier)):[10.1080/0015198X.2019.1596678](https://doi.org/10.1080%2F0015198X.2019.1596678).
117. [↑](./Machine_learning#cite_ref-117) Chung, Yunsie; Green, William H. (2024). ["Machine learning from quantum chemistry to predict experimental solvent effects on reaction rates"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10866337). *Chemical Science*. **15** (7): 2410–2424. [doi](./Doi_(identifier)):[10.1039/D3SC05353A](https://doi.org/10.1039%2FD3SC05353A). [ISSN](./ISSN_(identifier)) [2041-6520](https://search.worldcat.org/issn/2041-6520). [PMC](./PMC_(identifier)) [10866337](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10866337). [PMID](./PMID_(identifier)) [38362410](https://pubmed.ncbi.nlm.nih.gov/38362410).
118. [↑](./Machine_learning#cite_ref-118) Sun, Yuran; Huang, Shih-Kai; Zhao, Xilei (1 February 2024). ["Predicting Hurricane Evacuation Decisions with Interpretable Machine Learning Methods"](https://doi.org/10.1007%2Fs13753-024-00541-1). *International Journal of Disaster Risk Science*. **15** (1): 134–148. [arXiv](./ArXiv_(identifier)):[2303.06557](https://arxiv.org/abs/2303.06557). [Bibcode](./Bibcode_(identifier)):[2024IJDRS..15..134S](https://ui.adsabs.harvard.edu/abs/2024IJDRS..15..134S). [doi](./Doi_(identifier)):[10.1007/s13753-024-00541-1](https://doi.org/10.1007%2Fs13753-024-00541-1). [ISSN](./ISSN_(identifier)) [2192-6395](https://search.worldcat.org/issn/2192-6395).
119. [↑](./Machine_learning#cite_ref-119) Sun, Yuran; Zhao, Xilei; Lovreglio, Ruggiero; Kuligowski, Erica (2024). "AI for large-scale evacuation modeling: Promises and challenges". *Interpretable Machine Learning for the Analysis, Design, Assessment, and Informed Decision Making for Civil Infrastructure*. pp. 185–204. [doi](./Doi_(identifier)):[10.1016/B978-0-12-824073-1.00014-9](https://doi.org/10.1016%2FB978-0-12-824073-1.00014-9). [ISBN](./ISBN_(identifier)) [978-0-12-824073-1](./Special:BookSources/978-0-12-824073-1).
120. [↑](./Machine_learning#cite_ref-120) Xu, Ningzhe; Lovreglio, Ruggiero; Kuligowski, Erica D.; Cova, Thomas J.; Nilsson, Daniel; Zhao, Xilei (1 March 2023). "Predicting and Assessing Wildfire Evacuation Decision-Making Using Machine Learning: Findings from the 2019 Kincade Fire". *Fire Technology*. **59** (2): 793–825. [doi](./Doi_(identifier)):[10.1007/s10694-023-01363-1](https://doi.org/10.1007%2Fs10694-023-01363-1). [ISSN](./ISSN_(identifier)) [1572-8099](https://search.worldcat.org/issn/1572-8099).
121. [↑](./Machine_learning#cite_ref-121) Wang, Ke; Shi, Xiupeng; Goh, Algena Pei Xuan; Qian, Shunzhi (June 2019). "A machine learning based study on pedestrian movement dynamics under emergency evacuation". *Fire Safety Journal*. **106**: 163–176. [Bibcode](./Bibcode_(identifier)):[2019FirSJ.106..163W](https://ui.adsabs.harvard.edu/abs/2019FirSJ.106..163W). [doi](./Doi_(identifier)):[10.1016/j.firesaf.2019.04.008](https://doi.org/10.1016%2Fj.firesaf.2019.04.008). [hdl](./Hdl_(identifier)):[10356/143390](https://hdl.handle.net/10356%2F143390).
122. [↑](./Machine_learning#cite_ref-122) Zhao, Xilei; Lovreglio, Ruggiero; Nilsson, Daniel (May 2020). "Modelling and interpreting pre-evacuation decision-making using machine learning". *Automation in Construction*. **113** 103140. [doi](./Doi_(identifier)):[10.1016/j.autcon.2020.103140](https://doi.org/10.1016%2Fj.autcon.2020.103140). [hdl](./Hdl_(identifier)):[10179/17315](https://hdl.handle.net/10179%2F17315).
123. [↑](./Machine_learning#cite_ref-123) ["Why Machine Learning Models Often Fail to Learn: QuickTake Q&A"](https://web.archive.org/web/20170320225010/https://www.bloomberg.com/news/articles/2016-11-10/why-machine-learning-models-often-fail-to-learn-quicktake-q-a). *Bloomberg.com*. 10 November 2016. Archived from [the original](https://www.bloomberg.com/news/articles/2016-11-10/why-machine-learning-models-often-fail-to-learn-quicktake-q-a) on 20 March 2017. Retrieved 10 April 2017.
124. [↑](./Machine_learning#cite_ref-124) ["The First Wave of Corporate AI Is Doomed to Fail"](https://hbr.org/2017/04/the-first-wave-of-corporate-ai-is-doomed-to-fail). *Harvard Business Review*. 18 April 2017. [Archived](https://web.archive.org/web/20180821032004/https://hbr.org/2017/04/the-first-wave-of-corporate-ai-is-doomed-to-fail) from the original on 21 August 2018. Retrieved 20 August 2018.
125. [↑](./Machine_learning#cite_ref-125) ["Why the A.I. euphoria is doomed to fail"](https://venturebeat.com/2016/09/17/why-the-a-i-euphoria-is-doomed-to-fail/). *VentureBeat*. 18 September 2016. [Archived](https://web.archive.org/web/20180819124138/https://venturebeat.com/2016/09/17/why-the-a-i-euphoria-is-doomed-to-fail/) from the original on 19 August 2018. Retrieved 20 August 2018.
126. [↑](./Machine_learning#cite_ref-126) ["9 Reasons why your machine learning project will fail"](https://www.kdnuggets.com/2018/07/why-machine-learning-project-fail.html). *www.kdnuggets.com*. [Archived](https://web.archive.org/web/20180821031802/https://www.kdnuggets.com/2018/07/why-machine-learning-project-fail.html) from the original on 21 August 2018. Retrieved 20 August 2018.
127. [1](./Machine_learning#cite_ref-Babuta-2018_127-0) [2](./Machine_learning#cite_ref-Babuta-2018_127-1) Babuta, Alexander; Oswald, Marion; Rinik, Christine (2018). [Transparency and Intelligibility](https://www.jstor.org/stable/resrep37375.8) (Report). Royal United Services Institute (RUSI). pp. 17–22. [Archived](https://web.archive.org/web/20231209002929/https://www.jstor.org/stable/resrep37375.8) from the original on 9 December 2023. Retrieved 9 December 2023.
128. [↑](./Machine_learning#cite_ref-128) ["Why Uber's self-driving car killed a pedestrian"](https://www.economist.com/the-economist-explains/2018/05/29/why-ubers-self-driving-car-killed-a-pedestrian). *The Economist*. [Archived](https://web.archive.org/web/20180821031818/https://www.economist.com/the-economist-explains/2018/05/29/why-ubers-self-driving-car-killed-a-pedestrian) from the original on 21 August 2018. Retrieved 20 August 2018.
129. [↑](./Machine_learning#cite_ref-129) ["IBM's Watson recommended 'unsafe and incorrect' cancer treatments – STAT"](https://www.statnews.com/2018/07/25/ibm-watson-recommended-unsafe-incorrect-treatments/). *STAT*. 25 July 2018. [Archived](https://web.archive.org/web/20180821062616/https://www.statnews.com/2018/07/25/ibm-watson-recommended-unsafe-incorrect-treatments/) from the original on 21 August 2018. Retrieved 21 August 2018.
130. [↑](./Machine_learning#cite_ref-130) Hernandez, Daniela; Greenwald, Ted (11 August 2018). ["IBM Has a Watson Dilemma"](https://www.wsj.com/articles/ibm-bet-billions-that-watson-could-improve-cancer-treatment-it-hasnt-worked-1533961147). *[The Wall Street Journal](./The_Wall_Street_Journal)*. [ISSN](./ISSN_(identifier)) [0099-9660](https://search.worldcat.org/issn/0099-9660). [Archived](https://web.archive.org/web/20180821031906/https://www.wsj.com/articles/ibm-bet-billions-that-watson-could-improve-cancer-treatment-it-hasnt-worked-1533961147) from the original on 21 August 2018. Retrieved 21 August 2018.
131. [↑](./Machine_learning#cite_ref-131) Allyn, Bobby (27 February 2023). ["How Microsoft's experiment in artificial intelligence tech backfired"](https://www.npr.org/2023/02/27/1159630243/how-microsofts-experiment-in-artificial-intelligence-tech-backfired). *National Public Radio*. [Archived](https://web.archive.org/web/20231208234056/https://www.npr.org/2023/02/27/1159630243/how-microsofts-experiment-in-artificial-intelligence-tech-backfired) from the original on 8 December 2023. Retrieved 8 December 2023.
132. [↑](./Machine_learning#cite_ref-132) Reddy, Shivani M.; Patel, Sheila; Weyrich, Meghan; Fenton, Joshua; Viswanathan, Meera (2020). ["Comparison of a traditional systematic review approach with review-of-reviews and semi-automation as strategies to update the evidence"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7574591). *Systematic Reviews*. **9** (1): 243. [doi](./Doi_(identifier)):[10.1186/s13643-020-01450-2](https://doi.org/10.1186%2Fs13643-020-01450-2). [ISSN](./ISSN_(identifier)) [2046-4053](https://search.worldcat.org/issn/2046-4053). [PMC](./PMC_(identifier)) [7574591](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7574591). [PMID](./PMID_(identifier)) [33076975](https://pubmed.ncbi.nlm.nih.gov/33076975).
133. [↑](./Machine_learning#cite_ref-133) Rudin, Cynthia (2019). ["Stop explaining black box machine learning models for high stakes decisions and use interpretable models instead"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9122117). *Nature Machine Intelligence*. **1** (5): 206–215. [doi](./Doi_(identifier)):[10.1038/s42256-019-0048-x](https://doi.org/10.1038%2Fs42256-019-0048-x). [PMC](./PMC_(identifier)) [9122117](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9122117). [PMID](./PMID_(identifier)) [35603010](https://pubmed.ncbi.nlm.nih.gov/35603010).
134. [↑](./Machine_learning#cite_ref-134) Hu, Tongxi; Zhang, Xuesong; Bohrer, Gil; Liu, Yanlan; Zhou, Yuyu; Martin, Jay; LI, Yang; Zhao, Kaiguang (2023). ["Crop yield prediction via explainable AI and interpretable machine learning: Dangers of black box models for evaluating climate change impacts on crop yield"](https://doi.org/10.1016%2Fj.agrformet.2023.109458). *Agricultural and Forest Meteorology*. **336** 109458. [Bibcode](./Bibcode_(identifier)):[2023AgFM..33609458H](https://ui.adsabs.harvard.edu/abs/2023AgFM..33609458H). [doi](./Doi_(identifier)):[10.1016/j.agrformet.2023.109458](https://doi.org/10.1016%2Fj.agrformet.2023.109458). [S2CID](./S2CID_(identifier)) [258552400](https://api.semanticscholar.org/CorpusID:258552400).
135. [↑](./Machine_learning#cite_ref-FOOTNOTEDomingos2015Chapter_6,_Chapter_7_135-0) [Domingos 2015](./Machine_learning#CITEREFDomingos2015), Chapter 6, Chapter 7.
136. [↑](./Machine_learning#cite_ref-136) ["'Generative inbreeding' and its risk to human culture"](https://venturebeat.com/ai/generative-inbreeding-and-its-risk-to-human-culture/). 26 August 2023.
137. [↑](./Machine_learning#cite_ref-137) ["AI could choke on its own exhaust as it fills the web"](https://www.axios.com/2023/08/28/ai-content-flood-model-collapse). 28 August 2023.
138. [↑](./Machine_learning#cite_ref-138) ["AI Cannibalism and the Law – Colorado Technology Law Journal"](https://ctlj.colorado.edu/?p=1280).
139. [↑](./Machine_learning#cite_ref-139) ["The Curious Case of AI Cannibalism & Possible Solutions"](https://www.cogitotech.com/blog/the-curious-case-of-ai-cannibalism-and-possible-solutions/). 26 July 2023.,
140. [↑](./Machine_learning#cite_ref-140) ["Inbred, gibberish or just MAD? Warnings rise about AI models"](https://www.france24.com/en/live-news/20240805-inbred-gibberish-or-just-mad-warnings-rise-about-ai-models). *France 24*. 5 August 2024. Retrieved 31 December 2024.
141. [↑](./Machine_learning#cite_ref-141) ["Model Autophagy Disorder – the Livescu Initiative on Neuro, Narrative and AI"](https://livescu.ucla.edu/model-autophagy-disorder/).
142. [↑](./Machine_learning#cite_ref-142) ["Generative AI Goes 'MAD' when Trained on AI-Created Data over Five Times"](https://www.tomshardware.com/news/generative-ai-goes-mad-when-trained-on-artificial-data-over-five-times). 12 July 2023.
143. [↑](./Machine_learning#cite_ref-143) Alemohammad, Sina; Casco-Rodriguez, Josue; Luzi, Lorenzo; Ahmed Imtiaz Humayun; Babaei, Hossein; LeJeune, Daniel; Siahkoohi, Ali; Baraniuk, Richard G. (2023). "Self-Consuming Generative Models Go MAD". [arXiv](./ArXiv_(identifier)):[2307.01850](https://arxiv.org/abs/2307.01850) [[cs.LG](https://arxiv.org/archive/cs.LG)].
144. [↑](./Machine_learning#cite_ref-Hallucination_(artificial_intelligence)_Hicks_Humphries_Slater_2024_144-0) Hicks, Michael Townsen; Humphries, James; Slater, Joe (June 2024). ["ChatGPT is bullshit"](https://eprints.gla.ac.uk/327588/1/327588.pdf) (PDF). *Ethics and Information Technology*. **26** (2) 38. [doi](./Doi_(identifier)):[10.1007/s10676-024-09775-5](https://doi.org/10.1007%2Fs10676-024-09775-5). [Archived](https://web.archive.org/web/20250513142821/https://eprints.gla.ac.uk/327588/1/327588.pdf) (PDF) from the original on 13 May 2025. Retrieved 23 May 2025.
145. [↑](./Machine_learning#cite_ref-145) Liang, Kaiqu; Hu, Haimin; Zhao, Xuandong; Song, Dawn; Griffiths, Thomas L.; Fernández Fisac, Jaime (2025). "Machine Bullshit: Characterizing the Emergent Disregard for Truth in Large Language Models". [arXiv](./ArXiv_(identifier)):[2507.07484](https://arxiv.org/abs/2507.07484) [[cs.CL](https://arxiv.org/archive/cs.CL)].
146. [↑](./Machine_learning#cite_ref-Hallucination_(artificial_intelligence)_ars_making_things_up_146-0) Edwards, Benj (6 April 2023). ["Why ChatGPT and Bing Chat are so good at making things up"](https://arstechnica.com/information-technology/2023/04/why-ai-chatbots-are-the-ultimate-bs-machines-and-how-people-hope-to-fix-them/). *Ars Technica*. [Archived](https://web.archive.org/web/20230611024338/https://arstechnica.com/information-technology/2023/04/why-ai-chatbots-are-the-ultimate-bs-machines-and-how-people-hope-to-fix-them/) from the original on 11 June 2023. Retrieved 11 June 2023.
147. [↑](./Machine_learning#cite_ref-147) Ortega, Pedro A.; Kunesch, Markus; Delétang, Grégoire; Genewein, Tim; Grau-Moya, Jordi; Veness, Joel; Buchli, Jonas; Degrave, Jonas; Piot, Bilal; Perolat, Julien; Everitt, Tom; Tallec, Corentin; Parisotto, Emilio; Erez, Tom; Chen, Yutian; Reed, Scott; Hutter, Marcus; Nando de Freitas; Legg, Shane (2021). Shaking the foundations: Delusions in sequence models for interaction and control (Preprint). [arXiv](./ArXiv_(identifier)):[2110.10819](https://arxiv.org/abs/2110.10819).
148. [↑](./Machine_learning#cite_ref-148) Maynez, Joshua; Narayan, Shashi; Bohnet, Bernd; McDonald, Ryan (2020). "On Faithfulness and Factuality in Abstractive Summarization". *Proceedings of the 58th Annual Meeting of the Association for Computational Linguistics*. pp. 1906–1919. [doi](./Doi_(identifier)):[10.18653/v1/2020.acl-main.173](https://doi.org/10.18653%2Fv1%2F2020.acl-main.173).
149. [↑](./Machine_learning#cite_ref-Hallucination_(artificial_intelligence)_nyt_149-0) Metz, Cade (6 November 2023). ["Chatbots May 'Hallucinate' More Often Than Many Realize"](https://www.nytimes.com/2023/11/06/technology/chatbots-hallucination-rates.html). *The New York Times*. [Archived](https://web.archive.org/web/20231207081252/https://www.nytimes.com/2023/11/06/technology/chatbots-hallucination-rates.html) from the original on 7 December 2023. Retrieved 6 November 2023.
150. [↑](./Machine_learning#cite_ref-Hallucination_(artificial_intelligence)_de_Wynter-2023_150-0) de Wynter, Adrian; Wang, Xun; Sokolov, Alex; Gu, Qilong; Chen, Si-Qing (September 2023). ["An evaluation on large language model outputs: Discourse and memorization"](https://doi.org/10.1016%2Fj.nlp.2023.100024). *Natural Language Processing Journal*. **4** 100024. [arXiv](./ArXiv_(identifier)):[2304.08637](https://arxiv.org/abs/2304.08637). [doi](./Doi_(identifier)):[10.1016/j.nlp.2023.100024](https://doi.org/10.1016%2Fj.nlp.2023.100024).
151. [↑](./Machine_learning#cite_ref-Hallucination_(artificial_intelligence)_cnbc_several_errors_151-0) Leswing, Kif (14 February 2023). ["Microsoft's Bing A.I. made several factual errors in last week's launch demo"](https://www.cnbc.com/2023/02/14/microsoft-bing-ai-made-several-errors-in-launch-demo-last-week-.html). *CNBC*. [Archived](https://web.archive.org/web/20230216072604/https://www.cnbc.com/2023/02/14/microsoft-bing-ai-made-several-errors-in-launch-demo-last-week-.html) from the original on 16 February 2023. Retrieved 16 February 2023.
152. [↑](./Machine_learning#cite_ref-Hallucination_(artificial_intelligence)_sigplan_152-0) Kang, Eunsuk; Shaw, Mary (2024). "tl;dr: Chill, y'all: AI Will Not Devour SE". *Proceedings of the 2024 ACM SIGPLAN International Symposium on New Ideas, New Paradigms, and Reflections on Programming and Software*. pp. 303–315. [arXiv](./ArXiv_(identifier)):[2409.00764](https://arxiv.org/abs/2409.00764). [doi](./Doi_(identifier)):[10.1145/3689492.3689816](https://doi.org/10.1145%2F3689492.3689816). [ISBN](./ISBN_(identifier)) [979-8-4007-1215-9](./Special:BookSources/979-8-4007-1215-9).
153. [↑](./Machine_learning#cite_ref-Hallucination_(artificial_intelligence)_salon_153-0) Desai, Rajiv (13 October 2023). ["Is artificial intelligence (AI) an existential threat? – Dr Rajiv Desai"](https://drrajivdesaimd.com/2023/10/13/is-artificial-intelligence-ai-an-existential-threat/). [Archived](https://web.archive.org/web/20260111024917/https://drrajivdesaimd.com/2023/10/13/is-artificial-intelligence-ai-an-existential-threat/) from the original on 11 January 2026. Retrieved 25 November 2025.
154. [↑](./Machine_learning#cite_ref-Hallucination_(artificial_intelligence)_Garcez_154-0) Garcez, Artur (30 May 2025). Vass, Steven (ed.). "Neurosymbolic AI is the answer to large language models' inability to stop hallucinating". *The Conversation*. [doi](./Doi_(identifier)):[10.64628/AB.5gpku36ct](https://doi.org/10.64628%2FAB.5gpku36ct).
155. [↑](./Machine_learning#cite_ref-FOOTNOTEDomingos2015286_155-0) [Domingos 2015](./Machine_learning#CITEREFDomingos2015), p. 286.
156. [↑](./Machine_learning#cite_ref-156) ["Single pixel change fools AI programs"](https://www.bbc.com/news/technology-41845878). *BBC News*. 3 November 2017. [Archived](https://web.archive.org/web/20180322011306/http://www.bbc.com/news/technology-41845878) from the original on 22 March 2018. Retrieved 12 March 2018.
157. [↑](./Machine_learning#cite_ref-157) ["AI Has a Hallucination Problem That's Proving Tough to Fix"](https://www.wired.com/story/ai-has-a-hallucination-problem-thats-proving-tough-to-fix/). *WIRED*. 2018. [Archived](https://web.archive.org/web/20180312024533/https://www.wired.com/story/ai-has-a-hallucination-problem-thats-proving-tough-to-fix/) from the original on 12 March 2018. Retrieved 12 March 2018.
158. [↑](./Machine_learning#cite_ref-TD_1_158-0) Madry, A.; Makelov, A.; Schmidt, L.; Tsipras, D.; Vladu, A. (4 September 2019). "Towards deep learning models resistant to adversarial attacks". [arXiv](./ArXiv_(identifier)):[1706.06083](https://arxiv.org/abs/1706.06083) [[stat.ML](https://arxiv.org/archive/stat.ML)].
159. [↑](./Machine_learning#cite_ref-159) ["Adversarial Machine Learning – CLTC UC Berkeley Center for Long-Term Cybersecurity"](https://cltc.berkeley.edu/aml/). *CLTC*. [Archived](https://web.archive.org/web/20220517045352/https://cltc.berkeley.edu/aml/) from the original on 17 May 2022. Retrieved 25 May 2022.
160. [↑](./Machine_learning#cite_ref-160) ["Machine-learning models vulnerable to undetectable backdoors"](https://www.theregister.com/2022/04/21/machine_learning_models_backdoors/). *[The Register](./The_Register)*. [Archived](https://web.archive.org/web/20220513171215/https://www.theregister.com/2022/04/21/machine_learning_models_backdoors/) from the original on 13 May 2022. Retrieved 13 May 2022.
161. [↑](./Machine_learning#cite_ref-161) ["Undetectable Backdoors Plantable In Any Machine-Learning Algorithm"](https://spectrum.ieee.org/machine-learningbackdoor). *[IEEE Spectrum](./IEEE_Spectrum)*. 10 May 2022. [Archived](https://web.archive.org/web/20220511152052/https://spectrum.ieee.org/machine-learningbackdoor) from the original on 11 May 2022. Retrieved 13 May 2022.
162. [↑](./Machine_learning#cite_ref-162) Goldwasser, Shafi; Kim, Michael P.; Vaikuntanathan, Vinod; Zamir, Or (14 April 2022). "Planting Undetectable Backdoors in Machine Learning Models". [arXiv](./ArXiv_(identifier)):[2204.06974](https://arxiv.org/abs/2204.06974) [[cs.LG](https://arxiv.org/archive/cs.LG)].
163. [↑](./Machine_learning#cite_ref-163) Kohavi, Ron (1995). ["A Study of Cross-Validation and Bootstrap for Accuracy Estimation and Model Selection"](https://ai.stanford.edu/~ronnyk/accEst.pdf) (PDF). *International Joint Conference on Artificial Intelligence*. [Archived](https://web.archive.org/web/20180712102706/http://web.cs.iastate.edu/~jtian/cs573/Papers/Kohavi-IJCAI-95.pdf) (PDF) from the original on 12 July 2018. Retrieved 26 March 2023.
164. [↑](./Machine_learning#cite_ref-164) Catal, Cagatay (2012). ["Performance Evaluation Metrics for Software Fault Prediction Studies"](http://www.uni-obuda.hu/journal/Catal_36.pdf) (PDF). *Acta Polytechnica Hungarica*. **9** (4). Retrieved 2 October 2016.
165. [1](./Machine_learning#cite_ref-Ethics_of_artificial_intelligence_Muller-2020_165-0) [2](./Machine_learning#cite_ref-Ethics_of_artificial_intelligence_Muller-2020_165-1) Müller, Vincent C. (30 April 2020). ["Ethics of Artificial Intelligence and Robotics"](https://plato.stanford.edu/entries/ethics-ai/). *Stanford Encyclopedia of Philosophy*. [Archived](https://web.archive.org/web/20201010174108/https://plato.stanford.edu/entries/ethics-ai/) from the original on 10 October 2020.
166. [↑](./Machine_learning#cite_ref-Ethics_of_artificial_intelligence_:4_166-0) ["Assessing potential future artificial intelligence risks, benefits and policy imperatives"](https://www.oecd.org/en/publications/assessing-potential-future-artificial-intelligence-risks-benefits-and-policy-imperatives_3f4e3dfb-en.html). *OECD*. 14 November 2024. Retrieved 4 August 2025.
167. [1](./Machine_learning#cite_ref-Garcia-2016_167-0) [2](./Machine_learning#cite_ref-Garcia-2016_167-1) Garcia, Megan (2016). "Racist in the Machine". *World Policy Journal*. **33** (4): 111–117. [doi](./Doi_(identifier)):[10.1215/07402775-3813015](https://doi.org/10.1215%2F07402775-3813015). [ISSN](./ISSN_(identifier)) [0740-2775](https://search.worldcat.org/issn/0740-2775). [S2CID](./S2CID_(identifier)) [151595343](https://api.semanticscholar.org/CorpusID:151595343).
168. [↑](./Machine_learning#cite_ref-168) Bostrom, Nick (2011). ["The Ethics of Artificial Intelligence"](https://web.archive.org/web/20160304015020/http://www.nickbostrom.com/ethics/artificial-intelligence.pdf) (PDF). Archived from [the original](http://www.nickbostrom.com/ethics/artificial-intelligence.pdf) (PDF) on 4 March 2016. Retrieved 11 April 2016.
169. [↑](./Machine_learning#cite_ref-Edionwe_Outline_169-0) Edionwe, Tolulope. ["The fight against racist algorithms"](https://theoutline.com/post/1571/the-fight-against-racist-algorithms). *The Outline*. [Archived](https://web.archive.org/web/20171117174504/https://theoutline.com/post/1571/the-fight-against-racist-algorithms) from the original on 17 November 2017. Retrieved 17 November 2017.
170. [↑](./Machine_learning#cite_ref-Jeffries_Outline_170-0) Jeffries, Adrianne. ["Machine learning is racist because the internet is racist"](https://theoutline.com/post/1439/machine-learning-is-racist-because-the-internet-is-racist). *The Outline*. [Archived](https://web.archive.org/web/20171117174503/https://theoutline.com/post/1439/machine-learning-is-racist-because-the-internet-is-racist) from the original on 17 November 2017. Retrieved 17 November 2017.
171. [1](./Machine_learning#cite_ref-Silva-2018_171-0) [2](./Machine_learning#cite_ref-Silva-2018_171-1) Silva, Selena; Kenney, Martin (2018). "Algorithms, Platforms, and Ethnic Bias: An Integrative Essay". *Phylon*. **55** (1 & 2): 9–37. [JSTOR](./JSTOR_(identifier)) [26545017](https://www.jstor.org/stable/26545017).
172. [↑](./Machine_learning#cite_ref-172) Wong, Carissa (30 March 2023). "AI 'fairness' research held back by lack of diversity". *Nature*. [doi](./Doi_(identifier)):[10.1038/d41586-023-00935-z](https://doi.org/10.1038%2Fd41586-023-00935-z). [PMID](./PMID_(identifier)) [36997714](https://pubmed.ncbi.nlm.nih.gov/36997714).
173. [1](./Machine_learning#cite_ref-Zhang_173-0) [2](./Machine_learning#cite_ref-Zhang_173-1) Zhang, Jack Clark. ["Artificial Intelligence Index Report 2021"](https://web.archive.org/web/20240519121545/https://aiindex.stanford.edu/wp-content/uploads/2021/11/2021-AI-Index-Report_Master.pdf) (PDF). *Stanford Institute for Human-Centered Artificial Intelligence*. Archived from [the original](https://aiindex.stanford.edu/wp-content/uploads/2021/11/2021-AI-Index-Report_Master.pdf) (PDF) on 19 May 2024. Retrieved 9 December 2023.
174. [↑](./Machine_learning#cite_ref-174) Caliskan, Aylin; Bryson, Joanna J.; Narayanan, Arvind (14 April 2017). "Semantics derived automatically from language corpora contain human-like biases". *Science*. **356** (6334): 183–186. [arXiv](./ArXiv_(identifier)):[1608.07187](https://arxiv.org/abs/1608.07187). [Bibcode](./Bibcode_(identifier)):[2017Sci...356..183C](https://ui.adsabs.harvard.edu/abs/2017Sci...356..183C). [doi](./Doi_(identifier)):[10.1126/science.aal4230](https://doi.org/10.1126%2Fscience.aal4230). [ISSN](./ISSN_(identifier)) [0036-8075](https://search.worldcat.org/issn/0036-8075). [PMID](./PMID_(identifier)) [28408601](https://pubmed.ncbi.nlm.nih.gov/28408601). [S2CID](./S2CID_(identifier)) [23163324](https://api.semanticscholar.org/CorpusID:23163324).
175. [↑](./Machine_learning#cite_ref-175) Wang, Xinan; Dasgupta, Sanjoy (2016), Lee, D. D.; Sugiyama, M.; Luxburg, U. V.; Guyon, I. (eds.), ["An algorithm for L1 nearest neighbor search via monotonic embedding"](http://papers.nips.cc/paper/6227-an-algorithm-for-l1-nearest-neighbor-search-via-monotonic-embedding.pdf) (PDF), *Advances in Neural Information Processing Systems 29*, Curran Associates, Inc., pp. 983–991, [archived](https://web.archive.org/web/20170407051313/http://papers.nips.cc/paper/6227-an-algorithm-for-l1-nearest-neighbor-search-via-monotonic-embedding.pdf) (PDF) from the original on 7 April 2017, retrieved 20 August 2018
176. [↑](./Machine_learning#cite_ref-176) M.O.R. Prates; P.H.C. Avelar; L.C. Lamb (11 March 2019). "Assessing Gender Bias in Machine Translation – A Case Study with Google Translate". [arXiv](./ArXiv_(identifier)):[1809.02208](https://arxiv.org/abs/1809.02208) [[cs.CY](https://arxiv.org/archive/cs.CY)].
177. [↑](./Machine_learning#cite_ref-177) Narayanan, Arvind (24 August 2016). ["Language necessarily contains human biases, and so will machines trained on language corpora"](https://freedom-to-tinker.com/2016/08/24/language-necessarily-contains-human-biases-and-so-will-machines-trained-on-language-corpora/). *Freedom to Tinker*. [Archived](https://web.archive.org/web/20180625021555/https://freedom-to-tinker.com/2016/08/24/language-necessarily-contains-human-biases-and-so-will-machines-trained-on-language-corpora/) from the original on 25 June 2018. Retrieved 19 November 2016.
178. [↑](./Machine_learning#cite_ref-178) Metz, Rachel (24 March 2016). ["Why Microsoft Accidentally Unleashed a Neo-Nazi Sexbot"](https://www.technologyreview.com/s/601111/why-microsoft-accidentally-unleashed-a-neo-nazi-sexbot/). *MIT Technology Review*. [Archived](https://web.archive.org/web/20181109023754/https://www.technologyreview.com/s/601111/why-microsoft-accidentally-unleashed-a-neo-nazi-sexbot/) from the original on 9 November 2018. Retrieved 20 August 2018.
179. [↑](./Machine_learning#cite_ref-179) Vincent, James (12 January 2018). ["Google 'fixed' its racist algorithm by removing gorillas from its image-labeling tech"](https://www.theverge.com/2018/1/12/16882408/google-racist-gorillas-photo-recognition-algorithm-ai). *The Verge*. [Archived](https://web.archive.org/web/20180821031830/https://www.theverge.com/2018/1/12/16882408/google-racist-gorillas-photo-recognition-algorithm-ai) from the original on 21 August 2018. Retrieved 20 August 2018.
180. [↑](./Machine_learning#cite_ref-180) Crawford, Kate (25 June 2016). ["Opinion | Artificial Intelligence's White Guy Problem"](https://www.nytimes.com/2016/06/26/opinion/sunday/artificial-intelligences-white-guy-problem.html). *[New York Times](./New_York_Times)*. [Archived](https://web.archive.org/web/20210114220619/https://www.nytimes.com/2016/06/26/opinion/sunday/artificial-intelligences-white-guy-problem.html) from the original on 14 January 2021. Retrieved 20 August 2018.
181. [↑](./Machine_learning#cite_ref-181) Simonite, Tom (30 March 2017). ["Microsoft: AI Isn't Yet Adaptable Enough to Help Businesses"](https://www.technologyreview.com/s/603944/microsoft-ai-isnt-yet-adaptable-enough-to-help-businesses/). *MIT Technology Review*. [Archived](https://web.archive.org/web/20181109022820/https://www.technologyreview.com/s/603944/microsoft-ai-isnt-yet-adaptable-enough-to-help-businesses/) from the original on 9 November 2018. Retrieved 20 August 2018.
182. [↑](./Machine_learning#cite_ref-182) Hempel, Jessi (13 November 2018). ["Fei-Fei Li's Quest to Make Machines Better for Humanity"](https://www.wired.com/story/fei-fei-li-artificial-intelligence-humanity/). *Wired*. [ISSN](./ISSN_(identifier)) [1059-1028](https://search.worldcat.org/issn/1059-1028). [Archived](https://web.archive.org/web/20201214095220/https://www.wired.com/story/fei-fei-li-artificial-intelligence-humanity/) from the original on 14 December 2020. Retrieved 17 February 2019.
183. [↑](./Machine_learning#cite_ref-183) Char, D. S.; Shah, N. H.; Magnus, D. (2018). ["Implementing Machine Learning in Health Care—Addressing Ethical Challenges"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5962261). *[New England Journal of Medicine](./New_England_Journal_of_Medicine)*. **378** (11): 981–983. [doi](./Doi_(identifier)):[10.1056/nejmp1714229](https://doi.org/10.1056%2Fnejmp1714229). [PMC](./PMC_(identifier)) [5962261](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5962261). [PMID](./PMID_(identifier)) [29539284](https://pubmed.ncbi.nlm.nih.gov/29539284).
184. [↑](./Machine_learning#cite_ref-184) Research, AI (23 October 2015). ["Deep Neural Networks for Acoustic Modeling in Speech Recognition"](http://airesearch.com/ai-research-papers/deep-neural-networks-for-acoustic-modeling-in-speech-recognition/). *airesearch.com*. [Archived](https://web.archive.org/web/20160201033801/http://airesearch.com/ai-research-papers/deep-neural-networks-for-acoustic-modeling-in-speech-recognition/) from the original on 1 February 2016. Retrieved 23 October 2015.
185. [↑](./Machine_learning#cite_ref-185) ["GPUs Continue to Dominate the AI Accelerator Market for Now"](https://www.informationweek.com/big-data/ai-machine-learning/gpus-continue-to-dominate-the-ai-accelerator-market-for-now/a/d-id/1336475). *InformationWeek*. December 2019. [Archived](https://web.archive.org/web/20200610094310/https://www.informationweek.com/big-data/ai-machine-learning/gpus-continue-to-dominate-the-ai-accelerator-market-for-now/a/d-id/1336475) from the original on 10 June 2020. Retrieved 11 June 2020.
186. [↑](./Machine_learning#cite_ref-186) Ray, Tiernan (2019). ["AI is changing the entire nature of compute"](https://www.zdnet.com/article/ai-is-changing-the-entire-nature-of-compute/). *ZDNet*. [Archived](https://web.archive.org/web/20200525144635/https://www.zdnet.com/article/ai-is-changing-the-entire-nature-of-compute/) from the original on 25 May 2020. Retrieved 11 June 2020.
187. [↑](./Machine_learning#cite_ref-187) ["AI and compute"](https://openai.com/blog/ai-and-compute/). *OpenAI*. 16 May 2018. [Archived](https://web.archive.org/web/20200617200602/https://openai.com/blog/ai-and-compute/) from the original on 17 June 2020. Retrieved 11 June 2020.
188. [↑](./Machine_learning#cite_ref-188) Jouppi, Norman P.; Young, Cliff; Patil, Nishant; Patterson, David; Agrawal, Gaurav; Bajwa, Raminder; Bates, Sarah; Bhatia, Suresh; Boden, Nan; Borchers, Al; Boyle, Rick; Cantin, Pierre-luc; Chao, Clifford; Clark, Chris; Coriell, Jeremy (24 June 2017). "In-Datacenter Performance Analysis of a Tensor Processing Unit". *Proceedings of the 44th Annual International Symposium on Computer Architecture*. ISCA '17. New York, NY, US: Association for Computing Machinery. pp. 1–12. [arXiv](./ArXiv_(identifier)):[1704.04760](https://arxiv.org/abs/1704.04760). [doi](./Doi_(identifier)):[10.1145/3079856.3080246](https://doi.org/10.1145%2F3079856.3080246). [ISBN](./ISBN_(identifier)) [978-1-4503-4892-8](./Special:BookSources/978-1-4503-4892-8).
189. [↑](./Machine_learning#cite_ref-189) Best, Jo (8 December 2020). ["What is neuromorphic computing? Everything you need to know about how it is changing the future of computing"](https://www.zdnet.com/article/what-is-neuromorphic-computing-everything-you-need-to-know-about-how-it-will-change-the-future-of-computing/). *ZDNET*. Retrieved 21 November 2024.
190. [↑](./Machine_learning#cite_ref-190) Hecate He (27 May 2021). Michael Sarazen; Chain Zhang (eds.). ["Cornell & NTT's Physical Neural Networks: A "Radical Alternative for Implementing Deep Neural Networks" That Enables Arbitrary Physical Systems Training"](https://syncedreview.com/2021/05/27/deepmind-podracer-tpu-based-rl-frameworks-deliver-exceptional-performance-at-low-cost-28/). *Synced*. [Archived](https://web.archive.org/web/20211027183428/https://syncedreview.com/2021/05/27/deepmind-podracer-tpu-based-rl-frameworks-deliver-exceptional-performance-at-low-cost-28/) from the original on 27 October 2021. Retrieved 12 October 2021.
191. [↑](./Machine_learning#cite_ref-191) Clark, Lindsay (5 October 2021). ["Nano-spaghetti to solve neural network power consumption"](https://www.theregister.com/2021/10/05/analogue_neural_network_research/). *The Register*. [Archived](https://web.archive.org/web/20211006150057/https://www.theregister.com/2021/10/05/analogue_neural_network_research/) from the original on 6 October 2021. Retrieved 12 October 2021.
192. [↑](./Machine_learning#cite_ref-192) Fafoutis, Xenofon; Marchegiani, Letizia; Elsts, Atis; Pope, James; Piechocki, Robert; Craddock, Ian (7 May 2018). ["Extending the battery lifetime of wearable sensors with embedded machine learning"](https://ieeexplore.ieee.org/document/8355116). [*2018 IEEE 4th World Forum on Internet of Things (WF-IoT)*](https://research-information.bris.ac.uk/en/publications/b8fdb58b-7114-45c6-82e4-4ab239c1327f). pp. 269–274. [doi](./Doi_(identifier)):[10.1109/WF-IoT.2018.8355116](https://doi.org/10.1109%2FWF-IoT.2018.8355116). [hdl](./Hdl_(identifier)):[1983/b8fdb58b-7114-45c6-82e4-4ab239c1327f](https://hdl.handle.net/1983%2Fb8fdb58b-7114-45c6-82e4-4ab239c1327f). [ISBN](./ISBN_(identifier)) [978-1-4673-9944-9](./Special:BookSources/978-1-4673-9944-9). [S2CID](./S2CID_(identifier)) [19192912](https://api.semanticscholar.org/CorpusID:19192912). [Archived](https://web.archive.org/web/20220118182543/https://ieeexplore.ieee.org/abstract/document/8355116?casa_token=LCpUeGLS1e8AAAAA:2OjuJfNwZBnV2pgDxfnEAC-jbrETv_BpTcX35_aFqN6IULFxu1xbYbVSRpD-zMd4GCUMELyG) from the original on 18 January 2022. Retrieved 17 January 2022.
193. [↑](./Machine_learning#cite_ref-193) ["A Beginner's Guide To Machine learning For Embedded Systems"](https://analyticsindiamag.com/a-beginners-guide-to-machine-learning-for-embedded-systems/). *Analytics India Magazine*. 2 June 2021. [Archived](https://web.archive.org/web/20220118182754/https://analyticsindiamag.com/a-beginners-guide-to-machine-learning-for-embedded-systems/) from the original on 18 January 2022. Retrieved 17 January 2022.
194. [↑](./Machine_learning#cite_ref-194) Synced (12 January 2022). ["Google, Purdue & Harvard U's Open-Source Framework for TinyML Achieves up to 75x Speedups on FPGAs | Synced"](https://syncedreview.com/2022/01/12/deepmind-podracer-tpu-based-rl-frameworks-deliver-exceptional-performance-at-low-cost-183/). *syncedreview.com*. [Archived](https://web.archive.org/web/20220118182404/https://syncedreview.com/2022/01/12/deepmind-podracer-tpu-based-rl-frameworks-deliver-exceptional-performance-at-low-cost-183/) from the original on 18 January 2022. Retrieved 17 January 2022.
195. [↑](./Machine_learning#cite_ref-195) AlSelek, Mohammad; Alcaraz-Calero, Jose M.; Wang, Qi (2024). ["Dynamic AI-IoT: Enabling Updatable AI Models in Ultralow-Power 5G IoT Devices"](https://research-portal.uws.ac.uk/en/publications/c8edfe21-77d0-4c3e-a8bc-d384faf605a0). *IEEE Internet of Things Journal*. **11** (8): 14192–14205. [Bibcode](./Bibcode_(identifier)):[2024IITJ...1114192A](https://ui.adsabs.harvard.edu/abs/2024IITJ...1114192A). [doi](./Doi_(identifier)):[10.1109/JIOT.2023.3340858](https://doi.org/10.1109%2FJIOT.2023.3340858).
196. [↑](./Machine_learning#cite_ref-196) Giri, Davide; Chiu, Kuan-Lin; Di Guglielmo, Giuseppe; Mantovani, Paolo; [Carloni, Luca P.](./Luca_Carloni) (15 June 2020). ["ESP4ML: Platform-Based Design of Systems-on-Chip for Embedded Machine Learning"](https://ieeexplore.ieee.org/document/9116317). *2020 Design, Automation & Test in Europe Conference & Exhibition (DATE)*. pp. 1049–1054. [arXiv](./ArXiv_(identifier)):[2004.03640](https://arxiv.org/abs/2004.03640). [doi](./Doi_(identifier)):[10.23919/DATE48585.2020.9116317](https://doi.org/10.23919%2FDATE48585.2020.9116317). [ISBN](./ISBN_(identifier)) [978-3-9819263-4-7](./Special:BookSources/978-3-9819263-4-7). [S2CID](./S2CID_(identifier)) [210928161](https://api.semanticscholar.org/CorpusID:210928161). [Archived](https://web.archive.org/web/20220118182342/https://ieeexplore.ieee.org/abstract/document/9116317?casa_token=5I_Tmgrrbu4AAAAA:v7pDHPEWlRuo2Vk3pU06194PO0-W21UOdyZqADrZxrRdPBZDMLwQrjJSAHUhHtzJmLu_VdgW) from the original on 18 January 2022. Retrieved 17 January 2022.
197. [↑](./Machine_learning#cite_ref-197) Louis, Marcia Sahaya; Azad, Zahra; Delshadtehrani, Leila; Gupta, Suyog; Warden, Pete; Reddi, Vijay Janapa; Joshi, Ajay (2019). ["Towards Deep Learning using TensorFlow Lite on RISC-V"](https://edge.seas.harvard.edu/publications/towards-deep-learning-using-tensorflow-lite-risc-v). *[Harvard University](./Harvard_University)*. [Archived](https://web.archive.org/web/20220117031909/https://edge.seas.harvard.edu/publications/towards-deep-learning-using-tensorflow-lite-risc-v) from the original on 17 January 2022. Retrieved 17 January 2022.
198. [↑](./Machine_learning#cite_ref-198) Ibrahim, Ali; Osta, Mario; Alameh, Mohamad; Saleh, Moustafa; Chible, Hussein; Valle, Maurizio (21 January 2019). "Approximate Computing Methods for Embedded Machine Learning". *2018 25th IEEE International Conference on Electronics, Circuits and Systems (ICECS)*. pp. 845–848. [doi](./Doi_(identifier)):[10.1109/ICECS.2018.8617877](https://doi.org/10.1109%2FICECS.2018.8617877). [ISBN](./ISBN_(identifier)) [978-1-5386-9562-3](./Special:BookSources/978-1-5386-9562-3). [S2CID](./S2CID_(identifier)) [58670712](https://api.semanticscholar.org/CorpusID:58670712).
199. [↑](./Machine_learning#cite_ref-199) ["dblp: TensorFlow Eager: A Multi-Stage, Python-Embedded DSL for Machine Learning"](https://dblp.org/rec/journals/corr/abs-1903-01855.html). *dblp.org*. [Archived](https://web.archive.org/web/20220118182335/https://dblp.org/rec/journals/corr/abs-1903-01855.html) from the original on 18 January 2022. Retrieved 17 January 2022.
200. [↑](./Machine_learning#cite_ref-200) Branco, Sérgio; Ferreira, André G.; Cabral, Jorge (5 November 2019). ["Machine Learning in Resource-Scarce Embedded Systems, FPGAs, and End-Devices: A Survey"](https://doi.org/10.3390%2Felectronics8111289). *Electronics*. **8** (11): 1289. [doi](./Doi_(identifier)):[10.3390/electronics8111289](https://doi.org/10.3390%2Felectronics8111289). [hdl](./Hdl_(identifier)):[1822/62521](https://hdl.handle.net/1822%2F62521). [ISSN](./ISSN_(identifier)) [2079-9292](https://search.worldcat.org/issn/2079-9292).

 

## Sources

 
- [Domingos, Pedro](./Pedro_Domingos) (22 September 2015). *The Master Algorithm: How the Quest for the Ultimate Learning Machine Will Remake Our World*. Basic Books. [ISBN](./ISBN_(identifier)) [978-0-465-06570-7](./Special:BookSources/978-0-465-06570-7).
- [Nilsson, Nils](./Nils_Nilsson_(researcher)) (1998). [*Artificial Intelligence: A New Synthesis*](https://archive.org/details/artificialintell0000nils). Morgan Kaufmann. [ISBN](./ISBN_(identifier)) [978-1-55860-467-4](./Special:BookSources/978-1-55860-467-4). [Archived](https://web.archive.org/web/20200726131654/https://archive.org/details/artificialintell0000nils) from the original on 26 July 2020. Retrieved 18 November 2019.
- Poole, David; [Mackworth, Alan](./Alan_Mackworth); Goebel, Randy (1998). [*Computational Intelligence: A Logical Approach*](https://archive.org/details/computationalint00pool). New York: Oxford University Press. [ISBN](./ISBN_(identifier)) [978-0-19-510270-3](./Special:BookSources/978-0-19-510270-3). [Archived](https://web.archive.org/web/20200726131436/https://archive.org/details/computationalint00pool) from the original on 26 July 2020. Retrieved 22 August 2020.
- [Russell, Stuart J.](./Stuart_J._Russell); [Norvig, Peter](./Peter_Norvig) (2003), [*Artificial Intelligence: A Modern Approach*](http://aima.cs.berkeley.edu/) (2nd ed.), Upper Saddle River, New Jersey: Prentice Hall, [ISBN](./ISBN_(identifier)) [0-13-790395-2](./Special:BookSources/0-13-790395-2).

 

## Further reading

  
- Alpaydin, Ethem (2020). *Introduction to Machine Learning*, (4th edition) MIT Press, [ISBN](./ISBN_(identifier)) [9780262043793](./Special:BookSources/9780262043793).
- [Bishop, Christopher](./Christopher_Bishop) (1995). *Neural Networks for Pattern Recognition*, Oxford University Press. [ISBN](./ISBN_(identifier)) [0-19-853864-2](./Special:BookSources/0-19-853864-2).
- Bishop, Christopher (2006) *Pattern Recognition and Machine Learning*, Springer. [ISBN](./ISBN_(identifier)) [978-0-387-31073-2](./Special:BookSources/978-0-387-31073-2)
- [Domingos, Pedro](./Pedro_Domingos) (September 2015), *[The Master Algorithm](./The_Master_Algorithm)*, Basic Books, [ISBN](./ISBN_(identifier)) [978-0-465-06570-7](./Special:BookSources/978-0-465-06570-7)
- [Duda, Richard O.](./Richard_O._Duda); [Hart, Peter E.](./Peter_E._Hart); Stork, David G. (2001) *Pattern classification* (2nd edition), Wiley, New York, [ISBN](./ISBN_(identifier)) [0-471-05669-3](./Special:BookSources/0-471-05669-3).
- [Hastie, Trevor](./Trevor_Hastie); [Tibshirani, Robert](./Robert_Tibshirani) & [Friedman, Jerome H.](./Jerome_H._Friedman) (2009) *The Elements of Statistical Learning*, Springer. [doi](./Doi_(identifier)):[10.1007/978-0-387-84858-7](https://doi.org/10.1007%2F978-0-387-84858-7) [ISBN](./ISBN_(identifier)) [0-387-95284-5](./Special:BookSources/0-387-95284-5).
- [MacKay, David J. C.](./David_J._C._MacKay) *Information Theory, Inference, and Learning Algorithms* Cambridge: Cambridge University Press, 2003. [ISBN](./ISBN_(identifier)) [0-521-64298-1](./Special:BookSources/0-521-64298-1)
- Murphy, Kevin P. (2022). [*Probabilistic Machine Learning: An Introduction*](https://probml.github.io/pml-book/book1.html). MIT Press. [ISBN](./ISBN_(identifier)) [978-0-262-04682-4](./Special:BookSources/978-0-262-04682-4).
- Nilsson, Nils J. (2015) *[Introduction to Machine Learning](https://ai.stanford.edu/people/nilsson/mlbook.html) [Archived](https://web.archive.org/web/20190816182600/http://ai.stanford.edu/people/nilsson/mlbook.html) 16 August 2019 at the [Wayback Machine](./Wayback_Machine)*.
- Russell, Stuart &  Norvig, Peter (2020). *Artificial Intelligence – A Modern Approach*. (4th edition) Pearson, [ISBN](./ISBN_(identifier)) [978-0134610993](./Special:BookSources/978-0134610993).
- [Solomonoff, Ray](./Ray_Solomonoff), (1956) *[An Inductive Inference Machine](http://world.std.com/~rjs/indinf56.pdf) [Archived](https://web.archive.org/web/20110426161749/http://world.std.com/~rjs/indinf56.pdf) 26 April 2011 at the [Wayback Machine](./Wayback_Machine)* A privately circulated report from the 1956 [Dartmouth Summer Research Conference on AI](./Dartmouth_workshop).
- Witten, Ian H.; Frank, Eibe; Hall, Mark A. (2011). *Data Mining: Practical Machine Learning Tools and Techniques*. [doi](./Doi_(identifier)):[10.1016/C2009-0-19715-5](https://doi.org/10.1016%2FC2009-0-19715-5). [ISBN](./ISBN_(identifier)) [978-0-12-374856-0](./Special:BookSources/978-0-12-374856-0).

  

## External links

 
- [International Machine Learning Society](https://web.archive.org/web/20171230081341/http://machinelearning.org/)
- [MLOSS page at JMLR](https://www.jmlr.org/mloss/) - an academic database of open-source machine learning software.

 
| vteArtificial intelligence(AI) |
| --- |
| HistorytimelineGlossaryCompaniesProjectsList of open-source AI software |
| Concepts | Automated reasoningParameterHyperparameterLoss functionsRegressionBias–variance tradeoffDouble descentOverfittingClusteringGradient descentSGDQuasi-Newton methodConjugate gradient methodBackpropagationAttentionConvolutionNormalizationBatchnormActivationSoftmaxSigmoidRectifierGatingWeight initializationRegularizationDatasetsAugmentationPrompt engineeringReinforcement learningQ-learningSARSAImitationPolicy gradientDiffusionLatent diffusion modelAutoregressionAdversaryRAGUncanny valleyRLHFSelf-supervised learningReflectionRecursive self-improvementHallucinationWord embeddingVibe codingSymbolic AINeuro-symbolic AI |
| Applications | Automated theorem provingMachine learningIn-context learningArtificial neural networkDeep learningLanguage modelLargeNMTReasoningModel Context ProtocolIntelligent agentAI agentArtificial human companionHumanity's Last ExamLethal autonomous weapons (LAWs)Generative AIWeak AIHypotheticalArtificial general intelligence (AGI)Artificial superintelligence (ASI)Agent2Agent protocol |
| Implementations | Audio–visualAlexNetWaveNetHuman image synthesisHWROCRComputer visionSpeech synthesis15.aiElevenLabsSpeech recognitionWhisperFacial recognitionAlphaFoldText-to-image modelsAuroraDALL-EFireflyFluxGPT ImageIdeogramImagenMidjourneyRecraftStable DiffusionText-to-video modelsDream MachineRunway GenHailuo AIKlingSoraSeedanceVeoMusic generationRiffusionSunoUdioWorld modelsGenieOasisTextList of large language modelsProject DebaterIBM WatsonIBM WatsonxDecisionalAlphaGoAlphaZeroOpenAI FiveSelf-driving carMuZeroAction selectionAutoGPTRobot controlReasoning systemsDeductive classifiersExpert systemsInference enginesKnowledge-based systemsLogic programsProcedural reasoning systemsSemantic reasonersRule-based systemsCognitive architecturesACT-RSoarCLARIONLIDAOpenCogKnowledge basesConceptNetWikidataDBpediaYAGO | Audio–visual | AlexNetWaveNetHuman image synthesisHWROCRComputer visionSpeech synthesis15.aiElevenLabsSpeech recognitionWhisperFacial recognitionAlphaFoldText-to-image modelsAuroraDALL-EFireflyFluxGPT ImageIdeogramImagenMidjourneyRecraftStable DiffusionText-to-video modelsDream MachineRunway GenHailuo AIKlingSoraSeedanceVeoMusic generationRiffusionSunoUdioWorld modelsGenieOasis | Text | List of large language modelsProject DebaterIBM WatsonIBM Watsonx | Decisional | AlphaGoAlphaZeroOpenAI FiveSelf-driving carMuZeroAction selectionAutoGPTRobot control | Reasoning systems | Deductive classifiersExpert systemsInference enginesKnowledge-based systemsLogic programsProcedural reasoning systemsSemantic reasonersRule-based systems | Cognitive architectures | ACT-RSoarCLARIONLIDAOpenCog | Knowledge bases | ConceptNetWikidataDBpediaYAGO |
| Audio–visual | AlexNetWaveNetHuman image synthesisHWROCRComputer visionSpeech synthesis15.aiElevenLabsSpeech recognitionWhisperFacial recognitionAlphaFoldText-to-image modelsAuroraDALL-EFireflyFluxGPT ImageIdeogramImagenMidjourneyRecraftStable DiffusionText-to-video modelsDream MachineRunway GenHailuo AIKlingSoraSeedanceVeoMusic generationRiffusionSunoUdioWorld modelsGenieOasis |
| Text | List of large language modelsProject DebaterIBM WatsonIBM Watsonx |
| Decisional | AlphaGoAlphaZeroOpenAI FiveSelf-driving carMuZeroAction selectionAutoGPTRobot control |
| Reasoning systems | Deductive classifiersExpert systemsInference enginesKnowledge-based systemsLogic programsProcedural reasoning systemsSemantic reasonersRule-based systems |
| Cognitive architectures | ACT-RSoarCLARIONLIDAOpenCog |
| Knowledge bases | ConceptNetWikidataDBpediaYAGO |
| People | Alan TuringWarren Sturgis McCullochWalter PittsJohn von NeumannChristopher D. ManningClaude ShannonShun'ichi AmariKunihiko FukushimaTakeo KanadeMarvin MinskyJohn McCarthyNathaniel RochesterAllen NewellCliff ShawHerbert A. SimonOliver SelfridgeFrank RosenblattBernard WidrowJoseph WeizenbaumSeymour PapertSeppo LinnainmaaPaul WerbosGeoffrey HintonJohn HopfieldJürgen SchmidhuberYann LeCunYoshua BengioLotfi A. ZadehStephen GrossbergAlex GravesJames GoodnightAndrew NgFei-Fei LiAlex KrizhevskyIlya SutskeverOriol VinyalsQuoc V. LeIan GoodfellowDemis HassabisDavid SilverAndrej KarpathyAshish VaswaniNoam ShazeerAidan GomezJohn SchulmanMustafa SuleymanJan LeikeDaniel KokotajloFrançois Chollet |
| Neural network architectures | Neural Turing machineDifferentiable neural computerTransformerVision transformer (ViT)Recurrent neural network (RNN)Long short-term memory (LSTM)Gated recurrent unit (GRU)Echo state networkMultilayer perceptron (MLP)Convolutional neural network (CNN)Residual neural network (RNN)Highway networkMambaAutoencoderVariational autoencoder (VAE)Generative adversarial network (GAN)Graph neural network (GNN) |
| Political | AI Cold WarAI safety(Alignment)AI takeoverElectionsEthics of AIEUAI ActNationalismPrecautionary principleRegulation of AIUSVirtual politicianPropaganda |
| Social and economic | AI boomAI bubbleAI data centerAI effectAI literacyAI slopAI veganismAI winterAnthropomorphismArms raceCompetitionEnvironmental impactExplainable AIGenerative engine optimizationIn architectureIn educationIn fictionIn healthcareChatbot psychosisIn marketingIn video gamesIn visual artMilitary applicationsAI warfareWorkplace impact |
| Category |

 
| vteComputer science |
| --- |
| This template follows roughly the 2012ACM Computing Classification System |
| Hardware | Printed circuit boardPeripheralIntegrated circuitVery-large-scale integrationSystem on a chip(SoC)Energy consumption(green computing)Electronic design automationHardware accelerationProcessorSize–Form |
| Systemsorganization | Computer architectureComputational complexityDependabilityEmbedded systemReal-time computingCyber-physical systemFault toleranceWireless sensor network |
| Networks | Network architectureNetwork protocolNetwork componentsNetwork schedulerNetwork performance evaluationNetwork service |
| Softwareorganization | InterpreterMiddlewareVirtual machineOperating systemSoftware quality |
| Softwarenotations,tools | Programming paradigmProgramming languageCompilerDomain-specific languageModeling languageSoftware frameworkIntegrated development environmentSoftware configuration managementSoftware librarySoftware repository |
| Softwaredevelopment | Control flowSoftware development processRequirements analysisSoftware designSoftware constructionSoftware deploymentSoftware engineeringSoftware maintenanceProgramming teamOpen sourcemodel |
| Theory ofcomputing | Model of computationStochasticFormal languageAutomata theoryComputability theoryComputational complexity theoryLogicSemantics |
| Algorithms | Algorithm designAnalysis of algorithmsAlgorithmic efficiencyRandomized algorithmComputational geometry |
| Mathematicsofcomputing | Discrete mathematicsProbabilityStatisticsMathematical softwareInformation theoryMathematical analysisNumerical analysisTheoretical computer scienceComputational problem |
| Informationsystems | DatabasemanagementInformation storageEnterprise informationSocial informationGeographic informationDecision supportProcess controlMultimedia informationData miningDigital libraryComputing platformDigital marketingWorld Wide WebInformation retrieval |
| Security | CryptographyFormal methodsSecurity hackerSecurityservicesIntrusion detection systemHardware securityNetwork securityInformation securityApplication security |
| Human-centeredcomputing | AccessibilityExtended realityaugmentedvirtualHuman–computer interactionInteraction designMobile computingSocial computingUbiquitous computingVisualization |
| Concurrency | Concurrent computingParallel computingDistributed computingMultithreadingMultiprocessing |
| Artificialintelligence | Computational intelligenceNatural language processingKnowledge representation and reasoningComputer visionAutomated planning and schedulingSearch methodologyControl methodPhilosophy ofDistributedMachinelearningSupervisedUnsupervisedReinforcementMulti-taskCross-validation | Computational intelligenceNatural language processingKnowledge representation and reasoningComputer visionAutomated planning and schedulingSearch methodologyControl methodPhilosophy ofDistributed | Machinelearning | SupervisedUnsupervisedReinforcementMulti-taskCross-validation |
| Computational intelligenceNatural language processingKnowledge representation and reasoningComputer visionAutomated planning and schedulingSearch methodologyControl methodPhilosophy ofDistributed |
| Machinelearning | SupervisedUnsupervisedReinforcementMulti-taskCross-validation |
| Graphics | AnimationRenderingPhotograph manipulationGraphics processing unitImage compressionSolid modeling |
| Appliedcomputing | Quantum computingE-commerceEnterprise softwareComputational mathematicsComputational physicsComputational chemistryComputational biologyComputational social scienceComputational engineeringDifferentiable computingComputational healthcareDigital artElectronic publishingCyberwarfareElectronic votingVideo gamesWord processingOperations researchEducational technologyDocument management |
| OutlineGlossariesCategory |

 [Portals](./Wikipedia:Contents/Portals):
- [![icon](//upload.wikimedia.org/wikipedia/commons/thumb/6/6f/Octicons-terminal.svg/20px-Octicons-terminal.svg.png)](./File:Octicons-terminal.svg) [Computer programming](./Portal:Computer_programming)
- [![icon](//upload.wikimedia.org/wikipedia/commons/thumb/3/3e/Nuvola_apps_edu_mathematics_blue-p.svg/20px-Nuvola_apps_edu_mathematics_blue-p.svg.png)](./File:Nuvola_apps_edu_mathematics_blue-p.svg) [Mathematics](./Portal:Mathematics)
- ![diagram](//upload.wikimedia.org/wikipedia/commons/thumb/0/00/Complex-adaptive-system.jpg/40px-Complex-adaptive-system.jpg) [Systems science](./Portal:Systems_science)
- [![icon](//upload.wikimedia.org/wikipedia/commons/thumb/a/a9/Noun-technology.svg/20px-Noun-technology.svg.png)](./File:Noun-technology.svg) [Technology](./Portal:Technology)

**Machine learning** at Wikipedia's [sister projects](./Wikipedia:Wikimedia_sister_projects):
- [![Wiktionary logo](//upload.wikimedia.org/wikipedia/commons/thumb/9/99/Wiktionary-logo-en-v2.svg/20px-Wiktionary-logo-en-v2.svg.png)](./File:Wiktionary-logo-en-v2.svg)[**Definitions**](https://en.wiktionary.org/wiki/machine%20learning) from Wiktionary
- [![Wikimedia Commons logo](//upload.wikimedia.org/wikipedia/en/thumb/4/4a/Commons-logo.svg/20px-Commons-logo.svg.png)](./File:Commons-logo.svg)[**Media**](https://commons.wikimedia.org/wiki/Category:Machine%20learning) from Commons
- ![](//upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Wikiquote-logo.svg/20px-Wikiquote-logo.svg.png)[**Quotations**](https://en.wikiquote.org/wiki/Machine%20learning) from Wikiquote
- [![Wikibooks logo](//upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Wikibooks-logo.svg/20px-Wikibooks-logo.svg.png)](./File:Wikibooks-logo.svg)[**Textbooks**](https://en.wikibooks.org/wiki/Special:Search/Machine%20learning) from Wikibooks
- [![Wikiversity logo](//upload.wikimedia.org/wikipedia/commons/thumb/0/0b/Wikiversity_logo_2017.svg/40px-Wikiversity_logo_2017.svg.png)](./File:Wikiversity_logo_2017.svg)[**Resources**](https://en.wikiversity.org/wiki/Machine%20learning) from Wikiversity
- ![](//upload.wikimedia.org/wikipedia/commons/thumb/f/ff/Wikidata-logo.svg/40px-Wikidata-logo.svg.png)[**Data**](https://www.wikidata.org/wiki/Q2539) from Wikidata

 
| Authority control databases |
| --- |
| International | GNDFAST |
| National | United StatesFranceBnF dataJapanCzech RepublicSpainIsrael |
| Other | Yale LUX |