---
source: sources/wiki-Convolutional_neural_network.md
source_url: https://en.wikipedia.org/wiki/Convolutional_neural_network
chunk: 2/8
---

## History

 

CNN are often compared to the way the brain achieves vision processing in living [organisms](./Organisms).[[36]](./Convolutional_neural_network#cite_note-36)

 

### Receptive fields in the visual cortex

 Main article: [Surround suppression](./Surround_suppression) 

Work by [Hubel](./David_H._Hubel) and [Wiesel](./Torsten_Wiesel) in the 1950s and 1960s showed that cat [visual cortices](./Visual_cortex) contain neurons that individually respond to small regions of the [visual field](./Visual_field). Provided the eyes are not moving, the region of visual space within which visual stimuli affect the firing of a single neuron is known as its [receptive field](./Receptive_field).[[37]](./Convolutional_neural_network#cite_note-:4-37) Neighboring cells have similar and overlapping receptive fields. Receptive field size and location varies systematically across the cortex to form a complete map of visual space.[*[citation needed](./Wikipedia:Citation_needed)*] The cortex in each hemisphere represents the contralateral [visual field](./Visual_field).[*[citation needed](./Wikipedia:Citation_needed)*]

 

Their 1968 paper identified two basic visual cell types in the brain:[[19]](./Convolutional_neural_network#cite_note-hubelwiesel1968-19)

 
- [simple cells](./Simple_cell), whose output is maximized by straight edges having particular orientations within their receptive field
- [complex cells](./Complex_cell), which have larger [receptive fields](./Receptive_field), whose output is insensitive to the exact position of the edges in the field.

 

Hubel and Wiesel also proposed a cascading model of these two types of cells for use in pattern recognition tasks.[[38]](./Convolutional_neural_network#cite_note-38)[[37]](./Convolutional_neural_network#cite_note-:4-37)

 

### Fukushima's analog threshold elements in a vision model

 

In 1969, [Kunihiko Fukushima](./Kunihiko_Fukushima) introduced a multilayer visual feature detection network, inspired by the above-mentioned work of Hubel and Wiesel, in which "All the elements in one layer have the same set of interconnecting coefficients; the arrangement of the elements and their interconnections are all homogeneous over a given layer."  This is the essential core of a convolutional network, but the weights were not trained.  In the same paper, Fukushima also introduced the [ReLU](./Rectifier_(neural_networks)) (rectified linear unit) [activation function](./Activation_function).[[39]](./Convolutional_neural_network#cite_note-Fukushima1969-39)[[40]](./Convolutional_neural_network#cite_note-DLhistory-40)

 

### Neocognitron, origin of the trainable CNN architecture

 

The "[neocognitron](./Neocognitron)"[[18]](./Convolutional_neural_network#cite_note-fukuneoscholar-18) was introduced by Fukushima in 1980.[[20]](./Convolutional_neural_network#cite_note-intro-20)[[28]](./Convolutional_neural_network#cite_note-mcdns-28)[[1]](./Convolutional_neural_network#cite_note-LeCun2015-1)  The neocognitron introduced the two basic types of layers:

 
- "S-layer": a shared-weights receptive-field layer, later known as a convolutional layer, which contains units whose receptive fields cover a patch of the previous layer. A shared-weights receptive-field group (a "plane" in neocognitron terminology) is often called a filter, and a layer typically has several such filters.
- "C-layer": a downsampling layer that contain units whose receptive fields cover patches of previous convolutional layers. Such a unit typically computes a weighted average of the activations of the units in its patch, and applies inhibition (divisive normalization) pooled from a somewhat larger patch and across different filters in a layer, and applies a saturating activation function. The patch weights are nonnegative and are not trainable in the original neocognitron. The downsampling and competitive inhibition help to classify features and objects in visual scenes even when the objects are shifted.

 

Several [supervised](./Supervised_learning) and [unsupervised learning](./Unsupervised_learning) algorithms have been proposed over the decades to train the weights of a neocognitron.[[18]](./Convolutional_neural_network#cite_note-fukuneoscholar-18) Today, however, the CNN architecture is usually trained through [backpropagation](./Backpropagation).

 

Fukushima's ReLU activation function was not used in his neocognitron since all the weights were nonnegative; lateral inhibition was used instead. The rectifier has become a very popular activation function for CNNs and [deep neural networks](./Deep_learning) in general.[[41]](./Convolutional_neural_network#cite_note-41)

 

### Convolution in time

 

The term "convolution" first appears in neural networks in a paper by Toshiteru Homma, Les Atlas, and Robert Marks II at the first [Conference on Neural Information Processing Systems](./Conference_on_Neural_Information_Processing_Systems) in 1987. Their paper replaced multiplication with convolution in time, inherently providing shift invariance, motivated by and connecting more directly to the [signal-processing concept of a filter](./Linear_shift-invariant_filter), and demonstrated it on a speech recognition task.[[8]](./Convolutional_neural_network#cite_note-homma-8) They also pointed out that as a data-trainable system, convolution is essentially equivalent to correlation since reversal of the weights does not affect the final learned function ("For convenience, we denote * as correlation instead of convolution. Note that convolving a(t) with b(t) is equivalent to correlating a(-t) with b(t).").[[8]](./Convolutional_neural_network#cite_note-homma-8) Modern CNN implementations typically do correlation and call it convolution, for convenience, as they did here.

 

### Time delay neural networks

 

The [time delay neural network](./Time_delay_neural_network) (TDNN) was introduced in 1987 by [Alex Waibel](./Alex_Waibel) et al. for phoneme recognition and was an early convolutional network exhibiting shift-invariance.[[42]](./Convolutional_neural_network#cite_note-Waibel1987-42) A TDNN is a 1-D convolutional neural net where the convolution is performed along the time axis of the data. It is the first CNN utilizing weight sharing in combination with a training by gradient descent, using [backpropagation](./Backpropagation).[[43]](./Convolutional_neural_network#cite_note-speechsignal-43) Thus, while also using a pyramidal structure as in the neocognitron, it performed a global optimization of the weights instead of a local one.[[42]](./Convolutional_neural_network#cite_note-Waibel1987-42)

 

TDNNs are convolutional networks that share weights along the temporal dimension.[[44]](./Convolutional_neural_network#cite_note-44) They allow speech signals to be processed time-invariantly. In 1990 Hampshire and Waibel introduced a variant that performs a two-dimensional convolution.[[45]](./Convolutional_neural_network#cite_note-Hampshire1990-45) Since these TDNNs operated on spectrograms, the resulting phoneme recognition system was invariant to both time and frequency shifts, as with images processed by a neocognitron.

 

TDNNs improved the performance of far-distance speech recognition.[[46]](./Convolutional_neural_network#cite_note-Ko2017-46)

 

### Image recognition with CNNs trained by gradient descent

 

Denker et al. (1989) designed a 2-D CNN system to recognize hand-written [ZIP Code](./ZIP_Code) numbers.[[47]](./Convolutional_neural_network#cite_note-47) However, the lack of an efficient training method to determine the [kernel](./Kernel_(image_processing)) coefficients of the involved convolutions meant that all the coefficients had to be laboriously hand-designed.[[48]](./Convolutional_neural_network#cite_note-:2-48)

 

Following the advances in the training of 1-D CNNs by Waibel et al. (1987), [Yann LeCun](./Yann_LeCun) et al. (1989)[[48]](./Convolutional_neural_network#cite_note-:2-48) used back-propagation to learn the convolution kernel coefficients directly from images of hand-written numbers. Learning was thus fully automatic, performed better than manual coefficient design, and was suited to a broader range of image recognition problems and image types. 
Wei Zhang et al. (1988)[[14]](./Convolutional_neural_network#cite_note-:0-14)[[15]](./Convolutional_neural_network#cite_note-:1-15) used back-propagation to train the convolution kernels of a CNN for alphabets recognition. The model was called shift-invariant pattern recognition neural network before the name CNN was coined later in the early 1990s. Wei Zhang et al. also applied the same CNN without the last fully connected layer for medical image object segmentation (1991)[[49]](./Convolutional_neural_network#cite_note-:wz1991-49) and breast cancer detection in mammograms (1994).[[50]](./Convolutional_neural_network#cite_note-:wz1994-50)

 

This approach became a foundation of modern [computer vision](./Computer_vision).

 

#### Max pooling

 

In 1990 Yamaguchi et al. introduced the concept of max pooling, a fixed filtering operation that calculates and propagates the maximum value of a given region. They did so by combining TDNNs with max pooling to realize a speaker-independent isolated word recognition system.[[27]](./Convolutional_neural_network#cite_note-Yamaguchi111990-27) In their system they used several TDNNs per word, one for each [syllable](./Syllable). The results of each TDNN over the input signal were combined using max pooling and the outputs of the pooling layers were then passed on to networks performing the actual word classification.

 

In a variant of the neocognitron called the *cresceptron*, instead of using Fukushima's spatial averaging with inhibition and saturation, J. Weng et al. in 1993 used max pooling, where a downsampling unit computes the maximum of the activations of the units in its patch,[[51]](./Convolutional_neural_network#cite_note-weng1993-51) introducing this method into the vision field.

 

Max pooling is often used in modern CNNs.[[52]](./Convolutional_neural_network#cite_note-schdeepscholar-52)

 

#### LeNet-5

 Main article: [LeNet](./LeNet) 

LeNet-5, a pioneering 7-level convolutional network by [LeCun](./Yann_LeCun) et al. in 1995,[[53]](./Convolutional_neural_network#cite_note-lecun95-53) classifies hand-written numbers on [checks](./Cheque) digitized in 32×32 pixel images. The ability to process higher-resolution images requires larger and more layers of convolutional neural networks, so this technique is constrained by the availability of computing resources.

 

It was superior than other commercial courtesy amount reading systems (as of 1995). The system was integrated in [NCR](./NCR_Voyix)'s check reading systems, and fielded in several American banks since June 1996, reading millions of checks per day.[[54]](./Convolutional_neural_network#cite_note-54)

 

### Shift-invariant neural network

 

A shift-invariant neural network was proposed by Wei Zhang et al. for image character recognition in 1988.[[14]](./Convolutional_neural_network#cite_note-:0-14)[[15]](./Convolutional_neural_network#cite_note-:1-15) It is a modified Neocognitron by keeping only the convolutional interconnections between the image feature layers and the last fully connected layer. The model was trained with back-propagation. The training algorithm was further improved in 1991[[55]](./Convolutional_neural_network#cite_note-55) to improve its generalization ability. The model architecture was modified by removing the last fully connected layer and applied for medical image segmentation (1991)[[49]](./Convolutional_neural_network#cite_note-:wz1991-49) and automatic detection of breast cancer in [mammograms (1994)](./Mammography).[[50]](./Convolutional_neural_network#cite_note-:wz1994-50)

 

A different convolution-based design was proposed in 1988[[56]](./Convolutional_neural_network#cite_note-56) for application to decomposition of one-dimensional [electromyography](./Electromyography) convolved signals via de-convolution. This design was modified in 1989 to other de-convolution-based designs.[[57]](./Convolutional_neural_network#cite_note-57)[[58]](./Convolutional_neural_network#cite_note-58)

 

### GPU implementations

 

Although CNNs were invented in the 1980s, their breakthrough in the 2000s required fast implementations on [graphics processing units](./Graphics_processing_unit) (GPUs).

 

In 2004, it was shown by K. S. Oh and K. Jung that standard neural networks can be greatly accelerated on GPUs. Their implementation was 20 times faster than an equivalent implementation on [CPU](./CPU).[[59]](./Convolutional_neural_network#cite_note-59) In 2005, another paper also emphasised the value of [GPGPU](./GPGPU) for [machine learning](./Machine_learning).[[60]](./Convolutional_neural_network#cite_note-60)

 

The first GPU-implementation of a CNN was described in 2006 by K. Chellapilla et al. Their implementation was 4 times faster than an equivalent implementation on CPU.[[61]](./Convolutional_neural_network#cite_note-61) In the same period, GPUs were also used for unsupervised training of [deep belief networks](./Deep_belief_network).[[62]](./Convolutional_neural_network#cite_note-62)[[63]](./Convolutional_neural_network#cite_note-63)[[64]](./Convolutional_neural_network#cite_note-64)[[65]](./Convolutional_neural_network#cite_note-LSD_1-65)

 

In 2010, Dan Ciresan et al. at [IDSIA](./IDSIA) trained deep feedforward networks on GPUs.[[66]](./Convolutional_neural_network#cite_note-66) In 2011, they extended this to CNNs, accelerating by 60 compared to training CPU.[[25]](./Convolutional_neural_network#cite_note-flexible-25) In 2011, the network won an image recognition contest where they achieved superhuman performance for the first time.[[67]](./Convolutional_neural_network#cite_note-67) Then they won more competitions and achieved state of the art on several benchmarks.[[68]](./Convolutional_neural_network#cite_note-68)[[52]](./Convolutional_neural_network#cite_note-schdeepscholar-52)[[28]](./Convolutional_neural_network#cite_note-mcdns-28)

 

Subsequently, [AlexNet](./AlexNet), a similar GPU-based CNN by Alex Krizhevsky et al. won the [ImageNet Large Scale Visual Recognition Challenge](./ImageNet_Large_Scale_Visual_Recognition_Challenge) 2012.[[69]](./Convolutional_neural_network#cite_note-:02-69) It was an early catalytic event for the [AI boom](./AI_boom).

 

Compared to the training of CNNs using [GPUs](./GPU), not much attention was given to CPU. (Viebke et al 2019) parallelizes CNN by thread- and [SIMD](./SIMD)-level parallelism that is available on the [Intel Xeon Phi](./Xeon_Phi).[[70]](./Convolutional_neural_network#cite_note-70)[[71]](./Convolutional_neural_network#cite_note-71)

 

## Distinguishing features

 

In the past, traditional [multilayer perceptron](./Multilayer_perceptron) (MLP) models were used for image recognition.[*[example needed](./Wikipedia:AUDIENCE)*] However, the full connectivity between nodes caused the [curse of dimensionality](./Curse_of_dimensionality), and was computationally intractable with higher-resolution images. A 1000×1000-pixel image with [RGB color](./RGB_color_model) channels has 3 million weights per fully-connected neuron, which is too high to feasibly process efficiently at scale.

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/8/8a/Conv_layers.png/250px-Conv_layers.png)](./File:Conv_layers.png)CNN layers arranged in 3 dimensions 

For example, in [CIFAR-10](./CIFAR-10), images are only of size 32×32×3 (32 wide, 32 high, 3 color channels), so a single fully connected neuron in the first hidden layer of a regular neural network would have 32*32*3 = 3,072 weights. A 200×200 image, however, would lead to neurons that have 200*200*3 = 120,000 weights.

 

Also, such network architecture does not take into account the spatial structure of data, treating input pixels which are far apart in the same way as pixels that are close together. This ignores [locality of reference](./Locality_of_reference) in data with a grid-topology (such as images), both computationally and semantically. Thus, full connectivity of neurons is wasteful for purposes such as image recognition that are dominated by [spatially local](./Spatial_locality) input patterns.

 

Convolutional neural networks are variants of multilayer perceptrons, designed to emulate the behavior of a [visual cortex](./Visual_cortex). These models mitigate the challenges posed by the MLP architecture by exploiting the strong spatially local correlation present in natural images. As opposed to MLPs, CNNs have the following distinguishing features:

 
- 3D volumes of neurons. The layers of a CNN have neurons arranged in [3 dimensions](./Three-dimensional_space): width, height and depth.[[72]](./Convolutional_neural_network#cite_note-72) Each neuron inside a convolutional layer is connected to only a small region of the layer before it, called a receptive field. Distinct types of layers, both locally and completely connected, are stacked to form a CNN architecture.
- Local connectivity: following the concept of receptive fields, CNNs exploit spatial locality by enforcing a local connectivity pattern between neurons of adjacent layers. The architecture thus ensures that the learned "filters" produce the strongest response to a spatially local input pattern. Stacking many such layers leads to nonlinear filters that become increasingly global (i.e. responsive to a larger region of pixel space) so that the network first creates representations of small parts of the input, then from them assembles representations of larger areas.
- Shared weights: In CNNs, each filter is replicated across the entire visual field. These replicated units share the same parameterization (weight vector and bias) and form a feature map. This means that all the neurons in a given convolutional layer respond to the same feature within their specific response field. Replicating units in this way allows for the resulting activation map to be [equivariant](./Equivariant_map) under shifts of the locations of input features in the visual field, i.e. they grant translational [equivariance](./Equivariant_map)—given that the layer has a stride of one.[[73]](./Convolutional_neural_network#cite_note-:5-73)
- Pooling: In a CNN's [pooling layers](./Pooling_layer), feature maps are divided into rectangular sub-regions, and the features in each rectangle are independently down-sampled to a single value, commonly by taking their average or maximum value. In addition to reducing the sizes of feature maps, the pooling operation grants a degree of local [translational invariance](./Translational_symmetry) to the features contained therein, allowing the CNN to be more robust to variations in their positions.[[16]](./Convolutional_neural_network#cite_note-:6-16)

 

Together, these properties allow CNNs to achieve better generalization on [vision problems](./Computer_vision). Weight sharing dramatically reduces the number of [free parameters](./Free_parameter) learned, thus lowering the memory requirements for running the network and allowing the training of larger, more powerful networks.

 


