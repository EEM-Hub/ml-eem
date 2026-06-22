---
source: sources/wiki-Recurrent_neural_network.md
source_url: https://en.wikipedia.org/wiki/Recurrent_neural_network
chunk: 5/7
---

## Other architectures

 

### Independently RNN (IndRNN)

 

The independently recurrent neural network (IndRNN)[[87]](./Recurrent_neural_network#cite_note-auto-87) addresses the gradient vanishing and exploding problems in the traditional fully connected RNN. Each neuron in one layer only receives its own past state as context information (instead of full connectivity to all other neurons in this layer) and thus neurons are independent of each other's history. The gradient backpropagation can be regulated to avoid gradient vanishing and exploding in order to keep long or short-term memory. The cross-neuron information is explored in the next layers. IndRNN can be robustly trained with non-saturated nonlinear functions such as [ReLU](./ReLU). Deep networks can be trained using [skip connections](./Skip_connections).

 

### Neural history compressor

 

The *neural history compressor* is an unsupervised stack of RNNs.[[96]](./Recurrent_neural_network#cite_note-schmidhuber1992-96) At the input level, it learns to predict its next input from the previous inputs. Only unpredictable inputs of some RNN in the hierarchy become inputs to the next higher level RNN, which therefore recomputes its internal state only rarely. Each higher level RNN thus studies a compressed representation of the information in the RNN below. This is done such that the input sequence can be precisely reconstructed from the representation at the highest level.

 

The system effectively minimizes the description length or the negative [logarithm](./Logarithm) of the probability of the data.[[97]](./Recurrent_neural_network#cite_note-scholarpedia2015pre-97) Given a lot of learnable predictability in the incoming data sequence, the highest level RNN can use supervised learning to easily classify even deep sequences with long intervals between important events.

 

It is possible to distill the RNN hierarchy into two RNNs: the "conscious" chunker (higher level) and the "subconscious" automatizer (lower level).[[96]](./Recurrent_neural_network#cite_note-schmidhuber1992-96) Once the chunker has learned to predict and compress inputs that are unpredictable by the automatizer, then the automatizer can be forced in the next learning phase to predict or imitate through additional units the hidden units of the more slowly changing chunker. This makes it easy for the automatizer to learn appropriate, rarely changing memories across long intervals. In turn, this helps the automatizer to make many of its once unpredictable inputs predictable, such that the chunker can focus on the remaining unpredictable events.[[96]](./Recurrent_neural_network#cite_note-schmidhuber1992-96)

 

A [generative model](./Generative_model) partially overcame the [vanishing gradient problem](./Vanishing_gradient_problem)[[55]](./Recurrent_neural_network#cite_note-hochreiter1991-55) of [automatic differentiation](./Automatic_differentiation) or [backpropagation](./Backpropagation) in neural networks in 1992. In 1993, such a system solved a "Very Deep Learning" task that required more than 1000 subsequent layers in an RNN unfolded in time.[[34]](./Recurrent_neural_network#cite_note-schmidhuber1993-34)

 

### Second order RNNs

 

Second-order RNNs use higher order weights     w     i j k     {\displaystyle w{}_{ijk}}  ![{\displaystyle w{}_{ijk}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/847af94eb75e72db4b5604559682ce920572fa69) instead of the standard     w     i j     {\displaystyle w{}_{ij}}  ![{\displaystyle w{}_{ij}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6ef1a6e570e9d6285d37905fd89313b583d2d871) weights, and states can be a product. This allows a direct mapping to a [finite-state machine](./Finite-state_machine) both in training, and representation.[[98]](./Recurrent_neural_network#cite_note-98)[[99]](./Recurrent_neural_network#cite_note-99) Long short-term memory is an example of this but has no such formal mappings or proof of stability.

 

### Hierarchical recurrent neural network

 

Hierarchical recurrent neural networks (HRNN) connect their neurons in various ways to decompose hierarchical behavior into useful subprograms.[[96]](./Recurrent_neural_network#cite_note-schmidhuber1992-96)[[100]](./Recurrent_neural_network#cite_note-100) Such hierarchical structures of cognition are present in theories of memory presented by philosopher [Henri Bergson](./Henri_Bergson), whose philosophical views have inspired hierarchical models.[[101]](./Recurrent_neural_network#cite_note-auto1-101)

 

Hierarchical recurrent neural networks are useful in [forecasting](./Forecasting), helping to predict disaggregated inflation components of the [consumer price index](./Consumer_price_index) (CPI). The HRNN model leverages information from higher levels in the CPI hierarchy to enhance lower-level predictions. Evaluation of a substantial dataset from the US CPI-U index demonstrates the superior performance of the HRNN model compared to various established [inflation](./Inflation) prediction methods.[[102]](./Recurrent_neural_network#cite_note-barkan-102)

 

### Recurrent multilayer perceptron network

 

Generally, a recurrent multilayer perceptron network (RMLPN) consists of cascaded subnetworks, each containing multiple layers of nodes. Each subnetwork is feed-forward except for the last layer, which can have feedback connections. Each of these subnets is connected only by feed-forward connections.[[103]](./Recurrent_neural_network#cite_note-103)

 

### Multiple timescales model

 

A multiple timescales recurrent neural network (MTRNN) is a neural-based computational model that can simulate the functional hierarchy of the brain through self-organization depending on the spatial connection between neurons and on distinct types of neuron activities, each with distinct time properties.[[104]](./Recurrent_neural_network#cite_note-104)[[105]](./Recurrent_neural_network#cite_note-105) With such varied neuronal activities, continuous sequences of any set of behaviors are segmented into reusable primitives, which in turn are flexibly integrated into diverse sequential behaviors. The biological approval of such a type of hierarchy was discussed in the [memory-prediction](./Memory-prediction_framework) theory of brain function by [Hawkins](./Jeff_Hawkins) in his book *[On Intelligence](./On_Intelligence)*.[*[citation needed](./Wikipedia:Citation_needed)*] Such a hierarchy also agrees with theories of memory posited by philosopher [Henri Bergson](./Henri_Bergson), which have been incorporated into an MTRNN model.[[101]](./Recurrent_neural_network#cite_note-auto1-101)[[106]](./Recurrent_neural_network#cite_note-106)

 

### Memristive networks

 

Greg Snider of [HP Labs](./HP_Labs) describes a system of cortical computing with memristive nanodevices.[[107]](./Recurrent_neural_network#cite_note-107) The [memristors](./Memristors) (memory resistors) are implemented by thin film materials in which the resistance is electrically tuned via the transport of ions or oxygen vacancies within the film. [DARPA](./DARPA)'s [SyNAPSE project](./SyNAPSE) has funded IBM Research and HP Labs, in collaboration with the Boston University Department of Cognitive and Neural Systems (CNS), to develop neuromorphic architectures that may be based on memristive systems.
[Memristive networks](./Memristive_networks?action=edit&redlink=1) are a particular type of [physical neural network](./Physical_neural_network) that have very similar properties to (Little-)Hopfield networks, as they have continuous dynamics, a limited memory capacity and natural relaxation via the minimization of a function which is asymptotic to the [Ising model](./Ising_model). In this sense, the dynamics of a memristive circuit have the advantage compared to a Resistor-Capacitor network to have a more interesting non-linear behavior. From this point of view, engineering analog memristive networks account for a peculiar type of [neuromorphic engineering](./Neuromorphic_engineering) in which the device behavior depends on the circuit wiring or topology.
The evolution of these networks can be studied analytically using variations of the [Caravelli-Traversa-Di Ventra equation](./Caravelli-Traversa-Di_Ventra_equation).[[108]](./Recurrent_neural_network#cite_note-108)

 

### Continuous-time

 

A continuous-time recurrent neural network (CTRNN) uses a system of [ordinary differential equations](./Ordinary_differential_equations) to model the effects on a neuron of the incoming inputs. They are typically analyzed by [dynamical systems theory](./Dynamical_systems_theory). Many RNN models in neuroscience are continuous-time.[[16]](./Recurrent_neural_network#cite_note-:0-16)

 

For a neuron     i   {\displaystyle i}  ![{\displaystyle i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/add78d8608ad86e54951b8c8bd6c8d8416533d20) in the network with activation      y  i     {\displaystyle y_{i}}  ![{\displaystyle y_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/67d30d30b6c2dbe4d6f150d699de040937ecc95f), the rate of change of activation is given by:

      τ τ   i       y ˙ ˙      i   = − −   y  i   +  ∑ ∑   j = 1   n    w  j i   σ σ  (  y  j   − −   Θ Θ   j   ) +  I  i   ( t )   {\displaystyle \tau _{i}{\dot {y}}_{i}=-y_{i}+\sum _{j=1}^{n}w_{ji}\sigma (y_{j}-\Theta _{j})+I_{i}(t)}  ![{\displaystyle \tau _{i}{\dot {y}}_{i}=-y_{i}+\sum _{j=1}^{n}w_{ji}\sigma (y_{j}-\Theta _{j})+I_{i}(t)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fe3aece040129e349beb408629229528edbafb24) 

Where:

 
-      τ τ   i     {\displaystyle \tau _{i}}  ![{\displaystyle \tau _{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/814ca8b33360ac3b7db8e9435271b5654175c853) : Time constant of [postsynaptic](./Synapse) node
-      y  i     {\displaystyle y_{i}}  ![{\displaystyle y_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/67d30d30b6c2dbe4d6f150d699de040937ecc95f) : Activation of postsynaptic node
-         y ˙ ˙      i     {\displaystyle {\dot {y}}_{i}}  ![{\displaystyle {\dot {y}}_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d7413f2eddfa4154ca58ecb3aba013f9e5e18309) : Rate of change of activation of postsynaptic node
-     w     j i     {\displaystyle w{}_{ji}}  ![{\displaystyle w{}_{ji}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/921dbd2f06de98163dd3eb31b8ca419431f77241) : Weight of connection from pre to postsynaptic node
-     σ σ  ( x )   {\displaystyle \sigma (x)}  ![{\displaystyle \sigma (x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ae09ff47b50183fbfd1ea5697c63963ec9eefa20) : [Sigmoid](./Sigmoid_function) of x e.g.     σ σ  ( x ) = 1  /  ( 1 +  e  − −  x   )   {\displaystyle \sigma (x)=1/(1+e^{-x})}  ![{\displaystyle \sigma (x)=1/(1+e^{-x})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2d652eb008d808b8f71210bb3d2fe48a5ee451a7).
-      y  j     {\displaystyle y_{j}}  ![{\displaystyle y_{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f8df4e372390588acb968986cfc388e50b930b3a) : Activation of presynaptic node
-      Θ Θ   j     {\displaystyle \Theta _{j}}  ![{\displaystyle \Theta _{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/10b9d5bab99a44d98171cce92f04d0e700060512) : Bias of presynaptic node
-      I  i   ( t )   {\displaystyle I_{i}(t)}  ![{\displaystyle I_{i}(t)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9452bc33550571d001aa8ba5399b61818c26fb60) : Input (if any) to node

 

CTRNNs have been applied to [evolutionary robotics](./Evolutionary_robotics) where they have been used to address vision,[[109]](./Recurrent_neural_network#cite_note-109) co-operation,[[110]](./Recurrent_neural_network#cite_note-Evolving_communication_without_dedicated_communication_channels-110) and minimal cognitive behaviour.[[111]](./Recurrent_neural_network#cite_note-The_dynamics_of_adaptive_behavior:_A_research_program-111)

 

Note that, by the [Shannon sampling theorem](./Shannon_sampling_theorem), discrete-time recurrent neural networks can be viewed as continuous-time recurrent neural networks where the differential equations have transformed into equivalent [difference equations](./Difference_equation).[[112]](./Recurrent_neural_network#cite_note-Sherstinsky-NeurIPS2018-CRACT-3-112) This transformation can be thought of as occurring after the post-synaptic node activation functions      y  i   ( t )   {\displaystyle y_{i}(t)}  ![{\displaystyle y_{i}(t)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/20dfaede0e3f6f701b4c82b5ed153148f5e7d0aa) have been [low-pass filtered](./Low-pass_filter) but prior to sampling.

 

They are in fact [recursive neural networks](./Recursive_neural_network) with a particular structure: that of a linear chain. Whereas recursive neural networks operate on any hierarchical structure, combining child representations into parent representations, recurrent neural networks operate on the linear progression of time, combining the previous time step and a hidden representation into the representation for the current time step.

 

From a time-series perspective, RNNs can appear as nonlinear versions of [finite impulse response](./Finite_impulse_response) and [infinite impulse response](./Infinite_impulse_response) filters and also as a [nonlinear autoregressive exogenous model](./Nonlinear_autoregressive_exogenous_model) (NARX).[[113]](./Recurrent_neural_network#cite_note-113) RNN has infinite impulse response whereas [convolutional neural network](./Convolutional_neural_network) has [finite impulse response](./Finite_impulse_response). Both classes of networks exhibit temporal [dynamic behavior](./Dynamic_system).[[114]](./Recurrent_neural_network#cite_note-114) A finite impulse recurrent network is a [directed acyclic graph](./Directed_acyclic_graph) that can be unrolled and replaced with a strictly feedforward neural network, while an infinite impulse recurrent network is a [directed cyclic graph](./Directed_cyclic_graph) that cannot be unrolled.

 

The effect of memory-based learning for the recognition of sequences can also be implemented by a more biological-based model which uses the silencing mechanism exhibited in neurons with a relatively high frequency [spiking activity](./Action_potential).[[115]](./Recurrent_neural_network#cite_note-115)

 

Additional stored states and the storage under direct control by the network can be added to both [infinite-impulse](./Infinite_impulse_response) and [finite-impulse](./Finite_impulse_response) networks. Another network or graph can also replace the storage if that incorporates time delays or has feedback loops. Such controlled states are referred to as gated states or gated memory and are part of [long short-term memory](./Long_short-term_memory) networks (LSTMs) and [gated recurrent units](./Gated_recurrent_unit). This is also called Feedback Neural Network (FNN).

 

## Libraries

 

Modern libraries provide runtime-optimized implementations of the above functionality or allow to speed up the slow loop by [just-in-time compilation](./Just-in-time_compilation).

 
- [Apache Singa](./Apache_Singa)
- [Caffe](./Caffe_(software)): Created by the Berkeley Vision and Learning Center (BVLC). It supports both CPU and GPU. Developed in [C++](./C++), and has [Python](./Python_(programming_language)) and [MATLAB](./MATLAB) wrappers.
- [Chainer](./Chainer): Fully in Python, production support for CPU, GPU, distributed training.
- [Deeplearning4j](./Deeplearning4j): Deep learning in [Java](./Java_(programming_language)) and [Scala](./Scala_(programming_language)) on multi-GPU-enabled [Spark](./Apache_Spark).
- [Flux](./Flux_(machine-learning_framework)): includes interfaces for RNNs, including GRUs and LSTMs, written in [Julia](./Julia_(programming_language)).
- [Keras](./Keras): High-level API, providing a wrapper to many other deep learning libraries.
- [Microsoft Cognitive Toolkit](./Microsoft_Cognitive_Toolkit)
- [MXNet](./MXNet): an open-source deep learning framework used to train and deploy deep neural networks.
- [PyTorch](./PyTorch): Tensors and Dynamic neural networks in Python with GPU acceleration.
- [TensorFlow](./TensorFlow): Apache 2.0-licensed Theano-like library with support for CPU, GPU and Google's proprietary [TPU](./Tensor_processing_unit),[[116]](./Recurrent_neural_network#cite_note-116) mobile
- [Theano](./Theano_(software)): A deep-learning library for Python with an API largely compatible with the [NumPy](./NumPy) library.
- [Torch](./Torch_(machine_learning)): A scientific computing framework with support for machine learning algorithms, written in [C](./C_(programming_language)) and [Lua](./Lua_(programming_language)).

 

## Applications

 

Applications of recurrent neural networks include:

 
- [Machine translation](./Machine_translation)[[42]](./Recurrent_neural_network#cite_note-sutskever2014-42)
- [Robot control](./Robot_control)[[117]](./Recurrent_neural_network#cite_note-117)
- [Time series prediction](./Time_series_prediction)[[118]](./Recurrent_neural_network#cite_note-118)[[119]](./Recurrent_neural_network#cite_note-119)[[120]](./Recurrent_neural_network#cite_note-120)
- [Speech recognition](./Speech_recognition)[[121]](./Recurrent_neural_network#cite_note-121)[[39]](./Recurrent_neural_network#cite_note-fernandez2007keyword-39)[[122]](./Recurrent_neural_network#cite_note-graves2013-122)
- [Speech synthesis](./Speech_synthesis)[[123]](./Recurrent_neural_network#cite_note-123)
- [Brain–computer interfaces](./Brain–computer_interfaces)[[124]](./Recurrent_neural_network#cite_note-124)
- Time series anomaly detection[[125]](./Recurrent_neural_network#cite_note-125)
- [Text-to-Video model](./Text-to-Video_model)[[126]](./Recurrent_neural_network#cite_note-126)
- [Energy forecasting](./Energy_forecasting)[[127]](./Recurrent_neural_network#cite_note-127)
- Rhythm learning[[128]](./Recurrent_neural_network#cite_note-peephole2002-128)
- Music composition[[129]](./Recurrent_neural_network#cite_note-129)
- Grammar learning[[130]](./Recurrent_neural_network#cite_note-130)[[58]](./Recurrent_neural_network#cite_note-peepholeLSTM-58)[[131]](./Recurrent_neural_network#cite_note-131)
- [Handwriting recognition](./Handwriting_recognition)[[132]](./Recurrent_neural_network#cite_note-132)[[133]](./Recurrent_neural_network#cite_note-133)
- Human action recognition[[134]](./Recurrent_neural_network#cite_note-134)
- Protein homology detection[[135]](./Recurrent_neural_network#cite_note-135)
- Predicting subcellular localization of proteins[[136]](./Recurrent_neural_network#cite_note-ThireoReczko-136)
- Several prediction tasks in the area of business process management[[137]](./Recurrent_neural_network#cite_note-137)
- Prediction in medical care pathways[[138]](./Recurrent_neural_network#cite_note-138)
- Predictions of fusion plasma disruptions in reactors (Fusion Recurrent Neural Network (FRNN) code) [[139]](./Recurrent_neural_network#cite_note-139)

 


