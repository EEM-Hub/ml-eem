---
source: sources/wiki-Backpropagation.md
source_url: https://en.wikipedia.org/wiki/Backpropagation
chunk: 3/8
---

## Intuition

 

### Motivation

 

The goal of any [supervised learning](./Supervised_learning) algorithm is to find a function that best maps a set of inputs to their correct output. The motivation for backpropagation is to train a multi-layered neural network such that it can learn the appropriate internal representations to allow it to learn any arbitrary mapping of input to output.[[5]](./Backpropagation#cite_note-RumelhartHintonWilliams1986a-11)

 

### Learning as an optimization problem

To understand the mathematical derivation of the backpropagation algorithm, it helps to first develop some intuition about the relationship between the actual output of a neuron and the correct output for a particular training example. Consider a simple neural network with two input units, one output unit and no hidden units, and in which each neuron uses a [linear output](./Artificial_neuron#Linear_combination) (unlike most work on neural networks, in which mapping from inputs to outputs is non-linear)[[g]](./Backpropagation#cite_note-12) that is the weighted sum of its input. 

[![](//upload.wikimedia.org/wikipedia/commons/thumb/4/42/A_simple_neural_network_with_two_input_units_and_one_output_unit.png/250px-A_simple_neural_network_with_two_input_units_and_one_output_unit.png)](./File:A_simple_neural_network_with_two_input_units_and_one_output_unit.png)A simple neural network with two input units (each with a single input) and one output unit (with two inputs) 

Initially, before training, the weights will be set randomly. Then the neuron learns from [training examples](./Training_set), which in this case consist of a set of [tuples](./Tuple)     (  x  1   ,  x  2   , t )   {\displaystyle (x_{1},x_{2},t)}  ![{\displaystyle (x_{1},x_{2},t)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/dbc9205ba047983879ece2f78ff0cf1f7525bdd5) where      x  1     {\displaystyle x_{1}}  ![{\displaystyle x_{1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a8788bf85d532fa88d1fb25eff6ae382a601c308) and      x  2     {\displaystyle x_{2}}  ![{\displaystyle x_{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d7af1b928f06e4c7e3e8ebfd60704656719bd766) are the inputs to the network and t is the correct output (the output the network should produce given those inputs, when it has been trained). The initial network, given      x  1     {\displaystyle x_{1}}  ![{\displaystyle x_{1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a8788bf85d532fa88d1fb25eff6ae382a601c308) and      x  2     {\displaystyle x_{2}}  ![{\displaystyle x_{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d7af1b928f06e4c7e3e8ebfd60704656719bd766), will compute an output y that likely differs from t (given random weights). A [loss function](./Loss_function)     L ( t , y )   {\displaystyle L(t,y)}  ![{\displaystyle L(t,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a6d0d207e3b5787cffb4f86784345fe4393893fe) is used for measuring the discrepancy between the target output t and the computed output y. For [regression analysis](./Regression_analysis) problems the squared error can be used as a loss function, for [classification](./Statistical_classification) the [categorical cross-entropy](./Cross-entropy) can be used.

 

As an example consider a regression problem using the square error as a loss:

     L ( t , y ) = ( t − −  y  )  2   = E ,   {\displaystyle L(t,y)=(t-y)^{2}=E,}  ![{\displaystyle L(t,y)=(t-y)^{2}=E,}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ca7e3b55f443f8e490f1e6e552470f93802e5e43) 

where E is the discrepancy or error.

 

Consider the network on a single training case:     ( 1 , 1 , 0 )   {\displaystyle (1,1,0)}  ![{\displaystyle (1,1,0)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5568de79a98cdcb48821cd81b670c095fa4c8b6f). Thus, the input      x  1     {\displaystyle x_{1}}  ![{\displaystyle x_{1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a8788bf85d532fa88d1fb25eff6ae382a601c308) and      x  2     {\displaystyle x_{2}}  ![{\displaystyle x_{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d7af1b928f06e4c7e3e8ebfd60704656719bd766) are 1 and 1 respectively and the correct output, t is 0. Now if the relation is plotted between the network's output y on the horizontal axis and the error E on the vertical axis, the result is a parabola. The [minimum](./Maxima_and_minima) of the [parabola](./Parabola) corresponds to the output y which minimizes the error E. For a single training case, the minimum also touches the horizontal axis, which means the error will be zero and the network can produce an output y that exactly matches the target output t. Therefore, the problem of mapping inputs to outputs can be reduced to an [optimization problem](./Optimization_problem) of finding a function that will produce the minimal error. 

[![](//upload.wikimedia.org/wikipedia/commons/thumb/f/f7/Error_surface_of_a_linear_neuron_for_a_single_training_case.png/250px-Error_surface_of_a_linear_neuron_for_a_single_training_case.png)](./File:Error_surface_of_a_linear_neuron_for_a_single_training_case.png)Error surface of a linear neuron for a single training case 

However, the output of a neuron depends on the weighted sum of all its inputs:

     y =  x  1    w  1   +  x  2    w  2   ,   {\displaystyle y=x_{1}w_{1}+x_{2}w_{2},}  ![{\displaystyle y=x_{1}w_{1}+x_{2}w_{2},}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6297e881012aa2988838c056f86c589828b80e7d) 

where      w  1     {\displaystyle w_{1}}  ![{\displaystyle w_{1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f6728d2b30f42f88b52281be5ae0584fdc9df64) and      w  2     {\displaystyle w_{2}}  ![{\displaystyle w_{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8998e0957bb573a19e7d9d934ced62ee68ab8fb8) are the weights on the connection from the input units to the output unit. Therefore, the error also depends on the incoming weights to the neuron, which is ultimately what needs to be changed in the network to enable learning.

 

In this example, upon injecting the training data     ( 1 , 1 , 0 )   {\displaystyle (1,1,0)}  ![{\displaystyle (1,1,0)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5568de79a98cdcb48821cd81b670c095fa4c8b6f), the loss function becomes

 

    E = ( t − −  y  )  2   =  y  2   = (  x  1    w  1   +  x  2    w  2    )  2   = (  w  1   +  w  2    )  2   .   {\displaystyle E=(t-y)^{2}=y^{2}=(x_{1}w_{1}+x_{2}w_{2})^{2}=(w_{1}+w_{2})^{2}.}  ![{\displaystyle E=(t-y)^{2}=y^{2}=(x_{1}w_{1}+x_{2}w_{2})^{2}=(w_{1}+w_{2})^{2}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9642579185c542b0e8312a7edeeacf6abbb8934f)

 

Then, the loss function     E   {\displaystyle E}  ![{\displaystyle E}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4232c9de2ee3eec0a9c0a19b15ab92daa6223f9b) takes the form of a parabolic cylinder with its base directed along      w  1   = − −   w  2     {\displaystyle w_{1}=-w_{2}}  ![{\displaystyle w_{1}=-w_{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/839b25f7684ef2b1c6f960f962d64c0e993520b2). Since all sets of weights that satisfy      w  1   = − −   w  2     {\displaystyle w_{1}=-w_{2}}  ![{\displaystyle w_{1}=-w_{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/839b25f7684ef2b1c6f960f962d64c0e993520b2) minimize the loss function, in this case additional constraints are required to converge to a unique solution. Additional constraints could either be generated by setting specific conditions to the weights, or by injecting additional training data.

 

One commonly used algorithm to find the set of weights that minimizes the error is [gradient descent](./Gradient_descent). By backpropagation, the steepest descent direction is calculated of the loss function versus the present synaptic weights. Then, the weights can be modified along the steepest descent direction, and the error is minimized in an efficient way.

 


