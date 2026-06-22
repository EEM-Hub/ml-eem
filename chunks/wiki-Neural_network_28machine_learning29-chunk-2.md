---
source: sources/wiki-Neural_network_28machine_learning29.md
source_url: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29
chunk: 2/10
---

## History

 Main article: [History of artificial neural networks](./History_of_artificial_neural_networks) 
|  | This sectionrelies largely or entirely on asingle source.Relevant discussion may be found on thetalk page. Please helpimprove this articlebyintroducing  citations to additional sources.Find sources:"Neural network"machine learning–news·newspapers·books·scholar·JSTOR(March 2026) |
| --- | --- |

 

### Mathematical foundations

 

Deep neural networks are based on [statistics](./Statistics) developed over 200 years ago. The simplest kind of [feedforward neural network](./Feedforward_neural_network) (FNN) is a linear network, which consists of a single layer of output nodes with linear activation functions; the inputs are fed directly to the outputs via weights. The sum of the products of the weights and the inputs is calculated at each node. The [mean squared errors](./Mean_squared_error) between these calculated outputs and the given target values are minimized by adjusting to the weights. This technique is the [method of least squares](./Method_of_least_squares) or [linear regression](./Linear_regression). It was used to find a rough linear fit to a set of points by [Legendre](./Adrien-Marie_Legendre) (1805) and [Gauss](./Gauss) (1795) for the prediction of planetary movement.[[6]](./Neural_network_(machine_learning)#cite_note-gauss17952-6)[[7]](./Neural_network_(machine_learning)#cite_note-DLhistory2-7)[[8]](./Neural_network_(machine_learning)#cite_note-stigler2-8)

 

### Perceptrons

 

Computers are based on [John von Neumann's model](./Von_Neumann_model). They execute explicit lists of instructions with access to memory to record their changing state. Neural networks instead originated from efforts to model information processing in biological systems via [connectionism](./Connectionism). Unlike the von Neumann model, connectionist computing does not separate memory and processing.[*[citation needed](./Wikipedia:Citation_needed)*]

 

[Warren McCulloch](./Warren_McCulloch) and [Walter Pitts](./Walter_Pitts)[[9]](./Neural_network_(machine_learning)#cite_note-WM2-9) (1943) considered a non-learning computational model for neural networks.[[10]](./Neural_network_(machine_learning)#cite_note-10) This model paved the way for research to split into one branch focused on biological processes and another focused on artificial intelligence. McCulloch and Pitts also developed mathematical models of artificial neurons capable of representing logical functions.[[9]](./Neural_network_(machine_learning)#cite_note-WM2-9)

 

In the late 1940s, [D. O. Hebb](./Donald_O._Hebb)[[11]](./Neural_network_(machine_learning)#cite_note-11) proposed a learning [hypothesis](./Hypothesis) based on [neural plasticity](./Neuroplasticity) that became known as [Hebbian learning](./Hebbian_learning). It was used in many early neural network experiments, such as Rosenblatt's [perceptron](./Perceptron) and the [Hopfield network](./Hopfield_network). [Farley](./Belmont_Farley?action=edit&redlink=1) and [Clark](./Wesley_A._Clark)[[12]](./Neural_network_(machine_learning)#cite_note-12) (1954) used computational machines to simulate a Hebbian network. Other neural networks computational machines were created by [Rochester](./Nathaniel_Rochester_(computer_scientist)), Holland, Habit and Duda (1956).[[13]](./Neural_network_(machine_learning)#cite_note-13)

 

In 1958, psychologist [Frank Rosenblatt](./Frank_Rosenblatt) described the [perceptron](./Perceptron), one of the first implemented neural networks,[[14]](./Neural_network_(machine_learning)#cite_note-14)[[15]](./Neural_network_(machine_learning)#cite_note-15)[[16]](./Neural_network_(machine_learning)#cite_note-Werbos_19752-16)[[17]](./Neural_network_(machine_learning)#cite_note-17) funded by the United States [Office of Naval Research](./Office_of_Naval_Research).[[18]](./Neural_network_(machine_learning)#cite_note-Olazaran2-18) R. D. Joseph (1960)[[19]](./Neural_network_(machine_learning)#cite_note-joseph19602-19)[*[verification needed](./Wikipedia:Verifiability)*] mentioned an earlier perceptron-like device by [B. G. Farley](./Belmont_Farley?action=edit&redlink=1) and [W. A. Clark](./Wesley_A._Clark) of the [MIT Lincoln Laboratory](./MIT_Lincoln_Laboratory);[[7]](./Neural_network_(machine_learning)#cite_note-DLhistory2-7) however, according to Joseph, "they dropped the subject."[[19]](./Neural_network_(machine_learning)#cite_note-joseph19602-19)[*[verification needed](./Wikipedia:Verifiability)*]

 

The first perceptrons did not have adaptive hidden units. However, Joseph (1960)[[19]](./Neural_network_(machine_learning)#cite_note-joseph19602-19) discussed [multilayer](./Multilayer_perceptrons) that did. Rosenblatt (1962)[[20]](./Neural_network_(machine_learning)#cite_note-rosenblatt19622-20): section 16  cited and adopted these ideas, crediting work by H. D. Block and B. W. Knight. However, these early efforts did not lead to a working learning algorithm for hidden units, i.e., [deep learning](./Deep_learning).[*[citation needed](./Wikipedia:Citation_needed)*]

 

The perceptron raised public excitement in neural networks, causing the US government to drastically increase funding. This contributed to "the Golden Age of AI", fueled by the optimistic claims made by computer scientists regarding the ability of perceptrons to emulate human intelligence.[[21]](./Neural_network_(machine_learning)#cite_note-:082-21)

 

### Historical foundations and the Dartmouth proposal

 

[Artificial neural networks](./Artificial_neural_network) were identified as a promising direction for artificial intelligence research in the 1955 proposal for the [Dartmouth Summer Research Project on Artificial Intelligence](./Dartmouth_Summer_Research_Project_on_Artificial_Intelligence).[[22]](./Neural_network_(machine_learning)#cite_note-:72-22) Neural network models initially faced major limitations. Hardware constraints limited network size and training efficiency, while theoretical understanding of learning algorithms remained incomplete. Many models used single-layer perceptrons, which were restricted to solving linearly separable problems. These limitations were highlighted in the book *[Perceptrons](./Perceptrons_(book))* by [Marvin Minsky](./Marvin_Minsky) and [Seymour Papert](./Seymour_Papert), which deflated interest during the late 1960s and 1970s.[[23]](./Neural_network_(machine_learning)#cite_note-23)[*[AI-generated?](./Wikipedia:Large_language_models)*]

 

### 1960s and 1970s

 

Fundamental research was conducted on NNs in the 1960s and 1970s. The first working deep learning algorithm was the [group method of data handling](./Group_method_of_data_handling), a method to train arbitrarily deep neural networks, published by [Alexey Ivakhnenko](./Alexey_Ivakhnenko) and Valentin Lapa in the [Soviet Union](./Soviet_Union) (1965). They regarded it as a form of [polynomial regression](./Polynomial_regression),[[24]](./Neural_network_(machine_learning)#cite_note-ivak19652-24) generalizing Rosenblatt's perceptron.[[25]](./Neural_network_(machine_learning)#cite_note-25) A 1971 paper described a deep network with eight layers trained by this method,[[26]](./Neural_network_(machine_learning)#cite_note-ivak19712-26) training layer by layer via regression analysis. Superfluous hidden units were pruned using a separate validation set. The activation functions of the nodes were [Kolmogorov-Gabor polynomials](./Kolmogorov-Gabor_polynomials?action=edit&redlink=1), the first deep networks with multiplicative units or "gates".[[7]](./Neural_network_(machine_learning)#cite_note-DLhistory2-7)

 

The first deep learning [multilayer perceptron](./Multilayer_perceptron) (MLP) trained by [stochastic gradient descent](./Stochastic_gradient_descent)[[27]](./Neural_network_(machine_learning)#cite_note-robbins19512-27) was published in 1967 by [Shun'ichi Amari](./Shun'ichi_Amari).[[28]](./Neural_network_(machine_learning)#cite_note-Amari19672-28) In computer experiments conducted by Amari's student S. Saito, a five layer MLP with two modifiable layers learned [internal representations](./Knowledge_representation) to classify non-linearily separable pattern classes.[[7]](./Neural_network_(machine_learning)#cite_note-DLhistory2-7) Subsequent developments in hardware and hyperparameter tuning made end-to-end stochastic gradient descent the dominant technique for reducing loss (error).[*[citation needed](./Wikipedia:Citation_needed)*]

 

In 1969, [Kunihiko Fukushima](./Kunihiko_Fukushima) introduced the [ReLU](./Rectifier_(neural_networks)) (rectified linear unit) activation function.[[7]](./Neural_network_(machine_learning)#cite_note-DLhistory2-7)[[29]](./Neural_network_(machine_learning)#cite_note-Fukushima19692-29)[[30]](./Neural_network_(machine_learning)#cite_note-sonoda172-30) RelLU is the most common activation function.[[31]](./Neural_network_(machine_learning)#cite_note-31)

 

Nevertheless, research stagnated in the United States after [Minsky](./Marvin_Minsky) and [Papert](./Seymour_Papert) (1969),[[32]](./Neural_network_(machine_learning)#cite_note-:1322-32) who emphasized that perceptrons were incapable of processing the [exclusive-or](./Exclusive-or) circuit. However, this insight was irrelevant for the deep networks of Ivakhnenko (1965) and Amari (1967).

 

In 1976, [transfer learning](./Transfer_learning) was introduced.[[33]](./Neural_network_(machine_learning)#cite_note-33)

 

### Backpropagation

 

Interest in neural networks revived during the 1980s because of the novel [backpropagation](./Backpropagation) algorithm, which allowed multi-layer neural networks to be trained efficiently by propagating error gradients backward (from output  back to input) through network layers.[[34]](./Neural_network_(machine_learning)#cite_note-34)[*[AI-generated?](./Wikipedia:Large_language_models)*] Backpropagation is an efficient application of the [chain rule](./Chain_rule) derived by [Gottfried Wilhelm Leibniz](./Gottfried_Wilhelm_Leibniz) in 1673[[35]](./Neural_network_(machine_learning)#cite_note-leibniz167622-35) to networks of [differentiable](./Differentiable) nodes. The terminology "back-propagating errors" was introduced in 1962 by Rosenblatt,[[20]](./Neural_network_(machine_learning)#cite_note-rosenblatt19622-20) but he did not describe how to implement this. [Henry J. Kelley](./Henry_J._Kelley) developed a precursor of backpropagation in 1960 in the context of [control theory](./Control_theory).[[36]](./Neural_network_(machine_learning)#cite_note-kelley196022-36) In 1970, [Seppo Linnainmaa](./Seppo_Linnainmaa) published the modern form of backpropagation in his master's thesis (1970).[[37]](./Neural_network_(machine_learning)#cite_note-lin197032-37)[[38]](./Neural_network_(machine_learning)#cite_note-lin197632-38)[[7]](./Neural_network_(machine_learning)#cite_note-DLhistory2-7) G.M. Ostrovski et al. republished it in 1971.[[39]](./Neural_network_(machine_learning)#cite_note-ostrowski19712-39)[[40]](./Neural_network_(machine_learning)#cite_note-backprop2-40) [Paul Werbos](./Paul_Werbos) applied backpropagation to neural networks in 1982[[41]](./Neural_network_(machine_learning)#cite_note-werbos19822-41)[[42]](./Neural_network_(machine_learning)#cite_note-:12-42) (his 1974 PhD thesis, reprinted in a 1994 book,[[43]](./Neural_network_(machine_learning)#cite_note-werbos19742-43) did not describe the algorithm).[[40]](./Neural_network_(machine_learning)#cite_note-backprop2-40) In 1986, [David E. Rumelhart](./David_E._Rumelhart), et al., popularized backpropagation but did not cite the original work.[[44]](./Neural_network_(machine_learning)#cite_note-44)

 

### Convolutional neural networks

 

Deep learning architectures for [convolutional neural networks](./Convolutional_neural_network) (CNNs) with convolutional layers and downsampling layers and weight replication began with the [neocognitron](./Neocognitron) introduced by Kunihiko Fukushima in 1979.[[45]](./Neural_network_(machine_learning)#cite_note-FUKU19792-45)[[46]](./Neural_network_(machine_learning)#cite_note-FUKU19802-46)[[47]](./Neural_network_(machine_learning)#cite_note-SCHIDHUB42-47) Fukushima's CNN architecture also introduced [max pooling](./Max_pooling),[[48]](./Neural_network_(machine_learning)#cite_note-48) a popular downsampling procedure for CNNs. CNNs have become an essential tool for [computer vision](./Computer_vision).

 

The [time delay neural network](./Time_delay_neural_network) (TDNN) was introduced in 1987 by [Alex Waibel](./Alex_Waibel) to apply CNNs to phoneme recognition. It used convolutions, weight sharing, and backpropagation.[[49]](./Neural_network_(machine_learning)#cite_note-Waibel19872-49)[[50]](./Neural_network_(machine_learning)#cite_note-speechsignal2-50) In 1988, Wei Zhang applied a backpropagation-trained CNN to recognizing individual letters.[[51]](./Neural_network_(machine_learning)#cite_note-wz19882-51) In 1989, [Yann LeCun](./Yann_LeCun) et al. created a CNN called [LeNet](./LeNet) for [recognizing handwritten ZIP codes](./Handwriting_recognition) on mail. Training required 3 days.[[52]](./Neural_network_(machine_learning)#cite_note-LECUN19892-52) In 1990, Wei Zhang implemented a CNN on [optical computing](./Optical_computing) hardware.[[53]](./Neural_network_(machine_learning)#cite_note-wz19902-53) In 1991, a CNN was applied to medical image object segmentation[[54]](./Neural_network_(machine_learning)#cite_note-54) and breast cancer detection in mammograms.[[55]](./Neural_network_(machine_learning)#cite_note-55) LeNet-5 (1998), a 7-level CNN by Yann LeCun et al. that classifies hand-written digits, was applied by banks to recognize numbers on checks digitized in 32×32 pixel images.[[56]](./Neural_network_(machine_learning)#cite_note-lecun982-56)

 

From 1988 onward,[[57]](./Neural_network_(machine_learning)#cite_note-Qian19882-57)[[58]](./Neural_network_(machine_learning)#cite_note-Bohr19882-58) the use of neural networks transformed the field of [protein structure prediction](./Protein_structure_prediction), in particular when the first cascading networks were trained on *profiles* (matrices) produced by multiple [sequence alignments](./Sequence_alignment).[[59]](./Neural_network_(machine_learning)#cite_note-Rost19932-59)

 

### Recurrent neural networks

 

One source of RNN was [statistical mechanics](./Statistical_mechanics). In 1972, [Shun'ichi Amari](./Shun'ichi_Amari) proposed to modify the weights of an [Ising model](./Ising_model) by [Hebbian learning](./Hebbian_theory) rule as a model of [associative memory](./Hopfield_network), adding in learning.[[60]](./Neural_network_(machine_learning)#cite_note-60) This was popularized as the Hopfield network by [John Hopfield](./John_Hopfield) (1982).[[61]](./Neural_network_(machine_learning)#cite_note-Hopfield198222-61) Another origin of RNN was neuroscience. The word "recurrent" is used to describe loop-like structures in anatomy. In 1901, [Cajal](./Santiago_Ramón_y_Cajal) observed "recurrent semicircles" in the [cerebellar cortex](./Cerebellum).[[62]](./Neural_network_(machine_learning)#cite_note-62) [Hebb](./Donald_O._Hebb) considered "reverberating circuit" as an explanation for short-term memory.[[63]](./Neural_network_(machine_learning)#cite_note-63) The McCulloch and Pitts paper (1943) considered neural networks that contain cycles, and noted that the current activity of such networks can be affected by activity indefinitely far in the past.[[9]](./Neural_network_(machine_learning)#cite_note-WM2-9)

 

In 1982 Crossbar Adaptive Array, a recurrent neural network with an array architecture (rather than a multilayer perceptron architecture),[[64]](./Neural_network_(machine_learning)#cite_note-CAA19822-64)[[65]](./Neural_network_(machine_learning)#cite_note-caa1995=2-65) used direct recurrent connections from the output to the supervisor (teaching) inputs. In addition to computing actions (decisions), it computed internal state evaluations (emotions) of consequence situations. Eliminating the external supervisor, it introduced the self-learning method in neural networks.

 

In cognitive psychology, the *[American Psychologist](./American_Psychologist)* journal in the early 1980s debated the relation between cognition and emotion. Social psychologist [Robert Zajonc](./Robert_Zajonc) in 1980 stated that emotion is computed first and is independent from cognition, while [Richard Lazarus](./Richard_Lazarus) in 1982 stated that cognition is computed first and is inseparable from emotion.[[66]](./Neural_network_(machine_learning)#cite_note-66)[[67]](./Neural_network_(machine_learning)#cite_note-67)[[68]](./Neural_network_(machine_learning)#cite_note-68) It was an example of a debate where an RNN contributed to an issue and also addressed cognitive psychology.[*[importance?](./Wikipedia:What_Wikipedia_is_not#Encyclopedic_content)*]

 

The [Jordan network](./Recurrent_neural_network#Jordan_network) (1986) and the [Elman network](./Recurrent_neural_network#Elman_network) (1990) applied RNN to study [cognitive psychology](./Cognitive_psychology).[*[citation needed](./Wikipedia:Citation_needed)*]

 

In the 1980s, backpropagation did not work well for deep RNNs. In 1991, [Jürgen Schmidhuber](./Jürgen_Schmidhuber) proposed the "neural sequence chunker" or "neural history compressor"[[69]](./Neural_network_(machine_learning)#cite_note-chunker19912-69)[[70]](./Neural_network_(machine_learning)#cite_note-schmidhuber19922-70) which introduced [self-supervised pre-training](./Self-supervised_learning) (the "P" in [ChatGPT](./ChatGPT)) and neural [knowledge distillation](./Knowledge_distillation).[[7]](./Neural_network_(machine_learning)#cite_note-DLhistory2-7) In 1993, a neural history compressor system solved a "Very Deep Learning" task that required more than 1000 [layers](./Layer_(deep_learning)) in an RNN unfolded in time.[[71]](./Neural_network_(machine_learning)#cite_note-schmidhuber199322-71)

 

In 1991, [Sepp Hochreiter](./Sepp_Hochreiter)'s diploma thesis identified and analyzed the [vanishing gradient problem](./Vanishing_gradient_problem)[[72]](./Neural_network_(machine_learning)#cite_note-HOCH19912-72)[[73]](./Neural_network_(machine_learning)#cite_note-HOCH20012-73) and proposed recurrent [residual](./Residual_neural_network) connections to solve it. He and Schmidhuber introduced [long short-term memory](./Long_short-term_memory) (LSTM), which set accuracy records in multiple application domains.[[74]](./Neural_network_(machine_learning)#cite_note-74)[[75]](./Neural_network_(machine_learning)#cite_note-lstm22-75) This was not the ultimate version of LSTM, which required the forget gate, and was introduced in 1999.[[76]](./Neural_network_(machine_learning)#cite_note-lstm19992-76) It became the default choice for RNN architecture.[*[citation needed](./Wikipedia:Citation_needed)*]

 

During 1985–1995, inspired by statistical mechanics, several architectures and methods were developed by [Terry Sejnowski](./Terry_Sejnowski), [Peter Dayan](./Peter_Dayan), [Geoffrey Hinton](./Geoffrey_Hinton), and others, including the [Boltzmann machine](./Boltzmann_machine),[[77]](./Neural_network_(machine_learning)#cite_note-77) [restricted Boltzmann machine](./Restricted_Boltzmann_machine),[[78]](./Neural_network_(machine_learning)#cite_note-78) [Helmholtz machine](./Helmholtz_machine),[[79]](./Neural_network_(machine_learning)#cite_note-nc952-79) and the [wake-sleep algorithm](./Wake-sleep_algorithm).[[80]](./Neural_network_(machine_learning)#cite_note-:133-80) These were designed for unsupervised learning of deep generative models.[*[citation needed](./Wikipedia:Citation_needed)*]

 

### Modern deep learning

 

Between 2009 and 2012, NNs began winning prizes in image recognition contests, approaching human performance on various tasks, initially in [pattern recognition](./Pattern_recognition) and [handwriting recognition](./Handwriting_recognition).[[81]](./Neural_network_(machine_learning)#cite_note-81)[[82]](./Neural_network_(machine_learning)#cite_note-82) In 2011, *DanNet,[[83]](./Neural_network_(machine_learning)#cite_note-:322-83)*[[84]](./Neural_network_(machine_learning)#cite_note-:622-84) a CNN by Dan Ciresan, Ueli Meier, Jonathan Masci, [Luca Maria Gambardella](./Luca_Maria_Gambardella), and Schmidhuber achieved for the first time superhuman performance in a visual pattern recognition contest, outperforming traditional methods by a factor of 3.[[47]](./Neural_network_(machine_learning)#cite_note-SCHIDHUB42-47) It then won more contests.[[85]](./Neural_network_(machine_learning)#cite_note-:822-85)[[86]](./Neural_network_(machine_learning)#cite_note-ciresan2013miccai2-86) They also showed how max-pooling CNNs on GPU improved performance.[[87]](./Neural_network_(machine_learning)#cite_note-:92-87)

 

In October 2012, [AlexNet](./AlexNet) by [Alex Krizhevsky](./Alex_Krizhevsky), [Ilya Sutskever](./Ilya_Sutskever), and Hinton[[88]](./Neural_network_(machine_learning)#cite_note-krizhevsky201222-88) won the large-scale [ImageNet competition](./ImageNet_competition) by a significant margin over shallow machine learning methods. Further incremental improvements included the VGG-16 network by Karen Simonyan and [Andrew Zisserman](./Andrew_Zisserman)[[89]](./Neural_network_(machine_learning)#cite_note-VGG2-89) and Google's [Inceptionv3](./Inceptionv3).[[90]](./Neural_network_(machine_learning)#cite_note-szegedy2-90)

 

In 2012, [Ng](./Andrew_Ng) and [Dean](./Jeff_Dean_(computer_scientist)) created a network that learned to recognize higher-level concepts, such as cats, from training only on unlabeled images.[[91]](./Neural_network_(machine_learning)#cite_note-ng20122-91) [Unsupervised](./Unsupervised_learning) pre-training and increased computing power from [GPUs](./GPU) and [distributed computing](./Distributed_computing) allowed the use of larger networks, particularly in image and visual recognition problems, which became known as "deep learning".[[92]](./Neural_network_(machine_learning)#cite_note-:42-92)

 

[Radial basis function](./Radial_basis_function_network) and wavelet networks were introduced in 2013. These can be shown to offer best approximation properties and have been applied in [nonlinear system identification](./Nonlinear_system_identification) and classification applications.[[93]](./Neural_network_(machine_learning)#cite_note-SAB12-93)

 

[Generative adversarial networks](./Generative_adversarial_network) (GANs) ([Ian Goodfellow](./Ian_Goodfellow) et al., 2014)[[94]](./Neural_network_(machine_learning)#cite_note-GANnips2-94) became state of the art in generative modeling from 2014–2018. GAN was originally published in 1991 by Schmidhuber, who called it "artificial curiosity": two neural networks contest with each other in the form of a [zero-sum game](./Zero-sum_game), where one network's gain is the other network's loss.[[95]](./Neural_network_(machine_learning)#cite_note-curiosity19912-95)[[96]](./Neural_network_(machine_learning)#cite_note-gancurpm20202-96) The first network is a [generative model](./Generative_model) that models a [probability distribution](./Probability_distribution) over output patterns. The second network learns by [gradient descent](./Gradient_descent) to predict the reactions of the environment to these patterns. Excellent image quality was achieved by [Nvidia](./Nvidia)'s [StyleGAN](./StyleGAN) (2018)[[97]](./Neural_network_(machine_learning)#cite_note-SyncedReview2018222-97) based on the Progressive GAN by Tero Karras et al.[[98]](./Neural_network_(machine_learning)#cite_note-progressiveGAN2017222-98) Here, the GAN generator is grown from small to large scale in a pyramidal fashion. Image generation by GAN reached popular success, and provoked discussions concerning [deepfakes](./Deepfake).[[99]](./Neural_network_(machine_learning)#cite_note-99) [Diffusion models](./Diffusion_model) (2015)[[100]](./Neural_network_(machine_learning)#cite_note-100) eclipsed GANs in generative modeling thereafter, with systems such as [DALL·E 2](./DALL·E_2) (2022) and [Stable Diffusion](./Stable_Diffusion) (2022).

 

In 2014, the state of the art was training "[a] very deep neural network" with 20 to 30 layers.[[101]](./Neural_network_(machine_learning)#cite_note-101) Stacking too many layers led to a steep reduction in [training](./Training,_validation,_and_test_data_sets) accuracy,[[102]](./Neural_network_(machine_learning)#cite_note-prelu22-102) known as the "degradation" problem.[[103]](./Neural_network_(machine_learning)#cite_note-resnet22-103) In 2015, training very deep networks advanced with the [highway network](./Highway_network), published in May,[[104]](./Neural_network_(machine_learning)#cite_note-highway201532-104) and the [residual neural network](./Residual_neural_network) (ResNet) in December.[[105]](./Neural_network_(machine_learning)#cite_note-resnet201532-105)[[106]](./Neural_network_(machine_learning)#cite_note-106) ResNet behaves like an open-gated Highway Net.[*[clarification needed](./Wikipedia:Please_clarify)*]

 

### Transformers

 Main article: [Transformer (deep learning architecture) § History](./Transformer_(deep_learning_architecture)#History) 

During the 2010s, the [seq2seq](./Seq2seq) model was developed, and attention mechanisms were added. This led to the modern [transformer](./Transformer_(deep_learning)) architecture in 2017 in "[Attention Is All You Need](./Attention_Is_All_You_Need)".[[4]](./Neural_network_(machine_learning)#cite_note-:63-4) It requires computation time that is quadratic in the size of the context window. Schmidhuber's fast weight controller (1992)[[107]](./Neural_network_(machine_learning)#cite_note-transform199222-107) scales linearly and was later shown to be equivalent to the unnormalized linear transformer.[[108]](./Neural_network_(machine_learning)#cite_note-fastlinear202022-108)[[109]](./Neural_network_(machine_learning)#cite_note-schlag202122-109)[[7]](./Neural_network_(machine_learning)#cite_note-DLhistory2-7) Transformers have increasingly become the model of choice for [natural language processing](./Natural_language_processing).[[110]](./Neural_network_(machine_learning)#cite_note-wolf20202-110) Many modern [large language models](./Large_language_model) such as [GPT](./GPT-5.5), [Gemini](./Gemini_(language_model)), [Grok](./Grok_(chatbot)), [DeepSeek](./DeepSeek), and [Qwen](./Qwen) use this architecture.

 


