---
source: sources/wiki-Deep_learning.md
source_url: https://en.wikipedia.org/wiki/Deep_learning
chunk: 3/7
---

## Neural networks

 Main article: [Artificial neural network](./Artificial_neural_network) [![](//upload.wikimedia.org/wikipedia/commons/thumb/0/0c/Simplified_neural_network_training_example.svg/250px-Simplified_neural_network_training_example.svg.png)](./File:Simplified_neural_network_training_example.svg)Simplified example of training a neural network in object detection: The network is trained by multiple images that are known to depict [starfish](./Starfish) and [sea urchins](./Sea_urchin), which are correlated with "nodes" that represent visual [features](./Feature_(computer_vision)). The starfish match with a ringed texture and a star outline, whereas most sea urchins match with a striped texture and oval shape. However, the instance of a ring textured sea urchin creates a weakly weighted association between them.[![](//upload.wikimedia.org/wikipedia/commons/thumb/b/b7/Simplified_neural_network_example.svg/250px-Simplified_neural_network_example.svg.png)](./File:Simplified_neural_network_example.svg)Subsequent run of the network on an input image (left):[[140]](./Deep_learning#cite_note-140) The network correctly detects the starfish. However, the weakly weighted association between ringed texture and sea urchin also confers a weak signal to the latter from one of two intermediate nodes. In addition, a [shell](./Seashell) that was not included in the training gives a weak signal for the oval shape, also resulting in a weak signal for the sea urchin output. These weak signals may result in a [false positive](./False_positive) result for sea urchin.
In reality, textures and outlines would not be represented by single nodes, but rather by associated weight patterns of multiple nodes. 

**Artificial neural networks** (**ANNs**) or **connectionist systems** are computing systems inspired by the [biological neural networks](./Biological_neural_network) that constitute animal brains. Such systems learn (progressively improve their ability) to do tasks by considering examples, generally without task-specific programming. For example, in image recognition, they might learn to identify images that contain cats by analyzing example images that have been manually [labeled](./Labeled_data) as "cat" or "no cat" and using the analytic results to identify cats in other images. They have found most use in applications difficult to express with a traditional computer algorithm using [rule-based programming](./Rule-based_programming).

 

An ANN is based on a collection of [connected](./Connectionism) units called [artificial neurons](./Artificial_neuron), (analogous to biological [neurons](./Neuron) in a [biological brain](./Brain)). Each connection ([synapse](./Synapse)) between neurons can transmit a signal to another neuron. The receiving (postsynaptic) neuron can process the signal(s) and then signal downstream neurons connected to it. Neurons may have state, generally represented by [real numbers](./Real_numbers), typically between 0 and 1. Neurons and synapses may also have a weight that varies as learning proceeds, which can increase or decrease the strength of the signal that it sends downstream.

 

Typically, neurons are organized in layers. Different layers may perform different kinds of transformations on their inputs. Signals travel from the first (input), to the last (output) layer, possibly after traversing the layers multiple times.

 

The original goal of the neural network approach was to solve problems in the same way that a human brain would. Over time, attention focused on matching specific mental abilities, leading to deviations from biology such as [backpropagation](./Backpropagation), or passing information in the reverse direction and adjusting the network to reflect that information.

 

Neural networks have been used on a variety of tasks, including computer vision, [speech recognition](./Speech_recognition), [machine translation](./Machine_translation), [social network](./Social_network) filtering, [playing board and video games](./General_game_playing) and medical diagnosis.

 

As of 2017, neural networks typically have a few thousand to a few million units and millions of connections. Despite this number being several order of magnitude less than the number of neurons on a human brain, these networks can perform many tasks at a level beyond that of humans (e.g., recognizing faces, or playing "Go"[[141]](./Deep_learning#cite_note-141)).

 

### Deep neural networks

 

A **deep neural network** (**DNN**) is an artificial neural network with multiple layers between the input and output layers.[[7]](./Deep_learning#cite_note-BENGIODEEP-7)[[9]](./Deep_learning#cite_note-SCHIDHUB-9) There are different types of neural networks but they always consist of the same components: neurons, synapses, weights, biases, and functions.[[142]](./Deep_learning#cite_note-Nokkada-142) These components as a whole function in a way that mimics functions of the human brain, and can be trained like any other ML algorithm.[*[citation needed](./Wikipedia:Citation_needed)*]

 

For example, a DNN that is trained to recognize dog breeds will go over the given image and calculate the probability that the dog in the image is a certain breed. The user can review the results and select which probabilities the network should display (above a certain threshold, etc.) and return the proposed label. Each mathematical manipulation as such is considered a layer,[[143]](./Deep_learning#cite_note-Kumar2021-143) and complex DNN have many layers, hence the name "deep" networks.

 

DNNs can model complex non-linear relationships. DNN architectures generate compositional models where the object is expressed as a layered composition of [primitives](./Primitive_data_type).[[144]](./Deep_learning#cite_note-144) The extra layers enable composition of features from lower layers, potentially modeling complex data with fewer units than a similarly performing shallow network.[[7]](./Deep_learning#cite_note-BENGIODEEP-7) For instance, it was proved that sparse [multivariate polynomials](./Multivariate_polynomial) are exponentially easier to approximate with DNNs than with shallow networks.[[145]](./Deep_learning#cite_note-rolnickpaper-145)

 

Deep architectures include many variants of a few basic approaches. Each architecture has found success in specific domains. It is not always possible to compare the performance of multiple architectures, unless they have been evaluated on the same data sets.[[143]](./Deep_learning#cite_note-Kumar2021-143)

 

DNNs are typically feedforward networks in which data flows from the input layer to the output layer without looping back. At first, the DNN creates a map of virtual neurons and assigns random numerical values, or "weights", to connections between them. The weights and inputs are multiplied and return an output between 0 and 1. If the network did not accurately recognize a particular pattern, an algorithm would adjust the weights.[[146]](./Deep_learning#cite_note-146) That way the algorithm can make certain parameters more influential, until it determines the correct mathematical manipulation to fully process the data.

 

[Recurrent neural networks](./Recurrent_neural_networks), in which data can flow in any direction, are used for applications such as [language modeling](./Language_model).[[147]](./Deep_learning#cite_note-gers2001-147)[[148]](./Deep_learning#cite_note-NIPS2014-148)[[149]](./Deep_learning#cite_note-vinyals2016-149)[[150]](./Deep_learning#cite_note-gillick2015-150)[[151]](./Deep_learning#cite_note-MIKO2010-151) Long short-term memory is particularly effective for this use.[[152]](./Deep_learning#cite_note-:0-152)[[153]](./Deep_learning#cite_note-:10-153)

 

[Convolutional neural networks](./Convolutional_neural_network) (CNNs) are used in computer vision.[[154]](./Deep_learning#cite_note-LECUN86-154) CNNs also have been applied to [acoustic modeling](./Acoustic_model) for automatic speech recognition (ASR).[[155]](./Deep_learning#cite_note-:2-155)

 

#### Challenges

 

As with ANNs, many issues can arise with naively trained DNNs. Two common issues are [overfitting](./Overfitting) and computation time.

 

DNNs are prone to overfitting because of the added layers of abstraction, which allow them to model rare dependencies in the training data. [Regularization](./Regularization_(mathematics)) methods such as Ivakhnenko's unit pruning[[41]](./Deep_learning#cite_note-ivak1971-41) or [weight decay](./Weight_decay) (     ℓ ℓ   2     {\displaystyle \ell _{2}}  ![{\displaystyle \ell _{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/85a4571ee9be10bd3c9df2480ab3d280f99e801a)-regularization) or [sparsity](./Sparse_matrix) (     ℓ ℓ   1     {\displaystyle \ell _{1}}  ![{\displaystyle \ell _{1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/361ddd720474aa41cb05453e03424fb7999d3b02)-regularization) can be applied during training to combat overfitting.[[156]](./Deep_learning#cite_note-156) Alternatively [dropout](./Dropout_(neural_networks)) regularization randomly omits units from the hidden layers during training. This helps to exclude rare dependencies.[[157]](./Deep_learning#cite_note-DAHL2013-157) Another interesting recent development is research into models of just enough complexity through an estimation of the intrinsic complexity of the task being modelled. This approach has been successfully applied for multivariate time series prediction tasks such as traffic prediction.[[158]](./Deep_learning#cite_note-Kumar2024-158) Finally, data can be augmented via methods such as cropping and rotating such that smaller training sets can be increased in size to reduce the chances of overfitting.[[159]](./Deep_learning#cite_note-159)

 

DNNs must consider many training parameters, such as the size (number of layers and number of units per layer), the [learning rate](./Learning_rate), and initial weights. [Sweeping through the parameter space](./Hyperparameter_optimization#Grid_search) for optimal parameters may not be feasible due to the cost in time and computational resources. Various tricks, such as [batching](./Batch_learning) (computing the gradient on several training examples at once rather than individual examples)[[160]](./Deep_learning#cite_note-RBMTRAIN-160) speed up computation. Large processing capabilities of many-core architectures (such as GPUs or the Intel Xeon Phi) have produced significant speedups in training, because of the suitability of such processing architectures for the matrix and vector computations.[[161]](./Deep_learning#cite_note-161)[[162]](./Deep_learning#cite_note-162)

 

Alternatively, engineers may look for other types of neural networks with more straightforward and convergent training algorithms. CMAC ([cerebellar model articulation controller](./Cerebellar_model_articulation_controller)) is one such kind of neural network. It doesn't require learning rates or randomized initial weights. The training process can be guaranteed to converge in one step with a new batch of data, and the computational complexity of the training algorithm is linear with respect to the number of neurons involved.[[163]](./Deep_learning#cite_note-Qin1-163)[[164]](./Deep_learning#cite_note-Qin2-164)

 

## Hardware

 

Since the 2010s, advances in both machine learning algorithms and [computer hardware](./Computer_hardware) have led to more efficient methods for training deep neural networks that contain many layers of non-linear hidden units and a very large output layer.[[165]](./Deep_learning#cite_note-165) By 2019, [graphics processing units](./Graphics_processing_unit) (GPUs), often with AI-specific enhancements, had displaced CPUs as the dominant method for training large-scale commercial cloud AI .[[166]](./Deep_learning#cite_note-166) [OpenAI](./OpenAI) estimated the hardware computation used in the largest deep learning projects from AlexNet (2012) to AlphaZero (2017) and found a 300,000-fold increase in the amount of computation required, with a doubling-time trendline of 3.4 months.[[167]](./Deep_learning#cite_note-167)[[168]](./Deep_learning#cite_note-168)

 

Special [electronic circuits](./Electronic_circuit) called [deep learning processors](./Deep_learning_processor) were designed to speed up deep learning algorithms. Deep learning processors include neural processing units (NPUs) in [Huawei](./Huawei) cellphones[[169]](./Deep_learning#cite_note-169) and [cloud computing](./Cloud_computing) servers such as [tensor processing units](./Tensor_processing_unit) (TPU) in the [Google Cloud Platform](./Google_Cloud_Platform).[[170]](./Deep_learning#cite_note-170) [Cerebras Systems](./Cerebras) has also built a dedicated system to handle large deep learning models, the CS-2, based on the largest processor in the industry, the second-generation Wafer Scale Engine (WSE-2).[[171]](./Deep_learning#cite_note-171)[[172]](./Deep_learning#cite_note-172)

 

Atomically thin [semiconductors](./Semiconductors) are considered promising for energy-efficient deep learning hardware where the same basic device structure is used for both logic operations and data storage.
In 2020, Marega et al. published experiments with a large-area active channel material for developing logic-in-memory devices and circuits based on [floating-gate](./Floating-gate) [field-effect transistors](./Field-effect_transistor) (FGFETs).[[173]](./Deep_learning#cite_note-atomthin-173)

 

In 2021, J. Feldmann et al. proposed an integrated [photonic](./Photonic) [hardware accelerator](./Hardware_accelerator) for parallel convolutional processing.[[174]](./Deep_learning#cite_note-photonic-174) The authors identify two key advantages of integrated photonics over its electronic counterparts: (1) massively parallel data transfer through [wavelength](./Wavelength) division [multiplexing](./Multiplexing) in conjunction with [frequency combs](./Frequency_comb), and (2) extremely high data modulation speeds.[[174]](./Deep_learning#cite_note-photonic-174) Their system can execute trillions of multiply-accumulate operations per second, indicating the potential of [integrated](./Photonic_integrated_circuit) [photonics](./Photonics) in data-heavy AI applications.[[174]](./Deep_learning#cite_note-photonic-174)

 


