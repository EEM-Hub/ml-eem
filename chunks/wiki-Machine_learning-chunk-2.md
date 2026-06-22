---
source: sources/wiki-Machine_learning.md
source_url: https://en.wikipedia.org/wiki/Machine_learning
chunk: 2/8
---

## Relationships to other fields

 

### Artificial intelligence

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/b/bb/AI-ML-DL.svg/250px-AI-ML-DL.svg.png)](./File:AI-ML-DL.svg)[Deep learning](./Deep_learning) is a subset of machine learning, which is itself a subset of [artificial intelligence](./Artificial_intelligence).[[20]](./Machine_learning#cite_note-journalimcms.org-20) 

As a scientific endeavour, machine learning grew out of the quest for [artificial intelligence](./Artificial_intelligence) (AI). In the early days of AI as an [academic discipline](./Discipline_(academia)), some researchers were interested in having machines learn from data. They attempted to approach the problem with various symbolic methods, as well as what were then termed "[neural networks](./Artificial_neural_network)"; these were mostly [perceptrons](./Perceptron) and [other models](./ADALINE) that were later found to be reinventions of the [generalised linear models](./Generalised_linear_model) of statistics.[[21]](./Machine_learning#cite_note-21) [Probabilistic reasoning](./Probabilistic_reasoning) was also employed, especially in [automated medical diagnosis](./Automated_medical_diagnosis).[[22]](./Machine_learning#cite_note-aima-22): 488 

 

However, an increasing emphasis on the [logical, knowledge-based approach](./Symbolic_AI) caused a rift between AI and machine learning. Probabilistic systems were plagued by theoretical and practical problems of data acquisition and representation.[[22]](./Machine_learning#cite_note-aima-22): 488  By 1980, [expert systems](./Expert_system) had come to dominate AI, and statistics was out of favour.[[23]](./Machine_learning#cite_note-changing-23) Work on symbolic/knowledge-based learning continued within AI, leading to [inductive logic programming](./Inductive_logic_programming) (ILP), but the more statistical line of research was now outside the field of AI proper, in [pattern recognition](./Pattern_recognition) and [information retrieval](./Information_retrieval).[[22]](./Machine_learning#cite_note-aima-22): 708–710, 755  Neural network research was abandoned by AI and [computer science](./Computer_science) around the same time. This subfield, termed "[connectionism](./Connectionism)", was continued by researchers from other disciplines, including [John Hopfield](./John_Hopfield), [David Rumelhart](./David_Rumelhart), and [Geoffrey Hinton](./Geoffrey_Hinton). Their main success came in the mid-1980s with the reinvention of [backpropagation](./Backpropagation).[[22]](./Machine_learning#cite_note-aima-22): 25 

 

Machine learning (ML), reorganised and recognised as its own field, started to flourish in the 1990s. The field changed its goal from achieving artificial intelligence to tackling solvable problems of a practical nature. It shifted focus away from the [symbolic approaches](./Symbolic_artificial_intelligence) it had inherited from AI, and toward methods and models borrowed from statistics, [fuzzy logic](./Fuzzy_logic), and [probability theory](./Probability_theory).[[23]](./Machine_learning#cite_note-changing-23)

 

### Data compression

 This section is an excerpt from [Data compression § Machine learning](./Data_compression#Machine_learning).[[edit](https://en.wikipedia.org/w/index.php?title=Data_compression&action=edit)] 

There is a close connection between machine learning and compression. A system that predicts the [posterior probabilities](./Posterior_probabilities) of a sequence given its entire history can be used for optimal data compression (by using [arithmetic coding](./Arithmetic_coding) on the output distribution). Conversely, an optimal compressor can be used for prediction (by finding the symbol that compresses best, given the previous history). This equivalence has been used as a justification for using data compression as a benchmark for "general intelligence".[[24]](./Machine_learning#cite_note-Data_compression_Mahoney-24)[[25]](./Machine_learning#cite_note-Data_compression_Market_Efficiency-25)[[26]](./Machine_learning#cite_note-Data_compression_Ben-Gal-26)

 

An alternative view can show compression algorithms implicitly map strings into implicit [feature space vectors](./Feature_space_vector), and compression-based similarity measures compute similarity within these feature spaces. For each compressor C(.) we define an associated vector space ℵ, such that C(.) maps an input string x, corresponding to the vector norm ||~x||. An exhaustive examination of the feature spaces underlying all compression algorithms is precluded by space; instead, feature vectors chooses to examine three representative lossless compression methods, LZW, LZ77, and PPM.[[27]](./Machine_learning#cite_note-Data_compression_ScullyBrodley-27)

 

According to [AIXI](./AIXI) theory, a connection more directly explained in [Hutter Prize](./Hutter_Prize), the best possible compression of x is the smallest possible software that generates x. For example, in that model, a zip file's compressed size includes both the zip file and the unzipping software, since you can not unzip it without both, but there may be an even smaller combined form.

 

Examples of AI-powered audio/video compression software include [NVIDIA Maxine](./NVIDIA_Maxine), AIVC.[[28]](./Machine_learning#cite_note-28) Examples of software that can perform AI-powered image compression include [OpenCV](./OpenCV), [TensorFlow](./TensorFlow), [MATLAB](./MATLAB)'s Image Processing Toolbox (IPT) and High-Fidelity Generative Image Compression.[[29]](./Machine_learning#cite_note-29)

 

In [unsupervised machine learning](./Unsupervised_machine_learning), [k-means clustering](./K-means_clustering) can be utilized to compress data by grouping similar data points into clusters. This technique simplifies handling extensive datasets that lack predefined labels and finds widespread use in fields such as [image compression](./Image_compression).[[30]](./Machine_learning#cite_note-30)

 

Data compression aims to reduce the size of data files, enhancing storage efficiency and speeding up data transmission. K-means clustering, an unsupervised machine learning algorithm, is employed to partition a dataset into a specified number of clusters, k, each represented by the [centroid](./Centroid) of its points. This process condenses extensive datasets into a more compact set of representative points. Particularly beneficial in [image](./Image_processing) and [signal processing](./Signal_processing), k-means clustering aids in data reduction by replacing groups of data points with their centroids, thereby preserving the core information of the original data while significantly decreasing the required storage space.[[31]](./Machine_learning#cite_note-31)

 

[Large language models](./Large_language_model) (LLMs) are also efficient lossless data compressors on some data sets, as demonstrated by [DeepMind](./DeepMind)'s research with the Chinchilla 70B model. Developed by DeepMind, Chinchilla 70B effectively compressed data, outperforming conventional methods such as [Portable Network Graphics](./Portable_Network_Graphics) (PNG) for images and [Free Lossless Audio Codec](./Free_Lossless_Audio_Codec) (FLAC) for audio. It achieved compression of image and audio data to 43.4% and 16.4% of their original sizes, respectively. There is, however, some reason to be concerned that the data set used for testing overlaps the LLM training data set, making it possible that the Chinchilla 70B model is only an efficient compression tool on data it has already been trained on.[[32]](./Machine_learning#cite_note-32)[[33]](./Machine_learning#cite_note-33)

   

### Data mining

 

Machine learning and [data mining](./Data_mining) often employ the same methods and overlap significantly, but while machine learning focuses on prediction based on *known* properties learned from the training data, data mining focuses on the [discovery](./Discovery_(observation)) of previously *unknown* properties in the data (this is the analysis step of [knowledge discovery](./Knowledge_discovery) in databases). Data mining uses many machine learning methods, but with different goals; on the other hand, machine learning also employs data mining methods as "[unsupervised learning](./Unsupervised_learning)" or as a preprocessing step to improve learner accuracy. Much of the confusion between these two research communities (which often have separate conferences and separate journals, [[ECML PKDD]] being a major exception) comes from the basic assumptions they work with: in machine learning, performance is usually evaluated with respect to the ability to *reproduce known* knowledge, while in knowledge discovery and data mining (KDD) the key task is the discovery of previously *unknown* knowledge. Evaluated with respect to known knowledge, an uninformed (unsupervised) method will easily be outperformed by other supervised methods, while in a typical KDD task, supervised methods cannot be used due to the unavailability of training data.[*[citation needed](./Wikipedia:Citation_needed)*]

 

Machine learning also has intimate ties to [optimization](./Optimization): Many learning problems are formulated as minimisation of some [loss function](./Loss_function) on a training set of examples. Loss functions express the discrepancy between the predictions of the model being trained and the actual problem instances (for example, in classification, one wants to assign a [label](./Labeled_data) to instances, and models are trained to correctly predict the preassigned labels of a set of examples).[[34]](./Machine_learning#cite_note-34)

 

### Generalization

 

Characterizing the generalisation of various learning algorithms is an active topic of current research, especially for [deep learning](./Deep_learning) algorithms.[*[citation needed](./Wikipedia:Citation_needed)*]

 

### Statistics

 

Machine learning and [statistics](./Statistics) are closely related fields in terms of methods, but distinct in their principal goal: statistics draws population [inferences](./Statistical_inference) from a [sample](./Sample_(statistics)), while machine learning finds generalisable predictive patterns.[[35]](./Machine_learning#cite_note-35)

 

Conventional statistical analyses require the a priori selection of a model most suitable for the study data set. In addition, only significant or theoretically relevant variables based on previous experience are included for analysis. In contrast, machine learning is not built on a pre-structured model; rather, the data shape the model by detecting underlying patterns. The more variables (input) used to train the model, the more accurate the ultimate model will be.[[36]](./Machine_learning#cite_note-36)

 

[Leo Breiman](./Leo_Breiman) distinguished two statistical modelling paradigms: the data model and the algorithmic model,[[37]](./Machine_learning#cite_note-Cornell-University-Library-2001-37) wherein "algorithmic model" means more or less the machine learning algorithms like [Random forest](./Random_forest).[*[clarification needed](./Wikipedia:Please_clarify)*]

 

Some statisticians have adopted methods from machine learning, producing the field of *statistical learning*.[[38]](./Machine_learning#cite_note-islr-38)

 

### Statistical physics

 

Analytical and computational techniques derived from deep-rooted physics of disordered systems can be extended to large-scale problems, including machine learning, e.g., to analyse the weight space of [deep neural networks](./Deep_neural_network).[[39]](./Machine_learning#cite_note-SP_1-39) Statistical physics is thus finding applications in the area of [medical diagnostics](./Medical_diagnostics).[[40]](./Machine_learning#cite_note-SP_2-40)[*[clarification needed](./Wikipedia:Please_clarify)*]

 

##  Theory

 Main articles: [Computational learning theory](./Computational_learning_theory) and [Statistical learning theory](./Statistical_learning_theory) 

A core objective of a learner is to generalise from its experience.[[2]](./Machine_learning#cite_note-bishop2006-2)[[41]](./Machine_learning#cite_note-Mohri-2012-41) Generalisation in this context is the ability of a learning machine to perform accurately on new, unseen examples/tasks after having experienced a learning data set. The training examples come from some generally unknown probability distribution (considered representative of the space of occurrences) and the learner has to build a general model about this space that enables it to produce sufficiently accurate predictions in new cases.

 

The computational analysis of machine learning algorithms and their performance is a branch of [theoretical computer science](./Theoretical_computer_science) known as [computational learning theory](./Computational_learning_theory) via the [probably approximately correct learning](./Probably_approximately_correct_learning) model.[*[clarification needed](./Wikipedia:Please_clarify)*] Because training sets are finite and the future is uncertain, learning theory usually does not yield guarantees of the performance of algorithms. Instead, probabilistic bounds on the performance are quite common. The [bias–variance decomposition](./Bias–variance_decomposition) is one way to quantify generalisation [error](./Errors_and_residuals).[*[citation needed](./Wikipedia:Citation_needed)*]

 

For the best performance in the context of generalisation, the complexity of the hypothesis should match the complexity of the function underlying the data. If the hypothesis is less complex than the function, then the model has underfitted the data. If the complexity of the model is increased in response, then the training error decreases. But if the hypothesis is too complex, then the model is subject to [overfitting](./Overfitting) and generalisation will be poorer.[[42]](./Machine_learning#cite_note-alpaydin-42)

 

In addition to performance bounds, learning theorists study the time complexity and feasibility of learning. In computational learning theory, a computation is considered feasible if it can be done in [polynomial time](./Time_complexity#Polynomial_time). There are two kinds of [time complexity](./Time_complexity) results: Positive results show that a certain class of functions can be learned in polynomial time. Negative results show that certain classes cannot be learned in polynomial time.[*[citation needed](./Wikipedia:Citation_needed)*]

 


