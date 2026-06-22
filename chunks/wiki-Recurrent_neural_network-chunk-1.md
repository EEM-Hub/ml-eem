---
source: sources/wiki-Recurrent_neural_network.md
source_url: https://en.wikipedia.org/wiki/Recurrent_neural_network
chunk: 1/7
---

Class of artificial neural network Not to be confused with [Recursive neural network](./Recursive_neural_network) or [Feedback neural network](./Feedback_neural_network). 
| Part of a series on |
| --- |
| Machine learninganddata mining |
| ParadigmsSupervised learningUnsupervised learningSemi-supervised learningSelf-supervised learningReinforcement learningMeta-learningOnline learningBatch learningCurriculum learningRule-based learningNeuro-symbolic AINeuromorphic engineeringQuantum machine learning |
| ProblemsClassificationGenerative modelingRegressionClusteringDimensionality reductionDensity estimationAnomaly detectionData cleaningAutoMLAssociation rulesSemantic analysisStructured predictionFeature engineeringFeature learningLearning to rankGrammar inductionOntology learningMultimodal learning |
| Supervised learning(classification•regression)Apprenticeship learningDecision treesEnsemblesBaggingBoostingRandom forestk-NNLinear regressionNaive BayesArtificial neural networksLogistic regressionPerceptronRelevance vector machine (RVM)Support vector machine (SVM) |
| ClusteringBIRCHCUREHierarchicalk-meansFuzzyExpectation–maximization (EM)DBSCANOPTICSMean shift |
| Dimensionality reductionFactor analysisCCAICALDANMFPCAPGDt-SNESDL |
| Structured predictionGraphical modelsBayes netConditional random fieldHidden Markov |
| Anomaly detectionRANSACk-NNLocal outlier factorIsolation forest |
| Neural networksAutoencoderDeep learningFeedforward neural networkRecurrent neural networkLSTMGRUESNreservoir computingBoltzmann machineRestrictedGANDiffusion modelSOMConvolutional neural networkU-NetLeNetAlexNetDeepDreamNeural fieldNeural radiance fieldPhysics-informed neural networksTransformerVisionMambaSpiking neural networkMemtransistorElectrochemical RAM(ECRAM) |
| Reinforcement learningQ-learningPolicy gradientSARSATemporal difference (TD)Multi-agentSelf-play |
| Learning with humansActive learningCrowdsourcingHuman-in-the-loopMechanistic interpretabilityRLHF |
| Model diagnosticsCoefficient of determinationConfusion matrixLearning curveROC curve |
| Mathematical foundationsKernel machinesBias–variance tradeoffComputational learning theoryEmpirical risk minimizationOccam learningPAC learningStatistical learningVC theoryTopological deep learning |
| Journals and conferencesAAAICVPRECCVECML PKDDEMNLPICCVNeurIPSICMLICLRIJCAIMLJMLR |
| Related articlesGlossary of artificial intelligenceList of datasets for machine-learning researchList of datasets in computer vision and image processingOutline of machine learning |
| vte |

 

In [artificial neural networks](./Artificial_neural_networks), **recurrent neural networks** (**RNNs**) are designed for processing sequential data, such as text, speech, and [time series](./Time_series),[[1]](./Recurrent_neural_network#cite_note-1) where the order of elements is important. Unlike [feedforward neural networks](./Feedforward_neural_network), which process inputs independently, RNNs utilize recurrent connections, where the output of a neuron at one time step is fed back as input to the network at the next time step. This enables RNNs to capture temporal dependencies and patterns within sequences.

 

The fundamental building block of RNN is the *recurrent unit*, which maintains a *hidden state*—a form of memory that is updated at each time step based on the current input and the previous hidden state. This feedback mechanism allows the network to learn from past inputs and incorporate that knowledge into its current processing. RNNs have been successfully applied to tasks such as unsegmented, connected [handwriting recognition](./Handwriting_recognition),[[2]](./Recurrent_neural_network#cite_note-2) [speech recognition](./Speech_recognition),[[3]](./Recurrent_neural_network#cite_note-sak2014-3)[[4]](./Recurrent_neural_network#cite_note-liwu2015-4) [natural language processing](./Natural_language_processing), and [neural machine translation](./Neural_machine_translation).[[5]](./Recurrent_neural_network#cite_note-5)[[6]](./Recurrent_neural_network#cite_note-6)

 

However, traditional RNNs suffer from the [vanishing gradient problem](./Vanishing_gradient_problem), which limits their ability to learn long-range dependencies. This issue was addressed by the development of the [long short-term memory](./Long_short-term_memory) (LSTM) architecture in 1997, making it the standard RNN variant for handling long-term dependencies. Later, [gated recurrent units](./Gated_recurrent_unit) (GRUs) were introduced as a more computationally efficient alternative.

 

In recent years, [transformers](./Transformer_(deep_learning_architecture)), which rely on self-attention mechanisms instead of recurrence, have become the dominant architecture for many sequence-processing tasks, particularly in natural language processing, due to their superior handling of long-range dependencies and greater parallelizability. Nevertheless, RNNs remain relevant for applications where computational efficiency, real-time processing, or the inherent sequential nature of data is crucial.

 

## History

 

### Before modern

One origin of RNN was neuroscience. The word "recurrent" is used to describe loop-like structures in [anatomy](./Anatomy). In 1901, [Cajal](./Santiago_Ramón_y_Cajal) observed "recurrent semicircles" in the [cerebellar cortex](./Cerebellum) formed by [parallel fiber](./Parallel_fiber), [Purkinje cells](./Purkinje_cell), and [granule cells](./Granule_cell).[[7]](./Recurrent_neural_network#cite_note-7)[[8]](./Recurrent_neural_network#cite_note-8) In 1933, [Lorente de Nó](./Rafael_Lorente_de_Nó) discovered "recurrent, reciprocal connections" by [Golgi's method](./Golgi's_method), and proposed that excitatory loops explain certain aspects of the [vestibulo-ocular reflex](./Vestibulo-ocular_reflex).[[9]](./Recurrent_neural_network#cite_note-9)[[10]](./Recurrent_neural_network#cite_note-10) During 1940s, multiple people proposed the existence of feedback in the brain, which was a contrast to the previous understanding of the neural system as a purely feedforward structure. [Hebb](./Donald_O._Hebb) considered "reverberating circuit" as an explanation for short-term memory.[[11]](./Recurrent_neural_network#cite_note-11) The McCulloch and Pitts paper (1943), which proposed the [McCulloch-Pitts neuron](./McCulloch-Pitts_neuron) model, considered networks that contains cycles. The current activity of such networks can be affected by activity indefinitely far in the past.[[12]](./Recurrent_neural_network#cite_note-12) They were both interested in closed loops as possible explanations for e.g. [epilepsy](./Epilepsy) and [causalgia](./Complex_regional_pain_syndrome).[[13]](./Recurrent_neural_network#cite_note-13)[[14]](./Recurrent_neural_network#cite_note-14) [Recurrent inhibition](./Renshaw_cell) was proposed in 1946 as a negative feedback mechanism in motor control. Neural feedback loops were a common topic of discussion at the [Macy conferences](./Macy_conferences).[[15]](./Recurrent_neural_network#cite_note-15) See [[16]](./Recurrent_neural_network#cite_note-:0-16) for an extensive review of recurrent neural network models in neuroscience.

[![](//upload.wikimedia.org/wikipedia/commons/thumb/a/a5/Typical_connections_in_a_close-loop_cross-coupled_perceptron.png/250px-Typical_connections_in_a_close-loop_cross-coupled_perceptron.png)](./File:Typical_connections_in_a_close-loop_cross-coupled_perceptron.png)A close-loop cross-coupled perceptron network[[17]](./Recurrent_neural_network#cite_note-:1-17): 403, Fig. 47  

[Frank Rosenblatt](./Frank_Rosenblatt) in 1960 published "close-loop cross-coupled perceptrons", which are 3-layered [perceptron](./Perceptron) networks whose middle layer contains recurrent connections that change by a [Hebbian learning](./Hebbian_theory) rule.[[18]](./Recurrent_neural_network#cite_note-18): 73–75  Later, in *Principles of Neurodynamics* (1961), he described "closed-loop cross-coupled" and "back-coupled" perceptron networks, and made theoretical and experimental studies for Hebbian learning in these networks,[[17]](./Recurrent_neural_network#cite_note-:1-17): Chapter 19, 21  and noted that a fully cross-coupled perceptron network is equivalent to an infinitely deep feedforward network.[[17]](./Recurrent_neural_network#cite_note-:1-17): Section 19.11 

 

Similar networks were published by Kaoru Nakano in 1971,[[19]](./Recurrent_neural_network#cite_note-Nakano1971-19)[[20]](./Recurrent_neural_network#cite_note-Nakano1972-20) [Shun'ichi Amari](./Shun'ichi_Amari) in 1972,[[21]](./Recurrent_neural_network#cite_note-Amari1972-21) and [William A. Little](./William_A._Little_(physicist)?action=edit&redlink=1) [[de](https://de.wikipedia.org/wiki/William%20A.%20Little)] in 1974,[[22]](./Recurrent_neural_network#cite_note-little74-22) who was acknowledged by Hopfield in his 1982 paper.

 

Another origin of RNN was [statistical mechanics](./Statistical_mechanics). The [Ising model](./Ising_model) was developed by [Wilhelm Lenz](./Wilhelm_Lenz)[[23]](./Recurrent_neural_network#cite_note-lenz1920-23) and [Ernst Ising](./Ernst_Ising)[[24]](./Recurrent_neural_network#cite_note-ising1925-24) in the 1920s[[25]](./Recurrent_neural_network#cite_note-25) as a simple statistical mechanical model of magnets at equilibrium. [Glauber](./Roy_J._Glauber) in 1963 studied the Ising model evolving in time, as a process towards equilibrium ([Glauber dynamics](./Glauber_dynamics)), adding in the component of time.[[26]](./Recurrent_neural_network#cite_note-:22-26)

 

The [Sherrington–Kirkpatrick model](./Spin_glass) of spin glass, published in 1975,[[27]](./Recurrent_neural_network#cite_note-27) is the Hopfield network with random initialization. Sherrington and Kirkpatrick found that it is highly likely for the energy function of the SK model to have many local minima. In the 1982 paper, Hopfield applied this recently developed theory to study the Hopfield network with binary activation functions.[[28]](./Recurrent_neural_network#cite_note-Hopfield19822-28) In a 1984 paper he extended this to continuous activation functions.[[29]](./Recurrent_neural_network#cite_note-:02-29) It became a standard model for the study of neural networks through statistical mechanics.[[30]](./Recurrent_neural_network#cite_note-30)[[31]](./Recurrent_neural_network#cite_note-31)

 

### Modern

 

Modern RNN networks are mainly based on two architectures: LSTM and BRNN.[[32]](./Recurrent_neural_network#cite_note-32)

 

At the resurgence of neural networks in the 1980s, recurrent networks were studied again. They were sometimes called "iterated nets".[[33]](./Recurrent_neural_network#cite_note-33) Two early influential works were the [Jordan network](./Recurrent_neural_network#Jordan_network) (1986) and the [Elman network](./Recurrent_neural_network#Elman_network) (1990), which applied RNN to study [cognitive psychology](./Cognitive_psychology). In 1993, a neural history compressor system solved a "Very Deep Learning" task that required more than 1000 subsequent [layers](./Layer_(deep_learning)) in an RNN unfolded in time.[[34]](./Recurrent_neural_network#cite_note-schmidhuber1993-34)

 

[Long short-term memory](./Long_short-term_memory) (LSTM) networks were invented by [Hochreiter](./Sepp_Hochreiter) and [Schmidhuber](./Jürgen_Schmidhuber) in 1995 and set accuracy records in multiple applications domains.[[35]](./Recurrent_neural_network#cite_note-35)[[36]](./Recurrent_neural_network#cite_note-lstm-36) It became the default choice for RNN architecture.

 

[Bidirectional recurrent neural networks](./Bidirectional_recurrent_neural_networks) (BRNN) use two RNNs that process the same input in opposite directions.[[37]](./Recurrent_neural_network#cite_note-Schuster-37) These two are often combined, giving the bidirectional LSTM architecture.

 

Around 2006, bidirectional LSTM started to revolutionize [speech recognition](./Speech_recognition), outperforming traditional models in certain speech applications.[[38]](./Recurrent_neural_network#cite_note-38)[[39]](./Recurrent_neural_network#cite_note-fernandez2007keyword-39) They also improved large-vocabulary speech recognition[[3]](./Recurrent_neural_network#cite_note-sak2014-3)[[4]](./Recurrent_neural_network#cite_note-liwu2015-4) and [text-to-speech](./Text-to-speech) synthesis[[40]](./Recurrent_neural_network#cite_note-fan2015-40) and was used in [Google voice search](./Google_Voice_Search), and dictation on [Android devices](./Android_(operating_system)).[[41]](./Recurrent_neural_network#cite_note-sak2015-41) They broke records for improved [machine translation](./Machine_translation),[[42]](./Recurrent_neural_network#cite_note-sutskever2014-42) [language modeling](./Language_Modeling)[[43]](./Recurrent_neural_network#cite_note-vinyals2016-43) and Multilingual Language Processing.[[44]](./Recurrent_neural_network#cite_note-gillick2015-44) Also, LSTM combined with [convolutional neural networks](./Convolutional_neural_network) (CNNs) improved [automatic image captioning](./Automatic_image_captioning).[[45]](./Recurrent_neural_network#cite_note-vinyals2015-45)

 

The idea of encoder-decoder sequence transduction had been developed in the early 2010s. The papers most commonly cited as the originators that produced seq2seq are two papers from 2014.[[46]](./Recurrent_neural_network#cite_note-:2-46)[[47]](./Recurrent_neural_network#cite_note-sequence-47) A [seq2seq](./Seq2seq) architecture employs two RNN, typically LSTM, an "encoder" and a "decoder", for sequence transduction, such as machine translation. They became state of the art in machine translation, and were instrumental in the development of [attention mechanisms](./Attention_(machine_learning)) and [transformers](./Transformer_(deep_learning_architecture)).

 


