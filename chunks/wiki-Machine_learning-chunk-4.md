---
source: sources/wiki-Machine_learning.md
source_url: https://en.wikipedia.org/wiki/Machine_learning
chunk: 4/8
---

## Models

 

A **machine learning model** is a type of [mathematical model](./Mathematical_model) that, once "trained" on a given dataset, can be used to make predictions or classifications on new data. During training, a learning algorithm iteratively adjusts the model's internal parameters to minimise errors in its predictions.[[84]](./Machine_learning#cite_note-84) By extension, the term "model" can refer to several levels of specificity, from a general class of models and their associated learning algorithms to a fully trained model with all its internal parameters tuned.[[85]](./Machine_learning#cite_note-85)

 

Various types of models have been used and researched for machine learning systems, picking the best model for a task is called [model selection](./Model_selection).

 

### Artificial neural networks

 Main article: [Artificial neural network](./Artificial_neural_network)See also: [Deep learning](./Deep_learning) [![](//upload.wikimedia.org/wikipedia/commons/thumb/4/46/Colored_neural_network.svg/250px-Colored_neural_network.svg.png)](./File:Colored_neural_network.svg)An artificial neural network is an interconnected group of nodes, akin to the vast network of [neurons](./Neuron) in a [brain](./Brain). Here, each circular node represents an [artificial neuron](./Artificial_neuron) and an arrow represents a connection from the output of one artificial neuron to the input of another. 

Artificial neural networks (ANNs), or [connectionist](./Connectionism) systems, are computing systems vaguely inspired by the [biological neural networks](./Biological_neural_network) that constitute animal [brains](./Brain). Such systems "learn" to perform tasks by considering examples, generally without being programmed with any task-specific rules.

 

An ANN is a model based on a collection of connected units or nodes called "[artificial neurons](./Artificial_neuron)", which loosely model the [neurons](./Neuron) in a biological brain. Each connection, like the [synapses](./Synapse) in a biological brain, can transmit information, a "signal", from one artificial neuron to another. An artificial neuron that receives a signal can process it and then signal additional artificial neurons connected to it. In common ANN implementations, the signal at a connection between artificial neurons is a [real number](./Real_number), and the output of each artificial neuron is computed by some non-linear function of the sum of its inputs. The connections between artificial neurons are called "edges". Artificial neurons and edges typically have a [weight](./Weight_(mathematics)) that adjusts as learning proceeds. The weight increases or decreases the strength of the signal at a connection. Artificial neurons may have a threshold such that the signal is only sent if the aggregate signal crosses that threshold. Typically, artificial neurons are aggregated into layers. Different layers may perform different kinds of transformations on their inputs. Signals travel from the first layer (the input layer) to the last layer (the output layer), possibly after traversing the layers multiple times.

 

The original goal of the ANN approach was to solve problems in the same way that a [human brain](./Human_brain) would. However, over time, attention moved to performing specific tasks, leading to deviations from [biology](./Biology). Artificial neural networks have been used on a variety of tasks, including [computer vision](./Computer_vision), [speech recognition](./Speech_recognition), [machine translation](./Machine_translation), [social network](./Social_network) filtering, [playing board and video games](./General_game_playing) and [medical diagnosis](./Medical_diagnosis).

 

[Deep learning](./Deep_learning) consists of multiple hidden layers in an artificial neural network. This approach tries to model the way the human brain processes light and sound into vision and hearing. Some successful applications of deep learning are computer vision and speech recognition.[[86]](./Machine_learning#cite_note-86)

 

### Decision trees

 Main article: [Decision tree learning](./Decision_tree_learning) [![](//upload.wikimedia.org/wikipedia/commons/thumb/e/eb/Decision_Tree.jpg/330px-Decision_Tree.jpg)](./File:Decision_Tree.jpg)A decision tree showing survival probability of passengers on the [Titanic](./Titanic) 

Decision tree learning uses a [decision tree](./Decision_tree) as a [predictive model](./Predictive_modeling) to go from observations about an item (represented in the branches) to conclusions about the item's target value (represented in the leaves). It is one of the predictive modelling approaches used in statistics, data mining, and machine learning. Tree models where the target variable can take a discrete set of values are called classification trees; in these tree structures, [leaves](./Leaf_node) represent class labels, and branches represent [conjunctions](./Logical_conjunction) of features that lead to those class labels. Decision trees where the target variable can take continuous values (typically [real numbers](./Real_numbers)) are called regression trees. In decision analysis, a decision tree can be used to visually and explicitly represent decisions and [decision making](./Decision_making). In data mining, a decision tree describes data, but the resulting classification tree can be an input for decision-making.

 

### Random forest regression

 

[Random forest regression](./Random_forest) (RFR) falls under the umbrella of decision [tree-based models](./Tree-based_models). RFR is an ensemble learning method that builds multiple decision trees and averages their predictions to improve accuracy and to avoid overfitting. To build decision trees, RFR uses bootstrapped sampling; for instance, each decision tree is trained on random data from the training set. This random selection of RFR for training enables the model to reduce biased predictions and achieve a higher degree of accuracy. RFR generates independent decision trees, and it can work on single-output data as well as multiple regressor tasks. This makes RFR compatible to be use in various applications.[[87]](./Machine_learning#cite_note-87)[[88]](./Machine_learning#cite_note-88)

 

### Support-vector machines

 Main article: [Support-vector machine](./Support-vector_machine) 

Support-vector machines (SVMs), also known as support-vector networks, are a set of related [supervised learning](./Supervised_learning) methods used for classification and regression. Given a set of training examples, each marked as belonging to one of two categories, an SVM training algorithm builds a model that predicts whether a new example falls into one category.[[89]](./Machine_learning#cite_note-CorinnaCortes-89) An SVM training algorithm is a non-[probabilistic](./Probabilistic_classification), [binary](./Binary_classifier), [linear classifier](./Linear_classifier), although methods such as [Platt scaling](./Platt_scaling) exist to use SVM in a probabilistic classification setting. In addition to performing linear classification, SVMs can efficiently perform a non-linear classification using what is called the [kernel trick](./Kernel_trick), implicitly mapping their inputs into high-dimensional feature spaces.

 

### Regression analysis

 Main article: [Regression analysis](./Regression_analysis) [![](//upload.wikimedia.org/wikipedia/commons/thumb/3/3a/Linear_regression.svg/330px-Linear_regression.svg.png)](./File:Linear_regression.svg)Illustration of linear regression on a data set 

Regression analysis encompasses a large variety of statistical methods to estimate the relationship between input variables and their associated features. Its most common form is [linear regression](./Linear_regression), where a single line is drawn to best fit the given data according to a mathematical criterion such as [ordinary least squares](./Ordinary_least_squares). The latter is often extended by [regularisation](./Regularization_(mathematics)) methods to mitigate overfitting and bias, as in [ridge regression](./Ridge_regression). When dealing with non-linear problems, go-to models include [polynomial regression](./Polynomial_regression) (for example, used for trendline fitting in Microsoft Excel[[90]](./Machine_learning#cite_note-90)), [logistic regression](./Logistic_regression) (often used in [statistical classification](./Statistical_classification)) or even [kernel regression](./Kernel_regression), which introduces non-linearity by taking advantage of the [kernel trick](./Kernel_trick) to implicitly map input variables to higher-dimensional space.

 

[Multivariate linear regression](./General_linear_model) extends the concept of linear regression to handle multiple dependent variables simultaneously. This approach estimates the relationships between a set of input variables and several output variables by fitting a [multidimensional](./Multidimensional_system) linear model. It is particularly useful in scenarios where outputs are interdependent or share underlying patterns, such as predicting multiple economic indicators or reconstructing images,[[91]](./Machine_learning#cite_note-91) which are inherently multi-dimensional.

 

### Bayesian networks

 Main article: [Bayesian network](./Bayesian_network) [![](//upload.wikimedia.org/wikipedia/commons/thumb/f/fd/SimpleBayesNetNodes.svg/250px-SimpleBayesNetNodes.svg.png)](./File:SimpleBayesNetNodes.svg)A simple Bayesian network. Rain influences whether the sprinkler is activated, and both rain and the sprinkler influence whether the grass is wet. 

A Bayesian network, belief network, or directed acyclic graphical model is a probabilistic [graphical model](./Graphical_model) that represents a set of [random variables](./Random_variables) and their [conditional independence](./Conditional_independence) with a [directed acyclic graph](./Directed_acyclic_graph) (DAG). For example, a Bayesian network could represent the probabilistic relationships between diseases and symptoms. Given symptoms, the network can be used to compute the probabilities of the presence of various diseases. Efficient algorithms exist that perform [inference](./Bayesian_inference) and learning. Bayesian networks that model sequences of variables, like [speech signals](./Speech_recognition) or [protein sequences](./Peptide_sequence), are called [dynamic Bayesian networks](./Dynamic_Bayesian_network). Generalisations of Bayesian networks that can represent and solve decision problems under uncertainty are called [influence diagrams](./Influence_diagram).

 

### Gaussian processes

 Main article: [Gaussian processes](./Gaussian_processes) [![](//upload.wikimedia.org/wikipedia/commons/thumb/a/a7/Regressions_sine_demo.svg/250px-Regressions_sine_demo.svg.png)](./File:Regressions_sine_demo.svg)An example of Gaussian Process Regression (prediction) compared with other regression models[[92]](./Machine_learning#cite_note-92) 

A Gaussian process is a [stochastic process](./Stochastic_process) in which every finite collection of the random variables in the process has a [multivariate normal distribution](./Multivariate_normal_distribution), and it relies on a pre-defined [covariance function](./Covariance_function), or kernel, that models how pairs of points relate to each other depending on their locations.

 

Given a set of observed points, or input–output examples, the distribution of the (unobserved) output of a new point as a function of its input data can be directly computed by looking at the observed points and the covariances between those points and the new, unobserved point.

 

Gaussian processes are popular surrogate models in [Bayesian optimisation](./Bayesian_optimisation) used to do [hyperparameter optimisation](./Hyperparameter_optimisation).

 

### Genetic algorithms

 Main article: [Genetic algorithm](./Genetic_algorithm) 

A genetic algorithm (GA) is a [search algorithm](./Search_algorithm) and [heuristic](./Heuristic_(computer_science)) technique that mimics the process of [natural selection](./Natural_selection), using methods such as [mutation](./Mutation_(genetic_algorithm)) and [crossover](./Crossover_(genetic_algorithm)) to generate new [genotypes](./Chromosome_(genetic_algorithm)) in the hope of finding good solutions to a given problem. In machine learning, genetic algorithms were used in the 1980s and 1990s.[[93]](./Machine_learning#cite_note-93)[[94]](./Machine_learning#cite_note-94) Conversely, machine learning techniques have been used to improve the performance of genetic and [evolutionary algorithms](./Evolutionary_algorithm).[[95]](./Machine_learning#cite_note-95)

 

### Belief functions

 Main article: [Dempster–Shafer theory](./Dempster–Shafer_theory) 

The theory of belief functions, also referred to as evidence theory or Dempster–Shafer theory, is a general framework for reasoning with uncertainty, with understood connections to other frameworks such as [probability](./Probability), [possibility](./Possibility_theory) and  [imprecise probability theories](./Imprecise_probability). These theoretical frameworks can be thought of as a kind of learner and have some analogous properties of how evidence is combined (e.g.,  Dempster's rule of combination), just like how in a [pmf](./Probability_mass_function)-based Bayesian approach would combine probabilities.[[96]](./Machine_learning#cite_note-96) However, there are many caveats to these beliefs functions when compared to Bayesian approaches to incorporate ignorance and [uncertainty quantification](./Uncertainty_quantification). These belief function approaches that are implemented within the machine learning domain typically leverage a fusion approach of various [ensemble methods](./Ensemble_methods) to better handle the learner's [decision boundary](./Decision_boundary), low samples, and ambiguous class issues that standard machine learning approach tend to have difficulty resolving.[[97]](./Machine_learning#cite_note-YoosefzadehNajafabadi-2021-97)[[6]](./Machine_learning#cite_note-Kohavi-6) However, the computational complexity of these algorithms is dependent on the number of propositions (classes), and can lead to a much higher computation time when compared to other machine learning approaches.

 

### Rule-based models

 Main article: [Rule-based machine learning](./Rule-based_machine_learning) 

Rule-based machine learning (RBML) is a branch of machine learning that automatically discovers and learns 'rules' from data. It provides interpretable models, making it useful for decision-making in fields like healthcare, fraud detection, and cybersecurity. Key RBML techniques includes [learning classifier systems](./Learning_classifier_system),[[98]](./Machine_learning#cite_note-98) [association rule learning](./Association_rule_learning),[[99]](./Machine_learning#cite_note-99) [artificial immune systems](./Artificial_immune_system),[[100]](./Machine_learning#cite_note-100) and other similar models. These methods extract patterns from data and evolve rules over time.

 

### Training models

 

Typically, machine learning models require a high quantity of reliable data to perform accurate predictions. When training a machine learning model, machine learning engineers need to target and collect a large and representative [sample](./Sample_(statistics)) of data. Data from the training set can be as varied as a [corpus of text](./Corpus_of_text), a collection of images, [sensor](./Sensor) data, and data collected from individual users of a service. [Overfitting](./Overfitting) is something to watch out for when training a machine learning model. Trained models derived from biased or non-evaluated data can result in skewed or undesired predictions. Biased models may result in detrimental outcomes, thereby furthering the negative impacts on society or objectives. [Algorithmic bias](./Algorithmic_bias) is a potential result of data not being fully prepared for training. Machine learning ethics is becoming a field of study and, notably, becoming integrated within machine learning engineering teams.

 

#### Federated learning

 Main article: [Federated learning](./Federated_learning) 

Federated learning is an adapted form of [distributed artificial intelligence](./Distributed_artificial_intelligence) to train machine learning models that decentralises the training process, allowing for users' privacy to be maintained by not needing to send their data to a centralised server. This also increases efficiency by decentralising the training process to many devices. For example, [Gboard](./Gboard) uses federated machine learning to train search query prediction models on users' mobile phones without having to send individual searches back to [Google](./Google).[[101]](./Machine_learning#cite_note-101)

 


