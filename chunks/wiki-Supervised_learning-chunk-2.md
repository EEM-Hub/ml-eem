---
source: sources/wiki-Supervised_learning.md
source_url: https://en.wikipedia.org/wiki/Supervised_learning
chunk: 2/3
---

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

 


