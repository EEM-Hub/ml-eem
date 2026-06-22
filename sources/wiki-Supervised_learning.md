---
source: https://en.wikipedia.org/wiki/Supervised_learning
fetched: 2026-06-21
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

 

## How supervised learning algorithms work

 

Given a set of     N   {\displaystyle N}  ![{\displaystyle N}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f5e3890c981ae85503089652feb48b191b57aae3) training examples of the form     { (  x  1   ,  y  1   ) , . . . , (  x  N   ,   y  N   ) }   {\displaystyle \{(x_{1},y_{1}),...,(x_{N},\;y_{N})\}}  ![{\displaystyle \{(x_{1},y_{1}),...,(x_{N},\;y_{N})\}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3688abd5ec58027a9d879916c83b6890744ce4dd) such that      x  i     {\displaystyle x_{i}}  ![{\displaystyle x_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e87000dd6142b81d041896a30fe58f0c3acb2158) is the [feature vector](./Feature_vector) of the     i   {\displaystyle i}  ![{\displaystyle i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/add78d8608ad86e54951b8c8bd6c8d8416533d20)-th example and      y  i     {\displaystyle y_{i}}  ![{\displaystyle y_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/67d30d30b6c2dbe4d6f150d699de040937ecc95f) is its label (i.e., class), a learning algorithm seeks a function     g : X → →  Y   {\displaystyle g:X\to Y}  ![{\displaystyle g:X\to Y}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5c825617c180ee9cbba1d56f8514978bf7c33b7c), where     X   {\displaystyle X}  ![{\displaystyle X}](https://wikimedia.org/api/rest_v1/media/math/render/svg/68baa052181f707c662844a465bfeeb135e82bab) is the input space and     Y   {\displaystyle Y}  ![{\displaystyle Y}](https://wikimedia.org/api/rest_v1/media/math/render/svg/961d67d6b454b4df2301ac571808a3538b3a6d3f) is the output space. The function     g   {\displaystyle g}  ![{\displaystyle g}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3556280e66fe2c0d0140df20935a6f057381d77) is an element of some space of possible functions     G   {\displaystyle G}  ![{\displaystyle G}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f5f3c8921a3b352de45446a6789b104458c9f90b), usually called the *hypothesis space*. It is sometimes convenient to represent     g   {\displaystyle g}  ![{\displaystyle g}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3556280e66fe2c0d0140df20935a6f057381d77) using a [scoring function](./Scoring_function)     f : X × ×  Y → →   R    {\displaystyle f:X\times Y\to \mathbb {R} }  ![{\displaystyle f:X\times Y\to \mathbb {R} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/e2c7bc3330b76d58cdb3bff67e7b0ec60a2509c9) such that     g   {\displaystyle g}  ![{\displaystyle g}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3556280e66fe2c0d0140df20935a6f057381d77) is defined as returning the     y   {\displaystyle y}  ![{\displaystyle y}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b8a6208ec717213d4317e666f1ae872e00620a0d) value that gives the highest score:     g ( x ) =    arg ⁡ ⁡  max  y    f ( x , y )   {\displaystyle g(x)={\underset {y}{\arg \max }}\;f(x,y)}  ![{\displaystyle g(x)={\underset {y}{\arg \max }}\;f(x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/cba4bc7532dc87fa4312abad85326b21e99f96d8). Let     F   {\displaystyle F}  ![{\displaystyle F}](https://wikimedia.org/api/rest_v1/media/math/render/svg/545fd099af8541605f7ee55f08225526be88ce57) denote the space of scoring functions.

 

Although     G   {\displaystyle G}  ![{\displaystyle G}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f5f3c8921a3b352de45446a6789b104458c9f90b) and     F   {\displaystyle F}  ![{\displaystyle F}](https://wikimedia.org/api/rest_v1/media/math/render/svg/545fd099af8541605f7ee55f08225526be88ce57) can be any space of functions, many learning algorithms are probabilistic models where     g   {\displaystyle g}  ![{\displaystyle g}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3556280e66fe2c0d0140df20935a6f057381d77) takes the form of a [conditional probability](./Conditional_probability) model     g ( x ) =    arg ⁡ ⁡  max  y    P ( y  |  x )   {\displaystyle g(x)={\underset {y}{\arg \max }}\;P(y|x)}  ![{\displaystyle g(x)={\underset {y}{\arg \max }}\;P(y|x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9416212f1466c7ce91578b8f87a42a15c9d831bb), or     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) takes the form of a [joint probability](./Joint_probability) model     f ( x , y ) = P ( x , y )   {\displaystyle f(x,y)=P(x,y)}  ![{\displaystyle f(x,y)=P(x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/497c7a6614b31a86270a3a7bed89410bcd1e001c). For example, [naive Bayes](./Naive_Bayes_classifier) and [linear discriminant analysis](./Linear_discriminant_analysis) are joint probability models, whereas [logistic regression](./Logistic_regression) is a conditional probability model.

 

There are two basic approaches to choosing     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) or     g   {\displaystyle g}  ![{\displaystyle g}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3556280e66fe2c0d0140df20935a6f057381d77): [empirical risk minimization](./Empirical_risk_minimization) and [structural risk minimization](./Structural_risk_minimization).[[7]](./Supervised_learning#cite_note-7) Empirical risk minimization seeks the function that best fits the training data. Structural risk minimization includes a *penalty function* that controls the bias/variance tradeoff.

 

In both cases, it is assumed that the training set consists of a sample of [independent and identically distributed pairs](./Independent_and_identically-distributed_random_variables),     (  x  i   ,   y  i   )   {\displaystyle (x_{i},\;y_{i})}  ![{\displaystyle (x_{i},\;y_{i})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/413bed828a4750e458455095965e7082bece1e98). In order to measure how well a function fits the training data, a [loss function](./Loss_function)     L : Y × ×  Y → →    R   ≥ ≥  0     {\displaystyle L:Y\times Y\to \mathbb {R} ^{\geq 0}}  ![{\displaystyle L:Y\times Y\to \mathbb {R} ^{\geq 0}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/881dc7b502a2b6a4970fb06609e170cf79475a59) is defined. For training example     (  x  i   ,   y  i   )   {\displaystyle (x_{i},\;y_{i})}  ![{\displaystyle (x_{i},\;y_{i})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/413bed828a4750e458455095965e7082bece1e98), the loss of predicting the value        y ^ ^       {\displaystyle {\hat {y}}}  ![{\displaystyle {\hat {y}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3dc8de3d8ea01304329ef9518fad7a6d196c4c01) is     L (  y  i   ,    y ^ ^     )   {\displaystyle L(y_{i},{\hat {y}})}  ![{\displaystyle L(y_{i},{\hat {y}})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6ac9025f28e57a00e0b20d64598436fe7a7477e9).

 

The *risk*     R ( g )   {\displaystyle R(g)}  ![{\displaystyle R(g)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ae075d527038ed7d449f85ced07e487b5807446c) of function     g   {\displaystyle g}  ![{\displaystyle g}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3556280e66fe2c0d0140df20935a6f057381d77) is defined as the expected loss of     g   {\displaystyle g}  ![{\displaystyle g}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3556280e66fe2c0d0140df20935a6f057381d77). This can be estimated from the training data as

      R  e m p   ( g ) =   1 N    ∑ ∑   i   L (  y  i   , g (  x  i   ) )   {\displaystyle R_{emp}(g)={\frac {1}{N}}\sum _{i}L(y_{i},g(x_{i}))}  ![{\displaystyle R_{emp}(g)={\frac {1}{N}}\sum _{i}L(y_{i},g(x_{i}))}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87fa2fe2f731e8e1b02e2710d36fc16076e449bf). 

### Empirical risk minimization

 Main article: [Empirical risk minimization](./Empirical_risk_minimization) 

In empirical risk minimization, the supervised learning algorithm seeks the function     g   {\displaystyle g}  ![{\displaystyle g}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3556280e66fe2c0d0140df20935a6f057381d77) that minimizes     R ( g )   {\displaystyle R(g)}  ![{\displaystyle R(g)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ae075d527038ed7d449f85ced07e487b5807446c). Hence, a supervised learning algorithm can be constructed by applying an [optimization algorithm](./Optimization_(mathematics)) to find     g   {\displaystyle g}  ![{\displaystyle g}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3556280e66fe2c0d0140df20935a6f057381d77).

 

When     g   {\displaystyle g}  ![{\displaystyle g}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3556280e66fe2c0d0140df20935a6f057381d77) is a conditional probability distribution     P ( y  |  x )   {\displaystyle P(y|x)}  ![{\displaystyle P(y|x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5d08508dff9e465cc317804ff19999c4ffbf7d94) and the loss function is the negative log likelihood:     L ( y ,    y ^ ^     ) = − −  log ⁡ ⁡  P ( y  |  x )   {\displaystyle L(y,{\hat {y}})=-\log P(y|x)}  ![{\displaystyle L(y,{\hat {y}})=-\log P(y|x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/eaee3db78a569f2bb35e3dced4a1953ace44665b), then empirical risk minimization is equivalent to [maximum likelihood estimation](./Maximum_likelihood).

 

When     G   {\displaystyle G}  ![{\displaystyle G}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f5f3c8921a3b352de45446a6789b104458c9f90b) contains many candidate functions or the training set is not sufficiently large, empirical risk minimization leads to high variance and poor generalization. The learning algorithm is able to memorize the training examples without generalizing well (overfitting).

 

### Structural risk minimization

 

[Structural risk minimization](./Structural_risk_minimization) seeks to prevent overfitting by incorporating a [regularization penalty](./Regularization_(mathematics)) into the optimization. The regularization penalty can be viewed as implementing a form of [Occam's razor](./Occam's_razor) that prefers simpler functions over more complex ones.

 

A wide variety of penalties have been employed that correspond to different definitions of complexity. For example, consider the case where the function     g   {\displaystyle g}  ![{\displaystyle g}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3556280e66fe2c0d0140df20935a6f057381d77) is a linear function of the form

     g ( x ) =  ∑ ∑   j = 1   d    β β   j    x  j     {\displaystyle g(x)=\sum _{j=1}^{d}\beta _{j}x_{j}}  ![{\displaystyle g(x)=\sum _{j=1}^{d}\beta _{j}x_{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/86f23781682d33c596d0cda976b013e2b6fdf939). 

A popular regularization penalty is      ∑ ∑   j    β β   j   2     {\displaystyle \sum _{j}\beta _{j}^{2}}  ![{\displaystyle \sum _{j}\beta _{j}^{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f7df304919e1cdf3dfc49b9db648afce80a189ce), which is the squared [Euclidean norm](./Euclidean_norm) of the weights, also known as the      L  2     {\displaystyle L_{2}}  ![{\displaystyle L_{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c6a952cfe42c86b7741f55a817da0e251793a358) norm. Other norms include the      L  1     {\displaystyle L_{1}}  ![{\displaystyle L_{1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0e79dc1b001f8b923df475ed14de023cbc456013) norm,      ∑ ∑   j    |   β β   j    |    {\displaystyle \sum _{j}|\beta _{j}|}  ![{\displaystyle \sum _{j}|\beta _{j}|}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4f7c345923255a0cf76b3e2080b915eeb02f4126), and the [     L  0     {\displaystyle L_{0}}  ![{\displaystyle L_{0}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/db742b8c210fc611329a4c2dcc3af4b4e1a110cb) "norm"](./L0_"norm"), which is the number of non-zero      β β   j     {\displaystyle \beta _{j}}  ![{\displaystyle \beta _{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/83edf0558c67ad56ca5c05096b550bd733d62c4b)s. The penalty will be denoted by     C ( g )   {\displaystyle C(g)}  ![{\displaystyle C(g)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e60538c5c17aadb0567923ff496ba4da02bcd40c).

 

The supervised learning optimization problem is to find the function     g   {\displaystyle g}  ![{\displaystyle g}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3556280e66fe2c0d0140df20935a6f057381d77) that minimizes

     J ( g ) =  R  e m p   ( g ) + λ λ  C ( g ) .   {\displaystyle J(g)=R_{emp}(g)+\lambda C(g).}  ![{\displaystyle J(g)=R_{emp}(g)+\lambda C(g).}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f66b4b813c97f6598ed08791352e014fc7e16514) 

The parameter     λ λ    {\displaystyle \lambda }  ![{\displaystyle \lambda }](https://wikimedia.org/api/rest_v1/media/math/render/svg/b43d0ea3c9c025af1be9128e62a18fa74bedda2a) controls the bias-variance tradeoff. When     λ λ  = 0   {\displaystyle \lambda =0}  ![{\displaystyle \lambda =0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/00c4bba30544017fe76932de5a4e25adb5512d95), this gives empirical risk minimization with low bias and high variance. When     λ λ    {\displaystyle \lambda }  ![{\displaystyle \lambda }](https://wikimedia.org/api/rest_v1/media/math/render/svg/b43d0ea3c9c025af1be9128e62a18fa74bedda2a) is large, the learning algorithm will have high bias and low variance. The value of     λ λ    {\displaystyle \lambda }  ![{\displaystyle \lambda }](https://wikimedia.org/api/rest_v1/media/math/render/svg/b43d0ea3c9c025af1be9128e62a18fa74bedda2a) can be chosen empirically via [ cross-validation](./Cross-validation_(statistics)).

 

The complexity penalty has a Bayesian interpretation as the negative log prior probability of     g   {\displaystyle g}  ![{\displaystyle g}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3556280e66fe2c0d0140df20935a6f057381d77),     − −  log ⁡ ⁡  P ( g )   {\displaystyle -\log P(g)}  ![{\displaystyle -\log P(g)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/140f8e655a53130f7068d9341b32891142e3a80c), in which case     J ( g )   {\displaystyle J(g)}  ![{\displaystyle J(g)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/81eae208007bd0ddec50b7f177e991b914a11508) is the [posterior probability](./Posterior_probability) of     g   {\displaystyle g}  ![{\displaystyle g}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3556280e66fe2c0d0140df20935a6f057381d77).

 

## Generative training

 

The training methods described above are *discriminative training* methods, because they seek to find a function     g   {\displaystyle g}  ![{\displaystyle g}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3556280e66fe2c0d0140df20935a6f057381d77) that discriminates well between the different output values (see [discriminative model](./Discriminative_model)). For the special case where     f ( x , y ) = P ( x , y )   {\displaystyle f(x,y)=P(x,y)}  ![{\displaystyle f(x,y)=P(x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/497c7a6614b31a86270a3a7bed89410bcd1e001c) is a [joint probability distribution](./Joint_probability_distribution) and the loss function is the negative log likelihood     − −   ∑ ∑   i   log ⁡ ⁡  P (  x  i   ,  y  i   ) ,   {\displaystyle -\sum _{i}\log P(x_{i},y_{i}),}  ![{\displaystyle -\sum _{i}\log P(x_{i},y_{i}),}](https://wikimedia.org/api/rest_v1/media/math/render/svg/89be2acbbec6725f4ac254167f2d9cd7e97d2c7c) a risk minimization algorithm is said to perform *generative training*, because     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) can be regarded as a [generative model](./Generative_model) that explains how the data were generated. Generative training algorithms are often simpler and more computationally efficient than discriminative training algorithms. In some cases, the solution can be computed in closed form as in [naive Bayes](./Naive_Bayes_classifier) and [linear discriminant analysis](./Linear_discriminant_analysis).

 

## Generalizations

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/9/90/Task-guidance.png/330px-Task-guidance.png)](./File:Task-guidance.png)Tendency for a task to employ supervised vs. unsupervised methods. Task names straddling circle boundaries is intentional. It shows that the classical division of imaginative tasks (left) employing unsupervised methods is blurred in today's learning schemes.

There are several ways in which the standard supervised learning problem can be generalized:

 
- [Semi-supervised learning](./Semi-supervised_learning) or [weak supervision](./Weak_supervision): the desired output values are provided only for a subset of the training data. The remaining data is unlabeled or imprecisely labeled.
- [Active learning](./Active_learning_(machine_learning)): Instead of assuming that all of the training examples are given at the start, active learning algorithms interactively collect new examples, typically by making queries to a human user. Often, the queries are based on unlabeled data, which is a scenario that combines semi-supervised learning with active learning.
- [Structured prediction](./Structured_prediction): When the desired output value is a complex object, such as a [parse tree](./Parse_tree) or a labeled graph, then standard methods must be extended.
- [Learning to rank](./Learning_to_rank): When the input is a set of objects and the desired output is a ranking of those objects, then again the standard methods must be extended.

 

## Approaches and algorithms

 
- Analytical learning
- [Artificial neural network](./Artificial_neural_network)
- [Backpropagation](./Backpropagation)
- [Boosting (meta-algorithm)](./Boosting_(meta-algorithm))
- [Bayesian statistics](./Bayesian_statistics)
- [Case-based reasoning](./Case-based_reasoning)
- [Decision tree learning](./Decision_tree_learning)
- [Inductive logic programming](./Inductive_logic_programming)
- [Gaussian process regression](./Gaussian_process_regression)
- [Genetic programming](./Genetic_programming)
- [Group method of data handling](./Group_method_of_data_handling)
- [Kernel estimators](./Variable_kernel_density_estimation#Use_for_statistical_classification)
- [Learning automata](./Learning_automaton)
- [Learning classifier systems](./Learning_classifier_system)
- [Learning vector quantization](./Learning_vector_quantization)
- [Minimum message length](./Minimum_message_length) ([decision trees](./Decision_tree), decision graphs, etc.)
- [Multilinear subspace learning](./Multilinear_subspace_learning)
- [Naive Bayes classifier](./Naive_Bayes_classifier)
- [Maximum entropy classifier](./Maximum_entropy_classifier)
- [Conditional random field](./Conditional_random_field)
- [Nearest neighbor algorithm](./Nearest_neighbor_(pattern_recognition))
- [Probably approximately correct learning](./Probably_approximately_correct_learning) (PAC) learning
- [Ripple down rules](./Ripple_down_rules), a knowledge acquisition methodology
- Symbolic machine learning algorithms
- Subsymbolic machine learning algorithms
- [Support vector machines](./Support_vector_machine)
- Minimum complexity machines (MCM)
- [Random forests](./Random_forest)
- [Ensembles of classifiers](./Ensembles_of_classifiers)
- [Ordinal classification](./Ordinal_classification)
- [Data pre-processing](./Data_pre-processing)
- Handling imbalanced datasets
- [Statistical relational learning](./Statistical_relational_learning)
- [Proaftn](./Proaftn), a multicriteria classification algorithm

 

## Applications

 
- [Bioinformatics](./Bioinformatics)
- [Cheminformatics](./Cheminformatics) 
- [Quantitative structure–activity relationship](./Quantitative_structure–activity_relationship)

- [Database marketing](./Database_marketing)
- [Handwriting recognition](./Handwriting_recognition)
- [Information retrieval](./Information_retrieval) 
- [Learning to rank](./Learning_to_rank)

- [Information extraction](./Information_extraction)
- Object recognition in [computer vision](./Computer_vision)
- [Optical character recognition](./Optical_character_recognition)
- [Spam detection](./Spamming)
- [Pattern recognition](./Pattern_recognition)
- [Speech recognition](./Speech_recognition)
- Supervised learning is a special case of [downward causation](./Downward_causation) in biological systems
- Landform classification using [satellite imagery](./Satellite_imagery)[[8]](./Supervised_learning#cite_note-8)
- Spend classification in [procurement](./Procurement) processes[[9]](./Supervised_learning#cite_note-9)

 

## General issues

 
- [Computational learning theory](./Computational_learning_theory)
- [Inductive bias](./Inductive_bias)
- [Overfitting](./Overfitting)
- (Uncalibrated) [class membership probabilities](./Class_membership_probabilities)
- [Version spaces](./Version_space)

 

## See also

 
- [List of datasets for machine-learning research](./List_of_datasets_for_machine-learning_research)
- [Unsupervised learning](./Unsupervised_learning)

 

## References

  
1. [↑](./Supervised_learning#cite_ref-1) Mitchell, Tom M. (2013). *Machine learning*. McGraw-Hill series in Computer Science (Nachdr. ed.). New York: McGraw-Hill. [ISBN](./ISBN_(identifier)) [978-0-07-042807-2](./Special:BookSources/978-0-07-042807-2).
2. [↑](./Supervised_learning#cite_ref-2) [Mehryar Mohri](./Mehryar_Mohri), Afshin Rostamizadeh, Ameet Talwalkar (2012) *Foundations of Machine Learning*, The MIT Press [ISBN](./ISBN_(identifier)) [9780262018258](./Special:BookSources/9780262018258).
3. [↑](./Supervised_learning#cite_ref-3) S. Geman, E. Bienenstock, and R. Doursat (1992). [Neural networks and the bias/variance dilemma](http://delta-apache-vm.cs.tau.ac.il/~nin/Courses/NC06/VarbiasBiasGeman.pdf). Neural Computation 4, 1–58.
4. [↑](./Supervised_learning#cite_ref-4) G. James (2003) Variance and Bias for General Loss Functions, Machine Learning 51, 115–135. ([http://www-bcf.usc.edu/~gareth/research/bv.pdf](http://www-bcf.usc.edu/~gareth/research/bv.pdf))
5. [↑](./Supervised_learning#cite_ref-5) C.E. Brodely and M.A. Friedl (1999). Identifying and Eliminating Mislabeled Training Instances, Journal of Artificial Intelligence Research 11, 131–167. ([http://jair.org/media/606/live-606-1803-jair.pdf](http://jair.org/media/606/live-606-1803-jair.pdf))
6. [↑](./Supervised_learning#cite_ref-6) M.R. Smith and T. Martinez (2011). "Improving Classification Accuracy by Identifying and Removing Instances that Should Be Misclassified". *Proceedings of International Joint Conference on Neural Networks (IJCNN 2011)*. pp. 2690–2697. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.221.1371](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.221.1371). [doi](./Doi_(identifier)):[10.1109/IJCNN.2011.6033571](https://doi.org/10.1109%2FIJCNN.2011.6033571).
7. [↑](./Supervised_learning#cite_ref-7) Vapnik, V. N. [The Nature of Statistical Learning Theory](https://books.google.com/books?id=EqgACAAAQBAJ&q=%22empirical+risk+minimization%22+OR+%22structural+risk+minimization%22) (2nd Ed.), Springer Verlag, 2000.
8. [↑](./Supervised_learning#cite_ref-8) A. Maity (2016). "Supervised Classification of RADARSAT-2 Polarimetric Data for Different Land Features". [arXiv](./ArXiv_(identifier)):[1608.00501](https://arxiv.org/abs/1608.00501) [[cs.CV](https://arxiv.org/archive/cs.CV)].
9. [↑](./Supervised_learning#cite_ref-9) ["Key Technologies for Agile Procurement | SIPMM Publications"](https://publication.sipmm.edu.sg/key-technologies-agile-procurement/). *publication.sipmm.edu.sg*. 2020-10-09. Retrieved 2022-06-16.

 

## External links

 
- [Machine Learning Open Source Software (MLOSS)](http://www.mloss.org/)

 
| vteDifferentiable computing |
| --- |
| General | Differentiable programmingInformation geometryStatistical manifoldAutomatic differentiationNeuromorphic computingPattern recognitionRicci calculusComputational learning theoryInductive bias |
| Hardware | IPUTPUVPUMemristorSpiNNaker |
| Software libraries | TensorFlowPyTorchKerasscikit-learnTheanoJAXFlux.jlMindSpore |
| PortalsComputer programmingTechnology |

 
| Authority control databases |
| --- |
| National | United StatesIsrael |
| Other | Yale LUX |