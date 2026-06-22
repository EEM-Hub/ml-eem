---
source: sources/wiki-Convolutional_neural_network.md
source_url: https://en.wikipedia.org/wiki/Convolutional_neural_network
chunk: 5/8
---

## Applications

 

### Image recognition

 

CNNs are often used in [image recognition](./Image_recognition) systems. In 2012, an [error rate](./Per-comparison_error_rate) of 0.23% on the [MNIST database](./MNIST_database) was reported.[[28]](./Convolutional_neural_network#cite_note-mcdns-28) Another paper on using CNN for image classification reported that the learning process was "surprisingly fast"; in the same paper, the best published results as of 2011 were achieved in the MNIST database and the NORB database.[[25]](./Convolutional_neural_network#cite_note-flexible-25) Subsequently, a similar CNN called [AlexNet](./AlexNet)[[104]](./Convolutional_neural_network#cite_note-quartz-107) won the [ImageNet Large Scale Visual Recognition Challenge](./ImageNet_Large_Scale_Visual_Recognition_Challenge) 2012.

 

When applied to [facial recognition](./Facial_recognition_system), CNNs achieved a large decrease in error rate.[[105]](./Convolutional_neural_network#cite_note-108) Another paper reported a 97.6% recognition rate on "5,600 still images of more than 10 subjects".[[21]](./Convolutional_neural_network#cite_note-robust_face_detection-21) CNNs were used to assess [video quality](./Video_quality) in an objective way after manual training; the resulting system had a very low [root mean square error](./Root_mean_square_error).[[106]](./Convolutional_neural_network#cite_note-video_quality-109)

 

The [ImageNet Large Scale Visual Recognition Challenge](./ImageNet_Large_Scale_Visual_Recognition_Challenge) is a benchmark in object classification and detection, with millions of images and hundreds of object classes. In the ILSVRC 2014,[[107]](./Convolutional_neural_network#cite_note-ILSVRC2014-110) a large-scale visual recognition challenge, almost every highly ranked team used CNN as their basic framework. The winner [GoogLeNet](./GoogLeNet)[[108]](./Convolutional_neural_network#cite_note-googlenet-111) (the foundation of [DeepDream](./DeepDream)) increased the mean average [precision](./Precision_and_recall) of object detection to 0.439329, and reduced classification error to 0.06656, the best result to date. Its network applied more than 30 layers. That performance of convolutional neural networks on the ImageNet tests was close to that of humans.[[109]](./Convolutional_neural_network#cite_note-112) The best algorithms still struggle with objects that are small or thin, such as a small ant on a stem of a flower or a person holding a quill in their hand. They also have trouble with images that have been distorted with filters, an increasingly common phenomenon with modern digital cameras. By contrast, those kinds of images rarely trouble humans. Humans, however, tend to have trouble with other issues. For example, they are not good at classifying objects into fine-grained categories such as the particular breed of dog or species of bird, whereas convolutional neural networks handle this.[*[citation needed](./Wikipedia:Citation_needed)*]

 

In 2015, a many-layered CNN demonstrated the ability to spot faces from a wide range of angles, including upside down, even when partially occluded, with competitive performance. The network was trained on a database of 200,000 images that included faces at various angles and orientations and a further 20 million images without faces. They used batches of 128 images over 50,000 iterations.[[110]](./Convolutional_neural_network#cite_note-113)

 

### Video analysis

 

Compared to image data domains, there is relatively little work on applying CNNs to video classification. Video is more complex than images since it has another (temporal) dimension. However, some extensions of CNNs into the video domain have been explored. One approach is to treat space and time as equivalent dimensions of the input and perform convolutions in both time and space.[[111]](./Convolutional_neural_network#cite_note-114)[[112]](./Convolutional_neural_network#cite_note-115) Another way is to fuse the features of two convolutional neural networks, one for the spatial and one for the temporal stream.[[113]](./Convolutional_neural_network#cite_note-116)[[114]](./Convolutional_neural_network#cite_note-117)[[115]](./Convolutional_neural_network#cite_note-118) [Long short-term memory](./Long_short-term_memory) (LSTM) [recurrent](./Recurrent_neural_network) units are typically incorporated after the CNN to account for inter-frame or inter-clip dependencies.[[116]](./Convolutional_neural_network#cite_note-Wang_Duan_Zhang_Niu_p=1657-119)[[117]](./Convolutional_neural_network#cite_note-Duan_Wang_Zhai_Zheng_2018_p.-120) [Unsupervised learning](./Unsupervised_learning) schemes for training spatio-temporal features have been introduced, based on convolutional gated restricted [Boltzmann machines](./Boltzmann_machine)[[118]](./Convolutional_neural_network#cite_note-121) and independent subspace analysis.[[119]](./Convolutional_neural_network#cite_note-122) Its application can be seen in [text-to-video models](./Text-to-video_model).[*[citation needed](./Wikipedia:Citation_needed)*]

 

### Natural language processing

 

CNNs have also been explored for [natural language processing](./Natural_language_processing). CNN models are effective for various NLP problems and achieved excellent results in [semantic parsing](./Semantic_parsing),[[120]](./Convolutional_neural_network#cite_note-123) search query retrieval,[[121]](./Convolutional_neural_network#cite_note-124) sentence modeling,[[122]](./Convolutional_neural_network#cite_note-125) classification,[[123]](./Convolutional_neural_network#cite_note-126) prediction[[124]](./Convolutional_neural_network#cite_note-127) and other traditional NLP tasks.[[125]](./Convolutional_neural_network#cite_note-128)
Compared to traditional language processing methods such as [recurrent neural networks](./Recurrent_neural_networks), CNNs can represent different contextual realities of language that do not rely on a series-sequence assumption, while RNNs are better suitable when classical time series modeling is required.[[126]](./Convolutional_neural_network#cite_note-129)[[127]](./Convolutional_neural_network#cite_note-130)[[128]](./Convolutional_neural_network#cite_note-131)[[129]](./Convolutional_neural_network#cite_note-132)

 

### Animal behavior detection

 

CNNs have been applied in ecological and behavioral research to automatically detect and quantify animal behavior from visual data,[[130]](./Convolutional_neural_network#cite_note-133)[[131]](./Convolutional_neural_network#cite_note-:7-134) enabling identification of animals,[[132]](./Convolutional_neural_network#cite_note-135)[[133]](./Convolutional_neural_network#cite_note-136) tracking of individuals,[[134]](./Convolutional_neural_network#cite_note-137) estimation of pose,[[135]](./Convolutional_neural_network#cite_note-138)[[136]](./Convolutional_neural_network#cite_note-139)[[137]](./Convolutional_neural_network#cite_note-140) and classification of specific actions such as feeding,[[138]](./Convolutional_neural_network#cite_note-:8-141) and social interactions.[[131]](./Convolutional_neural_network#cite_note-:7-134)[[138]](./Convolutional_neural_network#cite_note-:8-141) Combined with multi-object tracking and temporal modeling, these systems can extract behavioral sequences over extended recordings, reducing reliance on manual annotation and increasing throughput for studies of individual variation, social networks, and collective dynamics.

 

### Anomaly detection

 

A CNN with 1-D convolutions was used on time series in the frequency domain (spectral residual) by an unsupervised model to detect anomalies in the time domain.[[139]](./Convolutional_neural_network#cite_note-142)

 

### Drug discovery

 

CNNs have been used in [drug discovery](./Drug_discovery). Predicting the interaction between molecules and biological [proteins](./Protein) can identify potential treatments. In 2015, Atomwise introduced AtomNet, the first deep learning neural network for [structure-based drug design](./Structure-based_drug_design).[[140]](./Convolutional_neural_network#cite_note-143) The system trains directly on 3-dimensional representations of chemical interactions. Similar to how image recognition networks learn to compose smaller, spatially proximate features into larger, complex structures,[[141]](./Convolutional_neural_network#cite_note-144) AtomNet discovers chemical features, such as [aromaticity](./Aromaticity), [sp3 carbons](./Orbital_hybridisation), and [hydrogen bonding](./Hydrogen_bond). Subsequently, AtomNet was used to predict novel candidate [biomolecules](./Biomolecule) for multiple disease targets, most notably treatments for the [Ebola virus](./Ebola_virus)[[142]](./Convolutional_neural_network#cite_note-145) and [multiple sclerosis](./Multiple_sclerosis).[[143]](./Convolutional_neural_network#cite_note-146)

 

### Checkers game

 

CNNs have been used in the game of [checkers](./Draughts). From 1999 to 2001, [Fogel](./David_B._Fogel) and Chellapilla published papers showing how a convolutional neural network could learn to play checkers using co-evolution. The learning process did not use prior human professional games, but rather focused on a minimal set of information contained in the checkerboard: the location and type of pieces, and the difference in number of pieces between the two sides. Ultimately, the program ([Blondie24](./Blondie24)) was tested on 165 games against players and ranked in the highest 0.4%.[[144]](./Convolutional_neural_network#cite_note-147)[[145]](./Convolutional_neural_network#cite_note-148) It also earned a win against the program [Chinook](./Chinook_(draughts_player)) at its "expert" level of play.[[146]](./Convolutional_neural_network#cite_note-149)

 

### Go

 

CNNs have been used in [computer Go](./Computer_Go). In December 2014, Clark and [Storkey](./Amos_Storkey) published a paper showing that a CNN trained by supervised learning from a database of human professional games could outperform [GNU Go](./GNU_Go) and win some games against [Monte Carlo tree search](./Monte_Carlo_tree_search) Fuego 1.1 in a fraction of the time it took Fuego to play.[[147]](./Convolutional_neural_network#cite_note-150) Later it was announced that a large 12-layer convolutional neural network had correctly predicted the professional move in 55% of positions, equalling the accuracy of a [6 dan](./Go_ranks_and_ratings) human player. When the trained convolutional network was used directly to play games of Go, without any search, it beat the traditional search program GNU Go in 97% of games, and matched the performance of the [Monte Carlo tree search](./Monte_Carlo_tree_search) program Fuego simulating ten thousand playouts (about a million positions) per move.[[148]](./Convolutional_neural_network#cite_note-151)

 

A couple of CNNs for choosing moves to try ("policy network") and evaluating positions ("value network") driving MCTS were used by [AlphaGo](./AlphaGo), the first to beat the best human player at the time.[[149]](./Convolutional_neural_network#cite_note-152)

 

### Time series forecasting

 

Recurrent neural networks are generally considered the best neural network architectures for time series forecasting (and sequence modeling in general), but recent studies show that convolutional networks can perform comparably or even better.[[150]](./Convolutional_neural_network#cite_note-153)[[13]](./Convolutional_neural_network#cite_note-Tsantekidis_7–12-13) Dilated convolutions[[151]](./Convolutional_neural_network#cite_note-154) might enable one-dimensional convolutional neural networks to effectively learn time series dependences.[[152]](./Convolutional_neural_network#cite_note-155) Convolutions can be implemented more efficiently than RNN-based solutions, and they do not suffer from vanishing (or exploding) gradients.[[153]](./Convolutional_neural_network#cite_note-156) Convolutional networks can provide an improved forecasting performance when there are multiple similar time series to learn from.[[154]](./Convolutional_neural_network#cite_note-157) CNNs can also be applied to further tasks in time series analysis (e.g., time series classification[[155]](./Convolutional_neural_network#cite_note-158) or quantile forecasting[[156]](./Convolutional_neural_network#cite_note-159)).

 

### Cultural heritage and 3D-datasets

 

As archaeological findings such as [clay tablets](./Clay_tablet) with [cuneiform writing](./Cuneiform) are increasingly acquired using [3D scanners](./3D_scanner), benchmark datasets are becoming available, including *HeiCuBeDa*[[157]](./Convolutional_neural_network#cite_note-HeiCuBeDa_Hilprecht-160) providing almost 2000 normalized 2-D and 3-D datasets prepared with the [GigaMesh Software Framework](./GigaMesh_Software_Framework).[[158]](./Convolutional_neural_network#cite_note-ICDAR19-161) So [curvature](./Curvature)-based measures are used in conjunction with geometric neural networks (GNNs), e.g. for period classification of those clay tablets being among the oldest documents of human history.[[159]](./Convolutional_neural_network#cite_note-ICFHR20-162)[[160]](./Convolutional_neural_network#cite_note-ICFHR20_Presentation-163)

 

## Fine-tuning

 

For many applications, training data is not very available. Convolutional neural networks usually require a large amount of training data in order to avoid [overfitting](./Overfitting). A common technique is to train the network on a larger data set from a related domain. Once the network parameters have converged an additional training step is performed using the in-domain data to fine-tune the network weights, this is known as [transfer learning](./Transfer_learning). Furthermore, this technique allows convolutional network architectures to successfully be applied to problems with tiny training sets.[[161]](./Convolutional_neural_network#cite_note-164)

 

## Human interpretable explanations

 

End-to-end training and prediction are common practice in [computer vision](./Computer_vision). However, human interpretable explanations are required for [critical systems](./Safety-critical_system) such as [self-driving cars](./Self-driving_car).[[162]](./Convolutional_neural_network#cite_note-Interpretable_ML_Symposium_2017-165) With recent advances in [visual salience](./Salience_(neuroscience)), [spatial attention](./Visual_spatial_attention), and [temporal attention](./Visual_temporal_attention), the most critical spatial regions/temporal instants could be visualized to justify the CNN predictions.[[163]](./Convolutional_neural_network#cite_note-Zang_Wang_Liu_Zhang_2018_pp._97–108-166)[[164]](./Convolutional_neural_network#cite_note-Wang_Zang_Zhang_Niu_p=1979-167)

 

## Related architectures

 

### Deep Q-networks

 

A deep Q-network (DQN) is a type of deep learning model that combines a deep neural network with [Q-learning](./Q-learning), a form of [reinforcement learning](./Reinforcement_learning). Unlike earlier reinforcement learning agents, DQNs that utilize CNNs can learn directly from high-dimensional sensory inputs via reinforcement learning.[[165]](./Convolutional_neural_network#cite_note-Ong_Chavez_Hong_2015-168)

 

Preliminary results were presented in 2014, with an accompanying paper in February 2015.[[166]](./Convolutional_neural_network#cite_note-DQN-169) The research described an application to [Atari 2600](./Atari_2600) gaming. Other deep reinforcement learning models preceded it.[[167]](./Convolutional_neural_network#cite_note-170)

 

### Deep belief networks

 Main article: [Deep belief network](./Deep_belief_network) 

[Convolutional deep belief networks](./Convolutional_deep_belief_network) (CDBN) have structure very similar to convolutional neural networks and are trained similarly to deep belief networks. Therefore, they exploit the 2D structure of images, like CNNs do, and make use of pre-training like [deep belief networks](./Deep_belief_network). They provide a generic structure that can be used in many image and signal processing tasks. Benchmark results on standard image datasets like CIFAR[[168]](./Convolutional_neural_network#cite_note-CDBN-CIFAR-171) have been obtained using CDBNs.[[169]](./Convolutional_neural_network#cite_note-CDBN-172)

[![Neural Abstraction Pyramid](//upload.wikimedia.org/wikipedia/commons/thumb/d/d9/Neural_Abstraction_Pyramid.jpg/250px-Neural_Abstraction_Pyramid.jpg)](./File:Neural_Abstraction_Pyramid.jpg)Neural abstraction pyramid 

### Neural abstraction pyramid

 

The feed-forward architecture of convolutional neural networks was extended in the neural abstraction pyramid[[170]](./Convolutional_neural_network#cite_note-173) by lateral and feedback connections. The resulting recurrent convolutional network allows for the flexible incorporation of contextual information to iteratively resolve local ambiguities. In contrast to previous models, image-like outputs at the highest resolution were generated, e.g., for semantic segmentation, image reconstruction, and object localization tasks.

 

## Notable libraries

 
- [Caffe](./Caffe_(software)): A library for convolutional neural networks. Created by the Berkeley Vision and Learning Center (BVLC). It supports both CPU and GPU. Developed in [C++](./C++), and has [Python](./Python_(programming_language)) and [MATLAB](./MATLAB) wrappers.
- [Deeplearning4j](./Deeplearning4j): Deep learning in [Java](./Java_(programming_language)) and [Scala](./Scala_(programming_language)) on multi-GPU-enabled [Spark](./Apache_Spark). A general-purpose deep learning library for the JVM production stack running on a C++ scientific computing engine. Allows the creation of custom layers. Integrates with Hadoop and Kafka.
- [Dlib](./Dlib): A toolkit for making real world machine learning and data analysis applications in C++.
- [Microsoft Cognitive Toolkit](./Microsoft_Cognitive_Toolkit): A deep learning toolkit written by Microsoft with several unique features enhancing scalability over multiple nodes. It supports full-fledged interfaces for training in C++ and Python and with additional support for model inference in [C#](./C_Sharp_(programming_language)) and Java.
- [TensorFlow](./TensorFlow): [Apache 2.0](./Apache_License#Version_2.0)-licensed Theano-like library with support for CPU, GPU, Google's proprietary [tensor processing unit](./Tensor_processing_unit) (TPU),[[171]](./Convolutional_neural_network#cite_note-174) and mobile devices.
- [Theano](./Theano_(software)): The reference deep-learning library for Python with an API largely compatible with the popular [NumPy](./NumPy) library. Allows user to write symbolic mathematical expressions, then automatically generates their derivatives, saving the user from having to code gradients or backpropagation. These symbolic expressions are automatically compiled to [CUDA](./CUDA) code for a fast, [on-the-GPU](./Compute_kernel) implementation.
- [Torch](./Torch_(machine_learning)): A [scientific computing](./Scientific_computing) framework with wide support for machine learning algorithms, written in [C](./C_(programming_language)) and [Lua](./Lua_(programming_language)).

 

## See also

 
- [Attention (machine learning)](./Attention_(machine_learning))
- [Circuit (neural network)](./Circuit_(neural_network))
- [Convolution](./Convolution)
- [Deep learning](./Deep_learning)
- [Natural-language processing](./Natural-language_processing)
- [Neocognitron](./Neocognitron)
- [Scale-invariant feature transform](./Scale-invariant_feature_transform)
- [Time delay neural network](./Time_delay_neural_network)
- [Vision processing unit](./Vision_processing_unit)

 


