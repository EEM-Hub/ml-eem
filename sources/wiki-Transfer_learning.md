---
source: https://en.wikipedia.org/wiki/Transfer_learning
fetched: 2026-06-21
---

Machine learning technique Not to be confused with [Transfer of learning](./Transfer_of_learning) or [knowledge transfer](./Knowledge_transfer). [![](//upload.wikimedia.org/wikipedia/commons/thumb/6/6f/Transfer_learning.svg/250px-Transfer_learning.svg.png)](./File:Transfer_learning.svg)Illustration of transfer learning 
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

 

**Transfer learning** (**TL**) is a technique in [machine learning](./Machine_learning) (ML) in which knowledge learned from a task is re-used in order to boost performance on a related task.[[1]](./Transfer_learning#cite_note-1) For example, for [image classification](./Computer_vision), knowledge gained while learning to [recognize](./Computer_vision#Recognition) cars could be applied when trying to recognize trucks. This topic is related to the psychological literature on [transfer of learning](./Transfer_of_learning), although practical ties between the two fields are limited. Reusing or transferring information from previously learned tasks to new tasks has the potential to significantly improve learning efficiency.[[2]](./Transfer_learning#cite_note-2)

 

Since transfer learning makes use of training with multiple objective functions it is related to [cost-sensitive machine learning](./Cost-sensitive_machine_learning) and [multi-objective optimization](./Multi-objective_optimization).[[3]](./Transfer_learning#cite_note-3)

 

## History

 Potential overusage of publications by Lorien Pratt, maybe by COI editor. Not a balanced view on the history of this topic, needs a broader range of sources. (see https://en.wikipedia.org/w/index.php?title=Transfer_learning&#x26;diff=684692020&#x26;oldid=646958283) 

In 1976, Bozinovski and Fulgosi published a paper addressing transfer learning in [neural network](./Neural_network) training.[[4]](./Transfer_learning#cite_note-4)[[5]](./Transfer_learning#cite_note-5) The paper gives a mathematical and geometrical model of the topic. In 1981, a report considered the application of transfer learning to a dataset of images representing letters of computer terminals, experimentally demonstrating positive and negative transfer learning.[[6]](./Transfer_learning#cite_note-6)

 

In 1992, [Lorien Pratt](./Lorien_Pratt) formulated the discriminability-based transfer (DBT) algorithm.[[7]](./Transfer_learning#cite_note-7)

 

By 1998, the field had advanced to include [multi-task learning](./Multi-task_learning),[[8]](./Transfer_learning#cite_note-8) along with more formal theoretical foundations.[[9]](./Transfer_learning#cite_note-9) Influential publications on transfer learning include the book *Learning to Learn* in 1998,[[10]](./Transfer_learning#cite_note-FOOTNOTEThrunPratt2012-10) a 2009 survey[[11]](./Transfer_learning#cite_note-11) and a 2019 survey.[[12]](./Transfer_learning#cite_note-12)

 

[Ng](./Andrew_Ng) said in his NIPS 2016 tutorial[[13]](./Transfer_learning#cite_note-13)[[14]](./Transfer_learning#cite_note-14) that TL would become the next driver of [machine learning](./Machine_learning) commercial success after [supervised learning](./Supervised_learning).

 

In the 2020 paper, "Rethinking Pre-Training and self-training",[[15]](./Transfer_learning#cite_note-15) Zoph et al. reported that pre-training can hurt accuracy, and advocate self-training instead.

 

## Definition

 

The definition of transfer learning is given in terms of domains and tasks. A domain       D     {\displaystyle {\mathcal {D}}}  ![{\displaystyle {\mathcal {D}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3277962e1959c3241fb1b70c7f0ac6dcefebd966) consists of: a [feature space](./Feature_space)       X     {\displaystyle {\mathcal {X}}}  ![{\displaystyle {\mathcal {X}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8c7e5461c5286852df4ef652fca7e4b0b63030e9) and a [marginal probability distribution](./Marginal_probability_distribution)     P ( X )   {\displaystyle P(X)}  ![{\displaystyle P(X)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/bf94167ebc67db1573e6be9e261cd0518e49e160), where     X = {  x  1   , . . . ,  x  n   } ∈ ∈    X     {\displaystyle X=\{x_{1},...,x_{n}\}\in {\mathcal {X}}}  ![{\displaystyle X=\{x_{1},...,x_{n}\}\in {\mathcal {X}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f366e8a442318d54e0a28b94f25e2756293014e4). Given a specific domain,       D   = {   X   , P ( X ) }   {\displaystyle {\mathcal {D}}=\{{\mathcal {X}},P(X)\}}  ![{\displaystyle {\mathcal {D}}=\{{\mathcal {X}},P(X)\}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/62b90afd89582dbf0e6672baa0708912628f9958), a task consists of two components: a label space       Y     {\displaystyle {\mathcal {Y}}}  ![{\displaystyle {\mathcal {Y}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8935ef8cf454efa0b58363386c33f16a48ec36ca) and an objective predictive function     f :   X   → →    Y     {\displaystyle f:{\mathcal {X}}\rightarrow {\mathcal {Y}}}  ![{\displaystyle f:{\mathcal {X}}\rightarrow {\mathcal {Y}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/24d657a1f4e3818257adc8c92ba313329ca7c4d1). The function     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) is used to predict the corresponding label     f ( x )   {\displaystyle f(x)}  ![{\displaystyle f(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/202945cce41ecebb6f643f31d119c514bec7a074) of a new instance     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4). This task, denoted by       T   = {   Y   , f ( x ) }   {\displaystyle {\mathcal {T}}=\{{\mathcal {Y}},f(x)\}}  ![{\displaystyle {\mathcal {T}}=\{{\mathcal {Y}},f(x)\}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/28815172a512bcdbb9f8184d63515a7bc4822fc5), is learned from the training data consisting of pairs     {  x  i   ,  y  i   }   {\displaystyle \{x_{i},y_{i}\}}  ![{\displaystyle \{x_{i},y_{i}\}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3c5044f20cfba071b7d4e92dc651c2b39ac0207b), where      x  i   ∈ ∈    X     {\displaystyle x_{i}\in {\mathcal {X}}}  ![{\displaystyle x_{i}\in {\mathcal {X}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/09d1f60c993f578ec3d8c08e521b87931d0feac8) and      y  i   ∈ ∈    Y     {\displaystyle y_{i}\in {\mathcal {Y}}}  ![{\displaystyle y_{i}\in {\mathcal {Y}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a7ab4d7fbffa36a1428d869b75f25508da3997e1).[[16]](./Transfer_learning#cite_note-Lin,_Jung_2017-16)

 

Given a source domain        D    S     {\displaystyle {\mathcal {D}}_{S}}  ![{\displaystyle {\mathcal {D}}_{S}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/73b93b620f34fe7db50f7f7525417ae5534d9b65) and learning task        T    S     {\displaystyle {\mathcal {T}}_{S}}  ![{\displaystyle {\mathcal {T}}_{S}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fd1420bea4f3d0b24470564614856f43f0f4b2a3), a target domain        D    T     {\displaystyle {\mathcal {D}}_{T}}  ![{\displaystyle {\mathcal {D}}_{T}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/13423a952f04fe320974a72ba018efc6c4e867e8) and learning task        T    T     {\displaystyle {\mathcal {T}}_{T}}  ![{\displaystyle {\mathcal {T}}_{T}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/27876915db93885f6db8689624b9dcfe88b2f3a0), where        D    S   ≠ ≠     D    T     {\displaystyle {\mathcal {D}}_{S}\neq {\mathcal {D}}_{T}}  ![{\displaystyle {\mathcal {D}}_{S}\neq {\mathcal {D}}_{T}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4bf039e3293649209545fe31ae5d6098aacbbd2a), or        T    S   ≠ ≠     T    T     {\displaystyle {\mathcal {T}}_{S}\neq {\mathcal {T}}_{T}}  ![{\displaystyle {\mathcal {T}}_{S}\neq {\mathcal {T}}_{T}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8b782c4e0cbf99cc00f83cac1148f4b7384f02de), transfer learning aims to help improve the learning of the target predictive function      f  T   ( ⋅ ⋅  )   {\displaystyle f_{T}(\cdot )}  ![{\displaystyle f_{T}(\cdot )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0af4f92ff9d7d2a44bc4dca321b8ccd5f0f806eb) in        D    T     {\displaystyle {\mathcal {D}}_{T}}  ![{\displaystyle {\mathcal {D}}_{T}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/13423a952f04fe320974a72ba018efc6c4e867e8) using the knowledge in        D    S     {\displaystyle {\mathcal {D}}_{S}}  ![{\displaystyle {\mathcal {D}}_{S}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/73b93b620f34fe7db50f7f7525417ae5534d9b65) and        T    S     {\displaystyle {\mathcal {T}}_{S}}  ![{\displaystyle {\mathcal {T}}_{S}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fd1420bea4f3d0b24470564614856f43f0f4b2a3).[[16]](./Transfer_learning#cite_note-Lin,_Jung_2017-16)

 

## Applications

 

Algorithms for transfer learning are available in [Markov logic networks](./Markov_logic_network)[[17]](./Transfer_learning#cite_note-17) and [Bayesian networks](./Bayesian_networks).[[18]](./Transfer_learning#cite_note-18) Transfer learning has been applied to cancer subtype discovery,[[19]](./Transfer_learning#cite_note-:bmdl-19) building utilization,[[20]](./Transfer_learning#cite_note-20)[[21]](./Transfer_learning#cite_note-21) [general game playing](./General_game_playing),[[22]](./Transfer_learning#cite_note-22) [text classification](./Document_classification),[[23]](./Transfer_learning#cite_note-23)[[24]](./Transfer_learning#cite_note-24) digit recognition,[[25]](./Transfer_learning#cite_note-25) medical imaging and [spam filtering](./E-mail_filtering).[[26]](./Transfer_learning#cite_note-26)

 

In 2020, it was discovered that, due to their similar physical natures, transfer learning is possible between [electromyographic](./Electromyographic) (EMG) signals from the muscles and classifying the behaviors of [electroencephalographic](./Electroencephalographic) (EEG) brainwaves, from the [gesture recognition](./Gesture_recognition) domain to the mental state recognition domain. It was noted that this relationship worked in both directions, showing that EEG brainwaves can likewise be used to classify EMG signals.[[27]](./Transfer_learning#cite_note-27) The experiments noted that the accuracy of [neural networks](./Artificial_neural_network) and [convolutional neural networks](./Convolutional_neural_network) were improved[[28]](./Transfer_learning#cite_note-28) through transfer learning both prior to any learning (compared to standard random weight distribution) and at the end of the learning process (asymptote). That is, results are improved by exposure to another domain. Moreover, the end-user of a pre-trained model can change the structure of fully-connected layers to improve performance.[[29]](./Transfer_learning#cite_note-29)

 

## See also

 
- [Crossover (genetic algorithm)](./Crossover_(genetic_algorithm))
- [Domain adaptation](./Domain_adaptation)
- [General game playing](./General_game_playing)
- [Multi-task learning](./Multi-task_learning)
- [Multitask optimization](./Multitask_optimization)
- [Transfer of learning](./Transfer_of_learning) in [educational psychology](./Educational_psychology)
- [Zero-shot learning](./Zero-shot_learning)
- [Feature learning](./Feature_learning)
- [external validity](./External_validity)

 

## References

  
1. [↑](./Transfer_learning#cite_ref-1) West, Jeremy; Ventura, Dan; Warnick, Sean (2007). ["Spring Research Presentation: A Theoretical Foundation for Inductive Transfer"](https://web.archive.org/web/20070801120743/http://cpms.byu.edu/springresearch/abstract-entry?id=861). Brigham Young University, College of Physical and Mathematical Sciences. Archived from [the original](http://cpms.byu.edu/springresearch/abstract-entry?id=861) on 2007-08-01. Retrieved 2007-08-05.
2. [↑](./Transfer_learning#cite_ref-2) George Karimpanal, Thommen; Bouffanais, Roland (2019). "Self-organizing maps for storage and transfer of knowledge in reinforcement learning". *Adaptive Behavior*. **27** (2): 111–126. [arXiv](./ArXiv_(identifier)):[1811.08318](https://arxiv.org/abs/1811.08318). [doi](./Doi_(identifier)):[10.1177/1059712318818568](https://doi.org/10.1177%2F1059712318818568). [ISSN](./ISSN_(identifier)) [1059-7123](https://search.worldcat.org/issn/1059-7123). [S2CID](./S2CID_(identifier)) [53774629](https://api.semanticscholar.org/CorpusID:53774629).
3. [↑](./Transfer_learning#cite_ref-3)  Cost-Sensitive Machine Learning. (2011). USA: CRC Press, Page 63, [https://books.google.com/books?id=8TrNBQAAQBAJ&pg=PA63](https://books.google.com/books?id=8TrNBQAAQBAJ&pg=PA63)
4. [↑](./Transfer_learning#cite_ref-4) Stevo. Bozinovski and Ante Fulgosi (1976). "The influence of pattern similarity and transfer learning on the base perceptron training." (original in Croatian) Proceedings of Symposium Informatica 3-121-5, Bled.
5. [↑](./Transfer_learning#cite_ref-5) Stevo Bozinovski (2020) ["Reminder of the first paper on transfer learning in neural networks, 1976"](https://www.informatica.si/index.php/informatica/article/viewFile/2828/1433). Informatica 44: 291–302.
6. [↑](./Transfer_learning#cite_ref-6) S. Bozinovski (1981). "Teaching space: A representation concept for adaptive pattern classification." COINS Technical Report, the University of Massachusetts at Amherst, No 81-28 [available [online](https://web.cs.umass.edu/publication/docs/1981/UM-CS-1981-028.pdf)]
7. [↑](./Transfer_learning#cite_ref-7) Pratt, L. Y. (1992). ["Discriminability-based transfer between neural networks"](https://proceedings.neurips.cc/paper/1992/file/67e103b0761e60683e83c559be18d40c-Paper.pdf) (PDF). [*NIPS Conference: Advances in Neural Information Processing Systems 5*](https://books.google.com/books?id=6tGHlwEACAAJ&pg=PA204). Morgan Kaufmann Publishers. pp. 204–211.
8. [↑](./Transfer_learning#cite_ref-8) Caruana, R., "Multitask Learning", pp. 95-134 in [Thrun & Pratt 2012](./Transfer_learning#CITEREFThrunPratt2012)
9. [↑](./Transfer_learning#cite_ref-9) Baxter, J., "Theoretical Models of Learning to Learn", pp. 71-95 [Thrun & Pratt 2012](./Transfer_learning#CITEREFThrunPratt2012)
10. [↑](./Transfer_learning#cite_ref-FOOTNOTEThrunPratt2012_10-0) [Thrun & Pratt 2012](./Transfer_learning#CITEREFThrunPratt2012).
11. [↑](./Transfer_learning#cite_ref-11) Pan, Sinno Jialin; Yang, Qiang (2010). ["A Survey on Transfer Learning"](https://www.cse.ust.hk/~qyang/Docs/2009/tkde_transfer_learning.pdf) (PDF). *IEEE Transactions on Knowledge and Data Engineering*. **22** (10): 1345–1359. [Bibcode](./Bibcode_(identifier)):[2010ITKDE..22.1345P](https://ui.adsabs.harvard.edu/abs/2010ITKDE..22.1345P). [doi](./Doi_(identifier)):[10.1109/TKDE.2009.191](https://doi.org/10.1109%2FTKDE.2009.191).
12. [↑](./Transfer_learning#cite_ref-12) Zhuang, Fuzhen; Qi, Zhiyuan; Duan, Keyu; Xi, Dongbo; Zhu, Yongchun; Zhu, Hengshu; Xiong, Hui; He, Qing (2019). "A Comprehensive Survey on Transfer Learning". [arXiv](./ArXiv_(identifier)):[1911.02685](https://arxiv.org/abs/1911.02685) [[cs.LG](https://arxiv.org/archive/cs.LG)].
13. [↑](./Transfer_learning#cite_ref-13) [*NIPS 2016 tutorial: "Nuts and bolts of building AI applications using Deep Learning" by Andrew Ng*](https://www.youtube.com/watch?v=wjqaz6m42wU), 6 May 2018, [archived](https://ghostarchive.org/varchive/youtube/20211219/wjqaz6m42wU) from the original on 2021-12-19, retrieved 2019-12-28
14. [↑](./Transfer_learning#cite_ref-14) ["Nuts and bolts of building AI applications using Deep Learning, slides"](https://media.nips.cc/Conferences/2016/Slides/6203-Slides.pdf) (PDF).
15. [↑](./Transfer_learning#cite_ref-15) Zoph, Barret (2020). ["Rethinking pre-training and self-training"](https://proceedings.neurips.cc/paper/2020/file/27e9661e033a73a6ad8cefcde965c54d-Paper.pdf) (PDF). *Advances in Neural Information Processing Systems*. **33**: 3833–3845. [arXiv](./ArXiv_(identifier)):[2006.06882](https://arxiv.org/abs/2006.06882). Retrieved 2022-12-20.
16. [1](./Transfer_learning#cite_ref-Lin,_Jung_2017_16-0) [2](./Transfer_learning#cite_ref-Lin,_Jung_2017_16-1) Lin, Yuan-Pin; Jung, Tzyy-Ping (27 June 2017). ["Improving EEG-Based Emotion Classification Using Conditional Transfer Learning"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5486154). *Frontiers in Human Neuroscience*. **11** 334. [doi](./Doi_(identifier)):[10.3389/fnhum.2017.00334](https://doi.org/10.3389%2Ffnhum.2017.00334). [PMC](./PMC_(identifier)) [5486154](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5486154). [PMID](./PMID_(identifier)) [28701938](https://pubmed.ncbi.nlm.nih.gov/28701938). [![](//upload.wikimedia.org/wikipedia/commons/thumb/e/e1/CC_BY_icon.svg/60px-CC_BY_icon.svg.png)](./File:CC-BY_icon.svg) Material was copied from this source, which is available under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).
17. [↑](./Transfer_learning#cite_ref-17) Mihalkova, Lilyana; Huynh, Tuyen; Mooney, Raymond J. (July 2007), ["Mapping and Revising Markov Logic Networks for Transfer"](http://www.cs.utexas.edu/users/ml/papers/mihalkova-aaai07.pdf) (PDF), *Learning Proceedings of the 22nd AAAI Conference on Artificial Intelligence (AAAI-2007)*, Vancouver, BC, pp. 608–614, retrieved 2007-08-05`{{citation}}`:  CS1 maint: location missing publisher ([link](./Category:CS1_maint:_location_missing_publisher))
18. [↑](./Transfer_learning#cite_ref-18) Niculescu-Mizil, Alexandru; Caruana, Rich (March 21–24, 2007), ["Inductive Transfer for Bayesian Network Structure Learning"](http://www.stat.umn.edu/~aistat/proceedings/data/papers/043.pdf) (PDF), *Proceedings of the Eleventh International Conference on Artificial Intelligence and Statistics (AISTATS 2007)*, retrieved 2007-08-05
19. [↑](./Transfer_learning#cite_ref-:bmdl_19-0) Hajiramezanali, E. & Dadaneh, S. Z. & Karbalayghareh, A. & Zhou, Z. & Qian, X. Bayesian multi-domain learning for cancer subtype discovery from next-generation sequencing count data. 32nd Conference on Neural Information Processing Systems (NeurIPS 2018), Montréal, Canada. [arXiv](./ArXiv_(identifier)):[1810.09433](https://arxiv.org/abs/1810.09433)
20. [↑](./Transfer_learning#cite_ref-20) Arief-Ang, I.B.; Salim, F.D.; Hamilton, M. (2017-11-08). [*DA-HOC: semi-supervised domain adaptation for room occupancy prediction using CO2 sensor data*](https://dl.acm.org/citation.cfm?id=3137146). 4th ACM International Conference on Systems for Energy-Efficient Built Environments (BuildSys). Delft, Netherlands. pp. 1–10. [doi](./Doi_(identifier)):[10.1145/3137133.3137146](https://doi.org/10.1145%2F3137133.3137146). [ISBN](./ISBN_(identifier)) [978-1-4503-5544-5](./Special:BookSources/978-1-4503-5544-5).
21. [↑](./Transfer_learning#cite_ref-21) Arief-Ang, I.B.; Hamilton, M.; Salim, F.D. (2018-12-01). "A Scalable Room Occupancy Prediction with Transferable Time Series Decomposition of CO2 Sensor Data". *ACM Transactions on Sensor Networks*. **14** (3–4): 21:1–21:28. [doi](./Doi_(identifier)):[10.1145/3217214](https://doi.org/10.1145%2F3217214). [S2CID](./S2CID_(identifier)) [54066723](https://api.semanticscholar.org/CorpusID:54066723).
22. [↑](./Transfer_learning#cite_ref-22) Banerjee, Bikramjit, and Peter Stone. "[General Game Learning Using Knowledge Transfer](http://www.aaai.org/Papers/IJCAI/2007/IJCAI07-107.pdf)." IJCAI. 2007.
23. [↑](./Transfer_learning#cite_ref-23) Do, Chuong B.; Ng, Andrew Y. (2005). "Transfer learning for text classification". [*Neural Information Processing Systems Foundation, NIPS*2005*](http://papers.nips.cc/paper/2843-transfer-learning-for-text-classification.pdf) (PDF). Retrieved 2007-08-05.
24. [↑](./Transfer_learning#cite_ref-24) Rajat, Raina; Ng, Andrew Y.; Koller, Daphne (2006). "Constructing Informative Priors using Transfer Learning". [*Twenty-third International Conference on Machine Learning*](https://ai.stanford.edu/~ang/papers/icml06-transferinformativepriors.pdf) (PDF). Retrieved 2007-08-05.
25. [↑](./Transfer_learning#cite_ref-25) Maitra, D. S.; Bhattacharya, U.; Parui, S. K. (August 2015). "CNN based common approach to handwritten character recognition of multiple scripts". *2015 13th International Conference on Document Analysis and Recognition (ICDAR)*. pp. 1021–1025. [doi](./Doi_(identifier)):[10.1109/ICDAR.2015.7333916](https://doi.org/10.1109%2FICDAR.2015.7333916). [ISBN](./ISBN_(identifier)) [978-1-4799-1805-8](./Special:BookSources/978-1-4799-1805-8). [S2CID](./S2CID_(identifier)) [25739012](https://api.semanticscholar.org/CorpusID:25739012).
26. [↑](./Transfer_learning#cite_ref-26) Bickel, Steffen (2006). "ECML-PKDD Discovery Challenge 2006 Overview". [*ECML-PKDD Discovery Challenge Workshop*](http://www.ecmlpkdd2006.org/discovery_challenge2006_overview.pdf) (PDF). Retrieved 2007-08-05.
27. [↑](./Transfer_learning#cite_ref-27) Bird, Jordan J.; Kobylarz, Jhonatan; Faria, Diego R.; Ekart, Aniko; Ribeiro, Eduardo P. (2020). ["Cross-Domain MLP and CNN Transfer Learning for Biological Signal Processing: EEG and EMG"](https://doi.org/10.1109%2Faccess.2020.2979074). *IEEE Access*. **8**. Institute of Electrical and Electronics Engineers (IEEE): 54789–54801. [Bibcode](./Bibcode_(identifier)):[2020IEEEA...854789B](https://ui.adsabs.harvard.edu/abs/2020IEEEA...854789B). [doi](./Doi_(identifier)):[10.1109/access.2020.2979074](https://doi.org/10.1109%2Faccess.2020.2979074). [ISSN](./ISSN_(identifier)) [2169-3536](https://search.worldcat.org/issn/2169-3536).
28. [↑](./Transfer_learning#cite_ref-28) Maitra, Durjoy Sen; Bhattacharya, Ujjwal; Parui, Swapan K. (August 2015). "CNN based common approach to handwritten character recognition of multiple scripts". *2015 13th International Conference on Document Analysis and Recognition (ICDAR)*. pp. 1021–1025. [doi](./Doi_(identifier)):[10.1109/ICDAR.2015.7333916](https://doi.org/10.1109%2FICDAR.2015.7333916). [ISBN](./ISBN_(identifier)) [978-1-4799-1805-8](./Special:BookSources/978-1-4799-1805-8). [S2CID](./S2CID_(identifier)) [25739012](https://api.semanticscholar.org/CorpusID:25739012).
29. [↑](./Transfer_learning#cite_ref-29) Kabir, H. M. Dipu; Abdar, Moloud; Jalali, Seyed Mohammad Jafar; Khosravi, Abbas; Atiya, Amir F.; Nahavandi, Saeid; [Srinivasan, Dipti](./Dipti_Srinivasan) (January 7, 2022). "SpinalNet: Deep Neural Network with Gradual Input". *IEEE Transactions on Artificial Intelligence*. **4** (5): 1165–1177. [arXiv](./ArXiv_(identifier)):[2007.03347](https://arxiv.org/abs/2007.03347). [doi](./Doi_(identifier)):[10.1109/TAI.2022.3185179](https://doi.org/10.1109%2FTAI.2022.3185179). [S2CID](./S2CID_(identifier)) [220381239](https://api.semanticscholar.org/CorpusID:220381239).

 

## Sources

 
- Thrun, Sebastian; Pratt, Lorien (6 December 2012). [*Learning to Learn*](https://books.google.com/books?id=X_jpBwAAQBAJ). Springer Science & Business Media. [ISBN](./ISBN_(identifier)) [978-1-4615-5529-2](./Special:BookSources/978-1-4615-5529-2).