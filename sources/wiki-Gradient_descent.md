---
source: https://en.wikipedia.org/wiki/Gradient_descent
fetched: 2026-06-21
---

Optimization algorithm For the analytical method called "steepest descent", see [Method of steepest descent](./Method_of_steepest_descent). Gradient descent in 2D 

**Gradient descent** is a method for unconstrained [mathematical optimization](./Mathematical_optimization). It is a [first-order](./Category:First_order_methods) [iterative](./Iterative_algorithm) [algorithm](./Algorithm) for minimizing a [differentiable](./Differentiable_function) [multivariate function](./Multivariate_function).

 
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

 

The idea is to take repeated steps in the opposite direction of the [gradient](./Gradient) (or approximate gradient) of the function at the current point, because this is the direction of steepest descent. Conversely, stepping in the direction of the gradient will lead to a trajectory that maximizes that function; the procedure is then known as *gradient ascent*.
Gradient descent should not be confused with [local search](./Local_search_(optimization)) algorithms, although both are [iterative methods](./Iterative_method) for [optimization](./Global_optimization).

 

Gradient descent is particularly useful in [machine learning](./Machine_learning) and [artificial intelligence](./Artificial_intelligence) for minimizing the cost or loss function.[[1]](./Gradient_descent#cite_note-auto-1)

 

Gradient descent is generally attributed to [Augustin-Louis Cauchy](./Augustin-Louis_Cauchy), who first suggested it in 1847.[[2]](./Gradient_descent#cite_note-2) [Jacques Hadamard](./Jacques_Hadamard) independently proposed a similar method in 1907.[[3]](./Gradient_descent#cite_note-3)[[4]](./Gradient_descent#cite_note-4) Its convergence properties for non-linear optimization problems were first studied by [Haskell Curry](./Haskell_Curry) in 1944,[[5]](./Gradient_descent#cite_note-5) with the method becoming increasingly well-studied and used in the following decades.[[6]](./Gradient_descent#cite_note-BP-6)[[7]](./Gradient_descent#cite_note-AK82-7)

 

A simple extension of gradient descent, [stochastic gradient descent](./Stochastic_gradient_descent), serves as the most basic algorithm used for training most [deep networks](./Deep_neural_network) today.

 

## Description

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/f/ff/Gradient_descent.svg/250px-Gradient_descent.svg.png)](./File:Gradient_descent.svg)Illustration of gradient descent on a series of [level sets](./Level_set) 

Gradient descent is based on the observation that if the [multi-variable function](./Multi-variable_function)     f (  x  )   {\displaystyle f(\mathbf {x} )}  ![{\displaystyle f(\mathbf {x} )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e41ea95e6949bf4cef6426116364ba87e0fdcd60) is [defined](./Defined_and_undefined) and [differentiable](./Differentiable_function) in a neighborhood of a point      a    {\displaystyle \mathbf {a} }  ![{\displaystyle \mathbf {a} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/1a957216653a9ee0d0133dcefd13fb75e36b8b9d), then     f (  x  )   {\displaystyle f(\mathbf {x} )}  ![{\displaystyle f(\mathbf {x} )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e41ea95e6949bf4cef6426116364ba87e0fdcd60) decreases *fastest* if one goes from      a    {\displaystyle \mathbf {a} }  ![{\displaystyle \mathbf {a} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/1a957216653a9ee0d0133dcefd13fb75e36b8b9d) in the direction of the negative [gradient](./Gradient) of     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) at      a  , i . e . , − −  ∇ ∇  f (  a  )   {\displaystyle \mathbf {a} ,i.e.,-\nabla f(\mathbf {a} )}  ![{\displaystyle \mathbf {a} ,i.e.,-\nabla f(\mathbf {a} )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/21ef520dfed6fd171c1c05546e2d58130b64f660). It follows that, if

       a   n + 1   =   a   n   − −  η η  ∇ ∇  f (   a   n   )   {\displaystyle \mathbf {a} _{n+1}=\mathbf {a} _{n}-\eta \nabla f(\mathbf {a} _{n})}  ![{\displaystyle \mathbf {a} _{n+1}=\mathbf {a} _{n}-\eta \nabla f(\mathbf {a} _{n})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0da6df8bb221173d4069002b90216ce1e4896fe9) 

for a small enough step size or [learning rate](./Learning_rate)     η η  ∈ ∈    R   +     {\displaystyle \eta \in \mathbb {R} _{+}}  ![{\displaystyle \eta \in \mathbb {R} _{+}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6dbcb888d2ec54232c942ac839c75958042f8ca7), then      f (   a  n    ) ≥ ≥  f (   a  n + 1    )   {\displaystyle f(\mathbf {a_{n}} )\geq f(\mathbf {a_{n+1}} )}  ![{\displaystyle f(\mathbf {a_{n}} )\geq f(\mathbf {a_{n+1}} )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f37eed2684f3af5cc064385a8638276c3c90cc0d). In other words, the term     η η  ∇ ∇  f (  a  )   {\displaystyle \eta \nabla f(\mathbf {a} )}  ![{\displaystyle \eta \nabla f(\mathbf {a} )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b45f2033014e5bb30ea034d03448dda0e32cbc0b) is subtracted from      a    {\displaystyle \mathbf {a} }  ![{\displaystyle \mathbf {a} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/1a957216653a9ee0d0133dcefd13fb75e36b8b9d) because we want to move against the gradient, toward the local minimum. With this observation in mind, one starts with a guess       x   0     {\displaystyle \mathbf {x} _{0}}  ![{\displaystyle \mathbf {x} _{0}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/799c59f89751f24a2719c4da95f1acdd3e2faf52) for a local minimum of     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61), and considers the sequence       x   0   ,   x   1   ,   x   2   , … …    {\displaystyle \mathbf {x} _{0},\mathbf {x} _{1},\mathbf {x} _{2},\ldots }  ![{\displaystyle \mathbf {x} _{0},\mathbf {x} _{1},\mathbf {x} _{2},\ldots }](https://wikimedia.org/api/rest_v1/media/math/render/svg/01c74f93321057d30c00a1963150b237313ba874) such that

       x   n + 1   =   x   n   − −   η η   n   ∇ ∇  f (   x   n   ) ,   n ≥ ≥  0.   {\displaystyle \mathbf {x} _{n+1}=\mathbf {x} _{n}-\eta _{n}\nabla f(\mathbf {x} _{n}),\ n\geq 0.}  ![{\displaystyle \mathbf {x} _{n+1}=\mathbf {x} _{n}-\eta _{n}\nabla f(\mathbf {x} _{n}),\ n\geq 0.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4f80cdf71d71a02e58d4bc3cf81663cb5f760399) 

We have a [monotonic](./Monotonic_function) sequence

     f (   x   0   ) ≥ ≥  f (   x   1   ) ≥ ≥  f (   x   2   ) ≥ ≥  ⋯ ⋯  ,   {\displaystyle f(\mathbf {x} _{0})\geq f(\mathbf {x} _{1})\geq f(\mathbf {x} _{2})\geq \cdots ,}  ![{\displaystyle f(\mathbf {x} _{0})\geq f(\mathbf {x} _{1})\geq f(\mathbf {x} _{2})\geq \cdots ,}](https://wikimedia.org/api/rest_v1/media/math/render/svg/240e43829142583ad0a8fbd0002a3e5345c3aca7) 

so the sequence     (   x   n   )   {\displaystyle (\mathbf {x} _{n})}  ![{\displaystyle (\mathbf {x} _{n})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/42c4ac385d2fc09aa0390781f96441e9b8615b95) converges to the desired local minimum. Note that the value of the *step size*     η η    {\displaystyle \eta }  ![{\displaystyle \eta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/e4d701857cf5fbec133eebaf94deadf722537f64) is allowed to change at every iteration. 

 

It is possible to guarantee the [convergence](./Convergent_series) to a local minimum under certain assumptions on the function     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) (for example,     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) [convex](./Convex_function) and     ∇ ∇  f   {\displaystyle \nabla f}  ![{\displaystyle \nabla f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b7b4d6de89b52c5a5e6e1583cb63eaee263e307b) [Lipschitz](./Lipschitz_continuity)) and particular choices of     η η    {\displaystyle \eta }  ![{\displaystyle \eta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/e4d701857cf5fbec133eebaf94deadf722537f64). Those include the sequence

 

     η η   n   =    |    (    x   n   − −    x   n − −  1    )   ⊤ ⊤     [  ∇ ∇  f (   x   n   ) − −  ∇ ∇  f (   x   n − −  1   )  ]   |    ‖  ∇ ∇  f (   x   n   ) − −  ∇ ∇  f (   x   n − −  1   )  ‖   2       {\displaystyle \eta _{n}={\frac {\left|\left(\mathbf {x} _{n}-\mathbf {x} _{n-1}\right)^{\top }\left[\nabla f(\mathbf {x} _{n})-\nabla f(\mathbf {x} _{n-1})\right]\right|}{\left\|\nabla f(\mathbf {x} _{n})-\nabla f(\mathbf {x} _{n-1})\right\|^{2}}}}  ![{\displaystyle \eta _{n}={\frac {\left|\left(\mathbf {x} _{n}-\mathbf {x} _{n-1}\right)^{\top }\left[\nabla f(\mathbf {x} _{n})-\nabla f(\mathbf {x} _{n-1})\right]\right|}{\left\|\nabla f(\mathbf {x} _{n})-\nabla f(\mathbf {x} _{n-1})\right\|^{2}}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/80f60d3675a08013f5cf38fcaf1c610eb1d96c46)

 

as in the [Barzilai-Borwein method](./Barzilai-Borwein_method),[[8]](./Gradient_descent#cite_note-8)[[9]](./Gradient_descent#cite_note-9) or a sequence      η η   n     {\displaystyle \eta _{n}}  ![{\displaystyle \eta _{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/cd926d56b81de76d958cf7efacd5df963f01297f) satisfying the [Wolfe conditions](./Wolfe_conditions) (which can be found by using [line search](./Line_search)). When the function     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) is [convex](./Convex_function), all local minima are also global minima, so in this case gradient descent can converge to the global solution.

 

This process is illustrated in the adjacent picture. Here,     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) is assumed to be defined on the plane, and that its graph has a [bowl](./Bowl_(vessel)) shape.  The blue curves are the [contour lines](./Contour_line), that is, the regions on which the value of     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) is constant. A red arrow originating at a point shows the direction of the negative gradient at that point. Note that the (negative) gradient at a point is [orthogonal](./Orthogonal) to the contour line going through that point. We see that gradient *descent* leads us to the bottom of the bowl, that is, to the point where the value of the function     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) is minimal.

 

### An analogy for understanding gradient descent

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/c/c7/Okanogan-Wenatchee_National_Forest%2C_morning_fog_shrouds_trees_%2837171636495%29.jpg/250px-Okanogan-Wenatchee_National_Forest%2C_morning_fog_shrouds_trees_%2837171636495%29.jpg)](./File:Okanogan-Wenatchee_National_Forest,_morning_fog_shrouds_trees_(37171636495).jpg)Fog in the mountains 

The basic intuition behind gradient descent can be illustrated by a hypothetical scenario. People are stuck in the mountains and are trying to get down (i.e., trying to find the global minimum). There is heavy fog such that visibility is extremely low. Therefore, the path down the mountain is not visible, so they must use local information to find the minimum. They can use the method of gradient descent, which involves looking at the steepness of the hill at their current position, then proceeding in the direction with the steepest descent (i.e., downhill). If they were trying to find the top of the mountain (i.e., the maximum), then they would proceed in the direction of steepest ascent (i.e., uphill). Using this method, they would eventually find their way down the mountain or possibly get stuck in some hole (i.e., local minimum or [saddle point](./Saddle_point)), like a mountain lake. However, assume also that the steepness of the hill is not immediately obvious with simple observation, but rather it requires a sophisticated instrument to measure, which the people happen to have at that moment. It takes quite some time to measure the steepness of the hill with the instrument. Thus, they should minimize their use of the instrument if they want to get down the mountain before sunset. The difficulty then is choosing the frequency at which they should measure the steepness of the hill so as not to go off track.

 

In this analogy, the people represent the algorithm, and the path taken down the mountain represents the sequence of parameter settings that the algorithm will explore. The steepness of the hill represents the [slope](./Slope) of the function at that point. The instrument used to measure steepness is [differentiation](./Differentiation_(mathematics)). The direction they choose to travel in aligns with the [gradient](./Gradient) of the function at that point. The amount of time they travel before taking another measurement is the step size.

 

### Choosing the step size and descent direction

 

Since using a step size     η η    {\displaystyle \eta }  ![{\displaystyle \eta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/e4d701857cf5fbec133eebaf94deadf722537f64) that is too small would slow convergence, and a     η η    {\displaystyle \eta }  ![{\displaystyle \eta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/e4d701857cf5fbec133eebaf94deadf722537f64) too large would lead to overshoot and divergence, finding a good setting of     η η    {\displaystyle \eta }  ![{\displaystyle \eta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/e4d701857cf5fbec133eebaf94deadf722537f64) is an important practical problem. [Philip Wolfe](./Philip_Wolfe_(mathematician)) also advocated using "clever choices of the [descent] direction" in practice.[[10]](./Gradient_descent#cite_note-10) While using a direction that deviates from the steepest descent direction may seem counter-intuitive, the idea is that the smaller slope may be compensated for by being sustained over a much longer distance.

 

To reason about this mathematically, consider a direction       p   n     {\displaystyle \mathbf {p} _{n}}  ![{\displaystyle \mathbf {p} _{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4a0378aee34f83e9a1b77b4d73c8e20d09e33e2d) and step size      η η   n     {\displaystyle \eta _{n}}  ![{\displaystyle \eta _{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/cd926d56b81de76d958cf7efacd5df963f01297f) and consider the more general update:

       a   n + 1   =   a   n   − −   η η   n      p   n     {\displaystyle \mathbf {a} _{n+1}=\mathbf {a} _{n}-\eta _{n}\,\mathbf {p} _{n}}  ![{\displaystyle \mathbf {a} _{n+1}=\mathbf {a} _{n}-\eta _{n}\,\mathbf {p} _{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5d42d84397d5c8984490dedce1493fc1b7a131af). 

Finding good settings of       p   n     {\displaystyle \mathbf {p} _{n}}  ![{\displaystyle \mathbf {p} _{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4a0378aee34f83e9a1b77b4d73c8e20d09e33e2d) and      η η   n     {\displaystyle \eta _{n}}  ![{\displaystyle \eta _{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/cd926d56b81de76d958cf7efacd5df963f01297f) requires some thought. First of all, we would like the update direction to point downhill. Mathematically, letting      θ θ   n     {\displaystyle \theta _{n}}  ![{\displaystyle \theta _{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/79cc00920259451fc1a684ba7350b6f93ce4f08a) denote the angle between     − −  ∇ ∇  f (   a  n    )   {\displaystyle -\nabla f(\mathbf {a_{n}} )}  ![{\displaystyle -\nabla f(\mathbf {a_{n}} )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9be3a256ca2cd4b7d371d2b5dc6d4bd6a72ceb76) and       p   n     {\displaystyle \mathbf {p} _{n}}  ![{\displaystyle \mathbf {p} _{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4a0378aee34f83e9a1b77b4d73c8e20d09e33e2d), this requires that     cos ⁡ ⁡   θ θ   n   > 0.   {\displaystyle \cos \theta _{n}>0.}  ![{\displaystyle \cos \theta _{n}>0.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/54c11842aa128a748a96c2103dcf0a266806b6ba) To say more, we need more information about the objective function that we are optimising. Under the fairly weak assumption that     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) is continuously differentiable, we may prove that:[[11]](./Gradient_descent#cite_note-11)

 
| f(an+1)≤f(an)−ηn‖∇f(an)‖2‖pn‖2(cos⁡θn−maxt∈[0,1]‖∇f(an−tηnpn)−∇f(an)‖2‖∇f(an)‖2){\displaystyle f(\mathbf {a} _{n+1})\leq f(\mathbf {a} _{n})-\eta _{n}\|\nabla f(\mathbf {a} _{n})\|_{2}\|\mathbf {p} _{n}\|_{2}\left(\cos \theta _{n}-\max _{t\in [0,1]}{\frac {\|\nabla f(\mathbf {a} _{n}-t\eta _{n}\mathbf {p} _{n})-\nabla f(\mathbf {a} _{n})\|_{2}}{\|\nabla f(\mathbf {a} _{n})\|_{2}}}\right)} |  | 1 |
| --- | --- | --- |

 

This inequality implies that the amount by which we can be sure the function     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) is decreased depends on a trade off between the two terms in square brackets. The first term in square brackets measures the angle between the descent direction and the negative gradient. The second term measures how quickly the gradient changes along the descent direction.

 

In principle inequality (**[1](./Gradient_descent#math_1)**) could be optimized over       p   n     {\displaystyle \mathbf {p} _{n}}  ![{\displaystyle \mathbf {p} _{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4a0378aee34f83e9a1b77b4d73c8e20d09e33e2d) and      η η   n     {\displaystyle \eta _{n}}  ![{\displaystyle \eta _{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/cd926d56b81de76d958cf7efacd5df963f01297f) to choose an optimal step size and direction. The problem is that evaluating the second term in square brackets requires evaluating     ∇ ∇  f (   a   n   − −  t  η η   n     p   n   )   {\displaystyle \nabla f(\mathbf {a} _{n}-t\eta _{n}\mathbf {p} _{n})}  ![{\displaystyle \nabla f(\mathbf {a} _{n}-t\eta _{n}\mathbf {p} _{n})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fb3b13d16f89aa6c94edfd0f30d70fa1859cc07d), and extra gradient evaluations are generally expensive and undesirable. Some ways around this problem are:

 
- Forgo the benefits of a clever descent direction by setting       p   n   = ∇ ∇  f (   a  n    )   {\displaystyle \mathbf {p} _{n}=\nabla f(\mathbf {a_{n}} )}  ![{\displaystyle \mathbf {p} _{n}=\nabla f(\mathbf {a_{n}} )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/63c5f6d185d084209f228c79cb5df6a7b465d80b), and use [line search](./Line_search) to find a suitable step-size      γ γ   n     {\displaystyle \gamma _{n}}  ![{\displaystyle \gamma _{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/84a6d83f89515bf8d1a053639dc484e620f42036), such as one that satisfies the [Wolfe conditions](./Wolfe_conditions). A more economic way of choosing learning rates is [backtracking line search](./Backtracking_line_search), a method that has both good theoretical guarantees and experimental results. Note that one does not need to choose        p   n     {\displaystyle \mathbf {p} _{n}}  ![{\displaystyle \mathbf {p} _{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4a0378aee34f83e9a1b77b4d73c8e20d09e33e2d) to be the gradient; any direction that has positive inner product with the gradient will result in a reduction of the function value (for a sufficiently small value of      η η   n     {\displaystyle \eta _{n}}  ![{\displaystyle \eta _{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/cd926d56b81de76d958cf7efacd5df963f01297f)).
- Assuming that     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) is twice-differentiable, use its Hessian      ∇ ∇   2   f   {\displaystyle \nabla ^{2}f}  ![{\displaystyle \nabla ^{2}f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f41018628f3a828a558d68269557e7cd3ec7342e) to estimate     ‖ ‖  ∇ ∇  f (   a   n   − −  t  η η   n     p   n   ) − −  ∇ ∇  f (   a   n   )  ‖ ‖   2   ≈ ≈  ‖ ‖  t  η η   n    ∇ ∇   2   f (   a   n   )   p   n   ‖ ‖  .   {\displaystyle \|\nabla f(\mathbf {a} _{n}-t\eta _{n}\mathbf {p} _{n})-\nabla f(\mathbf {a} _{n})\|_{2}\approx \|t\eta _{n}\nabla ^{2}f(\mathbf {a} _{n})\mathbf {p} _{n}\|.}  ![{\displaystyle \|\nabla f(\mathbf {a} _{n}-t\eta _{n}\mathbf {p} _{n})-\nabla f(\mathbf {a} _{n})\|_{2}\approx \|t\eta _{n}\nabla ^{2}f(\mathbf {a} _{n})\mathbf {p} _{n}\|.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ba6dea727dcaa1bcc44fa0b6b71f11092a6f58f6)Then choose       p   n     {\displaystyle \mathbf {p} _{n}}  ![{\displaystyle \mathbf {p} _{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4a0378aee34f83e9a1b77b4d73c8e20d09e33e2d) and      η η   n     {\displaystyle \eta _{n}}  ![{\displaystyle \eta _{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/cd926d56b81de76d958cf7efacd5df963f01297f) by optimising inequality (**[1](./Gradient_descent#math_1)**).
- Assuming that     ∇ ∇  f   {\displaystyle \nabla f}  ![{\displaystyle \nabla f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b7b4d6de89b52c5a5e6e1583cb63eaee263e307b) is [Lipschitz](./Lipschitz_continuity), use its Lipschitz constant     L   {\displaystyle L}  ![{\displaystyle L}](https://wikimedia.org/api/rest_v1/media/math/render/svg/103168b86f781fe6e9a4a87b8ea1cebe0ad4ede8) to bound     ‖ ‖  ∇ ∇  f (   a   n   − −  t  η η   n     p   n   ) − −  ∇ ∇  f (   a   n   )  ‖ ‖   2   ≤ ≤  L t  η η   n   ‖ ‖    p   n   ‖ ‖  .   {\displaystyle \|\nabla f(\mathbf {a} _{n}-t\eta _{n}\mathbf {p} _{n})-\nabla f(\mathbf {a} _{n})\|_{2}\leq Lt\eta _{n}\|\mathbf {p} _{n}\|.}  ![{\displaystyle \|\nabla f(\mathbf {a} _{n}-t\eta _{n}\mathbf {p} _{n})-\nabla f(\mathbf {a} _{n})\|_{2}\leq Lt\eta _{n}\|\mathbf {p} _{n}\|.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6ebbf2f830739e759537177a1fcff40a31de481c) Then choose       p   n     {\displaystyle \mathbf {p} _{n}}  ![{\displaystyle \mathbf {p} _{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4a0378aee34f83e9a1b77b4d73c8e20d09e33e2d) and      η η   n     {\displaystyle \eta _{n}}  ![{\displaystyle \eta _{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/cd926d56b81de76d958cf7efacd5df963f01297f) by optimising inequality (**[1](./Gradient_descent#math_1)**).
- Build a custom model of      max  t ∈ ∈  [ 0 , 1 ]      ‖ ‖  ∇ ∇  f (   a   n   − −  t  η η   n     p   n   ) − −  ∇ ∇  f (   a   n   )  ‖ ‖   2     ‖ ‖  ∇ ∇  f (   a   n   )  ‖ ‖   2        {\displaystyle \max _{t\in [0,1]}{\frac {\|\nabla f(\mathbf {a} _{n}-t\eta _{n}\mathbf {p} _{n})-\nabla f(\mathbf {a} _{n})\|_{2}}{\|\nabla f(\mathbf {a} _{n})\|_{2}}}}  ![{\displaystyle \max _{t\in [0,1]}{\frac {\|\nabla f(\mathbf {a} _{n}-t\eta _{n}\mathbf {p} _{n})-\nabla f(\mathbf {a} _{n})\|_{2}}{\|\nabla f(\mathbf {a} _{n})\|_{2}}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/827944aec1ba3c40ce5b61e29ebbadfc5daf4040) for     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61). Then choose       p   n     {\displaystyle \mathbf {p} _{n}}  ![{\displaystyle \mathbf {p} _{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4a0378aee34f83e9a1b77b4d73c8e20d09e33e2d) and      η η   n     {\displaystyle \eta _{n}}  ![{\displaystyle \eta _{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/cd926d56b81de76d958cf7efacd5df963f01297f) by optimising inequality (**[1](./Gradient_descent#math_1)**).
- Under stronger assumptions on the function     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) such as [convexity](./Convex_function), more [advanced techniques](./Gradient_descent#Fast_gradient_methods) may be possible.

 

Usually by following one of the recipes above, [convergence](./Convergent_series) to a local minimum can be guaranteed. When the function     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) is [convex](./Convex_function), all local minima are also global minima, so in this case gradient descent can converge to the global solution.

 

## Solution of a linear system

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/7/7b/Steepest_descent.png/250px-Steepest_descent.png)](./File:Steepest_descent.png)The steepest descent algorithm applied to the [Wiener filter](./Wiener_filter)[[12]](./Gradient_descent#cite_note-12) 

Gradient descent can be used to solve a [system of linear equations](./System_of_linear_equations)

      A   x  − −   b  = 0   {\displaystyle \mathbf {A} \mathbf {x} -\mathbf {b} =0}  ![{\displaystyle \mathbf {A} \mathbf {x} -\mathbf {b} =0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/435e223a0da553ca83961b0af747b0a3567bfe26) 

reformulated as a quadratic minimization problem.
If the system matrix      A    {\displaystyle \mathbf {A} }  ![{\displaystyle \mathbf {A} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/0795cc96c75d81520a120482662b90f024c9a1a1) is real [symmetric](./Symmetric_matrix) and [positive-definite](./Positive-definite_matrix), an objective function is defined as the quadratic function, with minimization of

     f (  x  ) =   x   ⊤ ⊤     A   x  − −  2   x   ⊤ ⊤     b  ,   {\displaystyle f(\mathbf {x} )=\mathbf {x} ^{\top }\mathbf {A} \mathbf {x} -2\mathbf {x} ^{\top }\mathbf {b} ,}  ![{\displaystyle f(\mathbf {x} )=\mathbf {x} ^{\top }\mathbf {A} \mathbf {x} -2\mathbf {x} ^{\top }\mathbf {b} ,}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ba4556b22259b1326230d6e75cb40fda87073029) 

so that

     ∇ ∇  f (  x  ) = 2 (  A   x  − −   b  ) .   {\displaystyle \nabla f(\mathbf {x} )=2(\mathbf {A} \mathbf {x} -\mathbf {b} ).}  ![{\displaystyle \nabla f(\mathbf {x} )=2(\mathbf {A} \mathbf {x} -\mathbf {b} ).}](https://wikimedia.org/api/rest_v1/media/math/render/svg/769dc711ac488ef07e64a0ddc3fe4f0c35617ca3) 

For a general real matrix      A    {\displaystyle \mathbf {A} }  ![{\displaystyle \mathbf {A} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/0795cc96c75d81520a120482662b90f024c9a1a1), [linear least squares](./Linear_least_squares) define

     f (  x  ) =   ‖   A   x  − −   b   ‖   2   .   {\displaystyle f(\mathbf {x} )=\left\|\mathbf {A} \mathbf {x} -\mathbf {b} \right\|^{2}.}  ![{\displaystyle f(\mathbf {x} )=\left\|\mathbf {A} \mathbf {x} -\mathbf {b} \right\|^{2}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8e1c13e49915329e1a406839842e788ad4f21a7f) 

In traditional linear least squares for real      A    {\displaystyle \mathbf {A} }  ![{\displaystyle \mathbf {A} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/0795cc96c75d81520a120482662b90f024c9a1a1) and      b    {\displaystyle \mathbf {b} }  ![{\displaystyle \mathbf {b} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/13ebf4628a1adf07133a6009e4a78bdd990c6eb9) the [Euclidean norm](./Euclidean_norm) is used, in which case

     ∇ ∇  f (  x  ) = 2   A   ⊤ ⊤    (  A   x  − −   b  ) .   {\displaystyle \nabla f(\mathbf {x} )=2\mathbf {A} ^{\top }(\mathbf {A} \mathbf {x} -\mathbf {b} ).}  ![{\displaystyle \nabla f(\mathbf {x} )=2\mathbf {A} ^{\top }(\mathbf {A} \mathbf {x} -\mathbf {b} ).}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e65e5b1a7819a9b8449f15b7f031f83a4ac9f190) 

The [line search](./Line_search) minimization, finding the locally optimal step size     η η    {\displaystyle \eta }  ![{\displaystyle \eta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/e4d701857cf5fbec133eebaf94deadf722537f64) on every iteration, can be performed analytically for quadratic functions, and explicit formulas for the locally optimal     η η    {\displaystyle \eta }  ![{\displaystyle \eta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/e4d701857cf5fbec133eebaf94deadf722537f64) are known.[[6]](./Gradient_descent#cite_note-BP-6)[[13]](./Gradient_descent#cite_note-saad1996iterative-13)

 

For example, for real [symmetric](./Symmetric_matrix) and [positive-definite](./Positive-definite_matrix) matrix      A    {\displaystyle \mathbf {A} }  ![{\displaystyle \mathbf {A} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/0795cc96c75d81520a120482662b90f024c9a1a1), a simple algorithm can be as follows,[[6]](./Gradient_descent#cite_note-BP-6)

           repeat in the loop:         r  :=  b  − −   A x        η η  :=    r   ⊤ ⊤     r    /     r   ⊤ ⊤     A r          x  :=  x  + η η   r          if      r   ⊤ ⊤     r    is sufficiently small, then exit loop        end repeat loop        return    x    as the result        {\displaystyle {\begin{aligned}&{\text{repeat in the loop:}}\\&\qquad \mathbf {r} :=\mathbf {b} -\mathbf {Ax} \\&\qquad \eta :={\mathbf {r} ^{\top }\mathbf {r} }/{\mathbf {r} ^{\top }\mathbf {Ar} }\\&\qquad \mathbf {x} :=\mathbf {x} +\eta \mathbf {r} \\&\qquad {\hbox{if }}\mathbf {r} ^{\top }\mathbf {r} {\text{ is sufficiently small, then exit loop}}\\&{\text{end repeat loop}}\\&{\text{return }}\mathbf {x} {\text{ as the result}}\end{aligned}}}  ![{\displaystyle {\begin{aligned}&{\text{repeat in the loop:}}\\&\qquad \mathbf {r} :=\mathbf {b} -\mathbf {Ax} \\&\qquad \eta :={\mathbf {r} ^{\top }\mathbf {r} }/{\mathbf {r} ^{\top }\mathbf {Ar} }\\&\qquad \mathbf {x} :=\mathbf {x} +\eta \mathbf {r} \\&\qquad {\hbox{if }}\mathbf {r} ^{\top }\mathbf {r} {\text{ is sufficiently small, then exit loop}}\\&{\text{end repeat loop}}\\&{\text{return }}\mathbf {x} {\text{ as the result}}\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/45b2d98ecf8d9c7a974384ca0e5364e45c23277a) 

To avoid multiplying by      A    {\displaystyle \mathbf {A} }  ![{\displaystyle \mathbf {A} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/0795cc96c75d81520a120482662b90f024c9a1a1) twice per iteration,
we note that      x  :=  x  + η η   r    {\displaystyle \mathbf {x} :=\mathbf {x} +\eta \mathbf {r} }  ![{\displaystyle \mathbf {x} :=\mathbf {x} +\eta \mathbf {r} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/eec57220e5a6166f62d330bf03b967187dd9601e) implies      r  :=  r  − −  η η   A r    {\displaystyle \mathbf {r} :=\mathbf {r} -\eta \mathbf {Ar} }  ![{\displaystyle \mathbf {r} :=\mathbf {r} -\eta \mathbf {Ar} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/596f784bd1c487b5c58e8fc7d49da3f1803cc2b7), which gives the traditional algorithm,[[14]](./Gradient_descent#cite_note-:0-14)

           r  :=  b  − −   A x        repeat in the loop:        η η  :=    r   ⊤ ⊤     r    /     r   ⊤ ⊤     A r          x  :=  x  + η η   r          if      r   ⊤ ⊤     r    is sufficiently small, then exit loop         r  :=  r  − −  η η   A r        end repeat loop        return    x    as the result        {\displaystyle {\begin{aligned}&\mathbf {r} :=\mathbf {b} -\mathbf {Ax} \\&{\text{repeat in the loop:}}\\&\qquad \eta :={\mathbf {r} ^{\top }\mathbf {r} }/{\mathbf {r} ^{\top }\mathbf {Ar} }\\&\qquad \mathbf {x} :=\mathbf {x} +\eta \mathbf {r} \\&\qquad {\hbox{if }}\mathbf {r} ^{\top }\mathbf {r} {\text{ is sufficiently small, then exit loop}}\\&\qquad \mathbf {r} :=\mathbf {r} -\eta \mathbf {Ar} \\&{\text{end repeat loop}}\\&{\text{return }}\mathbf {x} {\text{ as the result}}\end{aligned}}}  ![{\displaystyle {\begin{aligned}&\mathbf {r} :=\mathbf {b} -\mathbf {Ax} \\&{\text{repeat in the loop:}}\\&\qquad \eta :={\mathbf {r} ^{\top }\mathbf {r} }/{\mathbf {r} ^{\top }\mathbf {Ar} }\\&\qquad \mathbf {x} :=\mathbf {x} +\eta \mathbf {r} \\&\qquad {\hbox{if }}\mathbf {r} ^{\top }\mathbf {r} {\text{ is sufficiently small, then exit loop}}\\&\qquad \mathbf {r} :=\mathbf {r} -\eta \mathbf {Ar} \\&{\text{end repeat loop}}\\&{\text{return }}\mathbf {x} {\text{ as the result}}\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1fff635ae5452ba52667f206b2173ecca3660291)[![](//upload.wikimedia.org/wikipedia/commons/thumb/6/6c/Steepest_descent_convergence_path_for_A_%3D_2_2%2C_2_3.png/250px-Steepest_descent_convergence_path_for_A_%3D_2_2%2C_2_3.png)](./File:Steepest_descent_convergence_path_for_A_=_2_2,_2_3.png)Convergence path of steepest descent method for A = [[2, 2], [2, 3]] 

The method is rarely used for solving linear equations, with the [conjugate gradient method](./Conjugate_gradient_method) being one of the most popular alternatives. The number of gradient descent iterations is commonly proportional to the spectral [condition number](./Condition_number)     κ κ  (  A  )   {\displaystyle \kappa (\mathbf {A} )}  ![{\displaystyle \kappa (\mathbf {A} )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f4a3dab1be502165a1ac693234b92db1c5ad660f) of the system matrix      A    {\displaystyle \mathbf {A} }  ![{\displaystyle \mathbf {A} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/0795cc96c75d81520a120482662b90f024c9a1a1) (the ratio of the maximum to minimum [eigenvalues](./Eigenvalues) of       A   ⊤ ⊤     A    {\displaystyle \mathbf {A} ^{\top }\mathbf {A} }  ![{\displaystyle \mathbf {A} ^{\top }\mathbf {A} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/8fda2f40a3140773a86e8409b54d9ea7aa148f9e)), while the convergence of [conjugate gradient method](./Conjugate_gradient_method) is typically determined by a square root of the condition number, i.e., is much faster. Both methods can benefit from [preconditioning](./Preconditioner), where gradient descent may require less assumptions on the preconditioner.[[14]](./Gradient_descent#cite_note-:0-14)

 

### Geometric behavior and residual orthogonality

 

In steepest descent applied to solving      A x  =  b    {\displaystyle \mathbf {Ax} =\mathbf {b} }  ![{\displaystyle \mathbf {Ax} =\mathbf {b} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/e68388b7df59f536a3bef4e70def2f2bb36f48c0), where      A    {\displaystyle \mathbf {A} }  ![{\displaystyle \mathbf {A} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/0795cc96c75d81520a120482662b90f024c9a1a1) is symmetric positive-definite, the residual vectors       r   k   =  b  − −   A    x   k     {\displaystyle \mathbf {r} _{k}=\mathbf {b} -\mathbf {A} \mathbf {x} _{k}}  ![{\displaystyle \mathbf {r} _{k}=\mathbf {b} -\mathbf {A} \mathbf {x} _{k}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fb35c202ad0912a4bb19012c7af3529163586b97) are orthogonal across iterations:

     ⟨ ⟨    r   k + 1   ,   r   k   ⟩ ⟩  = 0.   {\displaystyle \langle \mathbf {r} _{k+1},\mathbf {r} _{k}\rangle =0.}  ![{\displaystyle \langle \mathbf {r} _{k+1},\mathbf {r} _{k}\rangle =0.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/75f9a3bb5c53033de95a00b1c183b9de5f77345b) 

Because each step is taken in the steepest direction, steepest-descent steps alternate between directions aligned with the extreme axes of the elongated level sets.  When     κ κ  (  A  )   {\displaystyle \kappa (\mathbf {A} )}  ![{\displaystyle \kappa (\mathbf {A} )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f4a3dab1be502165a1ac693234b92db1c5ad660f) is large, this produces a characteristic zig–zag path. The poor conditioning of      A    {\displaystyle \mathbf {A} }  ![{\displaystyle \mathbf {A} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/0795cc96c75d81520a120482662b90f024c9a1a1) is the primary cause of the slow convergence, and orthogonality of successive residuals reinforces this alternation.

 

As shown in the image on the right, steepest descent converges slowly due to the high condition number of      A    {\displaystyle \mathbf {A} }  ![{\displaystyle \mathbf {A} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/0795cc96c75d81520a120482662b90f024c9a1a1), and the orthogonality of residuals forces each new direction to undo the overshoot from the previous step. The result is a path that zigzags toward the solution. This inefficiency is one reason conjugate gradient or preconditioning methods are preferred.[[15]](./Gradient_descent#cite_note-15)

 

## Solution of a non-linear system

 

Gradient descent can also be used to solve a system of [nonlinear equations](./Nonlinear_equation). Below is an example that shows how to use the gradient descent to solve for three unknown variables, *x*1, *x*2, and *x*3. This example shows one iteration of the gradient descent.

 

Consider the nonlinear system of equations

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/b/b5/Gradient_Descent_Example_Nonlinear_Equations.gif/500px-Gradient_Descent_Example_Nonlinear_Equations.gif)](./File:Gradient_Descent_Example_Nonlinear_Equations.gif)An animation showing the first 83 iterations of gradient descent applied to this example. Surfaces are [isosurfaces](./Isosurface) of     f (   x   ( n )   )   {\displaystyle f(\mathbf {x} ^{(n)})}  ![{\displaystyle f(\mathbf {x} ^{(n)})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fddab40001c0d518f35ca0208a4d4abd282faa84) at current guess       x   ( n )     {\displaystyle \mathbf {x} ^{(n)}}  ![{\displaystyle \mathbf {x} ^{(n)}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f499a0c7f0c98f9393b40fd64dd97b26f345c547), and arrows show the direction of descent. Due to a small and constant step size, the convergence is slow.      {    3  x  1   − −  cos ⁡ ⁡  (  x  2    x  3   ) − −     3 2    = 0     4  x  1   2   − −  625  x  2   2   + 2  x  2   − −  1 = 0     exp ⁡ ⁡  ( − −   x  1    x  2   ) + 20  x  3   +     10 π π  − −  3  3    = 0         {\displaystyle {\begin{cases}3x_{1}-\cos(x_{2}x_{3})-{\tfrac {3}{2}}=0\\4x_{1}^{2}-625x_{2}^{2}+2x_{2}-1=0\\\exp(-x_{1}x_{2})+20x_{3}+{\tfrac {10\pi -3}{3}}=0\end{cases}}}  ![{\displaystyle {\begin{cases}3x_{1}-\cos(x_{2}x_{3})-{\tfrac {3}{2}}=0\\4x_{1}^{2}-625x_{2}^{2}+2x_{2}-1=0\\\exp(-x_{1}x_{2})+20x_{3}+{\tfrac {10\pi -3}{3}}=0\end{cases}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/540a1ea603de51e040c6fe8034ce8ccb10b3f4d7) 

Let us introduce the associated function

     G (  x  ) =   [    3  x  1   − −  cos ⁡ ⁡  (  x  2    x  3   ) − −     3 2        4  x  1   2   − −  625  x  2   2   + 2  x  2   − −  1     exp ⁡ ⁡  ( − −   x  1    x  2   ) + 20  x  3   +     10 π π  − −  3  3       ]   ,   {\displaystyle G(\mathbf {x} )={\begin{bmatrix}3x_{1}-\cos(x_{2}x_{3})-{\tfrac {3}{2}}\\4x_{1}^{2}-625x_{2}^{2}+2x_{2}-1\\\exp(-x_{1}x_{2})+20x_{3}+{\tfrac {10\pi -3}{3}}\\\end{bmatrix}},}  ![{\displaystyle G(\mathbf {x} )={\begin{bmatrix}3x_{1}-\cos(x_{2}x_{3})-{\tfrac {3}{2}}\\4x_{1}^{2}-625x_{2}^{2}+2x_{2}-1\\\exp(-x_{1}x_{2})+20x_{3}+{\tfrac {10\pi -3}{3}}\\\end{bmatrix}},}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9b649372ae6174f11549dd035f107eac303b5377) 

where

      x  =   [     x  1        x  2        x  3      ]   .   {\displaystyle \mathbf {x} ={\begin{bmatrix}x_{1}\\x_{2}\\x_{3}\\\end{bmatrix}}.}  ![{\displaystyle \mathbf {x} ={\begin{bmatrix}x_{1}\\x_{2}\\x_{3}\\\end{bmatrix}}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/669781ad6ed5e35cc494e28efac793c74311195f) 

One might now define the objective function

         f (  x  )    =   1 2    G  ⊤ ⊤    (  x  ) G (  x  )       =   1 2    [    (  3  x  1   − −  cos ⁡ ⁡  (  x  2    x  3   ) − −    3 2    )   2   +   (  4  x  1   2   − −  625  x  2   2   + 2  x  2   − −  1  )   2   +                (  exp ⁡ ⁡  ( − −   x  1    x  2   ) + 20  x  3   +    10 π π  − −  3  3    )   2   ]  ,       {\displaystyle {\begin{aligned}f(\mathbf {x} )&={\frac {1}{2}}G^{\top }(\mathbf {x} )G(\mathbf {x} )\\&={\frac {1}{2}}\left[\left(3x_{1}-\cos(x_{2}x_{3})-{\frac {3}{2}}\right)^{2}+\left(4x_{1}^{2}-625x_{2}^{2}+2x_{2}-1\right)^{2}+\right.\\&{}\qquad \left.\left(\exp(-x_{1}x_{2})+20x_{3}+{\frac {10\pi -3}{3}}\right)^{2}\right],\end{aligned}}}  ![{\displaystyle {\begin{aligned}f(\mathbf {x} )&={\frac {1}{2}}G^{\top }(\mathbf {x} )G(\mathbf {x} )\\&={\frac {1}{2}}\left[\left(3x_{1}-\cos(x_{2}x_{3})-{\frac {3}{2}}\right)^{2}+\left(4x_{1}^{2}-625x_{2}^{2}+2x_{2}-1\right)^{2}+\right.\\&{}\qquad \left.\left(\exp(-x_{1}x_{2})+20x_{3}+{\frac {10\pi -3}{3}}\right)^{2}\right],\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/205d7f08ca51e53e3b010ca85c55de40d4c068be) 

which we will attempt to minimize. As an initial guess, let us use

       x   ( 0 )   =  0  =   [    0     0     0    ]   .   {\displaystyle \mathbf {x} ^{(0)}=\mathbf {0} ={\begin{bmatrix}0\\0\\0\\\end{bmatrix}}.}  ![{\displaystyle \mathbf {x} ^{(0)}=\mathbf {0} ={\begin{bmatrix}0\\0\\0\\\end{bmatrix}}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/828f564078b2a3d2307d9a0388a0cc76f21716c4) 

We know that

       x   ( 1 )   =  0  − −   η η   0   ∇ ∇  f (  0  ) =  0  − −   η η   0    J  G   (  0   )  ⊤ ⊤    G (  0  ) ,   {\displaystyle \mathbf {x} ^{(1)}=\mathbf {0} -\eta _{0}\nabla f(\mathbf {0} )=\mathbf {0} -\eta _{0}J_{G}(\mathbf {0} )^{\top }G(\mathbf {0} ),}  ![{\displaystyle \mathbf {x} ^{(1)}=\mathbf {0} -\eta _{0}\nabla f(\mathbf {0} )=\mathbf {0} -\eta _{0}J_{G}(\mathbf {0} )^{\top }G(\mathbf {0} ),}](https://wikimedia.org/api/rest_v1/media/math/render/svg/01a8568ba794f4fd29ffc61bd210ebfed8ecabf5) 

where the [Jacobian matrix](./Jacobian_matrix)      J  G     {\displaystyle J_{G}}  ![{\displaystyle J_{G}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/eb18051dfc2735d7015023e0d0615ad6cb52af77) is given by

      J  G   (  x  ) =   [    3   sin ⁡ ⁡  (  x  2    x  3   )  x  3     sin ⁡ ⁡  (  x  2    x  3   )  x  2       8  x  1     − −  1250  x  2   + 2   0     − −   x  2   exp ⁡ ⁡   ( − −   x  1    x  2   )    − −   x  1   exp ⁡ ⁡  ( − −   x  1    x  2   )   20    ]   .   {\displaystyle J_{G}(\mathbf {x} )={\begin{bmatrix}3&\sin(x_{2}x_{3})x_{3}&\sin(x_{2}x_{3})x_{2}\\8x_{1}&-1250x_{2}+2&0\\-x_{2}\exp {(-x_{1}x_{2})}&-x_{1}\exp(-x_{1}x_{2})&20\\\end{bmatrix}}.}  ![{\displaystyle J_{G}(\mathbf {x} )={\begin{bmatrix}3&\sin(x_{2}x_{3})x_{3}&\sin(x_{2}x_{3})x_{2}\\8x_{1}&-1250x_{2}+2&0\\-x_{2}\exp {(-x_{1}x_{2})}&-x_{1}\exp(-x_{1}x_{2})&20\\\end{bmatrix}}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2bac1f9f28f50a955bea2944d1ca3d5f3918c340) 

We calculate:

      J  G   (  0  ) =   [    3   0   0     0   2   0     0   0   20    ]   ,  G (  0  ) =   [    − −  2.5     − −  1     10.472    ]   .   {\displaystyle J_{G}(\mathbf {0} )={\begin{bmatrix}3&0&0\\0&2&0\\0&0&20\end{bmatrix}},\qquad G(\mathbf {0} )={\begin{bmatrix}-2.5\\-1\\10.472\end{bmatrix}}.}  ![{\displaystyle J_{G}(\mathbf {0} )={\begin{bmatrix}3&0&0\\0&2&0\\0&0&20\end{bmatrix}},\qquad G(\mathbf {0} )={\begin{bmatrix}-2.5\\-1\\10.472\end{bmatrix}}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e90a90b31c95af2cccea00cf025c041e5228c647) 

Thus

       x   ( 1 )   =  0  − −   η η   0     [    − −  7.5     − −  2     209.44    ]   ,   {\displaystyle \mathbf {x} ^{(1)}=\mathbf {0} -\eta _{0}{\begin{bmatrix}-7.5\\-2\\209.44\end{bmatrix}},}  ![{\displaystyle \mathbf {x} ^{(1)}=\mathbf {0} -\eta _{0}{\begin{bmatrix}-7.5\\-2\\209.44\end{bmatrix}},}](https://wikimedia.org/api/rest_v1/media/math/render/svg/11c69f5345d6222e6238b4ae22bc3eb1ca0c0924) 

and

     f (  0  ) = 0.5  (  ( − −  2.5  )  2   + ( − −  1  )  2   + ( 10.472  )  2    )  = 58.456.   {\displaystyle f(\mathbf {0} )=0.5\left((-2.5)^{2}+(-1)^{2}+(10.472)^{2}\right)=58.456.}  ![{\displaystyle f(\mathbf {0} )=0.5\left((-2.5)^{2}+(-1)^{2}+(10.472)^{2}\right)=58.456.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/08d7cbf06614cc328c0955fd10d2dddeeb5ebe23) 

Now, a suitable      η η   0     {\displaystyle \eta _{0}}  ![{\displaystyle \eta _{0}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ef3886c3f161b7f02d23221bfead21a18ffb82ff) must be found such that

     f  (   x   ( 1 )   )  ≤ ≤  f  (   x   ( 0 )   )  = f (  0  ) .   {\displaystyle f\left(\mathbf {x} ^{(1)}\right)\leq f\left(\mathbf {x} ^{(0)}\right)=f(\mathbf {0} ).}  ![{\displaystyle f\left(\mathbf {x} ^{(1)}\right)\leq f\left(\mathbf {x} ^{(0)}\right)=f(\mathbf {0} ).}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6b504c9de91de9e0b1dd85a96d8b778dedd84734) 

This can be done with any of a variety of [line search](./Line_search) algorithms. One might also simply guess      η η   0   = 0.001 ,   {\displaystyle \eta _{0}=0.001,}  ![{\displaystyle \eta _{0}=0.001,}](https://wikimedia.org/api/rest_v1/media/math/render/svg/509fb1dafab8b9f14788aca57dd06940dc1066d8) which gives

       x   ( 1 )   =   [    0.0075     0.002     − −  0.20944    ]   .   {\displaystyle \mathbf {x} ^{(1)}={\begin{bmatrix}0.0075\\0.002\\-0.20944\\\end{bmatrix}}.}  ![{\displaystyle \mathbf {x} ^{(1)}={\begin{bmatrix}0.0075\\0.002\\-0.20944\\\end{bmatrix}}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/685640a7600f2b9f2b69fc9bbbb1ab448af8a487) 

Evaluating the objective function at this value, yields

     f  (   x   ( 1 )   )  = 0.5  (  ( − −  2.48  )  2   + ( − −  1.00  )  2   + ( 6.28  )  2    )  = 23.306.   {\displaystyle f\left(\mathbf {x} ^{(1)}\right)=0.5\left((-2.48)^{2}+(-1.00)^{2}+(6.28)^{2}\right)=23.306.}  ![{\displaystyle f\left(\mathbf {x} ^{(1)}\right)=0.5\left((-2.48)^{2}+(-1.00)^{2}+(6.28)^{2}\right)=23.306.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/79df72924f1aa4d4fa5886bbd37ee4c9eeb3770b) 

The decrease from     f (  0  ) = 58.456   {\displaystyle f(\mathbf {0} )=58.456}  ![{\displaystyle f(\mathbf {0} )=58.456}](https://wikimedia.org/api/rest_v1/media/math/render/svg/54b4036d6c293c46e7535e2a269d71c1f12ecb31) to the next step's value of

     f  (   x   ( 1 )   )  = 23.306   {\displaystyle f\left(\mathbf {x} ^{(1)}\right)=23.306}  ![{\displaystyle f\left(\mathbf {x} ^{(1)}\right)=23.306}](https://wikimedia.org/api/rest_v1/media/math/render/svg/efa2e84afa98511a87ff55b16480cd5683a98e25) 

is a sizable decrease in the objective function. Further steps would reduce its value further until an approximate solution to the system was found.

 

## Comments

 

Gradient descent works in spaces of any number of dimensions, even in infinite-dimensional ones. In the latter case, the search space is typically a [function space](./Function_space), and one calculates the [Fréchet derivative](./Fréchet_derivative) of the functional to be minimized to determine the descent direction.[[7]](./Gradient_descent#cite_note-AK82-7)

 

That gradient descent works in any number of dimensions (finite number at least) can be seen as a consequence of the [Cauchy–Schwarz inequality](./Cauchy–Schwarz_inequality), i.e. the magnitude of the inner (dot) product of two vectors of any dimension is maximized when they are [colinear](./Colinear). In the case of gradient descent, that would be when the vector of independent variable adjustments is proportional to the gradient vector of partial derivatives.

 

The gradient descent can take many iterations to compute a local minimum with a required [accuracy](./Accuracy), if the [curvature](./Curvature) in different directions is very different for the given function. For such functions, [preconditioning](./Preconditioning), which changes the geometry of the space to shape the function level sets like [concentric circles](./Concentric_circles), cures the slow convergence. Constructing and applying preconditioning can be computationally expensive, however.

 

The gradient descent can be modified via momentums[[16]](./Gradient_descent#cite_note-16) ([Nesterov](./Nesterov), Polyak,[[17]](./Gradient_descent#cite_note-17) and Frank–Wolfe[[18]](./Gradient_descent#cite_note-18)) and heavy-ball parameters (exponential moving averages[[19]](./Gradient_descent#cite_note-19) and positive-negative momentum[[20]](./Gradient_descent#cite_note-20)). The main examples of such optimizers are Adam, DiffGrad, Yogi, AdaBelief, etc.

 

Methods based on [Newton's method](./Newton's_method_in_optimization) and inversion of the [Hessian](./Hessian_matrix) using [conjugate gradient](./Conjugate_gradient) techniques can be better alternatives.[[21]](./Gradient_descent#cite_note-21)[[22]](./Gradient_descent#cite_note-22) Generally, such methods converge in fewer iterations, but the cost of each iteration is higher. An example is the [BFGS method](./Broyden–Fletcher–Goldfarb–Shanno_algorithm) which consists in calculating on every step a matrix by which the gradient vector is multiplied to go into a "better" direction, combined with a more sophisticated [line search](./Line_search) algorithm, to find the "best" value of     η η  .   {\displaystyle \eta .}  ![{\displaystyle \eta .}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fc94fc42a3ecbad87643808e17ec9634147cf812) For extremely large problems, where the computer-memory issues dominate, a limited-memory method such as [L-BFGS](./Limited-memory_BFGS) should be used instead of BFGS or the steepest descent. 

 

While it is sometimes possible to substitute gradient descent for a [local search](./Local_search_(optimization)) algorithm, gradient descent is not in the same family: although it is an [iterative method](./Iterative_method) for [local optimization](./Global_optimization), it relies on an [objective function's gradient](./Loss_function) rather than an explicit exploration of a [solution space](./Feasible_region).

 

Gradient descent can be viewed as applying [Euler's method](./Euler's_method) for solving [ordinary differential equations](./Ordinary_differential_equations)      x ′  ( t ) = − −  ∇ ∇  f ( x ( t ) )   {\displaystyle x'(t)=-\nabla f(x(t))}  ![{\displaystyle x'(t)=-\nabla f(x(t))}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f7efd24e9cf34508df8d402a5b9801290acb2afc) to a [gradient flow](./Gradient_flow).  In turn, this equation may be derived as an optimal controller[[23]](./Gradient_descent#cite_note-23) for the control system      x ′  ( t ) = u ( t )   {\displaystyle x'(t)=u(t)}  ![{\displaystyle x'(t)=u(t)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/861cfd9214a74c07501a0b53535245f7d96715ec) with     u ( t )   {\displaystyle u(t)}  ![{\displaystyle u(t)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b375df3b65d282f8715835dc91ccb22f46993959) given in feedback form     u ( t ) = − −  ∇ ∇  f ( x ( t ) )   {\displaystyle u(t)=-\nabla f(x(t))}  ![{\displaystyle u(t)=-\nabla f(x(t))}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f86ee85b8175055e73c54efb92404922a835f7dd).

 

## Modifications

 

Gradient descent can converge to a local minimum and slow down in a neighborhood of a [saddle point](./Saddle_point). Even for unconstrained quadratic minimization, gradient descent develops a zig–zag pattern of subsequent iterates as iterations progress, resulting in slow convergence. Multiple modifications of gradient descent have been proposed to address these deficiencies.

 

### Fast gradient methods

 

[Yurii Nesterov](./Yurii_Nesterov) has proposed[[24]](./Gradient_descent#cite_note-24) a simple modification that enables faster convergence for convex problems and has been since further generalized. For unconstrained smooth problems, the method is called the [fast gradient method](./Fast_gradient_method?action=edit&redlink=1) (FGM) or the [accelerated gradient method](./Accelerated_gradient_method?action=edit&redlink=1) (AGM). Specifically, if the differentiable function     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) is convex and     ∇ ∇  f   {\displaystyle \nabla f}  ![{\displaystyle \nabla f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b7b4d6de89b52c5a5e6e1583cb63eaee263e307b) is [Lipschitz](./Lipschitz_continuity), and it is not assumed that     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) is [strongly convex](./Convex_function#Strongly_convex_functions), then the error in the objective value generated at each step     k   {\displaystyle k}  ![{\displaystyle k}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c3c9a2c7b599b37105512c5d570edc034056dd40) by the gradient descent method will be [bounded by](./Big_O_notation)       O    (   k  − −  1    )    {\textstyle {\mathcal {O}}\left({k^{-1}}\right)}  ![{\textstyle {\mathcal {O}}\left({k^{-1}}\right)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/88d4397c2f60be08675706a530f8029e45e25e00). Using the Nesterov acceleration technique, the error decreases at       O    (   k  − −  2    )    {\textstyle {\mathcal {O}}\left({k^{-2}}\right)}  ![{\textstyle {\mathcal {O}}\left({k^{-2}}\right)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/25c553eab8e24c9b73b4b543a86d4cf8ea56324f).[[25]](./Gradient_descent#cite_note-25)[[26]](./Gradient_descent#cite_note-26) It is known that the rate       O    (   k  − −  2    )    {\displaystyle {\mathcal {O}}\left({k^{-2}}\right)}  ![{\displaystyle {\mathcal {O}}\left({k^{-2}}\right)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3f99834ce0fe13b17fc7d4fc3fcf51ea74ced8d1) for the decrease of the [cost function](./Loss_function) is optimal for first-order optimization methods. Nevertheless, there is the opportunity to improve the algorithm by reducing the constant factor. The [optimized gradient method](./Optimized_gradient_method?action=edit&redlink=1) (OGM)[[27]](./Gradient_descent#cite_note-27) reduces that constant by a factor of two and is an optimal first-order method for large-scale problems.[[28]](./Gradient_descent#cite_note-28)

 

For constrained or non-smooth problems, Nesterov's FGM is called the [fast proximal gradient method](./Fast_proximal_gradient_method?action=edit&redlink=1) (FPGM), an acceleration of the [proximal gradient method](./Proximal_gradient_method).

 

### Momentum or *heavy ball* method

 

Trying to break the zig-zag pattern of gradient descent, the *momentum or heavy ball method* uses a momentum term in analogy to a heavy ball sliding on the surface of values of the function being minimized,[[6]](./Gradient_descent#cite_note-BP-6) or to mass movement in [Newtonian dynamics](./Newtonian_dynamics) through a [viscous](./Viscous) medium in a [conservative force](./Conservative_force) field.[[29]](./Gradient_descent#cite_note-29) Gradient descent with momentum remembers the solution update at each iteration, and determines the next update as a [linear combination](./Linear_combination) of the gradient and the previous update. For unconstrained quadratic minimization, a theoretical convergence rate bound of the heavy ball method is asymptotically the same as that for the optimal [conjugate gradient method](./Conjugate_gradient_method).[[6]](./Gradient_descent#cite_note-BP-6)

 

This technique is used in [stochastic gradient descent](./Stochastic_gradient_descent#Momentum) and as an extension to the [backpropagation](./Backpropagation) algorithms used to train [artificial neural networks](./Artificial_neural_network).[[30]](./Gradient_descent#cite_note-30)[[31]](./Gradient_descent#cite_note-31) In the direction of updating, stochastic gradient descent adds a stochastic property. The weights can be used to calculate the derivatives.

 

## Extensions

 

Gradient descent can be extended to handle [constraints](./Constraint_(mathematics)) by including a [projection](./Projection_(linear_algebra)) onto the set of constraints. This method is only feasible when the projection is efficiently computable on a computer. Under suitable assumptions, this method converges.  This method is a specific case of the [forward–backward algorithm](./Forward–backward_algorithm) for monotone inclusions (which includes [convex programming](./Convex_programming) and [variational inequalities](./Variational_inequality)).[[32]](./Gradient_descent#cite_note-32)

 

Gradient descent is a special case of [mirror descent](./Mirror_descent) using the squared Euclidean distance as the given [Bregman divergence](./Bregman_divergence).[[33]](./Gradient_descent#cite_note-33)

 

## Theoretical properties

 

The properties of gradient descent depend on the properties of the objective function and the variant of gradient descent used (for example, if a [line search](./Line_search) step is used). The assumptions made affect the convergence rate, and other properties, that can be proven for gradient descent.[[34]](./Gradient_descent#cite_note-:1-34) For example, if the objective is assumed to be [strongly convex](./Strongly_convex_function) and [lipschitz smooth](./Lipschitz_continuity), then gradient descent converges linearly with a fixed step size.[[1]](./Gradient_descent#cite_note-auto-1) Looser assumptions lead to either weaker convergence guarantees or require a more sophisticated step size selection.[[34]](./Gradient_descent#cite_note-:1-34)

 

## Examples

 
- [Yang–Mills flow](./Yang–Mills_flow)
- [Yang–Mills–Higgs flow](./Yang–Mills–Higgs_flow)
- [Seiberg–Witten flow](./Seiberg–Witten_flow)

 

## See also

  
- [Backtracking line search](./Backtracking_line_search)
- [Conjugate gradient method](./Conjugate_gradient_method)
- [Stochastic gradient descent](./Stochastic_gradient_descent)
- [Rprop](./Rprop)
- [Delta rule](./Delta_rule)
- [Wolfe conditions](./Wolfe_conditions)
- [Preconditioning](./Preconditioning)
- [Broyden–Fletcher–Goldfarb–Shanno algorithm](./Broyden–Fletcher–Goldfarb–Shanno_algorithm)
- [Davidon–Fletcher–Powell formula](./Davidon–Fletcher–Powell_formula)
- [Nelder–Mead method](./Nelder–Mead_method)
- [Gauss–Newton algorithm](./Gauss–Newton_algorithm)
- [Hill climbing](./Hill_climbing)
- [Quantum annealing](./Quantum_annealing)
- [CLS](./TFNP#CLS) (continuous local search)
- [Neuroevolution](./Neuroevolution)

  

## References

 
1. [1](./Gradient_descent#cite_ref-auto_1-0) [2](./Gradient_descent#cite_ref-auto_1-1) Boyd, Stephen; Vandenberghe, Lieven (2004-03-08). *Convex Optimization*. Cambridge University Press. [doi](./Doi_(identifier)):[10.1017/cbo9780511804441](https://doi.org/10.1017%2Fcbo9780511804441). [ISBN](./ISBN_(identifier)) [978-0-521-83378-3](./Special:BookSources/978-0-521-83378-3).
2. [↑](./Gradient_descent#cite_ref-2) Lemaréchal, C. (1 January 2012). ["Cauchy and the gradient method"](https://web.archive.org/web/20181229073335/https://www.math.uni-bielefeld.de/documenta/vol-ismp/40_lemarechal-claude.pdf) (PDF). In [Grötschel, M.](./Martin_Grötschel) (ed.). *Optimization Stories*. Documenta Mathematica Series. Vol. 6 (1st ed.). EMS Press. pp. 251–254. [doi](./Doi_(identifier)):[10.4171/dms/6/27](https://doi.org/10.4171%2Fdms%2F6%2F27). [ISBN](./ISBN_(identifier)) [978-3-936609-58-5](./Special:BookSources/978-3-936609-58-5). Archived from [the original](https://www.math.uni-bielefeld.de/documenta/vol-ismp/40_lemarechal-claude.pdf) (PDF) on 2018-12-29. Retrieved 2020-01-26.
3. [↑](./Gradient_descent#cite_ref-3) Hadamard, Jacques (1908). "Mémoire sur le problème d'analyse relatif à l'équilibre des plaques élastiques encastrées". *Mémoires présentés par divers savants éstrangers à l'Académie des Sciences de l'Institut de France*. **33**.
4. [↑](./Gradient_descent#cite_ref-4) Courant, R. (1943). ["Variational methods for the solution of problems of equilibrium and vibrations"](https://doi.org/10.1090%2FS0002-9904-1943-07818-4). *Bulletin of the American Mathematical Society*. **49** (1): 1–23. [doi](./Doi_(identifier)):[10.1090/S0002-9904-1943-07818-4](https://doi.org/10.1090%2FS0002-9904-1943-07818-4).
5. [↑](./Gradient_descent#cite_ref-5) Curry, Haskell B. (1944). ["The Method of Steepest Descent for Non-linear Minimization Problems"](https://doi.org/10.1090%2Fqam%2F10667). *Quart. Appl. Math*. **2** (3): 258–261. [doi](./Doi_(identifier)):[10.1090/qam/10667](https://doi.org/10.1090%2Fqam%2F10667).
6. [1](./Gradient_descent#cite_ref-BP_6-0) [2](./Gradient_descent#cite_ref-BP_6-1) [3](./Gradient_descent#cite_ref-BP_6-2) [4](./Gradient_descent#cite_ref-BP_6-3) [5](./Gradient_descent#cite_ref-BP_6-4) [Polyak, Boris](./Boris_T._Polyak?action=edit&redlink=1) (1987). [*Introduction to Optimization*](https://www.researchgate.net/publication/342978480).
7. [1](./Gradient_descent#cite_ref-AK82_7-0) [2](./Gradient_descent#cite_ref-AK82_7-1) Akilov, G. P.; [Kantorovich, L. V.](./Leonid_Kantorovich) (1982). *Functional Analysis* (2nd ed.). Pergamon Press. [ISBN](./ISBN_(identifier)) [0-08-023036-9](./Special:BookSources/0-08-023036-9).
8. [↑](./Gradient_descent#cite_ref-8) Barzilai, Jonathan; Borwein, Jonathan M. (1988). "Two-Point Step Size Gradient Methods". *IMA Journal of Numerical Analysis*. **8** (1): 141–148. [doi](./Doi_(identifier)):[10.1093/imanum/8.1.141](https://doi.org/10.1093%2Fimanum%2F8.1.141).
9. [↑](./Gradient_descent#cite_ref-9) Fletcher, R. (2005). "On the Barzilai–Borwein Method". In Qi, L.; Teo, K.; Yang, X. (eds.). *Optimization and Control with Applications*. Applied Optimization. Vol. 96. Boston: Springer. pp. 235–256. [ISBN](./ISBN_(identifier)) [0-387-24254-6](./Special:BookSources/0-387-24254-6).
10. [↑](./Gradient_descent#cite_ref-10) Wolfe, Philip (April 1969). "Convergence Conditions for Ascent Methods". *SIAM Review*. **11** (2): 226–235. [doi](./Doi_(identifier)):[10.1137/1011036](https://doi.org/10.1137%2F1011036).
11. [↑](./Gradient_descent#cite_ref-11) Bernstein, Jeremy; Vahdat, Arash; Yue, Yisong; Liu, Ming-Yu (2020-06-12). "On the distance between two neural networks and the stability of learning". [arXiv](./ArXiv_(identifier)):[2002.03432](https://arxiv.org/abs/2002.03432) [[cs.LG](https://arxiv.org/archive/cs.LG)].
12. [↑](./Gradient_descent#cite_ref-12) Haykin, Simon S. Adaptive filter theory. Pearson Education India, 2008. - p. 108-142, 217-242
13. [↑](./Gradient_descent#cite_ref-saad1996iterative_13-0) Saad, Yousef (2003). [*Iterative methods for sparse linear systems*](https://archive.org/details/iterativemethods0000saad/page/195) (2nd ed.). Philadelphia, Pa.: Society for Industrial and Applied Mathematics. pp. [195](https://archive.org/details/iterativemethods0000saad/page/195). [ISBN](./ISBN_(identifier)) [978-0-89871-534-7](./Special:BookSources/978-0-89871-534-7).
14. [1](./Gradient_descent#cite_ref-:0_14-0) [2](./Gradient_descent#cite_ref-:0_14-1) Bouwmeester, Henricus; Dougherty, Andrew; Knyazev, Andrew V. (2015). ["Nonsymmetric Preconditioning for Conjugate Gradient and Steepest Descent Methods"](https://doi.org/10.1016%2Fj.procs.2015.05.241). *Procedia Computer Science*. **51**: 276–285. [arXiv](./ArXiv_(identifier)):[1212.6680](https://arxiv.org/abs/1212.6680). [doi](./Doi_(identifier)):[10.1016/j.procs.2015.05.241](https://doi.org/10.1016%2Fj.procs.2015.05.241).
15. [↑](./Gradient_descent#cite_ref-15) Holmes, M. (2023). *Introduction to Scientific Computing and Data Analysis, 2nd Ed*. Springer. [ISBN](./ISBN_(identifier)) [978-3-031-22429-4](./Special:BookSources/978-3-031-22429-4).
16. [↑](./Gradient_descent#cite_ref-16) Abdulkadirov, Ruslan; Lyakhov, Pavel; Nagornov, Nikolay (January 2023). ["Survey of Optimization Algorithms in Modern Neural Networks"](https://doi.org/10.3390%2Fmath11112466). *Mathematics*. **11** (11): 2466. [doi](./Doi_(identifier)):[10.3390/math11112466](https://doi.org/10.3390%2Fmath11112466). [ISSN](./ISSN_(identifier)) [2227-7390](https://search.worldcat.org/issn/2227-7390).
17. [↑](./Gradient_descent#cite_ref-17) Diakonikolas, Jelena; Jordan, Michael I. (January 2021). ["Generalized Momentum-Based Methods: A Hamiltonian Perspective"](https://epubs.siam.org/doi/10.1137/20M1322716). *SIAM Journal on Optimization*. **31** (1): 915–944. [arXiv](./ArXiv_(identifier)):[1906.00436](https://arxiv.org/abs/1906.00436). [doi](./Doi_(identifier)):[10.1137/20M1322716](https://doi.org/10.1137%2F20M1322716). [ISSN](./ISSN_(identifier)) [1052-6234](https://search.worldcat.org/issn/1052-6234).
18. [↑](./Gradient_descent#cite_ref-18) Meyer, Gerard G. L. (November 1974). ["Accelerated Frank–Wolfe Algorithms"](http://epubs.siam.org/doi/10.1137/0312050). *SIAM Journal on Control*. **12** (4): 655–663. [doi](./Doi_(identifier)):[10.1137/0312050](https://doi.org/10.1137%2F0312050). [ISSN](./ISSN_(identifier)) [0036-1402](https://search.worldcat.org/issn/0036-1402).
19. [↑](./Gradient_descent#cite_ref-19) Kingma, Diederik P.; Ba, Jimmy (2017-01-29), *Adam: A Method for Stochastic Optimization*, [arXiv](./ArXiv_(identifier)):[1412.6980](https://arxiv.org/abs/1412.6980)
20. [↑](./Gradient_descent#cite_ref-20) Xie, Zeke; Yuan, Li; Zhu, Zhanxing; Sugiyama, Masashi (2021-07-01). ["Positive-Negative Momentum: Manipulating Stochastic Gradient Noise to Improve Generalization"](https://proceedings.mlr.press/v139/xie21h.html). *Proceedings of the 38th International Conference on Machine Learning*. PMLR: 11448–11458. [arXiv](./ArXiv_(identifier)):[2103.17182](https://arxiv.org/abs/2103.17182).
21. [↑](./Gradient_descent#cite_ref-21) [Press, W. H.](./William_H._Press); [Teukolsky, S. A.](./Saul_Teukolsky); Vetterling, W. T.; [Flannery, B. P.](./Brian_P._Flannery) (1992). [*Numerical Recipes in C: The Art of Scientific Computing*](https://archive.org/details/numericalrecipes00pres_0) (2nd ed.). New York: [Cambridge University Press](./Cambridge_University_Press). [ISBN](./ISBN_(identifier)) [0-521-43108-5](./Special:BookSources/0-521-43108-5).
22. [↑](./Gradient_descent#cite_ref-22) Strutz, T. (2016). *Data Fitting and Uncertainty: A Practical Introduction to Weighted Least Squares and Beyond* (2nd ed.). Springer Vieweg. [ISBN](./ISBN_(identifier)) [978-3-658-11455-8](./Special:BookSources/978-3-658-11455-8).
23. [↑](./Gradient_descent#cite_ref-23) Ross, I.M. (July 2019). ["An optimal control theory for nonlinear optimization"](https://doi.org/10.1016%2Fj.cam.2018.12.044). *Journal of Computational and Applied Mathematics*. **354**: 39–51. [doi](./Doi_(identifier)):[10.1016/j.cam.2018.12.044](https://doi.org/10.1016%2Fj.cam.2018.12.044). [S2CID](./S2CID_(identifier)) [127649426](https://api.semanticscholar.org/CorpusID:127649426).
24. [↑](./Gradient_descent#cite_ref-24) [Nesterov, Yurii](./Yurii_Nesterov) (2004). *Introductory Lectures on Convex Optimization: A Basic Course*. Springer. [ISBN](./ISBN_(identifier)) [1-4020-7553-7](./Special:BookSources/1-4020-7553-7).
25. [↑](./Gradient_descent#cite_ref-25) Vandenberghe, Lieven (2019). ["Fast Gradient Methods"](https://www.seas.ucla.edu/~vandenbe/236C/lectures/fgrad.pdf) (PDF). *Lecture notes for EE236C at UCLA*.
26. [↑](./Gradient_descent#cite_ref-26) Walkington, Noel J. (2023). ["Nesterov's Method for Convex Optimization"](https://epubs.siam.org/doi/10.1137/21M1390037). *SIAM Review*. **65** (2): 539–562. [doi](./Doi_(identifier)):[10.1137/21M1390037](https://doi.org/10.1137%2F21M1390037). [ISSN](./ISSN_(identifier)) [0036-1445](https://search.worldcat.org/issn/0036-1445).
27. [↑](./Gradient_descent#cite_ref-27) Kim, D.; Fessler, J. A. (2016). ["Optimized First-order Methods for Smooth Convex Minimization"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5067109). *[Mathematical Programming](./Mathematical_Programming)*. **151** (1–2): 81–107. [arXiv](./ArXiv_(identifier)):[1406.5468](https://arxiv.org/abs/1406.5468). [doi](./Doi_(identifier)):[10.1007/s10107-015-0949-3](https://doi.org/10.1007%2Fs10107-015-0949-3). [PMC](./PMC_(identifier)) [5067109](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5067109). [PMID](./PMID_(identifier)) [27765996](https://pubmed.ncbi.nlm.nih.gov/27765996). [S2CID](./S2CID_(identifier)) [207055414](https://api.semanticscholar.org/CorpusID:207055414).
28. [↑](./Gradient_descent#cite_ref-28) Drori, Yoel (2017). "The Exact Information-based Complexity of Smooth Convex Minimization". *Journal of Complexity*. **39**: 1–16. [arXiv](./ArXiv_(identifier)):[1606.01424](https://arxiv.org/abs/1606.01424). [doi](./Doi_(identifier)):[10.1016/j.jco.2016.11.001](https://doi.org/10.1016%2Fj.jco.2016.11.001). [S2CID](./S2CID_(identifier)) [205861966](https://api.semanticscholar.org/CorpusID:205861966).
29. [↑](./Gradient_descent#cite_ref-29) Qian, Ning (January 1999). "On the momentum term in gradient descent learning algorithms". *[Neural Networks](./Neural_Networks_(journal))*. **12** (1): 145–151. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.57.5612](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.57.5612). [doi](./Doi_(identifier)):[10.1016/S0893-6080(98)00116-6](https://doi.org/10.1016%2FS0893-6080%2898%2900116-6). [PMID](./PMID_(identifier)) [12662723](https://pubmed.ncbi.nlm.nih.gov/12662723). [S2CID](./S2CID_(identifier)) [2783597](https://api.semanticscholar.org/CorpusID:2783597).
30. [↑](./Gradient_descent#cite_ref-30) ["Momentum and Learning Rate Adaptation"](http://www.willamette.edu/~gorr/classes/cs449/momrate.html). [Willamette University](./Willamette_University). Retrieved 17 October 2014.
31. [↑](./Gradient_descent#cite_ref-31) [Geoffrey Hinton](./Geoffrey_Hinton); Nitish Srivastava; Kevin Swersky. ["The momentum method"](https://www.coursera.org/lecture/neural-networks/the-momentum-method-Oya9a). *[Coursera](./Coursera)*. Retrieved 2 October 2018.[*[dead link](./Wikipedia:Link_rot)*] Part of a lecture series for the [Coursera](./Coursera) online course [Neural Networks for Machine Learning](https://www.coursera.org/learn/neural-networks) [Archived](https://web.archive.org/web/20161231174321/https://www.coursera.org/learn/neural-networks) 2016-12-31 at the [Wayback Machine](./Wayback_Machine).
32. [↑](./Gradient_descent#cite_ref-32) Combettes, P. L.; Pesquet, J.-C. (2011). "Proximal splitting methods in signal processing". In Bauschke, H. H.; [Burachik, R. S.](./Regina_S._Burachik); Combettes, P. L.; Elser, V.; Luke, D. R.; Wolkowicz, H. (eds.). *Fixed-Point Algorithms for Inverse Problems in Science and Engineering*. New York: Springer. pp. 185–212. [arXiv](./ArXiv_(identifier)):[0912.3522](https://arxiv.org/abs/0912.3522). [ISBN](./ISBN_(identifier)) [978-1-4419-9568-1](./Special:BookSources/978-1-4419-9568-1).
33. [↑](./Gradient_descent#cite_ref-33) ["Mirror descent algorithm"](https://tlienart.github.io/posts/2018/10/27-mirror-descent-algorithm/).
34. [1](./Gradient_descent#cite_ref-:1_34-0) [2](./Gradient_descent#cite_ref-:1_34-1) Bubeck, Sébastien (2015). "Convex Optimization: Algorithms and Complexity". [arXiv](./ArXiv_(identifier)):[1405.4980](https://arxiv.org/abs/1405.4980) [[math.OC](https://arxiv.org/archive/math.OC)].

 

## Further reading

 
- [Boyd, Stephen](./Stephen_P._Boyd); Vandenberghe, Lieven (2004). ["Unconstrained Minimization"](https://web.stanford.edu/~boyd/cvxbook/bv_cvxbook.pdf#page=471) (PDF). *Convex Optimization*. New York: Cambridge University Press. pp. 457–520. [ISBN](./ISBN_(identifier)) [0-521-83378-7](./Special:BookSources/0-521-83378-7).
- Chong, Edwin K. P.; Żak, Stanislaw H. (2013). ["Gradient Methods"](https://books.google.com/books?id=iD5s0iKXHP8C&pg=PA131). *An Introduction to Optimization* (Fourth ed.). Hoboken: Wiley. pp. 131–160. [ISBN](./ISBN_(identifier)) [978-1-118-27901-4](./Special:BookSources/978-1-118-27901-4).
- Himmelblau, David M. (1972). "Unconstrained Minimization Procedures Using Derivatives". *Applied Nonlinear Programming*. New York: McGraw-Hill. pp. 63–132. [ISBN](./ISBN_(identifier)) [0-07-028921-2](./Special:BookSources/0-07-028921-2).

 

## External links

   [![Wikimedia Commons logo](//upload.wikimedia.org/wikipedia/en/thumb/4/4a/Commons-logo.svg/40px-Commons-logo.svg.png)](./File:Commons-logo.svg) Wikimedia Commons has media related to [Gradient descent](https://commons.wikimedia.org/wiki/Category:Gradient%20descent).  
- [Using gradient descent in C++, Boost, Ublas for linear regression](https://codingplayground.blogspot.it/2013/05/learning-linear-regression-with.html)
- [Series of Khan Academy videos discusses gradient ascent](https://www.khanacademy.org/math/multivariable-calculus/multivariable-derivatives/gradient-and-directional-derivatives/v/gradient)
- [Online book teaching gradient descent in deep neural network context](http://neuralnetworksanddeeplearning.com/chap1.html#learning_with_gradient_descent)
- Archived at [Ghostarchive](https://ghostarchive.org/varchive/youtube/20211211/IHZwWFHWa-w) and the [Wayback Machine](https://web.archive.org/web/20171016173155/https://www.youtube.com/watch?v=IHZwWFHWa-w): ["Gradient Descent, How Neural Networks Learn"](https://www.youtube.com/watch?v=IHZwWFHWa-w&list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi&index=2). *3Blue1Brown*. October 16, 2017 – via [YouTube](./YouTube).
- Garrigos, Guillaume; Gower, Robert M. (2023). "Handbook of Convergence Theorems for (Stochastic) Gradient Methods". [arXiv](./ArXiv_(identifier)):[2301.11235](https://arxiv.org/abs/2301.11235) [[math.OC](https://arxiv.org/archive/math.OC)].

 
| vteArtificial intelligence(AI) |
| --- |
| HistorytimelineGlossaryCompaniesProjectsList of open-source AI software |
| Concepts | Automated reasoningParameterHyperparameterLoss functionsRegressionBias–variance tradeoffDouble descentOverfittingClusteringGradient descentSGDQuasi-Newton methodConjugate gradient methodBackpropagationAttentionConvolutionNormalizationBatchnormActivationSoftmaxSigmoidRectifierGatingWeight initializationRegularizationDatasetsAugmentationPrompt engineeringReinforcement learningQ-learningSARSAImitationPolicy gradientDiffusionLatent diffusion modelAutoregressionAdversaryRAGUncanny valleyRLHFSelf-supervised learningReflectionRecursive self-improvementHallucinationWord embeddingVibe codingSymbolic AINeuro-symbolic AI |
| Applications | Automated theorem provingMachine learningIn-context learningArtificial neural networkDeep learningLanguage modelLargeNMTReasoningModel Context ProtocolIntelligent agentAI agentArtificial human companionHumanity's Last ExamLethal autonomous weapons (LAWs)Generative AIWeak AIHypotheticalArtificial general intelligence (AGI)Artificial superintelligence (ASI)Agent2Agent protocol |
| Implementations | Audio–visualAlexNetWaveNetHuman image synthesisHWROCRComputer visionSpeech synthesis15.aiElevenLabsSpeech recognitionWhisperFacial recognitionAlphaFoldText-to-image modelsAuroraDALL-EFireflyFluxGPT ImageIdeogramImagenMidjourneyRecraftStable DiffusionText-to-video modelsDream MachineRunway GenHailuo AIKlingSoraSeedanceVeoMusic generationRiffusionSunoUdioWorld modelsGenieOasisTextList of large language modelsProject DebaterIBM WatsonIBM WatsonxDecisionalAlphaGoAlphaZeroOpenAI FiveSelf-driving carMuZeroAction selectionAutoGPTRobot controlReasoning systemsDeductive classifiersExpert systemsInference enginesKnowledge-based systemsLogic programsProcedural reasoning systemsSemantic reasonersRule-based systemsCognitive architecturesACT-RSoarCLARIONLIDAOpenCogKnowledge basesConceptNetWikidataDBpediaYAGO | Audio–visual | AlexNetWaveNetHuman image synthesisHWROCRComputer visionSpeech synthesis15.aiElevenLabsSpeech recognitionWhisperFacial recognitionAlphaFoldText-to-image modelsAuroraDALL-EFireflyFluxGPT ImageIdeogramImagenMidjourneyRecraftStable DiffusionText-to-video modelsDream MachineRunway GenHailuo AIKlingSoraSeedanceVeoMusic generationRiffusionSunoUdioWorld modelsGenieOasis | Text | List of large language modelsProject DebaterIBM WatsonIBM Watsonx | Decisional | AlphaGoAlphaZeroOpenAI FiveSelf-driving carMuZeroAction selectionAutoGPTRobot control | Reasoning systems | Deductive classifiersExpert systemsInference enginesKnowledge-based systemsLogic programsProcedural reasoning systemsSemantic reasonersRule-based systems | Cognitive architectures | ACT-RSoarCLARIONLIDAOpenCog | Knowledge bases | ConceptNetWikidataDBpediaYAGO |
| Audio–visual | AlexNetWaveNetHuman image synthesisHWROCRComputer visionSpeech synthesis15.aiElevenLabsSpeech recognitionWhisperFacial recognitionAlphaFoldText-to-image modelsAuroraDALL-EFireflyFluxGPT ImageIdeogramImagenMidjourneyRecraftStable DiffusionText-to-video modelsDream MachineRunway GenHailuo AIKlingSoraSeedanceVeoMusic generationRiffusionSunoUdioWorld modelsGenieOasis |
| Text | List of large language modelsProject DebaterIBM WatsonIBM Watsonx |
| Decisional | AlphaGoAlphaZeroOpenAI FiveSelf-driving carMuZeroAction selectionAutoGPTRobot control |
| Reasoning systems | Deductive classifiersExpert systemsInference enginesKnowledge-based systemsLogic programsProcedural reasoning systemsSemantic reasonersRule-based systems |
| Cognitive architectures | ACT-RSoarCLARIONLIDAOpenCog |
| Knowledge bases | ConceptNetWikidataDBpediaYAGO |
| People | Alan TuringWarren Sturgis McCullochWalter PittsJohn von NeumannChristopher D. ManningClaude ShannonShun'ichi AmariKunihiko FukushimaTakeo KanadeMarvin MinskyJohn McCarthyNathaniel RochesterAllen NewellCliff ShawHerbert A. SimonOliver SelfridgeFrank RosenblattBernard WidrowJoseph WeizenbaumSeymour PapertSeppo LinnainmaaPaul WerbosGeoffrey HintonJohn HopfieldJürgen SchmidhuberYann LeCunYoshua BengioLotfi A. ZadehStephen GrossbergAlex GravesJames GoodnightAndrew NgFei-Fei LiAlex KrizhevskyIlya SutskeverOriol VinyalsQuoc V. LeIan GoodfellowDemis HassabisDavid SilverAndrej KarpathyAshish VaswaniNoam ShazeerAidan GomezJohn SchulmanMustafa SuleymanJan LeikeDaniel KokotajloFrançois Chollet |
| Neural network architectures | Neural Turing machineDifferentiable neural computerTransformerVision transformer (ViT)Recurrent neural network (RNN)Long short-term memory (LSTM)Gated recurrent unit (GRU)Echo state networkMultilayer perceptron (MLP)Convolutional neural network (CNN)Residual neural network (RNN)Highway networkMambaAutoencoderVariational autoencoder (VAE)Generative adversarial network (GAN)Graph neural network (GNN) |
| Political | AI Cold WarAI safety(Alignment)AI takeoverElectionsEthics of AIEUAI ActNationalismPrecautionary principleRegulation of AIUSVirtual politicianPropaganda |
| Social and economic | AI boomAI bubbleAI data centerAI effectAI literacyAI slopAI veganismAI winterAnthropomorphismArms raceCompetitionEnvironmental impactExplainable AIGenerative engine optimizationIn architectureIn educationIn fictionIn healthcareChatbot psychosisIn marketingIn video gamesIn visual artMilitary applicationsAI warfareWorkplace impact |
| Category |

 
| vteOptimization:Algorithms,methods, andheuristics |
| --- |
| Unconstrained nonlinearFunctionsGolden-section searchPowell's methodLine searchNelder–Mead methodSuccessive parabolic interpolationGradientsConvergenceTrust regionWolfe conditionsQuasi–NewtonBerndt–Hall–Hall–HausmanBroyden–Fletcher–Goldfarb–ShannoandL-BFGSDavidon–Fletcher–PowellSymmetric rank-one (SR1)Other methodsConjugate gradientGauss–NewtonGradientMirrorLevenberg–MarquardtPowell's dog leg methodTruncated NewtonHessiansNewton's method | Unconstrained nonlinear | FunctionsGolden-section searchPowell's methodLine searchNelder–Mead methodSuccessive parabolic interpolationGradientsConvergenceTrust regionWolfe conditionsQuasi–NewtonBerndt–Hall–Hall–HausmanBroyden–Fletcher–Goldfarb–ShannoandL-BFGSDavidon–Fletcher–PowellSymmetric rank-one (SR1)Other methodsConjugate gradientGauss–NewtonGradientMirrorLevenberg–MarquardtPowell's dog leg methodTruncated NewtonHessiansNewton's method | Functions | Golden-section searchPowell's methodLine searchNelder–Mead methodSuccessive parabolic interpolation | Gradients | ConvergenceTrust regionWolfe conditionsQuasi–NewtonBerndt–Hall–Hall–HausmanBroyden–Fletcher–Goldfarb–ShannoandL-BFGSDavidon–Fletcher–PowellSymmetric rank-one (SR1)Other methodsConjugate gradientGauss–NewtonGradientMirrorLevenberg–MarquardtPowell's dog leg methodTruncated Newton | Convergence | Trust regionWolfe conditions | Quasi–Newton | Berndt–Hall–Hall–HausmanBroyden–Fletcher–Goldfarb–ShannoandL-BFGSDavidon–Fletcher–PowellSymmetric rank-one (SR1) | Other methods | Conjugate gradientGauss–NewtonGradientMirrorLevenberg–MarquardtPowell's dog leg methodTruncated Newton | Hessians | Newton's method | Optimization computes maxima and minima. |
| Unconstrained nonlinear |
| FunctionsGolden-section searchPowell's methodLine searchNelder–Mead methodSuccessive parabolic interpolationGradientsConvergenceTrust regionWolfe conditionsQuasi–NewtonBerndt–Hall–Hall–HausmanBroyden–Fletcher–Goldfarb–ShannoandL-BFGSDavidon–Fletcher–PowellSymmetric rank-one (SR1)Other methodsConjugate gradientGauss–NewtonGradientMirrorLevenberg–MarquardtPowell's dog leg methodTruncated NewtonHessiansNewton's method | Functions | Golden-section searchPowell's methodLine searchNelder–Mead methodSuccessive parabolic interpolation | Gradients | ConvergenceTrust regionWolfe conditionsQuasi–NewtonBerndt–Hall–Hall–HausmanBroyden–Fletcher–Goldfarb–ShannoandL-BFGSDavidon–Fletcher–PowellSymmetric rank-one (SR1)Other methodsConjugate gradientGauss–NewtonGradientMirrorLevenberg–MarquardtPowell's dog leg methodTruncated Newton | Convergence | Trust regionWolfe conditions | Quasi–Newton | Berndt–Hall–Hall–HausmanBroyden–Fletcher–Goldfarb–ShannoandL-BFGSDavidon–Fletcher–PowellSymmetric rank-one (SR1) | Other methods | Conjugate gradientGauss–NewtonGradientMirrorLevenberg–MarquardtPowell's dog leg methodTruncated Newton | Hessians | Newton's method |
| Functions | Golden-section searchPowell's methodLine searchNelder–Mead methodSuccessive parabolic interpolation |
| Gradients | ConvergenceTrust regionWolfe conditionsQuasi–NewtonBerndt–Hall–Hall–HausmanBroyden–Fletcher–Goldfarb–ShannoandL-BFGSDavidon–Fletcher–PowellSymmetric rank-one (SR1)Other methodsConjugate gradientGauss–NewtonGradientMirrorLevenberg–MarquardtPowell's dog leg methodTruncated Newton | Convergence | Trust regionWolfe conditions | Quasi–Newton | Berndt–Hall–Hall–HausmanBroyden–Fletcher–Goldfarb–ShannoandL-BFGSDavidon–Fletcher–PowellSymmetric rank-one (SR1) | Other methods | Conjugate gradientGauss–NewtonGradientMirrorLevenberg–MarquardtPowell's dog leg methodTruncated Newton |
| Convergence | Trust regionWolfe conditions |
| Quasi–Newton | Berndt–Hall–Hall–HausmanBroyden–Fletcher–Goldfarb–ShannoandL-BFGSDavidon–Fletcher–PowellSymmetric rank-one (SR1) |
| Other methods | Conjugate gradientGauss–NewtonGradientMirrorLevenberg–MarquardtPowell's dog leg methodTruncated Newton |
| Hessians | Newton's method |
| Constrained nonlinearGeneralBarrier methodsPenalty methodsDifferentiableAugmented Lagrangian methodsSequential quadratic programmingSuccessive linear programming | Constrained nonlinear | GeneralBarrier methodsPenalty methodsDifferentiableAugmented Lagrangian methodsSequential quadratic programmingSuccessive linear programming | General | Barrier methodsPenalty methods | Differentiable | Augmented Lagrangian methodsSequential quadratic programmingSuccessive linear programming |
| Constrained nonlinear |
| GeneralBarrier methodsPenalty methodsDifferentiableAugmented Lagrangian methodsSequential quadratic programmingSuccessive linear programming | General | Barrier methodsPenalty methods | Differentiable | Augmented Lagrangian methodsSequential quadratic programmingSuccessive linear programming |
| General | Barrier methodsPenalty methods |
| Differentiable | Augmented Lagrangian methodsSequential quadratic programmingSuccessive linear programming |
| Convex optimizationConvexminimizationCutting-plane methodReduced gradient (Frank–Wolfe)Subgradient methodLinearandquadraticInterior pointAffine scalingEllipsoid algorithm of KhachiyanProjective algorithm of KarmarkarBasis-exchangeSimplex algorithm of DantzigRevised simplex algorithmCriss-cross algorithmPrincipal pivoting algorithm of LemkeActive-set method | Convex optimization | ConvexminimizationCutting-plane methodReduced gradient (Frank–Wolfe)Subgradient methodLinearandquadraticInterior pointAffine scalingEllipsoid algorithm of KhachiyanProjective algorithm of KarmarkarBasis-exchangeSimplex algorithm of DantzigRevised simplex algorithmCriss-cross algorithmPrincipal pivoting algorithm of LemkeActive-set method | Convexminimization | Cutting-plane methodReduced gradient (Frank–Wolfe)Subgradient method | Linearandquadratic | Interior pointAffine scalingEllipsoid algorithm of KhachiyanProjective algorithm of KarmarkarBasis-exchangeSimplex algorithm of DantzigRevised simplex algorithmCriss-cross algorithmPrincipal pivoting algorithm of LemkeActive-set method | Interior point | Affine scalingEllipsoid algorithm of KhachiyanProjective algorithm of Karmarkar | Basis-exchange | Simplex algorithm of DantzigRevised simplex algorithmCriss-cross algorithmPrincipal pivoting algorithm of LemkeActive-set method |
| Convex optimization |
| ConvexminimizationCutting-plane methodReduced gradient (Frank–Wolfe)Subgradient methodLinearandquadraticInterior pointAffine scalingEllipsoid algorithm of KhachiyanProjective algorithm of KarmarkarBasis-exchangeSimplex algorithm of DantzigRevised simplex algorithmCriss-cross algorithmPrincipal pivoting algorithm of LemkeActive-set method | Convexminimization | Cutting-plane methodReduced gradient (Frank–Wolfe)Subgradient method | Linearandquadratic | Interior pointAffine scalingEllipsoid algorithm of KhachiyanProjective algorithm of KarmarkarBasis-exchangeSimplex algorithm of DantzigRevised simplex algorithmCriss-cross algorithmPrincipal pivoting algorithm of LemkeActive-set method | Interior point | Affine scalingEllipsoid algorithm of KhachiyanProjective algorithm of Karmarkar | Basis-exchange | Simplex algorithm of DantzigRevised simplex algorithmCriss-cross algorithmPrincipal pivoting algorithm of LemkeActive-set method |
| Convexminimization | Cutting-plane methodReduced gradient (Frank–Wolfe)Subgradient method |
| Linearandquadratic | Interior pointAffine scalingEllipsoid algorithm of KhachiyanProjective algorithm of KarmarkarBasis-exchangeSimplex algorithm of DantzigRevised simplex algorithmCriss-cross algorithmPrincipal pivoting algorithm of LemkeActive-set method | Interior point | Affine scalingEllipsoid algorithm of KhachiyanProjective algorithm of Karmarkar | Basis-exchange | Simplex algorithm of DantzigRevised simplex algorithmCriss-cross algorithmPrincipal pivoting algorithm of LemkeActive-set method |
| Interior point | Affine scalingEllipsoid algorithm of KhachiyanProjective algorithm of Karmarkar |
| Basis-exchange | Simplex algorithm of DantzigRevised simplex algorithmCriss-cross algorithmPrincipal pivoting algorithm of LemkeActive-set method |
| CombinatorialParadigmsApproximation algorithmDynamic programmingGreedy algorithmInteger programmingBranch and bound/cutGraphalgorithmsMinimumspanning treeBorůvkaPrimKruskalShortest pathBellman–FordSPFADijkstraFloyd–WarshallNetwork flowsDinicEdmonds–KarpFord–FulkersonPush–relabel maximum flow | Combinatorial | ParadigmsApproximation algorithmDynamic programmingGreedy algorithmInteger programmingBranch and bound/cutGraphalgorithmsMinimumspanning treeBorůvkaPrimKruskalShortest pathBellman–FordSPFADijkstraFloyd–WarshallNetwork flowsDinicEdmonds–KarpFord–FulkersonPush–relabel maximum flow | Paradigms | Approximation algorithmDynamic programmingGreedy algorithmInteger programmingBranch and bound/cut | Graphalgorithms | Minimumspanning treeBorůvkaPrimKruskalShortest pathBellman–FordSPFADijkstraFloyd–Warshall | Minimumspanning tree | BorůvkaPrimKruskal | Shortest path | Bellman–FordSPFADijkstraFloyd–Warshall | Network flows | DinicEdmonds–KarpFord–FulkersonPush–relabel maximum flow |
| Combinatorial |
| ParadigmsApproximation algorithmDynamic programmingGreedy algorithmInteger programmingBranch and bound/cutGraphalgorithmsMinimumspanning treeBorůvkaPrimKruskalShortest pathBellman–FordSPFADijkstraFloyd–WarshallNetwork flowsDinicEdmonds–KarpFord–FulkersonPush–relabel maximum flow | Paradigms | Approximation algorithmDynamic programmingGreedy algorithmInteger programmingBranch and bound/cut | Graphalgorithms | Minimumspanning treeBorůvkaPrimKruskalShortest pathBellman–FordSPFADijkstraFloyd–Warshall | Minimumspanning tree | BorůvkaPrimKruskal | Shortest path | Bellman–FordSPFADijkstraFloyd–Warshall | Network flows | DinicEdmonds–KarpFord–FulkersonPush–relabel maximum flow |
| Paradigms | Approximation algorithmDynamic programmingGreedy algorithmInteger programmingBranch and bound/cut |
| Graphalgorithms | Minimumspanning treeBorůvkaPrimKruskalShortest pathBellman–FordSPFADijkstraFloyd–Warshall | Minimumspanning tree | BorůvkaPrimKruskal | Shortest path | Bellman–FordSPFADijkstraFloyd–Warshall |
| Minimumspanning tree | BorůvkaPrimKruskal |
| Shortest path | Bellman–FordSPFADijkstraFloyd–Warshall |
| Network flows | DinicEdmonds–KarpFord–FulkersonPush–relabel maximum flow |
| MetaheuristicsEvolutionary algorithmHill climbingLocal searchParallel metaheuristicsSimulated annealingSpiral optimization algorithmTabu search | Metaheuristics | Evolutionary algorithmHill climbingLocal searchParallel metaheuristicsSimulated annealingSpiral optimization algorithmTabu search |
| Metaheuristics |
| Evolutionary algorithmHill climbingLocal searchParallel metaheuristicsSimulated annealingSpiral optimization algorithmTabu search |
| Software |