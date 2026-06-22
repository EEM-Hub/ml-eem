---
source: sources/wiki-Deep_learning.md
source_url: https://en.wikipedia.org/wiki/Deep_learning
chunk: 1/7
---

Branch of machine learning For the TV series episode, see [Deep Learning (*South Park*)](./Deep_Learning_(South_Park)). [![Representing images on multiple layers of abstraction in deep learning](//upload.wikimedia.org/wikipedia/commons/thumb/2/26/Deep_Learning.jpg/500px-Deep_Learning.jpg)](./File:Deep_Learning.jpg)Representing images on multiple layers of abstraction in deep learning[[1]](./Deep_learning#cite_note-1) 
| Part ofa serieson |
| --- |
| Artificial intelligence (AI) |
| Major goalsArtificial general intelligenceIntelligent agentRecursive self-improvementPlanningComputer visionGeneral game playingKnowledge representationNatural language processingRoboticsAI safety |
| ApproachesMachine learningSymbolicDeep learningBayesian networksEvolutionary algorithmsNeuro-symbolic AISystems integrationOpen-sourceAI data centers |
| ApplicationsBioinformaticsDeepfakeEarth sciencesFinanceGenerative AIArtAudioMusicGovernmentHealthcareIndustrySoftware developmentTranslationMilitaryPhysicsProjects |
| PhilosophyAI alignmentArtificial consciousnessThe bitter lessonChinese roomFriendly AIEthicsExistential riskTuring testUncanny valleyHuman–AI interaction |
| HistoryTimelineProgressAI winterAI boomAI bubble |
| ControversiesDeepfake pornographyTaylor Swift deepfake pornography controversyGrok sexual deepfake scandalGoogle Gemini image generation controversyIt's the Most Terrible Time of the YearPause Giant AI ExperimentsRemoval of Sam Altman from OpenAIStatement on AI RiskTay (chatbot)Théâtre D'opéra SpatialVoiceverse NFT plagiarism scandal |
| GlossaryGlossary |
| vte |

 

In [machine learning](./Machine_learning), **deep learning** (**DL**) focuses on utilizing multilayered [neural networks](./Neural_network_(machine_learning)) to perform tasks such as [classification](./Statistical_classification), [regression](./Regression_analysis), and [representation learning](./Representation_learning). The field takes inspiration from [biological neuroscience](./Neuroscience) and revolves around stacking [artificial neurons](./Artificial_neuron) into layers and "training" them to process data. The adjective "deep" refers to the use of multiple layers (ranging from three to several hundred or thousands) in the network. Methods used can be [supervised](./Supervised_learning), [semi-supervised](./Semi-supervised_learning) or [unsupervised](./Unsupervised_learning).[[2]](./Deep_learning#cite_note-NatureBengio-2)

 

Some common deep learning network architectures include [fully connected networks](./Fully_connected_network), [deep belief networks](./Deep_belief_network), [recurrent neural networks](./Recurrent_neural_network), [convolutional neural networks](./Convolutional_neural_network), [generative adversarial networks](./Generative_adversarial_network), [transformers](./Transformer_(deep_learning)), and [neural radiance fields](./Neural_radiance_field). These architectures have been applied to fields including [computer vision](./Computer_vision), [speech recognition](./Speech_recognition), [natural language processing](./Natural_language_processing), [machine translation](./Machine_translation), [bioinformatics](./Bioinformatics), [drug design](./Drug_design), [medical image analysis](./Medical_image_analysis), [climate science](./Climatology), material inspection and [board game](./Board_game) programs, where they have produced results comparable to and in some cases surpassing human expert performance.[[3]](./Deep_learning#cite_note-:9-3)[[4]](./Deep_learning#cite_note-krizhevsky2012-4)[[5]](./Deep_learning#cite_note-5)

 

Early forms of neural networks were inspired by information processing and distributed communication nodes in [biological systems](./Biological_system), particularly the [human brain](./Human_brain). However, current neural networks do not intend to model the brain function of organisms, and are generally seen as low-quality models for that purpose.[[6]](./Deep_learning#cite_note-6)

  

## Overview

 

Most modern deep learning models are based on multi-layered [neural networks](./Neural_network_(machine_learning)) such as [convolutional neural networks](./Convolutional_neural_network) and [transformers](./Transformer_(neural_network)), although they can also include [propositional formulas](./Propositional_formula) or latent variables organized layer-wise in deep [generative models](./Generative_model) such as the nodes in [deep belief networks](./Deep_belief_network) and deep [Boltzmann machines](./Boltzmann_machine).[[7]](./Deep_learning#cite_note-BENGIODEEP-7)

 

Fundamentally, deep learning refers to a class of [machine learning](./Machine_learning) [algorithms](./Algorithm) in which a hierarchy of layers is used to transform input data into a progressively more abstract and composite representation. For example, in an [image recognition](./Image_recognition) model, the raw input may be an [image](./Image) (represented as a [tensor](./Tensor_(machine_learning)) of [pixels](./Pixel)). The first representational layer may attempt to identify basic shapes such as lines and circles, the second layer may compose and encode arrangements of edges, the third layer may encode a nose and eyes, and the fourth layer may recognize that the image contains a face.

 

Importantly, a deep learning process can learn which features to optimally place at which level *on its own*. Prior to deep learning, machine learning techniques often involved hand-crafted [feature engineering](./Feature_engineering) to transform the data into a more suitable representation for a classification algorithm to operate on. In the deep learning approach, features are not hand-crafted and the model [discovers](./Representation_learning) useful feature representations from the data automatically. This does not eliminate the need for hand-tuning; for example, varying numbers of layers and layer sizes can provide different degrees of abstraction.[[8]](./Deep_learning#cite_note-BENGIO2012-8)[[2]](./Deep_learning#cite_note-NatureBengio-2)

 

The word "deep" in "deep learning" refers to the number of layers through which the data is transformed. More precisely, deep learning systems have a substantial *credit assignment path* (CAP) depth. The CAP is the chain of transformations from input to output. CAPs describe potentially causal connections between input and output. For a [feedforward neural network](./Feedforward_neural_network), the depth of the CAPs is that of the network and is the number of hidden layers plus one (as the output layer is also parameterized). For [recurrent neural networks](./Recurrent_neural_network), in which a signal may propagate through a layer more than once, the CAP depth is potentially unlimited.[[9]](./Deep_learning#cite_note-SCHIDHUB-9) No universally agreed-upon threshold of depth divides shallow learning from deep learning, but most researchers agree that deep learning involves CAP depth higher than two. CAP of depth two has been shown to be a universal approximator in the sense that it can emulate any function.[[10]](./Deep_learning#cite_note-10)[*[citation needed](./Wikipedia:Citation_needed)*] Beyond that, more layers do not add to the function approximator ability of the network. Deep models (CAP > two) are able to extract better features than shallow models and hence, extra layers help in learning the features effectively.

 

Deep learning architectures can be constructed with a [greedy](./Greedy_algorithm) layer-by-layer method.[[11]](./Deep_learning#cite_note-BENGIO2007-11) Deep learning helps to disentangle these abstractions and pick out which features improve performance.[[8]](./Deep_learning#cite_note-BENGIO2012-8)

 

Deep learning algorithms can be applied to unsupervised learning tasks. This is an important benefit because unlabeled data is more abundant than labeled data. Examples of deep structures that can be trained in an unsupervised manner are [deep belief networks](./Deep_belief_network).[[8]](./Deep_learning#cite_note-BENGIO2012-8)[[12]](./Deep_learning#cite_note-SCHOLARDBNS-12)

 

The term *deep learning* was introduced to the machine learning community by [Rina Dechter](./Rina_Dechter) in 1986,[[13]](./Deep_learning#cite_note-dechter1986-13) and to artificial neural networks by Igor Aizenberg and colleagues in 2000, in the context of [Boolean](./Boolean_network) threshold neurons.[[14]](./Deep_learning#cite_note-MV_1-14)[[15]](./Deep_learning#cite_note-15) The etymology of the term is more complicated.[[16]](./Deep_learning#cite_note-16)

 

## Interpretations

 

Deep neural networks are generally interpreted in terms of the [universal approximation theorem](./Universal_approximation_theorem)[[17]](./Deep_learning#cite_note-cyb-17)[[18]](./Deep_learning#cite_note-horn-18)[[19]](./Deep_learning#cite_note-Haykin,_Simon_1998-19)[[20]](./Deep_learning#cite_note-Hassoun,_M._1995_p._48-20)[[21]](./Deep_learning#cite_note-ZhouLu-21) or [probabilistic inference](./Bayesian_inference).[[22]](./Deep_learning#cite_note-22)[[23]](./Deep_learning#cite_note-BOOK2014-23)[[8]](./Deep_learning#cite_note-BENGIO2012-8)[[9]](./Deep_learning#cite_note-SCHIDHUB-9)[[24]](./Deep_learning#cite_note-MURPHY-24)

 

The classic universal approximation theorem concerns the capacity of [feedforward neural networks](./Feedforward_neural_networks) with a single hidden layer of finite size to approximate [continuous functions](./Continuous_functions).[[17]](./Deep_learning#cite_note-cyb-17)[[18]](./Deep_learning#cite_note-horn-18)[[19]](./Deep_learning#cite_note-Haykin,_Simon_1998-19)[[20]](./Deep_learning#cite_note-Hassoun,_M._1995_p._48-20) In 1989, the first proof was published by [George Cybenko](./George_Cybenko) for [sigmoid](./Sigmoid_function) activation functions[[17]](./Deep_learning#cite_note-cyb-17) and was generalised to feed-forward multi-layer architectures in 1991 by Kurt Hornik.[[18]](./Deep_learning#cite_note-horn-18) Recent work also showed that universal approximation also holds for non-bounded activation functions such as [Kunihiko Fukushima](./Kunihiko_Fukushima)'s [rectified linear unit](./Rectified_linear_unit).[[25]](./Deep_learning#cite_note-Fukushima1969-25)[[26]](./Deep_learning#cite_note-sonoda17-26)

 

The universal approximation theorem for [deep neural networks](./Deep_neural_network) concerns the capacity of networks with bounded width but the depth is allowed to grow. Lu et al.[[21]](./Deep_learning#cite_note-ZhouLu-21) proved that if the width of a deep neural network with [ReLU](./ReLU) activation is strictly larger than the input dimension, then the network can approximate any [Lebesgue integrable function](./Lebesgue_integration); if the width is smaller or equal to the input dimension, then a deep neural network is not a universal approximator.

 

The [probabilistic](./Probabilistic) interpretation[[24]](./Deep_learning#cite_note-MURPHY-24) derives from the field of [machine learning](./Machine_learning). It features inference,[[23]](./Deep_learning#cite_note-BOOK2014-23)[[7]](./Deep_learning#cite_note-BENGIODEEP-7)[[8]](./Deep_learning#cite_note-BENGIO2012-8)[[9]](./Deep_learning#cite_note-SCHIDHUB-9)[[12]](./Deep_learning#cite_note-SCHOLARDBNS-12)[[24]](./Deep_learning#cite_note-MURPHY-24) as well as the [optimization](./Optimization) concepts of [training](./Training) and [testing](./Test_(assessment)), related to fitting and [generalization](./Generalization), respectively. More specifically, the probabilistic interpretation considers the activation nonlinearity as a [cumulative distribution function](./Cumulative_distribution_function).[[24]](./Deep_learning#cite_note-MURPHY-24) The probabilistic interpretation led to the introduction of [dropout](./Dropout_(neural_networks)) as [regularizer](./Regularization_(mathematics)) in neural networks. The probabilistic interpretation was introduced by researchers including [Hopfield](./John_Hopfield), [Widrow](./Bernard_Widrow) and [Narendra](./Kumpati_S._Narendra) and popularized in surveys such as the one by [Bishop](./Christopher_Bishop).[[27]](./Deep_learning#cite_note-prml-27)

 


