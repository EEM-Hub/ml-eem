---
source: sources/wiki-Convolutional_neural_network.md
source_url: https://en.wikipedia.org/wiki/Convolutional_neural_network
chunk: 4/8
---

## Hyperparameters

 
|  | This sectionneeds additional citations forverification.Please helpimprove this articlebyadding citations to reliable sourcesin this section. Unsourced material may be challenged and removed.(June 2017)(Learn how and when to remove this message) |
| --- | --- |

 

Hyperparameters are various settings that are used to control the learning process. CNNs use more [hyperparameters](./Hyperparameter_(machine_learning)) than a standard multilayer perceptron (MLP).

 

### Padding

 

Padding is the addition of (typically) 0-valued pixels on the borders of an image. This is done so that the border pixels are not undervalued (lost) from the output because they would ordinarily participate in only a single receptive field instance. The padding applied is typically one less than the corresponding kernel dimension. For example, a convolutional layer using 3x3 kernels would receive a 2-pixel pad, that is 1 pixel on each side of the image.[*[citation needed](./Wikipedia:Citation_needed)*]

 

### Stride

 

The stride is the number of pixels that the analysis window moves on each iteration. A stride of 2 means that each kernel is offset by 2 pixels from its predecessor.

 

### Number of filters

 

Since feature map size decreases with depth, layers near the input layer tend to have fewer filters while higher layers can have more. To equalize computation at each layer, the product of feature values *va* with pixel position is kept roughly constant across layers. Preserving more information about the input would require keeping the total number of activations (number of feature maps times number of pixel positions) non-decreasing from one layer to the next.

 

The number of feature maps directly controls the capacity and depends on the number of available examples and task complexity.

 

### Filter (or kernel) size

 

Common filter sizes found in the literature vary greatly, and are usually chosen based on the data set. Typical filter sizes range from 1x1 to 7x7. As two famous examples, [AlexNet](./AlexNet) used 3x3, 5x5, and 11x11. [Inceptionv3](./Inceptionv3) used 1x1, 3x3, and 5x5.

 

The challenge is to find the right level of granularity so as to create abstractions at the proper scale, given a particular data set, and without [overfitting](./Overfitting).

 

### Pooling type and size

 

[Max pooling](./Max_pooling) is typically used, often with a 2x2 dimension. This implies that the input is drastically [downsampled](./Downsampling_(signal_processing)), reducing processing cost.

 

Greater pooling [reduces the dimension](./Dimensionality_reduction) of the signal, and may result in unacceptable [information loss](./Data_loss). Often, non-overlapping pooling windows perform best.[[78]](./Convolutional_neural_network#cite_note-Scherer-ICANN-2010-80)

 

### Dilation

 

Dilation involves ignoring pixels within a kernel. This reduces processing memory potentially without significant signal loss. A dilation of 2 on a 3x3 kernel expands the kernel to 5x5, while still processing 9 (evenly spaced) pixels. Specifically, the processed pixels after the dilation are the cells (1,1), (1,3), (1,5), (3,1), (3,3), (3,5), (5,1), (5,3), (5,5), where (i,j) denotes the cell of the i-th row and j-th column in the expanded 5x5 kernel. Accordingly, dilation of 4 expands the kernel to 7x7.[*[citation needed](./Wikipedia:Citation_needed)*]

 

## Translation equivariance and aliasing

 

It is commonly assumed that CNNs are invariant to shifts of the input. Convolution or pooling layers within a CNN that do not have a stride greater than one are indeed [equivariant](./Equivariant_map) to translations of the input.[[73]](./Convolutional_neural_network#cite_note-:5-73) However, layers with a stride greater than one ignore the [Nyquist–Shannon sampling theorem](./Nyquist–Shannon_sampling_theorem) and might lead to [aliasing](./Aliasing) of the input signal[[73]](./Convolutional_neural_network#cite_note-:5-73) While, in principle, CNNs are capable of implementing anti-aliasing filters, it has been observed that this does not happen in practice,[[88]](./Convolutional_neural_network#cite_note-91) and therefore yield models that are not equivariant to translations.

 

Furthermore, if a CNN makes use of fully connected layers, translation equivariance does not imply translation invariance, as the fully connected layers are not invariant to shifts of the input.[[89]](./Convolutional_neural_network#cite_note-92)[[16]](./Convolutional_neural_network#cite_note-:6-16) One solution for complete translation invariance is avoiding any down-sampling throughout the network and applying global average pooling at the last layer.[[73]](./Convolutional_neural_network#cite_note-:5-73) Additionally, several other partial solutions have been proposed, such as [anti-aliasing](./Anti-aliasing_filter) before downsampling operations,[[90]](./Convolutional_neural_network#cite_note-93) spatial transformer networks,[[91]](./Convolutional_neural_network#cite_note-94) [data augmentation](./Data_augmentation), subsampling combined with pooling,[[16]](./Convolutional_neural_network#cite_note-:6-16) and [capsule neural networks](./Capsule_neural_network).[[92]](./Convolutional_neural_network#cite_note-95)

 

## Evaluation

 

The accuracy of the final model is typically estimated on a sub-part of the dataset set apart at the start, often called a test set. Alternatively, methods such as [*k*-fold cross-validation](./Cross-validation_(statistics)) are applied. Other strategies include using [conformal prediction](./Conformal_prediction).[[93]](./Convolutional_neural_network#cite_note-96)[[94]](./Convolutional_neural_network#cite_note-97)

 

## Regularization methods

 Main article: [Regularization (mathematics)](./Regularization_(mathematics)) 
|  | This sectionneeds additional citations forverification.Please helpimprove this articlebyadding citations to reliable sourcesin this section. Unsourced material may be challenged and removed.(June 2017)(Learn how and when to remove this message) |
| --- | --- |

 

[Regularization](./Regularization_(mathematics)) is a process of introducing additional information to solve an [ill-posed problem](./Ill-posed_problem) or to prevent [overfitting](./Overfitting). CNNs use various types of regularization.

 

### Empirical

 

#### Dropout

 

Because networks have so many parameters, they are prone to overfitting. One method to reduce overfitting is [dropout](./Dropout_(neural_networks)), introduced in 2014.[[95]](./Convolutional_neural_network#cite_note-98) At each training stage, individual nodes are either "dropped out" of the net (ignored) with probability     1 − −  p   {\displaystyle 1-p}  ![{\displaystyle 1-p}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9633a8692121eedfa99cace406205e5d1511ef8d) or kept with probability     p   {\displaystyle p}  ![{\displaystyle p}](https://wikimedia.org/api/rest_v1/media/math/render/svg/81eac1e205430d1f40810df36a0edffdc367af36), so that a reduced network is left; incoming and outgoing edges to a dropped-out node are also removed. Only the reduced network is trained on the data in that stage. The removed nodes are then reinserted into the network with their original weights.

 

In the training stages,     p   {\displaystyle p}  ![{\displaystyle p}](https://wikimedia.org/api/rest_v1/media/math/render/svg/81eac1e205430d1f40810df36a0edffdc367af36) is usually 0.5; for input nodes, it is typically much higher because information is directly lost when input nodes are ignored.

 

At testing time after training has finished, we would ideally like to find a sample average of all possible      2  n     {\displaystyle 2^{n}}  ![{\displaystyle 2^{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8226f30650ee4fe4e640c6d2798127e80e9c160d) dropped-out networks; unfortunately this is unfeasible for large values of     n   {\displaystyle n}  ![{\displaystyle n}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a601995d55609f2d9f5e233e36fbe9ea26011b3b). However, we can find an approximation by using the full network with each node's output weighted by a factor of     p   {\displaystyle p}  ![{\displaystyle p}](https://wikimedia.org/api/rest_v1/media/math/render/svg/81eac1e205430d1f40810df36a0edffdc367af36), so the [expected value](./Expected_value) of the output of any node is the same as in the training stages. This is the biggest contribution of the dropout method: although it effectively generates      2  n     {\displaystyle 2^{n}}  ![{\displaystyle 2^{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8226f30650ee4fe4e640c6d2798127e80e9c160d) neural nets, and as such allows for model combination, at test time only a single network needs to be tested.

 

By avoiding training all nodes on all training data, dropout decreases overfitting. The method also significantly improves training speed. This makes the model combination practical, even for [deep neural networks](./Deep_neural_network). The technique seems to reduce node interactions, leading them to learn more robust features[*[clarification needed](./Wikipedia:Please_clarify)*] that better generalize to new data.

 

#### DropConnect

 

DropConnect is the generalization of dropout in which each connection, rather than each output unit, can be dropped with probability     1 − −  p   {\displaystyle 1-p}  ![{\displaystyle 1-p}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9633a8692121eedfa99cace406205e5d1511ef8d). Each unit thus receives input from a random subset of units in the previous layer.[[96]](./Convolutional_neural_network#cite_note-99)

 

DropConnect is similar to dropout as it introduces dynamic sparsity within the model, but differs in that the sparsity is on the weights, rather than the output vectors of a layer. In other words, the fully connected layer with DropConnect becomes a sparsely connected layer in which the connections are chosen at random during the training stage.

 

#### Stochastic pooling

 

A major drawback to dropout is that it does not have the same benefits for convolutional layers, where the neurons are not fully connected.

 

Even before dropout, in 2013 a technique called stochastic pooling,[[97]](./Convolutional_neural_network#cite_note-100) the conventional [deterministic](./Deterministic_algorithm) pooling operations were replaced with a stochastic procedure, where the activation within each pooling region is picked randomly according to a [multinomial distribution](./Multinomial_distribution), given by the activities within the pooling region. This approach is free of hyperparameters and can be combined with other regularization approaches, such as dropout and [data augmentation](./Data_augmentation).

 

An alternate view of stochastic pooling is that it is equivalent to standard max pooling but with many copies of an input image, each having small local [deformations](./Deformation_theory). This is similar to explicit [elastic deformations](./Elastic_deformation) of the input images,[[98]](./Convolutional_neural_network#cite_note-:3-101) which delivers excellent performance on the [MNIST data set](./MNIST_database).[[98]](./Convolutional_neural_network#cite_note-:3-101) Using stochastic pooling in a multilayer model gives an exponential number of deformations since the selections in higher layers are independent of those below.

 

#### Artificial data

 Main article: [Data augmentation](./Data_augmentation) 

Because the degree of model overfitting is determined by both its power and the amount of training it receives, providing a convolutional network with more training examples can reduce overfitting. Because there is often not enough available data to train, especially considering that some part should be spared for later testing, two approaches are to either generate new data from scratch (if possible) or perturb existing data to create new ones. The latter one is used since mid-1990s.[[53]](./Convolutional_neural_network#cite_note-lecun95-53) For example, input images can be cropped, rotated, or rescaled to create new examples with the same labels as the original training set.[[99]](./Convolutional_neural_network#cite_note-102)

 

### Explicit

 

#### Early stopping

 Main article: [Early stopping](./Early_stopping) 

One of the simplest methods to prevent overfitting of a network is to simply stop the training before overfitting has had a chance to occur. It comes with the disadvantage that the learning process is halted.

 

#### Number of parameters

 

Another simple way to prevent overfitting is to limit the number of parameters, typically by limiting the number of hidden units in each layer or limiting network depth. For convolutional networks, the filter size also affects the number of parameters. Limiting the number of parameters restricts the predictive power of the network directly, reducing the complexity of the function that it can perform on the data, and thus limits the amount of overfitting. This is equivalent to a "[zero norm](./Zero_norm)".

 

#### Weight decay

 

A simple form of added regularizer is weight decay, which simply adds an additional error, proportional to the sum of weights ([L1 norm](./L1-norm)) or squared magnitude ([L2 norm](./L2_norm)) of the weight vector, to the error at each node. The level of acceptable model complexity can be reduced by increasing the proportionality constant('alpha' hyperparameter), thus increasing the penalty for large weight vectors.

 

L2 regularization is the most common form of regularization. It can be implemented by penalizing the squared magnitude of all parameters directly in the objective. The L2 regularization has the intuitive interpretation of heavily penalizing peaky weight vectors and preferring diffuse weight vectors. Due to multiplicative interactions between weights and inputs this has the useful property of encouraging the network to use all of its inputs a little rather than some of its inputs a lot.

 

L1 regularization is also common. It makes the weight vectors sparse during optimization. In other words, neurons with L1 regularization end up using only a sparse subset of their most important inputs and become nearly invariant to the noisy inputs. L1 with L2 regularization can be combined; this is called [elastic net regularization](./Elastic_net_regularization).

 

#### Max norm constraints

 

Another form of regularization is to enforce an absolute upper bound on the magnitude of the weight vector for every neuron and use [projected gradient descent](./Sparse_approximation#Projected_Gradient_Descent) to enforce the constraint. In practice, this corresponds to performing the parameter update as normal, and then enforcing the constraint by clamping the weight vector        w → →       {\displaystyle {\vec {w}}}  ![{\displaystyle {\vec {w}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8b6c48cdaecf8d81481ea21b1d0c046bf34b68ec) of every neuron to satisfy     ‖ ‖     w → →      ‖ ‖   2   < c   {\displaystyle \|{\vec {w}}\|_{2}<c}  ![{\displaystyle \|{\vec {w}}\|_{2}<c}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a1a47ec91922a4d2bc7122e90cff40c4b8b73d66). Typical values of     c   {\displaystyle c}  ![{\displaystyle c}](https://wikimedia.org/api/rest_v1/media/math/render/svg/86a67b81c2de995bd608d5b2df50cd8cd7d92455) are order of 3–4. Some papers report improvements[[100]](./Convolutional_neural_network#cite_note-103) when using this form of regularization.

 

## Hierarchical coordinate frames

 

Pooling loses the precise spatial relationships between high-level parts (such as nose and mouth in a face image). These relationships are needed for identity recognition. Overlapping the pools so that each feature occurs in multiple pools, helps retain the information. Translation alone cannot extrapolate the understanding of geometric relationships to a radically new viewpoint, such as a different orientation or scale. On the other hand, people are very good at extrapolating; after seeing a new shape once they can recognize it from a different viewpoint.[[101]](./Convolutional_neural_network#cite_note-104)

 

An earlier common way to deal with this problem is to train the network on transformed data in different orientations, scales, lighting, etc. so that the network can cope with these variations. This is computationally intensive for large data-sets. The alternative is to use a hierarchy of coordinate frames and use a group of neurons to represent a conjunction of the shape of the feature and its pose relative to the [retina](./Retina). The pose relative to the retina is the relationship between the coordinate frame of the retina and the intrinsic features' coordinate frame.[[102]](./Convolutional_neural_network#cite_note-105)

 

Thus, one way to represent something is to embed the coordinate frame within it. This allows large features to be recognized by using the consistency of the poses of their parts (e.g. nose and mouth poses make a consistent prediction of the pose of the whole face). This approach ensures that the higher-level entity (e.g. face) is present when the lower-level (e.g. nose and mouth) agree on its prediction of the pose. The vectors of neuronal activity that represent pose ("pose vectors") allow spatial transformations modeled as linear operations that make it easier for the network to learn the hierarchy of visual entities and generalize across viewpoints. This is similar to the way the human [visual system](./Visual_system) imposes coordinate frames in order to represent shapes.[[103]](./Convolutional_neural_network#cite_note-106)

 


