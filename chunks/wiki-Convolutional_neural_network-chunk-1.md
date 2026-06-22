---
source: sources/wiki-Convolutional_neural_network.md
source_url: https://en.wikipedia.org/wiki/Convolutional_neural_network
chunk: 1/8
---

Type of feedforward neural network 
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

 

A **convolutional neural network** (**CNN**) is a type of [feedforward neural network](./Feedforward_neural_network) that learns [features](./Feature_engineering) via filter (or [kernel](./Kernel_(image_processing))) optimization. This type of [deep learning](./Deep_learning) network has been applied to process and make [predictions](./Prediction#Statistics) from many different types of data including text, images and audio.[[1]](./Convolutional_neural_network#cite_note-LeCun2015-1) CNNs are the de-facto standard in deep learning-based approaches to [computer vision](./Computer_vision)[[2]](./Convolutional_neural_network#cite_note-2) and [image processing](./Image_processing), and have only recently been replaced—in some cases—by newer architectures such as the [transformer](./Transformer_(deep_learning)).

 

[Vanishing gradients](./Vanishing_gradient_problem) and exploding gradients, seen during [backpropagation](./Backpropagation) in earlier neural networks, are prevented by the [regularization](./Regularization_(mathematics)) that comes from using shared weights over fewer connections.[[3]](./Convolutional_neural_network#cite_note-auto3-3)[[4]](./Convolutional_neural_network#cite_note-auto2-4) For example, for *each* neuron in the fully-connected layer, 10,000 weights would be required for processing an image sized 100 × 100 pixels. However, applying cascaded *convolution* (or cross-correlation) kernels,[[5]](./Convolutional_neural_network#cite_note-5)[[6]](./Convolutional_neural_network#cite_note-6) only 25 weights for each convolutional layer are required to process 5x5-sized tiles.[[7]](./Convolutional_neural_network#cite_note-auto1-7)[[8]](./Convolutional_neural_network#cite_note-homma-8) Higher-layer features are extracted from wider context windows, compared to lower-layer features.

 

Some applications of CNNs include: 

 
- [image and video recognition](./Computer_vision),[[9]](./Convolutional_neural_network#cite_note-Valueva_Nagornov_Lyakhov_Valuev_2020_pp._232–243-9)
- [recommender systems](./Recommender_system),[[10]](./Convolutional_neural_network#cite_note-10)
- [image classification](./Image_classification),
- [image segmentation](./Image_segmentation),
- [medical image analysis](./Medical_image_computing),
- [natural language processing](./Natural_language_processing),[[11]](./Convolutional_neural_network#cite_note-11)
- [brain–computer interfaces](./Brain–computer_interface),[[12]](./Convolutional_neural_network#cite_note-12) and
- financial [time series](./Time_series).[[13]](./Convolutional_neural_network#cite_note-Tsantekidis_7–12-13)

 

CNNs are also known as **shift invariant** or **space invariant artificial neural networks**, based on the shared-weight architecture of the [convolution](./Convolution) kernels or filters that slide along input features and provide translation-[equivariant](./Equivariant_map) responses known as feature maps.[[14]](./Convolutional_neural_network#cite_note-:0-14)[[15]](./Convolutional_neural_network#cite_note-:1-15) Counter-intuitively, most convolutional neural networks are not [invariant to translation](./Translation_invariant), due to the downsampling operation they apply to the input.[[16]](./Convolutional_neural_network#cite_note-:6-16)

 

[Feedforward neural networks](./Feedforward_neural_network) are usually fully connected networks, that is, each neuron in one [layer](./Layer_(deep_learning)) is connected to all neurons in the next [layer](./Layer_(deep_learning)). The "full connectivity" of these networks makes them prone to [overfitting](./Overfitting) data. Typical ways of regularization, or preventing overfitting, include: penalizing parameters during training (such as weight decay) or trimming connectivity (skipped connections, dropout, etc.) Robust datasets also increase the probability that CNNs will learn the generalized principles that characterize a given dataset rather than the biases of a poorly-populated set.[[17]](./Convolutional_neural_network#cite_note-17)

 

Convolutional networks were [inspired](./Mathematical_biology) by [biological](./Biological) processes[[18]](./Convolutional_neural_network#cite_note-fukuneoscholar-18)[[19]](./Convolutional_neural_network#cite_note-hubelwiesel1968-19)[[20]](./Convolutional_neural_network#cite_note-intro-20)[[21]](./Convolutional_neural_network#cite_note-robust_face_detection-21) in that the connectivity pattern between [neurons](./Artificial_neuron) resembles the organization of the animal [visual cortex](./Visual_cortex). Individual [cortical neurons](./Cortical_neuron) respond to stimuli only in a restricted region of the [visual field](./Visual_field) known as the [receptive field](./Receptive_field). The receptive fields of different neurons partially overlap such that they cover the entire visual field.

 

CNNs use relatively little pre-processing compared to other [image classification algorithms](./Image_classification). This means that the network learns to optimize the filters (or kernels) through automated learning, whereas in traditional algorithms these filters are [hand-engineered](./Feature_engineering). This simplifies and automates the process, enhancing efficiency and scalability overcoming human-intervention bottlenecks.

  

## Architecture

 Main article: [Layer (deep learning)](./Layer_(deep_learning)) [![](//upload.wikimedia.org/wikipedia/commons/thumb/c/cc/Comparison_image_neural_networks.svg/500px-Comparison_image_neural_networks.svg.png)](./File:Comparison_image_neural_networks.svg)Comparison of the [LeNet](./LeNet) (1995) and [AlexNet](./AlexNet) (2012) convolution, pooling and dense layers
 

A convolutional neural network consists of an input layer, [hidden layers](./Artificial_neural_network#Organization) and an output layer. In a convolutional neural network, the hidden layers include one or more layers that perform convolutions. Typically this includes a layer that performs a [dot product](./Dot_product) of the convolution kernel with the layer's input matrix. This product is usually the [Frobenius inner product](./Frobenius_inner_product), and its activation function is commonly [ReLU](./Rectifier_(neural_networks)). As the convolution kernel slides along the input matrix for the layer, the convolution operation generates a feature map, which in turn contributes to the input of the next layer. This is followed by other layers such as [pooling layers](./Pooling_layer), fully connected layers, and normalization layers.
Here it should be noted how close a convolutional neural network is to a [matched filter](./Matched_filter).[[22]](./Convolutional_neural_network#cite_note-22)

 

### Convolutional layers

 

In a CNN, the input is a [tensor](./Tensor_(machine_learning)) with shape:

 

(number of inputs) × (input height) × (input width) × (input [channels](./Channel_(digital_image)))

 

After passing through a convolutional layer, the image becomes abstracted to a feature map, also called an activation map, with shape:

 

(number of inputs) × (feature map height) × (feature map width) × (feature map [channels](./Channel_(digital_image))).

 

Convolutional layers convolve the input and pass its result to the next layer. This is similar to the response of a neuron in the visual cortex to a specific stimulus.[[23]](./Convolutional_neural_network#cite_note-deeplearning-23) Each convolutional neuron processes data only for its [receptive field](./Receptive_field). 

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/3/31/1D_Convolutional_Neural_Network_feed_forward_example.png/250px-1D_Convolutional_Neural_Network_feed_forward_example.png)](./File:1D_Convolutional_Neural_Network_feed_forward_example.png)1D convolutional neural network feed forward example 

Although [fully connected feedforward neural networks](./Multilayer_perceptron) can be used to learn features and classify data, this architecture is generally impractical for larger inputs (e.g., high-resolution images), which would require massive numbers of neurons because each pixel is a relevant input feature. A fully connected layer for an image of size 100 × 100 has 10,000 weights for *each* neuron in the second layer. Convolution reduces the number of free parameters, allowing the network to be deeper.[[7]](./Convolutional_neural_network#cite_note-auto1-7) For example, using a 5 × 5 tiling region, each with the same shared weights, requires only 25 neurons. Using shared weights means there are many fewer parameters, which helps avoid the vanishing gradients and exploding gradients problems seen during [backpropagation](./Backpropagation) in earlier neural networks.[[3]](./Convolutional_neural_network#cite_note-auto3-3)[[4]](./Convolutional_neural_network#cite_note-auto2-4)

 

To speed processing, standard convolutional layers can be replaced by depthwise separable convolutional layers,[[24]](./Convolutional_neural_network#cite_note-24) which are based on a depthwise convolution followed by a pointwise convolution. The *depthwise convolution* is a spatial convolution applied independently over each channel of the input tensor, while the *pointwise convolution* is a standard convolution restricted to the use of     1 × ×  1   {\displaystyle 1\times 1}  ![{\displaystyle 1\times 1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2b4bf91a527dc01af9ef6ace81199becf1308e00) kernels.

 

### Pooling layers

 

Convolutional networks may include local and/or global pooling layers along with traditional convolutional layers. Pooling layers reduce the dimensions of data by combining the outputs of neuron clusters at one layer into a single neuron in the next layer. Local pooling combines small clusters, tiling sizes such as 2 × 2 are commonly used. Global pooling acts on all the neurons of the feature map.[[25]](./Convolutional_neural_network#cite_note-flexible-25)[[26]](./Convolutional_neural_network#cite_note-26) There are two common types of pooling in popular use: max and average. *Max pooling* uses the maximum value of each local cluster of neurons in the feature map,[[27]](./Convolutional_neural_network#cite_note-Yamaguchi111990-27)[[28]](./Convolutional_neural_network#cite_note-mcdns-28) while *average pooling* takes the average value.

 

### Fully connected layers

 

Fully connected layers connect every neuron in one layer to every neuron in another layer. It is the same as a traditional [multilayer perceptron](./Multilayer_perceptron) neural network (MLP). Each neuron in the fully connected layer receives input from all the neurons in the previous layer. These inputs are weighted and summed with the corresponding biases, and then passed through an activation function to perform a nonlinear transformation, generating the output. The flattened matrix goes through a fully connected layer to classify the images.

 

### Receptive field

 

In neural networks, each neuron receives input from some number of locations in the previous layer. In a convolutional layer, each neuron receives input from only a restricted area of the previous layer called the neuron's *receptive field*. Typically the area is a square (e.g. 5 by 5 neurons). Whereas, in a fully connected layer, the receptive field is the *entire previous layer*. Thus, in each convolutional layer, each neuron takes input from a larger area in the input than previous layers. This is due to applying the convolution over and over, which takes the value of a pixel into account, as well as its surrounding pixels. When using dilated layers, the number of pixels in the receptive field remains constant, but the field is more sparsely populated as its dimensions grow when combining the effect of several layers.

 

To manipulate the receptive field size as desired, there are some alternatives to the standard convolutional layer. For example, atrous or dilated convolution[[29]](./Convolutional_neural_network#cite_note-29)[[30]](./Convolutional_neural_network#cite_note-30) expands the receptive field size without increasing the number of parameters by interleaving visible and blind regions. Moreover, a single dilated convolutional layer can comprise filters with multiple dilation ratios,[[31]](./Convolutional_neural_network#cite_note-31) thus having a variable receptive field size.

 

### Weights

 

Each neuron in a neural network computes an output value by applying a specific function to the input values received from the receptive field in the previous layer. The function that is applied to the input values is determined by a vector of weights and a bias (typically real numbers). Learning consists of iteratively adjusting these biases and weights.

 

The vectors of weights and biases are called *filters* and represent particular [features](./Feature_(machine_learning)) of the input (e.g., a particular shape). A distinguishing feature of CNNs is that many neurons can share the same filter. This reduces the [memory footprint](./Memory_footprint) because a single bias and a single vector of weights are used across all receptive fields that share that filter, as opposed to each receptive field having its own bias and vector weighting.[[32]](./Convolutional_neural_network#cite_note-LeCun-32)

 

### Deconvolutional

 

 

A deconvolutional neural network is essentially the reverse of a CNN. It consists of deconvolutional layers and unpooling layers.[[33]](./Convolutional_neural_network#cite_note-33)

 

A deconvolutional layer is the transpose of a convolutional layer. Specifically, a convolutional layer can be written as a multiplication with a matrix, and a deconvolutional layer is multiplication with the transpose of that matrix.[[34]](./Convolutional_neural_network#cite_note-34)

 

An unpooling layer expands the layer. The max-unpooling layer is the simplest, as it simply copies each entry multiple times. For example, a 2-by-2 max-unpooling layer is     [ x ] ↦ ↦    [    x   x     x   x    ]     {\displaystyle [x]\mapsto {\begin{bmatrix}x&x\\x&x\end{bmatrix}}}  ![{\displaystyle [x]\mapsto {\begin{bmatrix}x&x\\x&x\end{bmatrix}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ba907f707b81817e69c003905058b928e9097b86).

 

Deconvolution layers are used in image generators. By default, it creates periodic checkerboard artifact, which can be fixed by upscale-then-convolve.[[35]](./Convolutional_neural_network#cite_note-35)

 


