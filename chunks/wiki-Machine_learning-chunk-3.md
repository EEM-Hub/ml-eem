---
source: sources/wiki-Machine_learning.md
source_url: https://en.wikipedia.org/wiki/Machine_learning
chunk: 3/8
---

## Approaches

 

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/4/4d/Supervised_and_unsupervised_learning.png/330px-Supervised_and_unsupervised_learning.png)](./File:Supervised_and_unsupervised_learning.png)In [supervised learning](./Supervised_learning), the training data is labelled with the expected answers, while in [unsupervised learning](./Unsupervised_learning), the model identifies patterns or structures in unlabelled data. 

Machine learning approaches are traditionally divided into three broad categories, which correspond to learning paradigms, depending on the nature of the "signal" or "feedback" available to the learning system:

 
- [Supervised learning](./Supervised_learning): The computer is presented with example inputs and their desired outputs, given by a "teacher", and the goal is to learn a general rule that [maps](./Map_(mathematics)) inputs to outputs.
- [Unsupervised learning](./Unsupervised_learning): No labels are given to the learning algorithm, leaving it on its own to find structure in its input. Unsupervised learning can be a goal in itself (discovering hidden patterns in data) or a means towards an end ([feature learning](./Feature_learning)).
- [Reinforcement learning](./Reinforcement_learning): A computer program interacts with a dynamic environment in which it must perform a certain goal (such as [driving a vehicle](./Autonomous_car) or playing a game against an opponent). As it navigates its problem space, the program is provided rewards as feedback, which it tries to maximize, thus resulting in the program learning from experience.[[2]](./Machine_learning#cite_note-bishop2006-2)

 

Although each algorithm has advantages and limitations, no single algorithm works for all problems.[[43]](./Machine_learning#cite_note-43)[[44]](./Machine_learning#cite_note-44)[[45]](./Machine_learning#cite_note-45)

 

### Supervised learning

 Main article: [Supervised learning](./Supervised_learning) [![](//upload.wikimedia.org/wikipedia/commons/thumb/2/2a/Svm_max_sep_hyperplane_with_margin.png/250px-Svm_max_sep_hyperplane_with_margin.png)](./File:Svm_max_sep_hyperplane_with_margin.png)A [support-vector machine](./Support-vector_machine) is a supervised learning model that divides the data into regions separated by a [linear boundary](./Linear_classifier). Here, the linear boundary divides the black circles from the white. 

Supervised learning algorithms build a mathematical model of a set of data that contains both the inputs and the desired outputs.[[46]](./Machine_learning#cite_note-46) The data, known as [training data](./Training_data), consists of a set of training examples. Each training example has one or more inputs and the desired output, also known as a supervisory signal. In the mathematical model, each training example is represented by an [array](./Array_data_structure) or vector, sometimes called a [feature vector](./Feature_vector), and the training data is represented by a [matrix](./Matrix_(mathematics)). Through [iterative optimisation](./Mathematical_optimization#Computational_optimization_techniques) of an [objective function](./Loss_function), supervised learning algorithms learn a function that can be used to predict the output associated with new inputs.[[47]](./Machine_learning#cite_note-47) An optimal function allows the algorithm to correctly determine the output for inputs that were not a part of the training data. An algorithm that improves the accuracy of its outputs or predictions over time is said to have learned to perform that task.[[15]](./Machine_learning#cite_note-Mitchell-1997-15)

 

Types of supervised-learning algorithms include [active learning](./Active_learning_(machine_learning)), [classification](./Statistical_classification) and [regression](./Regression_analysis).[[48]](./Machine_learning#cite_note-Alpaydin-2010-48) Classification algorithms are used when the outputs are restricted to a limited set of values, while regression algorithms are used when the outputs can take any numerical value within a range. For example, in a classification algorithm that filters emails, the input is an incoming email, and the output is the folder in which to file the email. In contrast, regression is used for tasks such as predicting a person's height based on factors like age and genetics or forecasting future temperatures based on historical data.[[49]](./Machine_learning#cite_note-49)

 

[Similarity learning](./Similarity_learning) is an area of supervised machine learning closely related to regression and classification, but the goal is to learn from examples using a similarity function that measures how similar or related two objects are. It has applications in [ranking](./Ranking), [recommendation systems](./Recommender_system), visual identity tracking, face verification, and speaker verification.

 

### Unsupervised learning

 Main article: [Unsupervised learning](./Unsupervised_learning)See also: [Cluster analysis](./Cluster_analysis) 

Unsupervised learning algorithms find structures in data that has not been labelled, classified or categorised. Instead of responding to feedback, unsupervised learning algorithms identify commonalities in the data and react based on the presence or absence of such commonalities in each new piece of data. Central applications of unsupervised machine learning include clustering, [dimensionality reduction](./Dimensionality_reduction),[[4]](./Machine_learning#cite_note-Friedman-1998-4) and [density estimation](./Density_estimation).[[50]](./Machine_learning#cite_note-JordanBishop2004-50)

 

Cluster analysis is the assignment of a set of observations into subsets (called *clusters*) so that observations within the same cluster are similar according to one or more predesignated criteria, while observations drawn from different clusters are dissimilar. Different clustering techniques make different assumptions on the structure of the data, often defined by some *similarity metric* and evaluated, for example, by *internal compactness*, or the similarity between members of the same cluster, and *separation*, the difference between clusters. Other methods are based on *estimated density* and *graph connectivity*.

 

A special type of unsupervised learning called [self-supervised learning](./Self-supervised_learning) involves training a model by generating the supervisory signal from the data itself.[[51]](./Machine_learning#cite_note-51)[[52]](./Machine_learning#cite_note-52)

 

#### Dimensionality reduction

 

[Dimensionality reduction](./Dimensionality_reduction) is a process of reducing the number of random variables under consideration by obtaining a set of principal variables.[[53]](./Machine_learning#cite_note-53) In other words, it is a process of reducing the dimension of the [feature](./Feature_(machine_learning)) set, also called the "number of features". Most of the dimensionality reduction techniques can be considered as either feature elimination or [extraction](./Feature_extraction). One of the popular methods of dimensionality reduction is [principal component analysis](./Principal_component_analysis) (PCA). PCA involves changing higher-dimensional data (e.g., 3D) to a smaller space (e.g., 2D).
The [manifold hypothesis](./Manifold_hypothesis) proposes that high-dimensional data sets lie along low-dimensional [manifolds](./Manifold), and many dimensionality reduction techniques make this assumption, leading to the areas of [manifold learning](./Manifold_learning) and [manifold regularisation](./Manifold_regularisation).

 

### Semi-supervised learning

 Main article: [Semi-supervised learning](./Semi-supervised_learning) 

Semi-supervised learning falls between [unsupervised learning](./Unsupervised_learning) (without any labelled training data) and [supervised learning](./Supervised_learning) (with completely labelled training data). Some of the training examples are missing training labels, yet many machine-learning researchers have found that unlabelled data, when used in conjunction with a small amount of labelled data, can produce a considerable improvement in learning accuracy.

 

In [weakly supervised learning](./Weak_supervision), the training labels are noisy, limited, or imprecise; however, these labels are often cheaper to obtain, resulting in larger effective training sets.[[54]](./Machine_learning#cite_note-54)

 

### Reinforcement learning

 Main article: [Reinforcement learning](./Reinforcement_learning) [![](//upload.wikimedia.org/wikipedia/commons/thumb/1/1b/Reinforcement_learning_diagram.svg/250px-Reinforcement_learning_diagram.svg.png)](./File:Reinforcement_learning_diagram.svg)In reinforcement learning, an agent takes actions in an environment: these produce a reward or a representation of the state, which is fed back to the agent. 

Reinforcement learning is an area of machine learning concerned with how [software agents](./Software_agent) ought to take [actions](./Action_selection) in an environment to maximise some notion of cumulative reward. Due to its generality, the field is studied in many other disciplines, such as [game theory](./Game_theory), [control theory](./Control_theory), [operations research](./Operations_research), [information theory](./Information_theory), [simulation-based optimisation](./Simulation-based_optimisation), [multi-agent systems](./Multi-agent_system), [swarm intelligence](./Swarm_intelligence), [statistics](./Statistics) and [genetic algorithms](./Genetic_algorithm). In reinforcement learning, the environment is typically represented as a [Markov decision process](./Markov_decision_process) (MDP). Many reinforcement learning algorithms use [dynamic programming](./Dynamic_programming) techniques.[[55]](./Machine_learning#cite_note-55) Reinforcement learning algorithms do not assume knowledge of an exact mathematical model of the MDP and are used when exact models are infeasible. Reinforcement learning algorithms are used in autonomous vehicles or in learning to play a game against a human opponent.

 

### Other types

 

Other approaches have been developed which do not fit neatly into this three-fold categorisation, and sometimes more than one is used by the same machine learning system. For example, [topic modelling](./Topic_model), [meta-learning](./Meta-learning_(computer_science)).[[56]](./Machine_learning#cite_note-56)

 

#### Self-learning

 

Self-learning, as a machine learning paradigm, was introduced in 1982 along with a neural network capable of self-learning, named *crossbar adaptive array* (CAA).[[57]](./Machine_learning#cite_note-57)[[58]](./Machine_learning#cite_note-58) It gives a solution to the problem learning without any external reward, by introducing emotion as an internal reward. Emotion is used as a state evaluation of a self-learning agent. The CAA self-learning algorithm computes, in a crossbar fashion, both decisions about actions and emotions (feelings) about consequence situations. The system is driven by the interaction between cognition and emotion.[[59]](./Machine_learning#cite_note-59)
The self-learning algorithm updates a memory matrix W =||w(a,s)|| such that in each iteration executes the following machine learning routine: 

 
1. in situation *s* act *a*
2. receive a consequence situation *s*'
3. compute emotion of being in the consequence situation *v(s')*
4. update crossbar memory  *w'(a,s) = w(a,s) + v(s')*

 

It is a system with only one input, situation, and only one output, action (or behaviour) a. There is neither a separate reinforcement input nor an advice input from the environment. The backpropagated value (secondary reinforcement) is the emotion toward the consequence situation. The CAA exists in two environments, one is the behavioural environment where it behaves, and the other is the genetic environment, wherefrom it initially and only once receives initial emotions about situations to be encountered in the behavioural environment. After receiving the genome (species) vector from the genetic environment, the CAA learns a goal-seeking behaviour in an environment that contains both desirable and undesirable situations.[[60]](./Machine_learning#cite_note-60)

 

#### Feature learning

 Main article: [Feature learning](./Feature_learning) 

Several learning algorithms aim at discovering better representations of the inputs provided during training.[[61]](./Machine_learning#cite_note-pami-61) Classic examples include [principal component analysis](./Principal_component_analysis) and cluster analysis. Feature learning algorithms, also called representation learning algorithms, often attempt to preserve the information in their input but also transform it in a way that makes it useful, often as a pre-processing step before performing classification or predictions. This technique allows reconstruction of the inputs coming from the unknown data-generating distribution, while not being necessarily faithful to configurations that are implausible under that distribution. This replaces manual [feature engineering](./Feature_engineering), and allows a machine to both learn the features and use them to perform a specific task.

 

Feature learning can be either supervised or unsupervised. In supervised feature learning, features are learned using labelled input data. Examples include [artificial neural networks](./Artificial_neural_network), [multilayer perceptrons](./Multilayer_perceptron), and supervised [dictionary learning](./Dictionary_learning). In unsupervised feature learning, features are learned with unlabelled input data.  Examples include dictionary learning, [independent component analysis](./Independent_component_analysis), [autoencoders](./Autoencoder), [matrix factorisation](./Matrix_decomposition)[[62]](./Machine_learning#cite_note-62) and various forms of [clustering](./Cluster_analysis).[[63]](./Machine_learning#cite_note-coates2011-63)[[64]](./Machine_learning#cite_note-64)[[65]](./Machine_learning#cite_note-jurafsky-65)

 

[Manifold learning](./Manifold_learning) algorithms attempt to do so under the constraint that the learned representation is low-dimensional. [Sparse coding](./Sparse_coding) algorithms attempt to do so under the constraint that the learned representation is sparse, meaning that the mathematical model has many zeros. [Multilinear subspace learning](./Multilinear_subspace_learning) algorithms aim to learn low-dimensional representations directly from [tensor](./Tensor) representations for multidimensional data, without reshaping them into higher-dimensional vectors.[[66]](./Machine_learning#cite_note-66) [Deep learning](./Deep_learning) algorithms discover multiple levels of representation, or a hierarchy of features, with higher-level, more abstract features defined in terms of (or generating) lower-level features. It has been argued that an intelligent machine learns a representation that disentangles the underlying factors of variation that explain the observed data.[[67]](./Machine_learning#cite_note-67)

 

Feature learning is motivated by the fact that machine learning tasks such as classification often require input that is mathematically and computationally convenient to process. However, real-world data such as images, video, and sensory data have not yielded attempts to algorithmically define specific features. An alternative is to discover such features or representations through examination, without relying on explicit algorithms.

 

#### Sparse dictionary learning

 Main article: [Sparse dictionary learning](./Sparse_dictionary_learning) 

Sparse dictionary learning is a feature learning method where a training example is represented as a linear combination of [basis functions](./Basis_function) and assumed to be a [sparse matrix](./Sparse_matrix). The method is [strongly NP-hard](./Strongly_NP-hard) and difficult to solve approximately.[[68]](./Machine_learning#cite_note-68) A popular [heuristic](./Heuristic) method for sparse dictionary learning is the [*k*-SVD](./K-SVD) algorithm. Sparse dictionary learning has been applied in several contexts. In classification, the problem is to determine the class to which a previously unseen training example belongs. For a dictionary where each class has already been built, a new training example is associated with the class that is best sparsely represented by the corresponding dictionary. Sparse dictionary learning has also been applied in [image denoising](./Image_denoising). The key idea is that a clean image patch can be sparsely represented by an image dictionary, but the noise cannot.[[69]](./Machine_learning#cite_note-69)

 

#### Anomaly detection

 Main article: [Anomaly detection](./Anomaly_detection) 

In [data mining](./Data_mining), anomaly detection, also known as outlier detection, is the identification of rare items, events or observations that raise suspicions by differing significantly from the majority of the data.[[70]](./Machine_learning#cite_note-Zimek-2017-70) Typically, the anomalous items represent an issue such as [bank fraud](./Bank_fraud), a structural defect, medical problems or errors in a text. Anomalies are referred to as [outliers](./Outlier), novelties, noise, deviations and exceptions.[[71]](./Machine_learning#cite_note-71)

 

In particular, in the context of abuse and network intrusion detection, the interesting objects are often not rare, but unexpected bursts of inactivity. This pattern does not adhere to the common statistical definition of an outlier as a rare object. Many outlier detection methods (in particular, unsupervised algorithms) will fail on such data unless aggregated appropriately. Instead, a cluster analysis algorithm may be able to detect the micro-clusters formed by these patterns.[[72]](./Machine_learning#cite_note-72)

 

Three broad categories of anomaly detection techniques exist.[[73]](./Machine_learning#cite_note-ChandolaSurvey-73) Unsupervised anomaly detection techniques detect anomalies in an unlabelled test data set under the assumption that the majority of the instances in the data set are normal, by looking for instances that seem to fit the least to the remainder of the data set. Supervised anomaly detection techniques require a data set that has been labelled as "normal" and "abnormal" and involves training a classifier (the key difference from many other statistical classification problems is the inherently unbalanced nature of outlier detection). Semi-supervised anomaly detection techniques construct a model representing normal behaviour from a given normal training data set and then test the likelihood of a test instance being generated by the model.

 

#### Robot learning

 

[Robot learning](./Robot_learning) is inspired by a multitude of machine learning methods, starting from supervised learning, reinforcement learning,[[74]](./Machine_learning#cite_note-74)[[75]](./Machine_learning#cite_note-75) and finally [meta-learning](./Meta-learning_(computer_science)) (e.g. MAML).

 

#### Association rules

 Main article: [Association rule learning](./Association_rule_learning)See also: [Inductive logic programming](./Inductive_logic_programming) 

Association rule learning is a [rule-based machine learning](./Rule-based_machine_learning) method for discovering relationships between variables in large databases. It is intended to identify strong rules discovered in databases using some measure of "interestingness".[[76]](./Machine_learning#cite_note-piatetsky-76)

 

Rule-based machine learning is a general term for any machine learning method that identifies, learns, or evolves "rules" to store, manipulate or apply knowledge. The defining characteristic of a rule-based machine learning algorithm is the identification and utilisation of a set of relational rules that collectively represent the knowledge captured by the system. This is in contrast to other machine learning algorithms that commonly identify a singular model that can be universally applied to any instance in order to make a prediction.[[77]](./Machine_learning#cite_note-77) Rule-based machine learning approaches include [learning classifier systems](./Learning_classifier_system), association rule learning, and [artificial immune systems](./Artificial_immune_system).

 

Based on the concept of strong rules, [Rakesh Agrawal](./Rakesh_Agrawal_(computer_scientist)), [Tomasz Imieliński](./Tomasz_Imieliński) and Arun Swami introduced association rules for discovering regularities between products in large-scale transaction data recorded by [point-of-sale](./Point-of-sale) (POS) systems in supermarkets.[[78]](./Machine_learning#cite_note-mining-78) For example, the rule     {  o n i o n s , p o t a t o e s  } ⇒ ⇒  {  b u r g e r  }   {\displaystyle \{\mathrm {onions,potatoes} \}\Rightarrow \{\mathrm {burger} \}}  ![{\displaystyle \{\mathrm {onions,potatoes} \}\Rightarrow \{\mathrm {burger} \}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2e6daa2c8e553e87e411d6e0ec66ae596c3c9381) found in the sales data of a supermarket would indicate that if a customer buys onions and potatoes together, they are likely to also buy hamburger meat. Such information can be used as the basis for decisions about marketing activities such as promotional [pricing](./Pricing) or [product placements](./Product_placement). In addition to [market basket analysis](./Market_basket_analysis), association rules are employed today in application areas including [Web usage mining](./Web_usage_mining), [intrusion detection](./Intrusion_detection), [continuous production](./Continuous_production), and [bioinformatics](./Bioinformatics). In contrast with [sequence mining](./Sequence_mining), association rule learning typically does not consider the order of items either within a transaction or across transactions.

 

[Learning classifier systems](./Learning_classifier_system) (LCS) are a family of rule-based machine learning algorithms that combine a discovery component, typically a [genetic algorithm](./Genetic_algorithm), with a learning component, performing either [supervised learning](./Supervised_learning), [reinforcement learning](./Reinforcement_learning), or [unsupervised learning](./Unsupervised_learning). They seek to identify a set of context-dependent rules that collectively store and apply knowledge in a [piecewise](./Piecewise) manner to make predictions.[[79]](./Machine_learning#cite_note-79)

 

[Inductive logic programming](./Inductive_logic_programming) (ILP) is an approach to rule learning using [logic programming](./Logic_programming) as a uniform representation for input examples, background knowledge, and hypotheses. Given an encoding of the known background knowledge and a set of examples represented as a logical database of facts, an ILP system will derive a hypothesized logic program that [entails](./Entailment) all positive and no negative examples. [Inductive programming](./Inductive_programming) is a related field that considers any kind of programming language for representing hypotheses (and not only logic programming), such as [functional programs](./Functional_programming).

 

Inductive logic programming is particularly useful in [bioinformatics](./Bioinformatics) and [natural language processing](./Natural_language_processing). [Gordon Plotkin](./Gordon_Plotkin) and [Ehud Shapiro](./Ehud_Shapiro) laid the initial theoretical foundation for inductive machine learning in a logical setting.[[80]](./Machine_learning#cite_note-80)[[81]](./Machine_learning#cite_note-81)[[82]](./Machine_learning#cite_note-82) Shapiro built their first implementation (Model Inference System) in 1981: a [Prolog](./Prolog) program that inductively inferred logic programs from positive and negative examples.[[83]](./Machine_learning#cite_note-83) The term *inductive* here refers to [philosophical](./Inductive_reasoning) induction, suggesting a theory to explain observed facts, rather than [mathematical induction](./Mathematical_induction), proving a property for all members of a well-ordered set.

 


