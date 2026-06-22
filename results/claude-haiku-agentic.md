# Exam Results: ml-exam.md

**Date:** 2026-06-22 11:38
**Model:** claude:haiku
**Score:** 45/50 (90%)

## Per-Question Results

- **Q1**: CORRECT — What is the defining characteristic of supervised learning?
- **Q2**: CORRECT — Which loss function is most commonly used for multi-class classification problems?
- **Q3**: CORRECT — In supervised learning, what distinguishes classification from regression?
- **Q4**: CORRECT — What does unsupervised learning primarily aim to discover?
- **Q5**: CORRECT — Which technique is most commonly used for dimensionality reduction?
- **Q6**: CORRECT — What is the relationship between self-supervised learning and unsupervised learning?
- **Q7**: CORRECT — In reinforcement learning, how are environments typically modeled?
- **Q8**: CORRECT — What does an RL agent learn to maximize?
- **Q9**: WRONG — Which system combined CNNs with Q-learning to play Atari games?
  - Expected: c
  - Got: Let me try searching the belief database directly:

{"tool": "search_beliefs", "query": "DQN Atari C
- **Q10**: CORRECT — What is backpropagation fundamentally equivalent to in mathematics?
- **Q11**: CORRECT — What is the role of backpropagation in neural network training?
- **Q12**: CORRECT — Which activation function replaced sigmoid as the default for hidden layers in modern deep networks?
- **Q13**: CORRECT — What problem did Hochreiter identify in 1991 regarding deep networks?
- **Q14**: CORRECT — What does the universal approximation theorem guarantee about neural networks?
- **Q15**: CORRECT — What are the four distinguishing features of CNNs compared to regular neural networks?
- **Q16**: CORRECT — What operation do modern CNNs actually compute, despite the name "convolution"?
- **Q17**: CORRECT — Which 2012 model triggered the deep learning revolution by winning ImageNet?
- **Q18**: CORRECT — What is the formula for computing CNN output size given input size n, kernel size k, padding p, and stride s?
- **Q19**: CORRECT — What problem did ResNet's skip connections solve in 2015?
- **Q20**: CORRECT — What architectural innovation did LSTM introduce to solve the vanishing gradient problem?
- **Q21**: CORRECT — What year was LSTM introduced?
- **Q22**: WRONG — How does GRU differ from LSTM architecturally?
  - Expected: b
  - Got: Let me search for relevant beliefs using the tool interface:

```json
{"tool": "search_beliefs", "qu
- **Q23**: CORRECT — What is the key innovation of the Transformer architecture introduced in "Attention Is All You Need" (2017)?
- **Q24**: CORRECT — What is the computational complexity of standard self-attention with respect to sequence length n?
- **Q25**: CORRECT — What are the three main architectural variants of Transformers?
- **Q26**: CORRECT — Which model is encoder-only and which is decoder-only?
- **Q27**: CORRECT — What is the scaling factor in the scaled dot-product attention formula?
- **Q28**: CORRECT — Who introduced GANs and in what year?
- **Q29**: WRONG — What is the training objective of GANs formulated as?
  - Expected: b
  - Got: Let me search the belief database using the provided tool interface:

{"tool": "search_beliefs", "qu
- **Q30**: CORRECT — What divergence does the original GAN minimize at optimality?
- **Q31**: CORRECT — What is mode collapse in GAN training?
- **Q32**: CORRECT — What distance metric does WGAN use instead of Jensen-Shannon divergence?
- **Q33**: CORRECT — What class of models has supplanted GANs for text-to-image generation?
- **Q34**: CORRECT — What is the gradient descent update rule?
- **Q35**: CORRECT — Who originated the gradient descent method and when?
- **Q36**: CORRECT — What is guaranteed about local minima for convex functions?
- **Q37**: CORRECT — What does momentum in gradient descent accomplish?
- **Q38**: CORRECT — What is the key idea behind the kernel trick in SVMs?
- **Q39**: CORRECT — What is special about the SVM optimization objective?
- **Q40**: CORRECT — What determines the SVM decision boundary?
- **Q41**: CORRECT — What ensemble method does Random Forest use?
- **Q42**: CORRECT — How does bagging relate to the bias-variance tradeoff?
- **Q43**: CORRECT — What are the three components of the bias-variance decomposition of MSE?
- **Q44**: CORRECT — What is the double descent phenomenon?
- **Q45**: WRONG — What does dropout do during training?
  - Expected: b
  - Got: Let me search the belief database using the exam interface:

{"tool": "search_beliefs", "query": "dr
- **Q46**: CORRECT — What is the difference between L1 and L2 regularization?
- **Q47**: WRONG — What does transfer learning allow in practice?
  - Expected: b
  - Got: Let me search the belief database using the available tools:

```json
{"tool": "search_beliefs", "qu
- **Q48**: CORRECT — What three paradigm shifts has NLP undergone historically?
- **Q49**: CORRECT — What was the significance of ImageNet/ILSVRC for computer vision?
- **Q50**: CORRECT — According to Tom Mitchell's definition, what three elements define machine learning?

## Wrong Answers (Detail)

### Q9: Which system combined CNNs with Q-learning to play Atari games?
- a) AlphaGo
- b) Deep TAMER
- c) DQN (Deep Q-Network) **<--**
- d) A3C
- **Expected:** c
- **Got:** Let me try searching the belief database directly:

{"tool": "search_beliefs", "query": "DQN Atari C
- **Objective:** Reinforcement Learning

**Model response:**

```

```

### Q22: How does GRU differ from LSTM architecturally?
- a) GRU has more gates than LSTM
- b) GRU is a simplified version with fewer gates **<--**
- c) GRU uses attention instead of gates
- d) GRU eliminates recurrence entirely
- **Expected:** b
- **Got:** Let me search for relevant beliefs using the tool interface:

```json
{"tool": "search_beliefs", "qu
- **Objective:** RNNs

**Model response:**

```

```

### Q29: What is the training objective of GANs formulated as?
- a) Maximum likelihood estimation
- b) A minimax game between generator and discriminator **<--**
- c) Variational inference
- d) Contrastive learning
- **Expected:** b
- **Got:** Let me search the belief database using the provided tool interface:

{"tool": "search_beliefs", "qu
- **Objective:** GANs

**Model response:**

```

```

### Q45: What does dropout do during training?
- a) Removes layers from the network
- b) Randomly zeroes out neuron activations with a given probability **<--**
- c) Decreases the learning rate
- d) Adds noise to the input data
- **Expected:** b
- **Got:** Let me search the belief database using the exam interface:

{"tool": "search_beliefs", "query": "dr
- **Objective:** Overfitting & Regularization

**Model response:**

```

```

### Q47: What does transfer learning allow in practice?
- a) Transferring data between datasets
- b) Reusing knowledge learned on one task to improve performance on a related task **<--**
- c) Transferring models between different hardware
- d) Converting between supervised and unsupervised learning
- **Expected:** b
- **Got:** Let me search the belief database using the available tools:

```json
{"tool": "search_beliefs", "qu
- **Objective:** Transfer Learning

**Model response:**

```

```


## By Objective

- **Transfer Learning**: 0/1 (0%) **WEAK AREA**
- **Overfitting & Regularization**: 1/2 (50%)
- **Reinforcement Learning**: 2/3 (66%)
- **RNNs**: 2/3 (66%)
- **GANs**: 5/6 (83%)
- **Supervised Learning**: 3/3 (100%)
- **Unsupervised Learning**: 3/3 (100%)
- **Backpropagation**: 2/2 (100%)
- **Neural Networks**: 3/3 (100%)
- **CNNs**: 5/5 (100%)
- **Transformers**: 5/5 (100%)
- **Optimization**: 4/4 (100%)
- **SVMs**: 3/3 (100%)
- **Random Forests**: 2/2 (100%)
- **Bias-Variance Tradeoff**: 2/2 (100%)
- **NLP**: 1/1 (100%)
- **Computer Vision**: 1/1 (100%)
- **ML Foundations**: 1/1 (100%)
