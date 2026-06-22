---
source: sources/wiki-Neural_network_28machine_learning29.md
source_url: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29
chunk: 3/10
---

## Elements

 
|  | This sectionmay beconfusing or unclearto readers.Please helpclarify the section. There might be a discussion about this onthe talk page.(April 2017)(Learn how and when to remove this message) |
| --- | --- |

Further information: [Mathematics of artificial neural networks](./Mathematics_of_artificial_neural_networks) [![](//upload.wikimedia.org/wikipedia/commons/thumb/4/44/Neuron3.png/250px-Neuron3.png)](./File:Neuron3.png)Neuron and myelinated axon, with signal flow from inputs at dendrites to outputs at axon terminals 

NNs began as an attempt to replicate the architecture of the brain in the digital realm. NNs immediately showed promise for handling non-linear relationships, but encountered obstacles. Models soon reoriented to applying mathematical insights to improve empirical results, at the expense of biological fidelity. 

 

### Neuron

 [![Artificial neuron structure](//upload.wikimedia.org/wikipedia/commons/thumb/c/c6/Artificial_neuron_structure.svg/330px-Artificial_neuron_structure.svg.png)](./File:Artificial_neuron_structure.svg)Structure of an artificial neuron 

NNs are composed of [digital neurons](./Artificial_neurons), conceptually derived from biological [neurons](./Neuron). Each neuron has one or more numerical inputs and produces a single numerical output.[[111]](./Neural_network_(machine_learning)#cite_note-Abbod20072-111) An input (e.g., an image) is typically parceled across the set of input neurons (each getting a piece of the image). Each neuron's inputs, [weighted](./Weight_function) by the weights of the connections from each of those inputs are summed. A bias term is added to this sum.[[112]](./Neural_network_(machine_learning)#cite_note-DAWSON19982-112)) The result is then passed through a nonlinear [activation function](./Activation_function) to produce the neuron's output. Small enough outputs may be zeroed out (ignored).[[113]](./Neural_network_(machine_learning)#cite_note-:52-113)[[114]](./Neural_network_(machine_learning)#cite_note-114)[[115]](./Neural_network_(machine_learning)#cite_note-115)

 

### Network

 

NNs connect neurons to each other, using the output of some neurons as the input of others, akin to biological [axon](./Axoneme)-[synapse](./Synapse)-[dendrite](./Matrix_(protocol)) connections.[[116]](./Neural_network_(machine_learning)#cite_note-Winston2-116) The network forms a [directed](./Directed_graph), [weighted graph](./Weighted_graph). The weights apply to both the graph's the nodes and edges.[[117]](./Neural_network_(machine_learning)#cite_note-Zell1994ch5.22-117)

 

Nodes are arranged in layers, with the bottom layers directly addressing raw data, while the top layers reveal the final results. Intermediate layers gradually increase the level of abstraction, so what began as for example, pixels in an image, gradually resolves into things such as object boundaries, and then into real-world objects such as letters and faces.[[117]](./Neural_network_(machine_learning)#cite_note-Zell1994ch5.22-117)[[113]](./Neural_network_(machine_learning)#cite_note-:52-113) Single layer and unlayered networks are also used.[*[citation needed](./Wikipedia:Citation_needed)*]

[![](//upload.wikimedia.org/wikipedia/commons/thumb/1/15/Neural_Network.svg/250px-Neural_Network.svg.png)](./File:Neural_Network.svg)Structure of a feedforward neural network with four layers 

Multiple connection patterns have been used. Traditionally, they are *fully connected*, with every neuron in one layer connecting to every neuron in the next layer.[[118]](./Neural_network_(machine_learning)#cite_note-118) However, in [convolutional neural networks](./Convolutional_neural_network), some layers are *convolutional,* meaning each neuron in one layer is connected to a subset of neurons in the previous layer, such as those representing one section of an image.[[119]](./Neural_network_(machine_learning)#cite_note-flexible2-119)[[120]](./Neural_network_(machine_learning)#cite_note-120)[*[clarification needed](./Wikipedia:Please_clarify)*]

 

In most neural networks,[*[citation needed](./Wikipedia:Citation_needed)*] the outputs of the neurons in one layer are connected only to neurons in the immediately  following layer ([directed acyclic graph](./Directed_acyclic_graph)), meaning information only flows forward from one layer to the next. These are known as [feedforward networks](./Feedforward_neural_network).[[121]](./Neural_network_(machine_learning)#cite_note-Zell1994p732-121) In contrast, networks that allow connections between neurons in the same or previous layers are known as [recurrent networks](./Recurrent_neural_network).[[122]](./Neural_network_(machine_learning)#cite_note-122)

 


