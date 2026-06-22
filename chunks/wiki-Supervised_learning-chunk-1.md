---
source: sources/wiki-Supervised_learning.md
source_url: https://en.wikipedia.org/wiki/Supervised_learning
chunk: 1/3
---

Machine learning paradigm [![](//upload.wikimedia.org/wikipedia/commons/thumb/4/4d/Supervised_and_unsupervised_learning.png/500px-Supervised_and_unsupervised_learning.png)](./File:Supervised_and_unsupervised_learning.png)In supervised learning, the training data is labeled with the expected answers, while in [unsupervised learning](./Unsupervised_learning), the model identifies patterns or structures in unlabeled data. 

In [machine learning](./Machine_learning), **supervised learning** (**SL**) is a type of [machine learning paradigm](./Machine_learning#Approaches) where an algorithm learns to map input data to a specific output based on example input-output pairs. This process involves training a statistical model using [labeled data](./Labeled_data), meaning each piece of input data is provided with the correct output. The term "supervised" refers to the role of a teacher or supervisor who provides this training data, guiding the algorithm towards correct predictions.[[1]](./Supervised_learning#cite_note-1) For instance, if you want a model to identify cats in images, supervised learning would involve feeding it many images of cats (inputs) that are explicitly labeled "cat" (outputs).

 

The goal of supervised learning is for the trained model to accurately predict the output for new, unseen data.[[2]](./Supervised_learning#cite_note-2) This requires the algorithm to effectively [generalize](./Generalization_(learning)) from the training examples, a quality measured by its *[generalization error](./Generalization_error)*. Supervised learning is commonly used for tasks like [classification](./Classification) (predicting a category, e.g., spam or not spam) and [regression](./Regression_analysis) (predicting a continuous value, e.g., house prices).

 

## Steps to follow

 

To solve a given problem of supervised learning, the following steps must be performed:

 
1. Determine the type of training samples. Before doing anything else, the user should decide what kind of data is to be used as a [training set](./Training,_validation,_and_test_data_sets). In the case of [handwriting analysis](./Handwriting_analysis), for example, this might be a single handwritten character, an entire handwritten word, an entire sentence of handwriting, or a full paragraph of handwriting.
2. Gather a training set. The training set needs to be representative of the real-world use of the function. Thus, a set of input objects is gathered together with corresponding outputs, either from [human experts](./Subject-matter_expert) or from measurements.
3. Determine the input [feature](./Feature_(machine_learning)) representation of the learned function. The accuracy of the learned function depends strongly on how the input object is represented. Typically, the input object is transformed into a [feature vector](./Feature_vector), which contains a number of features that are descriptive of the object. The number of features should not be too large, because of the [curse of dimensionality](./Curse_of_dimensionality); but should contain enough information to accurately predict the output.
4. Determine the structure of the learned function and corresponding learning algorithm. For example, one may choose to use [support-vector machines](./Support-vector_machine) or [decision trees](./Decision_tree_learning).
5. Complete the design. Run the learning algorithm on the gathered training set. Some supervised learning algorithms require the user to determine certain [control parameters](./Hyperparameter_(machine_learning)). These parameters may be adjusted by optimizing performance on a subset (called a *[validation set](./Validation_set)*) of the training set, or via [cross-validation](./Cross-validation_(statistics)).
6. Evaluate the accuracy of the learned function. After parameter adjustment and learning, the performance of the resulting function should be measured on a [test set](./Test_set) that is separate from the training set.

 

## Algorithm choice

 

A wide range of supervised learning algorithms are available, each with its strengths and weaknesses. There is no single learning algorithm that works best on all supervised learning problems (see the [No free lunch theorem](./No_free_lunch_in_search_and_optimization)).

 

There are four major issues to consider in supervised learning:

 

### Bias–variance tradeoff

 Main article: [Bias–variance tradeoff](./Bias–variance_tradeoff) 

A first issue is the tradeoff between *bias* and *variance*.[[3]](./Supervised_learning#cite_note-3) Imagine that we have available several different, but equally good, training data sets. A learning algorithm is biased for a particular input     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4) if, when trained on each of these data sets, it is systematically incorrect when predicting the correct output for     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4). A learning algorithm has high variance for a particular input     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4) if it predicts different output values when trained on different training sets. The prediction error of a learned classifier is related to the sum of the bias and the variance of the learning algorithm.[[4]](./Supervised_learning#cite_note-4) Generally, there is a tradeoff between bias and variance. A learning algorithm with low bias must be "flexible" so that it can fit the data well. But if the learning algorithm is too flexible, it will fit each training data set differently, and hence have high variance. A key aspect of many supervised learning methods is that they are able to adjust this tradeoff between bias and variance (either automatically or by providing a bias/variance parameter that the user can adjust).

 

### Function complexity and amount of training data

 

The second issue is of the amount of training data available relative to the complexity of the "true" function (classifier or regression function). If the true function is simple, then an "inflexible" learning algorithm with high bias and low variance will be able to learn it from a small amount of data. But if the true function is highly complex (e.g., because it involves complex interactions among many different input features and behaves differently in different parts of the input space), then the function will only be able to learn with a large amount of training data paired with a "flexible" learning algorithm with low bias and high variance.

 

### Dimensionality of the input space

 

A third issue is the dimensionality of the input space. If the input feature vectors have large dimensions, learning the function can be difficult even if the true function only depends on a small number of those features. This is because the many "extra" dimensions can confuse the learning algorithm and cause it to have high variance. Hence, input data of large dimensions typically requires tuning the classifier to have low variance and high bias. In practice, if the engineer can manually remove irrelevant features from the input data, it will likely improve the accuracy of the learned function. In addition, there are many algorithms for [feature selection](./Feature_selection) that seek to identify the relevant features and discard the irrelevant ones. This is an instance of the more general strategy of [dimensionality reduction](./Dimensionality_reduction), which seeks to map the input data into a lower-dimensional space prior to running the supervised learning algorithm.

 

### Noise in the output values

 

A fourth issue is the degree of noise in the desired output values (the supervisory [target variables](./Target_variable)). If the desired output values are often incorrect (because of human error or sensor errors), then the learning algorithm should not attempt to find a function that exactly matches the training examples. Attempting to fit the data too carefully leads to [overfitting](./Overfitting). You can overfit even when there are no measurement errors (stochastic noise) if the function you are trying to learn is too complex for your learning model. In such a situation, the part of the target function that cannot be modeled "corrupts" your training data – this phenomenon has been called [deterministic noise](./Deterministic_noise). When either type of noise is present, it is better to go with a higher bias, lower variance estimator.

 

In practice, there are several approaches to alleviate noise in the output values such as [early stopping](./Early_stopping) to prevent overfitting as well as [detecting](./Anomaly_detection) and removing the noisy training examples prior to training the supervised learning algorithm. There are several algorithms that identify noisy training examples and removing the suspected noisy training examples prior to training has decreased [generalization error](./Generalization_error) with [statistical significance](./Statistical_significance).[[5]](./Supervised_learning#cite_note-5)[[6]](./Supervised_learning#cite_note-6)

 

### Other factors to consider

 

Other factors to consider when choosing and applying a learning algorithm include the following:

 
- Heterogeneity of the data. If the feature vectors include features of many different kinds (discrete, discrete ordered, counts, continuous values), some algorithms are easier to apply than others. Many algorithms, including [support-vector machines](./Support_Vector_Machines), [linear regression](./Linear_regression), [logistic regression](./Logistic_regression), [neural networks](./Neural_network_(machine_learning)), and [nearest neighbor methods](./K-nearest_neighbors_algorithm), require that the input features be numerical and scaled to similar ranges (e.g., to the [-1,1] interval). Methods that employ a distance function, such as nearest neighbor methods and [support-vector machines with Gaussian kernels](./Support_Vector_Machines), are particularly sensitive to this. An advantage of [decision trees](./Decision_tree_learning) is that they easily handle heterogeneous data.
- Redundancy in the data. If the input features contain redundant information (e.g., highly correlated features), some learning algorithms (e.g., [linear regression](./Linear_regression), [logistic regression](./Logistic_regression), and [ distance-based methods](./K-nearest_neighbors_algorithm)) will perform poorly because of numerical instabilities. These problems can often be solved by imposing some form of [regularization](./Regularization_(mathematics)).
- Presence of interactions and non-linearities. If each of the features makes an independent contribution to the output, then algorithms based on linear functions (e.g., [linear regression](./Linear_regression), [logistic regression](./Logistic_regression), [support-vector machines](./Support-vector_machine), [naive Bayes](./Naive_Bayes_classifier)) and distance functions (e.g., nearest neighbor methods, [support-vector machines with Gaussian kernels](./Support_Vector_Machines)) generally perform well. However, if there are complex interactions among features, then algorithms such as [decision trees](./Decision_tree_learning) and neural networks work better, because they are specifically designed to discover these interactions. Linear methods can also be applied, but the engineer must manually specify the interactions when using them.

 

When considering a new application, the engineer can compare multiple learning algorithms and experimentally determine which one works best on the problem at hand (see [ cross-validation](./Cross-validation_(statistics))). Tuning the performance of a learning algorithm can be very time-consuming. Given fixed resources, it is often better to spend more time collecting additional training data and more informative features than it is to spend extra time tuning the learning algorithms.

 

### Algorithms

 

The most widely used learning algorithms are: 

 
- [Support-vector machines](./Support-vector_machine)
- [Linear regression](./Linear_regression)
- [Logistic regression](./Logistic_regression)
- [Naive Bayes](./Naive_Bayes_classifier)
- [Linear discriminant analysis](./Linear_discriminant_analysis)
- [Decision trees](./Decision_tree_learning)
- [*k*-nearest neighbors algorithm](./K-nearest_neighbors_algorithm)
- [Neural networks](./Neural_network_(machine_learning)) (e.g., [Multilayer perceptron](./Multilayer_perceptron))
- [Similarity learning](./Similarity_learning)

 


