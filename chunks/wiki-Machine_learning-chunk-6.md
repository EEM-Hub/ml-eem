---
source: sources/wiki-Machine_learning.md
source_url: https://en.wikipedia.org/wiki/Machine_learning
chunk: 6/8
---

## Ethics

 This section is an excerpt from [Ethics of artificial intelligence](./Ethics_of_artificial_intelligence).[[edit](https://en.wikipedia.org/w/index.php?title=Ethics_of_artificial_intelligence&action=edit)] 

The [ethics](./Ethics) of [artificial intelligence](./Artificial_intelligence) covers a broad range of topics within AI that are considered to have particular ethical stakes.[[165]](./Machine_learning#cite_note-Ethics_of_artificial_intelligence_Muller-2020-165) This includes [algorithmic biases](./Algorithmic_bias), [fairness](./Fairness_(machine_learning)), [accountability](./Accountability), transparency, privacy, and [regulation](./Regulation_of_artificial_intelligence), particularly where systems influence or automate human decision-making. It also covers various emerging or potential future challenges such as [machine ethics](./Machine_ethics) (how to make machines that behave ethically), [lethal autonomous weapon systems](./Lethal_autonomous_weapon), [arms race](./Artificial_intelligence_arms_race) dynamics, [AI safety](./AI_safety) and [alignment](./AI_alignment), [technological unemployment](./Technological_unemployment), AI-enabled [misinformation](./Misinformation),[[166]](./Machine_learning#cite_note-Ethics_of_artificial_intelligence_:4-166) how to treat certain AI systems if they have a [moral status](./Moral_status) (AI welfare and rights), [artificial superintelligence](./Artificial_superintelligence) and [existential risks](./Existential_risk_from_artificial_general_intelligence).[[165]](./Machine_learning#cite_note-Ethics_of_artificial_intelligence_Muller-2020-165)

 

Some application areas may also have particularly important ethical implications, like [healthcare](./Artificial_intelligence_in_healthcare), education, criminal justice, or the military.

   

### Bias

 Main article: [Algorithmic bias](./Algorithmic_bias) 

Different machine learning approaches can suffer from different data biases. A machine learning system trained specifically on current customers may not be able to predict the needs of new customer groups that are not represented in the training data. When trained on human-made data, machine learning is likely to pick up the constitutional and unconscious biases already present in society.[[167]](./Machine_learning#cite_note-Garcia-2016-167)

 

Systems that are trained on datasets collected with biases may exhibit these biases upon use (algorithmic bias), thus digitising cultural prejudices.[[168]](./Machine_learning#cite_note-168) For example, in 1988, the UK's [Commission for Racial Equality](./Commission_for_Racial_Equality) found that [St. George's Medical School](./St_George's,_University_of_London) had been using a computer program trained from data of previous admissions staff and this program had denied nearly 60 candidates who were found to either be women or have non-European-sounding names.[[167]](./Machine_learning#cite_note-Garcia-2016-167) Using job hiring data from a firm with racist hiring policies may lead to a machine learning system duplicating the bias by scoring job applicants by similarity to previous successful applicants.[[169]](./Machine_learning#cite_note-Edionwe_Outline-169)[[170]](./Machine_learning#cite_note-Jeffries_Outline-170) Another example includes predictive policing company [Geolitica](./Geolitica)'s predictive algorithm that resulted in "disproportionately high levels of over-policing in low-income and minority communities" after being trained with historical crime data.[[171]](./Machine_learning#cite_note-Silva-2018-171)

 

While responsible [collection of data](./Data_collection) and documentation of algorithmic rules used by a system is considered a critical part of machine learning, some researchers blame the lack of participation and representation of minority populations in the field of AI for machine learning's vulnerability to biases.[[172]](./Machine_learning#cite_note-172) In fact, according to research carried out by the Computing Research Association in 2021, "female faculty make up just 16.1%" of all faculty members who focus on AI among several universities around the world.[[173]](./Machine_learning#cite_note-Zhang-173) Furthermore, among the group of "new U.S. resident AI PhD graduates," 45% identified as white, 22.4% as Asian, 3.2% as Hispanic, and 2.4% as African American, which further demonstrates a lack of diversity in the field of AI.[[173]](./Machine_learning#cite_note-Zhang-173)

 

Language models learned from data have been shown to contain human-like biases.[[174]](./Machine_learning#cite_note-174)[[175]](./Machine_learning#cite_note-175) Because human languages contain biases, machines trained on language *[corpora](./Text_corpus)* will necessarily also learn these biases.[[176]](./Machine_learning#cite_note-176)[[177]](./Machine_learning#cite_note-177) In 2016, Microsoft tested [Tay](./Tay_(chatbot)), a [chatbot](./Chatbot) that learned from Twitter, and it quickly picked up racist and sexist language.[[178]](./Machine_learning#cite_note-178)

 

In an experiment carried out by [ProPublica](./ProPublica), an [investigative journalism](./Investigative_journalism) organisation, a machine learning algorithm's insight into the recidivism rates among prisoners falsely flagged "black defendants high risk twice as often as white defendants".[[171]](./Machine_learning#cite_note-Silva-2018-171) In 2015, Google Photos once tagged a couple of black people as gorillas, which caused controversy. The gorilla label was subsequently removed, and in 2023, it still cannot recognise gorillas.[[179]](./Machine_learning#cite_note-179) Similar issues with recognising non-white people have been found in many other systems.[[180]](./Machine_learning#cite_note-180)

 

Because of such challenges, the effective use of machine learning may take longer to be adopted in other domains.[[181]](./Machine_learning#cite_note-181) Concern for [fairness](./Fairness_(machine_learning)) in machine learning, that is, reducing bias in machine learning and propelling its use for human good, is increasingly expressed by artificial intelligence scientists, including [Fei-Fei Li](./Fei-Fei_Li), who said that "[t]here's nothing artificial about AI. It's inspired by people, it's created by people, and—most importantly—it impacts people. It is a powerful tool we are only just beginning to understand, and that is a profound responsibility."[[182]](./Machine_learning#cite_note-182)

 

### Financial incentives

 

There are concerns among health care professionals that these systems might not be designed in the public's interest but as income-generating machines. This is especially true in the United States, where there is a long-standing ethical dilemma of improving health care, but also increasing profits. For example, the algorithms could be designed to provide patients with unnecessary tests or medication in which the algorithm's proprietary owners hold stakes. There is potential for machine learning in health care to provide professionals with an additional tool to diagnose, medicate, and plan recovery paths for patients, but this requires these biases to be mitigated.[[183]](./Machine_learning#cite_note-183)

 

## Hardware

 

Since the 2010s, advances in both machine learning algorithms and computer hardware have led to more efficient methods for training [deep neural networks](./Deep_neural_network) (a particular narrow subdomain of machine learning) that contain many layers of nonlinear hidden units.[[184]](./Machine_learning#cite_note-184) By 2019, graphics processing units ([GPUs](./GPU)), often with AI-specific enhancements, had displaced CPUs as the dominant method of training large-scale commercial cloud AI.[[185]](./Machine_learning#cite_note-185) [OpenAI](./OpenAI) estimated the hardware compute used in the largest deep learning projects from [AlexNet](./AlexNet) (2012) to [AlphaZero](./AlphaZero) (2017), and found a 300,000-fold increase in the amount of compute required, with a doubling-time trendline of 3.4 months.[[186]](./Machine_learning#cite_note-186)[[187]](./Machine_learning#cite_note-187)

 

### Tensor Processing Units (TPUs)

 

[Tensor Processing Units (TPUs)](./Tensor_Processing_Unit) are specialised hardware accelerators developed by [Google](./Google) specifically for machine learning workloads. Unlike general-purpose [GPUs](./Graphics_processing_unit) and [FPGAs](./Field-programmable_gate_array), TPUs are optimised for tensor computations, making them particularly efficient for deep learning tasks such as training and inference. They are widely used in Google Cloud AI services and large-scale machine learning models like Google's DeepMind AlphaFold and large language models. TPUs leverage [matrix multiplication](./Computational_complexity_of_matrix_multiplication) units and high-bandwidth memory to accelerate computations while maintaining energy efficiency.[[188]](./Machine_learning#cite_note-188) Since their introduction in 2016, TPUs have become a key component of AI infrastructure, especially in cloud-based environments.

 

### Neuromorphic computing

 

[Neuromorphic computing](./Neuromorphic_computing) refers to a class of computing systems designed to emulate the structure and functionality of biological neural networks. These systems may be implemented through software-based simulations on conventional hardware or through specialised hardware architectures.[[189]](./Machine_learning#cite_note-189)

 

#### Physical neural networks

 

A [physical neural network](./Physical_neural_network) is a specific type of neuromorphic hardware that relies on electrically adjustable materials, such as memristors, to emulate the function of [neural synapses](./Chemical_synapse). The term "physical neural network" highlights the use of physical hardware for computation, as opposed to software-based implementations. It broadly refers to artificial neural networks that use materials with adjustable resistance to replicate neural synapses.[[190]](./Machine_learning#cite_note-190)[[191]](./Machine_learning#cite_note-191)

 

### Embedded machine learning

 

Embedded machine learning is a sub-field of machine learning where models are deployed on [embedded systems](./Embedded_systems) with limited computing resources, such as [wearable computers](./Wearable_computer), [edge devices](./Edge_device) and [microcontrollers](./Microcontrollers).[[192]](./Machine_learning#cite_note-192)[[193]](./Machine_learning#cite_note-193)[[194]](./Machine_learning#cite_note-194)[[195]](./Machine_learning#cite_note-195) Running models directly on these devices eliminates the need to transfer and store data on cloud servers for further processing, thereby reducing the risk of data breaches, privacy leaks and theft of intellectual property, personal data and business secrets. Embedded machine learning can be achieved through various techniques, such as [hardware acceleration](./Hardware_acceleration),[[196]](./Machine_learning#cite_note-196)[[197]](./Machine_learning#cite_note-197) [approximate computing](./Approximate_computing),[[198]](./Machine_learning#cite_note-198) and model optimization.[[199]](./Machine_learning#cite_note-199)[[200]](./Machine_learning#cite_note-200) Common optimization techniques include [pruning](./Pruning_(artificial_neural_network)), [quantisation](./Model_compression#Quantization), [knowledge distillation](./Knowledge_distillation), low-rank factorisation, network architecture search, and parameter sharing.

 

## Software

 See also: [Comparison of machine learning software](./Comparison_of_machine_learning_software) 

### Free and open-source software

 See also: [Lists of open-source artificial intelligence software](./Lists_of_open-source_artificial_intelligence_software)  
- [Mahout](./Apache_Mahout)
- [Apache OpenNLP](./Apache_OpenNLP)
- [Apache SINGA](./Apache_SINGA)
- [Spark MLlib](./Apache_Spark#MLlib_Machine_Learning_Library)
- [Apache SystemDS](./Apache_SystemDS)
- [Caffe](./Caffe_(software))
- [CatBoost](./CatBoost)
- [Deeplearning4j](./Deeplearning4j)
- [DeepSpeed](./DeepSpeed)
- [Dlib](./Dlib)
- [ELKI](./ELKI)
- [Flux.jl](./Flux.jl)
- [Gensim](./Gensim)
- [Google JAX](./Google_JAX)
- [H2O](./H2O_(software))
- [Infer.NET](./Infer.NET)
- [JASP](./JASP)
- [Jubatus](./Jubatus)
- [Keras](./Keras)
- [Kubeflow](./Kubeflow)
- [LIBSVM](./LIBSVM)
- [LightGBM](./LightGBM)
- [Mallet](./Mallet_(software_project))
- [Microsoft Cognitive Toolkit](./Microsoft_Cognitive_Toolkit)
- [MindSpore](./MindSpore)
- [ML.NET](./ML.NET)
- [mlpack](./Mlpack)
- [MXNet](./MXNet)
- [OpenNN](./OpenNN)
- [Orange](./Orange_(software))
- [ROOT](./ROOT) (TMVA with ROOT)
- [scikit-learn](./Scikit-learn)
- [Shogun](./Shogun_(toolbox))
- [TensorFlow](./TensorFlow)
- [Theano](./Theano_(software))
- [Torch](./Torch_(machine_learning)) / [PyTorch](./PyTorch) / [PyTorch Lightning](./PyTorch_Lightning)
- [Vowpal Wabbit](./Vowpal_Wabbit)
- [Weka](./Weka_(machine_learning)) / [MOA](./MOA_(Massive_Online_Analysis))
- [XGBoost](./XGBoost)
- [Yooreeka](./Yooreeka)

  

### Proprietary software with free and open-source editions

 
- [KNIME](./KNIME)
- [RapidMiner](./RapidMiner)

 

### Proprietary software

  
- [Amazon Machine Learning](./Amazon_Machine_Learning)
- [Angoss](./Angoss) KnowledgeSTUDIO
- [Azure Machine Learning](./Azure_Machine_Learning)
- [IBM Watson Studio](./IBM_Watson_Studio)
- [Google Cloud Vertex AI](./Google_Cloud_Platform#Cloud_AI)
- [Google Prediction API](./Google_APIs)
- [IBM SPSS Modeller](./SPSS_Modeler)
- [KXEN Modeller](./KXEN_Inc.)
- [LIONsolver](./LIONsolver)
- [Mathematica](./Mathematica)
- [MATLAB](./MATLAB)
- [Neural Designer](./Neural_Designer)
- [NeuroSolutions](./NeuroSolutions)
- [Oracle Data Mining](./Oracle_Data_Mining)
- [Oracle AI Platform Cloud Service](./Oracle_Cloud#Infrastructure_as_a_Service_(IaaS)_and_Platform_as_a_Service_(PaaS))
- [PolyAnalyst](./PolyAnalyst)
- [RCASE](./RCASE)
- [SAS Enterprise Miner](./SAS_(software)#Components)
- [SequenceL](./SequenceL)
- [Splunk](./Splunk)
- [STATISTICA](./STATISTICA) Data Miner

  

## Journals

 
- [Journal of Machine Learning Research](./Journal_of_Machine_Learning_Research)
- [Machine Learning](./Machine_Learning_(journal))
- [Nature Machine Intelligence](./Nature_Machine_Intelligence)
- [Neural Computation](./Neural_Computation_(journal))
- [IEEE Transactions on Pattern Analysis and Machine Intelligence](./IEEE_Transactions_on_Pattern_Analysis_and_Machine_Intelligence)

 

## Conferences

 
- [AAAI Conference on Artificial Intelligence](./AAAI_Conference_on_Artificial_Intelligence)
- [Association for Computational Linguistics (**ACL**)](./Association_for_Computational_Linguistics)
- [European Conference on Machine Learning and Principles and Practice of Knowledge Discovery in Databases (**ECML PKDD**)](./European_Conference_on_Machine_Learning_and_Principles_and_Practice_of_Knowledge_Discovery_in_Databases)
- [International Conference on Computational Intelligence Methods for Bioinformatics and Biostatistics (**CIBB**)](./International_Conference_on_Computational_Intelligence_Methods_for_Bioinformatics_and_Biostatistics)
- [International Conference on Machine Learning (**ICML**)](./International_Conference_on_Machine_Learning)
- [International Conference on Learning Representations (**ICLR**)](./International_Conference_on_Learning_Representations)
- [International Conference on Intelligent Robots and Systems (**IROS**)](./International_Conference_on_Intelligent_Robots_and_Systems)
- [Conference on Knowledge Discovery and Data Mining (**KDD**)](./Conference_on_Knowledge_Discovery_and_Data_Mining)
- [Conference on Neural Information Processing Systems (**NeurIPS**)](./Conference_on_Neural_Information_Processing_Systems)

 

## See also

 
- [Automated machine learning](./Automated_machine_learning) – Process of automating the application of machine learning
- [Big data](./Big_data) – Extremely large or complex datasets
- [Deep learning](./Deep_learning) — branch of ML concerned with [artificial neural networks](./Artificial_neural_network)
- [Differentiable programming](./Differentiable_programming) – Programming paradigm
- [Google Colab](./Google_Colab) – no setup [online IDE](./Online_integrated_development_environment) for machine learning in [Python](./List_of_Python_software#Machine_learning_and_deep_learning) and [Julia](./List_of_Julia_software_and_tools#Machine_learning_and_artificial_intelligence)
- [List of datasets for machine-learning research](./List_of_datasets_for_machine-learning_research)
- [List of machine learning algorithms](./Outline_of_machine_learning#Machine_learning_algorithms) and [List of algorithms for machine learning and statistical classification](./List_of_algorithms#Machine_learning_and_statistical_classification)
- [M-theory (learning framework)](./M-theory_(learning_framework)) – Framework in machine learning
- [Machine unlearning](./Machine_unlearning) – Field of study in artificial intelligence
- [Outline of machine learning](./Outline_of_machine_learning)
- [Solomonoff's theory of inductive inference](./Solomonoff's_theory_of_inductive_inference) – Mathematical theory
- [TinyML](./TinyML) — Machine learning on low-power [embedded systems](./Embedded_system)

 


