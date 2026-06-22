---
source: sources/wiki-Neural_network_28machine_learning29.md
source_url: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29
chunk: 5/10
---

## Types

 This section is an excerpt from [Types of artificial neural networks](./Types_of_artificial_neural_networks).[[edit](https://en.wikipedia.org/w/index.php?title=Types_of_artificial_neural_networks&action=edit)] 

[Types of neural networks](./Types_of_artificial_neural_networks) (NN) include a family of techniques. The simplest types have static components, including number of units, number of layers, unit weights and [topology](./Topology). Dynamic NNs evolve via learning. Some types allow/require learning to be "supervised" by the operator, while others operate independently. Some types operate purely in hardware, while others are purely software and run on general purpose computers.

 

The main types are:

 
- [Transformers](./Transformer_(deep_learning)): these use [attention](./Attention_(machine_learning)) to analyze every token in the input stream against every other token in the stream. That technique has enabled neural networks to reach the general public via chatbots, code generators and many other forms.
- [Convolutional neural networks](./Convolutional_neural_networks) (CNN): a FNN that uses kernels and regularization to evade problems in prior generations of NNs. They are typically used to analyze visual and other two-dimensional data.[[169]](./Neural_network_(machine_learning)#cite_note-169)[[170]](./Neural_network_(machine_learning)#cite_note-Types_of_artificial_neural_networks_lecun2016slides2-170)
- [Generative adversarial networks](./Generative_adversarial_network) set networks (of varying structure) against each other, each trying to push the other(s) to produce better results such as winning a game[[171]](./Neural_network_(machine_learning)#cite_note-Types_of_artificial_neural_networks_preprint2-171) or to deceive the opponent about the authenticity of an input.[[172]](./Neural_network_(machine_learning)#cite_note-Types_of_artificial_neural_networks_GANnips2-172) 

  

## Network design

 

The choice of model depends on the data and the application. Models that work well with textual data are typically not the best choice for image data, etc. An important element is which training/learning the model uses.[[173]](./Neural_network_(machine_learning)#cite_note-173)

 

[Neural architecture search](./Neural_architecture_search) (NAS) uses machine learning to automate NN design. NAS has yielded networks that compare well with hand-designed systems. The basic algorithm is to propose a candidate model, evaluate it against a dataset, and use the results as feedback to teach the NAS network.[[174]](./Neural_network_(machine_learning)#cite_note-174) Efforts include [AutoML](./Automated_machine_learning) and AutoKeras.[[175]](./Neural_network_(machine_learning)#cite_note-175) [scikit-learn library](./Scikit-learn) provides functions to help with building a deep network from scratch. 

 

Hyperparameters are design choices (they are not learned).[[176]](./Neural_network_(machine_learning)#cite_note-abs1502.021272-176)

 

## Theoretical properties

 

### Computational power

 

The [multilayer perceptron](./Multilayer_perceptron) is a [universal function](./UTM_theorem) approximator, as proven by the [universal approximation theorem](./Universal_approximation_theorem). However, the proof does not specify the number of neurons required, the network topology, the weights or the learning parameters.

 

A recurrent architecture with [rational](./Rational_number)-valued weights (as opposed to full precision real number-valued weights) has the power of a [universal Turing machine](./Universal_Turing_machine),[[177]](./Neural_network_(machine_learning)#cite_note-177) using a finite number of neurons and linear connections. Further, the use of [irrational](./Irrational_number) values for weights results in a machine with [super-Turing](./Hypercomputation) power.[[178]](./Neural_network_(machine_learning)#cite_note-178)[[179]](./Neural_network_(machine_learning)#cite_note-179)[*[failed verification](./Wikipedia:Verifiability)*]

 

### Capacity

 

A model's "capacity" property is its ability to model any given function. It is related to the amount of information that can be stored in the network and to the notion of complexity. Information capacity and the [VC dimension](./VC_dimension) are two metrics. The capacity of a network of standard neurons (not convolutional) can be derived by four rules[[180]](./Neural_network_(machine_learning)#cite_note-180) that derive from considering a neuron as an electrical element. 

 

The information capacity captures the functions that the network can model given any data as input. The VC dimension uses the principles of [measure theory](./Measure_theory) and finds the maximum capacity under optimal circumstances, given input data in a specific form. The VC Dimension for arbitrary inputs is half the information capacity of a perceptron. The VC Dimension for arbitrary points is sometimes referred to as Memory Capacity.[[181]](./Neural_network_(machine_learning)#cite_note-181)[[182]](./Neural_network_(machine_learning)#cite_note-auto2-182)

 

### Convergence

 

Models may not consistently converge on a single solution, because the system may get stuck in a local minima. Alternatively, the optimization method used might not guarantee to converge should it begin far from any local minima. Thirdly, for sufficiently large data or parameters, some methods are  impractically slow/expensive. Training may also cross some [saddle point](./Saddle_point) that may then prevent access to the solution.

 

When the width of a network approaches infinity, it is well described by its first order [Taylor expansion](./Taylor_expansion) throughout training, and so inherits the [convergence](./Convergent_series) behavior of [affine models](./Linear_model).[[183]](./Neural_network_(machine_learning)#cite_note-183)[[184]](./Neural_network_(machine_learning)#cite_note-184) When parameter numbers are small, NNs often fit target functions from low to high frequencies. This behavior is referred to as spectral bias, or the frequency principle.[[185]](./Neural_network_(machine_learning)#cite_note-185)[[186]](./Neural_network_(machine_learning)#cite_note-186)[[187]](./Neural_network_(machine_learning)#cite_note-187) This phenomenon is the opposite of the behavior of some well-studied iterative numerical schemes such as the [Jacobi method](./Jacobi_method). Deeper neural networks are more biased towards low frequency functions.[[188]](./Neural_network_(machine_learning)#cite_note-188)

 

### Generalization and statistics

 
|  | This sectiondoes notciteanysources.Please helpimprove this sectionbyadding citations to reliable sources. Unsourced material may be challenged andremoved.(May 2026)(Learn how and when to remove this message) |
| --- | --- |

 

Applications that must generalize well to unseen examples, must avoid [over-training](./Overfitting). This arises in convoluted or over-specified systems when the network capacity is much larger than needed.

 

Two approaches address over-training. [Cross-validation](./Cross-validation_(statistics)) and similar techniques can check for over-training and select appropriate hyperparameters to minimize generalization error. *[Regularization](./Regularization_(mathematics))* in a probabilistic (Bayesian) framework can be performed by selecting a larger prior probability over simpler models; but also in statistical learning theory, where the goal is to minimize two quantities: the 'empirical risk' and the 'structural risk', which roughly corresponds to the error over the training set and the predicted error in unseen data due to overfitting.

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/2/22/Synapse_deployment.jpg/250px-Synapse_deployment.jpg)](./File:Synapse_deployment.jpg)Confidence analysis of a neural network 

Supervised neural networks that use a [mean squared error](./Mean_squared_error) (MSE) cost function can use formal statistical methods to determine the confidence of the trained model. The MSE on a validation set can be used as an estimate for variance. This value can then be used to calculate the [confidence interval](./Confidence_interval) of network output, assuming a [normal distribution](./Normal_distribution). A confidence analysis made this way is statistically valid as long as the output [probability distribution](./Probability_distribution) stays the same and the network is not modified.

 

By adopting a [softmax activation function](./Softmax_activation_function), a generalization of the [logistic function](./Logistic_function), on the output layer of the neural network (or a softmax component in a component-based network) for categorical target variables, the outputs can be interpreted as posterior probabilities. This is useful in classification as it gives a certainty measure.

 

The softmax activation function is:

      y  i   =    e   x  i       ∑ ∑   j = 1   c    e   x  j          {\displaystyle y_{i}={\frac {e^{x_{i}}}{\sum _{j=1}^{c}e^{x_{j}}}}}  ![{\displaystyle y_{i}={\frac {e^{x_{i}}}{\sum _{j=1}^{c}e^{x_{j}}}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/481884e3588b192020e8d0aafe16b41c0ed26007) 


