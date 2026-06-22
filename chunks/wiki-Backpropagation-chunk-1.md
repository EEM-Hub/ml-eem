---
source: sources/wiki-Backpropagation.md
source_url: https://en.wikipedia.org/wiki/Backpropagation
chunk: 1/8
---

Optimization algorithm for artificial neural networks This article is about the computer algorithm. For the biological process, see [Neural backpropagation](./Neural_backpropagation). Backpropagation can also refer to the way the result of a playout is propagated up the search tree in [Monte Carlo tree search](./Monte_Carlo_tree_search#Principle_of_operation). 
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

 

In [machine learning](./Machine_learning), **backpropagation** is a [gradient](./Gradient) computation method commonly used for training a [neural network](./Neural_network_(machine_learning)) in computing parameter updates.

 

It is an efficient application of the [chain rule](./Chain_rule) to neural networks. Backpropagation efficiently computes the gradient of the loss with respect to the network weights for a single input–output example. It does this by propagating derivatives backward, one layer at a time, from the output layer to the input layer, thereby avoiding redundant chain-rule calculations.

 

Strictly speaking, the term *backpropagation* refers only to an algorithm for efficiently computing the gradient, not how the gradient is used, but the term is often used loosely to refer to the entire learning algorithm. This includes changing model parameters in the negative direction of the gradient, such as by [stochastic gradient descent](./Stochastic_gradient_descent), or as an intermediate step in a more complicated optimizer, such as [Adaptive Moment Estimation](./Stochastic_gradient_descent#Adam).[[1]](./Backpropagation#cite_note-1)

 

Backpropagation had multiple discoveries and partial discoveries, with a tangled history and terminology (see [§ History](./Backpropagation#History)). Some other names for the technique include "reverse mode of [automatic differentiation](./Automatic_differentiation)" or "[reverse accumulation](./Reverse_accumulation)".[[2]](./Backpropagation#cite_note-DL-reverse-mode-2)

 

## Overview

 

Backpropagation computes the gradient in [weight space](./Parameter_space) of a feedforward neural network, with respect to a [loss function](./Loss_function). Denote:

 
-     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4): input (vector of features)
-     y   {\displaystyle y}  ![{\displaystyle y}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b8a6208ec717213d4317e666f1ae872e00620a0d): target output
For classification, output will be a vector of class probabilities (e.g.,     ( 0.1 , 0.7 , 0.2 )   {\displaystyle (0.1,0.7,0.2)}  ![{\displaystyle (0.1,0.7,0.2)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fbb2f54392fb76b6dea26425e24447bf2c48cc94), and target output is a specific class, encoded by the [one-hot](./One-hot)/[dummy variable](./Dummy_variable_(statistics)) (e.g.,     ( 0 , 1 , 0 )   {\displaystyle (0,1,0)}  ![{\displaystyle (0,1,0)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3e28bfe8a44d06939011e3ba2159e894c0f22f23)).
-     C   {\displaystyle C}  ![{\displaystyle C}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4fc55753007cd3c18576f7933f6f089196732029): [loss function](./Loss_function) or "cost function"[[a]](./Backpropagation#cite_note-3) For classification, this is usually [cross-entropy](./Cross-entropy) (XC, [log loss](./Log_loss)), while for regression it is usually [squared error loss](./Squared_error_loss) (SEL).
-     L   {\displaystyle L}  ![{\displaystyle L}](https://wikimedia.org/api/rest_v1/media/math/render/svg/103168b86f781fe6e9a4a87b8ea1cebe0ad4ede8): the number of layers
-      W  l   = (  w  j k   l   )   {\displaystyle W^{l}=(w_{jk}^{l})}  ![{\displaystyle W^{l}=(w_{jk}^{l})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6ef80d37cec97e026476841a0e20f9b35c402bd0): the weights between layer     l − −  1   {\displaystyle l-1}  ![{\displaystyle l-1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4e0d448948a353d0b2469b88ca918f34e32c8752) and     l   {\displaystyle l}  ![{\displaystyle l}](https://wikimedia.org/api/rest_v1/media/math/render/svg/829091f745070b9eb97a80244129025440a1cfac), where      w  j k   l     {\displaystyle w_{jk}^{l}}  ![{\displaystyle w_{jk}^{l}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8f47c5a00989f34da7a6cde720321223af36a019) is the weight between the     k   {\displaystyle k}  ![{\displaystyle k}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c3c9a2c7b599b37105512c5d570edc034056dd40)-th node in layer     l − −  1   {\displaystyle l-1}  ![{\displaystyle l-1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4e0d448948a353d0b2469b88ca918f34e32c8752) and the     j   {\displaystyle j}  ![{\displaystyle j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f461e54f5c093e92a55547b9764291390f0b5d0)-th node in layer     l   {\displaystyle l}  ![{\displaystyle l}](https://wikimedia.org/api/rest_v1/media/math/render/svg/829091f745070b9eb97a80244129025440a1cfac)[[b]](./Backpropagation#cite_note-4)
-      f  l     {\displaystyle f^{l}}  ![{\displaystyle f^{l}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ee0e6c373d37a6a029890630310cf35ba6acd174): [activation functions](./Activation_function) at layer     l   {\displaystyle l}  ![{\displaystyle l}](https://wikimedia.org/api/rest_v1/media/math/render/svg/829091f745070b9eb97a80244129025440a1cfac) For classification the last layer is usually the [logistic function](./Logistic_function) for binary classification, and [softmax](./Softmax_function) (softargmax) for multi-class classification, while for the hidden layers this was traditionally a [sigmoid function](./Sigmoid_function) (logistic function or others) on each node (coordinate), but today is more varied, with [rectifier](./Rectifier_(neural_networks)) ([ramp](./Ramp_function), [ReLU](./ReLU)) being common.
-      a  j   l     {\displaystyle a_{j}^{l}}  ![{\displaystyle a_{j}^{l}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fbb8152a0d8674023edebc1a8760c3ef478831d8): activation of the     j   {\displaystyle j}  ![{\displaystyle j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f461e54f5c093e92a55547b9764291390f0b5d0)-th node in layer     l   {\displaystyle l}  ![{\displaystyle l}](https://wikimedia.org/api/rest_v1/media/math/render/svg/829091f745070b9eb97a80244129025440a1cfac).

 

In the derivation of backpropagation, other intermediate quantities are used by introducing them as needed below. Bias terms are not treated specially since they correspond to a weight with a fixed input of 1. For backpropagation the specific loss function and activation functions do not matter as long as they and their derivatives can be evaluated efficiently. Traditional activation functions include [sigmoid](./Sigmoid_function), [tanh](./Tanh), [ReLU](./Rectifier_(neural_networks)), [Swish](./Swish_function),[[3]](./Backpropagation#cite_note-5) [Mish](./Rectifier_(neural_networks)#Mish),[[4]](./Backpropagation#cite_note-6), and many others.

 

The overall network is a combination of [function composition](./Function_composition) and [matrix multiplication](./Matrix_multiplication):

     g ( x ) :=  f  L   (  W  L    f  L − −  1   (  W  L − −  1   ⋯ ⋯   f  1   (  W  1   x ) ⋯ ⋯  ) )   {\displaystyle g(x):=f^{L}(W^{L}f^{L-1}(W^{L-1}\cdots f^{1}(W^{1}x)\cdots ))}  ![{\displaystyle g(x):=f^{L}(W^{L}f^{L-1}(W^{L-1}\cdots f^{1}(W^{1}x)\cdots ))}](https://wikimedia.org/api/rest_v1/media/math/render/svg/110b3c8ee790c91cf79a882f1515f6f05f8db335) 

For a training set there will be a set of input–output pairs,      {  (  x  i   ,  y  i   )  }    {\displaystyle \left\{(x_{i},y_{i})\right\}}  ![{\displaystyle \left\{(x_{i},y_{i})\right\}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/26d74b1e662ee0f0e1604f2e5a63fde1456bb19e). For each input–output pair     (  x  i   ,  y  i   )   {\displaystyle (x_{i},y_{i})}  ![{\displaystyle (x_{i},y_{i})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d6dbb919b91ccacf17ed47898048428a1baf9703) in the training set, the loss of the model on that pair is the cost of the difference between the predicted output     g (  x  i   )   {\displaystyle g(x_{i})}  ![{\displaystyle g(x_{i})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3badcf4ca3e9414821942baee2851b8f9bd27294) and the target output      y  i     {\displaystyle y_{i}}  ![{\displaystyle y_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/67d30d30b6c2dbe4d6f150d699de040937ecc95f):

     C (  y  i   , g (  x  i   ) )   {\displaystyle C(y_{i},g(x_{i}))}  ![{\displaystyle C(y_{i},g(x_{i}))}](https://wikimedia.org/api/rest_v1/media/math/render/svg/57cd91c74155873ce3e1df0fab12d13e7a8f335f) 

Note the distinction: during model evaluation the weights are fixed while the inputs vary (and the target output may be unknown), and the network ends with the output layer (it does not include the loss function). During model training the input–output pair is fixed while the weights vary, and the network ends with the loss function.

 

Backpropagation computes the gradient for a *fixed* input–output pair     (  x  i   ,  y  i   )   {\displaystyle (x_{i},y_{i})}  ![{\displaystyle (x_{i},y_{i})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d6dbb919b91ccacf17ed47898048428a1baf9703), where the weights      w  j k   l     {\displaystyle w_{jk}^{l}}  ![{\displaystyle w_{jk}^{l}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8f47c5a00989f34da7a6cde720321223af36a019) can vary. Each individual component of the gradient,     ∂ ∂  C  /  ∂ ∂   w  j k   l   ,   {\displaystyle \partial C/\partial w_{jk}^{l},}  ![{\displaystyle \partial C/\partial w_{jk}^{l},}](https://wikimedia.org/api/rest_v1/media/math/render/svg/924218a6182ed0f43094ec9f5d8a66c4b9b9026f) can be computed by the chain rule; but doing this separately for each weight is inefficient. Backpropagation efficiently computes the gradient by avoiding duplicate calculations and not computing unnecessary intermediate values, by computing the gradient of each layer – specifically the gradient of the weighted *input* of each layer, denoted by      δ δ   l     {\displaystyle \delta ^{l}}  ![{\displaystyle \delta ^{l}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/249b787ef6af0149f7d71b951651c43633e0d56d) – from back to front.

 

Informally, the key point is that since the only way a weight in      W  l     {\displaystyle W^{l}}  ![{\displaystyle W^{l}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/60b87bc8138a82f110491bb1abd0ea6eefe84c22) affects the loss is through its effect on the *next* layer, and it does so *linearly*,      δ δ   l     {\displaystyle \delta ^{l}}  ![{\displaystyle \delta ^{l}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/249b787ef6af0149f7d71b951651c43633e0d56d) are the only data you need to compute the gradients of the weights at layer     l   {\displaystyle l}  ![{\displaystyle l}](https://wikimedia.org/api/rest_v1/media/math/render/svg/829091f745070b9eb97a80244129025440a1cfac), and then the gradients of weights of previous layer can be computed by      δ δ   l − −  1     {\displaystyle \delta ^{l-1}}  ![{\displaystyle \delta ^{l-1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e4ff3faf90011d3ed813a4ac2fe31904765e2963) and repeated recursively. This avoids inefficiency in two ways. First, it avoids duplication because when computing the gradient at layer     l   {\displaystyle l}  ![{\displaystyle l}](https://wikimedia.org/api/rest_v1/media/math/render/svg/829091f745070b9eb97a80244129025440a1cfac), it is unnecessary to recompute all derivatives on later layers     l + 1 , l + 2 , … …    {\displaystyle l+1,l+2,\ldots }  ![{\displaystyle l+1,l+2,\ldots }](https://wikimedia.org/api/rest_v1/media/math/render/svg/49f721be70a4213a6196f3d14f58eb5844eebb1a) each time. Second, it avoids unnecessary intermediate calculations, because at each stage it directly computes the gradient of the weights with respect to the ultimate output (the loss), rather than unnecessarily computing the derivatives of the values of hidden layers with respect to changes in weights     ∂ ∂   a   j ′     l ′     /  ∂ ∂   w  j k   l     {\displaystyle \partial a_{j'}^{l'}/\partial w_{jk}^{l}}  ![{\displaystyle \partial a_{j'}^{l'}/\partial w_{jk}^{l}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/67e885d69c5968ab173f51222b89d0701b3459d6).

 

Backpropagation can be expressed for simple feedforward networks in terms of [matrix multiplication](./Backpropagation#Matrix_multiplication), or more generally in terms of the [adjoint graph](./Backpropagation#Adjoint_graph).

 


