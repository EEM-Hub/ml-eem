---
source: sources/wiki-Recurrent_neural_network.md
source_url: https://en.wikipedia.org/wiki/Recurrent_neural_network
chunk: 4/7
---

## Training

 

### Teacher forcing

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/7/72/Seq2seq_RNN_encoder-decoder_with_attention_mechanism%2C_training_and_inferring.png/250px-Seq2seq_RNN_encoder-decoder_with_attention_mechanism%2C_training_and_inferring.png)](./File:Seq2seq_RNN_encoder-decoder_with_attention_mechanism,_training_and_inferring.png)Encoder-decoder RNN without attention mechanism. Teacher forcing is shown in red.

An RNN can be trained into a conditionally [generative model](./Generative_model) of sequences, aka **autoregression**.

 

Concretely, let us consider the problem of machine translation, that is, given a sequence     (  x  1   ,  x  2   , … …  ,  x  n   )   {\displaystyle (x_{1},x_{2},\dots ,x_{n})}  ![{\displaystyle (x_{1},x_{2},\dots ,x_{n})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7c0e6a4f6008f01547bb5cc1e8b01207272939e9) of English words, the model is to produce a sequence     (  y  1   , … …  ,  y  m   )   {\displaystyle (y_{1},\dots ,y_{m})}  ![{\displaystyle (y_{1},\dots ,y_{m})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1f788b82def8d7a3933ae95cc81463bde894ae57) of French words. It is to be solved by a [seq2seq](./Seq2seq) model.

 

Now, during training, the encoder half of the model would first ingest     (  x  1   ,  x  2   , … …  ,  x  n   )   {\displaystyle (x_{1},x_{2},\dots ,x_{n})}  ![{\displaystyle (x_{1},x_{2},\dots ,x_{n})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7c0e6a4f6008f01547bb5cc1e8b01207272939e9), then the decoder half would start generating a sequence     (     y ^ ^      1   ,     y ^ ^      2   , … …  ,     y ^ ^      l   )   {\displaystyle ({\hat {y}}_{1},{\hat {y}}_{2},\dots ,{\hat {y}}_{l})}  ![{\displaystyle ({\hat {y}}_{1},{\hat {y}}_{2},\dots ,{\hat {y}}_{l})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1c690f99611b8115d603410038d1c900eb099b69). The problem is that if the model makes a mistake early on, say at         y ^ ^      2     {\displaystyle {\hat {y}}_{2}}  ![{\displaystyle {\hat {y}}_{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2d678e9549266e3dfc09066e1145e3f7a13fd7d2), then subsequent tokens are likely to also be mistakes. This makes it inefficient for the model to obtain a learning signal, since the model would mostly learn to shift         y ^ ^      2     {\displaystyle {\hat {y}}_{2}}  ![{\displaystyle {\hat {y}}_{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2d678e9549266e3dfc09066e1145e3f7a13fd7d2) towards      y  2     {\displaystyle y_{2}}  ![{\displaystyle y_{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7377c7399e662562cd420fa5c7ce49cfba574998), but not the others.

 

**Teacher forcing** makes it so that the decoder uses the correct output sequence for generating the next entry in the sequence. So for example, it would see     (  y  1   , … …  ,  y  k   )   {\displaystyle (y_{1},\dots ,y_{k})}  ![{\displaystyle (y_{1},\dots ,y_{k})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/06fbc6292b20008e7ee5b70877d89c445b81f6d5) in order to generate         y ^ ^      k + 1     {\displaystyle {\hat {y}}_{k+1}}  ![{\displaystyle {\hat {y}}_{k+1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a1af03c401fbfdd242dd870b01707b2d946b0d68).

 

### Gradient descent

 Main articles: [Gradient descent](./Gradient_descent) and [Vanishing gradient problem](./Vanishing_gradient_problem) 

Gradient descent is a [first-order](./Category:First_order_methods) [iterative](./Iterative_algorithm) [optimization](./Mathematical_optimization) [algorithm](./Algorithm) for finding the minimum of a function. In neural networks, it can be used to minimize the error term by changing each weight in proportion to the derivative of the error with respect to that weight, provided the non-linear [activation functions](./Activation_function) are [differentiable](./Differentiable_function).

 

The standard method for training RNN by gradient descent is the "[backpropagation through time](./Backpropagation_through_time)" (BPTT) algorithm, which is a special case of the general algorithm of [backpropagation](./Backpropagation). A more computationally expensive online variant is called "Real-Time Recurrent Learning" or RTRL,[[78]](./Recurrent_neural_network#cite_note-78)[[79]](./Recurrent_neural_network#cite_note-79) which is an instance of [automatic differentiation](./Automatic_differentiation) in the forward accumulation mode with stacked tangent vectors. Unlike BPTT, this algorithm is [local](./Local_algorithm) in time but not local in space.

 

In this context, local in space means that a unit's weight vector can be updated using only information stored in the connected units and the unit itself such that update complexity of a single unit is linear in the dimensionality of the weight vector. Local in time means that the updates take place continually (on-line) and depend only on the most recent time step rather than on multiple time steps within a given time horizon as in BPTT. Biological neural networks appear to be local with respect to both time and space.[[80]](./Recurrent_neural_network#cite_note-80)[[81]](./Recurrent_neural_network#cite_note-PríncipeEuliano2000-81)

 

For recursively computing the partial derivatives, RTRL has a time-complexity of O(number of hidden x number of weights) per time step for computing the [Jacobian matrices](./Jacobian_matrix), while BPTT only takes O(number of weights) per time step, at the cost of storing all forward activations within the given time horizon.[[82]](./Recurrent_neural_network#cite_note-Ollivier2015-82) An online hybrid between BPTT and RTRL with intermediate complexity exists,[[83]](./Recurrent_neural_network#cite_note-83)[[84]](./Recurrent_neural_network#cite_note-84) along with variants for continuous time.[[85]](./Recurrent_neural_network#cite_note-85)

 

A major problem with gradient descent for standard RNN architectures is that [error gradients vanish](./Vanishing_gradient_problem) exponentially quickly with the size of the time lag between important events.[[55]](./Recurrent_neural_network#cite_note-hochreiter1991-55)[[86]](./Recurrent_neural_network#cite_note-HOCH2001-86) LSTM combined with a BPTT/RTRL hybrid learning method attempts to overcome these problems.[[36]](./Recurrent_neural_network#cite_note-lstm-36) This problem is also solved in the independently recurrent neural network (IndRNN)[[87]](./Recurrent_neural_network#cite_note-auto-87) by reducing the context of a neuron to its own past state and the cross-neuron information can then be explored in the following layers. Memories of different ranges including long-term memory can be learned without the gradient vanishing and exploding problems.

 

The [online algorithm](./Online_algorithm) called **causal recursive backpropagation** (CRBP), implements and combines BPTT and RTRL paradigms for locally recurrent networks.[[88]](./Recurrent_neural_network#cite_note-88) It works with the most general locally recurrent networks. The CRBP algorithm can minimize the global error term. This fact improves the stability of the algorithm, providing a unifying view of gradient calculation techniques for recurrent networks with local feedback.

 

One approach to gradient information computation in RNNs with arbitrary architectures is based on signal-flow graphs diagrammatic derivation.[[89]](./Recurrent_neural_network#cite_note-89) It uses the BPTT batch algorithm, based on Lee's theorem for network sensitivity calculations.[[90]](./Recurrent_neural_network#cite_note-ReferenceA-90) It was proposed by Wan and Beaufays, while its fast online version was proposed by Campolucci, Uncini and Piazza.[[90]](./Recurrent_neural_network#cite_note-ReferenceA-90)

 

### Connectionist temporal classification

 

The [connectionist temporal classification](./Connectionist_temporal_classification) (CTC)[[91]](./Recurrent_neural_network#cite_note-graves2006-91) is a specialized loss function for training RNNs for sequence modeling problems where the timing is variable.[[92]](./Recurrent_neural_network#cite_note-92)

 

### Global optimization methods

 

Training the weights in a neural network can be modeled as a non-linear [global optimization](./Global_optimization) problem. A target function can be formed to evaluate the fitness or error of a particular weight vector as follows: First, the weights in the network are set according to the weight vector. Next, the network is evaluated against the training sequence. Typically, the sum-squared difference between the predictions and the target values specified in the training sequence is used to represent the error of the current weight vector. Arbitrary global optimization techniques may then be used to minimize this target function.

 

The most common global optimization method for training RNNs is [genetic algorithms](./Genetic_algorithm), especially in unstructured networks.[[93]](./Recurrent_neural_network#cite_note-93)[[94]](./Recurrent_neural_network#cite_note-94)[[95]](./Recurrent_neural_network#cite_note-95)

 

Initially, the genetic algorithm is encoded with the neural network weights in a predefined manner where one gene in the [chromosome](./Chromosome_(genetic_algorithm)) represents one weight link. The whole network is represented as a single chromosome. The fitness function is evaluated as follows:

 
- Each weight encoded in the chromosome is assigned to the respective weight link of the network.
- The training set is presented to the network which propagates the input signals forward.
- The mean-squared error is returned to the fitness function.
- This function drives the genetic selection process.

 

Many chromosomes make up the population; therefore, many different neural networks are evolved until a stopping criterion is satisfied. A common stopping scheme can be: 

 
- When the neural network has learned a certain percentage of the training data.
- When the minimum value of the mean-squared-error is satisfied.
- When the maximum number of training generations has been reached.

 

The fitness function evaluates the stopping criterion as it receives the mean-squared error reciprocal from each network during training. Therefore, the goal of the genetic algorithm is to maximize the fitness function, reducing the mean-squared error.

 

Other global (and/or evolutionary) optimization techniques may be used to seek a good set of weights, such as [simulated annealing](./Simulated_annealing) or [particle swarm optimization](./Particle_swarm_optimization).

 


