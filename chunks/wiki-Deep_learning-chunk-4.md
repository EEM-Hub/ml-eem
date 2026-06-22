---
source: sources/wiki-Deep_learning.md
source_url: https://en.wikipedia.org/wiki/Deep_learning
chunk: 4/7
---

## Applications

 

### Automatic speech recognition

 Main article: [Speech recognition](./Speech_recognition) 

Large-scale automatic speech recognition is the first and most convincing successful case of deep learning. LSTM RNNs can learn "Very Deep Learning" tasks[[9]](./Deep_learning#cite_note-SCHIDHUB-9) that involve multi-second intervals containing speech events separated by thousands of discrete time steps, where one time step corresponds to about 10 ms. LSTM with forget gates[[153]](./Deep_learning#cite_note-:10-153) is competitive with traditional speech recognizers on certain tasks.[[93]](./Deep_learning#cite_note-graves2003-93)

 

The initial success in speech recognition was based on small-scale recognition tasks based on TIMIT. The data set contains 630 speakers from eight major [dialects](./Dialect) of [American English](./American_English), where each speaker reads 10 sentences.[[175]](./Deep_learning#cite_note-APC_1-175) Its small size lets many configurations be tried. More importantly, the TIMIT task concerns [phone](./Phone_(phonetics))-sequence recognition, which, unlike word-sequence recognition, allows weak phone [bigram](./Bigram) language models. This lets the strength of the acoustic modeling aspects of speech recognition be more easily analyzed. The error rates listed below, including these early results and measured as percent phone error rates (PER), have been summarized since 1991.

 
| Method | Percent phoneerror rate (PER) (%) |
| --- | --- |
| Randomly Initialized RNN[176] | 26.1 |
| Bayesian Triphone GMM-HMM | 25.6 |
| Hidden Trajectory (Generative) Model | 24.8 |
| Monophone Randomly Initialized DNN | 23.4 |
| Monophone DBN-DNN | 22.4 |
| Triphone GMM-HMM with BMMI Training | 21.7 |
| Monophone DBN-DNN on fbank | 20.7 |
| Convolutional DNN[177] | 20.0 |
| Convolutional DNN w. Heterogeneous Pooling | 18.7 |
| Ensemble DNN/CNN/RNN[178] | 18.3 |
| Bidirectional LSTM | 17.8 |
| Hierarchical Convolutional Deep Maxout Network[179] | 16.5 |

 

The debut of DNNs for speaker recognition in the late 1990s and speech recognition around 2009-2011 and of LSTM around 2003–2007, accelerated progress in eight major areas:[[23]](./Deep_learning#cite_note-BOOK2014-23)[[106]](./Deep_learning#cite_note-interspeech2014Keynote-106)[[104]](./Deep_learning#cite_note-ReferenceA-104)

 
- Scale-up/out and accelerated DNN training and decoding
- Sequence discriminative training
- Feature processing by deep models with solid understanding of the underlying mechanisms
- Adaptation of DNNs and related deep models
- [Multi-task](./Multi-task_learning) and [transfer learning](./Transfer_learning) by DNNs and related deep models
- [CNNs](./Convolutional_neural_network) and how to design them to best exploit [domain knowledge](./Domain_knowledge) of speech
- [RNN](./Recurrent_neural_network) and its rich LSTM variants
- Other types of deep models including tensor-based models and integrated deep generative/discriminative models.

 

More recent speech recognition models use [Transformers](./Transformer_(deep_learning_architecture)) or [Temporal Convolution Networks](./Time_delay_neural_network) with significant success and widespread applications.[[180]](./Deep_learning#cite_note-180)[[181]](./Deep_learning#cite_note-181)[[182]](./Deep_learning#cite_note-182) All major commercial speech recognition systems (e.g., Microsoft [Cortana](./Cortana_(software)), [Xbox](./Xbox), [Skype Translator](./Skype_Translator), [Amazon Alexa](./Amazon_Alexa), [Google Now](./Google_Now), [Apple Siri](./Siri), [Baidu](./Baidu) and [iFlyTek](./IFlytek) voice search, and a range of [Nuance](./Nuance_Communications) speech products, etc.) are based on deep learning.[[23]](./Deep_learning#cite_note-BOOK2014-23)[[183]](./Deep_learning#cite_note-183)[[184]](./Deep_learning#cite_note-Baidu-184)

 

### Image recognition

 Main article: [Computer vision](./Computer_vision) Richard Green explains how deep learning is used with a [remotely operated vehicle](./Remotely_operated_underwater_vehicle) in [mussel aquaculture](./Mussel#Aquaculture). 

A common evaluation set for image classification is the [MNIST database](./MNIST_database) data set. MNIST is composed of handwritten digits and includes 60,000 training examples and 10,000 test examples. As with TIMIT, its small size lets users test multiple configurations. A comprehensive list of results on this set is available.[[185]](./Deep_learning#cite_note-YANNMNIST-185)

 

Deep learning-based image recognition has become "superhuman", producing more accurate results than human contestants. This first occurred in 2011 in recognition of traffic signs, and in 2014, with recognition of human faces.[[186]](./Deep_learning#cite_note-:7-186)[[187]](./Deep_learning#cite_note-surpass1-187)

 

Deep learning-trained vehicles now interpret 360° camera views.[[188]](./Deep_learning#cite_note-188) Another example is Facial Dysmorphology Novel Analysis (FDNA) used to analyze cases of human malformation connected to a large database of genetic syndromes.

 

### Visual art processing

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/7/75/Jimmy_Wales_in_France%2C_with_the_style_of_Munch%27s_%22The_Scream%22_applied_using_neural_style_transfer.jpg/250px-Jimmy_Wales_in_France%2C_with_the_style_of_Munch%27s_%22The_Scream%22_applied_using_neural_style_transfer.jpg)](./File:Jimmy_Wales_in_France,_with_the_style_of_Munch's_"The_Scream"_applied_using_neural_style_transfer.jpg)Visual art processing of Jimmy Wales in France, with the style of Munch's "[The Scream](./The_Scream)" applied using neural style transfer 

Closely related to the progress that has been made in image recognition is the increasing application of deep learning techniques to various visual art tasks. DNNs have proven themselves capable, for example, of

 
- identifying the style period of a given painting[[189]](./Deep_learning#cite_note-art1-189)[[190]](./Deep_learning#cite_note-art2-190)
- [Neural Style Transfer](./Neural_Style_Transfer) –  capturing the style of a given artwork and applying it in a visually pleasing manner to an arbitrary photograph or video[[189]](./Deep_learning#cite_note-art1-189)[[190]](./Deep_learning#cite_note-art2-190)
- generating striking imagery based on random visual input fields.[[189]](./Deep_learning#cite_note-art1-189)[[190]](./Deep_learning#cite_note-art2-190)

 

### Natural language processing

 Main article: [Natural language processing](./Natural_language_processing) 

Neural networks have been used for implementing language models since the early 2000s.[[147]](./Deep_learning#cite_note-gers2001-147) LSTM helped to improve machine translation and language modeling.[[148]](./Deep_learning#cite_note-NIPS2014-148)[[149]](./Deep_learning#cite_note-vinyals2016-149)[[150]](./Deep_learning#cite_note-gillick2015-150)

 

Other key techniques in this field are negative sampling[[191]](./Deep_learning#cite_note-GoldbergLevy2014-191) and [word embedding](./Word_embedding). Word embedding, such as *[word2vec](./Word2vec)*, can be thought of as a representational layer in a deep learning architecture that transforms an atomic word into a positional representation of the word relative to other words in the dataset; the position is represented as a point in a [vector space](./Vector_space). Using word embedding as an RNN input layer allows the network to parse sentences and phrases using an effective compositional vector grammar. A compositional vector grammar can be thought of as [probabilistic context free grammar](./Probabilistic_context_free_grammar) (PCFG) implemented by an RNN.[[192]](./Deep_learning#cite_note-SocherManning2014-192) Recursive auto-encoders built atop word embeddings can assess sentence similarity and detect paraphrasing.[[192]](./Deep_learning#cite_note-SocherManning2014-192) Deep neural architectures provide the best results for constituency parsing,[[193]](./Deep_learning#cite_note-193) [sentiment analysis](./Sentiment_analysis),[[194]](./Deep_learning#cite_note-RDM_1-194) information retrieval,[[195]](./Deep_learning#cite_note-195)[[196]](./Deep_learning#cite_note-196) spoken language understanding,[[197]](./Deep_learning#cite_note-IEEE-TASL2015-197) machine translation,[[148]](./Deep_learning#cite_note-NIPS2014-148)[[198]](./Deep_learning#cite_note-auto-198) contextual entity linking,[[198]](./Deep_learning#cite_note-auto-198) writing style recognition,[[199]](./Deep_learning#cite_note-BROC2017-199) [named-entity recognition](./Named-entity_recognition) (token classification),[[200]](./Deep_learning#cite_note-200) text classification, and others.[[201]](./Deep_learning#cite_note-201)

 

Recent developments generalize [word embedding](./Word_embedding) to [sentence embedding](./Sentence_embedding).

 

[Google Translate](./Google_Translate) (GT) uses a large end-to-end [long short-term memory](./Long_short-term_memory) (LSTM) network.[[202]](./Deep_learning#cite_note-GT_Turovsky_2016-202)[[203]](./Deep_learning#cite_note-googleblog_GNMT_2016-203)[[204]](./Deep_learning#cite_note-GoogleTranslate-204)[[205]](./Deep_learning#cite_note-WiredGoogleTranslate-205) [Google Neural Machine Translation (GNMT)](./Google_Neural_Machine_Translation) uses an [example-based machine translation](./Example-based_machine_translation) method in which the system "learns from millions of examples".[[203]](./Deep_learning#cite_note-googleblog_GNMT_2016-203) It translates "whole sentences at a time, rather than pieces". Google Translate supports over one hundred languages.[[203]](./Deep_learning#cite_note-googleblog_GNMT_2016-203) The network encodes the "semantics of the sentence rather than simply memorizing phrase-to-phrase translations".[[203]](./Deep_learning#cite_note-googleblog_GNMT_2016-203)[[206]](./Deep_learning#cite_note-Biotet-206) GT uses English as an intermediate between most language pairs.[[206]](./Deep_learning#cite_note-Biotet-206)

 

### Drug discovery and toxicology

 For more information, see [Drug discovery](./Drug_discovery) and [Toxicology](./Toxicology). 

A large percentage of candidate drugs fail to win regulatory approval. These failures are caused by insufficient efficacy (on-target effect), undesired interactions (off-target effects), or unanticipated [toxic effects](./Toxicity).[[207]](./Deep_learning#cite_note-ARROWSMITH2013-207)[[208]](./Deep_learning#cite_note-VERBIEST2015-208) Research has explored use of deep learning to predict the [biomolecular targets](./Biomolecular_target),[[209]](./Deep_learning#cite_note-MERCK2012-209)[[210]](./Deep_learning#cite_note-:5-210) [off-targets](./Off-target), and [toxic effects](./Toxicity) of environmental chemicals in nutrients, household products and drugs.[[211]](./Deep_learning#cite_note-TOX21-211)[[212]](./Deep_learning#cite_note-TOX21Data-212)[[213]](./Deep_learning#cite_note-:11-213)

 

AtomNet is a deep learning system for structure-based [rational drug design](./Drug_design).[[214]](./Deep_learning#cite_note-214) AtomNet was used to predict novel candidate biomolecules for disease targets such as the [Ebola virus](./Ebola_virus)[[215]](./Deep_learning#cite_note-Toronto-215) and [multiple sclerosis](./Multiple_sclerosis).[[216]](./Deep_learning#cite_note-216)[[215]](./Deep_learning#cite_note-Toronto-215)

 

In 2017 [graph neural networks](./Graph_neural_network) were used for the first time to predict various properties of molecules in a large toxicology data set.[[217]](./Deep_learning#cite_note-217) In 2019, generative neural networks were used to produce molecules that were validated experimentally all the way into mice.[[218]](./Deep_learning#cite_note-218)[[219]](./Deep_learning#cite_note-219)

 

### Recommendation systems

 Main article: [Recommender system](./Recommender_system) 

Recommendation systems have used deep learning to extract meaningful features for a latent factor model for content-based music and journal recommendations.[[220]](./Deep_learning#cite_note-220)[[221]](./Deep_learning#cite_note-221) Multi-view deep learning has been applied for learning user preferences from multiple domains.[[222]](./Deep_learning#cite_note-222) The model uses a hybrid collaborative and content-based approach and enhances recommendations in multiple tasks.

 

### Bioinformatics

 Main article: [Bioinformatics](./Bioinformatics) 

An [autoencoder](./Autoencoder) ANN was used in [bioinformatics](./Bioinformatics), to predict [gene ontology](./Gene_Ontology) annotations and gene-function relationships.[[223]](./Deep_learning#cite_note-223)

 

In medical informatics, deep learning was used to predict sleep quality based on data from wearables[[224]](./Deep_learning#cite_note-224) and predictions of health complications from [electronic health record](./Electronic_health_record) data.[[225]](./Deep_learning#cite_note-225)

 

Deep neural networks have shown unparalleled performance in [predicting protein structure](./Protein_structure_prediction), according to the sequence of the amino acids that make it up. In 2020, [AlphaFold](./AlphaFold), a deep-learning based system, achieved a level of accuracy significantly higher than all previous computational methods.[[226]](./Deep_learning#cite_note-226)[[227]](./Deep_learning#cite_note-227)

 

### Deep Neural Network Estimations

 

Deep neural networks can be used to estimate the entropy of a [stochastic process](./Stochastic_process) through an arrangement called a Neural Joint Entropy Estimator (NJEE).[[228]](./Deep_learning#cite_note-SPB22-228) Such an estimation provides insights on the effects of input [random variables](./Random_variables) on an independent [random variable](./Random_variable). Practically, the DNN is trained as a [classifier](./Classifier_(machine_learning)) that maps an input [vector](./Vector_(mathematics_and_physics)) or [matrix](./Matrix_(mathematics)) X to an output [probability distribution](./Probability_distribution) over the possible classes of random variable Y, given input X. For example, in [image classification](./Image_classification) tasks, the NJEE maps a vector of [pixels](./Pixels)' color values to probabilities over possible image classes. In practice, the probability distribution of Y is obtained by a [Softmax](./Softmax) layer with number of nodes that is equal to the [alphabet](./Alphabet) size of Y. NJEE uses continuously differentiable [activation functions](./Activation_function), such that the conditions for the [universal approximation theorem](./Universal_approximation_theorem) holds. It is shown that this method provides a strongly [consistent estimator](./Consistent_estimator) and outperforms other methods in cases of large alphabet sizes.[[228]](./Deep_learning#cite_note-SPB22-228)

 

### Medical image analysis

 

Deep learning has been shown to produce competitive results in medical applications such as cancer cell classification, lesion detection, organ segmentation and image enhancement.[[229]](./Deep_learning#cite_note-229)[[230]](./Deep_learning#cite_note-230) Modern deep learning tools demonstrate the high accuracy of detecting various diseases and the helpfulness of their use by specialists to improve the diagnosis efficiency.[[231]](./Deep_learning#cite_note-231)[[232]](./Deep_learning#cite_note-232)

 

### Mobile advertising

 

Finding the appropriate mobile audience for [mobile advertising](./Mobile_advertising) is always challenging, since many data points must be considered and analyzed before a target segment can be created and used in ad serving by any ad server.[[233]](./Deep_learning#cite_note-233) Deep learning has been used to interpret large, many-dimensioned advertising datasets. Many data points are collected during the request/serve/click internet advertising cycle. This information can form the basis of machine learning to improve ad selection.

 

### Image restoration

 

Deep learning has been successfully applied to [inverse problems](./Inverse_problems) such as [denoising](./Denoising), [super-resolution](./Super-resolution), [inpainting](./Inpainting), and [film colorization](./Film_colorization).[[234]](./Deep_learning#cite_note-234) These applications include learning methods such as "Shrinkage Fields for Effective Image Restoration"[[235]](./Deep_learning#cite_note-235) which trains on an image dataset, and [Deep Image Prior](./Deep_Image_Prior), which trains on the image that needs restoration.

 

### Financial fraud detection

 

Deep learning is being applied to financial [fraud detection](./Fraud_detection), tax evasion detection,[[236]](./Deep_learning#cite_note-236) and anti-money laundering.[[237]](./Deep_learning#cite_note-237)

 

### Materials science

 

In November 2023, researchers at [Google DeepMind](./Google_DeepMind) and [Lawrence Berkeley National Laboratory](./Lawrence_Berkeley_National_Laboratory) announced that they had developed an AI system known as GNoME. This system has contributed to [materials science](./Materials_science) by discovering over 2 million new materials within a relatively short timeframe. GNoME employs deep learning techniques to efficiently explore potential material structures, achieving a significant increase in the identification of stable inorganic [crystal structures](./Crystal_structure). The system's predictions were validated through autonomous robotic experiments, demonstrating a noteworthy success rate of 71%. The data of newly discovered materials is publicly available through the [Materials Project](./Materials_Project) database, offering researchers the opportunity to identify materials with desired properties for various applications. This development has implications for the future of scientific discovery and the integration of AI in material science research, potentially expediting material innovation and reducing costs in product development. The use of AI and deep learning suggests the possibility of minimizing or eliminating manual lab experiments and allowing scientists to focus more on the design and analysis of unique compounds.[[238]](./Deep_learning#cite_note-238)[[239]](./Deep_learning#cite_note-239)[[240]](./Deep_learning#cite_note-240)

 

### Military

 

The United States Department of Defense applied deep learning to train robots in new tasks through observation.[[241]](./Deep_learning#cite_note-:12-241)

 

### Partial differential equations

 

[Physics-informed neural networks](./Physics-informed_neural_network) have been used to solve [partial differential equations](./Partial_differential_equation) in both forward and inverse problems in a data driven manner.[[242]](./Deep_learning#cite_note-242) One example is the reconstructing fluid flow governed by the [Navier-Stokes equations](./Navier–Stokes_equations). Using physics informed neural networks does not require the often expensive mesh generation that conventional [CFD](./Computational_fluid_dynamics) methods rely on.[[243]](./Deep_learning#cite_note-243)[[244]](./Deep_learning#cite_note-244) It is evident that geometric and physical constraints have a synergistic effect on neural PDE surrogates, thereby enhancing their efficacy in predicting stable and super long rollouts.[[245]](./Deep_learning#cite_note-245)

 

### Deep backward stochastic differential equation method

 

[Deep backward stochastic differential equation method](./Deep_backward_stochastic_differential_equation_method) is a numerical method that combines deep learning with [Backward stochastic differential equation](./Backward_stochastic_differential_equation) (BSDE). This method is particularly useful for solving high-dimensional problems in financial mathematics. By leveraging the powerful function approximation capabilities of [deep neural networks](./Deep_neural_networks), deep BSDE addresses the computational challenges faced by traditional numerical methods in high-dimensional settings. Specifically, traditional methods like finite difference methods or Monte Carlo simulations often struggle with the curse of dimensionality, where computational cost increases exponentially with the number of dimensions. Deep BSDE methods, however, employ deep neural networks to approximate solutions of high-dimensional partial differential equations (PDEs), effectively reducing the computational burden.[[246]](./Deep_learning#cite_note-Han2018-246)

 

In addition, the integration of [Physics-informed neural networks](./Physics-informed_neural_networks) (PINNs) into the deep BSDE framework enhances its capability by embedding the underlying physical laws directly into the neural network architecture. This ensures that the solutions not only fit the data but also adhere to the governing stochastic differential equations. PINNs leverage the power of deep learning while respecting the constraints imposed by the physical models, resulting in more accurate and reliable solutions for financial mathematics problems.

 

### Image reconstruction

 

Image reconstruction is the reconstruction of the underlying images from the image-related measurements. Several works showed the better and superior performance of the deep learning methods compared to analytical methods for various applications, e.g., spectral imaging [[247]](./Deep_learning#cite_note-247) and ultrasound imaging.[[248]](./Deep_learning#cite_note-248)

 

### Weather prediction

 

Traditional weather prediction systems solve a very complex system of partial differential equations. GraphCast is a deep learning based model, trained on a long history of weather data to predict how weather patterns change over time. It is able to  predict weather conditions for up to 10 days globally, at a very detailed level, and in under a minute, with precision similar to state of the art systems.[[249]](./Deep_learning#cite_note-249)[[250]](./Deep_learning#cite_note-250)

 

### Epigenetic clock

 Main article: [Epigenetic clock](./Epigenetic_clock) 

An epigenetic clock is a [biochemical test](./Biomarkers_of_aging) that can be used to measure age. Galkin et al. used deep neural networks to train an epigenetic aging clock of unprecedented accuracy using >6,000 blood samples.[[251]](./Deep_learning#cite_note-251) The clock uses information from 1000 [CpG sites](./CpG_site) and predicts people with certain conditions older than healthy controls: [IBD](./Inflammatory_bowel_disease), [frontotemporal dementia](./Frontotemporal_dementia), [ovarian cancer](./Ovarian_cancer), [obesity](./Obesity). The aging clock was planned to be released for public use in 2021 by an [Insilico Medicine](./Insilico_Medicine) spinoff company Deep Longevity.

 


