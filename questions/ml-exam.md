# Machine Learning Comprehensive Exam

## Q1: What is the defining characteristic of supervised learning?
- a) The model learns from unlabeled data by discovering hidden patterns
- b) The model learns a mapping from inputs to outputs using labeled training data
- c) The model learns through trial and error by maximizing a reward signal
- d) The model generates new data samples that resemble the training distribution
Answer: b
Objective: Supervised Learning

## Q2: Which loss function is most commonly used for multi-class classification problems?
- a) Mean squared error
- b) Hinge loss
- c) Cross-entropy loss
- d) Huber loss
Answer: c
Objective: Supervised Learning

## Q3: In supervised learning, what distinguishes classification from regression?
- a) Classification uses neural networks while regression uses linear models
- b) Classification predicts discrete labels while regression predicts continuous values
- c) Classification requires more data than regression
- d) Classification is unsupervised while regression is supervised
Answer: b
Objective: Supervised Learning

## Q4: What does unsupervised learning primarily aim to discover?
- a) The optimal policy for sequential decision-making
- b) The mapping between inputs and labeled outputs
- c) Hidden structure or patterns in unlabeled data
- d) The gradient of the loss function
Answer: c
Objective: Unsupervised Learning

## Q5: Which technique is most commonly used for dimensionality reduction?
- a) Random forests
- b) Principal Component Analysis (PCA)
- c) Support vector machines
- d) Gradient boosting
Answer: b
Objective: Unsupervised Learning

## Q6: What is the relationship between self-supervised learning and unsupervised learning?
- a) They are completely unrelated paradigms
- b) Self-supervised learning is a subset of unsupervised learning
- c) Unsupervised learning is a subset of self-supervised learning
- d) Self-supervised learning requires labeled data
Answer: b
Objective: Unsupervised Learning

## Q7: In reinforcement learning, how are environments typically modeled?
- a) As Bayesian networks
- b) As Markov Decision Processes (MDPs)
- c) As directed acyclic graphs
- d) As Hidden Markov Models
Answer: b
Objective: Reinforcement Learning

## Q8: What does an RL agent learn to maximize?
- a) The accuracy on a validation set
- b) The log-likelihood of the data
- c) The cumulative reward signal
- d) The entropy of the policy
Answer: c
Objective: Reinforcement Learning

## Q9: Which system combined CNNs with Q-learning to play Atari games?
- a) AlphaGo
- b) Deep TAMER
- c) DQN (Deep Q-Network)
- d) A3C
Answer: c
Objective: Reinforcement Learning

## Q10: What is backpropagation fundamentally equivalent to in mathematics?
- a) Forward-mode automatic differentiation
- b) Reverse-mode automatic differentiation
- c) Numerical differentiation using finite differences
- d) Symbolic differentiation
Answer: b
Objective: Backpropagation

## Q11: What is the role of backpropagation in neural network training?
- a) It is a complete learning algorithm that updates weights
- b) It computes gradients; a separate optimizer updates weights
- c) It initializes the network weights randomly
- d) It determines the network architecture
Answer: b
Objective: Backpropagation

## Q12: Which activation function replaced sigmoid as the default for hidden layers in modern deep networks?
- a) Tanh
- b) Softmax
- c) ReLU
- d) Leaky ReLU
Answer: c
Objective: Neural Networks

## Q13: What problem did Hochreiter identify in 1991 regarding deep networks?
- a) The exploding gradient problem
- b) The vanishing gradient problem
- c) The mode collapse problem
- d) The overfitting problem
Answer: b
Objective: Neural Networks

## Q14: What does the universal approximation theorem guarantee about neural networks?
- a) Deep networks always converge to the global optimum
- b) A sufficiently wide single-hidden-layer network can approximate any continuous function
- c) Deeper networks always outperform shallower ones
- d) Neural networks can solve any NP-hard problem
Answer: b
Objective: Neural Networks

## Q15: What are the four distinguishing features of CNNs compared to regular neural networks?
- a) Local connectivity, shared weights, pooling, and multiple layers
- b) Attention, residual connections, normalization, and dropout
- c) Recurrence, gating, memory cells, and forget gates
- d) Generative, discriminative, adversarial, and variational components
Answer: a
Objective: CNNs

## Q16: What operation do modern CNNs actually compute, despite the name "convolution"?
- a) Fourier transform
- b) Cross-correlation
- c) Autocorrelation
- d) Deconvolution
Answer: b
Objective: CNNs

## Q17: Which 2012 model triggered the deep learning revolution by winning ImageNet?
- a) LeNet-5
- b) VGGNet
- c) AlexNet
- d) ResNet
Answer: c
Objective: CNNs

## Q18: What is the formula for computing CNN output size given input size n, kernel size k, padding p, and stride s?
- a) (n + 2p - k) / s + 1
- b) (n - k + p) * s
- c) n * k / (s + p)
- d) (n + k - 2p) / s
Answer: a
Objective: CNNs

## Q19: What problem did ResNet's skip connections solve in 2015?
- a) The overfitting problem in shallow networks
- b) The degradation problem where deeper networks had higher training error
- c) The mode collapse problem in generative models
- d) The class imbalance problem in detection
Answer: b
Objective: CNNs

## Q20: What architectural innovation did LSTM introduce to solve the vanishing gradient problem?
- a) Attention mechanisms
- b) Residual connections
- c) Gating mechanisms (input, forget, output gates)
- d) Batch normalization
Answer: c
Objective: RNNs

## Q21: What year was LSTM introduced?
- a) 1991
- b) 1995 (or 1997)
- c) 2001
- d) 2006
Answer: b
Objective: RNNs

## Q22: How does GRU differ from LSTM architecturally?
- a) GRU has more gates than LSTM
- b) GRU is a simplified version with fewer gates
- c) GRU uses attention instead of gates
- d) GRU eliminates recurrence entirely
Answer: b
Objective: RNNs

## Q23: What is the key innovation of the Transformer architecture introduced in "Attention Is All You Need" (2017)?
- a) Using recurrence with attention
- b) Replacing recurrence entirely with self-attention mechanisms
- c) Combining CNNs with attention
- d) Using reinforcement learning for sequence modeling
Answer: b
Objective: Transformers

## Q24: What is the computational complexity of standard self-attention with respect to sequence length n?
- a) O(n)
- b) O(n log n)
- c) O(n^2)
- d) O(n^3)
Answer: c
Objective: Transformers

## Q25: What are the three main architectural variants of Transformers?
- a) Small, medium, and large
- b) Encoder-only, decoder-only, and encoder-decoder
- c) Attention, convolution, and recurrence
- d) Pre-trained, fine-tuned, and distilled
Answer: b
Objective: Transformers

## Q26: Which model is encoder-only and which is decoder-only?
- a) GPT is encoder-only, BERT is decoder-only
- b) BERT is encoder-only, GPT is decoder-only
- c) Both are encoder-decoder models
- d) Both are decoder-only models
Answer: b
Objective: Transformers

## Q27: What is the scaling factor in the scaled dot-product attention formula?
- a) 1/d_k
- b) sqrt(d_k)
- c) 1/sqrt(d_k)
- d) log(d_k)
Answer: c
Objective: Transformers

## Q28: Who introduced GANs and in what year?
- a) Yann LeCun in 2012
- b) Ian Goodfellow in 2014
- c) Geoffrey Hinton in 2006
- d) Yoshua Bengio in 2010
Answer: b
Objective: GANs

## Q29: What is the training objective of GANs formulated as?
- a) Maximum likelihood estimation
- b) A minimax game between generator and discriminator
- c) Variational inference
- d) Contrastive learning
Answer: b
Objective: GANs

## Q30: What divergence does the original GAN minimize at optimality?
- a) KL divergence
- b) Wasserstein distance
- c) Jensen-Shannon divergence
- d) Total variation distance
Answer: c
Objective: GANs

## Q31: What is mode collapse in GAN training?
- a) The discriminator becomes too powerful
- b) The generator produces only a limited variety of outputs
- c) The learning rate becomes too small
- d) The network weights diverge to infinity
Answer: b
Objective: GANs

## Q32: What distance metric does WGAN use instead of Jensen-Shannon divergence?
- a) KL divergence
- b) Earth mover's (Wasserstein) distance
- c) Hellinger distance
- d) Total variation distance
Answer: b
Objective: GANs

## Q33: What class of models has supplanted GANs for text-to-image generation?
- a) Variational autoencoders
- b) Diffusion models
- c) Flow-based models
- d) Energy-based models
Answer: b
Objective: GANs

## Q34: What is the gradient descent update rule?
- a) x_{n+1} = x_n + gamma * gradient(F(x_n))
- b) x_{n+1} = x_n - gamma * gradient(F(x_n))
- c) x_{n+1} = x_n * gamma * gradient(F(x_n))
- d) x_{n+1} = x_n / gradient(F(x_n))
Answer: b
Objective: Optimization

## Q35: Who originated the gradient descent method and when?
- a) Newton in 1687
- b) Euler in 1768
- c) Cauchy in 1847
- d) Gauss in 1809
Answer: c
Objective: Optimization

## Q36: What is guaranteed about local minima for convex functions?
- a) They don't exist
- b) There are exactly two
- c) Any local minimum is also a global minimum
- d) They are always saddle points
Answer: c
Objective: Optimization

## Q37: What does momentum in gradient descent accomplish?
- a) It increases the learning rate over time
- b) It accumulates past gradients to accelerate convergence and dampen oscillations
- c) It randomly perturbs the weights
- d) It clips gradients to prevent explosion
Answer: b
Objective: Optimization

## Q38: What is the key idea behind the kernel trick in SVMs?
- a) Using multiple kernels simultaneously
- b) Computing dot products in high-dimensional space without explicit mapping
- c) Reducing the kernel size to speed up computation
- d) Applying convolution kernels to the data
Answer: b
Objective: SVMs

## Q39: What is special about the SVM optimization objective?
- a) It is non-convex
- b) It is convex, guaranteeing a global optimum
- c) It has multiple local minima
- d) It cannot be solved analytically
Answer: b
Objective: SVMs

## Q40: What determines the SVM decision boundary?
- a) All training examples
- b) Only the support vectors (points closest to the boundary)
- c) Only the outliers
- d) A random subset of training points
Answer: b
Objective: SVMs

## Q41: What ensemble method does Random Forest use?
- a) Boosting
- b) Stacking
- c) Bagging (bootstrap aggregating)
- d) Cascading
Answer: c
Objective: Random Forests

## Q42: How does bagging relate to the bias-variance tradeoff?
- a) Bagging reduces bias
- b) Bagging reduces variance
- c) Bagging increases both bias and variance
- d) Bagging has no effect on bias or variance
Answer: b
Objective: Random Forests

## Q43: What are the three components of the bias-variance decomposition of MSE?
- a) Bias, variance, and covariance
- b) Bias squared, variance, and irreducible error
- c) Mean, median, and mode
- d) Training error, validation error, and test error
Answer: b
Objective: Bias-Variance Tradeoff

## Q44: What is the double descent phenomenon?
- a) The loss decreases, then increases, then decreases again as model complexity grows
- b) The learning rate must be decreased twice during training
- c) Two separate gradient descent runs are needed
- d) The model must be trained on two separate datasets
Answer: a
Objective: Bias-Variance Tradeoff

## Q45: What does dropout do during training?
- a) Removes layers from the network
- b) Randomly zeroes out neuron activations with a given probability
- c) Decreases the learning rate
- d) Adds noise to the input data
Answer: b
Objective: Overfitting & Regularization

## Q46: What is the difference between L1 and L2 regularization?
- a) L1 is faster, L2 is more accurate
- b) L1 encourages sparse weights, L2 encourages small but diffuse weights
- c) L1 works only for classification, L2 only for regression
- d) There is no practical difference
Answer: b
Objective: Overfitting & Regularization

## Q47: What does transfer learning allow in practice?
- a) Transferring data between datasets
- b) Reusing knowledge learned on one task to improve performance on a related task
- c) Transferring models between different hardware
- d) Converting between supervised and unsupervised learning
Answer: b
Objective: Transfer Learning

## Q48: What three paradigm shifts has NLP undergone historically?
- a) Rule-based, template-based, neural
- b) Symbolic, statistical, neural (deep learning)
- c) Supervised, unsupervised, reinforcement
- d) Bag-of-words, TF-IDF, embeddings
Answer: b
Objective: NLP

## Q49: What was the significance of ImageNet/ILSVRC for computer vision?
- a) It was the first computer vision dataset
- b) It triggered the deep learning revolution when AlexNet won dramatically in 2012
- c) It proved that classical methods were superior to deep learning
- d) It introduced the concept of transfer learning
Answer: b
Objective: Computer Vision

## Q50: According to Tom Mitchell's definition, what three elements define machine learning?
- a) Data, algorithm, and hardware
- b) A task T, performance measure P, and experience E
- c) Input, hidden layers, and output
- d) Training, validation, and test sets
Answer: b
Objective: ML Foundations
