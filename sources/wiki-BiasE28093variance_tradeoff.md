---
source: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff
fetched: 2026-06-21
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

 

## Bias–variance decomposition of mean squared error

 Main article: [Mean squared error](./Mean_squared_error) [![](//upload.wikimedia.org/wikipedia/commons/thumb/2/29/Bias-variance_decomposition.png/250px-Bias-variance_decomposition.png)](./File:Bias-variance_decomposition.png)Bias–variance decomposition in the case of mean squared loss. The green dots are samples of test label     y   {\displaystyle y}  ![{\displaystyle y}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b8a6208ec717213d4317e666f1ae872e00620a0d) at a fixed test feature     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4). Their variance around the mean       E   y ∼ ∼  p ( ⋅ ⋅   |  x )   [ y ]   {\displaystyle \mathbb {E} _{y\sim p(\cdot |x)}[y]}  ![{\displaystyle \mathbb {E} _{y\sim p(\cdot |x)}[y]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c23faf1477131ac8efa4b9671c13051031db50b3) is the irreducible error      σ σ   2     {\displaystyle \sigma ^{2}}  ![{\displaystyle \sigma ^{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/53a5c55e536acf250c1d3e0f754be5692b843ef5). The red dots are test label predictions     f ( x  |  D )   {\displaystyle f(x|D)}  ![{\displaystyle f(x|D)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f27b4da08025dc1a2e631f86c69b619d9d09933e) as the training set     D   {\displaystyle D}  ![{\displaystyle D}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f34a0c600395e5d4345287e21fb26efd386990e6) is randomly sampled. Their variance around the mean       E   D   [ f ( x  |  D ) ]   {\displaystyle \mathbb {E} _{D}[f(x|D)]}  ![{\displaystyle \mathbb {E} _{D}[f(x|D)]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d03e366778e4058f3e5c440129a40bfca3090d67) is the variance      Var  D   ⁡ ⁡    [   f ( x  |  D )   ]     {\displaystyle \operatorname {Var} _{D}{\big [}f(x|D){\big ]}}  ![{\displaystyle \operatorname {Var} _{D}{\big [}f(x|D){\big ]}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/debf8d2bda6af2b584fe8af5321f8e29830f39d8). The difference between the red dash and the green dash is the bias      Bias  D   ⁡ ⁡    [   f ( x  |  D )   ]     {\displaystyle \operatorname {Bias} _{D}{\big [}f(x|D){\big ]}}  ![{\displaystyle \operatorname {Bias} _{D}{\big [}f(x|D){\big ]}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/432e815d6e96765bb20ca9ce8718e36edb71efea). The bias–variance decomposition is then visually clear: the mean squared error between the red dots and the green dots is the sum of the three components. 

Suppose that we have a training set consisting of a set of points      x  1   , … …  ,  x  n     {\displaystyle x_{1},\dots ,x_{n}}  ![{\displaystyle x_{1},\dots ,x_{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e5afdbc2d248d8fa9ba2c4f5188d946a0537e753) and real-valued labels      y  i     {\displaystyle y_{i}}  ![{\displaystyle y_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/67d30d30b6c2dbe4d6f150d699de040937ecc95f) associated with the points      x  i     {\displaystyle x_{i}}  ![{\displaystyle x_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e87000dd6142b81d041896a30fe58f0c3acb2158). We assume that the data is generated by a function     f ( x )   {\displaystyle f(x)}  ![{\displaystyle f(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/202945cce41ecebb6f643f31d119c514bec7a074) such as     y = f ( x ) + ε ε    {\displaystyle y=f(x)+\varepsilon }  ![{\displaystyle y=f(x)+\varepsilon }](https://wikimedia.org/api/rest_v1/media/math/render/svg/93f385c9e8b0b5372dd00cfcaa57b1fe20bb812b), where the noise,     ε ε    {\displaystyle \varepsilon }  ![{\displaystyle \varepsilon }](https://wikimedia.org/api/rest_v1/media/math/render/svg/a30c89172e5b88edbd45d3e2772c7f5e562e5173), has zero mean and unit variance      σ σ   2     {\displaystyle \sigma ^{2}}  ![{\displaystyle \sigma ^{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/53a5c55e536acf250c1d3e0f754be5692b843ef5). That is,      y  i   = f (  x  i   ) +  ε ε   i     {\displaystyle y_{i}=f(x_{i})+\varepsilon _{i}}  ![{\displaystyle y_{i}=f(x_{i})+\varepsilon _{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/416bfa435006697e7aa8b64d17bebc2959169f26), where      ε ε   i     {\displaystyle \varepsilon _{i}}  ![{\displaystyle \varepsilon _{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/00e1b6ad3cbad4af49bf21a3ad2dc379ff045079) is a noise sample.

 

We want to find a function        f ^ ^      ( x ; D )   {\displaystyle {\hat {f}}\!(x;D)}  ![{\displaystyle {\hat {f}}\!(x;D)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/186b08856b7fcdba602c5de5f7f3f36c087ef1f0), that approximates the true function     f ( x )   {\displaystyle f(x)}  ![{\displaystyle f(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/202945cce41ecebb6f643f31d119c514bec7a074) as well as possible, by means of some learning algorithm based on a training dataset (sample)     D = { (  x  1   ,  y  1   ) … …  , (  x  n   ,  y  n   ) }   {\displaystyle D=\{(x_{1},y_{1})\dots ,(x_{n},y_{n})\}}  ![{\displaystyle D=\{(x_{1},y_{1})\dots ,(x_{n},y_{n})\}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/757190ec5d200f1ca40a0d23e32f090a12352b6d). We make "as well as possible" precise by measuring the [mean squared error](./Mean_squared_error) between     y   {\displaystyle y}  ![{\displaystyle y}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b8a6208ec717213d4317e666f1ae872e00620a0d) and        f ^ ^      ( x ; D )   {\displaystyle {\hat {f}}\!(x;D)}  ![{\displaystyle {\hat {f}}\!(x;D)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/186b08856b7fcdba602c5de5f7f3f36c087ef1f0): we want     ( y − −     f ^ ^      ( x ; D )  )  2     {\displaystyle (y-{\hat {f}}\!(x;D))^{2}}  ![{\displaystyle (y-{\hat {f}}\!(x;D))^{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f3c81e7f198fb1a27a19e6672a9b11f356a69ec2) to be minimal, both for      x  1   , … …  ,  x  n     {\displaystyle x_{1},\dots ,x_{n}}  ![{\displaystyle x_{1},\dots ,x_{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e5afdbc2d248d8fa9ba2c4f5188d946a0537e753) *and for points outside of our sample*. Of course, we cannot hope to do so perfectly, since the      y  i     {\displaystyle y_{i}}  ![{\displaystyle y_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/67d30d30b6c2dbe4d6f150d699de040937ecc95f) contain noise     ε ε    {\displaystyle \varepsilon }  ![{\displaystyle \varepsilon }](https://wikimedia.org/api/rest_v1/media/math/render/svg/a30c89172e5b88edbd45d3e2772c7f5e562e5173); this means we must be prepared to accept an *irreducible error* in any function we come up with.

 

Finding an        f ^ ^       {\displaystyle {\hat {f}}}  ![{\displaystyle {\hat {f}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/14ce989fd75da938ec6f95a0cdb71037b23a11cb) that generalizes to points outside of the training set can be done with any of the countless algorithms used for supervised learning. It turns out that whichever function        f ^ ^       {\displaystyle {\hat {f}}}  ![{\displaystyle {\hat {f}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/14ce989fd75da938ec6f95a0cdb71037b23a11cb) we select, we can decompose its [expected](./Expected_value) error on an unseen sample     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4) (i.e. conditional on     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4)) as follows:[[7]](./Bias–variance_tradeoff#cite_note-islr-7): 34 [[8]](./Bias–variance_tradeoff#cite_note-ESL-8): 223 

 

      E   D , ε ε      [     (   y − −     f ^ ^      ( x ; D )    )    2     ]   =   (    Bias  D   ⁡ ⁡    [      f ^ ^      ( x ; D )   ]      )    2   +  Var  D   ⁡ ⁡    [      f ^ ^      ( x ; D )   ]   +  σ σ   2     {\displaystyle \mathbb {E} _{D,\varepsilon }{\Big [}{\big (}y-{\hat {f}}\!(x;D){\big )}^{2}{\Big ]}={\Big (}\operatorname {Bias} _{D}{\big [}{\hat {f}}\!(x;D){\big ]}{\Big )}^{2}+\operatorname {Var} _{D}{\big [}{\hat {f}}\!(x;D){\big ]}+\sigma ^{2}}  ![{\displaystyle \mathbb {E} _{D,\varepsilon }{\Big [}{\big (}y-{\hat {f}}\!(x;D){\big )}^{2}{\Big ]}={\Big (}\operatorname {Bias} _{D}{\big [}{\hat {f}}\!(x;D){\big ]}{\Big )}^{2}+\operatorname {Var} _{D}{\big [}{\hat {f}}\!(x;D){\big ]}+\sigma ^{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/bc8ac14785fa40e88187a561d274bce4d88c0bde)

 

where
         Bias  D   ⁡ ⁡    [      f ^ ^      ( x ; D )   ]      ≜ ≜    E   D     [      f ^ ^      ( x ; D ) − −  f ( x )   ]         =   E   D     [      f ^ ^      ( x ; D )   ]    − −   f ( x )       =   E   D     [      f ^ ^      ( x ; D )   ]    − −     E   y  |  x     [   y ( x )   ]         {\displaystyle {\begin{aligned}\operatorname {Bias} _{D}{\big [}{\hat {f}}\!(x;D){\big ]}&\triangleq \mathbb {E} _{D}{\big [}{\hat {f}}\!(x;D)-f(x){\big ]}\\&=\mathbb {E} _{D}{\big [}{\hat {f}}\!(x;D){\big ]}\,-\,f(x)\\&=\mathbb {E} _{D}{\big [}{\hat {f}}\!(x;D){\big ]}\,-\,\mathbb {E} _{y|x}{\big [}y(x){\big ]}\end{aligned}}}  ![{\displaystyle {\begin{aligned}\operatorname {Bias} _{D}{\big [}{\hat {f}}\!(x;D){\big ]}&\triangleq \mathbb {E} _{D}{\big [}{\hat {f}}\!(x;D)-f(x){\big ]}\\&=\mathbb {E} _{D}{\big [}{\hat {f}}\!(x;D){\big ]}\,-\,f(x)\\&=\mathbb {E} _{D}{\big [}{\hat {f}}\!(x;D){\big ]}\,-\,\mathbb {E} _{y|x}{\big [}y(x){\big ]}\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/043d7739b154fbe3689b442accca933fda092ffd)

 

and

 

     Var  D   ⁡ ⁡    [      f ^ ^      ( x ; D )   ]   ≜ ≜    E   D    [   (    E   D   [    f ^ ^      ( x ; D ) ] − −     f ^ ^      ( x ; D )  )   2   ]    {\displaystyle \operatorname {Var} _{D}{\big [}{\hat {f}}\!(x;D){\big ]}\triangleq \mathbb {E} _{D}\left[\left(\mathbb {E} _{D}[{\hat {f}}\!(x;D)]-{\hat {f}}\!(x;D)\right)^{2}\right]}  ![{\displaystyle \operatorname {Var} _{D}{\big [}{\hat {f}}\!(x;D){\big ]}\triangleq \mathbb {E} _{D}\left[\left(\mathbb {E} _{D}[{\hat {f}}\!(x;D)]-{\hat {f}}\!(x;D)\right)^{2}\right]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9c4a50e75a9073200a5bc1e9e188768c8b7018ac)

 

and

 

     σ σ   2   =  E  y   ⁡ ⁡    [     (   y − −      f ( x )  ⏟ ⏟      E  y  |  x   [ y ]      )    2     ]     {\displaystyle \sigma ^{2}=\operatorname {E} _{y}{\Big [}{\big (}y-\underbrace {f(x)} _{E_{y|x}[y]}{\big )}^{2}{\Big ]}}  ![{\displaystyle \sigma ^{2}=\operatorname {E} _{y}{\Big [}{\big (}y-\underbrace {f(x)} _{E_{y|x}[y]}{\big )}^{2}{\Big ]}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/363178ae1f1f3bb2ccd1d6b28d4c33aa7b71ba11)

 

The expectation ranges over different choices of the training set     D = { (  x  1   ,  y  1   ) … …  , (  x  n   ,  y  n   ) }   {\displaystyle D=\{(x_{1},y_{1})\dots ,(x_{n},y_{n})\}}  ![{\displaystyle D=\{(x_{1},y_{1})\dots ,(x_{n},y_{n})\}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/757190ec5d200f1ca40a0d23e32f090a12352b6d), all sampled from the same joint distribution     P ( x , y )   {\displaystyle P(x,y)}  ![{\displaystyle P(x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d5b3d8f37f5458c22b61eaf26e5af0523acb63e2) which can for example be done via [bootstrapping](./Bootstrapping_(statistics)).
The three terms represent:

 
- the square of the *bias* of the learning method, which can be thought of as the error caused by the simplifying assumptions built into the method. E.g., when approximating a non-linear function     f ( x )   {\displaystyle f(x)}  ![{\displaystyle f(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/202945cce41ecebb6f643f31d119c514bec7a074) using a learning method for [linear models](./Linear_model), there will be error in the estimates        f ^ ^      ( x )   {\displaystyle {\hat {f}}\!(x)}  ![{\displaystyle {\hat {f}}\!(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5e78398f42d06067149ec542265486da6e5061c2) due to this assumption;
- the *variance* of the learning method, or, intuitively, how much the learning method        f ^ ^      ( x )   {\displaystyle {\hat {f}}\!(x)}  ![{\displaystyle {\hat {f}}\!(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5e78398f42d06067149ec542265486da6e5061c2) will move around its mean;
- the irreducible error      σ σ   2     {\displaystyle \sigma ^{2}}  ![{\displaystyle \sigma ^{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/53a5c55e536acf250c1d3e0f754be5692b843ef5).

 

Since all three terms are non-negative, the irreducible error forms a lower bound on the expected error on unseen samples.[[7]](./Bias–variance_tradeoff#cite_note-islr-7): 34 

 

The more complex the model        f ^ ^      ( x )   {\displaystyle {\hat {f}}\!(x)}  ![{\displaystyle {\hat {f}}\!(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5e78398f42d06067149ec542265486da6e5061c2) is, the more data points it will capture, and the lower the bias will be. However, complexity will make the model "move" more to capture the data points, and hence its variance will be larger.

 

### Derivation

 

The derivation of the bias–variance decomposition for squared error proceeds as follows.[[9]](./Bias–variance_tradeoff#cite_note-9)[[10]](./Bias–variance_tradeoff#cite_note-10) For convenience, we drop the     D   {\displaystyle D}  ![{\displaystyle D}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f34a0c600395e5d4345287e21fb26efd386990e6) subscript in the following lines, such that        f ^ ^      ( x ; D ) =    f ^ ^      ( x )   {\displaystyle {\hat {f}}\!(x;D)={\hat {f}}\!(x)}  ![{\displaystyle {\hat {f}}\!(x;D)={\hat {f}}\!(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/676475fabb2b5f39aacec8b9cfa208489a6040ff).

 

Let us write the mean-squared error of our model:

 

         MSE  ( x )    ≜ ≜   E    [     (   y − −     f ^ ^      ( x )    )    2     ]         =  E    [     (   f ( x ) + ε ε  − −     f ^ ^      ( x )    )    2     ]       since   y ≜ ≜  f ( x ) + ε ε        =  E    [     (   f ( x ) − −     f ^ ^      ( x )    )    2     ]    +  2    E    [     (   f ( x ) − −     f ^ ^      ( x )   )   ε ε    ]    +   E  [  ε ε   2   ]       {\displaystyle {\begin{aligned}{\text{MSE}}(x)&\triangleq \mathbb {E} {\Big [}{\big (}y-{\hat {f}}\!(x){\big )}^{2}{\Big ]}\\&=\mathbb {E} {\Big [}{\big (}f(x)+\varepsilon -{\hat {f}}\!(x){\big )}^{2}{\Big ]}&&{\text{since }}y\triangleq f(x)+\varepsilon \\&=\mathbb {E} {\Big [}{\big (}f(x)-{\hat {f}}\!(x){\big )}^{2}{\Big ]}\,+\,2\ \mathbb {E} {\Big [}{\big (}f(x)-{\hat {f}}\!(x){\big )}\varepsilon {\Big ]}\,+\,\mathbb {E} [\varepsilon ^{2}]\end{aligned}}}  ![{\displaystyle {\begin{aligned}{\text{MSE}}(x)&\triangleq \mathbb {E} {\Big [}{\big (}y-{\hat {f}}\!(x){\big )}^{2}{\Big ]}\\&=\mathbb {E} {\Big [}{\big (}f(x)+\varepsilon -{\hat {f}}\!(x){\big )}^{2}{\Big ]}&&{\text{since }}y\triangleq f(x)+\varepsilon \\&=\mathbb {E} {\Big [}{\big (}f(x)-{\hat {f}}\!(x){\big )}^{2}{\Big ]}\,+\,2\ \mathbb {E} {\Big [}{\big (}f(x)-{\hat {f}}\!(x){\big )}\varepsilon {\Big ]}\,+\,\mathbb {E} [\varepsilon ^{2}]\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1184d0758eb38c370a3d25fff749b0cd26f9f760)

 

We can show that the second term of this equation is null:

 

         E    [     (   f ( x ) − −     f ^ ^      ( x )   )   ε ε    ]      =  E    [   f ( x ) − −     f ^ ^      ( x )   ]      E    [   ε ε    ]       since   ε ε    is independent from   x       = 0     since    E    [   ε ε    ]   = 0       {\displaystyle {\begin{aligned}\mathbb {E} {\Big [}{\big (}f(x)-{\hat {f}}\!(x){\big )}\varepsilon {\Big ]}&=\mathbb {E} {\big [}f(x)-{\hat {f}}\!(x){\big ]}\ \mathbb {E} {\big [}\varepsilon {\big ]}&&{\text{since }}\varepsilon {\text{ is independent from }}x\\&=0&&{\text{since }}\mathbb {E} {\big [}\varepsilon {\big ]}=0\end{aligned}}}  ![{\displaystyle {\begin{aligned}\mathbb {E} {\Big [}{\big (}f(x)-{\hat {f}}\!(x){\big )}\varepsilon {\Big ]}&=\mathbb {E} {\big [}f(x)-{\hat {f}}\!(x){\big ]}\ \mathbb {E} {\big [}\varepsilon {\big ]}&&{\text{since }}\varepsilon {\text{ is independent from }}x\\&=0&&{\text{since }}\mathbb {E} {\big [}\varepsilon {\big ]}=0\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7bebcd8c98779f7aebc9d8353ce6f42d50cc335e)

 

Moreover, the third term of this equation is nothing but      σ σ   2     {\displaystyle \sigma ^{2}}  ![{\displaystyle \sigma ^{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/53a5c55e536acf250c1d3e0f754be5692b843ef5), the variance of     ε ε    {\displaystyle \varepsilon }  ![{\displaystyle \varepsilon }](https://wikimedia.org/api/rest_v1/media/math/render/svg/a30c89172e5b88edbd45d3e2772c7f5e562e5173).

 

Let us now expand the remaining term:

 

           E   ⁡ ⁡   [   (  f ( x ) − −     f ^ ^      ( x )  )   2   ]        =   E   ⁡ ⁡   [   (  f ( x ) − −    E   ⁡ ⁡  [    f ^ ^      ( x ) ] +   E   ⁡ ⁡  [    f ^ ^      ( x ) ] − −     f ^ ^      ( x )  )   2   ]        =     E   ⁡ ⁡   [   (  f ( x ) − −    E   ⁡ ⁡  [    f ^ ^      ( x ) ]  )   2   ]     +    E   ⁡ ⁡   [   (    E   ⁡ ⁡  [    f ^ ^      ( x ) ] − −     f ^ ^      ( x )  )   2   ]          +  2       E   ⁡ ⁡   [   (  f ( x ) − −    E   ⁡ ⁡  [    f ^ ^      ( x ) ]  )   (    E   ⁡ ⁡  [    f ^ ^      ( x ) ] − −     f ^ ^      ( x )  )   ]          {\displaystyle {\begin{aligned}&\operatorname {\mathbb {E} } \left[\left(f(x)-{\hat {f}}\!(x)\right)^{2}\right]\\[1ex]&=\operatorname {\mathbb {E} } \left[\left(f(x)-\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]+\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]-{\hat {f}}\!(x)\right)^{2}\right]\\[1ex]&={\color {Blue}\operatorname {\mathbb {E} } \left[\left(f(x)-\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]\right)^{2}\right]}\,+\,\operatorname {\mathbb {E} } \left[\left(\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]-{\hat {f}}\!(x)\right)^{2}\right]\\&\quad \,+\,2\ {\color {PineGreen}\operatorname {\mathbb {E} } \left[\left(f(x)-\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]\right)\left(\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]-{\hat {f}}\!(x)\right)\right]}\end{aligned}}}  ![{\displaystyle {\begin{aligned}&\operatorname {\mathbb {E} } \left[\left(f(x)-{\hat {f}}\!(x)\right)^{2}\right]\\[1ex]&=\operatorname {\mathbb {E} } \left[\left(f(x)-\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]+\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]-{\hat {f}}\!(x)\right)^{2}\right]\\[1ex]&={\color {Blue}\operatorname {\mathbb {E} } \left[\left(f(x)-\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]\right)^{2}\right]}\,+\,\operatorname {\mathbb {E} } \left[\left(\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]-{\hat {f}}\!(x)\right)^{2}\right]\\&\quad \,+\,2\ {\color {PineGreen}\operatorname {\mathbb {E} } \left[\left(f(x)-\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]\right)\left(\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]-{\hat {f}}\!(x)\right)\right]}\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/85f3a62afba18942b33b348e836e8a06f95141da)

 

We show that:

 

           E    [     (   f ( x ) − −   E    [      f ^ ^     ( x )   ]      )    2     ]        =  E    [   f ( x  )  2     ]    − −   2    E    [   f ( x )    E    [      f ^ ^     ( x )   ]     ]    +   E    [    E    [      f ^ ^     ( x )    ]    2     ]         = f ( x  )  2    − −   2   f ( x )    E    [      f ^ ^     ( x )   ]    +   E    [      f ^ ^     ( x )    ]    2         =   (   f ( x ) − −   E    [      f ^ ^     ( x )   ]      )    2         {\displaystyle {\begin{aligned}{\color {Blue}\mathbb {E} {\Big [}{\big (}f(x)-\mathbb {E} {\big [}{\hat {f}}(x){\big ]}{\big )}^{2}{\Big ]}}&=\mathbb {E} {\big [}f(x)^{2}{\big ]}\,-\,2\ \mathbb {E} {\Big [}f(x)\ \mathbb {E} {\big [}{\hat {f}}(x){\big ]}{\Big ]}\,+\,\mathbb {E} {\Big [}\mathbb {E} {\big [}{\hat {f}}(x){\big ]}^{2}{\Big ]}\\&=f(x)^{2}\,-\,2\ f(x)\ \mathbb {E} {\big [}{\hat {f}}(x){\big ]}\,+\,\mathbb {E} {\big [}{\hat {f}}(x){\big ]}^{2}\\&={\Big (}f(x)-\mathbb {E} {\big [}{\hat {f}}(x){\big ]}{\Big )}^{2}\end{aligned}}}  ![{\displaystyle {\begin{aligned}{\color {Blue}\mathbb {E} {\Big [}{\big (}f(x)-\mathbb {E} {\big [}{\hat {f}}(x){\big ]}{\big )}^{2}{\Big ]}}&=\mathbb {E} {\big [}f(x)^{2}{\big ]}\,-\,2\ \mathbb {E} {\Big [}f(x)\ \mathbb {E} {\big [}{\hat {f}}(x){\big ]}{\Big ]}\,+\,\mathbb {E} {\Big [}\mathbb {E} {\big [}{\hat {f}}(x){\big ]}^{2}{\Big ]}\\&=f(x)^{2}\,-\,2\ f(x)\ \mathbb {E} {\big [}{\hat {f}}(x){\big ]}\,+\,\mathbb {E} {\big [}{\hat {f}}(x){\big ]}^{2}\\&={\Big (}f(x)-\mathbb {E} {\big [}{\hat {f}}(x){\big ]}{\Big )}^{2}\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ec4eabfbb69527a08fa50c28e1ad1f3b09791b10)

 

This last series of equalities comes from the fact that     f ( x )   {\displaystyle f(x)}  ![{\displaystyle f(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/202945cce41ecebb6f643f31d119c514bec7a074) is not a random variable, but a fixed, deterministic function of     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4). Therefore,       E   ⁡ ⁡   [  f ( x )  ]  = f ( x )   {\displaystyle \operatorname {\mathbb {E} } \left[f(x)\right]=f(x)}  ![{\displaystyle \operatorname {\mathbb {E} } \left[f(x)\right]=f(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a4ad3ac5be826f6c4dcda2ba1d4055d1a1d06e83). Similarly       E   ⁡ ⁡   [  f ( x  )  2    ]  = f ( x  )  2     {\displaystyle \operatorname {\mathbb {E} } \left[f(x)^{2}\right]=f(x)^{2}}  ![{\displaystyle \operatorname {\mathbb {E} } \left[f(x)^{2}\right]=f(x)^{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0ff27cef242c5012b8230225c42153d277387d82), and       E   ⁡ ⁡   [  f ( x )    E   ⁡ ⁡  [    f ^ ^      ( x ) ]  ]  = f ( x )    E   ⁡ ⁡   [    E   ⁡ ⁡  [    f ^ ^      ( x ) ]  ]  = f ( x )   E   ⁡ ⁡  [    f ^ ^      ( x ) ]   {\displaystyle \operatorname {\mathbb {E} } \left[f(x)\,\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]\right]=f(x)\,\operatorname {\mathbb {E} } \left[\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]\right]=f(x)\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]}  ![{\displaystyle \operatorname {\mathbb {E} } \left[f(x)\,\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]\right]=f(x)\,\operatorname {\mathbb {E} } \left[\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]\right]=f(x)\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3ad05dcff5c1b12a86a093cb5d80a701f7ac1c30). Using the same reasoning, we can expand the second term and show that it is null:

 

             E   ⁡ ⁡   [   (  f ( x ) − −    E   ⁡ ⁡  [    f ^ ^      ( x ) ]  )   (    E   ⁡ ⁡  [    f ^ ^      ( x ) ] − −     f ^ ^      ( x )  )   ]          =   E   ⁡ ⁡   [  f ( x )    E   ⁡ ⁡  [    f ^ ^      ( x ) ]  − −   f ( x )    f ^ ^      ( x )  − −     E   ⁡ ⁡  [    f ^ ^      ( x )  ]  2   +   E   ⁡ ⁡  [    f ^ ^      ( x ) ]     f ^ ^      ( x )  ]        = f ( x )    E   ⁡ ⁡  [    f ^ ^      ( x ) ]  − −   f ( x )    E   ⁡ ⁡  [    f ^ ^      ( x ) ]  − −     E   ⁡ ⁡  [    f ^ ^      ( x )  ]  2    +    E   ⁡ ⁡  [    f ^ ^      ( x )  ]  2         = 0       {\displaystyle {\begin{aligned}&{\color {PineGreen}\operatorname {\mathbb {E} } \left[\left(f(x)-\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]\right)\left(\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]-{\hat {f}}\!(x)\right)\right]}\\&=\operatorname {\mathbb {E} } \left[f(x)\,\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]\,-\,f(x){\hat {f}}\!(x)\,-\,\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]^{2}+\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]\,{\hat {f}}\!(x)\right]\\&=f(x)\,\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]\,-\,f(x)\,\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]\,-\,\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]^{2}\,+\,\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]^{2}\\&=0\end{aligned}}}  ![{\displaystyle {\begin{aligned}&{\color {PineGreen}\operatorname {\mathbb {E} } \left[\left(f(x)-\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]\right)\left(\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]-{\hat {f}}\!(x)\right)\right]}\\&=\operatorname {\mathbb {E} } \left[f(x)\,\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]\,-\,f(x){\hat {f}}\!(x)\,-\,\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]^{2}+\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]\,{\hat {f}}\!(x)\right]\\&=f(x)\,\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]\,-\,f(x)\,\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]\,-\,\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]^{2}\,+\,\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]^{2}\\&=0\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/581af7c107f6d26b2196110ab5c6482460e6b46c)

 

Eventually, we plug our derivations back into the original equation, and identify each term:

 

         MSE  ( x )    =   (  f ( x ) − −    E   ⁡ ⁡  [    f ^ ^      ( x ) ]  )   2   +   E   ⁡ ⁡   [   (    E   ⁡ ⁡  [    f ^ ^      ( x ) ] − −     f ^ ^      ( x )  )   2   ]  +  σ σ   2         = Bias ⁡ ⁡    [     f ^ ^      ( x )  ]   2   +  Var ⁡ ⁡   [     f ^ ^      ( x )  ]   +   σ σ   2         {\displaystyle {\begin{aligned}{\text{MSE}}(x)&=\left(f(x)-\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]\right)^{2}+\operatorname {\mathbb {E} } \left[\left(\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]-{\hat {f}}\!(x)\right)^{2}\right]+\sigma ^{2}\\&=\operatorname {Bias} \left[{\hat {f}}\!(x)\right]^{2}+\,\operatorname {Var} \left[{\hat {f}}\!(x)\right]\,+\,\sigma ^{2}\end{aligned}}}  ![{\displaystyle {\begin{aligned}{\text{MSE}}(x)&=\left(f(x)-\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]\right)^{2}+\operatorname {\mathbb {E} } \left[\left(\operatorname {\mathbb {E} } [{\hat {f}}\!(x)]-{\hat {f}}\!(x)\right)^{2}\right]+\sigma ^{2}\\&=\operatorname {Bias} \left[{\hat {f}}\!(x)\right]^{2}+\,\operatorname {Var} \left[{\hat {f}}\!(x)\right]\,+\,\sigma ^{2}\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/82a89f9479c4406cd8f041a3a9aeecb12fb4aad1)

 

Finally, the MSE loss function (or negative log-likelihood) is obtained by taking the expectation value over     x ∼ ∼  P   {\displaystyle x\sim P}  ![{\displaystyle x\sim P}](https://wikimedia.org/api/rest_v1/media/math/render/svg/22dca9c851a0f2939e608ad215bf42408aa95be8):
     MSE  =    E    x   ⁡ ⁡   [   MSE  ( x )  ]  =    E    x   ⁡ ⁡   {   Bias  D      [     f ^ ^      ( x ; D )  ]   2   +  Var  D   ⁡ ⁡   [     f ^ ^      ( x ; D )  ]   }  +  σ σ   2   .   {\displaystyle {\text{MSE}}=\operatorname {\mathbb {E} } _{x}\left[{\text{MSE}}(x)\right]=\operatorname {\mathbb {E} } _{x}\left\{\operatorname {Bias} _{D}\!\left[{\hat {f}}\!(x;D)\right]^{2}+\operatorname {Var} _{D}\left[{\hat {f}}\!(x;D)\right]\right\}+\sigma ^{2}.}  ![{\displaystyle {\text{MSE}}=\operatorname {\mathbb {E} } _{x}\left[{\text{MSE}}(x)\right]=\operatorname {\mathbb {E} } _{x}\left\{\operatorname {Bias} _{D}\!\left[{\hat {f}}\!(x;D)\right]^{2}+\operatorname {Var} _{D}\left[{\hat {f}}\!(x;D)\right]\right\}+\sigma ^{2}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/361b54ec446151dee56c5b8b6bf172c05fbba8e5)

 

## Approaches

 

[Dimensionality reduction](./Dimensionality_reduction) and [feature selection](./Feature_selection) can decrease variance by simplifying models. Similarly, a larger training set tends to decrease variance. Adding features (predictors) tends to decrease bias, at the expense of introducing additional variance. Learning algorithms typically have some tunable parameters that control bias and variance; for example,

 
- [linear](./Linear_model) and [Generalized linear](./Generalized_linear_model) models can be [regularized](./Regularization_(mathematics)) to decrease their variance at the cost of increasing their bias.[[11]](./Bias–variance_tradeoff#cite_note-11)
- In [artificial neural networks](./Artificial_neural_network), the variance increases and the bias decreases as the number of hidden units increase,[[12]](./Bias–variance_tradeoff#cite_note-geman-12) although this classical assumption has been the subject of recent debate.[[4]](./Bias–variance_tradeoff#cite_note-neal2018-4) Like in GLMs, regularization is typically applied.
- In [*k*-nearest neighbor](./K-nearest_neighbor) models, a high value of k leads to high bias and low variance (see below).
- In [instance-based learning](./Instance-based_learning), regularization can be achieved varying the mixture of [prototypes](./Prototype) and exemplars.[[13]](./Bias–variance_tradeoff#cite_note-13)
- In [decision trees](./Decision_tree), the depth of the tree determines the variance. Decision trees are commonly pruned to control variance.[[7]](./Bias–variance_tradeoff#cite_note-islr-7): 307 

 

One way of resolving the trade-off is to use [mixture models](./Mixture_models) and [ensemble learning](./Ensemble_learning).[[14]](./Bias–variance_tradeoff#cite_note-14)[[15]](./Bias–variance_tradeoff#cite_note-15) For example, [boosting](./Boosting_(machine_learning)) combines many "weak" (high bias) models in an ensemble that has lower bias than the individual models, while [bagging](./Bootstrap_aggregating) combines "strong" learners in a way that reduces their variance.

 

[Model validation](./Model_validation) methods such as [cross-validation (statistics)](./Cross-validation_(statistics)) can be used to tune models so as to optimize the trade-off.

 

### *k*-nearest neighbors

 

In the case of [k-nearest neighbors regression](./K-nearest_neighbors_algorithm), when the expectation is taken over the possible labeling of a fixed training set, a [closed-form expression](./Closed-form_expression) exists that relates the bias–variance decomposition to the parameter k:[[8]](./Bias–variance_tradeoff#cite_note-ESL-8): 37, 223 

 

      E   ⁡ ⁡   [    (  y − −     f ^ ^      ( x )  )   2   ∣ ∣  X = x  ]  =   (  f ( x ) − −    1 k    ∑ ∑   i = 1   k   f (  N  i   ( x ) )  )   2   +    σ σ   2   k   +  σ σ   2     {\displaystyle \operatorname {\mathbb {E} } \left[\left(y-{\hat {f}}\!(x)\right)^{2}\mid X=x\right]=\left(f(x)-{\frac {1}{k}}\sum _{i=1}^{k}f(N_{i}(x))\right)^{2}+{\frac {\sigma ^{2}}{k}}+\sigma ^{2}}  ![{\displaystyle \operatorname {\mathbb {E} } \left[\left(y-{\hat {f}}\!(x)\right)^{2}\mid X=x\right]=\left(f(x)-{\frac {1}{k}}\sum _{i=1}^{k}f(N_{i}(x))\right)^{2}+{\frac {\sigma ^{2}}{k}}+\sigma ^{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/bef3ed7bc5663b2bf008a179f54d61e68a01b012)

 

where      N  1   ( x ) , … …  ,  N  k   ( x )   {\displaystyle N_{1}(x),\dots ,N_{k}(x)}  ![{\displaystyle N_{1}(x),\dots ,N_{k}(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5835207a9f81fe493e2b77a4a3ab0ca773e4fc50) are the k nearest neighbors of x in the training set. The bias (first term) is a monotone rising function of k, while the variance (second term) drops off as k is increased. In fact, under "reasonable assumptions" the bias of the first-nearest neighbor (1-NN) estimator vanishes entirely as the size of the training set approaches infinity.[[12]](./Bias–variance_tradeoff#cite_note-geman-12)

 

## Applications

 

### In regression

 

The bias–variance decomposition forms the conceptual basis for regression [regularization](./Regularization_(mathematics)) methods such as [LASSO](./Lasso_(statistics)) and [ridge regression](./Ridge_regression). Regularization methods introduce bias into the regression solution that can reduce variance considerably relative to the [ordinary least squares (OLS)](./Ordinary_least_squares) solution. Although the OLS solution provides non-biased regression estimates, the lower variance solutions produced by regularization techniques provide superior MSE performance.

 

### In classification

 

The bias–variance decomposition was originally formulated for least-squares regression. For the case of [classification](./Statistical_classification) under the [0-1 loss](./0-1_loss) (misclassification rate), it is possible to find a similar decomposition, with the caveat that the variance term becomes dependent on the target label.[[16]](./Bias–variance_tradeoff#cite_note-16)[[17]](./Bias–variance_tradeoff#cite_note-17) Alternatively, if the classification problem can be phrased as [probabilistic classification](./Probabilistic_classification), then the expected cross-entropy can instead be decomposed to give bias and variance terms with the same semantics but taking a different form.

 

It has been argued that as training data increases, the variance of learned models will tend to decrease, and hence that as training data quantity increases, error is minimised by methods that learn models with lesser bias, and that conversely, for smaller training data quantities it is ever more important to minimise variance.[[18]](./Bias–variance_tradeoff#cite_note-18)

 

### In reinforcement learning

 

Even though the bias–variance decomposition does not directly apply in [reinforcement learning](./Reinforcement_learning), a similar tradeoff can also characterize generalization. When an agent has limited information on its environment, the suboptimality of an RL algorithm can be decomposed into the sum of two terms: a term related to an asymptotic bias and a term due to overfitting. The asymptotic bias is directly related to the learning algorithm (independently of the quantity of data) while the overfitting term comes from the fact that the amount of data is limited.[[19]](./Bias–variance_tradeoff#cite_note-19)

 

### In Monte Carlo methods

 

While in traditional Monte Carlo methods the bias is typically zero, modern approaches, such as [Markov chain Monte Carlo](./Markov_chain_Monte_Carlo) are only asymptotically unbiased, at best.[[20]](./Bias–variance_tradeoff#cite_note-20) Convergence diagnostics can be used to control bias via [burn-in](./Burn-in) removal, but due to a limited computational budget, a bias–variance trade-off arises,[[21]](./Bias–variance_tradeoff#cite_note-21) leading to a wide range of approaches, in which a controlled bias is accepted, if this allows to dramatically reduce the variance, and hence the overall estimation error.[[22]](./Bias–variance_tradeoff#cite_note-22)[[23]](./Bias–variance_tradeoff#cite_note-23)[[24]](./Bias–variance_tradeoff#cite_note-24)

 

### In human learning

 

While widely discussed in the context of machine learning, the bias–variance dilemma has been examined in the context of [human cognition](./Cognitive_science), most notably by [Gerd Gigerenzer](./Gerd_Gigerenzer) and co-workers in the context of learned heuristics. They have argued (see references below) that the human brain resolves the dilemma in the case of the typically sparse, poorly-characterized training-sets provided by experience by adopting high-bias/low variance heuristics. This reflects the fact that a zero-bias approach has poor generalizability to new situations, and also unreasonably presumes precise knowledge of the true state of the world. The resulting heuristics are relatively simple, but produce better inferences in a wider variety of situations.[[25]](./Bias–variance_tradeoff#cite_note-ReferenceA-25)

 

[Geman](./Stuart_Geman) et al.[[12]](./Bias–variance_tradeoff#cite_note-geman-12) argue that the bias–variance dilemma implies that abilities such as generic [object recognition](./Object_recognition) cannot be learned from scratch, but require a certain degree of "hard wiring" that is later tuned by experience. This is because model-free approaches to inference require impractically large training sets if they are to avoid high variance.

 

## See also

  
- [Accuracy and precision](./Accuracy_and_precision)
- [Bias of an estimator](./Bias_of_an_estimator)
- [Double descent](./Double_descent)
- [Gauss–Markov theorem](./Gauss–Markov_theorem)
- [Hyperparameter optimization](./Hyperparameter_optimization)
- [Law of total variance](./Law_of_total_variance)
- [Minimum-variance unbiased estimator](./Minimum-variance_unbiased_estimator)
- [Model selection](./Model_selection)
- [Regression model validation](./Regression_model_validation)
- [Supervised learning](./Supervised_learning)
- [Cramér–Rao bound](./Cramér–Rao_bound)
- [Prediction interval](./Prediction_interval)

  

## References

  
1. [↑](./Bias–variance_tradeoff#cite_ref-:0_1-0) Kohavi, Ron; Wolpert, David H. (1996). "Bias Plus Variance Decomposition for Zero-One Loss Functions". *ICML*. **96**.
2. [↑](./Bias–variance_tradeoff#cite_ref-:1_2-0) Luxburg, Ulrike V.; Schölkopf, B. (2011). "Statistical learning theory: Models, concepts, and results". *Handbook of the History of Logic*. **10**: Section 2.4.
3. [↑](./Bias–variance_tradeoff#cite_ref-nealThesis2019_3-0) Neal, Brady (2019). "On the Bias–Variance Tradeoff: Textbooks Need an Update". [arXiv](./ArXiv_(identifier)):[1912.08286](https://arxiv.org/abs/1912.08286) [[cs.LG](https://arxiv.org/archive/cs.LG)].
4. [1](./Bias–variance_tradeoff#cite_ref-neal2018_4-0) [2](./Bias–variance_tradeoff#cite_ref-neal2018_4-1) Neal, Brady; Mittal, Sarthak; Baratin, Aristide; Tantia, Vinayak; Scicluna, Matthew; Lacoste-Julien, Simon; Mitliagkas, Ioannis (2018). "A Modern Take on the Bias–Variance Tradeoff in Neural Networks". [arXiv](./ArXiv_(identifier)):[1810.08591](https://arxiv.org/abs/1810.08591) [[cs.LG](https://arxiv.org/archive/cs.LG)].
5. [↑](./Bias–variance_tradeoff#cite_ref-5) Neal, Brady; Mittal, Sarthak; Baratin, Aristide; Tantia, Vinayak; Scicluna, Matthew; Lacoste-Julien, Simon; Mitliagkas, Ioannis (2019). [*A Modern Take on the Bias–Variance Tradeoff in Neural Networks*](https://openreview.net/forum?id=HkgmzhC5F7). International Conference on Learning Representations (ICLR) 2019.
6. [↑](./Bias–variance_tradeoff#cite_ref-6) Vapnik, Vladimir (2000). [*The nature of statistical learning theory*](https://dx.doi.org/10.1007/978-1-4757-3264-1). New York: Springer-Verlag. [doi](./Doi_(identifier)):[10.1007/978-1-4757-3264-1](https://doi.org/10.1007%2F978-1-4757-3264-1). [ISBN](./ISBN_(identifier)) [978-1-4757-3264-1](./Special:BookSources/978-1-4757-3264-1). [S2CID](./S2CID_(identifier)) [7138354](https://api.semanticscholar.org/CorpusID:7138354).
7. [1](./Bias–variance_tradeoff#cite_ref-islr_7-0) [2](./Bias–variance_tradeoff#cite_ref-islr_7-1) [3](./Bias–variance_tradeoff#cite_ref-islr_7-2) James, Gareth; [Witten, Daniela](./Daniela_Witten); [Hastie, Trevor](./Trevor_Hastie); [Tibshirani, Robert](./Robert_Tibshirani) (2013). [*An Introduction to Statistical Learning*](http://www-bcf.usc.edu/~gareth/ISL/). Springer.
8. [1](./Bias–variance_tradeoff#cite_ref-ESL_8-0) [2](./Bias–variance_tradeoff#cite_ref-ESL_8-1) Hastie, Trevor; Tibshirani, Robert; [Friedman, Jerome H.](./Jerome_H._Friedman) (2009). [*The Elements of Statistical Learning*](https://web.archive.org/web/20150126123924/http://statweb.stanford.edu/~tibs/ElemStatLearn/). Archived from [the original](http://statweb.stanford.edu/~tibs/ElemStatLearn/) on 2015-01-26. Retrieved 2014-08-20.
9. [↑](./Bias–variance_tradeoff#cite_ref-9) [Vijayakumar, Sethu](./Sethu_Vijayakumar) (2007). ["The Bias–Variance Tradeoff"](http://www.inf.ed.ac.uk/teaching/courses/mlsc/Notes/Lecture4/BiasVariance.pdf) (PDF). [University of Edinburgh](./University_of_Edinburgh). Retrieved 19 August 2014.
10. [↑](./Bias–variance_tradeoff#cite_ref-10) Shakhnarovich, Greg (2011). ["Notes on derivation of bias–variance decomposition in linear regression"](https://web.archive.org/web/20140821063842/http://ttic.uchicago.edu/~gregory/courses/wis-ml2012/lectures/biasVarDecom.pdf) (PDF). Archived from [the original](http://ttic.uchicago.edu/~gregory/courses/wis-ml2012/lectures/biasVarDecom.pdf) (PDF) on 21 August 2014. Retrieved 20 August 2014.
11. [↑](./Bias–variance_tradeoff#cite_ref-11) Belsley, David (1991). *Conditioning diagnostics : collinearity and weak data in regression*. New York (NY): Wiley. [ISBN](./ISBN_(identifier)) [978-0471528890](./Special:BookSources/978-0471528890).
12. [1](./Bias–variance_tradeoff#cite_ref-geman_12-0) [2](./Bias–variance_tradeoff#cite_ref-geman_12-1) [3](./Bias–variance_tradeoff#cite_ref-geman_12-2) [Geman, Stuart](./Stuart_Geman); Bienenstock, Élie; Doursat, René (1992). ["Neural networks and the bias/variance dilemma"](http://web.mit.edu/6.435/www/Geman92.pdf) (PDF). *Neural Computation*. **4**: 1–58. [doi](./Doi_(identifier)):[10.1162/neco.1992.4.1.1](https://doi.org/10.1162%2Fneco.1992.4.1.1). [S2CID](./S2CID_(identifier)) [14215320](https://api.semanticscholar.org/CorpusID:14215320).
13. [↑](./Bias–variance_tradeoff#cite_ref-13) Gagliardi, Francesco (May 2011). ["Instance-based classifiers applied to medical databases: diagnosis and knowledge extraction"](https://www.researchgate.net/publication/51173579). *Artificial Intelligence in Medicine*. **52** (3): 123–139. [doi](./Doi_(identifier)):[10.1016/j.artmed.2011.04.002](https://doi.org/10.1016%2Fj.artmed.2011.04.002). [PMID](./PMID_(identifier)) [21621400](https://pubmed.ncbi.nlm.nih.gov/21621400).
14. [↑](./Bias–variance_tradeoff#cite_ref-14) Ting, Jo-Anne; Vijaykumar, Sethu; Schaal, Stefan (2011). "Locally Weighted Regression for Control". In Sammut, Claude; Webb, Geoffrey I. (eds.). [*Encyclopedia of Machine Learning*](http://homepages.inf.ed.ac.uk/svijayak/publications/ting-EMLDM2016.pdf) (PDF). Springer. p. 615. [Bibcode](./Bibcode_(identifier)):[2010eoml.book.....S](https://ui.adsabs.harvard.edu/abs/2010eoml.book.....S).
15. [↑](./Bias–variance_tradeoff#cite_ref-15) Fortmann-Roe, Scott (2012). ["Understanding the Bias–Variance Tradeoff"](http://scott.fortmann-roe.com/docs/BiasVariance.html).
16. [↑](./Bias–variance_tradeoff#cite_ref-16) [Domingos, Pedro](./Pedro_Domingos) (2000). [*A unified bias–variance decomposition*](http://homes.cs.washington.edu/~pedrod/bvd.pdf) (PDF). ICML.
17. [↑](./Bias–variance_tradeoff#cite_ref-17) Valentini, Giorgio; [Dietterich, Thomas G.](./Thomas_G._Dietterich) (2004). ["Bias–variance analysis of support vector machines for the development of SVM-based ensemble methods"](http://www.jmlr.org/papers/volume5/valentini04a/valentini04a.pdf) (PDF). *[Journal of Machine Learning Research](./Journal_of_Machine_Learning_Research)*. **5**: 725–775.
18. [↑](./Bias–variance_tradeoff#cite_ref-18) Brain, Damian; [Webb, Geoffrey](./Geoff_Webb) (2002). [*The Need for Low Bias Algorithms in Classification Learning From Large Data Sets*](http://i.giwebb.com/wp-content/papercite-data/pdf/brainwebb02.pdf) (PDF). Proceedings of the Sixth European Conference on Principles of Data Mining and Knowledge Discovery (PKDD 2002).
19. [↑](./Bias–variance_tradeoff#cite_ref-19) Francois-Lavet, Vincent; Rabusseau, Guillaume; Pineau, Joelle; Ernst, Damien; Fonteneau, Raphael (2019). ["On Overfitting and Asymptotic Bias in Batch Reinforcement Learning with Partial Observability"](https://jair.org/index.php/jair/article/view/11478). *Journal of Artificial Intelligence Research*. **65**: 1–30. [arXiv](./ArXiv_(identifier)):[1709.07796](https://arxiv.org/abs/1709.07796). [doi](./Doi_(identifier)):[10.1613/jair.1.11478](https://doi.org/10.1613%2Fjair.1.11478).
20. [↑](./Bias–variance_tradeoff#cite_ref-20) Zlochin, M.; Baram, Y. (2001). ["The Bias–Variance Dilemma of the Monte Carlo Method"](https://doi.org/10.1007/3-540-44668-0_20). In Dorffner, G.; Bischof, H.; Hornik, K. (eds.). *Artificial Neural Networks — ICANN 2001*. Lecture Notes in Computer Science. Vol. 2130. Springer. pp. 257–264. [doi](./Doi_(identifier)):[10.1007/3-540-44668-0_20](https://doi.org/10.1007%2F3-540-44668-0_20). Retrieved 17 November 2024.
21. [↑](./Bias–variance_tradeoff#cite_ref-21) South, Leah F.; Riabiz, Marina; Teymur, Onur; Oates, Chris J. (March 1, 2022). ["Postprocessing of MCMC"](https://ssrn.com/abstract=4065369). *Annual Review of Statistics and Its Application*. **9** (1): 529–555. [arXiv](./ArXiv_(identifier)):[2103.16048](https://arxiv.org/abs/2103.16048). [Bibcode](./Bibcode_(identifier)):[2022AnRSA...9..529S](https://ui.adsabs.harvard.edu/abs/2022AnRSA...9..529S). [doi](./Doi_(identifier)):[10.1146/annurev-statistics-040220-091727](https://doi.org/10.1146%2Fannurev-statistics-040220-091727). [PMC](./PMC_(identifier)) [7616193](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7616193). [PMID](./PMID_(identifier)) [39006247](https://pubmed.ncbi.nlm.nih.gov/39006247). Retrieved 17 November 2024.
22. [↑](./Bias–variance_tradeoff#cite_ref-22) Nemeth, C.; Fearnhead, P. (2021). ["Stochastic Gradient Markov Chain Monte Carlo"](https://doi.org/10.1080/01621459.2020.1847120). *Journal of the American Statistical Association*. **116** (533): 433–450. [arXiv](./ArXiv_(identifier)):[1907.06986](https://arxiv.org/abs/1907.06986). [doi](./Doi_(identifier)):[10.1080/01621459.2020.1847120](https://doi.org/10.1080%2F01621459.2020.1847120). Retrieved 17 November 2024.
23. [↑](./Bias–variance_tradeoff#cite_ref-23) Vazquez, M.A.; Míguez, J. (2017). ["Importance sampling with transformed weights"](https://doi.org/10.1049/el.2016.3462). *Electronics Letters*. **53** (12): 783–785. [arXiv](./ArXiv_(identifier)):[1702.01987](https://arxiv.org/abs/1702.01987). [Bibcode](./Bibcode_(identifier)):[2017ElL....53..783V](https://ui.adsabs.harvard.edu/abs/2017ElL....53..783V). [doi](./Doi_(identifier)):[10.1049/el.2016.3462](https://doi.org/10.1049%2Fel.2016.3462). Retrieved 17 November 2024.
24. [↑](./Bias–variance_tradeoff#cite_ref-24) Korba, A.; Portier, F. (2022). ["Adaptive Importance Sampling meets Mirror Descent: A Bias–Variance Tradeoff"](https://proceedings.mlr.press/v151/korba22a.html). *Proceedings of The 25th International Conference on Artificial Intelligence and Statistics*. Proceedings of Machine Learning Research. Vol. 151. pp. 11503–11527. Retrieved 17 November 2024.
25. [↑](./Bias–variance_tradeoff#cite_ref-ReferenceA_25-0) [Gigerenzer, Gerd](./Gerd_Gigerenzer); Brighton, Henry (2009). "Homo Heuristicus: Why Biased Minds Make Better Inferences". *Topics in Cognitive Science*. **1** (1): 107–143. [doi](./Doi_(identifier)):[10.1111/j.1756-8765.2008.01006.x](https://doi.org/10.1111%2Fj.1756-8765.2008.01006.x). [hdl](./Hdl_(identifier)):[11858/00-001M-0000-0024-F678-0](https://hdl.handle.net/11858%2F00-001M-0000-0024-F678-0). [PMID](./PMID_(identifier)) [25164802](https://pubmed.ncbi.nlm.nih.gov/25164802).

 

## External links

 
- [MLU-Explain: The Bias Variance Tradeoff](https://mlu-explain.github.io/bias-variance/) — An interactive visualization of the bias–variance tradeoff in LOESS Regression and K-Nearest Neighbors.

 
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