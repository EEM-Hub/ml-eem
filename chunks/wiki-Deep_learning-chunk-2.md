---
source: sources/wiki-Deep_learning.md
source_url: https://en.wikipedia.org/wiki/Deep_learning
chunk: 2/7
---

## History

 

### Before 1980

 

There are two [types](./Types_of_artificial_neural_networks) of artificial neural network (ANN): [feedforward neural network](./Feedforward_neural_network) (FNN) or [multilayer perceptron](./Multilayer_perceptron) (MLP) and [recurrent neural networks](./Recurrent_neural_networks) (RNN). RNNs have cycles in their connectivity structure, whereas FNNs do not. In the 1920s, [Wilhelm Lenz](./Wilhelm_Lenz) and [Ernst Ising](./Ernst_Ising) created the [Ising model](./Ising_model)[[28]](./Deep_learning#cite_note-ising1925-28)[[29]](./Deep_learning#cite_note-brush67-29) which is essentially a non-learning RNN architecture consisting of neuron-like threshold elements. In 1972, [Shun'ichi Amari](./Shun'ichi_Amari) made this architecture adaptive.[[30]](./Deep_learning#cite_note-Amari1972-30)[[31]](./Deep_learning#cite_note-DLhistory-31) His learning RNN was republished by [John Hopfield](./John_Hopfield) in 1982.[[32]](./Deep_learning#cite_note-Hopfield1982-32) Other early [recurrent neural networks](./Recurrent_neural_network) were published by Kaoru Nakano in 1971.[[33]](./Deep_learning#cite_note-Nakano1971-33)[[34]](./Deep_learning#cite_note-Nakano1972-34) Already in 1948, [Alan Turing](./Alan_Turing) produced work on "Intelligent Machinery"  that was not published in his lifetime,[[35]](./Deep_learning#cite_note-turing1948-35) containing "ideas related to artificial evolution and learning RNNs".[[31]](./Deep_learning#cite_note-DLhistory-31)

 

[Frank Rosenblatt](./Frank_Rosenblatt) (1958)[[36]](./Deep_learning#cite_note-36) proposed the perceptron, an MLP with 3 layers: an input layer, a hidden layer with randomized weights that did not learn, and an output layer. He later published a 1962 book that also introduced variants and computer experiments, including a version with four-layer perceptrons "with adaptive preterminal networks" where the last two layers have learned weights (here he credits H. D. Block and B. W. Knight).[[37]](./Deep_learning#cite_note-rosenblatt1962-37): section 16  The book cites an earlier network by R. D. Joseph (1960)[[38]](./Deep_learning#cite_note-joseph1960-38) "functionally equivalent to a variation of" this four-layer system (the book mentions Joseph over 30 times). Should Joseph therefore be considered the originator of proper adaptive [multilayer perceptrons](./Multilayer_perceptrons) with learning hidden units? Unfortunately, the learning algorithm was not a functional one, and fell into oblivion.

 

The first working deep learning algorithm was the [Group method of data handling](./Group_method_of_data_handling), a method to train arbitrarily deep neural networks, published by [Alexey Ivakhnenko](./Alexey_Ivakhnenko) and Lapa in 1965. They regarded it as a form of polynomial regression,[[39]](./Deep_learning#cite_note-ivak1965-39) or a generalization of Rosenblatt's perceptron to handle more complex, nonlinear, and hierarchical relationships.[[40]](./Deep_learning#cite_note-40) A 1971 paper described a deep network with eight layers trained by this method,[[41]](./Deep_learning#cite_note-ivak1971-41) which is based on layer by layer training through regression analysis. Superfluous hidden units are pruned using a separate validation set. Since the activation functions of the nodes are Kolmogorov-Gabor polynomials, these were also the first deep networks with multiplicative units or "gates".[[31]](./Deep_learning#cite_note-DLhistory-31)

 

The first deep learning [multilayer perceptron](./Multilayer_perceptron) trained by [stochastic gradient descent](./Stochastic_gradient_descent)[[42]](./Deep_learning#cite_note-robbins1951-42) was published in 1967 by [Shun'ichi Amari](./Shun'ichi_Amari).[[43]](./Deep_learning#cite_note-Amari1967-43) In computer experiments conducted by Amari's student Saito, a five layer MLP with two modifiable layers learned  [internal representations](./Knowledge_representation) to classify non-linearily separable pattern classes.[[31]](./Deep_learning#cite_note-DLhistory-31) Subsequent developments in hardware and hyperparameter tunings have made end-to-end stochastic gradient descent the currently dominant training technique.

 

In 1969, [Kunihiko Fukushima](./Kunihiko_Fukushima) introduced the [ReLU](./Rectifier_(neural_networks)) (rectified linear unit) [activation function](./Activation_function).[[25]](./Deep_learning#cite_note-Fukushima1969-25)[[31]](./Deep_learning#cite_note-DLhistory-31) The rectifier has become the most popular activation function for deep learning.[[44]](./Deep_learning#cite_note-44)

 

Deep learning architectures for [convolutional neural networks](./Convolutional_neural_network) (CNNs) with convolutional layers and downsampling layers began with the [Neocognitron](./Neocognitron) introduced by [Kunihiko Fukushima](./Kunihiko_Fukushima) in 1979, though not trained by backpropagation.[[45]](./Deep_learning#cite_note-FUKU1979-45)[[46]](./Deep_learning#cite_note-FUKU1980-46)

 

[Backpropagation](./Backpropagation) is an efficient application of the [chain rule](./Chain_rule) derived by [Gottfried Wilhelm Leibniz](./Gottfried_Wilhelm_Leibniz) in 1673[[47]](./Deep_learning#cite_note-leibniz1676-47) to networks of differentiable nodes. The terminology "back-propagating errors" was actually introduced in 1962 by Rosenblatt,[[37]](./Deep_learning#cite_note-rosenblatt1962-37) but he did not know how to implement this, although [Henry J. Kelley](./Henry_J._Kelley) had a continuous precursor of backpropagation in 1960 in the context of [control theory](./Control_theory).[[48]](./Deep_learning#cite_note-kelley1960-48) The modern form of backpropagation was first published in [Seppo Linnainmaa](./Seppo_Linnainmaa)'s master thesis (1970).[[49]](./Deep_learning#cite_note-lin19703-49)[[50]](./Deep_learning#cite_note-lin19763-50)[[31]](./Deep_learning#cite_note-DLhistory-31) G.M. Ostrovski et al. republished it in 1971.[[51]](./Deep_learning#cite_note-ostrowski1971-51)[[52]](./Deep_learning#cite_note-backprop-52) [Paul Werbos](./Paul_Werbos) applied backpropagation to neural networks in 1982[[53]](./Deep_learning#cite_note-werbos1982-53) (his 1974 PhD thesis, reprinted in a 1994 book,[[54]](./Deep_learning#cite_note-werbos1974-54) did not yet describe the algorithm[[52]](./Deep_learning#cite_note-backprop-52)). In 1986, [David E. Rumelhart](./David_E._Rumelhart) et al. popularised backpropagation but did not cite the original work.[[55]](./Deep_learning#cite_note-55)[[56]](./Deep_learning#cite_note-rumelhart1986-56)

 

### 1980s-2000s

 

The [time delay neural network](./Time_delay_neural_network) (TDNN) was introduced in 1987 by [Alex Waibel](./Alex_Waibel) to apply CNN to phoneme recognition. It used convolutions, weight sharing, and backpropagation.[[57]](./Deep_learning#cite_note-Waibel1987-57)[[58]](./Deep_learning#cite_note-speechsignal-58) In 1988, Wei Zhang applied a backpropagation-trained CNN to alphabet recognition.[[59]](./Deep_learning#cite_note-wz1988-59) 
In 1989, [Yann LeCun](./Yann_LeCun) et al. created a CNN called [LeNet](./LeNet) for [recognizing handwritten ZIP codes](./Handwriting_recognition) on mail. Training required 3 days.[[60]](./Deep_learning#cite_note-LECUN1989-60) In 1990, Wei Zhang implemented a CNN on [optical computing](./Optical_computing) hardware.[[61]](./Deep_learning#cite_note-wz1990-61) In 1991, a CNN was applied to medical image object segmentation[[62]](./Deep_learning#cite_note-62) and breast cancer detection in mammograms.[[63]](./Deep_learning#cite_note-63) LeNet-5 (1998), a 7-level CNN by Yann LeCun et al., that classifies digits, was applied by several banks to recognize hand-written numbers on checks  digitized in 32x32 pixel images.[[64]](./Deep_learning#cite_note-lecun98-64)

 

[Recurrent neural networks](./Recurrent_neural_network) (RNN)[[28]](./Deep_learning#cite_note-ising1925-28)[[30]](./Deep_learning#cite_note-Amari1972-30) were further developed in the 1980s. Recurrence is used for sequence processing, and when a recurrent network is unrolled, it mathematically resembles a deep feedforward layer. Consequently, they have similar properties and issues, and their developments had mutual influences. In RNN, two early influential works were the [Jordan network](./Recurrent_neural_network#Jordan_network) (1986)[[65]](./Deep_learning#cite_note-65) and the [Elman network](./Recurrent_neural_network#Elman_network) (1990),[[66]](./Deep_learning#cite_note-66) which applied RNN to study problems in [cognitive psychology](./Cognitive_psychology).

 

In the 1980s, backpropagation did not work well for deep learning with long credit assignment paths. To overcome this problem, in 1991, [Jürgen Schmidhuber](./Jürgen_Schmidhuber) proposed a hierarchy of RNNs pre-trained one level at a time by [self-supervised learning](./Self-supervised_learning) where each RNN tries to predict its own next input, which is the next unexpected input of the RNN below.[[67]](./Deep_learning#cite_note-chunker1991-67)[[68]](./Deep_learning#cite_note-schmidhuber1992-68) This "neural history compressor" uses [predictive coding](./Predictive_coding)  to learn [internal representations](./Knowledge_representation) at multiple self-organizing time scales. This can substantially facilitate downstream deep learning. The RNN hierarchy can be *collapsed* into a single RNN, by  [distilling](./Knowledge_distillation) a higher level *chunker* network into a lower level *automatizer* network.[[67]](./Deep_learning#cite_note-chunker1991-67)[[68]](./Deep_learning#cite_note-schmidhuber1992-68)[[31]](./Deep_learning#cite_note-DLhistory-31) In 1993, a neural history compressor solved a "Very Deep Learning" task that required more than 1000 subsequent [layers](./Layer_(deep_learning)) in an RNN unfolded in time.[[69]](./Deep_learning#cite_note-schmidhuber1993-69) The "P" in [ChatGPT](./ChatGPT) refers to such pre-training.

 

[Sepp Hochreiter](./Sepp_Hochreiter)'s diploma thesis (1991)[[70]](./Deep_learning#cite_note-HOCH1991-70) implemented the neural history compressor,[[67]](./Deep_learning#cite_note-chunker1991-67) and identified and analyzed the [vanishing gradient problem](./Vanishing_gradient_problem).[[70]](./Deep_learning#cite_note-HOCH1991-70)[[71]](./Deep_learning#cite_note-HOCH2001-71)  Hochreiter proposed recurrent [residual](./Residual_neural_network) connections to solve the vanishing gradient problem. This led to the [long short-term memory](./Long_short-term_memory) (LSTM), published in 1995.[[72]](./Deep_learning#cite_note-72) LSTM can learn "very deep learning" tasks[[9]](./Deep_learning#cite_note-SCHIDHUB-9) with long credit assignment paths that require memories of events that happened thousands of discrete time steps before. That LSTM was not yet the modern architecture, which required a "forget gate", introduced in 1999,[[73]](./Deep_learning#cite_note-lstm1999-73) which became the standard RNN architecture.

 

In 1991, [Jürgen Schmidhuber](./Jürgen_Schmidhuber) also published adversarial neural networks that contest with each other in the form of a [zero-sum game](./Zero-sum_game), where one network's gain is the other network's loss.[[74]](./Deep_learning#cite_note-curiosity1991-74)[[75]](./Deep_learning#cite_note-fun2010-75) The first network is a [generative model](./Generative_model) that models a [probability distribution](./Probability_distribution) over output patterns. The second network learns by [gradient descent](./Gradient_descent) to predict the reactions of the environment to these patterns. This was called "artificial curiosity". In 2014, this principle was used in [generative adversarial networks](./Generative_adversarial_network) (GANs).[[76]](./Deep_learning#cite_note-gancurpm2020-76)

 

During 1985–1995, inspired by statistical mechanics, several architectures and methods were developed by [Terry Sejnowski](./Terry_Sejnowski), [Peter Dayan](./Peter_Dayan), [Geoffrey Hinton](./Geoffrey_Hinton), etc., including the [Boltzmann machine](./Boltzmann_machine),[[77]](./Deep_learning#cite_note-77) [restricted Boltzmann machine](./Restricted_Boltzmann_machine),[[78]](./Deep_learning#cite_note-78) [Helmholtz machine](./Helmholtz_machine),[[79]](./Deep_learning#cite_note-nc95-79) and the [wake-sleep algorithm](./Wake-sleep_algorithm).[[80]](./Deep_learning#cite_note-:1-80) These were designed for unsupervised learning of deep generative models. However, those were more computationally expensive compared to backpropagation. Boltzmann machine learning algorithm, published in 1985, was briefly popular before being eclipsed by the backpropagation algorithm in 1986. (p. 112 [[81]](./Deep_learning#cite_note-81)). A 1988 network became state of the art in [protein structure prediction](./Protein_structure_prediction), an early application of deep learning to bioinformatics.[[82]](./Deep_learning#cite_note-82)

 

Both shallow and deep learning (e.g., recurrent nets) of ANNs for [speech recognition](./Speech_recognition) have been explored for many years.[[83]](./Deep_learning#cite_note-83)[[84]](./Deep_learning#cite_note-Robinson1992-84)[[85]](./Deep_learning#cite_note-85) These methods never outperformed non-uniform internal-handcrafting Gaussian [mixture model](./Mixture_model)/[Hidden Markov model](./Hidden_Markov_model) (GMM-HMM) technology based on generative models of speech trained discriminatively.[[86]](./Deep_learning#cite_note-Baker2009-86) Key difficulties have been analyzed, including gradient diminishing[[70]](./Deep_learning#cite_note-HOCH1991-70) and weak temporal correlation structure in neural predictive models.[[87]](./Deep_learning#cite_note-Bengio1991-87)[[88]](./Deep_learning#cite_note-Deng1994-88) Additional difficulties were the lack of training data and limited computing power.

 

Most [speech recognition](./Speech_recognition) researchers moved away from neural nets to pursue generative modeling. An exception was at [SRI International](./SRI_International) in the late 1990s. Funded by the US government's [NSA](./National_Security_Agency) and [DARPA](./DARPA), SRI researched in speech and [speaker recognition](./Speaker_recognition). The speaker recognition team led by [Larry Heck](./Larry_Heck) reported significant success with deep neural networks in speech processing in the 1998 [NIST](./National_Institute_of_Standards_and_Technology) Speaker Recognition benchmark.[[89]](./Deep_learning#cite_note-Doddington2000-89)[[90]](./Deep_learning#cite_note-Heck2000-90) It was deployed in the Nuance Verifier, representing the first major industrial application of deep learning.[[91]](./Deep_learning#cite_note-91)

 

The principle of elevating "raw" features over hand-crafted optimization was first explored successfully in the architecture of deep autoencoder on the "raw" spectrogram or linear [filter-bank](./Filter_bank) features in the late 1990s,[[90]](./Deep_learning#cite_note-Heck2000-90) showing its superiority over the [Mel-Cepstral](./Mel-frequency_cepstrum) features that contain stages of fixed transformation from spectrograms. The raw features of speech, [waveforms](./Waveform), later produced excellent larger-scale results.[[92]](./Deep_learning#cite_note-92)

 

### 2000s

 

Neural networks entered a lull, and simpler models that use task-specific handcrafted features such as [Gabor filters](./Gabor_filter) and [support vector machines](./Support_vector_machine) (SVMs) became the preferred choices in the 1990s and 2000s, because of artificial neural networks' computational cost and a lack of understanding of how the brain wires its biological networks.[*[citation needed](./Wikipedia:Citation_needed)*]

 

In 2003, LSTM became competitive with traditional speech recognizers on certain tasks.[[93]](./Deep_learning#cite_note-graves2003-93) In 2006, [Alex Graves](./Alex_Graves_(computer_scientist)), Santiago Fernández, Faustino Gomez, and Schmidhuber combined it with [connectionist temporal classification](./Connectionist_temporal_classification) (CTC)[[94]](./Deep_learning#cite_note-graves2006-94) in stacks of LSTMs.[[95]](./Deep_learning#cite_note-fernandez2007keyword-95) In 2009, it became the first RNN to win a [pattern recognition](./Pattern_recognition) contest, in connected [handwriting recognition](./Handwriting_recognition).[[96]](./Deep_learning#cite_note-96)[[9]](./Deep_learning#cite_note-SCHIDHUB-9)

 

In 2006, publications by [Geoff Hinton](./Geoffrey_Hinton), [Ruslan Salakhutdinov](./Russ_Salakhutdinov), Osindero and [Teh](./Yee_Whye_Teh)[[97]](./Deep_learning#cite_note-Hinton_2007_Learning_multiple_layers-97)[[98]](./Deep_learning#cite_note-hinton06-98) [deep belief networks](./Deep_belief_network) were developed for generative modeling. They are trained by training one restricted Boltzmann machine, then freezing it and training another one on top of the first one, and so on, then optionally [fine-tuned](./Fine-tuning_(deep_learning)) using supervised backpropagation.[[97]](./Deep_learning#cite_note-Hinton_2007_Learning_multiple_layers-97) They could model high-dimensional probability distributions, such as the distribution of [MNIST images](./MNIST_database), but convergence was slow.[[97]](./Deep_learning#cite_note-Hinton_2007_Learning_multiple_layers-97)[[99]](./Deep_learning#cite_note-99)[[100]](./Deep_learning#cite_note-100)

 

The impact of deep learning in industry began in the early 2000s, when CNNs already processed an estimated 10% to 20% of all the checks written in the US, according to Yann LeCun.[[101]](./Deep_learning#cite_note-lecun2016slides-101) Industrial applications of deep learning to large-scale speech recognition started around 2010.

 

The 2009 NIPS Workshop on Deep Learning for Speech Recognition was motivated by the limitations of deep generative models of speech, and the possibility that given more capable hardware and large-scale data sets that deep neural nets might become practical. It was believed that pre-training DNNs using generative models of deep belief nets (DBN) would overcome the main difficulties of neural nets. However, it was discovered that replacing pre-training with large amounts of training data for straightforward backpropagation when using DNNs with large, context-dependent output layers produced error rates dramatically lower than then-state-of-the-art Gaussian mixture model (GMM)/Hidden Markov Model (HMM) and also than more-advanced generative model-based systems.[[102]](./Deep_learning#cite_note-HintonDengYu2012-102) The nature of the recognition errors produced by the two types of systems was characteristically different,[[103]](./Deep_learning#cite_note-ReferenceICASSP2013-103) offering technical insights into how to integrate deep learning into the existing highly efficient, run-time speech decoding system deployed by all major speech recognition systems.[[23]](./Deep_learning#cite_note-BOOK2014-23)[[104]](./Deep_learning#cite_note-ReferenceA-104)[[105]](./Deep_learning#cite_note-105) Analysis around 2009–2010, contrasting the GMM (and other generative speech models) vs. DNN models, stimulated early industrial investment in deep learning for speech recognition.[[103]](./Deep_learning#cite_note-ReferenceICASSP2013-103)  That analysis was done with comparable performance (less than 1.5% in error rate) between discriminative DNNs and generative models.[[102]](./Deep_learning#cite_note-HintonDengYu2012-102)[[103]](./Deep_learning#cite_note-ReferenceICASSP2013-103)[[106]](./Deep_learning#cite_note-interspeech2014Keynote-106)
In 2010, researchers extended deep learning from [TIMIT](./TIMIT) to large vocabulary speech recognition, by adopting large output layers of the DNN based on context-dependent HMM states constructed by [decision trees](./Decision_tree).[[107]](./Deep_learning#cite_note-Roles2010-107)[[108]](./Deep_learning#cite_note-108)[[109]](./Deep_learning#cite_note-109)[[104]](./Deep_learning#cite_note-ReferenceA-104)

 

### Deep learning revolution

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/b/bb/AI-ML-DL.svg/250px-AI-ML-DL.svg.png)](./File:AI-ML-DL.svg)How deep learning is a subset of machine learning and how machine learning is a subset of artificial intelligence (AI) 

The deep learning revolution started around CNN- and GPU-based computer vision.

 

Although CNNs trained by backpropagation had been around for decades and GPU implementations of NNs for years,[[110]](./Deep_learning#cite_note-jung2004-110) including CNNs,[[111]](./Deep_learning#cite_note-chellapilla2006-111) faster implementations of CNNs on GPUs were needed to progress on computer vision. Later, as deep learning becomes widespread, specialized hardware and algorithm optimizations were developed specifically for deep learning.[[112]](./Deep_learning#cite_note-sze2017-112)

 

A key advance for the deep learning revolution was hardware advances, especially GPU. Some early work dated back to 2004.[[110]](./Deep_learning#cite_note-jung2004-110)[[111]](./Deep_learning#cite_note-chellapilla2006-111) In 2009, Raina, Madhavan, and [Andrew Ng](./Andrew_Ng) reported a 100M deep belief network trained on 30 Nvidia [GeForce GTX 280](./GeForce_GTX_280) GPUs, an early demonstration of GPU-based deep learning. They reported up to 70 times faster training.[[113]](./Deep_learning#cite_note-113)

 

In 2011, a CNN named *DanNet[[114]](./Deep_learning#cite_note-:3-114)*[[115]](./Deep_learning#cite_note-:6-115) by Dan Ciresan, Ueli Meier, Jonathan Masci, [Luca Maria Gambardella](./Luca_Maria_Gambardella), and [Jürgen Schmidhuber](./Jürgen_Schmidhuber) achieved for the first time superhuman performance in a visual pattern recognition contest, outperforming traditional methods by a factor of 3.[[9]](./Deep_learning#cite_note-SCHIDHUB-9) It then won more contests.[[116]](./Deep_learning#cite_note-:8-116)[[117]](./Deep_learning#cite_note-ciresan2013miccai-117) They also showed how [max-pooling](./Max_pooling) CNNs on GPU improved performance significantly.[[3]](./Deep_learning#cite_note-:9-3)

 

In 2012, [Andrew Ng](./Andrew_Ng) and [Jeff Dean](./Jeff_Dean_(computer_scientist)) created an FNN that learned to recognize higher-level concepts, such as cats, only from watching unlabeled images taken from [YouTube](./YouTube) videos.[[118]](./Deep_learning#cite_note-ng2012-118)

 

In October 2012, [AlexNet](./AlexNet) by [Alex Krizhevsky](./Alex_Krizhevsky), [Ilya Sutskever](./Ilya_Sutskever), and [Geoffrey Hinton](./Geoffrey_Hinton)[[4]](./Deep_learning#cite_note-krizhevsky2012-4) won the large-scale [ImageNet competition](./ImageNet_competition) by a significant margin over shallow machine learning methods. Further incremental improvements included the [VGG-16](./VGG-19) network by [Karen Simonyan](./Karen_Simonyan_(scientist)?action=edit&redlink=1) and [Andrew Zisserman](./Andrew_Zisserman)[[119]](./Deep_learning#cite_note-VGG-119) and Google's [Inceptionv3](./Inceptionv3).[[120]](./Deep_learning#cite_note-szegedy-120)

 

The success in image classification was then extended to the more challenging task of [generating descriptions](./Automatic_image_annotation) (captions) for images, often as a combination of CNNs and LSTMs.[[121]](./Deep_learning#cite_note-1411.4555-121)[[122]](./Deep_learning#cite_note-1411.4952-122)[[123]](./Deep_learning#cite_note-1411.2539-123)

 

In 2014, the state of the art was training "very deep neural network" with 20 to 30 layers.[[124]](./Deep_learning#cite_note-124) Stacking too many layers led to a steep reduction in [training](./Training,_validation,_and_test_data_sets) accuracy,[[125]](./Deep_learning#cite_note-prelu-125) known as the "degradation" problem.[[126]](./Deep_learning#cite_note-He_Zhang_Deep_Residual_Learning_for_Image_Recognition-126) In 2015, two techniques were developed to train very deep networks: the [highway network](./Highway_network) was published in May 2015, and the [residual neural network](./Residual_neural_network) (ResNet)[[126]](./Deep_learning#cite_note-He_Zhang_Deep_Residual_Learning_for_Image_Recognition-126) in Dec 2015. ResNet behaves like an open-gated Highway Net.

 

Around the same time, deep learning started impacting the field of art. Early examples included [Google DeepDream](./DeepDream) (2015), and [neural style transfer](./Neural_style_transfer) (2015),[[127]](./Deep_learning#cite_note-127) both of which were based on pretrained image classification neural networks, such as [VGG-19](./VGG-19).

 

[Generative adversarial network](./Generative_adversarial_network) (GAN) by ([Ian Goodfellow](./Ian_Goodfellow) et al., 2014)[[128]](./Deep_learning#cite_note-GANnips-128) (based on  [Jürgen Schmidhuber](./Jürgen_Schmidhuber)'s principle of artificial curiosity[[74]](./Deep_learning#cite_note-curiosity1991-74)[[76]](./Deep_learning#cite_note-gancurpm2020-76))
became state of the art in generative modeling during 2014-2018 period. Excellent image quality is achieved by [Nvidia](./Nvidia)'s [StyleGAN](./StyleGAN) (2018)[[129]](./Deep_learning#cite_note-SyncedReview2018-129) based on the Progressive GAN by Tero Karras et al.[[130]](./Deep_learning#cite_note-progressiveGAN2017-130) Here the GAN generator is grown from small to large scale in a pyramidal fashion. Image generation by GAN reached popular success, and provoked discussions concerning [deepfakes](./Deepfake).[[131]](./Deep_learning#cite_note-131) [Diffusion models](./Diffusion_model) (2015)[[132]](./Deep_learning#cite_note-132) eclipsed GANs in generative modeling since then, with systems such as [DALL·E 2](./DALL-E) (2022) and [Stable Diffusion](./Stable_Diffusion) (2022).

 

In 2015, Google's speech recognition improved by 49% by an LSTM-based model, which they made available through [Google Voice Search](./Google_Voice_Search) on [smartphone](./Smartphone).[[133]](./Deep_learning#cite_note-GoogleVoiceTranscription-133)[[134]](./Deep_learning#cite_note-sak2015-134)

 

Deep learning is part of state-of-the-art systems in various disciplines, particularly computer vision and [automatic speech recognition](./Automatic_speech_recognition) (ASR). Results on commonly used evaluation sets such as [TIMIT](./TIMIT) (ASR) and [MNIST](./MNIST_database) ([image classification](./Image_classification)), as well as a range of large-vocabulary speech recognition tasks have steadily improved.[[102]](./Deep_learning#cite_note-HintonDengYu2012-102)[[135]](./Deep_learning#cite_note-135) Convolutional neural networks were superseded for ASR by [LSTM](./LSTM).[[134]](./Deep_learning#cite_note-sak2015-134)[[136]](./Deep_learning#cite_note-sak2014-136)[[137]](./Deep_learning#cite_note-liwu2015-137)[[138]](./Deep_learning#cite_note-zen2015-138) but are more successful in computer vision.

 

[Yoshua Bengio](./Yoshua_Bengio), [Geoffrey Hinton](./Geoffrey_Hinton) and [Yann LeCun](./Yann_LeCun) were awarded the 2018 [Turing Award](./Turing_Award) for "conceptual and engineering breakthroughs that have made deep neural networks a critical component of computing".[[139]](./Deep_learning#cite_note-139)

 


