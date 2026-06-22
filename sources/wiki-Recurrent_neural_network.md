---
source: https://en.wikipedia.org/wiki/Recurrent_neural_network
fetched: 2026-06-21
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

 

## Configurations

 Main article: [Layer (deep learning)](./Layer_(deep_learning)) 

An RNN-based model can be factored into two parts: configuration and architecture. Multiple RNNs can be combined in a data flow, and the data flow itself is the configuration. Each RNN itself may have any architecture, including LSTM, GRU, etc.

 

### Standard

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/b/b5/Recurrent_neural_network_unfold.svg/250px-Recurrent_neural_network_unfold.svg.png)](./File:Recurrent_neural_network_unfold.svg)Compressed (left) and unfolded (right) basic recurrent neural network 

RNNs come in many variants. Abstractly speaking, an RNN is a function      f  θ θ      {\displaystyle f_{\theta }}  ![{\displaystyle f_{\theta }}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9874ae06066a2250709085e0fb521eebff2c2fb7) of type     (  x  t   ,  h  t   ) ↦ ↦  (  y  t   ,  h  t + 1   )   {\displaystyle (x_{t},h_{t})\mapsto (y_{t},h_{t+1})}  ![{\displaystyle (x_{t},h_{t})\mapsto (y_{t},h_{t+1})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/daede0f2ff9c38ad773254c9b68cdf2846a65de6), where

 
-      x  t     {\displaystyle x_{t}}  ![{\displaystyle x_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f279a30bc8eabc788f3fe81c9cfb674e72e858db): input vector;
-      h  t     {\displaystyle h_{t}}  ![{\displaystyle h_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e8dbf3d8bfe322f68ff6400385578f8d78e1ba7c): hidden vector;
-      y  t     {\displaystyle y_{t}}  ![{\displaystyle y_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0fe9554452b93508c9d2479414a45981ecc75a2d): output vector;
-     θ θ    {\displaystyle \theta }  ![{\displaystyle \theta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/6e5ab2664b422d53eb0c7df3b87e1360d75ad9af): neural network parameters.

 

In words, it is a neural network that maps an input      x  t     {\displaystyle x_{t}}  ![{\displaystyle x_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f279a30bc8eabc788f3fe81c9cfb674e72e858db) into an output      y  t     {\displaystyle y_{t}}  ![{\displaystyle y_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0fe9554452b93508c9d2479414a45981ecc75a2d), with the hidden vector      h  t     {\displaystyle h_{t}}  ![{\displaystyle h_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e8dbf3d8bfe322f68ff6400385578f8d78e1ba7c) playing the role of "memory", a partial record of all previous input-output pairs. At each step, it transforms input to an output, and modifies its "memory" to help it to better perform future processing.

 

The illustration to the right may be misleading to many because practical neural network topologies are frequently organized in "layers" and the drawing gives that appearance. However, what appears to be [layers](./Layer_(deep_learning)) are, in fact, different steps in time, "unfolded" to produce the appearance of [layers](./Layer_(deep_learning)).

 

### Stacked RNN

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/e/e3/Stacked_RNN.png/250px-Stacked_RNN.png)](./File:Stacked_RNN.png)Stacked RNN

A **stacked RNN**, or **deep RNN**, is composed of multiple RNNs stacked one above the other. Abstractly, it is structured as follows

 
1. Layer 1 has hidden vector      h  1 , t     {\displaystyle h_{1,t}}  ![{\displaystyle h_{1,t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/41d508e0dc0b303c58fa98ac785044f0d302024c), parameters      θ θ   1     {\displaystyle \theta _{1}}  ![{\displaystyle \theta _{1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7f84b9443d095623e02fd287cd095123d70b0278), and maps      f   θ θ   1     : (  x  0 , t   ,  h  1 , t   ) ↦ ↦  (  x  1 , t   ,  h  1 , t + 1   )   {\displaystyle f_{\theta _{1}}:(x_{0,t},h_{1,t})\mapsto (x_{1,t},h_{1,t+1})}  ![{\displaystyle f_{\theta _{1}}:(x_{0,t},h_{1,t})\mapsto (x_{1,t},h_{1,t+1})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3d6c58b510835cafedab19747e1a57a95bfbbc28).
2. Layer 2 has hidden vector      h  2 , t     {\displaystyle h_{2,t}}  ![{\displaystyle h_{2,t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/30a4a50b190be9e0f1df9770bb3d42879f564aff), parameters      θ θ   2     {\displaystyle \theta _{2}}  ![{\displaystyle \theta _{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0ed6ea624b20b153403979ffaf5434fc36de2990), and maps      f   θ θ   2     : (  x  1 , t   ,  h  2 , t   ) ↦ ↦  (  x  2 , t   ,  h  2 , t + 1   )   {\displaystyle f_{\theta _{2}}:(x_{1,t},h_{2,t})\mapsto (x_{2,t},h_{2,t+1})}  ![{\displaystyle f_{\theta _{2}}:(x_{1,t},h_{2,t})\mapsto (x_{2,t},h_{2,t+1})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c936d144b72db51f32a1fc4af94e60849bfe2ffe).
3. ...
4. Layer     n   {\displaystyle n}  ![{\displaystyle n}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a601995d55609f2d9f5e233e36fbe9ea26011b3b) has hidden vector      h  n , t     {\displaystyle h_{n,t}}  ![{\displaystyle h_{n,t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/bc5bbbf6e890a622b1a1a9b492ab4f0b1c01d843), parameters      θ θ   n     {\displaystyle \theta _{n}}  ![{\displaystyle \theta _{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/79cc00920259451fc1a684ba7350b6f93ce4f08a), and maps      f   θ θ   n     : (  x  n − −  1 , t   ,  h  n , t   ) ↦ ↦  (  x  n , t   ,  h  n , t + 1   )   {\displaystyle f_{\theta _{n}}:(x_{n-1,t},h_{n,t})\mapsto (x_{n,t},h_{n,t+1})}  ![{\displaystyle f_{\theta _{n}}:(x_{n-1,t},h_{n,t})\mapsto (x_{n,t},h_{n,t+1})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ea881abbb0a57bb90425e6fe8c2cee342f8bef1c).

 

Each layer operates as a stand-alone RNN, and each layer's output sequence is used as the input sequence to the layer above. There is no conceptual limit to the depth of stacked RNN.

 

### Bidirectional

 Main article: [Bidirectional recurrent neural networks](./Bidirectional_recurrent_neural_networks) [![](//upload.wikimedia.org/wikipedia/commons/thumb/f/f0/Bidirectional_RNN.png/250px-Bidirectional_RNN.png)](./File:Bidirectional_RNN.png)Bidirectional RNN

A **bidirectional RNN** (biRNN) is composed of two RNNs, one processing the input sequence in one direction, and another in the opposite direction. Abstractly, it is structured as follows:

 
- The forward RNN processes in one direction:      f  θ θ    (  x  0   ,  h  0   ) = (  y  0   ,  h  1   ) ,  f  θ θ    (  x  1   ,  h  1   ) = (  y  1   ,  h  2   ) , … …    {\displaystyle f_{\theta }(x_{0},h_{0})=(y_{0},h_{1}),f_{\theta }(x_{1},h_{1})=(y_{1},h_{2}),\dots }  ![{\displaystyle f_{\theta }(x_{0},h_{0})=(y_{0},h_{1}),f_{\theta }(x_{1},h_{1})=(y_{1},h_{2}),\dots }](https://wikimedia.org/api/rest_v1/media/math/render/svg/f6129c199ab8b86d643b7c35e4655a42e36c0ea6)
- The backward RNN processes in the opposite direction:     f   θ θ  ′   ′  (  x  N   ,  h  N  ′  ) = (  y  N  ′  ,  h  N − −  1  ′  ) ,  f   θ θ  ′   ′  (  x  N − −  1   ,  h  N − −  1  ′  ) = (  y  N − −  1  ′  ,  h  N − −  2  ′  ) , … …    {\displaystyle f'_{\theta '}(x_{N},h_{N}')=(y'_{N},h_{N-1}'),f'_{\theta '}(x_{N-1},h_{N-1}')=(y'_{N-1},h_{N-2}'),\dots }  ![{\displaystyle f'_{\theta '}(x_{N},h_{N}')=(y'_{N},h_{N-1}'),f'_{\theta '}(x_{N-1},h_{N-1}')=(y'_{N-1},h_{N-2}'),\dots }](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f5f33f98c860de2b99b57d62dd99c59ebc80fc0)

 

The two output sequences are then concatenated to give the total output:     ( (  y  0   ,  y  0  ′  ) , (  y  1   ,  y  1  ′  ) , … …  , (  y  N   ,  y  N  ′  ) )   {\displaystyle ((y_{0},y_{0}'),(y_{1},y_{1}'),\dots ,(y_{N},y_{N}'))}  ![{\displaystyle ((y_{0},y_{0}'),(y_{1},y_{1}'),\dots ,(y_{N},y_{N}'))}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6b4f2aede172075e4a2d3ef5c525448fb5e241ae).

 

Bidirectional RNN allows the model to process a token both in the context of what came before it and what came after it. By stacking multiple bidirectional RNNs together, the model can process a token increasingly contextually. The [ELMo](./ELMo) model (2018)[[48]](./Recurrent_neural_network#cite_note-48) is a stacked bidirectional [LSTM](./Long_short-term_memory) which takes character-level as inputs and produces word-level embeddings.

 

### Encoder-decoder

 Main article: [seq2seq](./Seq2seq) [![](//upload.wikimedia.org/wikipedia/commons/thumb/7/7c/Decoder_RNN.png/250px-Decoder_RNN.png)](./File:Decoder_RNN.png)A decoder without an encoder [![](//upload.wikimedia.org/wikipedia/commons/thumb/7/72/Seq2seq_RNN_encoder-decoder_with_attention_mechanism%2C_training_and_inferring.png/250px-Seq2seq_RNN_encoder-decoder_with_attention_mechanism%2C_training_and_inferring.png)](./File:Seq2seq_RNN_encoder-decoder_with_attention_mechanism,_training_and_inferring.png)Encoder-decoder RNN without attention mechanism [![](//upload.wikimedia.org/wikipedia/commons/thumb/c/c7/Seq2seq_RNN_encoder-decoder_with_attention_mechanism%2C_training.png/250px-Seq2seq_RNN_encoder-decoder_with_attention_mechanism%2C_training.png)](./File:Seq2seq_RNN_encoder-decoder_with_attention_mechanism,_training.png)Encoder-decoder RNN with attention mechanism 

Two RNNs can be run front-to-back in an **encoder-decoder** configuration. The encoder RNN processes an input sequence into a sequence of hidden vectors, and the decoder RNN processes the sequence of hidden vectors to an output sequence, with an optional [attention mechanism](./Attention_(machine_learning)). This was used to construct state of the art [neural machine translators](./Neural_machine_translation) during the 2014–2017 period. This was an instrumental step towards the development of [transformers](./Transformer_(deep_learning_architecture)).[[49]](./Recurrent_neural_network#cite_note-49)

 

### PixelRNN

 

An RNN may process data with more than one dimension. PixelRNN processes two-dimensional data, with many possible directions.[[50]](./Recurrent_neural_network#cite_note-50) For example, the row-by-row direction processes an     n × ×  n   {\displaystyle n\times n}  ![{\displaystyle n\times n}](https://wikimedia.org/api/rest_v1/media/math/render/svg/59d2b4cb72e304526cf5b5887147729ea259da78) grid of vectors      x  i , j     {\displaystyle x_{i,j}}  ![{\displaystyle x_{i,j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fd698068c9322e82d11cb2bc02cb2f51739a2cc0) in the following order:      x  1 , 1   ,  x  1 , 2   , … …  ,  x  1 , n   ,  x  2 , 1   ,  x  2 , 2   , … …  ,  x  2 , n   , … …  ,  x  n , n     {\displaystyle x_{1,1},x_{1,2},\dots ,x_{1,n},x_{2,1},x_{2,2},\dots ,x_{2,n},\dots ,x_{n,n}}  ![{\displaystyle x_{1,1},x_{1,2},\dots ,x_{1,n},x_{2,1},x_{2,2},\dots ,x_{2,n},\dots ,x_{n,n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6b9de0f040f133e51ec188e98ed9541a98705908)The **diagonal BiLSTM** uses two LSTMs to process the same grid. One processes it from the top-left corner to the bottom-right, such that it processes      x  i , j     {\displaystyle x_{i,j}}  ![{\displaystyle x_{i,j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fd698068c9322e82d11cb2bc02cb2f51739a2cc0) depending on its hidden state and cell state on the top and the left side:      h  i − −  1 , j   ,  c  i − −  1 , j     {\displaystyle h_{i-1,j},c_{i-1,j}}  ![{\displaystyle h_{i-1,j},c_{i-1,j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ec3abb324832ed758f9376976cae69702169a7df) and      h  i , j − −  1   ,  c  i , j − −  1     {\displaystyle h_{i,j-1},c_{i,j-1}}  ![{\displaystyle h_{i,j-1},c_{i,j-1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/82483890bf0f5558df1cee92b40c57d6c0e29228). The other processes it from the top-right corner to the bottom-left.

 

## Architectures

 

### Fully recurrent

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/4/44/Hopfield-net-vector.svg/250px-Hopfield-net-vector.svg.png)](./File:Hopfield-net-vector.svg)A fully connected RNN with 4 neurons 

**Fully recurrent neural networks** (FRNN) connect the outputs of all neurons to the inputs of all neurons. In other words, it is a [fully connected network](./Fully_connected_network). This is the most general neural network topology, because all other topologies can be represented by setting some connection weights to zero to simulate the lack of connections between those neurons.

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/0/02/RNN_architecture.png/250px-RNN_architecture.png)](./File:RNN_architecture.png)A simple Elman network where      σ σ   h   = tanh ,  σ σ   y   =  Identity    {\displaystyle \sigma _{h}=\tanh ,\sigma _{y}={\text{Identity}}}  ![{\displaystyle \sigma _{h}=\tanh ,\sigma _{y}={\text{Identity}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/02121b05b248e1d48a45e75052bc4e5144c8bde7) 

### Hopfield

 Main article: [Hopfield network](./Hopfield_network) 

The **Hopfield network** is an RNN in which all connections across layers are equally sized. It requires [stationary](./Stationary_process) inputs and is thus not a general RNN, as it does not process sequences of patterns. However, it guarantees that it will converge. If the connections are trained using [Hebbian learning](./Hebbian_learning), then the Hopfield network can perform as [robust](./Robustness_(computer_science)) [content-addressable memory](./Content-addressable_memory), resistant to connection alteration.

 

### Elman networks and Jordan networks

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/8/8f/Elman_srnn.png/250px-Elman_srnn.png)](./File:Elman_srnn.png)The Elman network 

An **[Elman](./Jeff_Elman) network** is a three-layer network (arranged horizontally as *x*, *y*, and *z* in the illustration) with the addition of a set of context units (*u* in the illustration). The middle (hidden) layer is connected to these context units fixed with a weight of one.[[51]](./Recurrent_neural_network#cite_note-bmm615-51) At each time step, the input is fed forward and a [learning rule](./Learning_rule) is applied. The fixed back-connections save a copy of the previous values of the hidden units in the context units (since they propagate over the connections before the learning rule is applied). Thus the network can maintain a sort of state, allowing it to perform tasks such as sequence-prediction that are beyond the power of a standard [multilayer perceptron](./Multilayer_perceptron).

 

**[Jordan](./Michael_I._Jordan) networks** are similar to Elman networks. The context units are fed from the output layer instead of the hidden layer. The context units in a Jordan network are also called the state layer. They have a recurrent connection to themselves.[[51]](./Recurrent_neural_network#cite_note-bmm615-51)

 

Elman and Jordan networks are also known as "Simple recurrent networks" (SRN).

 Elman network[[52]](./Recurrent_neural_network#cite_note-52)          h  t      =  σ σ   h   (  W  h    x  t   +  U  h    h  t − −  1   +  b  h   )      y  t      =  σ σ   y   (  W  y    h  t   +  b  y   )       {\displaystyle {\begin{aligned}h_{t}&=\sigma _{h}(W_{h}x_{t}+U_{h}h_{t-1}+b_{h})\\y_{t}&=\sigma _{y}(W_{y}h_{t}+b_{y})\end{aligned}}}  ![{\displaystyle {\begin{aligned}h_{t}&=\sigma _{h}(W_{h}x_{t}+U_{h}h_{t-1}+b_{h})\\y_{t}&=\sigma _{y}(W_{y}h_{t}+b_{y})\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/983c33bfddb6c6d8b1bfdf9accf50bb5634e2f5a) Jordan network[[53]](./Recurrent_neural_network#cite_note-53)          h  t      =  σ σ   h   (  W  h    x  t   +  U  h    s  t   +  b  h   )      y  t      =  σ σ   y   (  W  y    h  t   +  b  y   )      s  t      =  σ σ   s   (  W  s , s    s  t − −  1   +  W  s , y    y  t − −  1   +  b  s   )       {\displaystyle {\begin{aligned}h_{t}&=\sigma _{h}(W_{h}x_{t}+U_{h}s_{t}+b_{h})\\y_{t}&=\sigma _{y}(W_{y}h_{t}+b_{y})\\s_{t}&=\sigma _{s}(W_{s,s}s_{t-1}+W_{s,y}y_{t-1}+b_{s})\end{aligned}}}  ![{\displaystyle {\begin{aligned}h_{t}&=\sigma _{h}(W_{h}x_{t}+U_{h}s_{t}+b_{h})\\y_{t}&=\sigma _{y}(W_{y}h_{t}+b_{y})\\s_{t}&=\sigma _{s}(W_{s,s}s_{t-1}+W_{s,y}y_{t-1}+b_{s})\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/da448ff637dcc68dbd497e10f7623c76c265b983) 

Variables and functions

 
-      x  t     {\displaystyle x_{t}}  ![{\displaystyle x_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f279a30bc8eabc788f3fe81c9cfb674e72e858db): input vector
-      h  t     {\displaystyle h_{t}}  ![{\displaystyle h_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e8dbf3d8bfe322f68ff6400385578f8d78e1ba7c): hidden layer vector
-      s  t     {\displaystyle s_{t}}  ![{\displaystyle s_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/92a402d151a0173378ee252a634c77898ebe4b06): "state" vector,
-      y  t     {\displaystyle y_{t}}  ![{\displaystyle y_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0fe9554452b93508c9d2479414a45981ecc75a2d): output vector
-     W   {\displaystyle W}  ![{\displaystyle W}](https://wikimedia.org/api/rest_v1/media/math/render/svg/54a9c4c547f4d6111f81946cad242b18298d70b7),     U   {\displaystyle U}  ![{\displaystyle U}](https://wikimedia.org/api/rest_v1/media/math/render/svg/458a728f53b9a0274f059cd695e067c430956025) and     b   {\displaystyle b}  ![{\displaystyle b}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f11423fbb2e967f986e36804a8ae4271734917c3): parameter matrices and vector
-     σ σ    {\displaystyle \sigma }  ![{\displaystyle \sigma }](https://wikimedia.org/api/rest_v1/media/math/render/svg/59f59b7c3e6fdb1d0365a494b81fb9a696138c36): [Activation functions](./Activation_function)

 

### Long short-term memory

 Main article: [Long short-term memory](./Long_short-term_memory) [![](//upload.wikimedia.org/wikipedia/commons/thumb/6/63/Long_Short-Term_Memory.svg/250px-Long_Short-Term_Memory.svg.png)](./File:Long_Short-Term_Memory.svg)Long short-term memory unit 

**Long short-term memory** (LSTM) is the most widely used RNN architecture. It was designed to solve the [vanishing gradient problem](./Vanishing_gradient_problem). LSTM is normally augmented by recurrent gates called "forget gates".[[54]](./Recurrent_neural_network#cite_note-gers2002-54) LSTM prevents backpropagated errors from vanishing or exploding.[[55]](./Recurrent_neural_network#cite_note-hochreiter1991-55) Instead, errors can flow backward through unlimited numbers of virtual layers unfolded in space. That is, LSTM can learn tasks that require memories of events that happened thousands or even millions of discrete time steps earlier. Problem-specific LSTM-like topologies can be evolved.[[56]](./Recurrent_neural_network#cite_note-bayer2009-56) LSTM works even given long delays between significant events and can handle signals that mix low and high-frequency components.

 

Many applications use stacks of LSTMs,[[57]](./Recurrent_neural_network#cite_note-fernandez2007-57) for which it is called "deep LSTM". LSTM can learn to recognize [context-sensitive languages](./Context-sensitive_languages) unlike previous models based on [hidden Markov models](./Hidden_Markov_model) (HMM) and similar concepts.[[58]](./Recurrent_neural_network#cite_note-peepholeLSTM-58)

 

### Gated recurrent unit

 Main article: [Gated recurrent unit](./Gated_recurrent_unit) [![](//upload.wikimedia.org/wikipedia/commons/thumb/5/5f/Gated_Recurrent_Unit.svg/250px-Gated_Recurrent_Unit.svg.png)](./File:Gated_Recurrent_Unit.svg)Gated recurrent unit 

**Gated recurrent unit** (GRU), introduced in 2014, was designed as a simplification of LSTM. They are used in the full form and several further simplified variants.[[59]](./Recurrent_neural_network#cite_note-59)[[60]](./Recurrent_neural_network#cite_note-60) They have fewer parameters than LSTM, as they lack an output gate.[[61]](./Recurrent_neural_network#cite_note-MyUser_Wildml.com_May_18_2016c-61)

 

Their performance on polyphonic music modeling and speech signal modeling was found to be similar to that of long short-term memory.[[62]](./Recurrent_neural_network#cite_note-MyUser_Arxiv.org_May_18_2016c2-62) There does not appear to be particular performance difference between LSTM and GRU.[[62]](./Recurrent_neural_network#cite_note-MyUser_Arxiv.org_May_18_2016c2-62)[[63]](./Recurrent_neural_network#cite_note-gruber_jockisch-63)

 

#### Bidirectional associative memory

 Main article: [Bidirectional associative memory](./Bidirectional_associative_memory) 

Introduced by [Bart Kosko](./Bart_Kosko),[[64]](./Recurrent_neural_network#cite_note-64) a bidirectional associative memory (BAM) network is a variant of a Hopfield network that stores associative data as a vector. The bidirectionality comes from passing information through a matrix and its [transpose](./Transpose). Typically, [bipolar encoding](./Bipolar_encoding) is preferred to binary encoding of the associative pairs. Recently, stochastic BAM models using [Markov](./Markov_chain) stepping are optimized for increased network stability and relevance to real-world applications.[[65]](./Recurrent_neural_network#cite_note-65)

 

A BAM network has two layers, either of which can be driven as an input to recall an association and produce an output on the other layer.[[66]](./Recurrent_neural_network#cite_note-66)

 

### Echo state

 Main article: [Echo state network](./Echo_state_network) 

[**Echo state networks**](./Echo_state_network) (ESN) have a sparsely connected random hidden layer. The weights of output neurons are the only part of the network that can change (be trained). ESNs are good at reproducing certain [time series](./Time_series).[[67]](./Recurrent_neural_network#cite_note-67) A variant for [spiking neurons](./Spiking_neural_network) is known as a [liquid state machine](./Liquid_state_machine).[[68]](./Recurrent_neural_network#cite_note-68)

 

### Recursive

 Main article: [Recursive neural network](./Recursive_neural_network) 

A **[recursive neural network](./Recursive_neural_network)**[[69]](./Recurrent_neural_network#cite_note-69) is created by applying the same set of weights [recursively](./Recursion) over a differentiable graph-like structure by traversing the structure in [topological order](./Topological_sort). Such networks are typically also trained by the reverse mode of [automatic differentiation](./Automatic_differentiation).[[70]](./Recurrent_neural_network#cite_note-lin1970-70)[[71]](./Recurrent_neural_network#cite_note-grie2008-71) They can process [distributed representations](./Distributed_representation) of structure, such as [logical terms](./Mathematical_logic). A special case of recursive neural networks is the RNN whose structure corresponds to a linear chain. Recursive neural networks have been applied to [natural language processing](./Natural_language_processing).[[72]](./Recurrent_neural_network#cite_note-72) The *recursive neural tensor network* uses a [tensor](./Tensor)-based composition function for all nodes in the tree.[[73]](./Recurrent_neural_network#cite_note-73)

 

### Neural Turing machines

 Main articles: [Neural Turing machine](./Neural_Turing_machine) and [Differentiable neural computer](./Differentiable_neural_computer) 

**Neural Turing machines** (NTMs) are a method of extending recurrent neural networks by coupling them to external [memory](./Memory) resources with which they interact. The combined system is analogous to a [Turing machine](./Turing_machine) or [Von Neumann architecture](./Von_Neumann_architecture) but is [differentiable](./Differentiable_neural_computer) end-to-end, allowing it to be efficiently trained with [gradient descent](./Gradient_descent).[[74]](./Recurrent_neural_network#cite_note-74)

 

**Differentiable neural computers** (DNCs) are an extension of neural Turing machines, allowing for the usage of fuzzy amounts of each memory address and a record of chronology.[[75]](./Recurrent_neural_network#cite_note-DNCnature2016-75)

 

**Neural network pushdown automata** (NNPDA) are similar to NTMs, but tapes are replaced by analog stacks that are differentiable and trained. In this way, they are similar in complexity to recognizers of [context free grammars](./Context_free_grammar) (CFGs).[[76]](./Recurrent_neural_network#cite_note-76)

 

Recurrent neural networks are [Turing complete](./Turing_complete) and can run arbitrary programs to process arbitrary sequences of inputs.[[77]](./Recurrent_neural_network#cite_note-77)

 

## Training

 

### Teacher forcing

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/7/72/Seq2seq_RNN_encoder-decoder_with_attention_mechanism%2C_training_and_inferring.png/250px-Seq2seq_RNN_encoder-decoder_with_attention_mechanism%2C_training_and_inferring.png)](./File:Seq2seq_RNN_encoder-decoder_with_attention_mechanism,_training_and_inferring.png)Encoder-decoder RNN without attention mechanism. Teacher forcing is shown in red.

An RNN can be trained into a conditionally [generative model](./Generative_model) of sequences, aka **autoregression**.

 

Concretely, let us consider the problem of machine translation, that is, given a sequence     (  x  1   ,  x  2   , … …  ,  x  n   )   {\displaystyle (x_{1},x_{2},\dots ,x_{n})}  ![{\displaystyle (x_{1},x_{2},\dots ,x_{n})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7c0e6a4f6008f01547bb5cc1e8b01207272939e9) of English words, the model is to produce a sequence     (  y  1   , … …  ,  y  m   )   {\displaystyle (y_{1},\dots ,y_{m})}  ![{\displaystyle (y_{1},\dots ,y_{m})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1f788b82def8d7a3933ae95cc81463bde894ae57) of French words. It is to be solved by a [seq2seq](./Seq2seq) model.

 

Now, during training, the encoder half of the model would first ingest     (  x  1   ,  x  2   , … …  ,  x  n   )   {\displaystyle (x_{1},x_{2},\dots ,x_{n})}  ![{\displaystyle (x_{1},x_{2},\dots ,x_{n})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7c0e6a4f6008f01547bb5cc1e8b01207272939e9), then the decoder half would start generating a sequence     (     y ^ ^      1   ,     y ^ ^      2   , … …  ,     y ^ ^      l   )   {\displaystyle ({\hat {y}}_{1},{\hat {y}}_{2},\dots ,{\hat {y}}_{l})}  ![{\displaystyle ({\hat {y}}_{1},{\hat {y}}_{2},\dots ,{\hat {y}}_{l})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1c690f99611b8115d603410038d1c900eb099b69). The problem is that if the model makes a mistake early on, say at         y ^ ^      2     {\displaystyle {\hat {y}}_{2}}  ![{\displaystyle {\hat {y}}_{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2d678e9549266e3dfc09066e1145e3f7a13fd7d2), then subsequent tokens are likely to also be mistakes. This makes it inefficient for the model to obtain a learning signal, since the model would mostly learn to shift         y ^ ^      2     {\displaystyle {\hat {y}}_{2}}  ![{\displaystyle {\hat {y}}_{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2d678e9549266e3dfc09066e1145e3f7a13fd7d2) towards      y  2     {\displaystyle y_{2}}  ![{\displaystyle y_{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7377c7399e662562cd420fa5c7ce49cfba574998), but not the others.

 

**Teacher forcing** makes it so that the decoder uses the correct output sequence for generating the next entry in the sequence. So for example, it would see     (  y  1   , … …  ,  y  k   )   {\displaystyle (y_{1},\dots ,y_{k})}  ![{\displaystyle (y_{1},\dots ,y_{k})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/06fbc6292b20008e7ee5b70877d89c445b81f6d5) in order to generate         y ^ ^      k + 1     {\displaystyle {\hat {y}}_{k+1}}  ![{\displaystyle {\hat {y}}_{k+1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a1af03c401fbfdd242dd870b01707b2d946b0d68).

 

### Gradient descent

 Main articles: [Gradient descent](./Gradient_descent) and [Vanishing gradient problem](./Vanishing_gradient_problem) 

Gradient descent is a [first-order](./Category:First_order_methods) [iterative](./Iterative_algorithm) [optimization](./Mathematical_optimization) [algorithm](./Algorithm) for finding the minimum of a function. In neural networks, it can be used to minimize the error term by changing each weight in proportion to the derivative of the error with respect to that weight, provided the non-linear [activation functions](./Activation_function) are [differentiable](./Differentiable_function).

 

The standard method for training RNN by gradient descent is the "[backpropagation through time](./Backpropagation_through_time)" (BPTT) algorithm, which is a special case of the general algorithm of [backpropagation](./Backpropagation). A more computationally expensive online variant is called "Real-Time Recurrent Learning" or RTRL,[[78]](./Recurrent_neural_network#cite_note-78)[[79]](./Recurrent_neural_network#cite_note-79) which is an instance of [automatic differentiation](./Automatic_differentiation) in the forward accumulation mode with stacked tangent vectors. Unlike BPTT, this algorithm is [local](./Local_algorithm) in time but not local in space.

 

In this context, local in space means that a unit's weight vector can be updated using only information stored in the connected units and the unit itself such that update complexity of a single unit is linear in the dimensionality of the weight vector. Local in time means that the updates take place continually (on-line) and depend only on the most recent time step rather than on multiple time steps within a given time horizon as in BPTT. Biological neural networks appear to be local with respect to both time and space.[[80]](./Recurrent_neural_network#cite_note-80)[[81]](./Recurrent_neural_network#cite_note-PríncipeEuliano2000-81)

 

For recursively computing the partial derivatives, RTRL has a time-complexity of O(number of hidden x number of weights) per time step for computing the [Jacobian matrices](./Jacobian_matrix), while BPTT only takes O(number of weights) per time step, at the cost of storing all forward activations within the given time horizon.[[82]](./Recurrent_neural_network#cite_note-Ollivier2015-82) An online hybrid between BPTT and RTRL with intermediate complexity exists,[[83]](./Recurrent_neural_network#cite_note-83)[[84]](./Recurrent_neural_network#cite_note-84) along with variants for continuous time.[[85]](./Recurrent_neural_network#cite_note-85)

 

A major problem with gradient descent for standard RNN architectures is that [error gradients vanish](./Vanishing_gradient_problem) exponentially quickly with the size of the time lag between important events.[[55]](./Recurrent_neural_network#cite_note-hochreiter1991-55)[[86]](./Recurrent_neural_network#cite_note-HOCH2001-86) LSTM combined with a BPTT/RTRL hybrid learning method attempts to overcome these problems.[[36]](./Recurrent_neural_network#cite_note-lstm-36) This problem is also solved in the independently recurrent neural network (IndRNN)[[87]](./Recurrent_neural_network#cite_note-auto-87) by reducing the context of a neuron to its own past state and the cross-neuron information can then be explored in the following layers. Memories of different ranges including long-term memory can be learned without the gradient vanishing and exploding problems.

 

The [online algorithm](./Online_algorithm) called **causal recursive backpropagation** (CRBP), implements and combines BPTT and RTRL paradigms for locally recurrent networks.[[88]](./Recurrent_neural_network#cite_note-88) It works with the most general locally recurrent networks. The CRBP algorithm can minimize the global error term. This fact improves the stability of the algorithm, providing a unifying view of gradient calculation techniques for recurrent networks with local feedback.

 

One approach to gradient information computation in RNNs with arbitrary architectures is based on signal-flow graphs diagrammatic derivation.[[89]](./Recurrent_neural_network#cite_note-89) It uses the BPTT batch algorithm, based on Lee's theorem for network sensitivity calculations.[[90]](./Recurrent_neural_network#cite_note-ReferenceA-90) It was proposed by Wan and Beaufays, while its fast online version was proposed by Campolucci, Uncini and Piazza.[[90]](./Recurrent_neural_network#cite_note-ReferenceA-90)

 

### Connectionist temporal classification

 

The [connectionist temporal classification](./Connectionist_temporal_classification) (CTC)[[91]](./Recurrent_neural_network#cite_note-graves2006-91) is a specialized loss function for training RNNs for sequence modeling problems where the timing is variable.[[92]](./Recurrent_neural_network#cite_note-92)

 

### Global optimization methods

 

Training the weights in a neural network can be modeled as a non-linear [global optimization](./Global_optimization) problem. A target function can be formed to evaluate the fitness or error of a particular weight vector as follows: First, the weights in the network are set according to the weight vector. Next, the network is evaluated against the training sequence. Typically, the sum-squared difference between the predictions and the target values specified in the training sequence is used to represent the error of the current weight vector. Arbitrary global optimization techniques may then be used to minimize this target function.

 

The most common global optimization method for training RNNs is [genetic algorithms](./Genetic_algorithm), especially in unstructured networks.[[93]](./Recurrent_neural_network#cite_note-93)[[94]](./Recurrent_neural_network#cite_note-94)[[95]](./Recurrent_neural_network#cite_note-95)

 

Initially, the genetic algorithm is encoded with the neural network weights in a predefined manner where one gene in the [chromosome](./Chromosome_(genetic_algorithm)) represents one weight link. The whole network is represented as a single chromosome. The fitness function is evaluated as follows:

 
- Each weight encoded in the chromosome is assigned to the respective weight link of the network.
- The training set is presented to the network which propagates the input signals forward.
- The mean-squared error is returned to the fitness function.
- This function drives the genetic selection process.

 

Many chromosomes make up the population; therefore, many different neural networks are evolved until a stopping criterion is satisfied. A common stopping scheme can be: 

 
- When the neural network has learned a certain percentage of the training data.
- When the minimum value of the mean-squared-error is satisfied.
- When the maximum number of training generations has been reached.

 

The fitness function evaluates the stopping criterion as it receives the mean-squared error reciprocal from each network during training. Therefore, the goal of the genetic algorithm is to maximize the fitness function, reducing the mean-squared error.

 

Other global (and/or evolutionary) optimization techniques may be used to seek a good set of weights, such as [simulated annealing](./Simulated_annealing) or [particle swarm optimization](./Particle_swarm_optimization).

 

## Other architectures

 

### Independently RNN (IndRNN)

 

The independently recurrent neural network (IndRNN)[[87]](./Recurrent_neural_network#cite_note-auto-87) addresses the gradient vanishing and exploding problems in the traditional fully connected RNN. Each neuron in one layer only receives its own past state as context information (instead of full connectivity to all other neurons in this layer) and thus neurons are independent of each other's history. The gradient backpropagation can be regulated to avoid gradient vanishing and exploding in order to keep long or short-term memory. The cross-neuron information is explored in the next layers. IndRNN can be robustly trained with non-saturated nonlinear functions such as [ReLU](./ReLU). Deep networks can be trained using [skip connections](./Skip_connections).

 

### Neural history compressor

 

The *neural history compressor* is an unsupervised stack of RNNs.[[96]](./Recurrent_neural_network#cite_note-schmidhuber1992-96) At the input level, it learns to predict its next input from the previous inputs. Only unpredictable inputs of some RNN in the hierarchy become inputs to the next higher level RNN, which therefore recomputes its internal state only rarely. Each higher level RNN thus studies a compressed representation of the information in the RNN below. This is done such that the input sequence can be precisely reconstructed from the representation at the highest level.

 

The system effectively minimizes the description length or the negative [logarithm](./Logarithm) of the probability of the data.[[97]](./Recurrent_neural_network#cite_note-scholarpedia2015pre-97) Given a lot of learnable predictability in the incoming data sequence, the highest level RNN can use supervised learning to easily classify even deep sequences with long intervals between important events.

 

It is possible to distill the RNN hierarchy into two RNNs: the "conscious" chunker (higher level) and the "subconscious" automatizer (lower level).[[96]](./Recurrent_neural_network#cite_note-schmidhuber1992-96) Once the chunker has learned to predict and compress inputs that are unpredictable by the automatizer, then the automatizer can be forced in the next learning phase to predict or imitate through additional units the hidden units of the more slowly changing chunker. This makes it easy for the automatizer to learn appropriate, rarely changing memories across long intervals. In turn, this helps the automatizer to make many of its once unpredictable inputs predictable, such that the chunker can focus on the remaining unpredictable events.[[96]](./Recurrent_neural_network#cite_note-schmidhuber1992-96)

 

A [generative model](./Generative_model) partially overcame the [vanishing gradient problem](./Vanishing_gradient_problem)[[55]](./Recurrent_neural_network#cite_note-hochreiter1991-55) of [automatic differentiation](./Automatic_differentiation) or [backpropagation](./Backpropagation) in neural networks in 1992. In 1993, such a system solved a "Very Deep Learning" task that required more than 1000 subsequent layers in an RNN unfolded in time.[[34]](./Recurrent_neural_network#cite_note-schmidhuber1993-34)

 

### Second order RNNs

 

Second-order RNNs use higher order weights     w     i j k     {\displaystyle w{}_{ijk}}  ![{\displaystyle w{}_{ijk}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/847af94eb75e72db4b5604559682ce920572fa69) instead of the standard     w     i j     {\displaystyle w{}_{ij}}  ![{\displaystyle w{}_{ij}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6ef1a6e570e9d6285d37905fd89313b583d2d871) weights, and states can be a product. This allows a direct mapping to a [finite-state machine](./Finite-state_machine) both in training, and representation.[[98]](./Recurrent_neural_network#cite_note-98)[[99]](./Recurrent_neural_network#cite_note-99) Long short-term memory is an example of this but has no such formal mappings or proof of stability.

 

### Hierarchical recurrent neural network

 

Hierarchical recurrent neural networks (HRNN) connect their neurons in various ways to decompose hierarchical behavior into useful subprograms.[[96]](./Recurrent_neural_network#cite_note-schmidhuber1992-96)[[100]](./Recurrent_neural_network#cite_note-100) Such hierarchical structures of cognition are present in theories of memory presented by philosopher [Henri Bergson](./Henri_Bergson), whose philosophical views have inspired hierarchical models.[[101]](./Recurrent_neural_network#cite_note-auto1-101)

 

Hierarchical recurrent neural networks are useful in [forecasting](./Forecasting), helping to predict disaggregated inflation components of the [consumer price index](./Consumer_price_index) (CPI). The HRNN model leverages information from higher levels in the CPI hierarchy to enhance lower-level predictions. Evaluation of a substantial dataset from the US CPI-U index demonstrates the superior performance of the HRNN model compared to various established [inflation](./Inflation) prediction methods.[[102]](./Recurrent_neural_network#cite_note-barkan-102)

 

### Recurrent multilayer perceptron network

 

Generally, a recurrent multilayer perceptron network (RMLPN) consists of cascaded subnetworks, each containing multiple layers of nodes. Each subnetwork is feed-forward except for the last layer, which can have feedback connections. Each of these subnets is connected only by feed-forward connections.[[103]](./Recurrent_neural_network#cite_note-103)

 

### Multiple timescales model

 

A multiple timescales recurrent neural network (MTRNN) is a neural-based computational model that can simulate the functional hierarchy of the brain through self-organization depending on the spatial connection between neurons and on distinct types of neuron activities, each with distinct time properties.[[104]](./Recurrent_neural_network#cite_note-104)[[105]](./Recurrent_neural_network#cite_note-105) With such varied neuronal activities, continuous sequences of any set of behaviors are segmented into reusable primitives, which in turn are flexibly integrated into diverse sequential behaviors. The biological approval of such a type of hierarchy was discussed in the [memory-prediction](./Memory-prediction_framework) theory of brain function by [Hawkins](./Jeff_Hawkins) in his book *[On Intelligence](./On_Intelligence)*.[*[citation needed](./Wikipedia:Citation_needed)*] Such a hierarchy also agrees with theories of memory posited by philosopher [Henri Bergson](./Henri_Bergson), which have been incorporated into an MTRNN model.[[101]](./Recurrent_neural_network#cite_note-auto1-101)[[106]](./Recurrent_neural_network#cite_note-106)

 

### Memristive networks

 

Greg Snider of [HP Labs](./HP_Labs) describes a system of cortical computing with memristive nanodevices.[[107]](./Recurrent_neural_network#cite_note-107) The [memristors](./Memristors) (memory resistors) are implemented by thin film materials in which the resistance is electrically tuned via the transport of ions or oxygen vacancies within the film. [DARPA](./DARPA)'s [SyNAPSE project](./SyNAPSE) has funded IBM Research and HP Labs, in collaboration with the Boston University Department of Cognitive and Neural Systems (CNS), to develop neuromorphic architectures that may be based on memristive systems.
[Memristive networks](./Memristive_networks?action=edit&redlink=1) are a particular type of [physical neural network](./Physical_neural_network) that have very similar properties to (Little-)Hopfield networks, as they have continuous dynamics, a limited memory capacity and natural relaxation via the minimization of a function which is asymptotic to the [Ising model](./Ising_model). In this sense, the dynamics of a memristive circuit have the advantage compared to a Resistor-Capacitor network to have a more interesting non-linear behavior. From this point of view, engineering analog memristive networks account for a peculiar type of [neuromorphic engineering](./Neuromorphic_engineering) in which the device behavior depends on the circuit wiring or topology.
The evolution of these networks can be studied analytically using variations of the [Caravelli-Traversa-Di Ventra equation](./Caravelli-Traversa-Di_Ventra_equation).[[108]](./Recurrent_neural_network#cite_note-108)

 

### Continuous-time

 

A continuous-time recurrent neural network (CTRNN) uses a system of [ordinary differential equations](./Ordinary_differential_equations) to model the effects on a neuron of the incoming inputs. They are typically analyzed by [dynamical systems theory](./Dynamical_systems_theory). Many RNN models in neuroscience are continuous-time.[[16]](./Recurrent_neural_network#cite_note-:0-16)

 

For a neuron     i   {\displaystyle i}  ![{\displaystyle i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/add78d8608ad86e54951b8c8bd6c8d8416533d20) in the network with activation      y  i     {\displaystyle y_{i}}  ![{\displaystyle y_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/67d30d30b6c2dbe4d6f150d699de040937ecc95f), the rate of change of activation is given by:

      τ τ   i       y ˙ ˙      i   = − −   y  i   +  ∑ ∑   j = 1   n    w  j i   σ σ  (  y  j   − −   Θ Θ   j   ) +  I  i   ( t )   {\displaystyle \tau _{i}{\dot {y}}_{i}=-y_{i}+\sum _{j=1}^{n}w_{ji}\sigma (y_{j}-\Theta _{j})+I_{i}(t)}  ![{\displaystyle \tau _{i}{\dot {y}}_{i}=-y_{i}+\sum _{j=1}^{n}w_{ji}\sigma (y_{j}-\Theta _{j})+I_{i}(t)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fe3aece040129e349beb408629229528edbafb24) 

Where:

 
-      τ τ   i     {\displaystyle \tau _{i}}  ![{\displaystyle \tau _{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/814ca8b33360ac3b7db8e9435271b5654175c853) : Time constant of [postsynaptic](./Synapse) node
-      y  i     {\displaystyle y_{i}}  ![{\displaystyle y_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/67d30d30b6c2dbe4d6f150d699de040937ecc95f) : Activation of postsynaptic node
-         y ˙ ˙      i     {\displaystyle {\dot {y}}_{i}}  ![{\displaystyle {\dot {y}}_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d7413f2eddfa4154ca58ecb3aba013f9e5e18309) : Rate of change of activation of postsynaptic node
-     w     j i     {\displaystyle w{}_{ji}}  ![{\displaystyle w{}_{ji}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/921dbd2f06de98163dd3eb31b8ca419431f77241) : Weight of connection from pre to postsynaptic node
-     σ σ  ( x )   {\displaystyle \sigma (x)}  ![{\displaystyle \sigma (x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ae09ff47b50183fbfd1ea5697c63963ec9eefa20) : [Sigmoid](./Sigmoid_function) of x e.g.     σ σ  ( x ) = 1  /  ( 1 +  e  − −  x   )   {\displaystyle \sigma (x)=1/(1+e^{-x})}  ![{\displaystyle \sigma (x)=1/(1+e^{-x})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2d652eb008d808b8f71210bb3d2fe48a5ee451a7).
-      y  j     {\displaystyle y_{j}}  ![{\displaystyle y_{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f8df4e372390588acb968986cfc388e50b930b3a) : Activation of presynaptic node
-      Θ Θ   j     {\displaystyle \Theta _{j}}  ![{\displaystyle \Theta _{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/10b9d5bab99a44d98171cce92f04d0e700060512) : Bias of presynaptic node
-      I  i   ( t )   {\displaystyle I_{i}(t)}  ![{\displaystyle I_{i}(t)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9452bc33550571d001aa8ba5399b61818c26fb60) : Input (if any) to node

 

CTRNNs have been applied to [evolutionary robotics](./Evolutionary_robotics) where they have been used to address vision,[[109]](./Recurrent_neural_network#cite_note-109) co-operation,[[110]](./Recurrent_neural_network#cite_note-Evolving_communication_without_dedicated_communication_channels-110) and minimal cognitive behaviour.[[111]](./Recurrent_neural_network#cite_note-The_dynamics_of_adaptive_behavior:_A_research_program-111)

 

Note that, by the [Shannon sampling theorem](./Shannon_sampling_theorem), discrete-time recurrent neural networks can be viewed as continuous-time recurrent neural networks where the differential equations have transformed into equivalent [difference equations](./Difference_equation).[[112]](./Recurrent_neural_network#cite_note-Sherstinsky-NeurIPS2018-CRACT-3-112) This transformation can be thought of as occurring after the post-synaptic node activation functions      y  i   ( t )   {\displaystyle y_{i}(t)}  ![{\displaystyle y_{i}(t)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/20dfaede0e3f6f701b4c82b5ed153148f5e7d0aa) have been [low-pass filtered](./Low-pass_filter) but prior to sampling.

 

They are in fact [recursive neural networks](./Recursive_neural_network) with a particular structure: that of a linear chain. Whereas recursive neural networks operate on any hierarchical structure, combining child representations into parent representations, recurrent neural networks operate on the linear progression of time, combining the previous time step and a hidden representation into the representation for the current time step.

 

From a time-series perspective, RNNs can appear as nonlinear versions of [finite impulse response](./Finite_impulse_response) and [infinite impulse response](./Infinite_impulse_response) filters and also as a [nonlinear autoregressive exogenous model](./Nonlinear_autoregressive_exogenous_model) (NARX).[[113]](./Recurrent_neural_network#cite_note-113) RNN has infinite impulse response whereas [convolutional neural network](./Convolutional_neural_network) has [finite impulse response](./Finite_impulse_response). Both classes of networks exhibit temporal [dynamic behavior](./Dynamic_system).[[114]](./Recurrent_neural_network#cite_note-114) A finite impulse recurrent network is a [directed acyclic graph](./Directed_acyclic_graph) that can be unrolled and replaced with a strictly feedforward neural network, while an infinite impulse recurrent network is a [directed cyclic graph](./Directed_cyclic_graph) that cannot be unrolled.

 

The effect of memory-based learning for the recognition of sequences can also be implemented by a more biological-based model which uses the silencing mechanism exhibited in neurons with a relatively high frequency [spiking activity](./Action_potential).[[115]](./Recurrent_neural_network#cite_note-115)

 

Additional stored states and the storage under direct control by the network can be added to both [infinite-impulse](./Infinite_impulse_response) and [finite-impulse](./Finite_impulse_response) networks. Another network or graph can also replace the storage if that incorporates time delays or has feedback loops. Such controlled states are referred to as gated states or gated memory and are part of [long short-term memory](./Long_short-term_memory) networks (LSTMs) and [gated recurrent units](./Gated_recurrent_unit). This is also called Feedback Neural Network (FNN).

 

## Libraries

 

Modern libraries provide runtime-optimized implementations of the above functionality or allow to speed up the slow loop by [just-in-time compilation](./Just-in-time_compilation).

 
- [Apache Singa](./Apache_Singa)
- [Caffe](./Caffe_(software)): Created by the Berkeley Vision and Learning Center (BVLC). It supports both CPU and GPU. Developed in [C++](./C++), and has [Python](./Python_(programming_language)) and [MATLAB](./MATLAB) wrappers.
- [Chainer](./Chainer): Fully in Python, production support for CPU, GPU, distributed training.
- [Deeplearning4j](./Deeplearning4j): Deep learning in [Java](./Java_(programming_language)) and [Scala](./Scala_(programming_language)) on multi-GPU-enabled [Spark](./Apache_Spark).
- [Flux](./Flux_(machine-learning_framework)): includes interfaces for RNNs, including GRUs and LSTMs, written in [Julia](./Julia_(programming_language)).
- [Keras](./Keras): High-level API, providing a wrapper to many other deep learning libraries.
- [Microsoft Cognitive Toolkit](./Microsoft_Cognitive_Toolkit)
- [MXNet](./MXNet): an open-source deep learning framework used to train and deploy deep neural networks.
- [PyTorch](./PyTorch): Tensors and Dynamic neural networks in Python with GPU acceleration.
- [TensorFlow](./TensorFlow): Apache 2.0-licensed Theano-like library with support for CPU, GPU and Google's proprietary [TPU](./Tensor_processing_unit),[[116]](./Recurrent_neural_network#cite_note-116) mobile
- [Theano](./Theano_(software)): A deep-learning library for Python with an API largely compatible with the [NumPy](./NumPy) library.
- [Torch](./Torch_(machine_learning)): A scientific computing framework with support for machine learning algorithms, written in [C](./C_(programming_language)) and [Lua](./Lua_(programming_language)).

 

## Applications

 

Applications of recurrent neural networks include:

 
- [Machine translation](./Machine_translation)[[42]](./Recurrent_neural_network#cite_note-sutskever2014-42)
- [Robot control](./Robot_control)[[117]](./Recurrent_neural_network#cite_note-117)
- [Time series prediction](./Time_series_prediction)[[118]](./Recurrent_neural_network#cite_note-118)[[119]](./Recurrent_neural_network#cite_note-119)[[120]](./Recurrent_neural_network#cite_note-120)
- [Speech recognition](./Speech_recognition)[[121]](./Recurrent_neural_network#cite_note-121)[[39]](./Recurrent_neural_network#cite_note-fernandez2007keyword-39)[[122]](./Recurrent_neural_network#cite_note-graves2013-122)
- [Speech synthesis](./Speech_synthesis)[[123]](./Recurrent_neural_network#cite_note-123)
- [Brain–computer interfaces](./Brain–computer_interfaces)[[124]](./Recurrent_neural_network#cite_note-124)
- Time series anomaly detection[[125]](./Recurrent_neural_network#cite_note-125)
- [Text-to-Video model](./Text-to-Video_model)[[126]](./Recurrent_neural_network#cite_note-126)
- [Energy forecasting](./Energy_forecasting)[[127]](./Recurrent_neural_network#cite_note-127)
- Rhythm learning[[128]](./Recurrent_neural_network#cite_note-peephole2002-128)
- Music composition[[129]](./Recurrent_neural_network#cite_note-129)
- Grammar learning[[130]](./Recurrent_neural_network#cite_note-130)[[58]](./Recurrent_neural_network#cite_note-peepholeLSTM-58)[[131]](./Recurrent_neural_network#cite_note-131)
- [Handwriting recognition](./Handwriting_recognition)[[132]](./Recurrent_neural_network#cite_note-132)[[133]](./Recurrent_neural_network#cite_note-133)
- Human action recognition[[134]](./Recurrent_neural_network#cite_note-134)
- Protein homology detection[[135]](./Recurrent_neural_network#cite_note-135)
- Predicting subcellular localization of proteins[[136]](./Recurrent_neural_network#cite_note-ThireoReczko-136)
- Several prediction tasks in the area of business process management[[137]](./Recurrent_neural_network#cite_note-137)
- Prediction in medical care pathways[[138]](./Recurrent_neural_network#cite_note-138)
- Predictions of fusion plasma disruptions in reactors (Fusion Recurrent Neural Network (FRNN) code) [[139]](./Recurrent_neural_network#cite_note-139)

 

## References

 
1. [↑](./Recurrent_neural_network#cite_ref-1) Tealab, Ahmed (2018-12-01). ["Time series forecasting using artificial neural networks methodologies: A systematic review"](https://doi.org/10.1016%2Fj.fcij.2018.10.003). *Future Computing and Informatics Journal*. **3** (2): 334–340. [doi](./Doi_(identifier)):[10.1016/j.fcij.2018.10.003](https://doi.org/10.1016%2Fj.fcij.2018.10.003). [ISSN](./ISSN_(identifier)) [2314-7288](https://search.worldcat.org/issn/2314-7288).
2. [↑](./Recurrent_neural_network#cite_ref-2) [Graves, Alex](./Alex_Graves_(computer_scientist)); Liwicki, Marcus; Fernandez, Santiago; Bertolami, Roman; Bunke, Horst; [Schmidhuber, Jürgen](./Jürgen_Schmidhuber) (2009). ["A Novel Connectionist System for Improved Unconstrained Handwriting Recognition"](http://www.idsia.ch/~juergen/tpami_2008.pdf) (PDF). *IEEE Transactions on Pattern Analysis and Machine Intelligence*. **31** (5): 855–868. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.139.4502](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.139.4502). [doi](./Doi_(identifier)):[10.1109/tpami.2008.137](https://doi.org/10.1109%2Ftpami.2008.137). [PMID](./PMID_(identifier)) [19299860](https://pubmed.ncbi.nlm.nih.gov/19299860). [S2CID](./S2CID_(identifier)) [14635907](https://api.semanticscholar.org/CorpusID:14635907).
3. [1](./Recurrent_neural_network#cite_ref-sak2014_3-0) [2](./Recurrent_neural_network#cite_ref-sak2014_3-1) Sak, Haşim; Senior, Andrew; Beaufays, Françoise (2014). ["Long Short-Term Memory recurrent neural network architectures for large scale acoustic modeling"](https://research.google.com/pubs/archive/43905.pdf) (PDF). Google Research.
4. [1](./Recurrent_neural_network#cite_ref-liwu2015_4-0) [2](./Recurrent_neural_network#cite_ref-liwu2015_4-1) Li, Xiangang; Wu, Xihong (2014-10-15). "Constructing Long Short-Term Memory based Deep Recurrent Neural Networks for Large Vocabulary Speech Recognition". [arXiv](./ArXiv_(identifier)):[1410.4281](https://arxiv.org/abs/1410.4281) [[cs.CL](https://arxiv.org/archive/cs.CL)].
5. [↑](./Recurrent_neural_network#cite_ref-5) Dupond, Samuel (2019). ["A thorough review on the current advance of neural network structures"](https://www.sciencedirect.com/journal/annual-reviews-in-control). *Annual Reviews in Control*. **14**: 200–230.
6. [↑](./Recurrent_neural_network#cite_ref-6) Abiodun, Oludare Isaac; Jantan, Aman; Omolara, Abiodun Esther; Dada, Kemi Victoria; Mohamed, Nachaat Abdelatif; Arshad, Humaira (2018-11-01). ["State-of-the-art in artificial neural network applications: A survey"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6260436). *Heliyon*. **4** (11) e00938. [Bibcode](./Bibcode_(identifier)):[2018Heliy...400938A](https://ui.adsabs.harvard.edu/abs/2018Heliy...400938A). [doi](./Doi_(identifier)):[10.1016/j.heliyon.2018.e00938](https://doi.org/10.1016%2Fj.heliyon.2018.e00938). [ISSN](./ISSN_(identifier)) [2405-8440](https://search.worldcat.org/issn/2405-8440). [PMC](./PMC_(identifier)) [6260436](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6260436). [PMID](./PMID_(identifier)) [30519653](https://pubmed.ncbi.nlm.nih.gov/30519653).
7. [↑](./Recurrent_neural_network#cite_ref-7) Espinosa-Sanchez, Juan Manuel; Gomez-Marin, Alex; de Castro, Fernando (2023-07-05). ["The Importance of Cajal's and Lorente de Nó's Neuroscience to the Birth of Cybernetics"](http://journals.sagepub.com/doi/10.1177/10738584231179932). *The Neuroscientist*. **31** (1): 14–30. [doi](./Doi_(identifier)):[10.1177/10738584231179932](https://doi.org/10.1177%2F10738584231179932). [hdl](./Hdl_(identifier)):[10261/348372](https://hdl.handle.net/10261%2F348372). [ISSN](./ISSN_(identifier)) [1073-8584](https://search.worldcat.org/issn/1073-8584). [PMID](./PMID_(identifier)) [37403768](https://pubmed.ncbi.nlm.nih.gov/37403768).
8. [↑](./Recurrent_neural_network#cite_ref-8) Ramón y Cajal, Santiago (1909). [*Histologie du système nerveux de l'homme & des vertébrés*](https://archive.org/details/b2129592x_0002/page/n159/mode/2up). Vol. II. Foyle Special Collections Library King's College London. Paris : A. Maloine. p. 149.
9. [↑](./Recurrent_neural_network#cite_ref-9) de NÓ, R. Lorente (1933-08-01). ["Vestibulo-Ocular Reflex Arc"](http://archneurpsyc.jamanetwork.com/article.aspx?doi=10.1001/archneurpsyc.1933.02240140009001). *Archives of Neurology and Psychiatry*. **30** (2): 245. [doi](./Doi_(identifier)):[10.1001/archneurpsyc.1933.02240140009001](https://doi.org/10.1001%2Farchneurpsyc.1933.02240140009001). [ISSN](./ISSN_(identifier)) [0096-6754](https://search.worldcat.org/issn/0096-6754).
10. [↑](./Recurrent_neural_network#cite_ref-10) Larriva-Sahd, Jorge A. (2014-12-03). ["Some predictions of Rafael Lorente de Nó 80 years later"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4253658). *Frontiers in Neuroanatomy*. **8**: 147. [doi](./Doi_(identifier)):[10.3389/fnana.2014.00147](https://doi.org/10.3389%2Ffnana.2014.00147). [ISSN](./ISSN_(identifier)) [1662-5129](https://search.worldcat.org/issn/1662-5129). [PMC](./PMC_(identifier)) [4253658](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4253658). [PMID](./PMID_(identifier)) [25520630](https://pubmed.ncbi.nlm.nih.gov/25520630).
11. [↑](./Recurrent_neural_network#cite_ref-11) ["reverberating circuit"](https://www.oxfordreference.com/display/10.1093/oi/authority.20110803100417461). *Oxford Reference*. Retrieved 2024-07-27.
12. [↑](./Recurrent_neural_network#cite_ref-12) McCulloch, Warren S.; Pitts, Walter (December 1943). ["A logical calculus of the ideas immanent in nervous activity"](http://link.springer.com/10.1007/BF02478259). *The Bulletin of Mathematical Biophysics*. **5** (4): 115–133. [doi](./Doi_(identifier)):[10.1007/BF02478259](https://doi.org/10.1007%2FBF02478259). [ISSN](./ISSN_(identifier)) [0007-4985](https://search.worldcat.org/issn/0007-4985).
13. [↑](./Recurrent_neural_network#cite_ref-13) Moreno-Díaz, Roberto; Moreno-Díaz, Arminda (April 2007). ["On the legacy of W.S. McCulloch"](https://linkinghub.elsevier.com/retrieve/pii/S0303264706002152). *Biosystems*. **88** (3): 185–190. [Bibcode](./Bibcode_(identifier)):[2007BiSys..88..185M](https://ui.adsabs.harvard.edu/abs/2007BiSys..88..185M). [doi](./Doi_(identifier)):[10.1016/j.biosystems.2006.08.010](https://doi.org/10.1016%2Fj.biosystems.2006.08.010). [PMID](./PMID_(identifier)) [17184902](https://pubmed.ncbi.nlm.nih.gov/17184902).
14. [↑](./Recurrent_neural_network#cite_ref-14) Arbib, Michael A (December 2000). ["Warren McCulloch's Search for the Logic of the Nervous System"](https://muse.jhu.edu/article/46496). *Perspectives in Biology and Medicine*. **43** (2): 193–216. [doi](./Doi_(identifier)):[10.1353/pbm.2000.0001](https://doi.org/10.1353%2Fpbm.2000.0001). [ISSN](./ISSN_(identifier)) [1529-8795](https://search.worldcat.org/issn/1529-8795). [PMID](./PMID_(identifier)) [10804585](https://pubmed.ncbi.nlm.nih.gov/10804585).
15. [↑](./Recurrent_neural_network#cite_ref-15) Renshaw, Birdsey (1946-05-01). ["Central Effects of Centripetal Impulses in Axons of Spinal Ventral Roots"](https://www.physiology.org/doi/10.1152/jn.1946.9.3.191). *Journal of Neurophysiology*. **9** (3): 191–204. [doi](./Doi_(identifier)):[10.1152/jn.1946.9.3.191](https://doi.org/10.1152%2Fjn.1946.9.3.191). [ISSN](./ISSN_(identifier)) [0022-3077](https://search.worldcat.org/issn/0022-3077). [PMID](./PMID_(identifier)) [21028162](https://pubmed.ncbi.nlm.nih.gov/21028162).
16. [1](./Recurrent_neural_network#cite_ref-:0_16-0) [2](./Recurrent_neural_network#cite_ref-:0_16-1) Grossberg, Stephen (2013-02-22). ["Recurrent Neural Networks"](https://doi.org/10.4249%2Fscholarpedia.1888). *Scholarpedia*. **8** (2): 1888. [Bibcode](./Bibcode_(identifier)):[2013SchpJ...8.1888G](https://ui.adsabs.harvard.edu/abs/2013SchpJ...8.1888G). [doi](./Doi_(identifier)):[10.4249/scholarpedia.1888](https://doi.org/10.4249%2Fscholarpedia.1888). [ISSN](./ISSN_(identifier)) [1941-6016](https://search.worldcat.org/issn/1941-6016).
17. [1](./Recurrent_neural_network#cite_ref-:1_17-0) [2](./Recurrent_neural_network#cite_ref-:1_17-1) [3](./Recurrent_neural_network#cite_ref-:1_17-2) Rosenblatt, Frank (1961-03-15). [*DTIC AD0256582: PRINCIPLES OF NEURODYNAMICS. PERCEPTRONS AND THE THEORY OF BRAIN MECHANISMS*](https://archive.org/details/DTIC_AD0256582/page/n3/mode/2up). Defense Technical Information Center.
18. [↑](./Recurrent_neural_network#cite_ref-18) F. Rosenblatt, "[Perceptual Generalization over Transformation Groups](//archive.org/details/SelfOrganizingSystems/page/n87/mode/1up)", pp. 63--100 in *Self-organizing Systems: Proceedings of an Inter-disciplinary Conference, 5 and 6 May 1959*. Edited by Marshall C. Yovitz and Scott Cameron. London, New York, [etc.], Pergamon Press, 1960. ix, 322 p.
19. [↑](./Recurrent_neural_network#cite_ref-Nakano1971_19-0) Nakano, Kaoru (1971). "Learning Process in a Model of Associative Memory". *Pattern Recognition and Machine Learning*. pp. 172–186. [doi](./Doi_(identifier)):[10.1007/978-1-4615-7566-5_15](https://doi.org/10.1007%2F978-1-4615-7566-5_15). [ISBN](./ISBN_(identifier)) [978-1-4615-7568-9](./Special:BookSources/978-1-4615-7568-9).
20. [↑](./Recurrent_neural_network#cite_ref-Nakano1972_20-0) Nakano, Kaoru (1972). "Associatron-A Model of Associative Memory". *IEEE Transactions on Systems, Man, and Cybernetics*. SMC-2 (3): 380–388. [Bibcode](./Bibcode_(identifier)):[1972ITSMC...2..380N](https://ui.adsabs.harvard.edu/abs/1972ITSMC...2..380N). [doi](./Doi_(identifier)):[10.1109/TSMC.1972.4309133](https://doi.org/10.1109%2FTSMC.1972.4309133).
21. [↑](./Recurrent_neural_network#cite_ref-Amari1972_21-0) Amari, Shun-Ichi (1972). "Learning patterns and pattern sequences by self-organizing nets of threshold elements". *IEEE Transactions*. **C** (21): 1197–1206.
22. [↑](./Recurrent_neural_network#cite_ref-little74_22-0) Little, W. A. (1974). "The Existence of Persistent States in the Brain". *Mathematical Biosciences*. **19** (1–2): 101–120. [doi](./Doi_(identifier)):[10.1016/0025-5564(74)90031-5](https://doi.org/10.1016%2F0025-5564%2874%2990031-5).
23. [↑](./Recurrent_neural_network#cite_ref-lenz1920_23-0) [Lenz, W.](./Wilhelm_Lenz) (1920), "Beiträge zum Verständnis der magnetischen Eigenschaften in festen Körpern", *Physikalische Zeitschrift*, **21**: 613–615.
24. [↑](./Recurrent_neural_network#cite_ref-ising1925_24-0) Ising, E. (1925), "Beitrag zur Theorie des Ferromagnetismus", *Z. Phys.*, **31** (1): 253–258, [Bibcode](./Bibcode_(identifier)):[1925ZPhy...31..253I](https://ui.adsabs.harvard.edu/abs/1925ZPhy...31..253I), [doi](./Doi_(identifier)):[10.1007/BF02980577](https://doi.org/10.1007%2FBF02980577), [S2CID](./S2CID_(identifier)) [122157319](https://api.semanticscholar.org/CorpusID:122157319)
25. [↑](./Recurrent_neural_network#cite_ref-25) Brush, Stephen G. (1967). "History of the Lenz-Ising Model". *Reviews of Modern Physics*. **39** (4): 883–893. [Bibcode](./Bibcode_(identifier)):[1967RvMP...39..883B](https://ui.adsabs.harvard.edu/abs/1967RvMP...39..883B). [doi](./Doi_(identifier)):[10.1103/RevModPhys.39.883](https://doi.org/10.1103%2FRevModPhys.39.883).
26. [↑](./Recurrent_neural_network#cite_ref-:22_26-0) Glauber, Roy J. (February 1963). ["Roy J. Glauber "Time-Dependent Statistics of the Ising Model""](https://aip.scitation.org/doi/abs/10.1063/1.1703954). *Journal of Mathematical Physics*. **4** (2): 294–307. [doi](./Doi_(identifier)):[10.1063/1.1703954](https://doi.org/10.1063%2F1.1703954). Retrieved 2021-03-21.
27. [↑](./Recurrent_neural_network#cite_ref-27) Sherrington, David; Kirkpatrick, Scott (1975-12-29). ["Solvable Model of a Spin-Glass"](https://link.aps.org/doi/10.1103/PhysRevLett.35.1792). *Physical Review Letters*. **35** (26): 1792–1796. [Bibcode](./Bibcode_(identifier)):[1975PhRvL..35.1792S](https://ui.adsabs.harvard.edu/abs/1975PhRvL..35.1792S). [doi](./Doi_(identifier)):[10.1103/PhysRevLett.35.1792](https://doi.org/10.1103%2FPhysRevLett.35.1792). [ISSN](./ISSN_(identifier)) [0031-9007](https://search.worldcat.org/issn/0031-9007).
28. [↑](./Recurrent_neural_network#cite_ref-Hopfield19822_28-0) Hopfield, J. J. (1982). ["Neural networks and physical systems with emergent collective computational abilities"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC346238). *Proceedings of the National Academy of Sciences*. **79** (8): 2554–2558. [Bibcode](./Bibcode_(identifier)):[1982PNAS...79.2554H](https://ui.adsabs.harvard.edu/abs/1982PNAS...79.2554H). [doi](./Doi_(identifier)):[10.1073/pnas.79.8.2554](https://doi.org/10.1073%2Fpnas.79.8.2554). [PMC](./PMC_(identifier)) [346238](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC346238). [PMID](./PMID_(identifier)) [6953413](https://pubmed.ncbi.nlm.nih.gov/6953413).
29. [↑](./Recurrent_neural_network#cite_ref-:02_29-0) Hopfield, J. J. (1984). ["Neurons with graded response have collective computational properties like those of two-state neurons"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC345226). *Proceedings of the National Academy of Sciences*. **81** (10): 3088–3092. [Bibcode](./Bibcode_(identifier)):[1984PNAS...81.3088H](https://ui.adsabs.harvard.edu/abs/1984PNAS...81.3088H). [doi](./Doi_(identifier)):[10.1073/pnas.81.10.3088](https://doi.org/10.1073%2Fpnas.81.10.3088). [PMC](./PMC_(identifier)) [345226](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC345226). [PMID](./PMID_(identifier)) [6587342](https://pubmed.ncbi.nlm.nih.gov/6587342).
30. [↑](./Recurrent_neural_network#cite_ref-30) Engel, A.; Broeck, C. van den (2001). *Statistical mechanics of learning*. Cambridge, UK; New York, NY: Cambridge University Press. [ISBN](./ISBN_(identifier)) [978-0-521-77307-2](./Special:BookSources/978-0-521-77307-2).
31. [↑](./Recurrent_neural_network#cite_ref-31) Seung, H. S.; Sompolinsky, H.; Tishby, N. (1992-04-01). ["Statistical mechanics of learning from examples"](https://journals.aps.org/pra/abstract/10.1103/PhysRevA.45.6056). *Physical Review A*. **45** (8): 6056–6091. [Bibcode](./Bibcode_(identifier)):[1992PhRvA..45.6056S](https://ui.adsabs.harvard.edu/abs/1992PhRvA..45.6056S). [doi](./Doi_(identifier)):[10.1103/PhysRevA.45.6056](https://doi.org/10.1103%2FPhysRevA.45.6056). [PMID](./PMID_(identifier)) [9907706](https://pubmed.ncbi.nlm.nih.gov/9907706).
32. [↑](./Recurrent_neural_network#cite_ref-32) Zhang, Aston; Lipton, Zachary; Li, Mu; Smola, Alexander J. (2024). ["10. Modern Recurrent Neural Networks"](https://d2l.ai/chapter_recurrent-modern/index.html). *Dive into deep learning*. Cambridge New York Port Melbourne New Delhi Singapore: Cambridge University Press. [ISBN](./ISBN_(identifier)) [978-1-009-38943-3](./Special:BookSources/978-1-009-38943-3).
33. [↑](./Recurrent_neural_network#cite_ref-33) Rumelhart, David E.; Hinton, Geoffrey E.; Williams, Ronald J. (October 1986). ["Learning representations by back-propagating errors"](https://www.nature.com/articles/323533a0). *Nature*. **323** (6088): 533–536. [Bibcode](./Bibcode_(identifier)):[1986Natur.323..533R](https://ui.adsabs.harvard.edu/abs/1986Natur.323..533R). [doi](./Doi_(identifier)):[10.1038/323533a0](https://doi.org/10.1038%2F323533a0). [ISSN](./ISSN_(identifier)) [1476-4687](https://search.worldcat.org/issn/1476-4687).
34. [1](./Recurrent_neural_network#cite_ref-schmidhuber1993_34-0) [2](./Recurrent_neural_network#cite_ref-schmidhuber1993_34-1) Schmidhuber, Jürgen (1993). [*Habilitation thesis: System modeling and optimization*](ftp://ftp.idsia.ch/pub/juergen/habilitation.pdf) (PDF).[*[permanent dead link](./Wikipedia:Link_rot)*] Page 150 ff demonstrates credit assignment across the equivalent of 1,200 layers in an unfolded RNN.
35. [↑](./Recurrent_neural_network#cite_ref-35) [Sepp Hochreiter](./Sepp_Hochreiter); [Jürgen Schmidhuber](./Jürgen_Schmidhuber) (21 August 1995), [*Long Short Term Memory*](ftp://ftp.idsia.ch/pub/juergen/fki-207-95.ps.gz), [Wikidata](./WDQ_(identifier)) [Q98967430](https://www.wikidata.org/wiki/Q98967430)
36. [1](./Recurrent_neural_network#cite_ref-lstm_36-0) [2](./Recurrent_neural_network#cite_ref-lstm_36-1) [Hochreiter, Sepp](./Sepp_Hochreiter); Schmidhuber, Jürgen (1997-11-01). "Long Short-Term Memory". *Neural Computation*. **9** (8): 1735–1780. [doi](./Doi_(identifier)):[10.1162/neco.1997.9.8.1735](https://doi.org/10.1162%2Fneco.1997.9.8.1735). [PMID](./PMID_(identifier)) [9377276](https://pubmed.ncbi.nlm.nih.gov/9377276). [S2CID](./S2CID_(identifier)) [1915014](https://api.semanticscholar.org/CorpusID:1915014).
37. [↑](./Recurrent_neural_network#cite_ref-Schuster_37-0) Schuster, Mike, and Kuldip K. Paliwal. "[Bidirectional recurrent neural networks](https://www.researchgate.net/profile/Mike_Schuster/publication/3316656_Bidirectional_recurrent_neural_networks/links/56861d4008ae19758395f85c.pdf)." Signal Processing, IEEE Transactions on 45.11 (1997): 2673-2681.2. Awni Hannun, Carl Case, Jared Casper, Bryan Catanzaro, Greg Diamos, Erich Elsen, Ryan
38. [↑](./Recurrent_neural_network#cite_ref-38) Graves, Alex; Schmidhuber, Jürgen (2005-07-01). "Framewise phoneme classification with bidirectional LSTM and other neural network architectures". *Neural Networks*. IJCNN 2005. **18** (5): 602–610. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.331.5800](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.331.5800). [doi](./Doi_(identifier)):[10.1016/j.neunet.2005.06.042](https://doi.org/10.1016%2Fj.neunet.2005.06.042). [PMID](./PMID_(identifier)) [16112549](https://pubmed.ncbi.nlm.nih.gov/16112549). [S2CID](./S2CID_(identifier)) [1856462](https://api.semanticscholar.org/CorpusID:1856462).
39. [1](./Recurrent_neural_network#cite_ref-fernandez2007keyword_39-0) [2](./Recurrent_neural_network#cite_ref-fernandez2007keyword_39-1) Fernández, Santiago; Graves, Alex; Schmidhuber, Jürgen (2007). ["An Application of Recurrent Neural Networks to Discriminative Keyword Spotting"](http://dl.acm.org/citation.cfm?id=1778066.1778092). *Proceedings of the 17th International Conference on Artificial Neural Networks*. ICANN'07. Berlin, Heidelberg: Springer-Verlag. pp. 220–229. [ISBN](./ISBN_(identifier)) [978-3-540-74693-5](./Special:BookSources/978-3-540-74693-5).
40. [↑](./Recurrent_neural_network#cite_ref-fan2015_40-0) Fan, Bo; Wang, Lijuan; Soong, Frank K.; Xie, Lei (2015). "Photo-Real Talking Head with Deep Bidirectional LSTM". *Proceedings of ICASSP 2015 IEEE International Conference on Acoustics, Speech and Signal Processing*. pp. 4884–8. [doi](./Doi_(identifier)):[10.1109/ICASSP.2015.7178899](https://doi.org/10.1109%2FICASSP.2015.7178899). [ISBN](./ISBN_(identifier)) [978-1-4673-6997-8](./Special:BookSources/978-1-4673-6997-8).
41. [↑](./Recurrent_neural_network#cite_ref-sak2015_41-0) Sak, Haşim; Senior, Andrew; Rao, Kanishka; Beaufays, Françoise; Schalkwyk, Johan (September 2015). ["Google voice search: faster and more accurate"](http://googleresearch.blogspot.ch/2015/09/google-voice-search-faster-and-more.html).
42. [1](./Recurrent_neural_network#cite_ref-sutskever2014_42-0) [2](./Recurrent_neural_network#cite_ref-sutskever2014_42-1) Sutskever, Ilya; Vinyals, Oriol; Le, Quoc V. (2014). ["Sequence to Sequence Learning with Neural Networks"](https://papers.nips.cc/paper/5346-sequence-to-sequence-learning-with-neural-networks.pdf) (PDF). *Electronic Proceedings of the Neural Information Processing Systems Conference*. **27**: 5346. [arXiv](./ArXiv_(identifier)):[1409.3215](https://arxiv.org/abs/1409.3215). [Bibcode](./Bibcode_(identifier)):[2014arXiv1409.3215S](https://ui.adsabs.harvard.edu/abs/2014arXiv1409.3215S).
43. [↑](./Recurrent_neural_network#cite_ref-vinyals2016_43-0) Jozefowicz, Rafal; Vinyals, Oriol; Schuster, Mike; Shazeer, Noam; Wu, Yonghui (2016-02-07). "Exploring the Limits of Language Modeling". [arXiv](./ArXiv_(identifier)):[1602.02410](https://arxiv.org/abs/1602.02410) [[cs.CL](https://arxiv.org/archive/cs.CL)].
44. [↑](./Recurrent_neural_network#cite_ref-gillick2015_44-0) Gillick, Dan; Brunk, Cliff; Vinyals, Oriol; Subramanya, Amarnag (2015-11-30). "Multilingual Language Processing From Bytes". [arXiv](./ArXiv_(identifier)):[1512.00103](https://arxiv.org/abs/1512.00103) [[cs.CL](https://arxiv.org/archive/cs.CL)].
45. [↑](./Recurrent_neural_network#cite_ref-vinyals2015_45-0) Vinyals, Oriol; Toshev, Alexander; Bengio, Samy; Erhan, Dumitru (2014-11-17). "Show and Tell: A Neural Image Caption Generator". [arXiv](./ArXiv_(identifier)):[1411.4555](https://arxiv.org/abs/1411.4555) [[cs.CV](https://arxiv.org/archive/cs.CV)].
46. [↑](./Recurrent_neural_network#cite_ref-:2_46-0) Cho, Kyunghyun; van Merrienboer, Bart; Gulcehre, Caglar; Bahdanau, Dzmitry; Bougares, Fethi; Schwenk, Holger; Bengio, Yoshua (2014-06-03). "Learning Phrase Representations using RNN Encoder-Decoder for Statistical Machine Translation". [arXiv](./ArXiv_(identifier)):[1406.1078](https://arxiv.org/abs/1406.1078) [[cs.CL](https://arxiv.org/archive/cs.CL)].
47. [↑](./Recurrent_neural_network#cite_ref-sequence_47-0) Sutskever, Ilya; Vinyals, Oriol; Le, Quoc Viet (14 Dec 2014). "Sequence to sequence learning with neural networks". [arXiv](./ArXiv_(identifier)):[1409.3215](https://arxiv.org/abs/1409.3215) [[cs.CL](https://arxiv.org/archive/cs.CL)]. [first version posted to arXiv on 10 Sep 2014]
48. [↑](./Recurrent_neural_network#cite_ref-48) Peters ME, Neumann M, Iyyer M, Gardner M, Clark C, Lee K, Zettlemoyer L (2018). "Deep contextualized word representations". [arXiv](./ArXiv_(identifier)):[1802.05365](https://arxiv.org/abs/1802.05365) [[cs.CL](https://arxiv.org/archive/cs.CL)].
49. [↑](./Recurrent_neural_network#cite_ref-49) Vaswani, Ashish; Shazeer, Noam; Parmar, Niki; Uszkoreit, Jakob; Jones, Llion; Gomez, Aidan N; Kaiser, Ł ukasz; Polosukhin, Illia (2017). ["Attention is All you Need"](https://proceedings.neurips.cc/paper/2017/hash/3f5ee243547dee91fbd053c1c4a845aa-Abstract.html). *Advances in Neural Information Processing Systems*. **30**. Curran Associates, Inc.
50. [↑](./Recurrent_neural_network#cite_ref-50) Oord, Aäron van den; Kalchbrenner, Nal; Kavukcuoglu, Koray (2016-06-11). ["Pixel Recurrent Neural Networks"](https://proceedings.mlr.press/v48/oord16.html). *Proceedings of the 33rd International Conference on Machine Learning*. PMLR: 1747–1756.
51. [1](./Recurrent_neural_network#cite_ref-bmm615_51-0) [2](./Recurrent_neural_network#cite_ref-bmm615_51-1) Cruse, Holk; [*Neural Networks as Cybernetic Systems*](http://www.brains-minds-media.org/archive/615/bmm615.pdf), 2nd and revised edition
52. [↑](./Recurrent_neural_network#cite_ref-52) Elman, Jeffrey L. (1990). ["Finding Structure in Time"](https://doi.org/10.1016%2F0364-0213%2890%2990002-E). *Cognitive Science*. **14** (2): 179–211. [doi](./Doi_(identifier)):[10.1016/0364-0213(90)90002-E](https://doi.org/10.1016%2F0364-0213%2890%2990002-E).
53. [↑](./Recurrent_neural_network#cite_ref-53) Jordan, Michael I. (1997-01-01). "Serial Order: A Parallel Distributed Processing Approach". *Neural-Network Models of Cognition — Biobehavioral Foundations*. Advances in Psychology. Vol. 121. pp. 471–495. [doi](./Doi_(identifier)):[10.1016/s0166-4115(97)80111-2](https://doi.org/10.1016%2Fs0166-4115%2897%2980111-2). [ISBN](./ISBN_(identifier)) [978-0-444-81931-4](./Special:BookSources/978-0-444-81931-4). [S2CID](./S2CID_(identifier)) [15375627](https://api.semanticscholar.org/CorpusID:15375627).
54. [↑](./Recurrent_neural_network#cite_ref-gers2002_54-0) Gers, Felix A.; Schraudolph, Nicol N.; Schmidhuber, Jürgen (2002). ["Learning Precise Timing with LSTM Recurrent Networks"](http://www.jmlr.org/papers/volume3/gers02a/gers02a.pdf) (PDF). *Journal of Machine Learning Research*. **3**: 115–143. Retrieved 2017-06-13.
55. [1](./Recurrent_neural_network#cite_ref-hochreiter1991_55-0) [2](./Recurrent_neural_network#cite_ref-hochreiter1991_55-1) [3](./Recurrent_neural_network#cite_ref-hochreiter1991_55-2) Hochreiter, Sepp (1991). [*Untersuchungen zu dynamischen neuronalen Netzen*](http://people.idsia.ch/~juergen/SeppHochreiter1991ThesisAdvisorSchmidhuber.pdf) (PDF) (Diploma). Institut f. Informatik, [Technical University of Munich](./Technical_University_of_Munich).
56. [↑](./Recurrent_neural_network#cite_ref-bayer2009_56-0) Bayer, Justin; Wierstra, Daan; Togelius, Julian; Schmidhuber, Jürgen (2009-09-14). "Evolving Memory Cell Structures for Sequence Learning". [*Artificial Neural Networks – ICANN 2009*](https://mediatum.ub.tum.de/doc/1289041/document.pdf) (PDF). Lecture Notes in Computer Science. Vol. 5769. Berlin, Heidelberg: Springer. pp. 755–764. [doi](./Doi_(identifier)):[10.1007/978-3-642-04277-5_76](https://doi.org/10.1007%2F978-3-642-04277-5_76). [ISBN](./ISBN_(identifier)) [978-3-642-04276-8](./Special:BookSources/978-3-642-04276-8).
57. [↑](./Recurrent_neural_network#cite_ref-fernandez2007_57-0) Fernández, Santiago; Graves, Alex; Schmidhuber, Jürgen (2007). ["Sequence labelling in structured domains with hierarchical recurrent neural networks"](https://www.ijcai.org/Proceedings/07/Papers/124.pdf) (PDF). *Proceedings of the 20th International Joint Conference on Artificial Intelligence, Ijcai 2007*. pp. 774–9. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.79.1887](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.79.1887).
58. [1](./Recurrent_neural_network#cite_ref-peepholeLSTM_58-0) [2](./Recurrent_neural_network#cite_ref-peepholeLSTM_58-1) Gers, Felix A.; Schmidhuber, Jürgen (2001). ["LSTM Recurrent Networks Learn Simple Context Free and Context Sensitive Languages"](https://web.archive.org/web/20170706014426/ftp://ftp.idsia.ch/pub/juergen/L-IEEE.pdf) (PDF). *IEEE Transactions on Neural Networks*. **12** (6): 1333–40. [Bibcode](./Bibcode_(identifier)):[2001ITNN...12.1333G](https://ui.adsabs.harvard.edu/abs/2001ITNN...12.1333G). [doi](./Doi_(identifier)):[10.1109/72.963769](https://doi.org/10.1109%2F72.963769). [PMID](./PMID_(identifier)) [18249962](https://pubmed.ncbi.nlm.nih.gov/18249962). [S2CID](./S2CID_(identifier)) [10192330](https://api.semanticscholar.org/CorpusID:10192330). Archived from [the original](ftp://ftp.idsia.ch/pub/juergen/L-IEEE.pdf) (PDF) on 2017-07-06. Retrieved 2017-12-12.
59. [↑](./Recurrent_neural_network#cite_ref-59) Heck, Joel; Salem, Fathi M. (2017-01-12). "Simplified Minimal Gated Unit Variations for Recurrent Neural Networks". [arXiv](./ArXiv_(identifier)):[1701.03452](https://arxiv.org/abs/1701.03452) [[cs.NE](https://arxiv.org/archive/cs.NE)].
60. [↑](./Recurrent_neural_network#cite_ref-60) Dey, Rahul; Salem, Fathi M. (2017-01-20). "Gate-Variants of Gated Recurrent Unit (GRU) Neural Networks". [arXiv](./ArXiv_(identifier)):[1701.05923](https://arxiv.org/abs/1701.05923) [[cs.NE](https://arxiv.org/archive/cs.NE)].
61. [↑](./Recurrent_neural_network#cite_ref-MyUser_Wildml.com_May_18_2016c_61-0) Britz, Denny (October 27, 2015). ["Recurrent Neural Network Tutorial, Part 4 – Implementing a GRU/LSTM RNN with Python and Theano – WildML"](http://www.wildml.com/2015/10/recurrent-neural-network-tutorial-part-4-implementing-a-grulstm-rnn-with-python-and-theano/). *Wildml.com*. Retrieved May 18, 2016.
62. [1](./Recurrent_neural_network#cite_ref-MyUser_Arxiv.org_May_18_2016c2_62-0) [2](./Recurrent_neural_network#cite_ref-MyUser_Arxiv.org_May_18_2016c2_62-1) Chung, Junyoung; Gulcehre, Caglar; Cho, KyungHyun; Bengio, Yoshua (2014). "Empirical Evaluation of Gated Recurrent Neural Networks on Sequence Modeling". [arXiv](./ArXiv_(identifier)):[1412.3555](https://arxiv.org/abs/1412.3555) [[cs.NE](https://arxiv.org/archive/cs.NE)].
63. [↑](./Recurrent_neural_network#cite_ref-gruber_jockisch_63-0) Gruber, N.; Jockisch, A. (2020), "Are GRU cells more specific and LSTM cells more sensitive in motive classification of text?", *Frontiers in Artificial Intelligence*, **3** 40, [doi](./Doi_(identifier)):[10.3389/frai.2020.00040](https://doi.org/10.3389%2Ffrai.2020.00040), [PMC](./PMC_(identifier)) [7861254](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7861254), [PMID](./PMID_(identifier)) [33733157](https://pubmed.ncbi.nlm.nih.gov/33733157), [S2CID](./S2CID_(identifier)) [220252321](https://api.semanticscholar.org/CorpusID:220252321)
64. [↑](./Recurrent_neural_network#cite_ref-64) Kosko, Bart (1988). "Bidirectional associative memories". *IEEE Transactions on Systems, Man, and Cybernetics*. **18** (1): 49–60. [Bibcode](./Bibcode_(identifier)):[1988ITSMC..18...49K](https://ui.adsabs.harvard.edu/abs/1988ITSMC..18...49K). [doi](./Doi_(identifier)):[10.1109/21.87054](https://doi.org/10.1109%2F21.87054). [S2CID](./S2CID_(identifier)) [59875735](https://api.semanticscholar.org/CorpusID:59875735).
65. [↑](./Recurrent_neural_network#cite_ref-65) Rakkiyappan, Rajan; Chandrasekar, Arunachalam; Lakshmanan, Subramanian; Park, Ju H. (2 January 2015). "Exponential stability for markovian jumping stochastic BAM neural networks with mode-dependent probabilistic time-varying delays and impulse control". *Complexity*. **20** (3): 39–65. [Bibcode](./Bibcode_(identifier)):[2015Cmplx..20c..39R](https://ui.adsabs.harvard.edu/abs/2015Cmplx..20c..39R). [doi](./Doi_(identifier)):[10.1002/cplx.21503](https://doi.org/10.1002%2Fcplx.21503).
66. [↑](./Recurrent_neural_network#cite_ref-66) Rojas, Rául (1996). [*Neural networks: a systematic introduction*](https://books.google.com/books?id=txsjjYzFJS4C&pg=PA336). Springer. p. 336. [ISBN](./ISBN_(identifier)) [978-3-540-60505-8](./Special:BookSources/978-3-540-60505-8).
67. [↑](./Recurrent_neural_network#cite_ref-67) Jaeger, Herbert; Haas, Harald (2004-04-02). "Harnessing Nonlinearity: Predicting Chaotic Systems and Saving Energy in Wireless Communication". *Science*. **304** (5667): 78–80. [Bibcode](./Bibcode_(identifier)):[2004Sci...304...78J](https://ui.adsabs.harvard.edu/abs/2004Sci...304...78J). [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.719.2301](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.719.2301). [doi](./Doi_(identifier)):[10.1126/science.1091277](https://doi.org/10.1126%2Fscience.1091277). [PMID](./PMID_(identifier)) [15064413](https://pubmed.ncbi.nlm.nih.gov/15064413). [S2CID](./S2CID_(identifier)) [2184251](https://api.semanticscholar.org/CorpusID:2184251).
68. [↑](./Recurrent_neural_network#cite_ref-68) Maass, Wolfgang; Natschläger, Thomas; Markram, Henry (2002). ["Real-time computing without stable states: a new framework for neural computation based on perturbations"](https://igi-web.tugraz.at/people/maass/psfiles/130.pdf) (PDF). *Neural Computation*. **14** (11): 2531–2560. [doi](./Doi_(identifier)):[10.1162/089976602760407955](https://doi.org/10.1162%2F089976602760407955). [PMID](./PMID_(identifier)) [12433288](https://pubmed.ncbi.nlm.nih.gov/12433288). [S2CID](./S2CID_(identifier)) [1045112](https://api.semanticscholar.org/CorpusID:1045112).
69. [↑](./Recurrent_neural_network#cite_ref-69) Goller, Christoph; Küchler, Andreas (1996). "Learning task-dependent distributed representations by backpropagation through structure". *Proceedings of International Conference on Neural Networks (ICNN'96)*. Vol. 1. p. 347. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.52.4759](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.52.4759). [doi](./Doi_(identifier)):[10.1109/ICNN.1996.548916](https://doi.org/10.1109%2FICNN.1996.548916). [ISBN](./ISBN_(identifier)) [978-0-7803-3210-2](./Special:BookSources/978-0-7803-3210-2). [S2CID](./S2CID_(identifier)) [6536466](https://api.semanticscholar.org/CorpusID:6536466).
70. [↑](./Recurrent_neural_network#cite_ref-lin1970_70-0) [Linnainmaa, Seppo](./Seppo_Linnainmaa) (1970). *The representation of the cumulative rounding error of an algorithm as a Taylor expansion of the local rounding errors* (MSc) (in Finnish). University of Helsinki.
71. [↑](./Recurrent_neural_network#cite_ref-grie2008_71-0) Griewank, Andreas; [Walther, Andrea](./Andrea_Walther) (2008). [*Evaluating Derivatives: Principles and Techniques of Algorithmic Differentiation*](https://books.google.com/books?id=xoiiLaRxcbEC) (Second ed.). SIAM. [ISBN](./ISBN_(identifier)) [978-0-89871-776-1](./Special:BookSources/978-0-89871-776-1).
72. [↑](./Recurrent_neural_network#cite_ref-72) Socher, Richard; Lin, Cliff; Ng, Andrew Y.; Manning, Christopher D., ["Parsing Natural Scenes and Natural Language with Recursive Neural Networks"](https://ai.stanford.edu/~ang/papers/icml11-ParsingWithRecursiveNeuralNetworks.pdf) (PDF), *28th International Conference on Machine Learning (ICML 2011)*
73. [↑](./Recurrent_neural_network#cite_ref-73) Socher, Richard; Perelygin, Alex; Wu, Jean Y.; Chuang, Jason; Manning, Christopher D.; Ng, Andrew Y.; Potts, Christopher. ["Recursive Deep Models for Semantic Compositionality Over a Sentiment Treebank"](http://nlp.stanford.edu/~socherr/EMNLP2013_RNTN.pdf) (PDF). *Emnlp 2013*.
74. [↑](./Recurrent_neural_network#cite_ref-74) Graves, Alex; Wayne, Greg; Danihelka, Ivo (2014). "Neural Turing Machines". [arXiv](./ArXiv_(identifier)):[1410.5401](https://arxiv.org/abs/1410.5401) [[cs.NE](https://arxiv.org/archive/cs.NE)].
75. [↑](./Recurrent_neural_network#cite_ref-DNCnature2016_75-0) Graves, Alex; Wayne, Greg; Reynolds, Malcolm; Harley, Tim; Danihelka, Ivo; Grabska-Barwińska, Agnieszka; Colmenarejo, Sergio Gómez; Grefenstette, Edward; Ramalho, Tiago (2016-10-12). ["Hybrid computing using a neural network with dynamic external memory"](http://www.nature.com/articles/nature20101.epdf?author_access_token=ImTXBI8aWbYxYQ51Plys8NRgN0jAjWel9jnR3ZoTv0MggmpDmwljGswxVdeocYSurJ3hxupzWuRNeGvvXnoO8o4jTJcnAyhGuZzXJ1GEaD-Z7E6X_a9R-xqJ9TfJWBqz). *Nature*. **538** (7626): 471–476. [Bibcode](./Bibcode_(identifier)):[2016Natur.538..471G](https://ui.adsabs.harvard.edu/abs/2016Natur.538..471G). [doi](./Doi_(identifier)):[10.1038/nature20101](https://doi.org/10.1038%2Fnature20101). [ISSN](./ISSN_(identifier)) [1476-4687](https://search.worldcat.org/issn/1476-4687). [PMID](./PMID_(identifier)) [27732574](https://pubmed.ncbi.nlm.nih.gov/27732574). [S2CID](./S2CID_(identifier)) [205251479](https://api.semanticscholar.org/CorpusID:205251479).
76. [↑](./Recurrent_neural_network#cite_ref-76) Sun, Guo-Zheng; Giles, C. Lee; Chen, Hsing-Hen (1998). "The Neural Network Pushdown Automaton: Architecture, Dynamics and Training". In Giles, C. Lee; Gori, Marco (eds.). *Adaptive Processing of Sequences and Data Structures*. Lecture Notes in Computer Science. Berlin, Heidelberg: Springer. pp. 296–345. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.56.8723](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.56.8723). [doi](./Doi_(identifier)):[10.1007/bfb0054003](https://doi.org/10.1007%2Fbfb0054003). [ISBN](./ISBN_(identifier)) [978-3-540-64341-8](./Special:BookSources/978-3-540-64341-8).
77. [↑](./Recurrent_neural_network#cite_ref-77) Hyötyniemi, Heikki (1996). "Turing machines are recurrent neural networks". *Proceedings of STeP '96/Publications of the Finnish Artificial Intelligence Society*: 13–24.
78. [↑](./Recurrent_neural_network#cite_ref-78) Robinson, Anthony J.; Fallside, Frank (1987). [*The Utility Driven Dynamic Error Propagation Network*](https://books.google.com/books?id=6JYYMwEACAAJ). Technical Report CUED/F-INFENG/TR.1. Department of Engineering, University of Cambridge.
79. [↑](./Recurrent_neural_network#cite_ref-79) Williams, Ronald J.; Zipser, D. (1 February 2013). "Gradient-based learning algorithms for recurrent networks and their computational complexity". In Chauvin, Yves; Rumelhart, David E. (eds.). [*Backpropagation: Theory, Architectures, and Applications*](https://books.google.com/books?id=B71nu3LDpREC). Psychology Press. [ISBN](./ISBN_(identifier)) [978-1-134-77581-1](./Special:BookSources/978-1-134-77581-1).
80. [↑](./Recurrent_neural_network#cite_ref-80) Schmidhuber, Jürgen (1989-01-01). "A Local Learning Algorithm for Dynamic Feedforward and Recurrent Networks". *Connection Science*. **1** (4): 403–412. [doi](./Doi_(identifier)):[10.1080/09540098908915650](https://doi.org/10.1080%2F09540098908915650). [S2CID](./S2CID_(identifier)) [18721007](https://api.semanticscholar.org/CorpusID:18721007).
81. [↑](./Recurrent_neural_network#cite_ref-PríncipeEuliano2000_81-0) Príncipe, José C.; Euliano, Neil R.; Lefebvre, W. Curt (2000). [*Neural and adaptive systems: fundamentals through simulations*](https://books.google.com/books?id=jgMZAQAAIAAJ). Wiley. [ISBN](./ISBN_(identifier)) [978-0-471-35167-2](./Special:BookSources/978-0-471-35167-2).
82. [↑](./Recurrent_neural_network#cite_ref-Ollivier2015_82-0) Yann, Ollivier; Tallec, Corentin; Charpiat, Guillaume (2015-07-28). "Training recurrent networks online without backtracking". [arXiv](./ArXiv_(identifier)):[1507.07680](https://arxiv.org/abs/1507.07680) [[cs.NE](https://arxiv.org/archive/cs.NE)].
83. [↑](./Recurrent_neural_network#cite_ref-83) Schmidhuber, Jürgen (1992-03-01). "A Fixed Size Storage O(n3) Time Complexity Learning Algorithm for Fully Recurrent Continually Running Networks". *Neural Computation*. **4** (2): 243–248. [doi](./Doi_(identifier)):[10.1162/neco.1992.4.2.243](https://doi.org/10.1162%2Fneco.1992.4.2.243). [S2CID](./S2CID_(identifier)) [11761172](https://api.semanticscholar.org/CorpusID:11761172).
84. [↑](./Recurrent_neural_network#cite_ref-84) Williams, Ronald J. (1989). [Complexity of exact gradient computation algorithms for recurrent neural networks](https://web.archive.org/web/20171020033840/http://citeseerx.ist.psu.edu/showciting?cid=128036) (Report). Technical Report NU-CCS-89-27. Boston (MA): Northeastern University, College of Computer Science. Archived from [the original](http://citeseerx.ist.psu.edu/showciting?cid=128036) on 2017-10-20. Retrieved 2017-07-02.
85. [↑](./Recurrent_neural_network#cite_ref-85) Pearlmutter, Barak A. (1989-06-01). ["Learning State Space Trajectories in Recurrent Neural Networks"](http://repository.cmu.edu/cgi/viewcontent.cgi?article=2865&context=compsci). *Neural Computation*. **1** (2): 263–269. [doi](./Doi_(identifier)):[10.1162/neco.1989.1.2.263](https://doi.org/10.1162%2Fneco.1989.1.2.263). [S2CID](./S2CID_(identifier)) [16813485](https://api.semanticscholar.org/CorpusID:16813485).
86. [↑](./Recurrent_neural_network#cite_ref-HOCH2001_86-0) Hochreiter, Sepp; et al. (15 January 2001). ["Gradient flow in recurrent nets: the difficulty of learning long-term dependencies"](https://books.google.com/books?id=NWOcMVA64aAC). In Kolen, John F.; Kremer, Stefan C. (eds.). *A Field Guide to Dynamical Recurrent Networks*. John Wiley & Sons. [ISBN](./ISBN_(identifier)) [978-0-7803-5369-5](./Special:BookSources/978-0-7803-5369-5).
87. [1](./Recurrent_neural_network#cite_ref-auto_87-0) [2](./Recurrent_neural_network#cite_ref-auto_87-1) Li, Shuai; Li, Wanqing; Cook, Chris; Zhu, Ce; Yanbo, Gao (2018). "Independently Recurrent Neural Network (IndRNN): Building a Longer and Deeper RNN". [arXiv](./ArXiv_(identifier)):[1803.04831](https://arxiv.org/abs/1803.04831) [[cs.CV](https://arxiv.org/archive/cs.CV)].
88. [↑](./Recurrent_neural_network#cite_ref-88) Campolucci, Paolo; Uncini, Aurelio; Piazza, Francesco; Rao, Bhaskar D. (1999). "On-Line Learning Algorithms for Locally Recurrent Neural Networks". *IEEE Transactions on Neural Networks*. **10** (2): 253–271. [Bibcode](./Bibcode_(identifier)):[1999ITNN...10..253C](https://ui.adsabs.harvard.edu/abs/1999ITNN...10..253C). [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.33.7550](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.33.7550). [doi](./Doi_(identifier)):[10.1109/72.750549](https://doi.org/10.1109%2F72.750549). [PMID](./PMID_(identifier)) [18252525](https://pubmed.ncbi.nlm.nih.gov/18252525).
89. [↑](./Recurrent_neural_network#cite_ref-89) Wan, Eric A.; Beaufays, Françoise (1996). "Diagrammatic derivation of gradient algorithms for neural networks". *Neural Computation*. **8**: 182–201. [doi](./Doi_(identifier)):[10.1162/neco.1996.8.1.182](https://doi.org/10.1162%2Fneco.1996.8.1.182). [S2CID](./S2CID_(identifier)) [15512077](https://api.semanticscholar.org/CorpusID:15512077).
90. [1](./Recurrent_neural_network#cite_ref-ReferenceA_90-0) [2](./Recurrent_neural_network#cite_ref-ReferenceA_90-1) Campolucci, Paolo; Uncini, Aurelio; Piazza, Francesco (2000). "A Signal-Flow-Graph Approach to On-line Gradient Calculation". *Neural Computation*. **12** (8): 1901–1927. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.212.5406](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.212.5406). [doi](./Doi_(identifier)):[10.1162/089976600300015196](https://doi.org/10.1162%2F089976600300015196). [PMID](./PMID_(identifier)) [10953244](https://pubmed.ncbi.nlm.nih.gov/10953244). [S2CID](./S2CID_(identifier)) [15090951](https://api.semanticscholar.org/CorpusID:15090951).
91. [↑](./Recurrent_neural_network#cite_ref-graves2006_91-0) Graves, Alex; Fernández, Santiago; Gomez, Faustino J. (2006). ["Connectionist temporal classification: Labelling unsegmented sequence data with recurrent neural networks"](https://axon.cs.byu.edu/~martinez/classes/778/Papers/p369-graves.pdf) (PDF). *Proceedings of the International Conference on Machine Learning*. pp. 369–376. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.75.6306](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.75.6306). [doi](./Doi_(identifier)):[10.1145/1143844.1143891](https://doi.org/10.1145%2F1143844.1143891). [ISBN](./ISBN_(identifier)) [1-59593-383-2](./Special:BookSources/1-59593-383-2).
92. [↑](./Recurrent_neural_network#cite_ref-92) Hannun, Awni (2017-11-27). ["Sequence Modeling with CTC"](https://distill.pub/2017/ctc). *Distill*. **2** (11) e8. [doi](./Doi_(identifier)):[10.23915/distill.00008](https://doi.org/10.23915%2Fdistill.00008). [ISSN](./ISSN_(identifier)) [2476-0757](https://search.worldcat.org/issn/2476-0757).
93. [↑](./Recurrent_neural_network#cite_ref-93) Gomez, Faustino J.; Miikkulainen, Risto (1999), ["Solving non-Markovian control tasks with neuroevolution"](http://www.cs.utexas.edu/users/nn/downloads/papers/gomez.ijcai99.pdf) (PDF), *IJCAI 99*, Morgan Kaufmann, retrieved 5 August 2017
94. [↑](./Recurrent_neural_network#cite_ref-94) Syed, Omar (May 1995). [*Applying Genetic Algorithms to Recurrent Neural Networks for Learning Network Parameters and Architecture*](http://arimaa.com/arimaa/about/Thesis/) (MSc). Department of Electrical Engineering, Case Western Reserve University.
95. [↑](./Recurrent_neural_network#cite_ref-95) Gomez, Faustino J.; Schmidhuber, Jürgen; Miikkulainen, Risto (June 2008). ["Accelerated Neural Evolution Through Cooperatively Coevolved Synapses"](https://www.jmlr.org/papers/volume9/gomez08a/gomez08a.pdf) (PDF). *Journal of Machine Learning Research*. **9**: 937–965.
96. [1](./Recurrent_neural_network#cite_ref-schmidhuber1992_96-0) [2](./Recurrent_neural_network#cite_ref-schmidhuber1992_96-1) [3](./Recurrent_neural_network#cite_ref-schmidhuber1992_96-2) [4](./Recurrent_neural_network#cite_ref-schmidhuber1992_96-3) Schmidhuber, Jürgen (1992). ["Learning complex, extended sequences using the principle of history compression"](https://web.archive.org/web/20170706014739/ftp://ftp.idsia.ch/pub/juergen/chunker.pdf) (PDF). *Neural Computation*. **4** (2): 234–242. [doi](./Doi_(identifier)):[10.1162/neco.1992.4.2.234](https://doi.org/10.1162%2Fneco.1992.4.2.234). [S2CID](./S2CID_(identifier)) [18271205](https://api.semanticscholar.org/CorpusID:18271205). Archived from [the original](ftp://ftp.idsia.ch/pub/juergen/chunker.pdf) (PDF) on 2017-07-06.
97. [↑](./Recurrent_neural_network#cite_ref-scholarpedia2015pre_97-0) Schmidhuber, Jürgen (2015). ["Deep Learning"](https://doi.org/10.4249%2Fscholarpedia.32832). *Scholarpedia*. **10** (11) 32832. [Bibcode](./Bibcode_(identifier)):[2015SchpJ..1032832S](https://ui.adsabs.harvard.edu/abs/2015SchpJ..1032832S). [doi](./Doi_(identifier)):[10.4249/scholarpedia.32832](https://doi.org/10.4249%2Fscholarpedia.32832).
98. [↑](./Recurrent_neural_network#cite_ref-98) Giles, C. Lee; Miller, Clifford B.; Chen, Dong; Chen, Hsing-Hen; Sun, Guo-Zheng; Lee, Yee-Chun (1992). ["Learning and Extracting Finite State Automata with Second-Order Recurrent Neural Networks"](https://clgiles.ist.psu.edu/pubs/NC1992-recurrent-NN.pdf) (PDF). *Neural Computation*. **4** (3): 393–405. [doi](./Doi_(identifier)):[10.1162/neco.1992.4.3.393](https://doi.org/10.1162%2Fneco.1992.4.3.393). [S2CID](./S2CID_(identifier)) [19666035](https://api.semanticscholar.org/CorpusID:19666035).
99. [↑](./Recurrent_neural_network#cite_ref-99) Omlin, Christian W.; Giles, C. Lee (1996). "Constructing Deterministic Finite-State Automata in Recurrent Neural Networks". *Journal of the ACM*. **45** (6): 937–972. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.32.2364](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.32.2364). [doi](./Doi_(identifier)):[10.1145/235809.235811](https://doi.org/10.1145%2F235809.235811). [S2CID](./S2CID_(identifier)) [228941](https://api.semanticscholar.org/CorpusID:228941).
100. [↑](./Recurrent_neural_network#cite_ref-100) Paine, Rainer W.; Tani, Jun (2005-09-01). "How Hierarchical Control Self-organizes in Artificial Adaptive Systems". *Adaptive Behavior*. **13** (3): 211–225. [doi](./Doi_(identifier)):[10.1177/105971230501300303](https://doi.org/10.1177%2F105971230501300303). [S2CID](./S2CID_(identifier)) [9932565](https://api.semanticscholar.org/CorpusID:9932565).
101. [1](./Recurrent_neural_network#cite_ref-auto1_101-0) [2](./Recurrent_neural_network#cite_ref-auto1_101-1) ["Burns, Benureau, Tani (2018) A Bergson-Inspired Adaptive Time Constant for the Multiple Timescales Recurrent Neural Network Model. JNNS"](https://www.researchgate.net/publication/328474302).
102. [↑](./Recurrent_neural_network#cite_ref-barkan_102-0) Barkan, Oren; Benchimol, Jonathan; Caspi, Itamar; Cohen, Eliya; Hammer, Allon; Koenigstein, Noam (2023). "Forecasting CPI inflation components with Hierarchical Recurrent Neural Networks". *International Journal of Forecasting*. **39** (3): 1145–1162. [arXiv](./ArXiv_(identifier)):[2011.07920](https://arxiv.org/abs/2011.07920). [doi](./Doi_(identifier)):[10.1016/j.ijforecast.2022.04.009](https://doi.org/10.1016%2Fj.ijforecast.2022.04.009).
103. [↑](./Recurrent_neural_network#cite_ref-103) Tutschku, Kurt (June 1995). *Recurrent Multilayer Perceptrons for Identification and Control: The Road to Applications*. Institute of Computer Science Research Report. Vol. 118. University of Würzburg Am Hubland. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.45.3527](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.45.3527).
104. [↑](./Recurrent_neural_network#cite_ref-104) Yamashita, Yuichi; Tani, Jun (2008-11-07). ["Emergence of Functional Hierarchy in a Multiple Timescale Neural Network Model: A Humanoid Robot Experiment"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2570613). *PLOS Computational Biology*. **4** (11) e1000220. [Bibcode](./Bibcode_(identifier)):[2008PLSCB...4E0220Y](https://ui.adsabs.harvard.edu/abs/2008PLSCB...4E0220Y). [doi](./Doi_(identifier)):[10.1371/journal.pcbi.1000220](https://doi.org/10.1371%2Fjournal.pcbi.1000220). [PMC](./PMC_(identifier)) [2570613](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2570613). [PMID](./PMID_(identifier)) [18989398](https://pubmed.ncbi.nlm.nih.gov/18989398).
105. [↑](./Recurrent_neural_network#cite_ref-105) Alnajjar, Fady; Yamashita, Yuichi; Tani, Jun (2013). ["The hierarchical and functional connectivity of higher-order cognitive mechanisms: neurorobotic model to investigate the stability and flexibility of working memory"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3575058). *Frontiers in Neurorobotics*. **7**: 2. [doi](./Doi_(identifier)):[10.3389/fnbot.2013.00002](https://doi.org/10.3389%2Ffnbot.2013.00002). [PMC](./PMC_(identifier)) [3575058](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3575058). [PMID](./PMID_(identifier)) [23423881](https://pubmed.ncbi.nlm.nih.gov/23423881).
106. [↑](./Recurrent_neural_network#cite_ref-106) ["Proceedings of the 28th Annual Conference of the Japanese Neural Network Society (October, 2018)"](https://web.archive.org/web/20200509004753/http://jnns.org/conference/2018/JNNS2018_Technical_Programs.pdf) (PDF). Archived from [the original](http://jnns.org/conference/2018/JNNS2018_Technical_Programs.pdf) (PDF) on 2020-05-09. Retrieved 2021-02-06.
107. [↑](./Recurrent_neural_network#cite_ref-107) Snider, Greg (2008), ["Cortical computing with memristive nanodevices"](https://web.archive.org/web/20160516070906/http://www.scidacreview.org/0804/html/hardware.html), *Sci-DAC Review*, **10**: 58–65, archived from [the original](http://www.scidacreview.org/0804/html/hardware.html) on 2016-05-16, retrieved 2019-09-06
108. [↑](./Recurrent_neural_network#cite_ref-108) Caravelli, Francesco; Traversa, Fabio Lorenzo; Di Ventra, Massimiliano (2017). "The complex dynamics of memristive circuits: analytical results and universal slow relaxation". *Physical Review E*. **95** (2) 022140. [arXiv](./ArXiv_(identifier)):[1608.08651](https://arxiv.org/abs/1608.08651). [Bibcode](./Bibcode_(identifier)):[2017PhRvE..95b2140C](https://ui.adsabs.harvard.edu/abs/2017PhRvE..95b2140C). [doi](./Doi_(identifier)):[10.1103/PhysRevE.95.022140](https://doi.org/10.1103%2FPhysRevE.95.022140). [PMID](./PMID_(identifier)) [28297937](https://pubmed.ncbi.nlm.nih.gov/28297937). [S2CID](./S2CID_(identifier)) [6758362](https://api.semanticscholar.org/CorpusID:6758362).
109. [↑](./Recurrent_neural_network#cite_ref-109) Harvey, Inman; Husbands, Phil; Cliff, Dave (1994), ["Seeing the light: Artificial evolution, real vision"](https://www.researchgate.net/publication/229091538_Seeing_the_Light_Artificial_Evolution_Real_Vision), *3rd international conference on Simulation of adaptive behavior: from animals to animats 3*, pp. 392–401
110. [↑](./Recurrent_neural_network#cite_ref-Evolving_communication_without_dedicated_communication_channels_110-0) Quinn, Matt (2001). "Evolving communication without dedicated communication channels". *Advances in Artificial Life: 6th European Conference, ECAL 2001*. pp. 357–366. [doi](./Doi_(identifier)):[10.1007/3-540-44811-X_38](https://doi.org/10.1007%2F3-540-44811-X_38). [ISBN](./ISBN_(identifier)) [978-3-540-42567-0](./Special:BookSources/978-3-540-42567-0).
111. [↑](./Recurrent_neural_network#cite_ref-The_dynamics_of_adaptive_behavior:_A_research_program_111-0) Beer, Randall D. (1997). "The dynamics of adaptive behavior: A research program". *Robotics and Autonomous Systems*. **20** (2–4): 257–289. [doi](./Doi_(identifier)):[10.1016/S0921-8890(96)00063-2](https://doi.org/10.1016%2FS0921-8890%2896%2900063-2).
112. [↑](./Recurrent_neural_network#cite_ref-Sherstinsky-NeurIPS2018-CRACT-3_112-0) Sherstinsky, Alex (2018-12-07). Bloem-Reddy, Benjamin; Paige, Brooks; Kusner, Matt; Caruana, Rich; Rainforth, Tom; Teh, Yee Whye (eds.). [*Deriving the Recurrent Neural Network Definition and RNN Unrolling Using Signal Processing*](https://www.researchgate.net/publication/331718291). [Critiquing and Correcting Trends in Machine Learning Workshop at NeurIPS-2018](https://ml-critique-correct.github.io/).
113. [↑](./Recurrent_neural_network#cite_ref-113) Siegelmann, Hava T.; Horne, Bill G.; Giles, C. Lee (1995). ["Computational Capabilities of Recurrent NARX Neural Networks"](https://books.google.com/books?id=830-HAAACAAJ&pg=PA208). *IEEE Transactions on Systems, Man, and Cybernetics - Part B: Cybernetics*. **27** (2): 208–15. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.48.7468](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.48.7468). [doi](./Doi_(identifier)):[10.1109/3477.558801](https://doi.org/10.1109%2F3477.558801). [PMID](./PMID_(identifier)) [18255858](https://pubmed.ncbi.nlm.nih.gov/18255858).
114. [↑](./Recurrent_neural_network#cite_ref-114) Miljanovic, Milos (Feb–Mar 2012). ["Comparative analysis of Recurrent and Finite Impulse Response Neural Networks in Time Series Prediction"](http://www.ijcse.com/docs/INDJCSE12-03-01-028.pdf) (PDF). *Indian Journal of Computer and Engineering*. **3** (1).
115. [↑](./Recurrent_neural_network#cite_ref-115) Hodassman, Shiri; Meir, Yuval; Kisos, Karin; Ben-Noam, Itamar; Tugendhaft, Yael; Goldental, Amir; Vardi, Roni; Kanter, Ido (2022-09-29). ["Brain inspired neuronal silencing mechanism to enable reliable sequence identification"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9523036). *Scientific Reports*. **12** (1): 16003. [arXiv](./ArXiv_(identifier)):[2203.13028](https://arxiv.org/abs/2203.13028). [Bibcode](./Bibcode_(identifier)):[2022NatSR..1216003H](https://ui.adsabs.harvard.edu/abs/2022NatSR..1216003H). [doi](./Doi_(identifier)):[10.1038/s41598-022-20337-x](https://doi.org/10.1038%2Fs41598-022-20337-x). [ISSN](./ISSN_(identifier)) [2045-2322](https://search.worldcat.org/issn/2045-2322). [PMC](./PMC_(identifier)) [9523036](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9523036). [PMID](./PMID_(identifier)) [36175466](https://pubmed.ncbi.nlm.nih.gov/36175466).
116. [↑](./Recurrent_neural_network#cite_ref-116) Metz, Cade (May 18, 2016). ["Google Built Its Very Own Chips to Power Its AI Bots"](https://www.wired.com/2016/05/google-tpu-custom-chips/). *Wired*.
117. [↑](./Recurrent_neural_network#cite_ref-117) Mayer, Hermann; Gomez, Faustino J.; Wierstra, Daan; Nagy, Istvan; Knoll, Alois; Schmidhuber, Jürgen (October 2006). "A System for Robotic Heart Surgery that Learns to Tie Knots Using Recurrent Neural Networks". *2006 IEEE/RSJ International Conference on Intelligent Robots and Systems*. pp. 543–548. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.218.3399](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.218.3399). [doi](./Doi_(identifier)):[10.1109/IROS.2006.282190](https://doi.org/10.1109%2FIROS.2006.282190). [ISBN](./ISBN_(identifier)) [978-1-4244-0258-8](./Special:BookSources/978-1-4244-0258-8). [S2CID](./S2CID_(identifier)) [12284900](https://api.semanticscholar.org/CorpusID:12284900).
118. [↑](./Recurrent_neural_network#cite_ref-118) Wierstra, Daan; Schmidhuber, Jürgen; Gomez, Faustino J. (2005). ["Evolino: Hybrid Neuroevolution/Optimal Linear Search for Sequence Learning"](https://www.academia.edu/5830256). *Proceedings of the 19th International Joint Conference on Artificial Intelligence (IJCAI), Edinburgh*. pp. 853–8. [OCLC](./OCLC_(identifier)) [62330637](https://search.worldcat.org/oclc/62330637).
119. [↑](./Recurrent_neural_network#cite_ref-119) Petneházi, Gábor (2019-01-01). "Recurrent neural networks for time series forecasting". [arXiv](./ArXiv_(identifier)):[1901.00069](https://arxiv.org/abs/1901.00069) [[cs.LG](https://arxiv.org/archive/cs.LG)].
120. [↑](./Recurrent_neural_network#cite_ref-120) Hewamalage, Hansika; Bergmeir, Christoph; Bandara, Kasun (2020). "Recurrent Neural Networks for Time Series Forecasting: Current Status and Future Directions". *International Journal of Forecasting*. **37**: 388–427. [arXiv](./ArXiv_(identifier)):[1909.00590](https://arxiv.org/abs/1909.00590). [doi](./Doi_(identifier)):[10.1016/j.ijforecast.2020.06.008](https://doi.org/10.1016%2Fj.ijforecast.2020.06.008). [S2CID](./S2CID_(identifier)) [202540863](https://api.semanticscholar.org/CorpusID:202540863).
121. [↑](./Recurrent_neural_network#cite_ref-121) Graves, Alex; Schmidhuber, Jürgen (2005). "Framewise phoneme classification with bidirectional LSTM and other neural network architectures". *Neural Networks*. **18** (5–6): 602–610. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.331.5800](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.331.5800). [doi](./Doi_(identifier)):[10.1016/j.neunet.2005.06.042](https://doi.org/10.1016%2Fj.neunet.2005.06.042). [PMID](./PMID_(identifier)) [16112549](https://pubmed.ncbi.nlm.nih.gov/16112549). [S2CID](./S2CID_(identifier)) [1856462](https://api.semanticscholar.org/CorpusID:1856462).
122. [↑](./Recurrent_neural_network#cite_ref-graves2013_122-0) Graves, Alex; Mohamed, Abdel-rahman; Hinton, Geoffrey E. (2013). "Speech recognition with deep recurrent neural networks". *2013 IEEE International Conference on Acoustics, Speech and Signal Processing*. pp. 6645–9. [arXiv](./ArXiv_(identifier)):[1303.5778](https://arxiv.org/abs/1303.5778). [doi](./Doi_(identifier)):[10.1109/ICASSP.2013.6638947](https://doi.org/10.1109%2FICASSP.2013.6638947). [ISBN](./ISBN_(identifier)) [978-1-4799-0356-6](./Special:BookSources/978-1-4799-0356-6). [S2CID](./S2CID_(identifier)) [206741496](https://api.semanticscholar.org/CorpusID:206741496).
123. [↑](./Recurrent_neural_network#cite_ref-123) Chang, Edward F.; Chartier, Josh; Anumanchipalli, Gopala K. (24 April 2019). ["Speech synthesis from neural decoding of spoken sentences"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9714519). *Nature*. **568** (7753): 493–8. [Bibcode](./Bibcode_(identifier)):[2019Natur.568..493A](https://ui.adsabs.harvard.edu/abs/2019Natur.568..493A). [doi](./Doi_(identifier)):[10.1038/s41586-019-1119-1](https://doi.org/10.1038%2Fs41586-019-1119-1). [ISSN](./ISSN_(identifier)) [1476-4687](https://search.worldcat.org/issn/1476-4687). [PMC](./PMC_(identifier)) [9714519](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9714519). [PMID](./PMID_(identifier)) [31019317](https://pubmed.ncbi.nlm.nih.gov/31019317). [S2CID](./S2CID_(identifier)) [129946122](https://api.semanticscholar.org/CorpusID:129946122).
124. [↑](./Recurrent_neural_network#cite_ref-124) Moses, David A.; Metzger, Sean L.; Liu, Jessie R.; Anumanchipalli, Gopala K.; Makin, Joseph G.; Sun, Pengfei F.; Chartier, Josh; Dougherty, Maximilian E.; Liu, Patricia M.; Abrams, Gary M.; Tu-Chan, Adelyn; Ganguly, Karunesh; Chang, Edward F. (2021-07-15). ["Neuroprosthesis for Decoding Speech in a Paralyzed Person with Anarthria"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8972947). *New England Journal of Medicine*. **385** (3): 217–227. [doi](./Doi_(identifier)):[10.1056/NEJMoa2027540](https://doi.org/10.1056%2FNEJMoa2027540). [PMC](./PMC_(identifier)) [8972947](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8972947). [PMID](./PMID_(identifier)) [34260835](https://pubmed.ncbi.nlm.nih.gov/34260835).
125. [↑](./Recurrent_neural_network#cite_ref-125) Malhotra, Pankaj; Vig, Lovekesh; Shroff, Gautam; Agarwal, Puneet (April 2015). ["Long Short Term Memory Networks for Anomaly Detection in Time Series"](https://books.google.com/books?id=USGLCgAAQBAJ&pg=PA89). *European Symposium on Artificial Neural Networks, Computational Intelligence and Machine Learning – ESANN 2015*. Ciaco. pp. 89–94. [ISBN](./ISBN_(identifier)) [978-2-87587-015-5](./Special:BookSources/978-2-87587-015-5).
126. [↑](./Recurrent_neural_network#cite_ref-126) ["Papers with Code - DeepHS-HDRVideo: Deep High Speed High Dynamic Range Video Reconstruction"](https://paperswithcode.com/paper/deephs-hdrvideo-deep-high-speed-high-dynamic). *paperswithcode.com*. Retrieved 2022-10-13.
127. [↑](./Recurrent_neural_network#cite_ref-127) Maity, Abhishek; Tukarul, Viraj (23 January 2026). "Forecasting Energy Consumption using Recurrent Neural Networks: A Comparative Analysis". [arXiv](./ArXiv_(identifier)):[2601.17110](https://arxiv.org/abs/2601.17110) [[cs.CY](https://arxiv.org/archive/cs.CY)].
128. [↑](./Recurrent_neural_network#cite_ref-peephole2002_128-0) Gers, Felix A.; Schraudolph, Nicol N.; Schmidhuber, Jürgen (2002). ["Learning precise timing with LSTM recurrent networks"](http://www.jmlr.org/papers/volume3/gers02a/gers02a.pdf) (PDF). *Journal of Machine Learning Research*. **3**: 115–143.
129. [↑](./Recurrent_neural_network#cite_ref-129) Eck, Douglas; Schmidhuber, Jürgen (2002-08-28). "Learning the Long-Term Structure of the Blues". *Artificial Neural Networks — ICANN 2002*. Lecture Notes in Computer Science. Vol. 2415. Berlin, Heidelberg: Springer. pp. 284–289. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.116.3620](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.116.3620). [doi](./Doi_(identifier)):[10.1007/3-540-46084-5_47](https://doi.org/10.1007%2F3-540-46084-5_47). [ISBN](./ISBN_(identifier)) [978-3-540-46084-8](./Special:BookSources/978-3-540-46084-8).
130. [↑](./Recurrent_neural_network#cite_ref-130) Schmidhuber, Jürgen; Gers, Felix A.; Eck, Douglas (2002). "Learning nonregular languages: A comparison of simple recurrent networks and LSTM". *Neural Computation*. **14** (9): 2039–2041. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.11.7369](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.11.7369). [doi](./Doi_(identifier)):[10.1162/089976602320263980](https://doi.org/10.1162%2F089976602320263980). [PMID](./PMID_(identifier)) [12184841](https://pubmed.ncbi.nlm.nih.gov/12184841). [S2CID](./S2CID_(identifier)) [30459046](https://api.semanticscholar.org/CorpusID:30459046).
131. [↑](./Recurrent_neural_network#cite_ref-131) Pérez-Ortiz, Juan Antonio; Gers, Felix A.; Eck, Douglas; Schmidhuber, Jürgen (2003). "Kalman filters improve LSTM network performance in problems unsolvable by traditional recurrent nets". *Neural Networks*. **16** (2): 241–250. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.381.1992](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.381.1992). [doi](./Doi_(identifier)):[10.1016/s0893-6080(02)00219-8](https://doi.org/10.1016%2Fs0893-6080%2802%2900219-8). [PMID](./PMID_(identifier)) [12628609](https://pubmed.ncbi.nlm.nih.gov/12628609).
132. [↑](./Recurrent_neural_network#cite_ref-132) Graves, Alex; Schmidhuber, Jürgen (2009). ["Offline Handwriting Recognition with Multidimensional Recurrent Neural Networks"](http://papers.neurips.cc/paper/3449-offline-handwriting-recognition-with-multidimensional-recurrent-neural-networks.pdf) (PDF). *Advances in Neural Information Processing Systems*. Vol. 22, NIPS'22. MIT Press. pp. 545–552.
133. [↑](./Recurrent_neural_network#cite_ref-133) Graves, Alex; Fernández, Santiago; Liwicki, Marcus; Bunke, Horst; Schmidhuber, Jürgen (2007). ["Unconstrained Online Handwriting Recognition with Recurrent Neural Networks"](http://dl.acm.org/citation.cfm?id=2981562.2981635). *Proceedings of the 20th International Conference on Neural Information Processing Systems*. Curran Associates. pp. 577–584. [ISBN](./ISBN_(identifier)) [978-1-60560-352-0](./Special:BookSources/978-1-60560-352-0).
134. [↑](./Recurrent_neural_network#cite_ref-134) Baccouche, Moez; Mamalet, Franck; Wolf, Christian; Garcia, Christophe; Baskurt, Atilla (2011). "Sequential Deep Learning for Human Action Recognition". In Salah, Albert Ali; Lepri, Bruno (eds.). *Human Behavior Unterstanding*. Lecture Notes in Computer Science. Vol. 7065. Amsterdam, Netherlands: Springer. pp. 29–39. [doi](./Doi_(identifier)):[10.1007/978-3-642-25446-8_4](https://doi.org/10.1007%2F978-3-642-25446-8_4). [ISBN](./ISBN_(identifier)) [978-3-642-25445-1](./Special:BookSources/978-3-642-25445-1).
135. [↑](./Recurrent_neural_network#cite_ref-135) Hochreiter, Sepp; Heusel, Martin; Obermayer, Klaus (2007). ["Fast model-based protein homology detection without alignment"](https://doi.org/10.1093%2Fbioinformatics%2Fbtm247). *Bioinformatics*. **23** (14): 1728–1736. [doi](./Doi_(identifier)):[10.1093/bioinformatics/btm247](https://doi.org/10.1093%2Fbioinformatics%2Fbtm247). [PMID](./PMID_(identifier)) [17488755](https://pubmed.ncbi.nlm.nih.gov/17488755).
136. [↑](./Recurrent_neural_network#cite_ref-ThireoReczko_136-0) Thireou, Trias; Reczko, Martin (July 2007). "Bidirectional Long Short-Term Memory Networks for Predicting the Subcellular Localization of Eukaryotic Proteins". *IEEE/ACM Transactions on Computational Biology and Bioinformatics*. **4** (3): 441–446. [Bibcode](./Bibcode_(identifier)):[2007ITCBB...4..441T](https://ui.adsabs.harvard.edu/abs/2007ITCBB...4..441T). [doi](./Doi_(identifier)):[10.1109/tcbb.2007.1015](https://doi.org/10.1109%2Ftcbb.2007.1015). [PMID](./PMID_(identifier)) [17666763](https://pubmed.ncbi.nlm.nih.gov/17666763). [S2CID](./S2CID_(identifier)) [11787259](https://api.semanticscholar.org/CorpusID:11787259).
137. [↑](./Recurrent_neural_network#cite_ref-137) Tax, Niek; Verenich, Ilya; La Rosa, Marcello; Dumas, Marlon (2017). "Predictive Business Process Monitoring with LSTM Neural Networks". *Advanced Information Systems Engineering*. Lecture Notes in Computer Science. Vol. 10253. pp. 477–492. [arXiv](./ArXiv_(identifier)):[1612.02130](https://arxiv.org/abs/1612.02130). [doi](./Doi_(identifier)):[10.1007/978-3-319-59536-8_30](https://doi.org/10.1007%2F978-3-319-59536-8_30). [ISBN](./ISBN_(identifier)) [978-3-319-59535-1](./Special:BookSources/978-3-319-59535-1). [S2CID](./S2CID_(identifier)) [2192354](https://api.semanticscholar.org/CorpusID:2192354).
138. [↑](./Recurrent_neural_network#cite_ref-138) Choi, Edward; Bahadori, Mohammad Taha; Schuetz, Andy; Stewart, Walter F.; Sun, Jimeng (2016). ["Doctor AI: Predicting Clinical Events via Recurrent Neural Networks"](http://proceedings.mlr.press/v56/Choi16.html). *JMLR Workshop and Conference Proceedings*. **56**: 301–318. [arXiv](./ArXiv_(identifier)):[1511.05942](https://arxiv.org/abs/1511.05942). [PMC](./PMC_(identifier)) [5341604](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5341604). [PMID](./PMID_(identifier)) [28286600](https://pubmed.ncbi.nlm.nih.gov/28286600).
139. [↑](./Recurrent_neural_network#cite_ref-139) ["Artificial intelligence helps accelerate progress toward efficient fusion reactions"](https://www.princeton.edu/news/2017/12/15/artificial-intelligence-helps-accelerate-progress-toward-efficient-fusion-reactions). *Princeton University*. Retrieved 2023-06-12.

 

## Further reading

 
- Mandic, Danilo P.; Chambers, Jonathon A. (2001). *Recurrent Neural Networks for Prediction: Learning Algorithms, Architectures and Stability*. Wiley. [ISBN](./ISBN_(identifier)) [978-0-471-49517-8](./Special:BookSources/978-0-471-49517-8).
- Grossberg, Stephen (2013-02-22). ["Recurrent Neural Networks"](https://doi.org/10.4249%2Fscholarpedia.1888). *Scholarpedia*. **8** (2): 1888. [Bibcode](./Bibcode_(identifier)):[2013SchpJ...8.1888G](https://ui.adsabs.harvard.edu/abs/2013SchpJ...8.1888G). [doi](./Doi_(identifier)):[10.4249/scholarpedia.1888](https://doi.org/10.4249%2Fscholarpedia.1888). [ISSN](./ISSN_(identifier)) [1941-6016](https://search.worldcat.org/issn/1941-6016).
- [Recurrent Neural Networks](http://www.idsia.ch/~juergen/rnn.html). List of RNN papers by [Jürgen Schmidhuber](./Jürgen_Schmidhuber)'s group at [Dalle Molle Institute for Artificial Intelligence Research](./Dalle_Molle_Institute_for_Artificial_Intelligence_Research).

 
| vteArtificial intelligence(AI) |
| --- |
| HistorytimelineGlossaryCompaniesProjectsList of open-source AI software |
| Concepts | Automated reasoningParameterHyperparameterLoss functionsRegressionBias–variance tradeoffDouble descentOverfittingClusteringGradient descentSGDQuasi-Newton methodConjugate gradient methodBackpropagationAttentionConvolutionNormalizationBatchnormActivationSoftmaxSigmoidRectifierGatingWeight initializationRegularizationDatasetsAugmentationPrompt engineeringReinforcement learningQ-learningSARSAImitationPolicy gradientDiffusionLatent diffusion modelAutoregressionAdversaryRAGUncanny valleyRLHFSelf-supervised learningReflectionRecursive self-improvementHallucinationWord embeddingVibe codingSymbolic AINeuro-symbolic AI |
| Applications | Automated theorem provingMachine learningIn-context learningArtificial neural networkDeep learningLanguage modelLargeNMTReasoningModel Context ProtocolIntelligent agentAI agentArtificial human companionHumanity's Last ExamLethal autonomous weapons (LAWs)Generative AIWeak AIHypotheticalArtificial general intelligence (AGI)Artificial superintelligence (ASI)Agent2Agent protocol |
| Implementations | Audio–visualAlexNetWaveNetHuman image synthesisHWROCRComputer visionSpeech synthesis15.aiElevenLabsSpeech recognitionWhisperFacial recognitionAlphaFoldText-to-image modelsAuroraDALL-EFireflyFluxGPT ImageIdeogramImagenMidjourneyRecraftStable DiffusionText-to-video modelsDream MachineRunway GenHailuo AIKlingSoraSeedanceVeoMusic generationRiffusionSunoUdioWorld modelsGenieOasisTextList of large language modelsProject DebaterIBM WatsonIBM WatsonxDecisionalAlphaGoAlphaZeroOpenAI FiveSelf-driving carMuZeroAction selectionAutoGPTRobot controlReasoning systemsDeductive classifiersExpert systemsInference enginesKnowledge-based systemsLogic programsProcedural reasoning systemsSemantic reasonersRule-based systemsCognitive architecturesACT-RSoarCLARIONLIDAOpenCogKnowledge basesConceptNetWikidataDBpediaYAGO | Audio–visual | AlexNetWaveNetHuman image synthesisHWROCRComputer visionSpeech synthesis15.aiElevenLabsSpeech recognitionWhisperFacial recognitionAlphaFoldText-to-image modelsAuroraDALL-EFireflyFluxGPT ImageIdeogramImagenMidjourneyRecraftStable DiffusionText-to-video modelsDream MachineRunway GenHailuo AIKlingSoraSeedanceVeoMusic generationRiffusionSunoUdioWorld modelsGenieOasis | Text | List of large language modelsProject DebaterIBM WatsonIBM Watsonx | Decisional | AlphaGoAlphaZeroOpenAI FiveSelf-driving carMuZeroAction selectionAutoGPTRobot control | Reasoning systems | Deductive classifiersExpert systemsInference enginesKnowledge-based systemsLogic programsProcedural reasoning systemsSemantic reasonersRule-based systems | Cognitive architectures | ACT-RSoarCLARIONLIDAOpenCog | Knowledge bases | ConceptNetWikidataDBpediaYAGO |
| Audio–visual | AlexNetWaveNetHuman image synthesisHWROCRComputer visionSpeech synthesis15.aiElevenLabsSpeech recognitionWhisperFacial recognitionAlphaFoldText-to-image modelsAuroraDALL-EFireflyFluxGPT ImageIdeogramImagenMidjourneyRecraftStable DiffusionText-to-video modelsDream MachineRunway GenHailuo AIKlingSoraSeedanceVeoMusic generationRiffusionSunoUdioWorld modelsGenieOasis |
| Text | List of large language modelsProject DebaterIBM WatsonIBM Watsonx |
| Decisional | AlphaGoAlphaZeroOpenAI FiveSelf-driving carMuZeroAction selectionAutoGPTRobot control |
| Reasoning systems | Deductive classifiersExpert systemsInference enginesKnowledge-based systemsLogic programsProcedural reasoning systemsSemantic reasonersRule-based systems |
| Cognitive architectures | ACT-RSoarCLARIONLIDAOpenCog |
| Knowledge bases | ConceptNetWikidataDBpediaYAGO |
| People | Alan TuringWarren Sturgis McCullochWalter PittsJohn von NeumannChristopher D. ManningClaude ShannonShun'ichi AmariKunihiko FukushimaTakeo KanadeMarvin MinskyJohn McCarthyNathaniel RochesterAllen NewellCliff ShawHerbert A. SimonOliver SelfridgeFrank RosenblattBernard WidrowJoseph WeizenbaumSeymour PapertSeppo LinnainmaaPaul WerbosGeoffrey HintonJohn HopfieldJürgen SchmidhuberYann LeCunYoshua BengioLotfi A. ZadehStephen GrossbergAlex GravesJames GoodnightAndrew NgFei-Fei LiAlex KrizhevskyIlya SutskeverOriol VinyalsQuoc V. LeIan GoodfellowDemis HassabisDavid SilverAndrej KarpathyAshish VaswaniNoam ShazeerAidan GomezJohn SchulmanMustafa SuleymanJan LeikeDaniel KokotajloFrançois Chollet |
| Neural network architectures | Neural Turing machineDifferentiable neural computerTransformerVision transformer (ViT)Recurrent neural network (RNN)Long short-term memory (LSTM)Gated recurrent unit (GRU)Echo state networkMultilayer perceptron (MLP)Convolutional neural network (CNN)Residual neural network (RNN)Highway networkMambaAutoencoderVariational autoencoder (VAE)Generative adversarial network (GAN)Graph neural network (GNN) |
| Political | AI Cold WarAI safety(Alignment)AI takeoverElectionsEthics of AIEUAI ActNationalismPrecautionary principleRegulation of AIUSVirtual politicianPropaganda |
| Social and economic | AI boomAI bubbleAI data centerAI effectAI literacyAI slopAI veganismAI winterAnthropomorphismArms raceCompetitionEnvironmental impactExplainable AIGenerative engine optimizationIn architectureIn educationIn fictionIn healthcareChatbot psychosisIn marketingIn video gamesIn visual artMilitary applicationsAI warfareWorkplace impact |
| Category |

 
| Authority control databases | GND |
| --- | --- |