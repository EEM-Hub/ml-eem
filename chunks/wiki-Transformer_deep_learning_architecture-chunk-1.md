---
source: sources/wiki-Transformer_deep_learning_architecture.md
source_url: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)
chunk: 1/8
---

Algorithm for modelling sequential data 
|  | This article has multiple issues.Please helpimprove itor discuss these issues on thetalk page.(Learn how and when to remove these messages)This articleneeds additional citations forverification.Please helpimprove this articlebyadding citations to reliable sources. Unsourced material may be challenged and removed.Find sources:"Transformer"deep learning–news·newspapers·books·scholar·JSTOR(June 2026)(Learn how and when to remove this message)Some of this article'slisted sourcesmay not bereliable.Please help improve this article by looking for better, more reliable sources. Unreliable citations may be challenged and removed.(June 2026)(Learn how and when to remove this message)(Learn how and when to remove this message) |  | This articleneeds additional citations forverification.Please helpimprove this articlebyadding citations to reliable sources. Unsourced material may be challenged and removed.Find sources:"Transformer"deep learning–news·newspapers·books·scholar·JSTOR(June 2026)(Learn how and when to remove this message) |  | Some of this article'slisted sourcesmay not bereliable.Please help improve this article by looking for better, more reliable sources. Unreliable citations may be challenged and removed.(June 2026)(Learn how and when to remove this message) |
| --- | --- | --- | --- | --- | --- |
|  | This articleneeds additional citations forverification.Please helpimprove this articlebyadding citations to reliable sources. Unsourced material may be challenged and removed.Find sources:"Transformer"deep learning–news·newspapers·books·scholar·JSTOR(June 2026)(Learn how and when to remove this message) |
|  | Some of this article'slisted sourcesmay not bereliable.Please help improve this article by looking for better, more reliable sources. Unreliable citations may be challenged and removed.(June 2026)(Learn how and when to remove this message) |

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/3/34/Transformer%2C_full_architecture.png/250px-Transformer%2C_full_architecture.png)](./File:Transformer,_full_architecture.png)A standard transformer architecture, showing on the left an encoder, and on the right a decoder. Note: it uses the pre-LN convention, which is different from the post-LN convention used in the original 2017 transformer. 
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

 

In [deep learning](./Deep_learning), the **transformer** is a family of [artificial neural network](./Artificial_neural_network) architectures based on the multi-head [attention](./Attention_(machine_learning)) mechanism, in which text is converted to numerical representations called [tokens](./Large_language_model#Tokenization), and each token is converted into a vector via lookup from a [word embedding](./Word_embedding) table.[[1]](./Transformer_(deep_learning)#cite_note-2017_Attention_Is_All_You_Need-1) At each layer, each [token](./Tokenization_(lexical_analysis)) is then [contextualized](./Contextualization_(computer_science)) within the scope of the [context window](./Context_window) with other (unmasked) tokens via a parallel multi-head attention mechanism, allowing the signal for key tokens to be amplified and less important tokens to be diminished. Because self-attention alone is permutation-invariant, transformers inject positional information, typically through positional encodings or learned positional embeddings, so token order can affect the output.[[2]](./Transformer_(deep_learning)#cite_note-2)

 

Transformers have the advantage of having no recurrent units, therefore requiring less training time than earlier [recurrent neural architectures](./Recurrent_neural_network) (RNNs) such as [long short-term memory](./Long_short-term_memory) (LSTM).[[3]](./Transformer_(deep_learning)#cite_note-lstm1997-3) Later variations have been widely adopted for training [large language models](./Large_language_model) (LLMs) on large (language) [datasets](./Training,_validation,_and_test_data_sets).[[4]](./Transformer_(deep_learning)#cite_note-:7-4) Modern transformer designs are commonly grouped into encoder-only, decoder-only, and encoder-decoder variants, depending on whether they are optimized for representation learning, autoregressive generation, or conditional sequence-to-sequence tasks.[[5]](./Transformer_(deep_learning)#cite_note-5)

The original version of the transformer architecture was proposed in the 2017 paper "[Attention Is All You Need](./Attention_Is_All_You_Need)" by researchers at [Google](./Google).[[1]](./Transformer_(deep_learning)#cite_note-2017_Attention_Is_All_You_Need-1) The predecessors of transformers were developed as an improvement over previous architectures for [machine translation](./Machine_translation),[[6]](./Transformer_(deep_learning)#cite_note-inventors-6)[[7]](./Transformer_(deep_learning)#cite_note-inventconfirm-7) but have found many applications since. They are used in large-scale [natural language processing](./Natural_language_processing), [computer vision](./Computer_vision) ([vision transformers](./Vision_transformer)), [reinforcement learning](./Reinforcement_learning),[[8]](./Transformer_(deep_learning)#cite_note-:10-8)[[9]](./Transformer_(deep_learning)#cite_note-9) [audio](./Audio_signal_processing),[[10]](./Transformer_(deep_learning)#cite_note-Robust_Speech_Recognition_via_Large-Scale_Weak_Supervision-10) [multimodal learning](./Multimodal_learning), [robotics](./Robotics),[[11]](./Transformer_(deep_learning)#cite_note-11), playing [chess](./Computer_chess)[[12]](./Transformer_(deep_learning)#cite_note-grandmaster-12) and at [disaster responses](./Disaster_response)[[13]](./Transformer_(deep_learning)#cite_note-disaster-13). It has also led to the development of [pre-trained systems](./Transfer_learning), such as [generative pre-trained transformers](./Generative_pre-trained_transformer) (GPTs)[[14]](./Transformer_(deep_learning)#cite_note-wolf2020-14) and [BERT](./BERT_(language_model))[[15]](./Transformer_(deep_learning)#cite_note-:6-15) (bidirectional encoder representations from transformers).

 


