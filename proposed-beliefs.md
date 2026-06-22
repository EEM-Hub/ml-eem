# Proposed Beliefs

Review each entry: change `[ACCEPT]` to `[ACCEPT]` to keep, or vice versa.
Then run: `expert-build accept-beliefs`

---

**Generated:** 2026-06-21
**Source:** 115 entries from entries/
**Model:** claude

### [ACCEPT] backprop-loss-derivative-is-covector
The derivative of a scalar-valued loss function with respect to a vector of parameters is a covector (row vector), not a column vector.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] activation-jacobian-is-diagonal
Element-wise activation functions have a diagonal Jacobian matrix, which can be equivalently computed as a Hadamard (element-wise) product with the vector of per-node derivatives.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] weight-matrix-derivative-of-linear-map
The derivative of a linear map Wx with respect to the input x is the matrix W itself: (Wx)' = W.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] weight-matrix-rows-cols-convention
Weight matrix W^l has rows equal to the number of neurons in layer l and columns equal to the number of neurons in layer l-1.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] rumelhart-weight-subscript-convention
In the Rumelhart, Hinton & Williams (1986) convention, w_ij denotes the weight from unit i to unit j.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] backprop-computes-gradient-not-learning
Backpropagation only computes the gradient; a separate optimization algorithm (e.g., SGD, Adam) performs the actual parameter updates.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] backprop-is-reverse-mode-autodiff
Backpropagation is a special case of reverse mode automatic differentiation.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] backprop-cost-function-requirements
For backpropagation to apply, the cost function must (1) be expressible as an average over individual training examples, and (2) be a function of the network's outputs.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] backprop-historical-priority
Kelley (1960) and Bryson (1961) first described gradient computation for optimal control; Linnainmaa (1970) formalized reverse mode AD; Werbos (1974) first applied it to neural networks; Rumelhart, Hinton & Williams (1986) popularized it.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] werbos-bptt-1990
Werbos (1990) described Backpropagation Through Time (BPTT) for applying backpropagation to recurrent networks.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] robbins-monro-foundation-for-sgd
The Robbins-Monro (1951) stochastic approximation theorem provides the theoretical foundation for stochastic gradient descent.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] bias-variance-decomposition-three-terms
Expected generalization error under MSE decomposes into exactly three additive terms: squared bias, variance, and irreducible error (noise).
- Source: entries/2026/06/21/wiki-BiasE28093variance_tradeoff-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

### [ACCEPT] high-bias-underfitting-high-variance-overfitting
High bias causes underfitting (model misses relevant relationships); high variance causes overfitting (model captures noise rather than signal).
- Source: entries/2026/06/21/wiki-BiasE28093variance_tradeoff-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

### [ACCEPT] parameter-count-poor-complexity-measure
Number of parameters is a poor measure of model complexity — a model f(x) = a·sin(bx) has only two parameters but can interpolate arbitrarily many points via high-frequency oscillation.
- Source: entries/2026/06/21/wiki-BiasE28093variance_tradeoff-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

### [ACCEPT] complex-models-not-necessarily-high-variance
It is a fallacy to assume that complex models must have high variance; high variance models are complex, but the reverse does not hold.
- Source: entries/2026/06/21/wiki-BiasE28093variance_tradeoff-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

### [ACCEPT] regularization-trades-bias-for-variance
Regularization (e.g., L1/L2, shrinkage, dropout) trades increased bias for decreased variance to improve generalization.
- Source: entries/2026/06/21/wiki-BiasE28093variance_tradeoff-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

### [ACCEPT] bias-variance-specific-to-supervised-learning
The bias-variance tradeoff is specific to supervised learning problems.
- Source: entries/2026/06/21/wiki-BiasE28093variance_tradeoff-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

### [ACCEPT] irreducible-error-lower-bound-on-mse
The irreducible error σ² is a hard lower bound on achievable MSE, independent of model choice, because all three decomposition terms are non-negative.
- Source: entries/2026/06/21/wiki-BiasE28093variance_tradeoff-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

### [ACCEPT] mse-cross-term-vanishes-independence-zero-mean
In the MSE bias-variance derivation, the cross-term between (f - f̂) and ε vanishes because noise ε is independent of inputs and has zero mean — both assumptions are required.
- Source: entries/2026/06/21/wiki-BiasE28093variance_tradeoff-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

### [ACCEPT] bias-variance-decomposition-mse-specific
The bias-variance decomposition MSE = Bias² + Variance + σ² is specific to the mean squared error loss function; other loss functions (e.g., 0-1 loss) have different decompositions.
- Source: entries/2026/06/21/wiki-BiasE28093variance_tradeoff-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

### [ACCEPT] bias-variance-expectation-over-training-sets
In the bias-variance decomposition, expectations are taken over random draws of the training set D from P(x, y), not over a single fixed dataset.
- Source: entries/2026/06/21/wiki-BiasE28093variance_tradeoff-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

### [ACCEPT] bagging-reduces-variance-boosting-reduces-bias
Bagging (e.g., random forests) reduces variance; boosting (e.g., gradient boosting) reduces bias.
- Source: entries/2026/06/21/wiki-BiasE28093variance_tradeoff-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

### [ACCEPT] backprop-is-gradient-computation-not-optimizer
Backpropagation is strictly a gradient computation algorithm (reverse-mode chain rule); it does not specify how weights are updated — that is the role of an optimizer such as SGD or Adam.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] backprop-is-reverse-mode-autodiff
Backpropagation is a specific instance of reverse-mode automatic differentiation (also called reverse accumulation) applied to neural networks.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] backprop-delta-recursive-computation
The key intermediate quantity delta^l (gradient of the weighted input at layer l) is computed recursively from delta^(l+1) via δ^(l-1) = (f^(l-1))' ∘ (W^l)^T · δ^l, and is sufficient to compute all weight gradients at that layer.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] backprop-weight-gradient-outer-product
The weight gradient at layer l is computed as an outer product: ∇_{W^l} C = δ^l · (a^(l-1))^T, which is why activations from the forward pass must be cached.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] backprop-backward-vs-forward-complexity
Backward-mode differentiation multiplies a vector by a matrix at each layer (O(n²) per layer), while forward-mode multiplies a matrix by a matrix (O(n³) per layer), making backward mode computationally superior for computing loss gradients.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] cross-entropy-loss-classification-squared-error-regression
Cross-entropy (log loss) is the standard loss function for classification tasks; squared error loss is standard for regression tasks in neural network training.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] softmax-multiclass-logistic-binary
Softmax activation is used at the output layer for multi-class classification; the logistic (sigmoid) function is used for binary classification.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] relu-replaced-sigmoid-default-hidden-activation
ReLU has largely replaced sigmoid as the default hidden-layer activation function in neural networks.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] logistic-sigmoid-derivative-formula
The logistic sigmoid function φ(z) = 1/(1 + e^(-z)) has the convenient derivative φ'(z) = φ(z)(1 - φ(z)).
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] backprop-gradient-factors-to-oi-delta-j
The gradient ∂E/∂w_ij factors into the compact form o_i · δ_j, where o_i is the activation of the sending neuron and δ_j is the error signal at the receiving neuron.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] hidden-neuron-delta-recursive-from-downstream
For hidden neurons, δ_j = (Σ_ℓ w_jℓ · δ_ℓ) · φ'(net_j) — the error signal is computed recursively as a weighted sum of downstream δ values, which is the mechanism that gives backpropagation its name.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] relu-nondifferentiable-at-zero-works-in-practice
ReLU is non-differentiable at exactly 0 (violating backpropagation's theoretical requirement for differentiable activations), but works in practice by convention of setting f'(0) = 0 (subgradient approach), and has been dominant since AlexNet.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] loss-function-requirements-for-backprop
A loss function usable with backpropagation must satisfy two requirements: (1) decomposable as an average over individual training examples E = (1/n) Σ E_x, and (2) expressible as a function of the network's outputs.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] gradient-descent-finds-local-not-global-minima
Gradient descent with backpropagation finds local minima only, with no guarantee of reaching a global minimum; however, LeCun et al. argued this is often acceptable in practice for neural networks.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] levenberg-marquardt-second-order-faster-convergence
The Levenberg–Marquardt algorithm uses second-order (Hessian) information and converges faster than first-order gradient descent on complex error landscapes, and may find solutions with smaller network architectures.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] fisher-information-approximates-hessian
The Fisher information matrix is used as a practical approximation to the Hessian matrix in second-order neural network optimization methods.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] backprop-history-linnainmaa-1970-werbos-1982-rumelhart-1986
Seppo Linnainmaa (1970) published the first reverse-mode automatic differentiation; Paul Werbos (1982) first applied backpropagation to multilayer perceptrons; Rumelhart, Hinton, and Williams (1986 Nature paper) popularized it and triggered the 1980s neural network resurgence.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] amari-1967-first-sgd-trained-mlp
Shun'ichi Amari (1967) published the first multilayer perceptron trained by stochastic gradient descent, with 5 layers and 2 learnable layers.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] forward-pass-must-cache-activations-and-derivatives
During the forward pass, both activations a^l and activation function derivatives (f^l)' must be cached at each layer for use in the backward pass.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] matrix-backprop-only-feedforward-no-skip-connections
The clean matrix multiplication formulation of backpropagation applies to feedforward networks with no skip connections and a scalar loss function; more general architectures require the adjoint graph / reverse-mode AD framework.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] single-training-example-infinite-weight-solutions
A single training example may yield infinitely many optimal weight configurations; additional training data or regularization constraints are needed to converge to a unique solution.
- Source: entries/2026/06/21/wiki-Backpropagation-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Backpropagation

### [ACCEPT] cv-three-recognition-types
Computer vision recognition has three types: object recognition (class), identification (instance), and detection (location)
- Source: entries/2026/06/21/wiki-Computer_vision-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] cnns-near-human-imagenet-but-fail-small-objects
CNNs achieve near human-level performance on ImageNet but still struggle with small/thin objects and filtered images
- Source: entries/2026/06/21/wiki-Computer_vision-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] cv-system-pipeline-six-stages
A computer vision system pipeline has 6 stages: image acquisition, pre-processing, feature extraction, detection/segmentation, high-level processing, and decision making
- Source: entries/2026/06/21/wiki-Computer_vision-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] egomotion-vs-optical-flow-vs-tracking
Egomotion is the camera's own 3D rigid motion, optical flow is per-pixel apparent motion, and tracking is following specific objects across frames
- Source: entries/2026/06/21/wiki-Computer_vision-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] ius-three-abstraction-levels
Image-understanding systems operate at three abstraction levels: low (edges/textures/regions), intermediate (boundaries/surfaces/volumes), and high (objects/scenes/events)
- Source: entries/2026/06/21/wiki-Computer_vision-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] vpus-emerged-circa-2016
Vision Processing Units (VPUs) emerged circa 2016 as specialized processors for computer vision workloads alongside CPUs and GPUs
- Source: entries/2026/06/21/wiki-Computer_vision-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] mit-summer-vision-project-1966
The MIT Summer Vision Project (Seymour Papert, 1966) proposed solving computer vision 'in a summer,' famously underestimating the difficulty of the problem
- Source: entries/2026/06/21/wiki-Computer_vision-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] imagenet-ilsvrc-triggered-dl-revolution
The ImageNet Large Scale Visual Recognition Challenge (ILSVRC) triggered the deep learning revolution in CV when AlexNet won in 2012
- Source: entries/2026/06/21/wiki-Computer_vision-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] lecun-bengio-hinton-2015-deep-learning
LeCun, Bengio, and Hinton published the canonical deep learning survey in Nature in 2015, and are known as the 'Godfathers of Deep Learning'
- Source: entries/2026/06/21/wiki-Computer_vision-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] cv-vs-machine-vision-distinction
Computer vision is the broader scientific research field while machine vision refers specifically to industrial/manufacturing application focus
- Source: entries/2026/06/21/wiki-Computer_vision-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] marr-vision-1982-foundational
David Marr's 'Vision' (1982) established the computational theory of vision and is considered the foundational theoretical work for the field
- Source: entries/2026/06/21/wiki-Computer_vision-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] hartley-zisserman-multiple-view-geometry
Hartley & Zisserman's 'Multiple View Geometry in Computer Vision' (2003) is the definitive reference for epipolar geometry, fundamental matrices, and 3D reconstruction from images
- Source: entries/2026/06/21/wiki-Computer_vision-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] cv-field-evolution-three-eras
Computer vision evolved from digital image processing (1980s) to geometric/mathematical vision (1990s) to algorithmic/learning-based vision (2000s-present)
- Source: entries/2026/06/21/wiki-Computer_vision-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] cnn-translation-equivariant-not-invariant
CNNs produce translation-equivariant feature maps but are typically NOT translation-invariant due to downsampling/pooling — a common misconception
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] cnn-weight-sharing-parameter-reduction
CNN weight sharing reduces parameters dramatically: a 5x5 kernel uses 25 weights vs 10,000 for a fully connected layer on 100x100 input
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] depthwise-separable-convolution-structure
Depthwise separable convolution splits into depthwise convolution (spatial, per-channel) followed by pointwise convolution (1x1 kernels) to reduce computation
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] dilated-convolution-expands-receptive-field
Dilated (atrous) convolution expands the receptive field without increasing parameters by interleaving visible and blind regions in the kernel
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] deconvolution-checkerboard-artifact-fix
Deconvolutional (transposed convolution) layers can create checkerboard artifacts; the fix is to use upscale-then-convolve instead
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] cnn-input-tensor-shape
CNN input tensor shape is (batch) x (height) x (width) x (channels)
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] neocognitron-1980-s-layers-c-layers
Fukushima's Neocognitron (1980) introduced S-layers (shared-weight convolutional layers) and C-layers (downsampling/pooling layers), the architectural precursors to modern CNN conv and pooling layers
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] relu-introduced-fukushima-1969
The ReLU activation function was first introduced by Fukushima in 1969, though it was not used in the neocognitron itself
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] lenet5-architecture-1995
LeNet-5 (LeCun et al., 1995) was a 7-layer CNN for handwritten digit recognition on 32x32 images, deployed commercially in bank check reading systems
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] modern-cnns-compute-correlation-not-convolution
Modern CNNs actually compute correlation and call it convolution — reversing the kernel weights doesn't affect the learned function
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] tdnn-first-weight-sharing-with-backprop
The Time Delay Neural Network (TDNN, Waibel 1987) was the first CNN to combine weight sharing with gradient descent/backpropagation training
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] lecun-1989-first-backprop-learned-conv-kernels
LeCun et al. (1989) were the first to use backpropagation to learn convolution kernels directly from images rather than hand-designing them
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] max-pooling-introduced-1990
Max pooling was introduced by Yamaguchi et al. in 1990 for speech recognition; Weng et al. (1993, cresceptron) brought it to computer vision
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] alexnet-2012-gpu-imagenet-ai-boom
AlexNet (2012) was a GPU-trained CNN that won ImageNet LSVRC and catalyzed the modern AI boom
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] cnn-four-distinguishing-features
CNNs have four distinguishing architectural features: 3D neuron volumes, local connectivity, shared weights, and pooling
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] boosting-reduces-bias-bagging-reduces-variance
In ensemble methods, boosting combines high-bias (weak) learners to reduce bias, while bagging combines strong learners to reduce variance.
- Source: entries/2026/06/21/wiki-BiasE28093variance_tradeoff-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

### [ACCEPT] knn-bias-variance-decomposition
In k-NN, the bias² term is a monotone rising function of k, the variance term is σ²/k (decreasing with k), and the third term is irreducible noise σ².
- Source: entries/2026/06/21/wiki-BiasE28093variance_tradeoff-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

### [ACCEPT] 1nn-bias-vanishes-infinite-data
The 1-NN classifier's bias vanishes as the training set size approaches infinity.
- Source: entries/2026/06/21/wiki-BiasE28093variance_tradeoff-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

### [ACCEPT] regularization-biased-lower-mse-than-ols
Regularized estimators (LASSO, ridge regression) are biased but can achieve lower MSE than unbiased OLS due to variance reduction.
- Source: entries/2026/06/21/wiki-BiasE28093variance_tradeoff-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

### [ACCEPT] classification-bv-decomposition-differs-from-regression
Under 0-1 loss in classification, the bias-variance decomposition differs from regression because the variance term depends on the true target label.
- Source: entries/2026/06/21/wiki-BiasE28093variance_tradeoff-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

### [ACCEPT] rl-suboptimality-bias-overfitting-decomposition
In reinforcement learning, suboptimality decomposes into asymptotic bias (algorithm-dependent) and overfitting (data-dependent), analogous to the classical bias-variance tradeoff.
- Source: entries/2026/06/21/wiki-BiasE28093variance_tradeoff-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

### [ACCEPT] mcmc-only-asymptotically-unbiased
MCMC methods are only asymptotically unbiased; controlled bias is sometimes accepted to dramatically reduce variance and overall estimation error.
- Source: entries/2026/06/21/wiki-BiasE28093variance_tradeoff-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

### [ACCEPT] total-prediction-error-decomposition
Total prediction error decomposes as: Bias² + Variance + Irreducible noise (Bayes error).
- Source: entries/2026/06/21/wiki-BiasE28093variance_tradeoff-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

### [ACCEPT] double-descent-phenomenon
Double descent is a phenomenon where test error decreases, increases, then decreases again as model complexity grows far beyond the interpolation threshold, challenging the classical U-shaped tradeoff curve.
- Source: entries/2026/06/21/wiki-BiasE28093variance_tradeoff-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

### [ACCEPT] more-training-data-reduces-variance-not-bias
Increasing training data reduces variance but does not affect bias.
- Source: entries/2026/06/21/wiki-BiasE28093variance_tradeoff-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

### [ACCEPT] larger-datasets-favor-complex-models
Larger training datasets favor lower-bias (more complex) models because variance decreases with more data, shifting the optimal complexity point.
- Source: entries/2026/06/21/wiki-BiasE28093variance_tradeoff-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

### [ACCEPT] cv-began-1960s-mit-summer-project
Computer vision originated in the late 1960s at AI-pioneering universities; the 1966 MIT summer project famously underestimated the difficulty of describing what a camera sees.
- Source: entries/2026/06/21/wiki-Computer_vision-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] neocognitron-inspired-by-visual-cortex
The Neocognitron (Kunihiko Fukushima, 1970s) was a neural network modeled on the primary visual cortex (V1) that prefigured modern CNNs.
- Source: entries/2026/06/21/wiki-Computer_vision-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] cv-and-cg-are-inverses
Computer vision and computer graphics are inverses: CV extracts 3D models from 2D images, while CG renders 2D images from 3D models; augmented reality combines both.
- Source: entries/2026/06/21/wiki-Computer_vision-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] image-processing-vs-cv-input-output
Image processing takes images as input and produces images as output (2D transformations), while computer vision takes images as input and produces interpretations, content analysis, or 3D models as output.
- Source: entries/2026/06/21/wiki-Computer_vision-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] machine-vision-is-industrial-cv
Machine vision is the application of computer vision specifically in industrial settings (factory automation, inspection, process control), emphasizing real-time processing, controlled conditions, and integration with control theory.
- Source: entries/2026/06/21/wiki-Computer_vision-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] cv-market-size-2024
The three largest computer vision market sectors in 2024 by size are: Industry ($5.22B), Medicine ($2.6B), and Military ($996.2M).
- Source: entries/2026/06/21/wiki-Computer_vision-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] autonomous-vehicles-use-slam
Autonomous vehicles use computer vision for navigation, SLAM (Simultaneous Localization and Mapping), obstacle detection, and event detection.
- Source: entries/2026/06/21/wiki-Computer_vision-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] mediapipe-google-cv-edge-framework
MediaPipe is Google's open-source framework for deploying computer vision models to edge devices, supporting face detection, image classification, and object detection.
- Source: entries/2026/06/21/wiki-Computer_vision-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] deep-learning-surpassed-prior-cv-methods
Deep learning has surpassed prior computer vision methods on classification, segmentation, and optical flow benchmarks.
- Source: entries/2026/06/21/wiki-Computer_vision-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] cnn-output-size-formula
The output spatial size of a convolutional layer is computed as (W - K + 2P) / S + 1, where W is input size, K is kernel size, P is padding, and S is stride
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] cnn-same-padding-formula
Same padding (preserving spatial dimensions when stride=1) requires P = (K - 1) / 2 zero-padding
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] max-pooling-2x2-discards-75-percent
Max pooling with 2x2 filters and stride 2 discards 75% of activations, with downsampling caused by the stride not the pooling operation itself
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] relu-activation-definition
ReLU activation is defined as f(x) = max(0, x), a non-saturating function that trains faster than tanh or sigmoid without significant accuracy loss
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] cnn-parameter-sharing-translation-invariance
Parameter sharing in convolutional layers (all neurons in a depth slice share weights and bias) reduces free parameters and provides translation invariance
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] locally-connected-layer-no-weight-sharing
Locally connected layers use independent weights per spatial location instead of parameter sharing, used when different spatial locations should learn different features (e.g., centered face images)
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] softmax-vs-sigmoid-vs-euclidean-loss
Softmax loss is used for mutually exclusive single-class classification, sigmoid cross-entropy for independent multi-label classification, and Euclidean loss for regression to real-valued labels
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] channel-max-pooling-reduces-channels
Channel max pooling (CMP) pools along the channel dimension rather than spatially, reducing channel count while preserving spatial dimensions
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] dropout-probability-conventions
Dropout keeps each node with probability p (typically 0.5 for hidden layers, higher for input layers) during training; at test time outputs are scaled by p to approximate an ensemble of 2^n sub-networks
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] dropconnect-drops-weights-not-neurons
DropConnect generalizes dropout by dropping individual connection weights rather than entire neuron outputs, creating dynamic sparsity on weights
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] dilation-effective-receptive-field
Dilation of d on a kernel of size k expands the effective receptive field to k + (k-1)(d-1) pixels while processing only k*k values; e.g., dilation 2 on 3x3 covers a 5x5 area with 9 parameters
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] stride-gt1-breaks-translation-equivariance
Stride greater than 1 in convolutional or pooling layers violates the Nyquist-Shannon sampling theorem, causing aliasing and breaking translation equivariance
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] fc-layers-break-translation-invariance
Fully connected layers break translation invariance even when all preceding convolutional layers preserve equivariance
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] l2-diffuse-l1-sparse-regularization
L2 regularization (weight decay) penalizes squared weight magnitude and encourages diffuse weight vectors; L1 regularization produces sparse weights; elastic net combines both L1 and L2
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] max-norm-constraint-typical-values
Max norm constraints clamp the L2 norm of weight vectors to an upper bound c (typically 3-4) after each parameter update via projected gradient descent
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] stochastic-pooling-hyperparameter-free
Stochastic pooling replaces deterministic pooling with random selection according to a multinomial distribution over activations; it is hyperparameter-free and equivalent to max pooling over locally deformed copies
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] alexnet-ilsvrc-2012-googlenet-2014
AlexNet won ILSVRC 2012 as the breakthrough CNN for image recognition; GoogLeNet (30+ layers) won ILSVRC 2014 with 0.439 mAP for detection and near-human classification accuracy
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] video-cnn-three-approaches
Three main approaches for video CNNs: (1) 3D convolutions over space+time, (2) two-stream fusion of spatial and temporal CNNs, (3) CNN feature extraction followed by LSTM for inter-frame dependencies
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] transfer-learning-standard-for-small-data
Transfer learning (pretraining on a large dataset then fine-tuning on a small target dataset) is the standard technique when training data is limited, preventing overfitting
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] dqn-cnn-plus-qlearning
Deep Q-Networks (DQN) combine CNNs with Q-learning for reinforcement learning directly from high-dimensional sensory input, demonstrated on Atari 2600 games in 2015
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] alphago-two-cnn-networks
AlphaGo used two CNNs — a policy network for move selection and a value network for position evaluation — driving Monte Carlo Tree Search
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] dilated-convolutions-solve-vanishing-gradients-timeseries
Dilated (atrous) convolutions enable 1D CNNs to learn long-range time series dependencies without the vanishing gradient problem that affects RNNs, making CNNs competitive for forecasting
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] cnn-convolution-is-cross-correlation
The convolution operation in CNNs is technically cross-correlation, not mathematical convolution
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] cnn-biological-origin-hubel-wiesel-1959
CNNs trace their biological inspiration to Hubel and Wiesel's 1959/1968 discovery of receptive fields in cat and monkey visual cortex, with simple and complex cell hierarchies
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] neocognitron-1980-cnn-precursor
Fukushima's Neocognitron (1980) was a self-organizing neural network for shift-invariant pattern recognition and the direct precursor to modern CNNs
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] tdnn-1987-first-weight-sharing
Waibel's Time-Delay Neural Network (1987) applied weight sharing (1D convolution) to speech/phoneme recognition, one of the first practical convolutional architectures
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] lecun-1989-backprop-cnn
LeCun et al. (1989) applied backpropagation to train CNNs for handwritten zip code recognition, establishing the modern CNN training paradigm
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] depthwise-separable-convolutions-xception
Depthwise separable convolutions (Chollet 2017, Xception) factor standard convolutions into depthwise and pointwise operations for computational efficiency, key to mobile architectures
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] transposed-convolution-checkerboard-artifacts
Transposed convolutions (deconvolution) produce checkerboard artifacts as a known failure mode; resize-convolution is the standard fix
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] cnn-not-limited-to-images
CNNs are not limited to image data — they apply wherever local spatial or temporal structure exists, including audio (time domain), spectrograms (frequency domain), time series, and text
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] cnns-approximate-not-exact-translation-invariance
CNNs achieve only approximate translation invariance, not exact — stride and pooling provide partial invariance, and global average pooling at the last layer is one solution for complete translation invariance
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] gan-introduced-goodfellow-2014
Generative Adversarial Networks were introduced by Ian Goodfellow et al. in 2014
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-two-network-minimax-game
A GAN consists of exactly two neural networks (generator and discriminator) trained as a minimax zero-sum game where the generator minimizes and the discriminator maximizes the same objective function
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-implicit-generative-model
GANs are implicit generative models that do not explicitly model the likelihood function and cannot find the latent variable for a given sample, unlike flow-based models or VAEs
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-single-pass-generation
GANs generate a complete sample in one forward pass, unlike autoregressive models (WaveNet, PixelRNN) which generate sequentially token-by-token
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-generator-deconv-discriminator-conv
For image tasks, the GAN generator is typically a deconvolutional neural network and the discriminator is typically a convolutional neural network
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-asymptotically-consistent
GANs are asymptotically consistent estimators of the data distribution due to the universal approximation theorem for neural networks
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-optimal-discriminator-formula
The optimal discriminator for a fixed generator is D*(x) = μ_ref(x) / (μ_ref(x) + μ_G(x)), which is the Radon-Nikodym derivative dμ_ref/d(μ_ref + μ_G)
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-minimizes-jensen-shannon-divergence
The original GAN implicitly minimizes the Jensen-Shannon divergence (not KL divergence) between the generated and real data distributions
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-equilibrium-generator-matches-data
At the unique GAN equilibrium, the generator matches the data distribution exactly (μ̂_G = μ_ref), the discriminator outputs 1/2 everywhere, and the objective value is −2 ln 2
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-optimal-discriminator-deterministic
The optimal GAN discriminator is always deterministic — stochastic discriminators cannot improve the objective, proven via Jensen's inequality
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-equilibria-coincide-original-only
Sequential (minimax/maximin) and Nash equilibria all coincide for the original GAN game, but this equivalence is not guaranteed for general GAN variants
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] reparameterization-trick-independent-discovery
The reparameterization trick was independently discovered for GANs (Goodfellow) and VAEs (Kingma & Welling, Rezende et al.) in 2013-2014
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-mode-collapse-vs-vanishing-gradient
Mode collapse (generator produces limited modes) and vanishing gradient (generator cannot learn) are opposite GAN failure modes caused by the discriminator being too weak vs. too strong, respectively
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-ttur-convergence
The Two Time-Scale Update Rule (TTUR) sets the generator's learning rate lower than the discriminator's and provably converges to a stationary local Nash equilibrium, but does not prevent mode collapse
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] wgan-uses-wasserstein-distance
Wasserstein GAN (WGAN) replaces the JS divergence with the Wasserstein (Earth Mover's) distance, constrains the discriminator's Lipschitz norm, and the discriminator outputs unbounded real values rather than probabilities
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-fid-lower-better-is-higher-better
FID (Fréchet Inception Distance) measures distance between generated and real distributions (lower is better); IS (Inception Score) measures output diversity and quality (higher is better) — both use Inception-v3
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] dcgan-fully-convolutional
DCGAN uses only convolution-deconvolution layers (fully convolutional) for both generator and discriminator with no fully connected layers
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] infogan-three-player-game
InfoGAN is a 3-player, 2-team game (generator + Q network vs. discriminator) that maximizes a variational lower bound on mutual information I(c, G(z,c)) to discover latent labels without supervision
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] bigan-three-player-encoder
BiGAN (Bidirectional GAN) is a 3-player, 2-team game (generator + encoder vs. discriminator) where the discriminator operates on (image, latent) pairs, enabling learned inference
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] cyclegan-four-player-unpaired-translation
CycleGAN is a 4-player, 2-team game that performs unpaired domain translation using two generators, two discriminators, and a cycle-consistency loss enforcing round-trip reconstruction G_Y(G_X(x)) ≈ x
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-non-saturating-loss-original-paper
The non-saturating generator loss (L_G = E[ln D(x)]) was recommended in the original GAN paper for faster convergence, addressing vanishing gradients when the generator is poor
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-synthetic-medical-imaging-privacy
GANs generate synthetic medical images (MRI, PET) to overcome patient privacy barriers that limit access to real medical imaging data
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-particle-physics-simulation-cern
GANs accelerate particle physics simulations at CERN by approximating expensive computational bottlenecks for high-energy jet formation, calorimeter showers, and turbulent flow reconstruction
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-edmond-de-belamy-432500
The GAN-generated painting 'Edmond de Belamy', trained on 15,000 WikiArt portraits, sold for US$432,500 at auction in 2018
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] schmidhuber-adversarial-networks-1991
Schmidhuber's 1991 'artificial curiosity' system using two neural networks in a zero-sum game is a historical precursor to GANs
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] california-deepfake-laws-2019
California signed AB-602 (banning non-consensual synthetic pornography) and AB-730 (banning manipulated political candidate videos within 60 days of elections) in 2019, effective 2020
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] dl-adversarial-examples-imperceptible-perturbations
Adversarial examples are inputs with small, human-imperceptible perturbations that cause neural networks to confidently misclassify them.
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] dl-contrastive-divergence-lacks-convergence-guarantees
Contrastive divergence lacks theoretical convergence and approximation quality guarantees, unlike gradient descent.
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] dl-data-poisoning-corrupts-training-data
Data poisoning is an adversarial attack where false data is injected into training sets to degrade model performance.
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] dl-unsupervised-more-biologically-plausible-than-backprop
Unsupervised deep learning methods (generative models, deep belief networks) are considered more biologically plausible than supervised backpropagation.
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] deep-tamer-2018-arl-ut-austin
Deep TAMER (2018, developed by ARL and UT Austin) combined deep learning with human evaluative reinforcement feedback for robot task learning from video or in-person demonstration.
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] muhlhoff-five-types-machinic-capture
Mühlhoff identified five types of 'machinic capture' for training data collection: gamification, trapping/tracking (CAPTCHAs), social motivation exploitation, information mining, and clickwork.
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] deep-learning-term-introduced-dechter-1986
The term 'deep learning' was introduced by Rina Dechter in 1986 in the context of constraint satisfaction, and was later adopted for neural networks.
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] ivakhnenko-gmdh-first-deep-learning-1965
Ivakhnenko and Lapa (1965–1971) created the first deep learning networks using the Group Method of Data Handling (GMDH) with 8+ hidden layers trained layer by layer.
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] universal-approximation-width-vs-depth
The universal approximation theorem (Cybenko 1989, Hornik 1991) shows a single hidden layer with sufficient width can approximate any continuous function, but depth provides exponentially more efficient representations.
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] vanishing-gradient-identified-hochreiter-1991
The vanishing/exploding gradient problem was identified by Hochreiter in 1991 as the core difficulty in training deep networks.
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] greedy-layerwise-pretraining-bengio-2007
Bengio et al. (2007) demonstrated that greedy layer-wise pretraining — training one layer at a time — could effectively initialize deep networks, reigniting deep learning research.
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] alexnet-imagenet-2012-triggered-dl-revolution
Krizhevsky et al.'s AlexNet winning ImageNet in 2012 is widely considered the event that triggered the modern deep learning revolution.
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] backprop-history-werbos-1982-rumelhart-1986
Werbos (1974/1982) first applied backpropagation to neural networks; Rumelhart, Hinton & Williams (1986) popularized it.
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] cnn-lineage-neocognitron-to-alexnet
CNN lineage runs from Fukushima's Neocognitron (1979–1980) to Zhang's shift-invariant networks (1988) to LeCun's LeNet (1989) to LeNet-5 (1998) to AlexNet (2012).
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] rnn-lineage-jordan-to-lstm-forget-gates
RNN lineage runs from Jordan networks (1986) to Elman networks (1990) to LSTM (Hochreiter & Schmidhuber, 1995/1997) to forget gates (Gers et al., 1999).
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] sgd-traces-to-robbins-monro-1951
Stochastic gradient descent traces to Robbins & Monro (1951), 'A Stochastic Approximation Method'.
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] dl-godfathers-lecun-bengio-hinton-turing-2018
LeCun, Bengio, and Hinton — known as the 'godfathers' of deep learning — received the 2018 Turing Award.
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] self-supervised-learning-dominant-pretraining-paradigm
Self-supervised learning is the dominant pre-training paradigm for modern deep learning, as opposed to supervised or unsupervised learning.
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] rlhf-connects-base-lm-to-aligned-chatbots
RLHF (Reinforcement Learning from Human Feedback) is the key technique connecting base language models to aligned, deployable chatbots.
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] latent-diffusion-model-behind-modern-image-generation
The latent diffusion model is the specific architecture behind modern image and video generation systems, not raw pixel-space diffusion.
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] neural-arch-taxonomy-mlp-cnn-rnn-transformer-mamba
Neural network architecture taxonomy progresses: MLP (feedforward) → CNN (spatial) → RNN/LSTM/GRU (sequential) → Transformer (attention-based, now dominant) → Mamba (state-space, emerging alternative).
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] generative-model-families-autoregressive-diffusion-gan-vae
Four main generative model families: autoregressive (GPT-style), diffusion (Stable Diffusion), adversarial (GAN), and variational (VAE).
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] feature-engineering-is-preprocessing-before-training
Feature engineering is a preprocessing step that occurs before model training, transforming raw data into more effective model inputs.
- Source: entries/2026/06/21/wiki-Feature_engineering-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Feature_engineering

### [ACCEPT] feature-explosion-too-many-features-solved-by-regularization
Feature explosion occurs when identified features become too numerous for effective model estimation; it is addressed by regularization, kernel methods, or feature selection.
- Source: entries/2026/06/21/wiki-Feature_engineering-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Feature_engineering

### [ACCEPT] pca-ica-unsupervised-lda-supervised-dimensionality-reduction
PCA and ICA are unsupervised dimensionality reduction techniques, while LDA (Linear Discriminant Analysis) is supervised.
- Source: entries/2026/06/21/wiki-Feature_engineering-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Feature_engineering

### [ACCEPT] deep-feature-synthesis-beat-615-of-906-human-teams
Deep Feature Synthesis (DFS) beat 615 of 906 human teams in an automated feature engineering competition.
- Source: entries/2026/06/21/wiki-Feature_engineering-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Feature_engineering

### [ACCEPT] nmf-nonnegative-yields-part-based-representations
Non-Negative Matrix Factorization (NMF) with non-negativity constraints yields part-based representations with natural clustering properties.
- Source: entries/2026/06/21/wiki-Feature_engineering-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Feature_engineering

### [ACCEPT] feature-store-centralized-repo-training-and-inference
A feature store is a centralized repository for storing, organizing, versioning, and serving features for both model training and production inference.
- Source: entries/2026/06/21/wiki-Feature_engineering-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Feature_engineering

### [ACCEPT] deep-learning-reduces-but-does-not-eliminate-feature-engineering
Deep learning reduces but does not eliminate the need for feature engineering — representation learning automates some feature construction but manual engineering remains valuable for structured and tabular data.
- Source: entries/2026/06/21/wiki-Feature_engineering-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Feature_engineering

### [ACCEPT] mrdtl-extends-decision-trees-to-relational-databases
Multi-relational Decision Tree Learning (MRDTL) extends decision trees to relational databases using selection graphs as decision nodes and tuple ID propagation to reduce redundant operations.
- Source: entries/2026/06/21/wiki-Feature_engineering-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Feature_engineering

### [ACCEPT] feature-selection-prevents-overfitting
Feature selection prevents overfitting by reducing the number of features, preventing models from becoming too specific to training data.
- Source: entries/2026/06/21/wiki-Feature_engineering-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Feature_engineering

### [ACCEPT] cnn-taxonomy-ai-ml-dl-architecture
CNNs sit in the hierarchy: Artificial Intelligence → Machine Learning → Deep Learning → CNN (as one architecture among many)
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] alexnet-2012-imagenet-deep-learning-revolution
AlexNet (2012) by Krizhevsky, Sutskever, and Hinton won ImageNet by a large margin over shallow methods and is widely considered the start of the deep learning revolution in computer vision
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] fukushima-neocognitron-1980-cnn-precursor
Kunihiko Fukushima created the Neocognitron (1979-1980), the precursor to modern CNNs, which had convolutional and downsampling layers but was not trained by backpropagation
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] vision-transformers-competing-with-cnns
Vision Transformers (ViT) are increasingly competing with or replacing CNNs in computer vision tasks
- Source: entries/2026/06/21/wiki-Convolutional_neural_network-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] deep-learning-cap-depth-definition
Deep learning generally means Credit Assignment Path (CAP) depth greater than 2, where CAP depth measures the chain of transformations from input to output
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] universal-approximation-cap-depth-2
The Universal Approximation Theorem shows a network with CAP depth of 2 can emulate any function, but deeper models extract better features in practice
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] relu-width-universal-approximation-constraint
Lu et al. proved that for ReLU networks, the width must be strictly larger than the input dimension to be a universal approximator; width ≤ input dimension fails
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] deep-learning-term-origin-dechter-1986
The term 'deep learning' was introduced to machine learning by Rina Dechter in 1986 and to neural networks by Igor Aizenberg et al. in 2000
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] probabilistic-interpretation-led-to-dropout
The probabilistic interpretation of neural networks (treating activation nonlinearities as cumulative distribution functions) led to the introduction of dropout as a regularization technique
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] gmdh-1965-first-deep-learning-algorithm
Group Method of Data Handling (GMDH, 1965) by Ivakhnenko and Lapa is considered the first working deep learning algorithm; a 1971 paper demonstrated an 8-layer network
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] amari-1967-first-sgd-trained-deep-mlp
Amari (1967) published the first deep MLP (5 layers) trained by stochastic gradient descent that learned internal representations for non-linearly separable classes
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] relu-introduced-fukushima-1969
The ReLU activation function was introduced by Kunihiko Fukushima in 1969 and is now the most popular activation function for deep learning
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] backpropagation-history-linnainmaa-werbos-rumelhart
Linnainmaa (1970) published the modern form of backpropagation in his master's thesis; Werbos (1982) applied it to neural networks; Rumelhart et al. (1986) popularized it
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] hochreiter-vanishing-gradient-1991-lstm-1995
Hochreiter identified the vanishing gradient problem in his 1991 thesis, then co-invented LSTM (1995) to solve it; the modern LSTM with forget gate came in 1999
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] resnet-2015-skip-connections-degradation
ResNet (2015) by He et al. solved the degradation problem of very deep networks (20-30+ layers) using skip/residual connections
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] bengio-hinton-lecun-2018-turing-award
Bengio, Hinton, and LeCun received the 2018 Turing Award for their contributions to deep learning
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] lenet5-1998-bank-check-recognition
LeNet-5 (1998) by LeCun was used by banks for check digit recognition; CNNs processed 10-20% of US checks by the early 2000s
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] diffusion-models-eclipsed-gans-2022
Diffusion models (DALL-E 2, Stable Diffusion) eclipsed GANs for generative modeling from approximately 2022 onward
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] dropout-regularization-mechanism
Dropout regularization works by randomly omitting hidden units during training to prevent co-adaptation on rare dependencies in the training data
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] l2-weight-decay-l1-sparsity-distinction
L2 regularization is equivalent to weight decay; L1 regularization promotes sparsity — these are distinct regularization strategies
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] sparse-polynomials-exponentially-easier-deep
Sparse multivariate polynomials are exponentially easier to approximate with deep networks than shallow ones, providing a key theoretical justification for network depth
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] openai-300000x-compute-alexnet-to-alphazero
OpenAI found a 300,000x increase in compute used from AlexNet (2012) to AlphaZero (2017), with a 3.4-month doubling time
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] gpus-displaced-cpus-training-2019
GPUs displaced CPUs as the dominant training hardware for large-scale commercial AI by 2019
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] asr-first-major-deep-learning-success
Automatic speech recognition (ASR) was the first major convincing success of deep learning; all major commercial speech systems (Cortana, Alexa, Google Now, Siri, Baidu) use deep learning
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] deep-learning-superhuman-image-recognition
Deep learning surpassed human performance in image recognition: traffic signs (2011) and human faces (2014)
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] alphafold-2020-protein-structure-prediction
AlphaFold (2020) achieved unprecedented accuracy in protein structure prediction from amino acid sequences, far beyond prior computational methods
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] gnome-2023-2m-new-materials-discovery
GNoME (Google DeepMind, November 2023) discovered 2M+ new materials using deep learning for crystal structure stability prediction, validated at 71% success rate via robotic experiments
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] pinns-embed-physical-laws-eliminate-mesh
Physics-Informed Neural Networks (PINNs) embed physical laws (e.g., Navier-Stokes equations) directly into neural network architecture, eliminating the need for mesh generation in computational fluid dynamics
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] graphcast-10-day-weather-under-one-minute
GraphCast predicts weather up to 10 days globally in under a minute, matching state-of-the-art traditional PDE-based systems that take hours
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] gnmt-whole-sentence-english-pivot
Google Neural Machine Translation (GNMT) uses end-to-end LSTM to translate whole sentences (not phrase-by-phrase) and uses English as an intermediate pivot language between most language pairs
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] deep-bsde-overcomes-curse-dimensionality
The Deep BSDE method combines deep learning with backward stochastic differential equations to solve high-dimensional PDEs in financial mathematics, overcoming the curse of dimensionality
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] neural-history-compressor-1991-pretraining
Schmidhuber's neural history compressor (1991) used predictive coding and self-supervised pre-training with a hierarchy of RNNs; in 1993 it solved a task requiring >1000 unfolded layers
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] hinton-2006-deep-belief-networks-rbm-pretraining
Hinton et al. (2006) introduced deep belief networks using layer-wise pre-training with restricted Boltzmann machines, optionally fine-tuned with backpropagation
- Source: entries/2026/06/21/wiki-Deep_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Deep_learning

### [ACCEPT] gan-original-paper-goodfellow-2014-nips
The original GAN paper by Goodfellow, Pouget-Abadie, Mirza, Xu, Warde-Farley, Ozair, Courville, and Bengio was published at NIPS 2014
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] fid-introduced-in-ttur-paper
Fréchet Inception Distance (FID) was introduced in the Two Time-Scale Update Rule (TTUR) paper by Heusel et al. (2017), not as a standalone metrics paper
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gans-no-guaranteed-nash-equilibrium
Farnia & Ozdaglar (ICML 2020) proved that GANs do not always have Nash equilibria, establishing a theoretical limitation of adversarial training
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] stylegan-progression-three-versions
StyleGAN (2019) → StyleGAN2 (2020, 'Analyzing and Improving Image Quality') → StyleGAN3 (2021, 'Alias-Free') were all by Karras et al. at NVIDIA
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] dcgan-bridge-fc-to-conv-gans
DCGAN (Radford, Metz, Chintala 2016) established convolutional architecture best practices for GANs, bridging fully-connected to convolutional GAN architectures
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] cyclegan-unpaired-pix2pix-paired
CycleGAN performs unpaired image-to-image translation while pix2pix performs paired image-to-image translation; both originated from the Berkeley group (Zhu, Isola, Efros et al.)
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] wgan-earth-mover-distance-training-stability
Wasserstein GAN addresses GAN training instability by using the Earth Mover's (Wasserstein) distance as the loss function; theoretical motivation by Arjovsky & Bottou (2017)
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] biggan-scaling-improves-sample-quality
BigGAN (Brock et al., 2018) demonstrated that scaling up GANs with large batch sizes and more parameters dramatically improves sample quality
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-architecture-generator-discriminator-adversarial
A GAN consists of two networks — a generator that creates synthetic data and a discriminator that distinguishes real from fake — trained adversarially in a minimax game
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] diffusion-models-supplanted-gans-text-to-image
Latent diffusion models (Stable Diffusion, DALL-E) have largely supplanted GANs as the dominant approach for text-to-image generation tasks
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-vs-vae-training-paradigm
GANs use adversarial training (minimax game) while VAEs use variational inference with an encoder-decoder structure; both are generative models but with fundamentally different training paradigms
- Source: entries/2026/06/21/wiki-Generative_adversarial_network-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gradient-descent-first-order-negative-gradient
Gradient descent is a first-order iterative optimization algorithm that moves in the negative gradient direction (steepest descent) to find local minima of differentiable functions
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] gradient-descent-update-rule
The gradient descent update rule is x_{n+1} = x_n - η·∇f(x_n), where η is the learning rate (step size) and ∇f is the gradient of the objective function
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] gradient-descent-cauchy-1847-origin
Gradient descent is attributed to Augustin-Louis Cauchy (1847), with independent work by Jacques Hadamard (1907) and convergence analysis for nonlinear problems by Haskell Curry (1944)
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] gradient-orthogonal-to-contour-lines
The gradient at any point is orthogonal to the contour line (level set) passing through that point
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] convex-functions-local-minima-are-global
For convex functions, all local minima are global minima, so gradient descent is guaranteed to converge to the global solution
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] barzilai-borwein-adaptive-step-size
The Barzilai-Borwein method computes an adaptive step size using consecutive gradient differences: η_n = |(x_n - x_{n-1})^T[∇f(x_n) - ∇f(x_{n-1})]| / ‖∇f(x_n) - ∇f(x_{n-1})‖², requiring no line search
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] steepest-descent-linear-systems-spd-step-size
For steepest descent on SPD linear systems Ax=b, the optimal step size is η = (r^T r)/(r^T A r) where r = b - Ax is the residual, derivable analytically from the quadratic structure
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] steepest-descent-residuals-orthogonal
In steepest descent with exact line search, consecutive residual vectors are orthogonal (⟨r_{k+1}, r_k⟩ = 0), which causes characteristic zig-zag convergence behavior
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] conjugate-gradient-sqrt-kappa-vs-steepest-descent-kappa
Steepest descent convergence for linear systems is O(κ) iterations while conjugate gradient is O(√κ), where κ is the spectral condition number — this is why conjugate gradient is preferred
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] any-positive-inner-product-direction-is-descent
Any direction with positive inner product with the negative gradient is a valid descent direction (not just the gradient itself), provided the step size is sufficiently small
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] gd-nonlinear-system-objective
To solve a nonlinear system G(x)=0 via gradient descent, define the objective f(x) = ½ G^T(x) G(x) and minimize it; a solution corresponds to f(x)=0
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] gd-gradient-via-jacobian
The gradient of f(x) = ½ ||G(x)||² is ∇f = J_G^T · G, where J_G is the Jacobian matrix of the system G
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] gd-momentum-update-rule
The heavy ball (momentum) update rule is x^(k+1) = x^(k) - η·∇f(x^(k)) + β·(x^(k) - x^(k-1)), adding a fraction of the previous step to dampen oscillation
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] nesterov-convergence-rate-optimal
Nesterov accelerated gradient achieves O(k^-2) convergence rate for convex Lipschitz-smooth objectives, improving over standard gradient descent's O(k^-1), and this is optimal for first-order methods
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] gd-gradient-flow-ode
Gradient descent is Euler's method applied to the ODE x'(t) = -∇f(x(t)), connecting optimization to dynamical systems theory
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] mirror-descent-generalizes-gd
Gradient descent is a special case of mirror descent using squared Euclidean distance as the Bregman divergence
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] gd-saddle-point-limitation
Gradient descent can slow down or get stuck near saddle points, which is a known limitation for non-convex optimization
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] gd-linear-convergence-conditions
Gradient descent with fixed step size achieves linear convergence (error decreases by a constant factor each iteration) when the objective is both strongly convex and has Lipschitz continuous gradients
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] optimizer-hierarchy-speed-vs-cost
The optimizer hierarchy in terms of convergence speed vs per-iteration cost is: gradient descent → momentum → Nesterov → quasi-Newton (BFGS)
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] cauchy-originated-gradient-method
Cauchy originated the gradient descent method in 1847; Curry formalized steepest descent in 1944
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] gd-first-order-method-taxonomy
Optimization methods are taxonomized as function-based (no gradient, e.g. Nelder-Mead), gradient-based/first-order (e.g. gradient descent), and Hessian-based/second-order (e.g. Newton's method)
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] gd-unconstrained-method
Gradient descent is an unconstrained optimization method; constrained problems require different methods such as barrier, penalty, or augmented Lagrangian methods
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] quasi-newton-approximate-hessian
Quasi-Newton methods (BFGS, L-BFGS, DFP, SR1) approximate second-order Hessian information without computing the full Hessian, offering faster convergence than plain gradient descent
- Source: entries/2026/06/21/wiki-Gradient_descent-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Gradient_descent

### [ACCEPT] ml-definition-mitchell
Tom Mitchell's definition: a computer program learns from experience E with respect to task T and performance measure P if its performance at T, measured by P, improves with E
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-term-coined-1959-samuel
The term 'machine learning' was coined in 1959 by Arthur Samuel at IBM
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-three-paradigms
The three major ML paradigms are supervised learning (classification, regression from labeled data), unsupervised learning (clustering, dimensionality reduction from unlabeled data), and reinforcement learning (sequential decisions via environment interaction)
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-foundations-stats-optimization
Statistics and mathematical optimization compose the foundations of machine learning
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] pac-learning-framework
PAC (Probably Approximately Correct) learning provides the mathematical/statistical framework for describing machine learning; most traditional ML and deep learning algorithms can be described as empirical risk minimization under PAC
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] deep-learning-subset-ml-subset-ai
Deep learning is a strict subset of machine learning, which is a strict subset of artificial intelligence: deep learning ⊂ ML ⊂ AI
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-vs-datamining-distinction
Machine learning focuses on prediction from known properties while data mining focuses on discovery of previously unknown properties; they share methods but differ in goals
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] breiman-two-cultures
Leo Breiman identified two statistical modeling paradigms: the data model (traditional statistics with a priori model selection) vs. the algorithmic model (ML algorithms like Random Forest where data shapes the model)
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] compression-prediction-equivalence
Optimal prediction and optimal data compression are formally equivalent: an optimal predictor of sequence probabilities can be used for optimal compression via arithmetic coding, and vice versa
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] bias-variance-decomposition
The bias-variance decomposition quantifies generalization error: underfitting occurs when the hypothesis is too simple (high bias) and overfitting when it is too complex (high variance)
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] backprop-reinvented-1980s
Backpropagation was reinvented in the mid-1980s by connectionism researchers including Hinton, Rumelhart, and Hopfield, outside mainstream AI/CS
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] gan-introduced-2014-goodfellow
Generative adversarial networks (GANs) were introduced in 2014 by Ian Goodfellow
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-acm-2012-subcategories
The ACM 2012 Computing Classification System categorizes Machine Learning under Artificial Intelligence with sub-categories: Supervised, Unsupervised, Reinforcement, Multi-task, and Cross-validation.
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] solomonoff-1956-inductive-inference-dartmouth
Solomonoff's 'An Inductive Inference Machine' (1956) was presented at the Dartmouth Summer Research Conference and is one of the earliest ML-related works.
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] double-descent-listed-as-core-ai-concept
Double descent is classified as a core AI concept alongside the classical bias-variance tradeoff in the ML taxonomy.
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] rlhf-and-self-supervised-categorized-core-ai
RLHF (Reinforcement Learning from Human Feedback) and self-supervised learning are categorized as core AI concepts, not techniques specific to LLMs.
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] mamba-is-state-space-model-architecture
Mamba is a neural network architecture based on state-space models, listed alongside Transformers, RNNs, CNNs, Autoencoders, GANs, and GNNs as a key architectural family.
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] nlp-three-paradigms-symbolic-statistical-neural
NLP has been driven by three major paradigms historically: symbolic/rule-based (1950s-early 1990s), statistical/ML (1990s-present), and neural network approaches (2010s-present).
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] georgetown-experiment-1954-first-auto-translation
The Georgetown experiment (1954) was the first automatic translation demonstration, translating Russian to English.
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] alpac-report-1966-cut-mt-funding
The ALPAC report (1966) dramatically cut machine translation funding after a decade of unmet expectations, effectively defunding MT research for years.
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] bengio-2003-mlp-beat-ngram-language-model
In 2003, Bengio et al. demonstrated a multi-layer perceptron that outperformed the best statistical n-gram model for language modeling, trained on up to 14 million words.
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] word2vec-mikolov-grew-from-rnn-language-modeling
Word2vec (Mikolov, ~2013) grew from applying simple RNNs to language modeling (2010), catalyzing the deep learning wave in NLP.
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] hmm-pos-tagging-marked-transition-from-rules
The application of Hidden Markov Models to part-of-speech tagging marked the real transition away from rule-based NLP toward statistical methods.
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] stemming-rule-based-vs-lemmatization-dictionary-based
Stemming applies rules to strip affixes (approximate), while lemmatization uses a dictionary to return the true base form (lemma) — lemmatization is more accurate but requires a dictionary.
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] speech-recognition-and-mt-are-ai-complete
Speech recognition and machine translation are classified as AI-complete problems, requiring grammar, semantics, and world knowledge.
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] ner-also-called-token-classification
Named Entity Recognition (NER) identifies proper names and their types (person, location, organization) and is also called token classification.
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] textual-entailment-three-outcomes
Textual entailment classification has three possible outcomes: entails, contradicts, or neutral.
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] coreference-broader-than-anaphora-resolution
Coreference resolution is broader than anaphora resolution — it includes bridging relationships and not just pronoun matching.
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] tokenization-trivial-english-hard-cjk-thai
Tokenization is trivial for space-delimited languages like English but a significant challenge for Chinese, Japanese, and Thai which lack space-delimited word boundaries.
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] conll-multilinguality-1-to-100-languages-1999-2018
CoNLL shared tasks expanded from 1 language (English, 1999) to over 100 languages by 2018, illustrating NLP's growing multilinguality.
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] conll-three-trend-lines-through-2020
Three major NLP trend lines observed from CoNLL Shared Tasks through 2020: increasing cognitive abstraction, growing multilinguality/multimodality, and elimination of symbolic representations.
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] deep-learning-overtook-statistical-nlp-around-2015
Deep learning overtook statistical NLP as the dominant framework around 2015, despite initial skepticism when Richard Socher presented a deep learning tutorial at ACL 2012.
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] chomskyan-linguistics-antagonistic-to-statistical-nlp
Chomskyan linguistics was historically antagonistic to statistical/ML approaches to language, due to the 'poverty of the stimulus' argument and focus on constructed corner cases rather than corpus data.
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] koskenniemi-1983-two-level-morphology
Koskenniemi (1983) introduced two-level morphology, an early computational model for word-form recognition and production, and a classic computational linguistics contribution.
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] ml-three-classical-paradigms
The three classical machine learning paradigms are supervised learning (labelled data), unsupervised learning (no labels), and reinforcement learning (reward signal)
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-no-free-lunch-theorem
The No Free Lunch theorem states that no single machine learning algorithm works best for all problems
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-classification-discrete-regression-continuous
Classification restricts outputs to a limited discrete set of values while regression allows any numerical output within a continuous range
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-self-supervised-subset-unsupervised
Self-supervised learning is a special case (subset) of unsupervised learning that generates supervisory signals from the data itself, not a separate paradigm
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-pca-most-popular-dimensionality-reduction
Principal Component Analysis (PCA) is the most popular dimensionality reduction method, projecting higher-dimensional data to lower-dimensional space by extracting principal variables
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-manifold-hypothesis
The manifold hypothesis proposes that high-dimensional data lies along low-dimensional manifolds, and is a foundational assumption for many dimensionality reduction techniques
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-rl-environments-modelled-as-mdps
Reinforcement learning environments are typically modelled as Markov Decision Processes (MDPs), and RL algorithms do not require exact mathematical models of the MDP
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-sparse-dictionary-learning-np-hard
Sparse dictionary learning (representing examples as sparse linear combinations of basis functions) is strongly NP-hard; k-SVD is the standard heuristic solver
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-deep-learning-hierarchical-features
Deep learning discovers hierarchical features where higher-level abstract features are built from lower-level ones across multiple layers
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-association-rules-no-item-order
Association rule learning discovers relationships between variables in databases (e.g., market basket analysis) but does not consider item order, in contrast with sequence mining
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-ilp-philosophical-induction
The 'inductive' in Inductive Logic Programming refers to philosophical induction (deriving theory from observations), not mathematical induction (proof over well-ordered sets)
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-svm-kernel-trick
Support Vector Machines are non-probabilistic binary linear classifiers that can perform non-linear classification via the kernel trick, which implicitly maps inputs to high-dimensional feature spaces
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-random-forest-ensemble-bootstrapping
Random Forest Regression is an ensemble method that builds multiple decision trees on bootstrapped samples (drawn with replacement) and averages predictions to reduce overfitting
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-ridge-regression-regularization
Ridge regression adds regularization to linear regression to mitigate overfitting by penalizing model complexity
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-logistic-regression-classification
Logistic regression is used for statistical classification despite having 'regression' in the name
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-bayesian-networks-dags
Bayesian networks are probabilistic graphical models using directed acyclic graphs (DAGs) to represent conditional independence among random variables; dynamic Bayesian networks handle sequential data
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-gaussian-processes-bayesian-optimization
Gaussian processes use a covariance function (kernel) to model point relationships and are commonly used as surrogate models in Bayesian optimization for hyperparameter tuning
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-federated-learning-decentralized
Federated learning decentralizes training across user devices, preserving privacy by not sending raw data to a central server (e.g., Google Gboard)
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-classification-trees-vs-regression-trees
Classification trees output discrete labels while regression trees output continuous values; both are types of decision tree models
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-platt-scaling-svm-probabilities
Platt scaling enables probabilistic classification with SVMs, which are otherwise non-probabilistic classifiers
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-holdout-split-convention
The holdout evaluation method conventionally splits data into 2/3 training and 1/3 test sets
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-k-fold-cross-validation
K-fold cross-validation partitions data into K subsets, running K experiments where each fold is used once for evaluation and K-1 folds for training, ensuring all data is used for both
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-bootstrap-sampling-with-replacement
Bootstrap model assessment samples n instances with replacement from the dataset to assess model accuracy
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-sensitivity-tpr-specificity-tnr
Sensitivity (True Positive Rate) is the proportion of actual positives correctly identified; Specificity (True Negative Rate) is the proportion of actual negatives correctly identified
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-auc-roc-interpretation
The ROC curve plots True Positive Rate vs False Positive Rate across thresholds; higher AUC (Area Under the ROC Curve) indicates a better model, providing threshold-independent assessment
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-model-collapse-synthetic-data
Model collapse is the degradation that occurs when models train on uncurated synthetic data or outputs of prior model versions, also called 'model autophagy disorder (MAD)'
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-hallucinations-symbolic-ai-immune
AI hallucinations are AI-generated content containing false information presented as fact; symbolic AI models generally do not hallucinate
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-adversarial-single-pixel
Adversarial examples are deliberately crafted input perturbations that can cause misclassification, sometimes by changing as little as a single pixel
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-netflix-prize-ensemble
The Netflix Prize (2006-2009) was won by an ensemble model achieving 10%+ improvement over Netflix's Cinematch algorithm; Netflix later shifted from ratings to behavioral signals for recommendations
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-gpu-displaced-cpu-2019
By 2019, GPUs displaced CPUs as the primary training hardware for large-scale commercial cloud AI
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-compute-300000x-alexnet-alphazero
OpenAI found a 300,000x increase in compute from AlexNet (2012) to AlphaZero (2017), with a doubling time of 3.4 months
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-tpu-google-2016
Tensor Processing Units (TPUs) are Google-designed ASICs optimized for tensor/matrix computations using matrix multiplication units and high-bandwidth memory, introduced in 2016
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-embedded-optimization-six-techniques
Six key model optimization techniques for embedded ML deployment are: pruning, quantization, knowledge distillation, low-rank factorization, neural architecture search (NAS), and parameter sharing
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-neuromorphic-memristors
Neuromorphic computing emulates biological neural network structure in hardware; physical neural networks use memristors to simulate synaptic function
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-st-georges-1988-bias
St. George's Medical School (1988) is an early documented case of algorithmic discrimination where a computer program denied approximately 60 candidates based on gender or non-European names
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-propublica-recidivism-bias
ProPublica found that an ML recidivism algorithm falsely flagged Black defendants as high risk at twice the rate of white defendants
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-arthur-samuel-1959-coined-term
Arthur Samuel coined the term 'machine learning' in 1959 using the game of checkers as a testbed; the famous 'without being explicitly programmed' phrasing is a later paraphrase, not a direct quote
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-mitchell-1997-formal-definition
Tom Mitchell's (1997) formal definition: a computer program learns from experience E with respect to task T and performance measure P if its performance on T as measured by P improves with experience E
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-breiman-two-cultures-2001
Breiman's 'Statistical Modeling: The Two Cultures' (2001) is a landmark paper on the divide between data-modeling (statistics) and algorithmic-modeling (ML) approaches
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-compression-learning-equivalence
Prediction and compression are formally equivalent; language models can exceed PNG/FLAC in lossless compression (Delétang et al., 2023: 'language modeling is compression')
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-pattern-recognition-same-field
Machine learning and pattern recognition are described as 'two facets of the same field' (Bishop, 2006)
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-gans-goodfellow-2014
Generative Adversarial Networks (GANs) were introduced by Goodfellow et al. in 2014 at NeurIPS
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-alphago-2016-deep-nn-tree-search
AlphaGo (Silver et al., 2016) demonstrated deep neural networks combined with tree search mastering the game of Go
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] ml-rule-based-interpretability
Rule-based machine learning (RBML) automatically discovers interpretable rules from data and is valued for interpretability in healthcare, fraud detection, and cybersecurity, distinguishing it from black-box approaches like deep learning
- Source: entries/2026/06/21/wiki-Machine_learning-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Machine_learning

### [ACCEPT] cybenko-universal-approximation-theorem-1989
Cybenko's Universal Approximation Theorem (1989) proves that a single hidden layer with sigmoidal activation functions can approximate any continuous function on compact subsets of R^n.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-9.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] cascade-correlation-constructive-algorithm
Cascade-Correlation (Fahlman & Lebiere, 1991) is a constructive learning algorithm that dynamically adds hidden units during training rather than fixing network architecture in advance.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-9.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] rnn-turing-completeness-siegelmann-sontag
Siegelmann & Sontag (1994) proved that recurrent neural networks with rational weights are Turing-complete, and with real-valued weights they are super-Turing.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-9.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] overfitting-definition-noise-as-signal
Overfitting occurs when a model extracts noise (residual variation) from training data as if it were genuine structure, resulting in excellent training performance but poor generalization to unseen data.
- Source: entries/2026/06/21/wiki-Overfitting-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Overfitting

### [ACCEPT] overfitting-diagnostic-signature
The diagnostic signature of overfitting is training error decreasing while validation error simultaneously increases.
- Source: entries/2026/06/21/wiki-Overfitting-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Overfitting

### [ACCEPT] one-in-ten-rule-overfitting
The one-in-ten rule is a guideline recommending approximately 10 observations per independent variable in logistic or Cox regression to avoid overfitting.
- Source: entries/2026/06/21/wiki-Overfitting-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Overfitting

### [ACCEPT] freedmans-paradox-spurious-significance
Freedman's paradox states that when many explanatory variables are unrelated to the target, some will be falsely found statistically significant, leading to overfitting.
- Source: entries/2026/06/21/wiki-Overfitting-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Overfitting

### [ACCEPT] parameters-geq-observations-memorization
When a model's parameter count equals or exceeds the number of observations, it can perfectly memorize training data but will generalize poorly.
- Source: entries/2026/06/21/wiki-Overfitting-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Overfitting

### [ACCEPT] underfitting-high-bias-low-variance
Underfitting produces high bias and low variance, while overfitting produces low bias and high variance.
- Source: entries/2026/06/21/wiki-Overfitting-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Overfitting

### [ACCEPT] benign-overfitting-overparameterization
Benign overfitting — where a model perfectly fits noisy training data yet still generalizes well — requires overparameterization where the number of unimportant directions in parameter space significantly exceeds the sample size.
- Source: entries/2026/06/21/wiki-Overfitting-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Overfitting

### [ACCEPT] bias-variance-tradeoff-three-components
The bias-variance tradeoff decomposes total prediction error into three components: bias error, variance error, and irreducible error.
- Source: entries/2026/06/21/wiki-Overfitting-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Overfitting

### [ACCEPT] regularization-dual-purpose-over-under-fitting
Regularization is a dual-purpose tool: it primarily prevents overfitting by penalizing model complexity, but tuning it too aggressively causes underfitting.
- Source: entries/2026/06/21/wiki-Overfitting-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Overfitting

### [ACCEPT] random-forest-ensemble-majority-vote-mean
Random forests output majority vote for classification and mean prediction for regression, aggregated across all trees in the ensemble.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] random-forest-feature-subset-defaults
Random forest default feature subset sizes per split are sqrt(p) for classification and p/3 for regression, where p is the total number of features.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] random-forest-oob-error-no-test-set
Out-of-bag (OOB) error in random forests provides a valid generalization error estimate without requiring a separate test set, since each training sample is left out of approximately 37% of bootstrap samples.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] random-forest-reduces-variance-not-bias
Random forests reduce variance (not bias) compared to individual decision trees by averaging many decorrelated trees.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] extratrees-vs-random-forest-differences
ExtraTrees (Extremely Randomized Trees) differs from standard random forests in two ways: (1) each tree is trained on the full dataset without bootstrap sampling, and (2) split cut-points are chosen randomly rather than optimally.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] random-forest-more-trees-no-overfitting
Adding more trees to a random forest does not cause overfitting; training and test error plateau after a sufficient number of trees.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] random-forest-breiman-2001-formulation
Leo Breiman (2001) formulated the modern random forest by combining bagging, random feature selection at each split, out-of-bag error estimation, and permutation importance.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] mdi-importance-biased-high-cardinality
Mean decrease in impurity (MDI) feature importance is biased toward high-cardinality features and reflects training fit rather than generalization performance.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] permutation-importance-correlated-features-failure
Permutation importance undervalues features in large correlated groups because permuting one correlated feature has little effect when others carry redundant information; the fix is to permute correlated groups together.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] random-forest-adaptive-neighborhood-kernel
Random forests can be interpreted as adaptive kernel smoothers: the prediction is a weighted average over training points, where the weight function (defined by shared leaf membership across trees) adapts to local feature relevance, unlike k-NN's fixed-shape neighborhoods.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] nlp-classified-ai-complete
Natural Language Processing is classified as AI-complete, meaning full NLP requires solving the general AI problem
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] nlp-distributional-semantics-models
Key distributional semantics models in NLP include BERT, Word2Vec, GloVe, fastText, Transformers, LSTM, and Seq2Seq
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] nlp-machine-translation-approaches
Machine translation approaches include rule-based, statistical, example-based, transfer-based, neural, and computer-assisted methods
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] nlp-standard-language-resources
Standard NLP language resources include WordNet (lexical database), FrameNet (semantic frames), Universal Dependencies (syntactic annotation), and PropBank (predicate-argument structures)
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] nlp-text-segmentation-pipeline
The NLP text segmentation pipeline proceeds: lexical analysis → stemming/lemmatization → sentence segmentation → word segmentation → chunking
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] hallucination-recognized-nlp-taxonomy
Hallucination is formally recognized as a related problem in the NLP field taxonomy
- Source: entries/2026/06/21/wiki-Natural_language_processing-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Natural_language_processing

### [ACCEPT] deep-nn-at-least-two-hidden-layers
A neural network is classified as 'deep' if it has at least two hidden layers
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] neuron-computation-formula
An artificial neuron computes: output = activation_function(sum(weight_i * input_i) + bias), applying a non-linear activation function to the weighted sum of inputs plus a bias term
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] feedforward-nn-is-dag
Feedforward neural networks form a directed acyclic graph (DAG) with no connections to same-layer or previous-layer neurons, while recurrent networks allow cycles
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] cnn-local-connectivity
Convolutional layers differ from fully connected layers by connecting each neuron to only a local subset of neurons in the previous layer rather than all neurons
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] mcculloch-pitts-1943-first-nn-model
McCulloch and Pitts (1943) created the first computational model for neural networks, a non-learning model capable of representing logical functions
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] rosenblatt-1958-perceptron
Frank Rosenblatt invented the perceptron in 1958, the first implemented learning neural network, limited to linearly separable problems
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] minsky-papert-1969-xor-ai-winter
Minsky and Papert's 1969 book 'Perceptrons' proved single-layer perceptrons cannot solve XOR, triggering an AI winter by deflating research funding
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] gmdh-1965-first-deep-learning
Ivakhnenko and Lapa's Group Method of Data Handling (GMDH, 1965) was the first working deep learning algorithm; an 8-layer network was trained by 1971
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] relu-introduced-1969-fukushima
The ReLU activation function was introduced by Kunihiko Fukushima in 1969 and became the most common activation function in modern deep learning
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] backpropagation-lineage
Backpropagation lineage: chain rule (Leibniz 1673) → control theory precursor (Kelley 1960) → modern automatic differentiation (Linnainmaa 1970) → applied to neural networks (Werbos 1982) → popularized (Rumelhart et al. 1986)
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] lstm-forget-gate-1999
LSTM was introduced by Hochreiter and Schmidhuber in 1997 to solve the vanishing gradient problem (identified 1991), with the forget gate added in 1999 completing the standard architecture
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] transformer-2017-quadratic-context
The Transformer architecture (2017, 'Attention Is All You Need') uses self-attention with quadratic computation cost in context window size and became the basis for GPT, Gemini, Grok, DeepSeek, and Qwen
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] gans-2014-eclipsed-by-diffusion
GANs were introduced by Goodfellow in 2014 (concept traces to Schmidhuber's 'artificial curiosity' 1991), reached peak quality with StyleGAN (2018), and were later eclipsed by diffusion models for image generation
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] resnets-highway-nets-2015-degradation
Highway networks (May 2015) and ResNets (December 2015) solved the degradation problem in very deep networks of 20-30+ layers
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] alexnet-2012-imagenet
AlexNet (Krizhevsky, Sutskever, Hinton, 2012) won ImageNet and catalyzed the modern deep learning era
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] ann-hierarchy-deep-learning-ml-ai
ANNs are the foundational substrate for deep learning, which is a subset of machine learning, which is an application of artificial intelligence
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-10.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] ann-bridge-four-fields
Artificial neural networks sit at the intersection of four major fields: Artificial Intelligence, Complex Systems, Control Theory, and Neuroscience
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-10.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] nn-layers-hierarchical-abstraction
Neural network layers provide hierarchical abstraction: bottom layers handle raw data, intermediate layers progressively increase abstraction (e.g., pixels → edges → objects), and top layers produce final results
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] self-supervised-pretraining-1991-schmidhuber
Self-supervised pre-training originated with Schmidhuber's neural history compressor in 1991, predating its use in GPT by decades
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] backpropagation-computes-loss-gradient-wrt-weights
Backpropagation calculates the gradient of the loss function with respect to weights, propagating error from output nodes back through the network to input nodes.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] loss-function-desirable-properties
Desirable properties of a loss function include convexity, differentiability, and robustness.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] learning-rate-speed-accuracy-tradeoff
High learning rates train faster with lower accuracy; low learning rates train slower with potentially greater accuracy.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] four-major-learning-paradigms
The four major neural network learning paradigms are supervised, unsupervised, reinforcement, and self-supervised learning.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] reinforcement-learning-modeled-as-mdp
Reinforcement learning is formally modeled as a Markov decision process (MDP) with state transitions governed by probability distributions.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] hyperparameters-set-before-training
Hyperparameters (learning rate, batch size, number of layers/nodes) are set before training begins and tuned between training runs, not during them.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] mini-batch-gradient-descent-compromise
Mini-batch gradient descent is a compromise between stochastic (per-sample) and batch (full-dataset) weight updates.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] stochastic-training-avoids-local-minima
Stochastic training (adjusting weights after each individual sample) introduces noise that helps avoid getting stuck in local minima.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] self-supervised-learning-two-step-process
Self-supervised learning generates supervisory signals from data itself via augmentation/transformation, using a two-step process: a pretext task with pseudo-labels, then supervised or unsupervised fine-tuning.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] universal-approximation-theorem-no-architecture-spec
The universal approximation theorem proves multilayer perceptrons can approximate any function, but does not specify how many neurons, what topology, or what weights are needed.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] recurrent-networks-turing-completeness
A recurrent neural network with rational-valued weights has universal Turing machine power; irrational weights theoretically yield super-Turing power (though the latter claim has failed verification).
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] vc-dimension-half-information-capacity
The VC dimension for arbitrary inputs equals half the information capacity of a perceptron.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] softmax-converts-outputs-to-posterior-probabilities
The softmax function (y_i = e^(x_i) / sum_j(e^(x_j))) converts raw output scores into a probability distribution over classes, interpretable as posterior probabilities for classification.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] spectral-bias-low-to-high-frequencies
Neural networks with small parameter counts exhibit spectral bias (frequency principle): they fit target functions from low to high frequencies, and deeper networks are more biased toward low frequencies.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] infinite-width-networks-behave-linearly
As neural network width approaches infinity, behavior is well-described by first-order Taylor expansion, inheriting convergence properties of affine (linear) models.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] gans-adversarial-generator-discriminator
Generative Adversarial Networks (GANs) pit two networks against each other: one generates content and the other discriminates real from fake, driving each other to improve.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] transformers-use-token-to-token-attention
Transformers use attention mechanisms to compare every token against every other token in the input sequence.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] three-concept-drift-monitoring-strategies
Three concept drift monitoring strategies are: error-based (comparing predictions to ground truth), data distribution monitoring (statistical tests on inputs), and representation monitoring (tracking hidden-layer embedding distributions).
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] nn-core-advantage-nonlinear-modeling
Neural networks' core advantage for broad applicability is their ability to model and reproduce nonlinear processes.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] nn-black-box-motivates-xai
Neural networks are 'black box' models lacking interpretability, which motivates research in Explainable AI (XAI) and hybrid neural-symbolic approaches.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] amazon-2018-recruiting-bias-example
Amazon's 2018 recruiting tool penalized women due to male-skewed training data, demonstrating that biased training data produces biased outputs.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] feedforward-network-dag-no-cycles
In a feedforward neural network, information flows in one direction only (input to output) with no cycles or feedback loops — the dependency graph is a directed acyclic graph (DAG).
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] single-layer-feedforward-equation
A single-layer feedforward network computes output as y_q = K(Σ_i(x_i · w_iq) − b_q), where K is the activation function, w_iq are weights, and b_q is the bias.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] activation-function-provides-nonlinearity
The activation function is what gives multi-layer networks their representational power; without non-linearity, stacking layers adds no capacity and the network collapses to a linear transformation.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] single-layer-only-linearly-separable
A single-layer network (no hidden layer) can only learn linearly separable functions; hidden layers are required for non-linear decision boundaries.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] fully-connected-layer-parameter-count
The number of learnable parameters in a single fully-connected layer is (p × q) weights + q biases, where p is the number of inputs and q is the number of outputs.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] mcculloch-pitts-1943-first-neuron-model
The McCulloch-Pitts neuron (1943) is the first mathematical model of an artificial neuron, framing neural activity as logical threshold computation.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] rosenblatt-perceptron-first-trainable-nn
Frank Rosenblatt's Perceptron (1957-1958) was the first trainable single-layer neural network.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] minsky-papert-1969-xor-limitation
Minsky and Papert (1969) demonstrated that single-layer perceptrons cannot compute XOR (non-linearly-separable functions), contributing to the first AI winter for neural networks.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] backpropagation-history-werbos-not-rumelhart
Backpropagation was not invented by Rumelhart/Hinton/Williams (1986) — they popularized it; Werbos described it in 1975 (thesis) and 1982 (publication), and Linnainmaa formalized reverse-mode automatic differentiation in 1970.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] transformer-attention-is-all-you-need-2017
The transformer architecture was introduced by Vaswani et al. in 'Attention Is All You Need' (2017, arXiv:1706.03762), replacing recurrence with self-attention.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] neocognitron-1980-cnn-precursor
Fukushima's Neocognitron (1979-1980) introduced convolutional structure and pooling for shift-invariant pattern recognition, serving as the direct architectural precursor to CNNs.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] hopfield-networks-1982-associative-memory
Hopfield networks (1982) are recurrent networks with energy-based dynamics and associative memory; John Hopfield received the Nobel Prize in Physics (2024) for this work.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] transfer-learning-dates-to-1976
Transfer learning dates to 1976 (Bozinovski), far earlier than the 2010s as commonly assumed.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] hebbian-learning-1949-neurons-fire-together
Donald Hebb's 'The Organization of Behavior' (1949) proposed that synaptic connections strengthen when neurons fire together, forming the basis for unsupervised learning rules.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] sgd-foundation-robbins-monro-1951
The Robbins-Monro stochastic approximation method (1951) provides the mathematical foundation for stochastic gradient descent.
- Source: entries/2026/06/21/wiki-Neural_network_28machine_learning29-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Neural_network_%28machine_learning%29

### [ACCEPT] kerf-pools-observations-across-trees
Kernel Random Forests (KeRF) compute predictions by pooling all observations falling in cells containing x across all trees before normalizing, rather than averaging per-tree predictions first as standard random forests do.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] kerf-connection-function-is-kernel
The KeRF connection function K_{M,n}(x, z) equals the proportion of trees in which x and z fall in the same cell, and this serves as the kernel for a Nadaraya-Watson-style kernel regression estimator.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] centered-kerf-converges-faster-than-uniform
Centered KeRF converges at rate O(n^{-1/(3 + d log 2)} · (log n)^2) while Uniform KeRF converges at O(n^{-2/(6 + 3d log 2)} · (log n)^2), making Centered KeRF strictly faster, under Lipschitz target function, uniform X on [0,1]^d, and Gaussian noise.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] rf-kerf-approximation-bound-cell-occupancy
The approximation bound between standard RF and KeRF predictions is |m_{M,n}(x) - m̃_{M,n}(x)| ≤ ((b_n - a_n)/a_n) · m̃_{M,n}(x), where a_n and b_n bound cell occupancy counts, so tighter bounds occur when all cells have similar counts.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] scornet-formalized-kerf-2015
Scornet (2015) formalized the KeRF definitions and proved consistency results, building on earlier observations by Breiman and the RF-kernel connection shown by Lin & Jeon (2006).
- Source: entries/2026/06/21/wiki-Random_forest-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] rf-primary-disadvantage-interpretability
The primary disadvantage of random forests compared to single decision trees is loss of interpretability, not loss of accuracy.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] born-again-tree-recovers-interpretability
Model compression via 'born-again' decision trees can transform a random forest into a single minimal decision tree that faithfully reproduces the ensemble's decision function, recovering interpretability.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] rf-no-benefit-linear-correlation
Random forests may not improve accuracy over a single decision tree when features are linearly correlated with the target variable.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] rf-struggles-multiple-categorical-variables
Random forests underperform on problems involving multiple categorical variables.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] four-interpretable-model-families
The four families of easily interpretable ML models are decision trees, linear models, rule-based models, and attention-based models.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] rf-impurity-importance-biased-high-cardinality
Default impurity-based feature importance in random forests is biased toward features with more categories or higher cardinality; permutation importance is the recommended unbiased alternative.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] extra-trees-randomize-split-threshold
Extremely Randomized Trees (Extra-Trees) differ from standard random forests by also randomizing the split threshold at each node, not just the feature subset, further reducing variance.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] rf-oob-error-internal-validation
Out-of-Bag (OOB) error provides an internal estimate of random forest generalization error without needing a separate validation set, using the ~37% of samples not selected in each bootstrap.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] rf-two-sources-of-randomness
Random forests introduce two sources of randomness: (1) bootstrap sampling of training data (bagging), and (2) random subset of features considered at each split.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] rf-consistency-proven-only-simplified-models
Consistency of random forests has been proven only for simplified models, not for the full Breiman algorithm in general settings.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] rf-trademark-registered
'Random Forests' is a registered U.S. trademark (registration #3185828, 2006) held by Health Care Productivity, Inc.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] mixed-effects-rf-for-clustered-data
Mixed-effects random forests (Hajjem et al., 2014) extend random forests to handle clustered/hierarchical data by incorporating random effects, bridging ensemble methods with multilevel modeling.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] random-multinomial-logit-extends-rf
Random Multinomial Logit (Prinzie & Poel, 2007) generalizes random forests beyond decision tree base learners to multinomial logit and Naive Bayes classifiers.
- Source: entries/2026/06/21/wiki-Random_forest-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Random_forest

### [ACCEPT] rnn-hidden-state-sequential-processing
Recurrent neural networks process sequential data by maintaining a hidden state updated at each time step based on current input and the previous hidden state, enabling temporal dependency capture.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] lstm-solves-vanishing-gradient
LSTM (Long Short-Term Memory), invented by Hochreiter and Schmidhuber (1995/1997), uses gating mechanisms to preserve long-term dependencies and was specifically designed to address the vanishing gradient problem in vanilla RNNs.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] gru-lightweight-lstm-alternative
GRU (Gated Recurrent Unit) is a more computationally efficient alternative to LSTM with fewer parameters while also addressing the vanishing gradient problem.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] seq2seq-encoder-decoder-2014
The encoder-decoder (seq2seq) architecture uses two RNNs (typically LSTMs) for sequence transduction, originated circa 2014, and was instrumental in developing attention mechanisms that led to the transformer architecture.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] transformers-replaced-rnns-for-nlp
Transformers have largely replaced RNNs for NLP tasks due to superior parallelizability and long-range dependency handling, but RNNs remain preferred for real-time processing and computationally constrained environments.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] bidirectional-rnn-processes-both-directions
Bidirectional RNNs (BRNNs) process input sequences in both forward and backward directions simultaneously, enabling access to both past and future context at each time step.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] hopfield-network-connects-rnn-stat-mech
The Hopfield network (1982) established a connection between recurrent neural networks and statistical mechanics via the Sherrington-Kirkpatrick spin glass model.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] lstm-gru-are-gated-rnn-variants
LSTM (Long Short-Term Memory) and GRU (Gated Recurrent Unit) are gated variants of RNNs designed to address the vanishing gradient problem
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] transformers-replaced-rnns-using-attention
Transformers largely replaced RNNs for sequence tasks by using attention mechanisms instead of recurrence
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] echo-state-network-reservoir-computing
Echo State Networks are a reservoir computing approach to RNNs where only the output weights are trained
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] mamba-state-space-model-competes-rnns-transformers
Mamba is a state-space model architecture that competes with both RNNs and Transformers for sequence modeling tasks
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] bptt-extends-backprop-for-recurrent-architectures
Backpropagation through time (BPTT) is an extension of standard backpropagation for training recurrent neural network architectures
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] rl-is-third-ml-paradigm
Reinforcement learning is one of three core machine learning paradigms alongside supervised and unsupervised learning, distinguished by learning from interaction and reward signals rather than static datasets
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] rl-environment-modeled-as-mdp
The RL environment is typically modeled as a Markov decision process (MDP) with four components: state space S, action space A, transition probability P, and reward function R
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] epsilon-greedy-exploration-strategy
The ε-greedy strategy selects the best-known action with probability (1 − ε) and a random action with probability ε to balance exploration and exploitation
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] pomdp-extends-mdp-partial-observability
When the agent observes only a subset or noisy observations of the state, the problem becomes a Partially Observable MDP (POMDP) rather than a standard MDP
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] rl-called-approximate-dynamic-programming
Reinforcement learning is also known as 'approximate dynamic programming' or 'neuro-dynamic programming' in operations research and control theory literature
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] optimal-policy-deterministic-stationary
An optimal RL policy can always be found among deterministic stationary policies — no need to search stochastic or history-dependent policies
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] q-star-sufficient-for-optimal-action
Knowing Q* (the optimal action-value function) alone is sufficient to act optimally by choosing argmax_a Q*(s,a), whereas V* alone requires the transition model
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] td-lambda-interpolates-mc-and-td
TD(λ) with λ=0 relies entirely on Bellman equations (pure TD), while λ=1 is equivalent to Monte Carlo with no Bellman reliance; λ provides continuous interpolation between the two
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] monte-carlo-rl-requires-episodic-tasks
Monte Carlo RL methods require episodic tasks and update only after episode completion; they do not require knowledge of environment dynamics
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] dyna-algorithm-learns-model-generates-simulated-transitions
The Dyna algorithm learns a model from real experience and generates simulated transitions to supplement real ones for value function updates, improving sample efficiency
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] actor-critic-combines-value-and-policy
Actor-critic methods combine value function estimation (critic) with direct policy optimization (actor) and belong to the Generalized Policy Iteration (GPI) class
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] dqn-discrete-actions-continuous-states
DQN bridges discrete action spaces with continuous state spaces; DDPG extends this to continuous action spaces
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] ppo-trpo-a3c-on-policy-advantage
PPO, TRPO, and A3C are on-policy algorithms that use the advantage function, while SAC, TD3, and DDPG are off-policy algorithms
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] inverse-rl-infers-reward-from-demonstrations
Inverse reinforcement learning (IRL) infers the reward function from observed expert behavior; MaxEnt IRL is a special case of Random Utility IRL (RU-IRL)
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] safe-rl-uses-cvar-constrained-optimization
Safe RL optimizes policies while respecting safety constraints using CVaR or constrained optimization, but CVaR optimization requires care to avoid gradient bias and 'blindness to success'
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] td-learning-models-dopamine-neuroscience
TD learning models dopamine-based learning in neuroscience; dopaminergic projections from substantia nigra to basal ganglia encode prediction error signals
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] rlhf-trains-reward-model-from-human-preferences
RLHF trains a reward model from human preference ratings, then uses that reward model to guide RL policy optimization — it is not direct human-in-the-loop RL
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] instructgpt-first-major-rlhf-application
InstructGPT was the first major application of RLHF to language models for instruction-following; ChatGPT built on this approach for response quality and safety
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] deepseek-r1-rl-without-sft
DeepSeek-R1 uses large-scale RL without supervised fine-tuning (SFT) as a preliminary step and achieves reasoning performance comparable to OpenAI-o1-1217
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] offline-rl-uses-historical-logs-no-live-interaction
Offline RL optimizes policies using fixed datasets of past interactions (e.g., conversation logs) without requiring live environment interaction during training
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] rnn-standard-function-signature
A standard RNN is defined as f_θ: (x_t, h_t) → (y_t, h_{t+1}), mapping an input and hidden state to an output and updated hidden state.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] rnn-unfolded-diagram-shows-timesteps-not-layers
Unfolding an RNN across time steps produces a diagram that resembles layers, but these represent time steps, not depth layers.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] birnn-concatenates-forward-backward-outputs
Bidirectional RNNs concatenate forward and backward outputs at each position (they do not average or add them).
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] rnn-config-vs-architecture-orthogonal
RNN configuration (data flow wiring: standard, stacked, bidirectional, encoder-decoder) and architecture (cell design: LSTM, GRU, vanilla) are orthogonal — any configuration can use any architecture.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] elmo-is-stacked-bidirectional-lstm
ELMo (2018) is a stacked bidirectional LSTM that takes character-level inputs and produces word-level embeddings.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] encoder-decoder-rnn-precursor-to-transformer
Encoder-decoder RNNs were state-of-the-art for neural machine translation from 2014–2017 and were a direct precursor to the Transformer architecture.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] attention-added-to-address-fixed-size-bottleneck
The attention mechanism was added to encoder-decoder RNNs to address the bottleneck of compressing all input information into a fixed-size vector.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] lstm-designed-to-solve-vanishing-gradient
LSTM was designed specifically to solve the vanishing gradient problem using forget gates as the key mechanism.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] lstm-learns-over-thousands-millions-timesteps
LSTM can learn dependencies across thousands or millions of time steps by allowing error to flow backward through unlimited virtual layers.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] gru-fewer-params-than-lstm-no-output-gate
GRU (introduced 2014) has fewer parameters than LSTM because it lacks an output gate; empirical performance is comparable with no clear winner.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] elman-network-context-from-hidden-layer
Elman networks feed hidden layer output to context units via fixed weight-one connections; Jordan networks feed output layer to context units (state layer) with self-recurrent connections.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] rnns-are-turing-complete
RNNs are Turing complete — they can run arbitrary programs on arbitrary input sequences.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] hopfield-network-requires-stationary-inputs
Hopfield networks require stationary (non-sequential) inputs, guarantee convergence, and when trained with Hebbian learning act as content-addressable memory.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] echo-state-network-only-trains-output-weights
Echo state networks have a sparsely connected random hidden layer where only output weights are trainable; the hidden layer is fixed.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] ntm-differentiable-end-to-end
Neural Turing Machines couple an RNN to external memory analogous to a Turing machine but are differentiable end-to-end and trainable with gradient descent.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] fully-recurrent-nn-most-general-topology
A fully recurrent neural network (every neuron's output connects to every neuron's input) is the most general RNN topology — all other architectures are special cases with some weights set to zero.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] teacher-forcing-feeds-ground-truth-not-predictions
Teacher forcing feeds ground-truth output tokens (not model predictions) to the decoder during training to prevent error accumulation across the sequence.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] bptt-vs-rtrl-locality-tradeoff
BPTT is O(weights) per step but requires storing all activations (local in space, not time); RTRL is O(hidden × weights) per step but is online (local in time, not space).
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] vanishing-gradient-exponential-decay
The vanishing gradient problem causes error gradients to decay exponentially with the time lag between relevant events, preventing standard RNNs from learning long-range dependencies.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] ctc-loss-for-variable-alignment
Connectionist Temporal Classification (CTC) is a loss function for sequence modeling where input-output alignment timing is variable, such as speech recognition.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] indrnn-each-neuron-own-past-state-only
IndRNN neurons receive only their own past state (not other neurons' states), eliminating inter-neuron dependencies within a layer and preventing vanishing/exploding gradients.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] neural-history-compressor-1993-deep-learning
The neural history compressor solved a task requiring 1000+ unfolded RNN layers in 1993, using an unsupervised stack of RNNs where each level only receives inputs unpredictable to the level below.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] second-order-rnns-use-weight-tensors
Second-order RNNs use weight tensors w_ijk (3-index) instead of matrices, enabling direct mapping to finite-state machines in both training and representation.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] finite-impulse-rnn-dag-infinite-impulse-cyclic
Finite-impulse RNNs are DAGs (unrollable to feedforward nets); infinite-impulse RNNs are directed cyclic graphs (cannot be unrolled).
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] ctrnn-discrete-equivalent-via-shannon-sampling
Discrete-time RNNs are equivalent to continuous-time RNNs (CTRNNs) via the Shannon sampling theorem after low-pass filtering.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] lstm-proposed-1997-hochreiter-schmidhuber
LSTM was proposed by Hochreiter & Schmidhuber in 1997 (doi:10.1162/neco.1997.9.8.1735), addressing the vanishing gradient problem identified in Hochreiter's 1991 diploma thesis.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] gru-proposed-2014-cho-et-al
GRU was proposed by Cho et al. in 2014 (arXiv:1406.1078); Gruber & Jockisch (2020) found GRU cells more specific and LSTM cells more sensitive.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] transformer-replaced-recurrence-with-self-attention-2017
The Transformer (Vaswani et al. 2017, 'Attention is All You Need') replaced recurrence with self-attention and became dominant for sequence modeling.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] seq2seq-sutskever-2014-variable-length-mapping
Seq2Seq (Sutskever, Vinyals & Le, 2014, arXiv:1409.3215) uses an encoder RNN and decoder RNN to enable variable-length input-to-output mapping for machine translation.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] rnn-historical-lineage-cajal-to-transformers
RNN historical lineage: neuroscience (Cajal 1909) → computational neuroscience (McCulloch-Pitts 1943) → perceptrons (Rosenblatt 1961) → associative memory (Hopfield 1982) → trainable RNNs (Rumelhart 1986) → LSTM (1997) → GRU (2014) → Transformers (2017).
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] hopfield-networks-connect-rnns-to-ising-model
Hopfield networks (1982) connect RNNs to statistical mechanics, drawing from the Ising model (Lenz 1920, Ising 1925) and spin-glass models (Sherrington & Kirkpatrick 1975).
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] lstm-recognizes-context-sensitive-languages
LSTM can recognize context-sensitive languages, surpassing HMM-based models which are limited to regular languages.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] q-learning-originated-watkins-1989
Q-learning was introduced in Chris Watkins' 1989 PhD thesis
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] dqn-mnih-2015-human-level-atari
Mnih et al. (2015) extended Q-learning to Deep Q-Networks (DQN), achieving human-level performance on Atari games
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] reinforce-williams-1987
The REINFORCE policy gradient algorithm was introduced by Williams in 1987
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] a3c-mnih-2016-async-actor-critic
A3C (Asynchronous Advantage Actor-Critic) was introduced by Mnih et al. (2016) using multiple parallel agents updating a shared model
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] td-learning-lineage-sutton-watkins-mnih
Temporal-difference learning has a direct lineage: Sutton (1984) → Watkins Q-learning (1989) → Mnih et al. DQN (2015)
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] experience-replay-lin-1992
Experience replay was introduced by Lin (1992) as a technique for self-improving agents, and later became a key component of DQN
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] inverse-rl-ng-russell-2000
Inverse reinforcement learning was defined by Ng & Russell (2000) as the problem of recovering reward functions from observed behavior
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] max-entropy-irl-ziebart-2008
Ziebart et al. (2008) introduced maximum entropy inverse reinforcement learning
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] dyna-architecture-sutton-1990
The Dyna architecture integrating learning, planning, and acting in model-based RL was introduced by Sutton (1990)
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] sutton-barto-canonical-rl-textbook
Sutton & Barto 'Reinforcement Learning: An Introduction' (2nd ed., 2018) is the canonical RL textbook, freely available at incompleteideas.net
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] td-learning-sutton-1988
Temporal-difference learning was formally introduced by Sutton in 1988, predating deep RL by decades
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] regret-bounds-auer-jaksch-ortner-2010
Auer, Jaksch & Ortner (2010) established near-optimal regret bounds for reinforcement learning, a key theoretical result for exploration-exploitation tradeoffs
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] deep-rl-adversarial-vulnerability
Deep RL policies share adversarial features across MDPs (Korkmaz 2022), making adversarial vulnerability a key limitation of deep RL
- Source: entries/2026/06/21/wiki-Reinforcement_learning-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Reinforcement_learning

### [ACCEPT] supervised-learning-classification-vs-regression
Supervised learning tasks divide into classification (predicting discrete categories) and regression (predicting continuous values)
- Source: entries/2026/06/21/wiki-Supervised_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Supervised_learning

### [ACCEPT] bias-variance-tradeoff-prediction-error
In supervised learning, prediction error decomposes approximately as bias + variance: flexible models have low bias but high variance, rigid models have high bias but low variance
- Source: entries/2026/06/21/wiki-Supervised_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Supervised_learning

### [ACCEPT] no-free-lunch-theorem-ml
The No Free Lunch Theorem states that no single supervised learning algorithm is best for all problems; algorithm choice is problem-dependent
- Source: entries/2026/06/21/wiki-Supervised_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Supervised_learning

### [ACCEPT] overfitting-stochastic-and-deterministic-noise
Overfitting can be caused by stochastic noise (measurement error) or deterministic noise (target function complexity exceeding model capacity)
- Source: entries/2026/06/21/wiki-Supervised_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Supervised_learning

### [ACCEPT] erm-neg-log-likelihood-equals-mle
Empirical risk minimization with negative log-likelihood loss is equivalent to maximum likelihood estimation
- Source: entries/2026/06/21/wiki-Supervised_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Supervised_learning

### [ACCEPT] structural-risk-minimization-regularization
Structural risk minimization adds a regularization penalty C(g) to empirical risk: J(g) = R_emp(g) + λC(g), where λ=0 gives pure ERM and large λ gives high bias/low variance
- Source: entries/2026/06/21/wiki-Supervised_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Supervised_learning

### [ACCEPT] l2-ridge-l1-lasso-regularization
L2 regularization (sum of squared weights) is ridge regression; L1 regularization (sum of absolute weights) is lasso and induces sparsity; L0 counts non-zero weights
- Source: entries/2026/06/21/wiki-Supervised_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Supervised_learning

### [ACCEPT] bayesian-interpretation-regularization-prior
The regularization penalty in structural risk minimization corresponds to the negative log prior, making the regularized objective equivalent to posterior probability
- Source: entries/2026/06/21/wiki-Supervised_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Supervised_learning

### [ACCEPT] generative-vs-discriminative-models
Generative models (naive Bayes, LDA) model the joint distribution P(x,y) and can have closed-form solutions; discriminative models (logistic regression) model P(y|x) directly and generally require iterative optimization
- Source: entries/2026/06/21/wiki-Supervised_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Supervised_learning

### [ACCEPT] inductive-bias-governs-generalization
Inductive bias is the set of assumptions a learner uses to predict outputs for unseen inputs; every supervised algorithm has one (e.g., linearity in linear regression, axis-aligned splits in decision trees)
- Source: entries/2026/06/21/wiki-Supervised_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Supervised_learning

### [ACCEPT] six-step-supervised-learning-procedure
The standard supervised learning procedure has six steps: determine sample type, gather training set, engineer features, select model/algorithm, train/tune with validation, evaluate on test set
- Source: entries/2026/06/21/wiki-Supervised_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Supervised_learning

### [ACCEPT] more-training-data-often-beats-algorithm-tuning
Given fixed resources, collecting more or better training data often outperforms tuning algorithms in supervised learning
- Source: entries/2026/06/21/wiki-Supervised_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Supervised_learning

### [ACCEPT] svm-soft-margin-cortes-vapnik-1995
Cortes and Vapnik (1995) introduced soft-margin support-vector networks in the foundational SVM paper.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-kernel-trick-boser-guyon-vapnik-1992
Boser, Guyon, and Vapnik (1992) proposed the kernel trick for optimal margin classifiers, predating the 1995 soft-margin paper.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-margin-formula-2-over-norm-w
The SVM geometric margin equals 2/||w||, derived from the separating hyperplane formulation.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-smo-platt-1998
Sequential Minimal Optimization (SMO), introduced by Platt in 1998, decomposes the SVM quadratic programming problem into minimal 2-variable subproblems.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-pegasos-sgd-solver
Pegasos (Shalev-Shwartz et al. 2007) is a stochastic gradient descent SVM solver operating in the primal with O(1/t) convergence.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-svr-epsilon-insensitive-loss
Support Vector Regression (SVR), introduced by Drucker et al. (1997), uses an epsilon-insensitive loss function.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-multiclass-one-vs-one-outperforms-one-vs-all
For multiclass SVM, one-vs-one generally outperforms one-vs-all (Hsu & Lin 2002; Duan & Keerthi 2005).
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-feature-scaling-critical
Feature scaling (standardization) is critical for SVM performance and should always be applied before training.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-practical-guide-rbf-default-grid-search
The practical SVM guide (Hsu et al. 2003) recommends: scale features, use RBF kernel as default, and grid-search C and gamma via cross-validation.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] liblinear-large-scale-linear-svm
LIBLINEAR (Fan et al. 2008) is optimized for large-scale linear classification and is the backend for scikit-learn's LinearSVC.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] libsvm-most-widely-used-svm-library
LIBSVM is the most widely-used SVM library, supporting classification, regression, and distribution estimation.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-transductive-joachims-1999
Transductive SVMs (Joachims 1999) bridge supervised and semi-supervised learning by using unlabeled test data during training.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-kernel-methods-superset
SVMs are kernel-based learning methods; all SVMs use kernels (even if just the linear kernel), but not all kernel methods are SVMs.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] transfer-learning-origin-1976-bozinovski
Transfer learning in neural networks dates back to Bozinovski and Fulgosi (1976), who studied pattern similarity and transfer in perceptron training.
- Source: entries/2026/06/21/wiki-Transfer_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Transfer_learning

### [ACCEPT] transfer-learning-formal-definition-domain-task
Transfer learning formally involves source domain D_S with task T_S and target domain D_T with task T_T, where either the domains or tasks must differ; if both are identical it is not transfer learning.
- Source: entries/2026/06/21/wiki-Transfer_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Transfer_learning

### [ACCEPT] negative-transfer-performance-degradation
Negative transfer occurs when source domain knowledge hurts target task performance; transferring from an unrelated domain can degrade results.
- Source: entries/2026/06/21/wiki-Transfer_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Transfer_learning

### [ACCEPT] pretraining-can-hurt-zoph-2020
Zoph et al. (2020) showed pre-training can reduce accuracy in some cases, finding self-training can outperform transfer learning when strong data augmentation is available.
- Source: entries/2026/06/21/wiki-Transfer_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Transfer_learning

### [ACCEPT] pan-yang-2010-canonical-transfer-learning-survey
Pan and Yang (2010) published the most-cited transfer learning survey in IEEE TKDE, defining the taxonomy of inductive, transductive, and unsupervised transfer.
- Source: entries/2026/06/21/wiki-Transfer_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Transfer_learning

### [ACCEPT] andrew-ng-transfer-learning-next-driver-ml
Andrew Ng at NIPS 2016 predicted transfer learning would be the next major driver of ML commercial success after supervised learning.
- Source: entries/2026/06/21/wiki-Transfer_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Transfer_learning

### [ACCEPT] domain-adaptation-subproblem-transfer-learning
Domain adaptation is a sub-problem of transfer learning focused on when source and target domains differ but the task is the same.
- Source: entries/2026/06/21/wiki-Transfer_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Transfer_learning

### [ACCEPT] transformer-attention-is-all-you-need-2017
The transformer architecture was introduced in 'Attention Is All You Need' (2017) by Google researchers, replacing recurrence with parallel multi-head attention.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] transformer-scaled-dot-product-attention-formula
Scaled dot-product attention is computed as Attention(Q,K,V) = softmax(QK^T / sqrt(d_k)) V, where d_k is the key dimension and the scaling prevents vanishing gradients in softmax.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] transformer-self-attention-permutation-invariant
Self-attention is permutation-invariant (order-agnostic), so transformers require positional encoding (fixed or learned) to preserve sequence order information.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] transformer-three-architectural-variants
Transformers have three architectural variants: encoder-only (e.g., BERT, for representation), decoder-only (e.g., GPT, for autoregressive generation), and encoder-decoder (e.g., T5, for sequence-to-sequence).
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] transformer-no-recurrence-enables-parallelism
Transformers eliminate sequential recurrence found in RNNs/LSTMs, enabling significantly more parallelism and shorter training times.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] transformer-multi-head-attention-subspaces
Multi-head attention runs scaled dot-product attention h times in parallel with different learned projections, allowing the model to attend to information from different representation subspaces at different positions simultaneously.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] transformer-pre-ln-vs-post-ln
The original 2017 transformer used post-layer-normalization; many modern implementations use pre-layer-normalization for more stable training.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] state-space-models-linear-complexity-alternative
State-space models (e.g., Mamba) have emerged as alternatives to transformers that handle long sequences with linear rather than quadratic complexity.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] svm-invented-vapnik-chervonenkis-1963
The linear SVM was proposed by Vapnik in 1963; the kernelized version was introduced by Boser, Guyon, and Vapnik in 1992; the soft margin formulation was published by Cortes and Vapnik in 1995.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-max-margin-hyperplane-minimizes-generalization-error
SVMs find the hyperplane that maximizes the margin between classes; larger margins correlate with lower generalization error and reduced overfitting.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-decision-boundary-depends-only-on-support-vectors
The SVM decision boundary depends only on the support vectors (points closest to the boundary), not on all training points, making SVMs memory-efficient at prediction time.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-kernel-trick-avoids-explicit-high-dim-mapping
The kernel trick enables nonlinear classification by computing dot products in a high-dimensional feature space via a kernel function k(x,y) without explicitly computing the high-dimensional mapping phi(x).
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-common-kernels-linear-poly-rbf-sigmoid
Common SVM kernel functions are: Linear k(x,y)=x·y, Polynomial k(x,y)=(x·y+c)^d, Gaussian RBF k(x,y)=exp(-gamma||x-y||²), and Sigmoid k(x,y)=tanh(alpha*x·y+c).
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-sklearn-svc-api
In scikit-learn, SVMs are used via sklearn.svm.SVC with parameters kernel, C, and gamma; e.g., SVC(kernel='rbf', C=1.0, gamma='scale').
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-margin-width-formula
The geometric width of the SVM margin is 2/||w||, so maximizing the margin is equivalent to minimizing ||w||.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-hard-margin-requires-linear-separability
Hard-margin SVM requires linearly separable data and permits no misclassifications; it minimizes (1/2)||w||² subject to y_i(w^T x_i - b) >= 1 for all i.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-soft-margin-hinge-loss-slack-variables
Soft-margin SVM handles non-separable data by introducing slack variables zeta_i >= 0 and hinge loss max(0, 1 - y_i(w^T x_i - b)), minimizing ||w||² + C * sum(zeta_i).
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-c-parameter-margin-error-tradeoff
The regularization parameter C controls the trade-off between maximizing the margin and minimizing classification errors: large C approximates hard-margin behavior (narrow margin, fewer errors); small C allows more violations (wider margin, more errors).
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-rbf-kernel-infinite-dimensional-space
The RBF (Gaussian) kernel can map data to an infinite-dimensional feature space.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-sigmoid-kernel-valid-only-some-params
The sigmoid kernel k(x,y) = tanh(kappa*x·y + c) is only a valid Mercer kernel for certain parameter values (kappa > 0, c < 0), not universally.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-objective-is-convex
The SVM optimization objective is convex, guaranteeing that any local minimum is the global minimum.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-weight-vector-linear-combination-support-vectors
The SVM weight vector w = sum(c_i * y_i * x_i) is a linear combination of support vectors only; most dual coefficients c_i are zero.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-dual-enables-kernel-trick
The dual formulation of the SVM involves only dot products between data points (x_i^T x_j), which is what enables the kernel trick by replacing these with k(x_i, x_j).
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-bias-recovery-from-support-vector
The SVM bias term b is recovered from any support vector on the margin boundary using b = w^T x_i - y_i, exploiting that y_i^(-1) = y_i for labels in {-1, +1}.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-subgradient-large-n-coorddescent-high-dim
Sub-gradient descent is preferred for SVMs with large n (many training examples); coordinate descent is preferred for high-dimensional feature spaces.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-equivalent-erm-hinge-loss-tikhonov
The soft-margin SVM is equivalent to empirical risk minimization (ERM) with hinge loss and Tikhonov (L2) regularization.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-hinge-loss-target-is-bayes-optimal-classifier
The hinge loss target function recovers exactly the Bayes-optimal classifier f*(x) (outputs ±1 based on whether p_x >= 1/2), unlike square loss (conditional expectation) or log-loss (logit) which estimate the full conditional distribution.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-hyperparameter-selection-grid-search-cv
SVM hyperparameters (kernel choice, gamma, lambda/C) are typically selected via grid search with exponentially growing sequences (e.g., 2^-5 to 2^15) evaluated by cross-validation, or alternatively by Bayesian optimization.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-limitations-labeled-data-binary-uncalibrated
Key SVM limitations: requires fully labeled data, produces uncalibrated probabilities, is natively binary-only (multiclass requires reduction strategies), and has difficult-to-interpret parameters.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-multiclass-ova-vs-ovo
Multiclass SVM uses one-versus-all (OVA: K classifiers, winner-takes-all on calibrated scores) or one-versus-one (OVO: K(K-1)/2 classifiers, max-wins voting).
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-crammer-singer-single-optimization
The Crammer-Singer method casts multiclass SVM as a single unified optimization problem rather than decomposing into multiple binary sub-problems.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-transductive-semi-supervised-learning
Transductive SVMs (Vapnik, 1998) extend SVMs to semi-supervised learning by jointly optimizing the separating hyperplane and the labels of unlabeled test data, where test labels y* are decision variables in the optimization.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svr-epsilon-insensitive-loss
Support Vector Regression (SVR) uses epsilon-insensitive loss: predictions within epsilon of the true value incur zero cost; only points outside the epsilon-tube are support vectors.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-smo-algorithm-2d-subproblems
The SMO (Sequential Minimal Optimization) algorithm decomposes the SVM quadratic programming problem into 2-dimensional sub-problems solved analytically, requiring no numerical optimizer or large matrix storage.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-liblinear-linear-time-iterations
LIBLINEAR's coordinate descent for linear SVMs has iterations that are linear in data read time with Q-linear convergence, making it extremely fast.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-preprocessing-standardization-critical
Data preprocessing via standardization (Z-score: subtract mean, divide by standard deviation per feature) is critical for SVM accuracy and highly recommended before training.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-bayesian-auto-hyperparameter-uncertainty
Bayesian SVM (Polson & Scott, 2011) interprets the SVM as a graphical model, enabling automatic hyperparameter tuning and predictive uncertainty quantification, unlike standard SVMs that require cross-validation.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] svm-platt-scaling-probability-calibration
Platt scaling is used to calibrate SVM outputs into probabilities, which is important for one-versus-all multiclass SVM.
- Source: entries/2026/06/21/wiki-Support_vector_machine-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Support_vector_machine

### [ACCEPT] transformer-attention-is-all-you-need-2017-neurips
The Transformer architecture was introduced in Vaswani et al. (2017) 'Attention Is All You Need' at NeurIPS 30, with all 8 authors at Google
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] bahdanau-attention-2014-precursor
Bahdanau et al. (2014) introduced additive attention for neural machine translation in RNN encoder-decoder models, predating the Transformer by 3 years
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] bert-masked-lm-gpt-causal-lm-same-year-2018
BERT (2018) uses masked language modeling (bidirectional) while GPT (2018) uses causal language modeling (autoregressive left-to-right); both published the same year with opposite pre-training strategies
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] vit-16x16-patches-as-tokens
Vision Transformer (ViT) by Dosovitskiy et al. (2021) divides images into 16x16 patches treated as tokens for image recognition
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] t5-text-to-text-unified-nlp-2020
T5 (Raffel et al., 2020) frames every NLP task as text-to-text, enabling unified fine-tuning across tasks
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] linear-transformers-equivalent-fast-weight-programmers
Linear Transformers (Katharopoulos et al., 2020) reduce attention from O(n²) to O(n) and are mathematically equivalent to fast-weight programmers (Schmidhuber, 1992)
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] chatgpt-launched-nov-30-2022-gpt35-rlhf
ChatGPT launched November 30, 2022, built on GPT-3.5 with RLHF
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] attention-evolution-timeline
Attention mechanism evolution: connectionist models (1982) → fast weights (1992) → additive attention (Bahdanau 2014) → multiplicative attention (Luong 2015) → self-attention (Vaswani 2017)
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] transformer-patent-us-10452978-google
The Transformer architecture is covered by US Patent 10,452,978 assigned to Google LLC, issued 2019-10-22, listing 8 inventors matching the 'Attention Is All You Need' authors
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] encoder-only-decoder-only-encoder-decoder-variants
BERT is encoder-only, GPT series is decoder-only, T5 is encoder-decoder — all are Transformer architecture variants
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] google-model-chronology-bert-to-gemma
Google's key model chronology: BERT (2018) → T5 (2019) → LaMDA (2021) → Chinchilla (2022) → PaLM (2022) → Gemini (2023) → Gemma (2024)
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] llm-training-pipeline-stages
Modern LLM training pipeline built on transformers: self-supervised learning → fine-tuning → instruction tuning → RLHF/Constitutional AI
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-8.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] unsupervised-learning-no-labeled-data
Unsupervised learning uses no labeled data — algorithms learn patterns exclusively from unlabeled data, in contrast to supervised learning which requires labeled datasets
- Source: entries/2026/06/21/wiki-Unsupervised_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Unsupervised_learning

### [ACCEPT] unsupervised-estimates-px-supervised-pxy
Unsupervised learning estimates the a priori probability distribution p(x); supervised learning estimates the conditional distribution p(x|y)
- Source: entries/2026/06/21/wiki-Unsupervised_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Unsupervised_learning

### [ACCEPT] generative-pretraining-paradigm-unsupervised-then-finetune
The generative pretraining paradigm (train unsupervised, then fine-tune supervised) is the foundation of modern LLMs
- Source: entries/2026/06/21/wiki-Unsupervised_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Unsupervised_learning

### [ACCEPT] self-supervised-classification-debated
Whether self-supervised learning is a form of unsupervised learning or a distinct paradigm is debated among researchers
- Source: entries/2026/06/21/wiki-Unsupervised_learning-chunk-1.md
- Source URL: https://en.wikipedia.org/wiki/Unsupervised_learning

### [ACCEPT] rbm-removes-lateral-connections-tractable
Restricted Boltzmann Machines (RBMs) remove lateral (within-layer) connections from Boltzmann machines, making training tractable via Contrastive Divergence with Gibbs Sampling
- Source: entries/2026/06/21/wiki-Unsupervised_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Unsupervised_learning

### [ACCEPT] vae-encodes-gaussian-parameters-reparameterization
VAE middle layer encodes parameters (mean, variance) of Gaussian distributions rather than fixed values, enabling stochastic generation via the reparameterization trick
- Source: entries/2026/06/21/wiki-Unsupervised_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Unsupervised_learning

### [ACCEPT] stacked-rbms-greedy-layerwise-no-backprop
Stacked RBMs (Deep Belief Networks) are trained greedily one layer at a time without backpropagation; optimal depth was found to be 3-4 layers as of 2009
- Source: entries/2026/06/21/wiki-Unsupervised_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Unsupervised_learning

### [ACCEPT] unsupervised-architecture-evolution-hopfield-to-vae
Unsupervised neural network architecture evolution: Hopfield (1982) → Boltzmann machine (1983) → RBM/Harmony Theory (1986) → LSTM (1995) → Helmholtz machine (1995) → VAE (2013)
- Source: entries/2026/06/21/wiki-Unsupervised_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Unsupervised_learning

### [ACCEPT] method-of-moments-global-convergence-vs-em-local
Method of moments provides global convergence guarantees under certain conditions for latent variable model estimation; EM algorithm can get stuck in local optima
- Source: entries/2026/06/21/wiki-Unsupervised_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Unsupervised_learning

### [ACCEPT] unsupervised-three-algorithmic-categories
Three main algorithmic categories of unsupervised learning: clustering (k-means, DBSCAN, hierarchical), anomaly detection (local outlier factor, isolation forest), and latent variable models (EM, method of moments)
- Source: entries/2026/06/21/wiki-Unsupervised_learning-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Unsupervised_learning

### [ACCEPT] helmholtz-machines-asymmetric-weights-wake-sleep
Helmholtz machines use asymmetric weights with separate recognition (forward) and generative (backward) networks, trained with the Wake-Sleep algorithm; they were early inspiration for VAEs
- Source: entries/2026/06/21/wiki-Unsupervised_learning-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Unsupervised_learning

### [ACCEPT] decision-transformer-rl-as-sequence-modeling
Decision Transformer (Chen et al., 2021) casts reinforcement learning as sequence modeling using the Transformer architecture
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] weight-tying-input-output-embeddings
Press & Wolf (2017) showed that sharing (tying) input and output embedding weights improves language model performance
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-7.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] transformer-original-paper-date
The original transformer paper 'Attention Is All You Need' was published on 2017-06-12.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] transformer-original-100m-params
The original transformer was a 100M-parameter encoder-decoder model.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] transformer-quadratic-cost-context
The transformer has quadratic computational cost in context window size, compared to linear cost for RNNs.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] lstm-introduced-1997-gating
LSTM was introduced in 1997 with multiplicative gating units to mitigate the vanishing gradient problem.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] pre-ln-removes-warmup-need
Pre-LN transformer (layer normalization before attention/FFN) stabilizes training and removes the need for learning rate warmup, unlike the original post-LN convention.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] bert-encoder-only-gpt-decoder-only-t5-enc-dec
BERT is encoder-only (masked LM task), GPT is decoder-only (autoregressive task), and T5 is encoder-decoder (prefixLM task).
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] three-lm-task-types
The three language modeling task types are: masked (BERT), autoregressive (GPT), and prefixLM (T5).
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] pretrain-finetune-paradigm
The dominant transformer training paradigm is self-supervised pretraining on unlabeled data followed by supervised fine-tuning on labeled task-specific data.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-2.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] attention-formula-scaled-dot-product
The scaled dot-product attention formula is Attention(Q,K,V) = softmax(QK^T / sqrt(d_k)) * V.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] attention-scaling-factor-sqrt-dk
Attention scores are divided by sqrt(d_k) (not d_k) to stabilize gradients during training.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] ffn-intermediate-4x-embedding
The feedforward network intermediate size is conventionally 4x the embedding size (d_ffn = 4 * d_emb) in GPT-2 and BERT families.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] original-transformer-relu-activation
The original transformer used ReLU activation in feedforward layers.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] weight-tying-embedding-unembedding
Weight tying uses the transpose of the embedding matrix as the un-embedding matrix, halving embedding parameters and preventing training divergence.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] attention-non-symmetric
Attention is non-symmetric: high attention from token i to token j does not imply high attention from j to i, because W^Q and W^K are different matrices.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] sinusoidal-positional-encoding-n-10000
The original transformer's sinusoidal positional encoding uses N=10000, with the key property that position shifts can be represented as linear transformations.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] subword-tokenization-bpe-ulm
Common subword tokenization algorithms are Byte Pair Encoding (BPE) and Unigram Language Model (ULM).
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] ffn-contains-most-transformer-params
Feedforward network layers contain most of the parameters in a transformer, handling 'memory' while attention layers handle 'communication' between tokens.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-3.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] encoder-2-sublayers-decoder-3-sublayers
Each encoder layer has 2 sublayers (self-attention, FFN); each decoder layer has 3 sublayers (masked self-attention, cross-attention, FFN).
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] decoder-only-removes-cross-attention
In decoder-only models (e.g., GPT), the cross-attention sublayer is removed entirely, leaving only 2 sublayers: masked self-attention and FFN.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] cross-attention-queries-decoder-kv-encoder
In cross-attention, queries come from the decoder and keys/values come from the encoder output.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] residual-connection-formula
Residual connections in transformers use the formula x -> F(x) + x, originating from ResNet, preventing vanishing gradients in deep stacking.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] prefixlm-bidirectional-prefix-causal-rest
PrefixLM is a decoder-only variant with a modified mask where prefix tokens attend bidirectionally and subsequent tokens attend causally.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-4.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] rope-relative-position-rotation
RoPE (Rotary Positional Embedding) encodes position by rotating pairs of embedding dimensions by angle mθ; dot products depend only on relative position, not absolute.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] alibi-linear-bias-attention
ALiBi adds a linear bias matrix B (where B_{i,j} = j-i) scaled by scalar s directly to attention logits, enabling short-context pretraining followed by long-context fine-tuning.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] kv-caching-autoregressive-inference
KV caching reuses previously computed key and value vectors during autoregressive inference since they don't change; prefilling is the initial forward pass that populates the cache.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] flashattention-exact-communication-avoiding
FlashAttention is a communication-avoiding algorithm that computes exact attention (not an approximation) using block matrix multiplications sized to fit GPU cache.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] flashattention2-230tflops-a100
FlashAttention-2 achieves up to 230 TFLOPS/s on A100, 2x faster than v1 and 9x over standard PyTorch attention.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] mqa-gqa-mla-kv-cache-variants
MQA shares K/V projections across all heads; GQA partitions heads into groups sharing K/V; MLA uses low-rank projection to compress KV cache to low-dimensional latent vectors.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] speculative-decoding-preserves-distribution
Speculative decoding uses a small model to generate candidate tokens verified in parallel by the large model, preserving the large model's output distribution via stochastic accept/reject.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] swiGLU-llama-palm-gelu-gpt-bert
SwiGLU activation is used by Llama and PaLM; GELU is used by GPT-1 and BERT.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] rmsnorm-llama-simplifies-layernorm
RMSNorm (used by Llama) simplifies LayerNorm by removing the mean-centering step.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] reformer-n-log-n-bigbird-linear
Reformer achieves O(N log N) attention via locality-sensitive hashing; BigBird achieves O(N) via random small-world networks.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-5.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] alphafold-transformer-protein-folding
AlphaFold applies transformers to protein structure prediction, demonstrating the architecture generalizes beyond language to biological sequence analysis.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] transformer-chess-elo-2895-no-search
A transformer using only static evaluation (no Minimax search) achieved grandmaster-level chess with an Elo rating of 2895.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

### [ACCEPT] rwkv-ssm-avoid-quadratic-attention
RWKV and state space models are alternative architectures that avoid the quadratic attention complexity inherent in standard transformers.
- Source: entries/2026/06/21/wiki-Transformer_deep_learning_architecture-chunk-6.md
- Source URL: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)

