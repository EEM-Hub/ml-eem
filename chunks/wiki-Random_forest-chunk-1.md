---
source: sources/wiki-Random_forest.md
source_url: https://en.wikipedia.org/wiki/Random_forest
chunk: 1/6
---

This article is about the machine learning technique. For other kinds of random tree, see [Random tree](./Random_tree). Tree-based ensemble machine learning methods 
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

 

**Random forests** or **random decision forests** is an [ensemble learning](./Ensemble_learning) method for [classification](./Statistical_classification), [regression](./Regression_analysis) and other tasks that works by creating a multitude of [decision trees](./Decision_tree_learning) during training. For classification tasks, the output of the random forest is the class selected by most trees. For regression tasks, the output is the average of the predictions of the trees.[[1]](./Random_forest#cite_note-ho1995-1)[[2]](./Random_forest#cite_note-ho1998-2) Random forests correct for decision trees' habit of [overfitting](./Overfitting) to their [training set](./Test_set).[[3]](./Random_forest#cite_note-elemstatlearn-3): 587–588 

 

The first algorithm for random decision forests was created in 1995 by [Tin Kam Ho](./Tin_Kam_Ho)[[1]](./Random_forest#cite_note-ho1995-1) using the [random subspace method](./Random_subspace_method),[[2]](./Random_forest#cite_note-ho1998-2) which, in Ho's formulation, is a way to implement the "stochastic discrimination" approach to classification proposed by Eugene Kleinberg.[[4]](./Random_forest#cite_note-kleinberg1990-4)[[5]](./Random_forest#cite_note-kleinberg1996-5)[[6]](./Random_forest#cite_note-kleinberg2000-6)

 

An extension of the algorithm was developed by [Leo Breiman](./Leo_Breiman)[[7]](./Random_forest#cite_note-breiman2001-7) and [Adele Cutler](./Adele_Cutler),[[8]](./Random_forest#cite_note-rpackage-8) who registered[[9]](./Random_forest#cite_note-9) "Random Forests" as a [trademark](./Trademark) in 2006 (as of 2019[[update]](https://en.wikipedia.org/w/index.php?title=Random_forest&action=edit), owned by [Minitab, Inc.](./Minitab)).[[10]](./Random_forest#cite_note-10) The extension combines Breiman's "[bagging](./Bootstrap_aggregating)" idea and random selection of features, introduced first by Ho[[1]](./Random_forest#cite_note-ho1995-1) and later independently by Amit and [Geman](./Donald_Geman)[[11]](./Random_forest#cite_note-amitgeman1997-11) in order to construct a collection of decision trees with controlled variance.

 

## History

 

The general method of random decision forests was first proposed by Salzberg and Heath in 1993,[[12]](./Random_forest#cite_note-12) with a method that used a randomized decision tree algorithm to create multiple trees and then combine them using majority voting.  This idea was developed further by Ho in 1995.[[1]](./Random_forest#cite_note-ho1995-1)  Ho established that forests of trees splitting with oblique hyperplanes can gain accuracy as they grow without suffering from overtraining, as long as the forests are randomly restricted to be sensitive to only selected [feature](./Feature_(machine_learning)) dimensions.  A subsequent work along the same lines[[2]](./Random_forest#cite_note-ho1998-2) concluded that other splitting methods behave similarly, as long as they are randomly forced to be insensitive to some feature dimensions.  This observation that a more complex classifier (a larger forest) gets more accurate nearly monotonically is in sharp contrast to the common belief that the complexity of a classifier can only grow to a certain level of accuracy before being hurt by overfitting.  The explanation of the forest method's resistance to overtraining can be found in Kleinberg's theory of stochastic discrimination.[[4]](./Random_forest#cite_note-kleinberg1990-4)[[5]](./Random_forest#cite_note-kleinberg1996-5)[[6]](./Random_forest#cite_note-kleinberg2000-6)

 

The early development of Breiman's notion of random forests was influenced by the work of Amit and Geman[[11]](./Random_forest#cite_note-amitgeman1997-11) who introduced the idea of searching over a random subset of the available decisions when splitting a node, in the context of growing a single [tree](./Decision_tree).  The idea of random subspace selection from Ho[[2]](./Random_forest#cite_note-ho1998-2) was also influential in the design of random forests.  This method grows a forest of trees, and introduces variation among the trees by projecting the training data into a randomly chosen [subspace](./Linear_subspace) before fitting each tree or each node.  Finally, the idea of randomized node optimization, where the decision at each node is selected by a randomized procedure, rather than a deterministic optimization was first introduced by [Thomas G. Dietterich](./Thomas_G._Dietterich).[[13]](./Random_forest#cite_note-13)

 

The proper introduction of random forests was made in a paper by [Leo Breiman](./Leo_Breiman),[[7]](./Random_forest#cite_note-breiman2001-7)
that has become one of the world's most cited papers.[[14]](./Random_forest#cite_note-14)
This paper describes a method of building a forest of uncorrelated trees using a [CART](./Classification_and_regression_tree)-like procedure, combined with randomized node optimization and [bagging](./Bootstrap_aggregating).  In addition, this paper combines several ingredients, some previously known and some novel, which form the basis of the modern practice of random forests, in particular:

 
1. Using [out-of-bag error](./Out-of-bag_error) as an estimate of the [generalization error](./Generalization_error).
2. Measuring variable importance through permutation.

 

The report also offers the first theoretical result for random forests in the form of a bound on the [generalization error](./Generalization_error) which depends on the strength of the trees in the forest and their [correlation](./Correlation).

 

## Algorithm

 

### Preliminaries: decision tree learning

 Main article: [Decision tree learning](./Decision_tree_learning) 

Decision trees are a popular method for various machine learning tasks. Tree learning is almost "an off-the-shelf procedure for data mining", say [Hastie](./Trevor_Hastie) *et al.*, "because it is invariant under scaling and various other transformations of feature values, is robust to inclusion of irrelevant features, and produces inspectable models. However, they are seldom accurate".[[3]](./Random_forest#cite_note-elemstatlearn-3): 352 

 

In particular, trees that are grown very deep tend to learn highly irregular patterns: they [overfit](./Overfitting) their training sets, i.e. have [low bias, but very high variance](./Bias–variance_tradeoff). Random forests are a way of averaging multiple deep decision trees, trained on different parts of the same training set, with the goal of reducing the variance.[[3]](./Random_forest#cite_note-elemstatlearn-3): 587–588  This comes at the expense of a small increase in the bias and some loss of interpretability, but generally greatly boosts the performance in the final model.

 

### Bagging

 Main article: [Bootstrap aggregating](./Bootstrap_aggregating) [![](//upload.wikimedia.org/wikipedia/commons/thumb/e/e3/Random_Forest_Bagging_Illustration.png/250px-Random_Forest_Bagging_Illustration.png)](./File:Random_Forest_Bagging_Illustration.png)Illustration of training a Random Forest model. The training dataset (in this case, of 250 rows and 100 columns) is randomly sampled with replacement *n* times. Then, a decision tree is trained on each sample. Finally, for prediction, the results of all *n* trees are aggregated to produce a final decision. 

The training algorithm for random forests applies the general technique of [bootstrap aggregating](./Bootstrap_aggregating), or bagging, to tree learners. Given a training set X = x1, ..., xn with responses Y = y1, ..., yn, bagging repeatedly (*B* times) selects a [random sample with replacement](./Sampling_(statistics)#Replacement_of_selected_units) of the training set and fits trees to these samples:

 For b = 1, ..., B:

1. Sample, with replacement, n training examples from X, Y; call these Xb, Yb.
2. Train a classification or regression tree fb on Xb, Yb.

 

After training, predictions for unseen samples x' can be made by averaging the predictions from all the individual regression trees on x':

 

       f ^ ^     =   1 B    ∑ ∑   b = 1   B    f  b   (  x ′  )   {\displaystyle {\hat {f}}={\frac {1}{B}}\sum _{b=1}^{B}f_{b}(x')}  ![{\displaystyle {\hat {f}}={\frac {1}{B}}\sum _{b=1}^{B}f_{b}(x')}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b54befce12aefdb29442bfc71cb5ad452364e8d8)

 

or by taking the plurality vote in the case of classification trees.

 

This bootstrapping procedure leads to better model performance because it decreases the [variance](./Bias–variance_dilemma) of the model, without increasing the bias. This means that while the predictions of a single tree are highly sensitive to noise in its training set, the average of many trees is not, as long as the trees are not correlated. Simply training many trees on a single training set would give strongly correlated trees (or even the same tree many times, if the training algorithm is deterministic); bootstrap sampling is a way of de-correlating the trees by showing them different training sets.

 

Additionally, an estimate of the uncertainty of the prediction can be made as the standard deviation of the predictions from all the individual regression trees on x′:
    σ σ  =      ∑ ∑   b = 1   B   (  f  b   (  x ′  ) − −     f ^ ^      )  2     B − −  1     .   {\displaystyle \sigma ={\sqrt {\frac {\sum _{b=1}^{B}(f_{b}(x')-{\hat {f}})^{2}}{B-1}}}.}  ![{\displaystyle \sigma ={\sqrt {\frac {\sum _{b=1}^{B}(f_{b}(x')-{\hat {f}})^{2}}{B-1}}}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/11e64a440f8625c492d848b38785f833a5882432)

 

The number B of samples (equivalently, of trees) is a free parameter. Typically, a few hundred to several thousand trees are used, depending on the size and nature of the training set. B can be optimized using [cross-validation](./Cross-validation_(statistics)), or by observing the *[out-of-bag error](./Out-of-bag_error)*: the mean prediction error on each training sample xi, using only the trees that did not have xi in their bootstrap sample.[[15]](./Random_forest#cite_note-islr-15)

 

The training and test error tend to level off after some number of trees have been fit.

 

### From bagging to random forests

 Main article: [Random subspace method](./Random_subspace_method) 

The above procedure describes the original bagging algorithm for trees. Random forests also include another type of bagging scheme: they use a modified tree learning algorithm that selects, at each candidate split in the learning process, a [random subset of the features](./Random_subspace_method). This process is sometimes called "feature bagging". The reason for doing this is the correlation of the trees in an ordinary bootstrap sample: if one or a few [features](./Feature_(machine_learning)) are very strong predictors for the response variable (target output), these features will be selected in many of the B trees, causing them to become correlated. An analysis of how bagging and random subspace projection contribute to accuracy gains under different conditions is given by Ho.[[16]](./Random_forest#cite_note-ho2002-16)

 

Typically, for a classification problem with     p   {\displaystyle p}  ![{\displaystyle p}](https://wikimedia.org/api/rest_v1/media/math/render/svg/81eac1e205430d1f40810df36a0edffdc367af36) features,       p     {\displaystyle {\sqrt {p}}}  ![{\displaystyle {\sqrt {p}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0527785cd1ad7fa60789e172c720affdcdb28b7f) (rounded down) features are used in each split.[[3]](./Random_forest#cite_note-elemstatlearn-3): 592   For regression problems the inventors recommend     p  /  3   {\displaystyle p/3}  ![{\displaystyle p/3}](https://wikimedia.org/api/rest_v1/media/math/render/svg/052d2d7aae02a138fdc6efc668d4b281a22dca8a) (rounded down) with a minimum node size of 5 as the default.[[3]](./Random_forest#cite_note-elemstatlearn-3): 592  In practice, the best values for these parameters should be tuned on a case-to-case basis for every problem.[[3]](./Random_forest#cite_note-elemstatlearn-3): 592 

 

### ExtraTrees

 

Adding one further step of randomization yields *extremely randomized trees*, or ExtraTrees. As with ordinary random forests, they are an ensemble of individual trees, but there are two main differences: (1) each tree is trained using the whole learning sample (rather than a bootstrap sample), and (2) the top-down splitting is randomized: for each feature under consideration, a number of *random* cut-points are selected, instead of computing the locally *optimal* cut-point (based on, e.g., [information gain](./Information_gain) or the [Gini impurity](./Gini_impurity)). The values are chosen from a uniform distribution within the feature's empirical range (in the tree's training set). Then, of all the randomly chosen splits, the split that yields the highest score is chosen to split the node.

 

Similar to ordinary random forests, the number of randomly selected features to be considered at each node can be specified. Default values for this parameter are       p     {\displaystyle {\sqrt {p}}}  ![{\displaystyle {\sqrt {p}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0527785cd1ad7fa60789e172c720affdcdb28b7f) for classification and     p   {\displaystyle p}  ![{\displaystyle p}](https://wikimedia.org/api/rest_v1/media/math/render/svg/81eac1e205430d1f40810df36a0edffdc367af36) for regression, where     p   {\displaystyle p}  ![{\displaystyle p}](https://wikimedia.org/api/rest_v1/media/math/render/svg/81eac1e205430d1f40810df36a0edffdc367af36) is the number of features in the model.[[17]](./Random_forest#cite_note-17)

 

### Random forests for high-dimensional data

 

The basic random forest procedure may not work well in situations where there are a large number of features but only a small proportion of these features are informative with respect to sample classification. This can be addressed by encouraging the procedure to focus mainly on features and trees that are informative. Some methods for accomplishing this are:

 
- Prefiltering: Eliminate features that are mostly just noise.[[18]](./Random_forest#cite_note-18)[[19]](./Random_forest#cite_note-19)
- Enriched Random Forest (ERF): Use weighted random sampling instead of simple random sampling at each node of each tree, giving greater weight to features that appear to be more informative.[[20]](./Random_forest#cite_note-20)[[21]](./Random_forest#cite_note-21)[[22]](./Random_forest#cite_note-22)
- Tree-weighted random forest (TWRF): Give more weight to more accurate trees.[[23]](./Random_forest#cite_note-23)[[24]](./Random_forest#cite_note-24)

 


