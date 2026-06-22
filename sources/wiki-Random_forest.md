---
source: https://en.wikipedia.org/wiki/Random_forest
fetched: 2026-06-21
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

 

## Properties

 

### Variable importance

 

Random forests can be used to rank the importance of variables in a regression or classification problem in a natural way.  The following technique was described in Breiman's original paper[[7]](./Random_forest#cite_note-breiman2001-7) and is implemented in the [R](./R_(programming_language)) package `randomForest`.[[8]](./Random_forest#cite_note-rpackage-8)

 

#### Permutation importance

 

To measure a feature's importance in a data set        D    n   = { (  X  i   ,  Y  i   )  }  i = 1   n     {\displaystyle {\mathcal {D}}_{n}=\{(X_{i},Y_{i})\}_{i=1}^{n}}  ![{\displaystyle {\mathcal {D}}_{n}=\{(X_{i},Y_{i})\}_{i=1}^{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ee98824c21c5539b16d0c560a1445101f74898ba), first a random forest is trained on the data.  During training, the [out-of-bag error](./Out-of-bag_error) for each data point is recorded and averaged over the forest. (If bagging is not used during training, we can instead compute errors on an independent test set.)

 

After training, the values of the feature are permuted in the out-of-bag samples and the out-of-bag error is again computed on this perturbed data set. The importance for the feature is computed by averaging the difference in out-of-bag error before and after the permutation over all trees.  The score is normalized by the standard deviation of these differences.

 

Features which produce large values for this score are ranked as more important than features which produce small values. The statistical definition of the variable importance measure was given and analyzed by Zhu *et al.*[[25]](./Random_forest#cite_note-25)

 

This method of determining variable importance has some drawbacks:

 
- When features have different numbers of values, random forests favor features with more values. Solutions to this problem include [partial permutations](./Partial_permutation)[[26]](./Random_forest#cite_note-26)[[27]](./Random_forest#cite_note-27)[[28]](./Random_forest#cite_note-:02-28) and growing unbiased trees.[[29]](./Random_forest#cite_note-29)[[30]](./Random_forest#cite_note-30)
- If the data contain groups of correlated features of similar relevance, then smaller groups are favored over large groups.[[31]](./Random_forest#cite_note-31)
- If there are collinear features, the procedure may fail to identify important features. A solution is to permute groups of correlated features together.[[32]](./Random_forest#cite_note-:2-32)

 

#### Mean decrease in impurity feature importance

 

This approach to feature importance for random forests considers as important the variables which decrease a lot the impurity during splitting.[[33]](./Random_forest#cite_note-33) It is described in the book *Classification and Regression Trees* by Leo Breiman[[34]](./Random_forest#cite_note-34) and is the default implementation in [`scikit learn`](./Scikit-learn) and [R](./R_(programming_language)). The definition is:     unormalized average importance  ( x ) =   1  n  T      ∑ ∑   i = 1    n  T      ∑ ∑    node   j ∈ ∈   T  i    |   split variable  ( j ) = x    p   T  i     ( j ) Δ Δ   i   T  i     ( j ) ,   {\displaystyle {\text{unormalized average importance}}(x)={\frac {1}{n_{T}}}\sum _{i=1}^{n_{T}}\sum _{{\text{node }}j\in T_{i}|{\text{split variable}}(j)=x}p_{T_{i}}(j)\Delta i_{T_{i}}(j),}  ![{\displaystyle {\text{unormalized average importance}}(x)={\frac {1}{n_{T}}}\sum _{i=1}^{n_{T}}\sum _{{\text{node }}j\in T_{i}|{\text{split variable}}(j)=x}p_{T_{i}}(j)\Delta i_{T_{i}}(j),}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f5b9e74f891d6049b82bc70ad12aa30cfb554ce0)where 

 
-     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4) is a feature
-      n  T     {\displaystyle n_{T}}  ![{\displaystyle n_{T}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1972fb23b45426057388210f0927fb46d6ff64ca) is the number of trees in the forest
-      T  i     {\displaystyle T_{i}}  ![{\displaystyle T_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a8dd1c50cb9436474f83624c3f679ccf3eebbfef) is tree     i   {\displaystyle i}  ![{\displaystyle i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/add78d8608ad86e54951b8c8bd6c8d8416533d20)
-      p   T  i     ( j ) =    n  j   n     {\displaystyle p_{T_{i}}(j)={\frac {n_{j}}{n}}}  ![{\displaystyle p_{T_{i}}(j)={\frac {n_{j}}{n}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ca9b544909fc0fbe2a859aef500749359f53ec41) is the fraction of samples reaching node     j   {\displaystyle j}  ![{\displaystyle j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f461e54f5c093e92a55547b9764291390f0b5d0)
-     Δ Δ   i   T  i     ( j )   {\displaystyle \Delta i_{T_{i}}(j)}  ![{\displaystyle \Delta i_{T_{i}}(j)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9766461fceef705ca580069d807ece0cff9b89f5) is the change in impurity in tree     i   {\displaystyle i}  ![{\displaystyle i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/add78d8608ad86e54951b8c8bd6c8d8416533d20) at node     j   {\displaystyle j}  ![{\displaystyle j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f461e54f5c093e92a55547b9764291390f0b5d0).

 

As impurity measure for samples falling in a node e.g. the following statistics can be used:

 
- [Entropy](./Entropy_(information_theory))
- [Gini coefficient](./Gini_coefficient)
- [Mean squared error](./Mean_squared_error)

 

The normalized importance is then obtained by normalizing over all features, so that the sum of normalized feature importances is 1.

 

The `scikit learn` default implementation can report misleading feature importance:[[32]](./Random_forest#cite_note-:2-32)

 
- it favors high cardinality features
- it uses training statistics and so does not reflect a feature's usefulness for predictions on a test set[[35]](./Random_forest#cite_note-35)

 

### Relationship to nearest neighbors

 

A relationship between random forests and the [k-nearest neighbor algorithm](./K-nearest_neighbor_algorithm) (k-NN) was pointed out by Lin and Jeon in 2002.[[36]](./Random_forest#cite_note-linjeon02-36) Both can be viewed as so-called *weighted neighborhoods schemes*. These are models built from a training set     { (  x  i   ,  y  i   )  }  i = 1   n     {\displaystyle \{(x_{i},y_{i})\}_{i=1}^{n}}  ![{\displaystyle \{(x_{i},y_{i})\}_{i=1}^{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0a9e0a59cd73d8fb11a10caa787512bf93af04b4) that make predictions        y ^ ^       {\displaystyle {\hat {y}}}  ![{\displaystyle {\hat {y}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3dc8de3d8ea01304329ef9518fad7a6d196c4c01) for new points x' by looking at the "neighborhood" of the point, formalized by a weight function W:       y ^ ^     =  ∑ ∑   i = 1   n   W (  x  i   ,  x ′  )   y  i   .   {\displaystyle {\hat {y}}=\sum _{i=1}^{n}W(x_{i},x')\,y_{i}.}  ![{\displaystyle {\hat {y}}=\sum _{i=1}^{n}W(x_{i},x')\,y_{i}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f9cd87e3168f0200bd67d04530ab9124dcb8cafc)Here,     W (  x  i   ,  x ′  )   {\displaystyle W(x_{i},x')}  ![{\displaystyle W(x_{i},x')}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f87df356c5a2445516fca56d2df6eb73e64e48ce) is the non-negative weight of the i'th training point relative to the new point x' in the same tree. For any x', the weights for points      x  i     {\displaystyle x_{i}}  ![{\displaystyle x_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e87000dd6142b81d041896a30fe58f0c3acb2158) must sum to 1. Weight functions are as follows:

 
- In k-NN,     W (  x  i   ,  x ′  ) =   1 k     {\displaystyle W(x_{i},x')={\frac {1}{k}}}  ![{\displaystyle W(x_{i},x')={\frac {1}{k}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ae3098adcbde36fd1253a0ee85a3868d67b1861f) if xi is one of the k points closest to x', and zero otherwise.
- In a tree,     W (  x  i   ,  x ′  ) =   1  k ′      {\displaystyle W(x_{i},x')={\frac {1}{k'}}}  ![{\displaystyle W(x_{i},x')={\frac {1}{k'}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d80899c24f8d4488f56290ae99cfe61558667873) if xi is one of the k' points in the same leaf as x', and zero otherwise.

 

Since a forest averages the predictions of a set of m trees with individual weight functions      W  j     {\displaystyle W_{j}}  ![{\displaystyle W_{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fa98874e6beb16373e8d0e056ba550cf653676a1), its predictions are       y ^ ^     =   1 m    ∑ ∑   j = 1   m    ∑ ∑   i = 1   n    W  j   (  x  i   ,  x ′  )   y  i   =  ∑ ∑   i = 1   n    (    1 m    ∑ ∑   j = 1   m    W  j   (  x  i   ,  x ′  )  )    y  i   .   {\displaystyle {\hat {y}}={\frac {1}{m}}\sum _{j=1}^{m}\sum _{i=1}^{n}W_{j}(x_{i},x')\,y_{i}=\sum _{i=1}^{n}\left({\frac {1}{m}}\sum _{j=1}^{m}W_{j}(x_{i},x')\right)\,y_{i}.}  ![{\displaystyle {\hat {y}}={\frac {1}{m}}\sum _{j=1}^{m}\sum _{i=1}^{n}W_{j}(x_{i},x')\,y_{i}=\sum _{i=1}^{n}\left({\frac {1}{m}}\sum _{j=1}^{m}W_{j}(x_{i},x')\right)\,y_{i}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8b819eff4f3bb5ee472825d9996c3fd5f6b18ed7)

 

This shows that the whole forest is again a weighted neighborhood scheme, with weights that average those of the individual trees. The neighbors of x' in this interpretation are the points      x  i     {\displaystyle x_{i}}  ![{\displaystyle x_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e87000dd6142b81d041896a30fe58f0c3acb2158) sharing the same leaf in any tree     j   {\displaystyle j}  ![{\displaystyle j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f461e54f5c093e92a55547b9764291390f0b5d0). In this way, the neighborhood of x' depends in a complex way on the structure of the trees, and thus on the structure of the training set. Lin and Jeon show that the shape of the neighborhood used by a random forest adapts to the local importance of each feature.[[36]](./Random_forest#cite_note-linjeon02-36)

 

## Unsupervised learning

 

As part of their construction, random forest predictors naturally lead to a dissimilarity measure among observations. One can analogously define dissimilarity between unlabeled data, by training a forest to distinguish original "observed" data from suitably generated synthetic data drawn from a reference distribution.[[7]](./Random_forest#cite_note-breiman2001-7)[[37]](./Random_forest#cite_note-37) A random forest dissimilarity is attractive because it handles mixed variable types very well, is invariant to monotonic transformations of the input variables, and is robust to outlying observations. Random forest dissimilarity easily deals with a large number of semi-continuous variables due to its intrinsic variable selection; for example, the "Addcl 1" random forest dissimilarity weighs the contribution of each variable according to how dependent it is on other variables. Random forest dissimilarity has been used in a variety of applications, e.g. to find clusters of patients based on tissue marker data.[[38]](./Random_forest#cite_note-38)

 

## Variants

 

Instead of decision trees, linear models have been proposed and evaluated as base estimators in random forests, in particular [multinomial logistic regression](./Multinomial_logistic_regression) and [naive Bayes classifiers](./Naive_Bayes_classifier).[[39]](./Random_forest#cite_note-:0-39)[[40]](./Random_forest#cite_note-40)[[41]](./Random_forest#cite_note-41) In cases that the relationship between the predictors and the target variable is linear, the base learners may have an equally high accuracy as the ensemble learner.[[42]](./Random_forest#cite_note-:1-42)[[39]](./Random_forest#cite_note-:0-39)

 

## Kernel random forest

 

In machine learning, kernel random forests (KeRF) establish the connection between random forests and [kernel methods](./Kernel_method). By slightly modifying their definition, random forests can be rewritten as [kernel methods](./Kernel_method), which are more interpretable and easier to analyze.[[43]](./Random_forest#cite_note-scornet2015random-43)

 

### History

 

[Leo Breiman](./Leo_Breiman)[[44]](./Random_forest#cite_note-breiman2000some-44) was the first person to notice the link between random forest and [kernel methods](./Kernel_methods). He pointed out that random forests trained using [i.i.d.](./I.i.d.) random vectors in the tree construction are equivalent to a kernel acting on the true margin. Lin and Jeon[[45]](./Random_forest#cite_note-lin2006random-45) established the connection between random forests and adaptive nearest neighbor, implying that random forests can be seen as adaptive kernel estimates. Davies and Ghahramani[[46]](./Random_forest#cite_note-davies2014random-46) proposed Kernel Random Forest (KeRF) and showed that it can empirically outperform state-of-art kernel methods. Scornet[[43]](./Random_forest#cite_note-scornet2015random-43) first defined KeRF estimates and gave the explicit link between KeRF estimates and random forest. He also gave explicit expressions for kernels based on centered random forest[[47]](./Random_forest#cite_note-breiman2004consistency-47) and uniform random forest,[[48]](./Random_forest#cite_note-arlot2014analysis-48) two simplified models of random forest. He named these two KeRFs Centered KeRF and Uniform KeRF, and proved upper bounds on their rates of consistency.

 

### Notations and definitions

 

#### Preliminaries: Centered forests

 

Centered forest[[47]](./Random_forest#cite_note-breiman2004consistency-47) is a simplified model for Breiman's original random forest, which uniformly selects an attribute among all attributes and performs splits at the center of the cell along the pre-chosen attribute. The algorithm stops when a fully binary tree of level     k   {\displaystyle k}  ![{\displaystyle k}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c3c9a2c7b599b37105512c5d570edc034056dd40) is built, where     k ∈ ∈   N    {\displaystyle k\in \mathbb {N} }  ![{\displaystyle k\in \mathbb {N} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/2a5bc4b7383031ba693b7433198ead7170954c1d) is a parameter of the algorithm.

 

#### Uniform forest

 

Uniform forest[[48]](./Random_forest#cite_note-arlot2014analysis-48) is another simplified model for Breiman's original random forest, which uniformly selects a feature among all features and performs splits at a point uniformly drawn on the side of the cell, along the preselected feature.

 

#### From random forest to KeRF

 

Given a training sample         D    n   = { (   X   i   ,  Y  i   )  }  i = 1   n     {\displaystyle {\mathcal {D}}_{n}=\{(\mathbf {X} _{i},Y_{i})\}_{i=1}^{n}}  ![{\displaystyle {\mathcal {D}}_{n}=\{(\mathbf {X} _{i},Y_{i})\}_{i=1}^{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c67c8cf7d7485be2a566d02284d9bc27a3f61241) of     [ 0 , 1  ]  p   × ×   R    {\displaystyle [0,1]^{p}\times \mathbb {R} }  ![{\displaystyle [0,1]^{p}\times \mathbb {R} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/6724c5c806dd7cee08c1f2133fc89f94ed0c2e91)-valued independent random variables distributed as the independent prototype pair     (  X  , Y )   {\displaystyle (\mathbf {X} ,Y)}  ![{\displaystyle (\mathbf {X} ,Y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f50eb05dacdb567fc019a3bbcd44b596a1c59a13), where     E ⁡ ⁡  [  Y  2   ] < ∞ ∞    {\displaystyle \operatorname {E} [Y^{2}]<\infty }  ![{\displaystyle \operatorname {E} [Y^{2}]<\infty }](https://wikimedia.org/api/rest_v1/media/math/render/svg/07a863a618762e9fecf30fadce90c3f6484db196). We aim at predicting the response     Y   {\displaystyle Y}  ![{\displaystyle Y}](https://wikimedia.org/api/rest_v1/media/math/render/svg/961d67d6b454b4df2301ac571808a3538b3a6d3f), associated with the random variable      X    {\displaystyle \mathbf {X} }  ![{\displaystyle \mathbf {X} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/9f75966a2f9d5672136fa9401ee1e75008f95ffd), by estimating the regression function     m (  x  ) = E ⁡ ⁡  [ Y ∣ ∣   X  =  x  ]   {\displaystyle m(\mathbf {x} )=\operatorname {E} [Y\mid \mathbf {X} =\mathbf {x} ]}  ![{\displaystyle m(\mathbf {x} )=\operatorname {E} [Y\mid \mathbf {X} =\mathbf {x} ]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0c097ce105048693746d5524ac0ef9fc514da53b). A random regression forest is an ensemble of     M   {\displaystyle M}  ![{\displaystyle M}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f82cade9898ced02fdd08712e5f0c0151758a0dd) randomized regression trees. Denote      m  n   (  x  ,   Θ Θ    j   )   {\displaystyle m_{n}(\mathbf {x} ,\mathbf {\Theta } _{j})}  ![{\displaystyle m_{n}(\mathbf {x} ,\mathbf {\Theta } _{j})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/95ad3dfa3a0ed6fc135df01b527d6be634ff9d07) the predicted value at point      x    {\displaystyle \mathbf {x} }  ![{\displaystyle \mathbf {x} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/32adf004df5eb0a8c7fd8c0b6b7405183c5a5ef2) by the     j   {\displaystyle j}  ![{\displaystyle j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f461e54f5c093e92a55547b9764291390f0b5d0)-th tree, where       Θ Θ    1   , … …  ,   Θ Θ    M     {\displaystyle \mathbf {\Theta } _{1},\ldots ,\mathbf {\Theta } _{M}}  ![{\displaystyle \mathbf {\Theta } _{1},\ldots ,\mathbf {\Theta } _{M}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8588793690df49c9b10f8c44499b1ee82106867f) are independent random variables, distributed as a generic random variable      Θ Θ     {\displaystyle \mathbf {\Theta } }  ![{\displaystyle \mathbf {\Theta } }](https://wikimedia.org/api/rest_v1/media/math/render/svg/1a15b5576ec407e52c5fdfc21c5d7bf45402406a), independent of the sample        D    n     {\displaystyle {\mathcal {D}}_{n}}  ![{\displaystyle {\mathcal {D}}_{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4ba7d8da2372a68d034e848dbd973b7f173769fe). This random variable can be used to describe the randomness induced by node splitting and the sampling procedure for tree construction. The trees are combined to form the finite forest estimate      m  M , n   (  x  ,  Θ Θ   1   , … …  ,  Θ Θ   M   ) =   1 M    ∑ ∑   j = 1   M    m  n   (  x  ,  Θ Θ   j   )   {\displaystyle m_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})={\frac {1}{M}}\sum _{j=1}^{M}m_{n}(\mathbf {x} ,\Theta _{j})}  ![{\displaystyle m_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})={\frac {1}{M}}\sum _{j=1}^{M}m_{n}(\mathbf {x} ,\Theta _{j})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e1cd03b3dba46782bb60f083359fd8e77250024c).
For regression trees, we have      m  n   =  ∑ ∑   i = 1   n       Y  i     1     X   i   ∈ ∈   A  n   (  x  ,  Θ Θ   j   )      N  n   (  x  ,  Θ Θ   j   )      {\displaystyle m_{n}=\sum _{i=1}^{n}{\frac {Y_{i}\mathbf {1} _{\mathbf {X} _{i}\in A_{n}(\mathbf {x} ,\Theta _{j})}}{N_{n}(\mathbf {x} ,\Theta _{j})}}}  ![{\displaystyle m_{n}=\sum _{i=1}^{n}{\frac {Y_{i}\mathbf {1} _{\mathbf {X} _{i}\in A_{n}(\mathbf {x} ,\Theta _{j})}}{N_{n}(\mathbf {x} ,\Theta _{j})}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d1ad1f4a5e0e849bfbf10492b08e5e9b55b6c711), where      A  n   (  x  ,  Θ Θ   j   )   {\displaystyle A_{n}(\mathbf {x} ,\Theta _{j})}  ![{\displaystyle A_{n}(\mathbf {x} ,\Theta _{j})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1811d33726c0ea70d83e6f5ee5228d82e6229300) is the cell containing      x    {\displaystyle \mathbf {x} }  ![{\displaystyle \mathbf {x} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/32adf004df5eb0a8c7fd8c0b6b7405183c5a5ef2), designed with randomness      Θ Θ   j     {\displaystyle \Theta _{j}}  ![{\displaystyle \Theta _{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/10b9d5bab99a44d98171cce92f04d0e700060512) and dataset        D    n     {\displaystyle {\mathcal {D}}_{n}}  ![{\displaystyle {\mathcal {D}}_{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4ba7d8da2372a68d034e848dbd973b7f173769fe), and      N  n   (  x  ,  Θ Θ   j   ) =  ∑ ∑   i = 1   n     1     X   i   ∈ ∈   A  n   (  x  ,  Θ Θ   j   )     {\displaystyle N_{n}(\mathbf {x} ,\Theta _{j})=\sum _{i=1}^{n}\mathbf {1} _{\mathbf {X} _{i}\in A_{n}(\mathbf {x} ,\Theta _{j})}}  ![{\displaystyle N_{n}(\mathbf {x} ,\Theta _{j})=\sum _{i=1}^{n}\mathbf {1} _{\mathbf {X} _{i}\in A_{n}(\mathbf {x} ,\Theta _{j})}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2c13629db1ca0ba725280a4f2bbf7adfc5c9f8a5).

 

Thus random forest estimates satisfy, for all      x  ∈ ∈  [ 0 , 1  ]  d     {\displaystyle \mathbf {x} \in [0,1]^{d}}  ![{\displaystyle \mathbf {x} \in [0,1]^{d}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/691c9727c059400e1d15031c7e0e08fbd6774282),      m  M , n   (  x  ,  Θ Θ   1   , … …  ,  Θ Θ   M   ) =   1 M    ∑ ∑   j = 1   M    (   ∑ ∑   i = 1   n       Y  i     1     X   i   ∈ ∈   A  n   (  x  ,  Θ Θ   j   )      N  n   (  x  ,  Θ Θ   j   )     )    {\displaystyle m_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})={\frac {1}{M}}\sum _{j=1}^{M}\left(\sum _{i=1}^{n}{\frac {Y_{i}\mathbf {1} _{\mathbf {X} _{i}\in A_{n}(\mathbf {x} ,\Theta _{j})}}{N_{n}(\mathbf {x} ,\Theta _{j})}}\right)}  ![{\displaystyle m_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})={\frac {1}{M}}\sum _{j=1}^{M}\left(\sum _{i=1}^{n}{\frac {Y_{i}\mathbf {1} _{\mathbf {X} _{i}\in A_{n}(\mathbf {x} ,\Theta _{j})}}{N_{n}(\mathbf {x} ,\Theta _{j})}}\right)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/671426d343ccaba3944706fd2517e5f7035f674c). Random regression forest has two levels of averaging, first over the samples in the target cell of a tree, then over all trees. Thus the contributions of observations that are in cells with a high density of data points are smaller than that of observations which belong to less populated cells. In order to improve the random forest methods and compensate the misestimation, Scornet[[43]](./Random_forest#cite_note-scornet2015random-43) defined KeRF by
        m ~ ~      M , n   (  x  ,  Θ Θ   1   , … …  ,  Θ Θ   M   ) =   1   ∑ ∑   j = 1   M    N  n   (  x  ,  Θ Θ   j   )     ∑ ∑   j = 1   M    ∑ ∑   i = 1   n    Y  i     1     X   i   ∈ ∈   A  n   (  x  ,  Θ Θ   j   )   ,   {\displaystyle {\tilde {m}}_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})={\frac {1}{\sum _{j=1}^{M}N_{n}(\mathbf {x} ,\Theta _{j})}}\sum _{j=1}^{M}\sum _{i=1}^{n}Y_{i}\mathbf {1} _{\mathbf {X} _{i}\in A_{n}(\mathbf {x} ,\Theta _{j})},}  ![{\displaystyle {\tilde {m}}_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})={\frac {1}{\sum _{j=1}^{M}N_{n}(\mathbf {x} ,\Theta _{j})}}\sum _{j=1}^{M}\sum _{i=1}^{n}Y_{i}\mathbf {1} _{\mathbf {X} _{i}\in A_{n}(\mathbf {x} ,\Theta _{j})},}](https://wikimedia.org/api/rest_v1/media/math/render/svg/565e75beaa1dd3b92753899bfa390abba19af5fc)
which is equal to the mean of the      Y  i     {\displaystyle Y_{i}}  ![{\displaystyle Y_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d57be496fff95ee2a97ee43c7f7fe244b4dbf8ae)'s falling in the cells containing      x    {\displaystyle \mathbf {x} }  ![{\displaystyle \mathbf {x} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/32adf004df5eb0a8c7fd8c0b6b7405183c5a5ef2) in the forest. If we define the connection function of the     M   {\displaystyle M}  ![{\displaystyle M}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f82cade9898ced02fdd08712e5f0c0151758a0dd) finite forest as      K  M , n   (  x  ,  z  ) =   1 M    ∑ ∑   j = 1   M     1    z  ∈ ∈   A  n   (  x  ,  Θ Θ   j   )     {\displaystyle K_{M,n}(\mathbf {x} ,\mathbf {z} )={\frac {1}{M}}\sum _{j=1}^{M}\mathbf {1} _{\mathbf {z} \in A_{n}(\mathbf {x} ,\Theta _{j})}}  ![{\displaystyle K_{M,n}(\mathbf {x} ,\mathbf {z} )={\frac {1}{M}}\sum _{j=1}^{M}\mathbf {1} _{\mathbf {z} \in A_{n}(\mathbf {x} ,\Theta _{j})}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7723dd64358a146a8bc819a79f9c15266b4d37dc), i.e. the proportion of cells shared between      x    {\displaystyle \mathbf {x} }  ![{\displaystyle \mathbf {x} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/32adf004df5eb0a8c7fd8c0b6b7405183c5a5ef2) and      z    {\displaystyle \mathbf {z} }  ![{\displaystyle \mathbf {z} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/82eca5d0928078d5a61b9e7e98cc73db31070909), then almost surely we have         m ~ ~      M , n   (  x  ,  Θ Θ   1   , … …  ,  Θ Θ   M   ) =     ∑ ∑   i = 1   n    Y  i    K  M , n   (  x  ,   x   i   )    ∑ ∑   ℓ ℓ  = 1   n    K  M , n   (  x  ,   x   ℓ ℓ    )      {\displaystyle {\tilde {m}}_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})={\frac {\sum _{i=1}^{n}Y_{i}K_{M,n}(\mathbf {x} ,\mathbf {x} _{i})}{\sum _{\ell =1}^{n}K_{M,n}(\mathbf {x} ,\mathbf {x} _{\ell })}}}  ![{\displaystyle {\tilde {m}}_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})={\frac {\sum _{i=1}^{n}Y_{i}K_{M,n}(\mathbf {x} ,\mathbf {x} _{i})}{\sum _{\ell =1}^{n}K_{M,n}(\mathbf {x} ,\mathbf {x} _{\ell })}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7ea4edc4c4ad2b30acfe0b5898862397424612eb), which defines the KeRF.

 

#### Centered KeRF

 

The construction of Centered KeRF of level     k   {\displaystyle k}  ![{\displaystyle k}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c3c9a2c7b599b37105512c5d570edc034056dd40) is the same as for centered forest, except that predictions are made by         m ~ ~      M , n   (  x  ,  Θ Θ   1   , … …  ,  Θ Θ   M   )   {\displaystyle {\tilde {m}}_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})}  ![{\displaystyle {\tilde {m}}_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3939edfe84d8ece5969248f08b77f0b23843ad3e), the corresponding kernel function, or connection function is
     K  k   c c   (  x  ,  z  ) =  ∑ ∑    k  1   , … …  ,  k  d   ,  ∑ ∑   j = 1   d    k  j   = k      k !    k  1   ! ⋯ ⋯   k  d   !      (   1 d   )   k    ∏ ∏   j = 1   d     1   ⌈ ⌈   2   k  j      x  j   ⌉ ⌉  = ⌈ ⌈   2   k  j      z  j   ⌉ ⌉    ,    for all    x  ,  z  ∈ ∈  [ 0 , 1  ]  d   .   {\displaystyle K_{k}^{cc}(\mathbf {x} ,\mathbf {z} )=\sum _{k_{1},\ldots ,k_{d},\sum _{j=1}^{d}k_{j}=k}{\frac {k!}{k_{1}!\cdots k_{d}!}}\left({\frac {1}{d}}\right)^{k}\prod _{j=1}^{d}\mathbf {1} _{\lceil 2^{k_{j}}x_{j}\rceil =\lceil 2^{k_{j}}z_{j}\rceil },\qquad {\text{ for all }}\mathbf {x} ,\mathbf {z} \in [0,1]^{d}.}  ![{\displaystyle K_{k}^{cc}(\mathbf {x} ,\mathbf {z} )=\sum _{k_{1},\ldots ,k_{d},\sum _{j=1}^{d}k_{j}=k}{\frac {k!}{k_{1}!\cdots k_{d}!}}\left({\frac {1}{d}}\right)^{k}\prod _{j=1}^{d}\mathbf {1} _{\lceil 2^{k_{j}}x_{j}\rceil =\lceil 2^{k_{j}}z_{j}\rceil },\qquad {\text{ for all }}\mathbf {x} ,\mathbf {z} \in [0,1]^{d}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b4b7a16a2bcfb63020d9081379559d5fcd82a7a5)

 

#### Uniform KeRF

 

Uniform KeRF is built in the same way as uniform forest, except that predictions are made by         m ~ ~      M , n   (  x  ,  Θ Θ   1   , … …  ,  Θ Θ   M   )   {\displaystyle {\tilde {m}}_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})}  ![{\displaystyle {\tilde {m}}_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3939edfe84d8ece5969248f08b77f0b23843ad3e), the corresponding kernel function, or connection function is
     K  k   u f   (  0  ,  x  ) =  ∑ ∑    k  1   , … …  ,  k  d   ,  ∑ ∑   j = 1   d    k  j   = k      k !    k  1   ! … …   k  d   !      (   1 d   )   k    ∏ ∏   m = 1   d    (  1 − −   |   x  m    |   ∑ ∑   j = 0    k  m   − −  1       (  − −  ln ⁡ ⁡   |   x  m    |   )   j    j !     )    for all    x  ∈ ∈  [ 0 , 1  ]  d   .   {\displaystyle K_{k}^{uf}(\mathbf {0} ,\mathbf {x} )=\sum _{k_{1},\ldots ,k_{d},\sum _{j=1}^{d}k_{j}=k}{\frac {k!}{k_{1}!\ldots k_{d}!}}\left({\frac {1}{d}}\right)^{k}\prod _{m=1}^{d}\left(1-|x_{m}|\sum _{j=0}^{k_{m}-1}{\frac {\left(-\ln |x_{m}|\right)^{j}}{j!}}\right){\text{ for all }}\mathbf {x} \in [0,1]^{d}.}  ![{\displaystyle K_{k}^{uf}(\mathbf {0} ,\mathbf {x} )=\sum _{k_{1},\ldots ,k_{d},\sum _{j=1}^{d}k_{j}=k}{\frac {k!}{k_{1}!\ldots k_{d}!}}\left({\frac {1}{d}}\right)^{k}\prod _{m=1}^{d}\left(1-|x_{m}|\sum _{j=0}^{k_{m}-1}{\frac {\left(-\ln |x_{m}|\right)^{j}}{j!}}\right){\text{ for all }}\mathbf {x} \in [0,1]^{d}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e06f4c0b6697dda0b20263456b511570143a7785)

 

### Properties

 

#### Relation between KeRF and random forest

 

Predictions given by KeRF and random forests are close if the number of points in each cell is controlled:

  

Assume that there exist sequences     (  a  n   ) , (  b  n   )   {\displaystyle (a_{n}),(b_{n})}  ![{\displaystyle (a_{n}),(b_{n})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6d8157b9b64afbd714b16ed6b8de06c32afb696a) such that, almost surely,
     a  n   ≤ ≤   N  n   (  x  , Θ Θ  ) ≤ ≤   b  n     and    a  n   ≤ ≤    1 M    ∑ ∑   m = 1   M    N  n     x  ,  Θ Θ   m    ≤ ≤   b  n   .   {\displaystyle a_{n}\leq N_{n}(\mathbf {x} ,\Theta )\leq b_{n}{\text{ and }}a_{n}\leq {\frac {1}{M}}\sum _{m=1}^{M}N_{n}{\mathbf {x} ,\Theta _{m}}\leq b_{n}.}  ![{\displaystyle a_{n}\leq N_{n}(\mathbf {x} ,\Theta )\leq b_{n}{\text{ and }}a_{n}\leq {\frac {1}{M}}\sum _{m=1}^{M}N_{n}{\mathbf {x} ,\Theta _{m}}\leq b_{n}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/139dc876ec018ffab1c1d499f269b95a6e8c245a)
Then almost surely,
     |   m  M , n   (  x  ) − −      m ~ ~      M , n   (  x  )  |  ≤ ≤      b  n   − −   a  n     a  n         m ~ ~      M , n   (  x  ) .   {\displaystyle |m_{M,n}(\mathbf {x} )-{\tilde {m}}_{M,n}(\mathbf {x} )|\leq {\frac {b_{n}-a_{n}}{a_{n}}}{\tilde {m}}_{M,n}(\mathbf {x} ).}  ![{\displaystyle |m_{M,n}(\mathbf {x} )-{\tilde {m}}_{M,n}(\mathbf {x} )|\leq {\frac {b_{n}-a_{n}}{a_{n}}}{\tilde {m}}_{M,n}(\mathbf {x} ).}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ad592965613268c7026f8f57701caba977fd34ed)

  

#### Relation between infinite KeRF and infinite random forest

 

When the number of trees     M   {\displaystyle M}  ![{\displaystyle M}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f82cade9898ced02fdd08712e5f0c0151758a0dd) goes to infinity, then we have infinite random forest and infinite KeRF. Their estimates are close if the number of observations in each cell is bounded:

  

Assume that there exist sequences     (  ε ε   n   ) , (  a  n   ) , (  b  n   )   {\displaystyle (\varepsilon _{n}),(a_{n}),(b_{n})}  ![{\displaystyle (\varepsilon _{n}),(a_{n}),(b_{n})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/67e5f769151263bad5a8d716a2c6af2686687855) such that, almost surely

 
-     E ⁡ ⁡  [  N  n   (  x  , Θ Θ  ) ] ≥ ≥  1 ,   {\displaystyle \operatorname {E} [N_{n}(\mathbf {x} ,\Theta )]\geq 1,}  ![{\displaystyle \operatorname {E} [N_{n}(\mathbf {x} ,\Theta )]\geq 1,}](https://wikimedia.org/api/rest_v1/media/math/render/svg/07f5beb5ef7860bc9f527fb5b01fbed3dc0fc716)
-     P ⁡ ⁡  [  a  n   ≤ ≤   N  n   (  x  , Θ Θ  ) ≤ ≤   b  n   ∣ ∣     D    n   ] ≥ ≥  1 − −   ε ε   n    /  2 ,   {\displaystyle \operatorname {P} [a_{n}\leq N_{n}(\mathbf {x} ,\Theta )\leq b_{n}\mid {\mathcal {D}}_{n}]\geq 1-\varepsilon _{n}/2,}  ![{\displaystyle \operatorname {P} [a_{n}\leq N_{n}(\mathbf {x} ,\Theta )\leq b_{n}\mid {\mathcal {D}}_{n}]\geq 1-\varepsilon _{n}/2,}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4bad78155a4139322247009072e48d6b7bf8c5b9)
-     P ⁡ ⁡  [  a  n   ≤ ≤   E  Θ Θ    ⁡ ⁡  [  N  n   (  x  , Θ Θ  ) ] ≤ ≤   b  n   ∣ ∣     D    n   ] ≥ ≥  1 − −   ε ε   n    /  2 ,   {\displaystyle \operatorname {P} [a_{n}\leq \operatorname {E} _{\Theta }[N_{n}(\mathbf {x} ,\Theta )]\leq b_{n}\mid {\mathcal {D}}_{n}]\geq 1-\varepsilon _{n}/2,}  ![{\displaystyle \operatorname {P} [a_{n}\leq \operatorname {E} _{\Theta }[N_{n}(\mathbf {x} ,\Theta )]\leq b_{n}\mid {\mathcal {D}}_{n}]\geq 1-\varepsilon _{n}/2,}](https://wikimedia.org/api/rest_v1/media/math/render/svg/71711062ff59f3d2075162074e8f94f917a0cdad)

 

Then almost surely,
     |   m  ∞ ∞  , n   (  x  ) − −      m ~ ~      ∞ ∞  , n   (  x  )  |  ≤ ≤      b  n   − −   a  n     a  n         m ~ ~      ∞ ∞  , n   (  x  ) + n  ε ε   n    (   max  1 ≤ ≤  i ≤ ≤  n    Y  i    )  .   {\displaystyle |m_{\infty ,n}(\mathbf {x} )-{\tilde {m}}_{\infty ,n}(\mathbf {x} )|\leq {\frac {b_{n}-a_{n}}{a_{n}}}{\tilde {m}}_{\infty ,n}(\mathbf {x} )+n\varepsilon _{n}\left(\max _{1\leq i\leq n}Y_{i}\right).}  ![{\displaystyle |m_{\infty ,n}(\mathbf {x} )-{\tilde {m}}_{\infty ,n}(\mathbf {x} )|\leq {\frac {b_{n}-a_{n}}{a_{n}}}{\tilde {m}}_{\infty ,n}(\mathbf {x} )+n\varepsilon _{n}\left(\max _{1\leq i\leq n}Y_{i}\right).}](https://wikimedia.org/api/rest_v1/media/math/render/svg/26197c8d5ca305f9a7a922c4227c5daa11350e76)

  

### Consistency results

 

Assume that     Y = m (  X  ) + ε ε    {\displaystyle Y=m(\mathbf {X} )+\varepsilon }  ![{\displaystyle Y=m(\mathbf {X} )+\varepsilon }](https://wikimedia.org/api/rest_v1/media/math/render/svg/d8617bcdd783f680a6c45c9d8c627a5730a878e5), where     ε ε    {\displaystyle \varepsilon }  ![{\displaystyle \varepsilon }](https://wikimedia.org/api/rest_v1/media/math/render/svg/a30c89172e5b88edbd45d3e2772c7f5e562e5173) is a centered Gaussian noise, independent of      X    {\displaystyle \mathbf {X} }  ![{\displaystyle \mathbf {X} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/9f75966a2f9d5672136fa9401ee1e75008f95ffd), with finite variance      σ σ   2   < ∞ ∞    {\displaystyle \sigma ^{2}<\infty }  ![{\displaystyle \sigma ^{2}<\infty }](https://wikimedia.org/api/rest_v1/media/math/render/svg/f9c01c50d5825dbb5b11add552a422af72a9664f). Moreover,      X    {\displaystyle \mathbf {X} }  ![{\displaystyle \mathbf {X} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/9f75966a2f9d5672136fa9401ee1e75008f95ffd) is uniformly distributed on     [ 0 , 1  ]  d     {\displaystyle [0,1]^{d}}  ![{\displaystyle [0,1]^{d}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e13ae4917276744b214714a20b3cb8ee305e309d) and     m   {\displaystyle m}  ![{\displaystyle m}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0a07d98bb302f3856cbabc47b2b9016692e3f7bc) is [Lipschitz](./Lipschitz_continuity). Scornet[[43]](./Random_forest#cite_note-scornet2015random-43) proved upper bounds on the rates of consistency for centered KeRF and uniform KeRF.

 

#### Consistency of centered KeRF

 

Providing     k → →  ∞ ∞    {\displaystyle k\rightarrow \infty }  ![{\displaystyle k\rightarrow \infty }](https://wikimedia.org/api/rest_v1/media/math/render/svg/612a3ec99f1c9f12de1cfab011e306ae799858ce) and     n  /   2  k   → →  ∞ ∞    {\displaystyle n/2^{k}\rightarrow \infty }  ![{\displaystyle n/2^{k}\rightarrow \infty }](https://wikimedia.org/api/rest_v1/media/math/render/svg/9fbec163fbc2ac671e4c9f78bdc70a985599dc19), there exists a constant      C  1   > 0   {\displaystyle C_{1}>0}  ![{\displaystyle C_{1}>0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c7f2ff302742806f4db7411f29e54944b4d9bda7) such that, for all     n   {\displaystyle n}  ![{\displaystyle n}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a601995d55609f2d9f5e233e36fbe9ea26011b3b),
     E  [     m ~ ~      n   c c   (  X  ) − −  m (  X  )  ]  2   ≤ ≤   C  1    n  − −  1  /  ( 3 + d log ⁡ ⁡  2 )   ( log ⁡ ⁡  n  )  2     {\displaystyle \mathbb {E} [{\tilde {m}}_{n}^{cc}(\mathbf {X} )-m(\mathbf {X} )]^{2}\leq C_{1}n^{-1/(3+d\log 2)}(\log n)^{2}}  ![{\displaystyle \mathbb {E} [{\tilde {m}}_{n}^{cc}(\mathbf {X} )-m(\mathbf {X} )]^{2}\leq C_{1}n^{-1/(3+d\log 2)}(\log n)^{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/bbd76dd80031cfdb1b8042faeab38ecaafefa2e3).

 

#### Consistency of uniform KeRF

 

Providing     k → →  ∞ ∞    {\displaystyle k\rightarrow \infty }  ![{\displaystyle k\rightarrow \infty }](https://wikimedia.org/api/rest_v1/media/math/render/svg/612a3ec99f1c9f12de1cfab011e306ae799858ce) and     n  /   2  k   → →  ∞ ∞    {\displaystyle n/2^{k}\rightarrow \infty }  ![{\displaystyle n/2^{k}\rightarrow \infty }](https://wikimedia.org/api/rest_v1/media/math/render/svg/9fbec163fbc2ac671e4c9f78bdc70a985599dc19), there exists a constant     C > 0   {\displaystyle C>0}  ![{\displaystyle C>0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c84d4126c6df243734f9355927c026df6b0d3859) such that,
     E  [     m ~ ~      n   u f   (  X  ) − −  m (  X  )  ]  2   ≤ ≤  C  n  − −  2  /  ( 6 + 3 d log ⁡ ⁡  2 )   ( log ⁡ ⁡  n  )  2     {\displaystyle \mathbb {E} [{\tilde {m}}_{n}^{uf}(\mathbf {X} )-m(\mathbf {X} )]^{2}\leq Cn^{-2/(6+3d\log 2)}(\log n)^{2}}  ![{\displaystyle \mathbb {E} [{\tilde {m}}_{n}^{uf}(\mathbf {X} )-m(\mathbf {X} )]^{2}\leq Cn^{-2/(6+3d\log 2)}(\log n)^{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/51b3c9f4980f936fc01a73621cc56e9857059da4).

 

## Disadvantages

 

While random forests often achieve higher accuracy than a single decision tree, they sacrifice the intrinsic [interpretability](./Interpretability) of decision trees. Decision trees are among a fairly small family of machine learning models that are easily interpretable along with linear models, [rule-based](./Rule-based_machine_learning) models, and [attention](./Attention_(machine_learning))-based models. This interpretability is one of the main advantages of decision trees. It allows developers to confirm that the model has learned realistic information from the data and allows end-users to have trust and confidence in the decisions made by the model.[[39]](./Random_forest#cite_note-:0-39)[[3]](./Random_forest#cite_note-elemstatlearn-3) For example, following the path that a decision tree takes to make its decision is quite trivial, but following the paths of tens or hundreds of trees is much harder. To achieve both performance and interpretability, some model compression techniques allow transforming a random forest into a minimal "born-again" decision tree that faithfully reproduces the same decision function.[[39]](./Random_forest#cite_note-:0-39)[[49]](./Random_forest#cite_note-49)[[50]](./Random_forest#cite_note-50)

 

Another limitation of random forests is that if features are linearly correlated with the target, random forest may not enhance the accuracy of the base learner.[[39]](./Random_forest#cite_note-:0-39)[[42]](./Random_forest#cite_note-:1-42) Likewise in problems with multiple categorical variables.[[51]](./Random_forest#cite_note-:3-51)

 

## See also

 
- [Boosting](./Boosting_(machine_learning)) – Ensemble learning method
- [Decision tree learning](./Decision_tree_learning) – Machine learning algorithm
- [Ensemble learning](./Ensemble_learning) – Statistics and machine learning technique
- [Gradient boosting](./Gradient_boosting) – Machine learning technique
- [Non-parametric statistics](./Non-parametric_statistics) – Type of statistical analysisPages displaying short descriptions of redirect targets
- [Randomized algorithm](./Randomized_algorithm) – Algorithm that employs a degree of randomness as part of its logic or procedure

 

## References

 
1. [1](./Random_forest#cite_ref-ho1995_1-0) [2](./Random_forest#cite_ref-ho1995_1-1) [3](./Random_forest#cite_ref-ho1995_1-2) [4](./Random_forest#cite_ref-ho1995_1-3) Ho, Tin Kam (1995). [*Random Decision Forests*](https://web.archive.org/web/20160417030218/http://ect.bell-labs.com/who/tkh/publications/papers/odt.pdf) (PDF). Proceedings of the 3rd International Conference on Document Analysis and Recognition, Montreal, QC, 14–16 August 1995. pp. 278–282. Archived from [the original](http://ect.bell-labs.com/who/tkh/publications/papers/odt.pdf) (PDF) on 17 April 2016. Retrieved 5 June 2016.
2. [1](./Random_forest#cite_ref-ho1998_2-0) [2](./Random_forest#cite_ref-ho1998_2-1) [3](./Random_forest#cite_ref-ho1998_2-2) [4](./Random_forest#cite_ref-ho1998_2-3) Ho TK (1998). ["The Random Subspace Method for Constructing Decision Forests"](http://ect.bell-labs.com/who/tkh/publications/papers/df.pdf) (PDF). *IEEE Transactions on Pattern Analysis and Machine Intelligence*. **20** (8): 832–844. [Bibcode](./Bibcode_(identifier)):[1998ITPAM..20..832T](https://ui.adsabs.harvard.edu/abs/1998ITPAM..20..832T). [doi](./Doi_(identifier)):[10.1109/34.709601](https://doi.org/10.1109%2F34.709601). [S2CID](./S2CID_(identifier)) [206420153](https://api.semanticscholar.org/CorpusID:206420153).
3. [1](./Random_forest#cite_ref-elemstatlearn_3-0) [2](./Random_forest#cite_ref-elemstatlearn_3-1) [3](./Random_forest#cite_ref-elemstatlearn_3-2) [4](./Random_forest#cite_ref-elemstatlearn_3-3) [5](./Random_forest#cite_ref-elemstatlearn_3-4) [6](./Random_forest#cite_ref-elemstatlearn_3-5) [7](./Random_forest#cite_ref-elemstatlearn_3-6) [Hastie, Trevor](./Trevor_Hastie); [Tibshirani, Robert](./Robert_Tibshirani); [Friedman, Jerome](./Jerome_H._Friedman) (2008). [*The Elements of Statistical Learning*](http://www-stat.stanford.edu/~tibs/ElemStatLearn/) (2nd ed.). Springer. [ISBN](./ISBN_(identifier)) [0-387-95284-5](./Special:BookSources/0-387-95284-5).
4. [1](./Random_forest#cite_ref-kleinberg1990_4-0) [2](./Random_forest#cite_ref-kleinberg1990_4-1) Kleinberg E (1990). ["Stochastic Discrimination"](https://web.archive.org/web/20180118124007/https://pdfs.semanticscholar.org/faa4/c502a824a9d64bf3dc26eb90a2c32367921f.pdf) (PDF). *[Annals of Mathematics and Artificial Intelligence](./Annals_of_Mathematics_and_Artificial_Intelligence?action=edit&redlink=1)*. **1** (1–4): 207–239. [Bibcode](./Bibcode_(identifier)):[1990AnMAI...1..207K](https://ui.adsabs.harvard.edu/abs/1990AnMAI...1..207K). [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.25.6750](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.25.6750). [doi](./Doi_(identifier)):[10.1007/BF01531079](https://doi.org/10.1007%2FBF01531079). [S2CID](./S2CID_(identifier)) [206795835](https://api.semanticscholar.org/CorpusID:206795835). Archived from [the original](https://pdfs.semanticscholar.org/faa4/c502a824a9d64bf3dc26eb90a2c32367921f.pdf) (PDF) on 2018-01-18.
5. [1](./Random_forest#cite_ref-kleinberg1996_5-0) [2](./Random_forest#cite_ref-kleinberg1996_5-1) Kleinberg E (1996). ["An Overtraining-Resistant Stochastic Modeling Method for Pattern Recognition"](https://doi.org/10.1214%2Faos%2F1032181157). *[Annals of Statistics](./Annals_of_Statistics)*. **24** (6): 2319–2349. [doi](./Doi_(identifier)):[10.1214/aos/1032181157](https://doi.org/10.1214%2Faos%2F1032181157). [MR](./MR_(identifier)) [1425956](https://mathscinet.ams.org/mathscinet-getitem?mr=1425956).
6. [1](./Random_forest#cite_ref-kleinberg2000_6-0) [2](./Random_forest#cite_ref-kleinberg2000_6-1) Kleinberg E (2000). ["On the Algorithmic Implementation of Stochastic Discrimination"](https://web.archive.org/web/20180118124006/https://pdfs.semanticscholar.org/8956/845b0701ec57094c7a8b4ab1f41386899aea.pdf) (PDF). *IEEE Transactions on Pattern Analysis and Machine Intelligence*. **22** (5): 473–490. [Bibcode](./Bibcode_(identifier)):[2000ITPAM..22..473K](https://ui.adsabs.harvard.edu/abs/2000ITPAM..22..473K). [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.33.4131](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.33.4131). [doi](./Doi_(identifier)):[10.1109/34.857004](https://doi.org/10.1109%2F34.857004). [S2CID](./S2CID_(identifier)) [3563126](https://api.semanticscholar.org/CorpusID:3563126). Archived from [the original](https://pdfs.semanticscholar.org/8956/845b0701ec57094c7a8b4ab1f41386899aea.pdf) (PDF) on 2018-01-18.
7. [1](./Random_forest#cite_ref-breiman2001_7-0) [2](./Random_forest#cite_ref-breiman2001_7-1) [3](./Random_forest#cite_ref-breiman2001_7-2) [4](./Random_forest#cite_ref-breiman2001_7-3) [Breiman L](./Leo_Breiman) (2001). ["Random Forests"](https://doi.org/10.1023%2FA%3A1010933404324). *[Machine Learning](./Machine_Learning_(journal))*. **45** (1): 5–32. [Bibcode](./Bibcode_(identifier)):[2001MachL..45....5B](https://ui.adsabs.harvard.edu/abs/2001MachL..45....5B). [doi](./Doi_(identifier)):[10.1023/A:1010933404324](https://doi.org/10.1023%2FA%3A1010933404324).
8. [1](./Random_forest#cite_ref-rpackage_8-0) [2](./Random_forest#cite_ref-rpackage_8-1) Liaw A (16 October 2012). ["Documentation for R package randomForest"](https://cran.r-project.org/web/packages/randomForest/randomForest.pdf) (PDF). Retrieved 15 March 2013. 
9. [↑](./Random_forest#cite_ref-9) U.S. trademark registration number 3185828, registered 2006/12/19.
10. [↑](./Random_forest#cite_ref-10) ["RANDOM FORESTS Trademark of Health Care Productivity, Inc. - Registration Number 3185828 - Serial Number 78642027 :: Justia Trademarks"](https://trademarks.justia.com/786/42/random-78642027.html).
11. [1](./Random_forest#cite_ref-amitgeman1997_11-0) [2](./Random_forest#cite_ref-amitgeman1997_11-1) Amit Y, [Geman D](./Donald_Geman) (1997). ["Shape quantization and recognition with randomized trees"](https://web.archive.org/web/20180205094828/http://www.cis.jhu.edu/publications/papers_in_database/GEMAN/shape.pdf) (PDF). *[Neural Computation](./Neural_Computation_(journal))*. **9** (7): 1545–1588. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.57.6069](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.57.6069). [doi](./Doi_(identifier)):[10.1162/neco.1997.9.7.1545](https://doi.org/10.1162%2Fneco.1997.9.7.1545). [S2CID](./S2CID_(identifier)) [12470146](https://api.semanticscholar.org/CorpusID:12470146). Archived from [the original](http://www.cis.jhu.edu/publications/papers_in_database/GEMAN/shape.pdf) (PDF) on 2018-02-05. Retrieved 2008-04-01.
12. [↑](./Random_forest#cite_ref-12) Heath, D., Kasif, S. and Salzberg, S. (1993). *k-DT: A multi-tree learning method.* In *Proceedings of the Second Intl. Workshop on Multistrategy Learning*, pp. 138-149.
13. [↑](./Random_forest#cite_ref-13) Dietterich, Thomas (2000). ["An Experimental Comparison of Three Methods for Constructing Ensembles of Decision Trees: Bagging, Boosting, and Randomization"](https://doi.org/10.1023%2FA%3A1007607513941). *[Machine Learning](./Machine_Learning_(journal))*. **40** (2): 139–157. [doi](./Doi_(identifier)):[10.1023/A:1007607513941](https://doi.org/10.1023%2FA%3A1007607513941).
14. [↑](./Random_forest#cite_ref-14) Helen Pearson; Heidi Ledford; Matthew Hutson; Richard Van Noorden (15 April 2025). "Exclusive: the most-cited papers of the twenty-first century". *[Nature](./Nature_(journal))*. **640** (8059): 588–592. [doi](./Doi_(identifier)):[10.1038/D41586-025-01125-9](https://doi.org/10.1038%2FD41586-025-01125-9). [ISSN](./ISSN_(identifier)) [1476-4687](https://search.worldcat.org/issn/1476-4687). [Wikidata](./WDQ_(identifier)) [Q135104889](https://www.wikidata.org/wiki/Q135104889).
15. [↑](./Random_forest#cite_ref-islr_15-0) Gareth James; Daniela Witten; Trevor Hastie; Robert Tibshirani (2013). [*An Introduction to Statistical Learning*](http://www-bcf.usc.edu/~gareth/ISL/). Springer. pp. 316–321.
16. [↑](./Random_forest#cite_ref-ho2002_16-0) Ho, Tin Kam (2002). ["A Data Complexity Analysis of Comparative Advantages of Decision Forest Constructors"](https://web.archive.org/web/20160417091232/http://ect.bell-labs.com/who/tkh/publications/papers/compare.pdf) (PDF). *Pattern Analysis and Applications*. **5** (2): 102–112. [doi](./Doi_(identifier)):[10.1007/s100440200009](https://doi.org/10.1007%2Fs100440200009). [S2CID](./S2CID_(identifier)) [7415435](https://api.semanticscholar.org/CorpusID:7415435). Archived from [the original](http://ect.bell-labs.com/who/tkh/publications/papers/compare.pdf) (PDF) on 2016-04-17. Retrieved 2015-11-13.
17. [↑](./Random_forest#cite_ref-17) Geurts P, Ernst D, Wehenkel L (2006). ["Extremely randomized trees"](http://orbi.ulg.ac.be/bitstream/2268/9357/1/geurts-mlj-advance.pdf) (PDF). *Machine Learning*. **63**: 3–42. [doi](./Doi_(identifier)):[10.1007/s10994-006-6226-1](https://doi.org/10.1007%2Fs10994-006-6226-1).
18. [↑](./Random_forest#cite_ref-18) Dessi, N. & Milia, G. & Pes, B. (2013). Enhancing random forests performance in microarray data classification. Conference paper, 99-103. 10.1007/978-3-642-38326-7_15.
19. [↑](./Random_forest#cite_ref-19) Ye, Y., Li, H., Deng, X., and Huang, J. (2008) Feature weighting random forest for detection of hidden web search interfaces. Journal of Computational Linguistics and Chinese Language Processing, 13, 387–404.
20. [↑](./Random_forest#cite_ref-20) Amaratunga, D., Cabrera, J., Lee, Y.S. (2008) Enriched Random Forest. Bioinformatics, 24, 2010-2014.
21. [↑](./Random_forest#cite_ref-21) Ghosh D, Cabrera J. (2022) Enriched random forest for high dimensional genomic data. IEEE/ACM Trans Comput Biol Bioinform. 19(5):2817-2828. doi:10.1109/TCBB.2021.3089417. 
22. [↑](./Random_forest#cite_ref-22)  Amaratunga, D., Cabrera, J., Shkedy, Z. (2014). Exploration and Analysis of DNA Microarray and Other High-Dimensional Data. New York: John Wiley. Second Edition. 0.1002/9781118364505. 
23. [↑](./Random_forest#cite_ref-23) Winham, Stacey & Freimuth, Robert & Biernacka, Joanna. (2013). A weighted random forests approach to improve predictive performance. Statistical Analysis and Data Mining. 6. 10.1002/sam.11196. 
24. [↑](./Random_forest#cite_ref-24)  Li, H. B., Wang, W., Ding, H. W., & Dong, J. (2010, 10-12 Nov. 2010). Trees weighting random forest method for classifying high-dimensional noisy data. Paper presented at the 2010 IEEE 7th International Conference on E-Business Engineering. 
25. [↑](./Random_forest#cite_ref-25) Zhu R, Zeng D, Kosorok MR (2015). ["Reinforcement Learning Trees"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4760114). *Journal of the American Statistical Association*. **110** (512): 1770–1784. [Bibcode](./Bibcode_(identifier)):[2015JASA..110.1770Z](https://ui.adsabs.harvard.edu/abs/2015JASA..110.1770Z). [doi](./Doi_(identifier)):[10.1080/01621459.2015.1036994](https://doi.org/10.1080%2F01621459.2015.1036994). [PMC](./PMC_(identifier)) [4760114](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4760114). [PMID](./PMID_(identifier)) [26903687](https://pubmed.ncbi.nlm.nih.gov/26903687).
26. [↑](./Random_forest#cite_ref-26) Deng, H.; Runger, G.; Tuv, E. (2011). [*Bias of importance measures for multi-valued attributes and solutions*](https://www.researchgate.net/publication/221079908). Proceedings of the 21st International Conference on Artificial Neural Networks (ICANN). pp. 293–300.
27. [↑](./Random_forest#cite_ref-27) Altmann A, Toloşi L, Sander O, Lengauer T (May 2010). ["Permutation importance: a corrected feature importance measure"](https://doi.org/10.1093%2Fbioinformatics%2Fbtq134). *Bioinformatics*. **26** (10): 1340–7. [doi](./Doi_(identifier)):[10.1093/bioinformatics/btq134](https://doi.org/10.1093%2Fbioinformatics%2Fbtq134). [PMID](./PMID_(identifier)) [20385727](https://pubmed.ncbi.nlm.nih.gov/20385727).
28. [↑](./Random_forest#cite_ref-:02_28-0) Piryonesi S. Madeh; El-Diraby Tamer E. (2020-06-01). "Role of Data Analytics in Infrastructure Asset Management: Overcoming Data Size and Quality Problems". *Journal of Transportation Engineering, Part B: Pavements*. **146** (2): 04020022. [doi](./Doi_(identifier)):[10.1061/JPEODX.0000175](https://doi.org/10.1061%2FJPEODX.0000175). [S2CID](./S2CID_(identifier)) [216485629](https://api.semanticscholar.org/CorpusID:216485629).
29. [↑](./Random_forest#cite_ref-29) Strobl C, Boulesteix AL, Augustin T (2007). ["Unbiased split selection for classification trees based on the Gini index"](https://epub.ub.uni-muenchen.de/1833/1/paper_464.pdf) (PDF). *Computational Statistics & Data Analysis*. **52**: 483–501. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.525.3178](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.525.3178). [doi](./Doi_(identifier)):[10.1016/j.csda.2006.12.030](https://doi.org/10.1016%2Fj.csda.2006.12.030).
30. [↑](./Random_forest#cite_ref-30) Painsky A, Rosset S (2017). "Cross-Validated Variable Selection in Tree-Based Methods Improves Predictive Performance". *IEEE Transactions on Pattern Analysis and Machine Intelligence*. **39** (11): 2142–2153. [arXiv](./ArXiv_(identifier)):[1512.03444](https://arxiv.org/abs/1512.03444). [Bibcode](./Bibcode_(identifier)):[2017ITPAM..39.2142P](https://ui.adsabs.harvard.edu/abs/2017ITPAM..39.2142P). [doi](./Doi_(identifier)):[10.1109/tpami.2016.2636831](https://doi.org/10.1109%2Ftpami.2016.2636831). [PMID](./PMID_(identifier)) [28114007](https://pubmed.ncbi.nlm.nih.gov/28114007). [S2CID](./S2CID_(identifier)) [5381516](https://api.semanticscholar.org/CorpusID:5381516).
31. [↑](./Random_forest#cite_ref-31) Tolosi L, Lengauer T (July 2011). ["Classification with correlated features: unreliability of feature ranking and solutions"](https://doi.org/10.1093%2Fbioinformatics%2Fbtr300). *Bioinformatics*. **27** (14): 1986–94. [doi](./Doi_(identifier)):[10.1093/bioinformatics/btr300](https://doi.org/10.1093%2Fbioinformatics%2Fbtr300). [PMID](./PMID_(identifier)) [21576180](https://pubmed.ncbi.nlm.nih.gov/21576180).
32. [1](./Random_forest#cite_ref-:2_32-0) [2](./Random_forest#cite_ref-:2_32-1) ["Beware Default Random Forest Importances"](http://explained.ai/decision-tree-viz/index.html). *explained.ai*. Retrieved 2023-10-25.
33. [↑](./Random_forest#cite_ref-33) Ortiz-Posadas, Martha Refugio (2020-02-29). [*Pattern Recognition Techniques Applied to Biomedical Problems*](https://books.google.com/books?id=d6LTDwAAQBAJ&dq=Mean+Decrease+in+Impurity+Feature+Importance&pg=PA116). Springer Nature. [ISBN](./ISBN_(identifier)) [978-3-030-38021-2](./Special:BookSources/978-3-030-38021-2).
34. [↑](./Random_forest#cite_ref-34) Breiman, Leo (2017-10-25). [*Classification and Regression Trees*](https://www.taylorfrancis.com/books/mono/10.1201/9781315139470/classification-regression-trees-leo-breiman). New York: Routledge. [doi](./Doi_(identifier)):[10.1201/9781315139470](https://doi.org/10.1201%2F9781315139470). [ISBN](./ISBN_(identifier)) [978-1-315-13947-0](./Special:BookSources/978-1-315-13947-0).
35. [↑](./Random_forest#cite_ref-35) [https://scikit-learn.org/stable/auto_examples/inspection/plot_permutation_importance.html](https://scikit-learn.org/stable/auto_examples/inspection/plot_permutation_importance.html) 31. Aug. 2023
36. [1](./Random_forest#cite_ref-linjeon02_36-0) [2](./Random_forest#cite_ref-linjeon02_36-1) Lin, Yi; Jeon, Yongho (2002). *Random forests and adaptive nearest neighbors* (Technical report). Technical Report No. 1055. University of Wisconsin. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.153.9168](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.153.9168).
37. [↑](./Random_forest#cite_ref-37) Shi, T.; Horvath, S. (2006). "Unsupervised Learning with Random Forest Predictors". *Journal of Computational and Graphical Statistics*. **15** (1): 118–138. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.698.2365](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.698.2365). [doi](./Doi_(identifier)):[10.1198/106186006X94072](https://doi.org/10.1198%2F106186006X94072). [JSTOR](./JSTOR_(identifier)) [27594168](https://www.jstor.org/stable/27594168). [S2CID](./S2CID_(identifier)) [245216](https://api.semanticscholar.org/CorpusID:245216).
38. [↑](./Random_forest#cite_ref-38) Shi T, Seligson D, Belldegrun AS, Palotie A, Horvath S (April 2005). ["Tumor classification by tissue microarray profiling: random forest clustering applied to renal cell carcinoma"](https://doi.org/10.1038%2Fmodpathol.3800322). *Modern Pathology*. **18** (4): 547–57. [doi](./Doi_(identifier)):[10.1038/modpathol.3800322](https://doi.org/10.1038%2Fmodpathol.3800322). [PMID](./PMID_(identifier)) [15529185](https://pubmed.ncbi.nlm.nih.gov/15529185).
39. [1](./Random_forest#cite_ref-:0_39-0) [2](./Random_forest#cite_ref-:0_39-1) [3](./Random_forest#cite_ref-:0_39-2) [4](./Random_forest#cite_ref-:0_39-3) [5](./Random_forest#cite_ref-:0_39-4) Piryonesi, S. Madeh; El-Diraby, Tamer E. (2021-02-01). ["Using Machine Learning to Examine Impact of Type of Performance Indicator on Flexible Pavement Deterioration Modeling"](http://ascelibrary.org/doi/10.1061/%28ASCE%29IS.1943-555X.0000602). *Journal of Infrastructure Systems*. **27** (2): 04021005. [doi](./Doi_(identifier)):[10.1061/(ASCE)IS.1943-555X.0000602](https://doi.org/10.1061%2F%28ASCE%29IS.1943-555X.0000602). [ISSN](./ISSN_(identifier)) [1076-0342](https://search.worldcat.org/issn/1076-0342). [S2CID](./S2CID_(identifier)) [233550030](https://api.semanticscholar.org/CorpusID:233550030).
40. [↑](./Random_forest#cite_ref-40) Prinzie, A.; Van den Poel, D. (2008). "Random Forests for multiclass classification: Random MultiNomial Logit". *Expert Systems with Applications*. **34** (3): 1721–1732. [doi](./Doi_(identifier)):[10.1016/j.eswa.2007.01.029](https://doi.org/10.1016%2Fj.eswa.2007.01.029).
41. [↑](./Random_forest#cite_ref-41) Prinzie, Anita (2007). "Random Multiclass Classification: Generalizing Random Forests to Random MNL and Random NB". In Roland Wagner; Norman Revell; Günther Pernul (eds.). *Database and Expert Systems Applications: 18th International Conference, DEXA 2007, Regensburg, Germany, September 3-7, 2007, Proceedings*. Lecture Notes in Computer Science. Vol. 4653. pp. 349–358. [doi](./Doi_(identifier)):[10.1007/978-3-540-74469-6_35](https://doi.org/10.1007%2F978-3-540-74469-6_35). [ISBN](./ISBN_(identifier)) [978-3-540-74467-2](./Special:BookSources/978-3-540-74467-2).
42. [1](./Random_forest#cite_ref-:1_42-0) [2](./Random_forest#cite_ref-:1_42-1) Smith, Paul F.; Ganesh, Siva; Liu, Ping (2013-10-01). ["A comparison of random forest regression and multiple linear regression for prediction in neuroscience"](https://linkinghub.elsevier.com/retrieve/pii/S0165027013003026). *Journal of Neuroscience Methods*. **220** (1): 85–91. [doi](./Doi_(identifier)):[10.1016/j.jneumeth.2013.08.024](https://doi.org/10.1016%2Fj.jneumeth.2013.08.024). [PMID](./PMID_(identifier)) [24012917](https://pubmed.ncbi.nlm.nih.gov/24012917). [S2CID](./S2CID_(identifier)) [13195700](https://api.semanticscholar.org/CorpusID:13195700).
43. [1](./Random_forest#cite_ref-scornet2015random_43-0) [2](./Random_forest#cite_ref-scornet2015random_43-1) [3](./Random_forest#cite_ref-scornet2015random_43-2) [4](./Random_forest#cite_ref-scornet2015random_43-3) Scornet, Erwan (2015). "Random forests and kernel methods". [arXiv](./ArXiv_(identifier)):[1502.03836](https://arxiv.org/abs/1502.03836) [[math.ST](https://arxiv.org/archive/math.ST)].
44. [↑](./Random_forest#cite_ref-breiman2000some_44-0) [Breiman, Leo](./Leo_Breiman) (2000). ["Some infinity theory for predictor ensembles"](https://statistics.berkeley.edu/tech-reports/579). Technical Report 579, Statistics Dept. UCB. `{{cite journal}}`: Cite journal requires `|journal=` ([help](./Help:CS1_errors#missing_periodical))
45. [↑](./Random_forest#cite_ref-lin2006random_45-0) Lin, Yi; Jeon, Yongho (2006). "Random forests and adaptive nearest neighbors". *Journal of the American Statistical Association*. **101** (474): 578–590. [Bibcode](./Bibcode_(identifier)):[2006JASA..101..578L](https://ui.adsabs.harvard.edu/abs/2006JASA..101..578L). [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.153.9168](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.153.9168). [doi](./Doi_(identifier)):[10.1198/016214505000001230](https://doi.org/10.1198%2F016214505000001230). [S2CID](./S2CID_(identifier)) [2469856](https://api.semanticscholar.org/CorpusID:2469856).
46. [↑](./Random_forest#cite_ref-davies2014random_46-0) Davies, Alex; Ghahramani, Zoubin (2014). "The Random Forest Kernel and other kernels for big data from random partitions". [arXiv](./ArXiv_(identifier)):[1402.4293](https://arxiv.org/abs/1402.4293) [[stat.ML](https://arxiv.org/archive/stat.ML)].
47. [1](./Random_forest#cite_ref-breiman2004consistency_47-0) [2](./Random_forest#cite_ref-breiman2004consistency_47-1) Breiman L, Ghahramani Z (2004). "Consistency for a simple model of random forests". *Statistical Department, University of California at Berkeley. Technical Report* (670). [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.618.90](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.618.90).
48. [1](./Random_forest#cite_ref-arlot2014analysis_48-0) [2](./Random_forest#cite_ref-arlot2014analysis_48-1) Arlot S, Genuer R (2014). "Analysis of purely random forests bias". [arXiv](./ArXiv_(identifier)):[1407.3939](https://arxiv.org/abs/1407.3939) [[math.ST](https://arxiv.org/archive/math.ST)].
49. [↑](./Random_forest#cite_ref-49) Sagi, Omer; Rokach, Lior (2020). ["Explainable decision forest: Transforming a decision forest into an interpretable tree"](https://www.sciencedirect.com/science/article/pii/S1566253519307869). *Information Fusion*. **61**: 124–138. [Bibcode](./Bibcode_(identifier)):[2020InfFu..61..124S](https://ui.adsabs.harvard.edu/abs/2020InfFu..61..124S). [doi](./Doi_(identifier)):[10.1016/j.inffus.2020.03.013](https://doi.org/10.1016%2Fj.inffus.2020.03.013). [S2CID](./S2CID_(identifier)) [216444882](https://api.semanticscholar.org/CorpusID:216444882).
50. [↑](./Random_forest#cite_ref-50) Vidal, Thibaut; Schiffer, Maximilian (2020). ["Born-Again Tree Ensembles"](http://proceedings.mlr.press/v119/vidal20a.html). *International Conference on Machine Learning*. **119**. PMLR: 9743–9753. [arXiv](./ArXiv_(identifier)):[2003.11132](https://arxiv.org/abs/2003.11132).
51. [↑](./Random_forest#cite_ref-:3_51-0) Piryonesi, Sayed Madeh (November 2019). [*The Application of Data Analytics to Asset Management: Deterioration and Climate Change Adaptation in Ontario Roads (Doctoral dissertation)*](https://tspace.library.utoronto.ca/handle/1807/97601) (Thesis).

 

## Further reading

   [![logo](//upload.wikimedia.org/wikipedia/commons/thumb/3/32/Scholia_logo.svg/40px-Scholia_logo.svg.png)](./File:Scholia_logo.svg) [Scholia](https://www.wikidata.org/wiki/Wikidata:Scholia) has a *topic* profile for ***[Random forest](https://iw.toolforge.org/scholia/topic/Q245748)***.   
- Prinzie A, Poel D (2007). ["Random Multiclass Classification: Generalizing Random Forests to Random MNL and Random NB"](https://www.researchgate.net/publication/225175169). *Database and Expert Systems Applications*. [Lecture Notes in Computer Science](./Lecture_Notes_in_Computer_Science). Vol. 4653. p. 349. [doi](./Doi_(identifier)):[10.1007/978-3-540-74469-6_35](https://doi.org/10.1007%2F978-3-540-74469-6_35). [ISBN](./ISBN_(identifier)) [978-3-540-74467-2](./Special:BookSources/978-3-540-74467-2).
- Denisko D, Hoffman MM (February 2018). ["Classification and interaction in random forests"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5828645). *Proceedings of the National Academy of Sciences of the United States of America*. **115** (8): 1690–1692. [Bibcode](./Bibcode_(identifier)):[2018PNAS..115.1690D](https://ui.adsabs.harvard.edu/abs/2018PNAS..115.1690D). [doi](./Doi_(identifier)):[10.1073/pnas.1800256115](https://doi.org/10.1073%2Fpnas.1800256115). [PMC](./PMC_(identifier)) [5828645](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5828645). [PMID](./PMID_(identifier)) [29440440](https://pubmed.ncbi.nlm.nih.gov/29440440).
- Hajjem, Ahlem; Bellavance, François; Larocque, Denis (2014-06-03). ["Mixed-effects random forest for clustered data"](http://www.tandfonline.com/doi/abs/10.1080/00949655.2012.741599). *Journal of Statistical Computation and Simulation*. **84** (6): 1313–1328. [doi](./Doi_(identifier)):[10.1080/00949655.2012.741599](https://doi.org/10.1080%2F00949655.2012.741599). [ISSN](./ISSN_(identifier)) [0094-9655](https://search.worldcat.org/issn/0094-9655).

  

## External links

 
- [Random Forests classifier description](https://www.stat.berkeley.edu/~breiman/RandomForests/cc_home.htm) (Leo Breiman's site)
- [Liaw, Andy & Wiener, Matthew "Classification and Regression by randomForest" R News (2002) Vol. 2/3 p. 18](https://cran.r-project.org/doc/Rnews/Rnews_2002-3.pdf) (Discussion of the use of the random forest package for [R](./R_programming_language))