---
source: sources/wiki-Recurrent_neural_network.md
source_url: https://en.wikipedia.org/wiki/Recurrent_neural_network
chunk: 3/7
---

## Architectures

 

### Fully recurrent

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/4/44/Hopfield-net-vector.svg/250px-Hopfield-net-vector.svg.png)](./File:Hopfield-net-vector.svg)A fully connected RNN with 4 neurons 

**Fully recurrent neural networks** (FRNN) connect the outputs of all neurons to the inputs of all neurons. In other words, it is a [fully connected network](./Fully_connected_network). This is the most general neural network topology, because all other topologies can be represented by setting some connection weights to zero to simulate the lack of connections between those neurons.

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/0/02/RNN_architecture.png/250px-RNN_architecture.png)](./File:RNN_architecture.png)A simple Elman network where      σ σ   h   = tanh ,  σ σ   y   =  Identity    {\displaystyle \sigma _{h}=\tanh ,\sigma _{y}={\text{Identity}}}  ![{\displaystyle \sigma _{h}=\tanh ,\sigma _{y}={\text{Identity}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/02121b05b248e1d48a45e75052bc4e5144c8bde7) 

### Hopfield

 Main article: [Hopfield network](./Hopfield_network) 

The **Hopfield network** is an RNN in which all connections across layers are equally sized. It requires [stationary](./Stationary_process) inputs and is thus not a general RNN, as it does not process sequences of patterns. However, it guarantees that it will converge. If the connections are trained using [Hebbian learning](./Hebbian_learning), then the Hopfield network can perform as [robust](./Robustness_(computer_science)) [content-addressable memory](./Content-addressable_memory), resistant to connection alteration.

 

### Elman networks and Jordan networks

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/8/8f/Elman_srnn.png/250px-Elman_srnn.png)](./File:Elman_srnn.png)The Elman network 

An **[Elman](./Jeff_Elman) network** is a three-layer network (arranged horizontally as *x*, *y*, and *z* in the illustration) with the addition of a set of context units (*u* in the illustration). The middle (hidden) layer is connected to these context units fixed with a weight of one.[[51]](./Recurrent_neural_network#cite_note-bmm615-51) At each time step, the input is fed forward and a [learning rule](./Learning_rule) is applied. The fixed back-connections save a copy of the previous values of the hidden units in the context units (since they propagate over the connections before the learning rule is applied). Thus the network can maintain a sort of state, allowing it to perform tasks such as sequence-prediction that are beyond the power of a standard [multilayer perceptron](./Multilayer_perceptron).

 

**[Jordan](./Michael_I._Jordan) networks** are similar to Elman networks. The context units are fed from the output layer instead of the hidden layer. The context units in a Jordan network are also called the state layer. They have a recurrent connection to themselves.[[51]](./Recurrent_neural_network#cite_note-bmm615-51)

 

Elman and Jordan networks are also known as "Simple recurrent networks" (SRN).

 Elman network[[52]](./Recurrent_neural_network#cite_note-52)          h  t      =  σ σ   h   (  W  h    x  t   +  U  h    h  t − −  1   +  b  h   )      y  t      =  σ σ   y   (  W  y    h  t   +  b  y   )       {\displaystyle {\begin{aligned}h_{t}&=\sigma _{h}(W_{h}x_{t}+U_{h}h_{t-1}+b_{h})\\y_{t}&=\sigma _{y}(W_{y}h_{t}+b_{y})\end{aligned}}}  ![{\displaystyle {\begin{aligned}h_{t}&=\sigma _{h}(W_{h}x_{t}+U_{h}h_{t-1}+b_{h})\\y_{t}&=\sigma _{y}(W_{y}h_{t}+b_{y})\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/983c33bfddb6c6d8b1bfdf9accf50bb5634e2f5a) Jordan network[[53]](./Recurrent_neural_network#cite_note-53)          h  t      =  σ σ   h   (  W  h    x  t   +  U  h    s  t   +  b  h   )      y  t      =  σ σ   y   (  W  y    h  t   +  b  y   )      s  t      =  σ σ   s   (  W  s , s    s  t − −  1   +  W  s , y    y  t − −  1   +  b  s   )       {\displaystyle {\begin{aligned}h_{t}&=\sigma _{h}(W_{h}x_{t}+U_{h}s_{t}+b_{h})\\y_{t}&=\sigma _{y}(W_{y}h_{t}+b_{y})\\s_{t}&=\sigma _{s}(W_{s,s}s_{t-1}+W_{s,y}y_{t-1}+b_{s})\end{aligned}}}  ![{\displaystyle {\begin{aligned}h_{t}&=\sigma _{h}(W_{h}x_{t}+U_{h}s_{t}+b_{h})\\y_{t}&=\sigma _{y}(W_{y}h_{t}+b_{y})\\s_{t}&=\sigma _{s}(W_{s,s}s_{t-1}+W_{s,y}y_{t-1}+b_{s})\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/da448ff637dcc68dbd497e10f7623c76c265b983) 

Variables and functions

 
-      x  t     {\displaystyle x_{t}}  ![{\displaystyle x_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f279a30bc8eabc788f3fe81c9cfb674e72e858db): input vector
-      h  t     {\displaystyle h_{t}}  ![{\displaystyle h_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e8dbf3d8bfe322f68ff6400385578f8d78e1ba7c): hidden layer vector
-      s  t     {\displaystyle s_{t}}  ![{\displaystyle s_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/92a402d151a0173378ee252a634c77898ebe4b06): "state" vector,
-      y  t     {\displaystyle y_{t}}  ![{\displaystyle y_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0fe9554452b93508c9d2479414a45981ecc75a2d): output vector
-     W   {\displaystyle W}  ![{\displaystyle W}](https://wikimedia.org/api/rest_v1/media/math/render/svg/54a9c4c547f4d6111f81946cad242b18298d70b7),     U   {\displaystyle U}  ![{\displaystyle U}](https://wikimedia.org/api/rest_v1/media/math/render/svg/458a728f53b9a0274f059cd695e067c430956025) and     b   {\displaystyle b}  ![{\displaystyle b}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f11423fbb2e967f986e36804a8ae4271734917c3): parameter matrices and vector
-     σ σ    {\displaystyle \sigma }  ![{\displaystyle \sigma }](https://wikimedia.org/api/rest_v1/media/math/render/svg/59f59b7c3e6fdb1d0365a494b81fb9a696138c36): [Activation functions](./Activation_function)

 

### Long short-term memory

 Main article: [Long short-term memory](./Long_short-term_memory) [![](//upload.wikimedia.org/wikipedia/commons/thumb/6/63/Long_Short-Term_Memory.svg/250px-Long_Short-Term_Memory.svg.png)](./File:Long_Short-Term_Memory.svg)Long short-term memory unit 

**Long short-term memory** (LSTM) is the most widely used RNN architecture. It was designed to solve the [vanishing gradient problem](./Vanishing_gradient_problem). LSTM is normally augmented by recurrent gates called "forget gates".[[54]](./Recurrent_neural_network#cite_note-gers2002-54) LSTM prevents backpropagated errors from vanishing or exploding.[[55]](./Recurrent_neural_network#cite_note-hochreiter1991-55) Instead, errors can flow backward through unlimited numbers of virtual layers unfolded in space. That is, LSTM can learn tasks that require memories of events that happened thousands or even millions of discrete time steps earlier. Problem-specific LSTM-like topologies can be evolved.[[56]](./Recurrent_neural_network#cite_note-bayer2009-56) LSTM works even given long delays between significant events and can handle signals that mix low and high-frequency components.

 

Many applications use stacks of LSTMs,[[57]](./Recurrent_neural_network#cite_note-fernandez2007-57) for which it is called "deep LSTM". LSTM can learn to recognize [context-sensitive languages](./Context-sensitive_languages) unlike previous models based on [hidden Markov models](./Hidden_Markov_model) (HMM) and similar concepts.[[58]](./Recurrent_neural_network#cite_note-peepholeLSTM-58)

 

### Gated recurrent unit

 Main article: [Gated recurrent unit](./Gated_recurrent_unit) [![](//upload.wikimedia.org/wikipedia/commons/thumb/5/5f/Gated_Recurrent_Unit.svg/250px-Gated_Recurrent_Unit.svg.png)](./File:Gated_Recurrent_Unit.svg)Gated recurrent unit 

**Gated recurrent unit** (GRU), introduced in 2014, was designed as a simplification of LSTM. They are used in the full form and several further simplified variants.[[59]](./Recurrent_neural_network#cite_note-59)[[60]](./Recurrent_neural_network#cite_note-60) They have fewer parameters than LSTM, as they lack an output gate.[[61]](./Recurrent_neural_network#cite_note-MyUser_Wildml.com_May_18_2016c-61)

 

Their performance on polyphonic music modeling and speech signal modeling was found to be similar to that of long short-term memory.[[62]](./Recurrent_neural_network#cite_note-MyUser_Arxiv.org_May_18_2016c2-62) There does not appear to be particular performance difference between LSTM and GRU.[[62]](./Recurrent_neural_network#cite_note-MyUser_Arxiv.org_May_18_2016c2-62)[[63]](./Recurrent_neural_network#cite_note-gruber_jockisch-63)

 

#### Bidirectional associative memory

 Main article: [Bidirectional associative memory](./Bidirectional_associative_memory) 

Introduced by [Bart Kosko](./Bart_Kosko),[[64]](./Recurrent_neural_network#cite_note-64) a bidirectional associative memory (BAM) network is a variant of a Hopfield network that stores associative data as a vector. The bidirectionality comes from passing information through a matrix and its [transpose](./Transpose). Typically, [bipolar encoding](./Bipolar_encoding) is preferred to binary encoding of the associative pairs. Recently, stochastic BAM models using [Markov](./Markov_chain) stepping are optimized for increased network stability and relevance to real-world applications.[[65]](./Recurrent_neural_network#cite_note-65)

 

A BAM network has two layers, either of which can be driven as an input to recall an association and produce an output on the other layer.[[66]](./Recurrent_neural_network#cite_note-66)

 

### Echo state

 Main article: [Echo state network](./Echo_state_network) 

[**Echo state networks**](./Echo_state_network) (ESN) have a sparsely connected random hidden layer. The weights of output neurons are the only part of the network that can change (be trained). ESNs are good at reproducing certain [time series](./Time_series).[[67]](./Recurrent_neural_network#cite_note-67) A variant for [spiking neurons](./Spiking_neural_network) is known as a [liquid state machine](./Liquid_state_machine).[[68]](./Recurrent_neural_network#cite_note-68)

 

### Recursive

 Main article: [Recursive neural network](./Recursive_neural_network) 

A **[recursive neural network](./Recursive_neural_network)**[[69]](./Recurrent_neural_network#cite_note-69) is created by applying the same set of weights [recursively](./Recursion) over a differentiable graph-like structure by traversing the structure in [topological order](./Topological_sort). Such networks are typically also trained by the reverse mode of [automatic differentiation](./Automatic_differentiation).[[70]](./Recurrent_neural_network#cite_note-lin1970-70)[[71]](./Recurrent_neural_network#cite_note-grie2008-71) They can process [distributed representations](./Distributed_representation) of structure, such as [logical terms](./Mathematical_logic). A special case of recursive neural networks is the RNN whose structure corresponds to a linear chain. Recursive neural networks have been applied to [natural language processing](./Natural_language_processing).[[72]](./Recurrent_neural_network#cite_note-72) The *recursive neural tensor network* uses a [tensor](./Tensor)-based composition function for all nodes in the tree.[[73]](./Recurrent_neural_network#cite_note-73)

 

### Neural Turing machines

 Main articles: [Neural Turing machine](./Neural_Turing_machine) and [Differentiable neural computer](./Differentiable_neural_computer) 

**Neural Turing machines** (NTMs) are a method of extending recurrent neural networks by coupling them to external [memory](./Memory) resources with which they interact. The combined system is analogous to a [Turing machine](./Turing_machine) or [Von Neumann architecture](./Von_Neumann_architecture) but is [differentiable](./Differentiable_neural_computer) end-to-end, allowing it to be efficiently trained with [gradient descent](./Gradient_descent).[[74]](./Recurrent_neural_network#cite_note-74)

 

**Differentiable neural computers** (DNCs) are an extension of neural Turing machines, allowing for the usage of fuzzy amounts of each memory address and a record of chronology.[[75]](./Recurrent_neural_network#cite_note-DNCnature2016-75)

 

**Neural network pushdown automata** (NNPDA) are similar to NTMs, but tapes are replaced by analog stacks that are differentiable and trained. In this way, they are similar in complexity to recognizers of [context free grammars](./Context_free_grammar) (CFGs).[[76]](./Recurrent_neural_network#cite_note-76)

 

Recurrent neural networks are [Turing complete](./Turing_complete) and can run arbitrary programs to process arbitrary sequences of inputs.[[77]](./Recurrent_neural_network#cite_note-77)

 


