---
source: sources/wiki-BiasE28093variance_tradeoff.md
source_url: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff
chunk: 3/4
---

## Approaches

 

[Dimensionality reduction](./Dimensionality_reduction) and [feature selection](./Feature_selection) can decrease variance by simplifying models. Similarly, a larger training set tends to decrease variance. Adding features (predictors) tends to decrease bias, at the expense of introducing additional variance. Learning algorithms typically have some tunable parameters that control bias and variance; for example,

 
- [linear](./Linear_model) and [Generalized linear](./Generalized_linear_model) models can be [regularized](./Regularization_(mathematics)) to decrease their variance at the cost of increasing their bias.[[11]](./Bias–variance_tradeoff#cite_note-11)
- In [artificial neural networks](./Artificial_neural_network), the variance increases and the bias decreases as the number of hidden units increase,[[12]](./Bias–variance_tradeoff#cite_note-geman-12) although this classical assumption has been the subject of recent debate.[[4]](./Bias–variance_tradeoff#cite_note-neal2018-4) Like in GLMs, regularization is typically applied.
- In [*k*-nearest neighbor](./K-nearest_neighbor) models, a high value of k leads to high bias and low variance (see below).
- In [instance-based learning](./Instance-based_learning), regularization can be achieved varying the mixture of [prototypes](./Prototype) and exemplars.[[13]](./Bias–variance_tradeoff#cite_note-13)
- In [decision trees](./Decision_tree), the depth of the tree determines the variance. Decision trees are commonly pruned to control variance.[[7]](./Bias–variance_tradeoff#cite_note-islr-7): 307 

 

One way of resolving the trade-off is to use [mixture models](./Mixture_models) and [ensemble learning](./Ensemble_learning).[[14]](./Bias–variance_tradeoff#cite_note-14)[[15]](./Bias–variance_tradeoff#cite_note-15) For example, [boosting](./Boosting_(machine_learning)) combines many "weak" (high bias) models in an ensemble that has lower bias than the individual models, while [bagging](./Bootstrap_aggregating) combines "strong" learners in a way that reduces their variance.

 

[Model validation](./Model_validation) methods such as [cross-validation (statistics)](./Cross-validation_(statistics)) can be used to tune models so as to optimize the trade-off.

 

### *k*-nearest neighbors

 

In the case of [k-nearest neighbors regression](./K-nearest_neighbors_algorithm), when the expectation is taken over the possible labeling of a fixed training set, a [closed-form expression](./Closed-form_expression) exists that relates the bias–variance decomposition to the parameter k:[[8]](./Bias–variance_tradeoff#cite_note-ESL-8): 37, 223 

 

      E   ⁡ ⁡   [    (  y − −     f ^ ^      ( x )  )   2   ∣ ∣  X = x  ]  =   (  f ( x ) − −    1 k    ∑ ∑   i = 1   k   f (  N  i   ( x ) )  )   2   +    σ σ   2   k   +  σ σ   2     {\displaystyle \operatorname {\mathbb {E} } \left[\left(y-{\hat {f}}\!(x)\right)^{2}\mid X=x\right]=\left(f(x)-{\frac {1}{k}}\sum _{i=1}^{k}f(N_{i}(x))\right)^{2}+{\frac {\sigma ^{2}}{k}}+\sigma ^{2}}  ![{\displaystyle \operatorname {\mathbb {E} } \left[\left(y-{\hat {f}}\!(x)\right)^{2}\mid X=x\right]=\left(f(x)-{\frac {1}{k}}\sum _{i=1}^{k}f(N_{i}(x))\right)^{2}+{\frac {\sigma ^{2}}{k}}+\sigma ^{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/bef3ed7bc5663b2bf008a179f54d61e68a01b012)

 

where      N  1   ( x ) , … …  ,  N  k   ( x )   {\displaystyle N_{1}(x),\dots ,N_{k}(x)}  ![{\displaystyle N_{1}(x),\dots ,N_{k}(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5835207a9f81fe493e2b77a4a3ab0ca773e4fc50) are the k nearest neighbors of x in the training set. The bias (first term) is a monotone rising function of k, while the variance (second term) drops off as k is increased. In fact, under "reasonable assumptions" the bias of the first-nearest neighbor (1-NN) estimator vanishes entirely as the size of the training set approaches infinity.[[12]](./Bias–variance_tradeoff#cite_note-geman-12)

 

## Applications

 

### In regression

 

The bias–variance decomposition forms the conceptual basis for regression [regularization](./Regularization_(mathematics)) methods such as [LASSO](./Lasso_(statistics)) and [ridge regression](./Ridge_regression). Regularization methods introduce bias into the regression solution that can reduce variance considerably relative to the [ordinary least squares (OLS)](./Ordinary_least_squares) solution. Although the OLS solution provides non-biased regression estimates, the lower variance solutions produced by regularization techniques provide superior MSE performance.

 

### In classification

 

The bias–variance decomposition was originally formulated for least-squares regression. For the case of [classification](./Statistical_classification) under the [0-1 loss](./0-1_loss) (misclassification rate), it is possible to find a similar decomposition, with the caveat that the variance term becomes dependent on the target label.[[16]](./Bias–variance_tradeoff#cite_note-16)[[17]](./Bias–variance_tradeoff#cite_note-17) Alternatively, if the classification problem can be phrased as [probabilistic classification](./Probabilistic_classification), then the expected cross-entropy can instead be decomposed to give bias and variance terms with the same semantics but taking a different form.

 

It has been argued that as training data increases, the variance of learned models will tend to decrease, and hence that as training data quantity increases, error is minimised by methods that learn models with lesser bias, and that conversely, for smaller training data quantities it is ever more important to minimise variance.[[18]](./Bias–variance_tradeoff#cite_note-18)

 

### In reinforcement learning

 

Even though the bias–variance decomposition does not directly apply in [reinforcement learning](./Reinforcement_learning), a similar tradeoff can also characterize generalization. When an agent has limited information on its environment, the suboptimality of an RL algorithm can be decomposed into the sum of two terms: a term related to an asymptotic bias and a term due to overfitting. The asymptotic bias is directly related to the learning algorithm (independently of the quantity of data) while the overfitting term comes from the fact that the amount of data is limited.[[19]](./Bias–variance_tradeoff#cite_note-19)

 

### In Monte Carlo methods

 

While in traditional Monte Carlo methods the bias is typically zero, modern approaches, such as [Markov chain Monte Carlo](./Markov_chain_Monte_Carlo) are only asymptotically unbiased, at best.[[20]](./Bias–variance_tradeoff#cite_note-20) Convergence diagnostics can be used to control bias via [burn-in](./Burn-in) removal, but due to a limited computational budget, a bias–variance trade-off arises,[[21]](./Bias–variance_tradeoff#cite_note-21) leading to a wide range of approaches, in which a controlled bias is accepted, if this allows to dramatically reduce the variance, and hence the overall estimation error.[[22]](./Bias–variance_tradeoff#cite_note-22)[[23]](./Bias–variance_tradeoff#cite_note-23)[[24]](./Bias–variance_tradeoff#cite_note-24)

 

### In human learning

 

While widely discussed in the context of machine learning, the bias–variance dilemma has been examined in the context of [human cognition](./Cognitive_science), most notably by [Gerd Gigerenzer](./Gerd_Gigerenzer) and co-workers in the context of learned heuristics. They have argued (see references below) that the human brain resolves the dilemma in the case of the typically sparse, poorly-characterized training-sets provided by experience by adopting high-bias/low variance heuristics. This reflects the fact that a zero-bias approach has poor generalizability to new situations, and also unreasonably presumes precise knowledge of the true state of the world. The resulting heuristics are relatively simple, but produce better inferences in a wider variety of situations.[[25]](./Bias–variance_tradeoff#cite_note-ReferenceA-25)

 

[Geman](./Stuart_Geman) et al.[[12]](./Bias–variance_tradeoff#cite_note-geman-12) argue that the bias–variance dilemma implies that abilities such as generic [object recognition](./Object_recognition) cannot be learned from scratch, but require a certain degree of "hard wiring" that is later tuned by experience. This is because model-free approaches to inference require impractically large training sets if they are to avoid high variance.

 

## See also

  
- [Accuracy and precision](./Accuracy_and_precision)
- [Bias of an estimator](./Bias_of_an_estimator)
- [Double descent](./Double_descent)
- [Gauss–Markov theorem](./Gauss–Markov_theorem)
- [Hyperparameter optimization](./Hyperparameter_optimization)
- [Law of total variance](./Law_of_total_variance)
- [Minimum-variance unbiased estimator](./Minimum-variance_unbiased_estimator)
- [Model selection](./Model_selection)
- [Regression model validation](./Regression_model_validation)
- [Supervised learning](./Supervised_learning)
- [Cramér–Rao bound](./Cramér–Rao_bound)
- [Prediction interval](./Prediction_interval)

  

## References

  
1. [↑](./Bias–variance_tradeoff#cite_ref-:0_1-0) Kohavi, Ron; Wolpert, David H. (1996). "Bias Plus Variance Decomposition for Zero-One Loss Functions". *ICML*. **96**.
2. [↑](./Bias–variance_tradeoff#cite_ref-:1_2-0) Luxburg, Ulrike V.; Schölkopf, B. (2011). "Statistical learning theory: Models, concepts, and results". *Handbook of the History of Logic*. **10**: Section 2.4.
3. [↑](./Bias–variance_tradeoff#cite_ref-nealThesis2019_3-0) Neal, Brady (2019). "On the Bias–Variance Tradeoff: Textbooks Need an Update". [arXiv](./ArXiv_(identifier)):[1912.08286](https://arxiv.org/abs/1912.08286) [[cs.LG](https://arxiv.org/archive/cs.LG)].
4. [1](./Bias–variance_tradeoff#cite_ref-neal2018_4-0) [2](./Bias–variance_tradeoff#cite_ref-neal2018_4-1) Neal, Brady; Mittal, Sarthak; Baratin, Aristide; Tantia, Vinayak; Scicluna, Matthew; Lacoste-Julien, Simon; Mitliagkas, Ioannis (2018). "A Modern Take on the Bias–Variance Tradeoff in Neural Networks". [arXiv](./ArXiv_(identifier)):[1810.08591](https://arxiv.org/abs/1810.08591) [[cs.LG](https://arxiv.org/archive/cs.LG)].
5. [↑](./Bias–variance_tradeoff#cite_ref-5) Neal, Brady; Mittal, Sarthak; Baratin, Aristide; Tantia, Vinayak; Scicluna, Matthew; Lacoste-Julien, Simon; Mitliagkas, Ioannis (2019). [*A Modern Take on the Bias–Variance Tradeoff in Neural Networks*](https://openreview.net/forum?id=HkgmzhC5F7). International Conference on Learning Representations (ICLR) 2019.
6. [↑](./Bias–variance_tradeoff#cite_ref-6) Vapnik, Vladimir (2000). [*The nature of statistical learning theory*](https://dx.doi.org/10.1007/978-1-4757-3264-1). New York: Springer-Verlag. [doi](./Doi_(identifier)):[10.1007/978-1-4757-3264-1](https://doi.org/10.1007%2F978-1-4757-3264-1). [ISBN](./ISBN_(identifier)) [978-1-4757-3264-1](./Special:BookSources/978-1-4757-3264-1). [S2CID](./S2CID_(identifier)) [7138354](https://api.semanticscholar.org/CorpusID:7138354).
7. [1](./Bias–variance_tradeoff#cite_ref-islr_7-0) [2](./Bias–variance_tradeoff#cite_ref-islr_7-1) [3](./Bias–variance_tradeoff#cite_ref-islr_7-2) James, Gareth; [Witten, Daniela](./Daniela_Witten); [Hastie, Trevor](./Trevor_Hastie); [Tibshirani, Robert](./Robert_Tibshirani) (2013). [*An Introduction to Statistical Learning*](http://www-bcf.usc.edu/~gareth/ISL/). Springer.
8. [1](./Bias–variance_tradeoff#cite_ref-ESL_8-0) [2](./Bias–variance_tradeoff#cite_ref-ESL_8-1) Hastie, Trevor; Tibshirani, Robert; [Friedman, Jerome H.](./Jerome_H._Friedman) (2009). [*The Elements of Statistical Learning*](https://web.archive.org/web/20150126123924/http://statweb.stanford.edu/~tibs/ElemStatLearn/). Archived from [the original](http://statweb.stanford.edu/~tibs/ElemStatLearn/) on 2015-01-26. Retrieved 2014-08-20.
9. [↑](./Bias–variance_tradeoff#cite_ref-9) [Vijayakumar, Sethu](./Sethu_Vijayakumar) (2007). ["The Bias–Variance Tradeoff"](http://www.inf.ed.ac.uk/teaching/courses/mlsc/Notes/Lecture4/BiasVariance.pdf) (PDF). [University of Edinburgh](./University_of_Edinburgh). Retrieved 19 August 2014.
10. [↑](./Bias–variance_tradeoff#cite_ref-10) Shakhnarovich, Greg (2011). ["Notes on derivation of bias–variance decomposition in linear regression"](https://web.archive.org/web/20140821063842/http://ttic.uchicago.edu/~gregory/courses/wis-ml2012/lectures/biasVarDecom.pdf) (PDF). Archived from [the original](http://ttic.uchicago.edu/~gregory/courses/wis-ml2012/lectures/biasVarDecom.pdf) (PDF) on 21 August 2014. Retrieved 20 August 2014.
11. [↑](./Bias–variance_tradeoff#cite_ref-11) Belsley, David (1991). *Conditioning diagnostics : collinearity and weak data in regression*. New York (NY): Wiley. [ISBN](./ISBN_(identifier)) [978-0471528890](./Special:BookSources/978-0471528890).
12. [1](./Bias–variance_tradeoff#cite_ref-geman_12-0) [2](./Bias–variance_tradeoff#cite_ref-geman_12-1) [3](./Bias–variance_tradeoff#cite_ref-geman_12-2) [Geman, Stuart](./Stuart_Geman); Bienenstock, Élie; Doursat, René (1992). ["Neural networks and the bias/variance dilemma"](http://web.mit.edu/6.435/www/Geman92.pdf) (PDF). *Neural Computation*. **4**: 1–58. [doi](./Doi_(identifier)):[10.1162/neco.1992.4.1.1](https://doi.org/10.1162%2Fneco.1992.4.1.1). [S2CID](./S2CID_(identifier)) [14215320](https://api.semanticscholar.org/CorpusID:14215320).
13. [↑](./Bias–variance_tradeoff#cite_ref-13) Gagliardi, Francesco (May 2011). ["Instance-based classifiers applied to medical databases: diagnosis and knowledge extraction"](https://www.researchgate.net/publication/51173579). *Artificial Intelligence in Medicine*. **52** (3): 123–139. [doi](./Doi_(identifier)):[10.1016/j.artmed.2011.04.002](https://doi.org/10.1016%2Fj.artmed.2011.04.002). [PMID](./PMID_(identifier)) [21621400](https://pubmed.ncbi.nlm.nih.gov/21621400).
14. [↑](./Bias–variance_tradeoff#cite_ref-14) Ting, Jo-Anne; Vijaykumar, Sethu; Schaal, Stefan (2011). "Locally Weighted Regression for Control". In Sammut, Claude; Webb, Geoffrey I. (eds.). [*Encyclopedia of Machine Learning*](http://homepages.inf.ed.ac.uk/svijayak/publications/ting-EMLDM2016.pdf) (PDF). Springer. p. 615. [Bibcode](./Bibcode_(identifier)):[2010eoml.book.....S](https://ui.adsabs.harvard.edu/abs/2010eoml.book.....S).
15. [↑](./Bias–variance_tradeoff#cite_ref-15) Fortmann-Roe, Scott (2012). ["Understanding the Bias–Variance Tradeoff"](http://scott.fortmann-roe.com/docs/BiasVariance.html).
16. [↑](./Bias–variance_tradeoff#cite_ref-16) [Domingos, Pedro](./Pedro_Domingos) (2000). [*A unified bias–variance decomposition*](http://homes.cs.washington.edu/~pedrod/bvd.pdf) (PDF). ICML.
17. [↑](./Bias–variance_tradeoff#cite_ref-17) Valentini, Giorgio; [Dietterich, Thomas G.](./Thomas_G._Dietterich) (2004). ["Bias–variance analysis of support vector machines for the development of SVM-based ensemble methods"](http://www.jmlr.org/papers/volume5/valentini04a/valentini04a.pdf) (PDF). *[Journal of Machine Learning Research](./Journal_of_Machine_Learning_Research)*. **5**: 725–775.
18. [↑](./Bias–variance_tradeoff#cite_ref-18) Brain, Damian; [Webb, Geoffrey](./Geoff_Webb) (2002). [*The Need for Low Bias Algorithms in Classification Learning From Large Data Sets*](http://i.giwebb.com/wp-content/papercite-data/pdf/brainwebb02.pdf) (PDF). Proceedings of the Sixth European Conference on Principles of Data Mining and Knowledge Discovery (PKDD 2002).
19. [↑](./Bias–variance_tradeoff#cite_ref-19) Francois-Lavet, Vincent; Rabusseau, Guillaume; Pineau, Joelle; Ernst, Damien; Fonteneau, Raphael (2019). ["On Overfitting and Asymptotic Bias in Batch Reinforcement Learning with Partial Observability"](https://jair.org/index.php/jair/article/view/11478). *Journal of Artificial Intelligence Research*. **65**: 1–30. [arXiv](./ArXiv_(identifier)):[1709.07796](https://arxiv.org/abs/1709.07796). [doi](./Doi_(identifier)):[10.1613/jair.1.11478](https://doi.org/10.1613%2Fjair.1.11478).
20. [↑](./Bias–variance_tradeoff#cite_ref-20) Zlochin, M.; Baram, Y. (2001). ["The Bias–Variance Dilemma of the Monte Carlo Method"](https://doi.org/10.1007/3-540-44668-0_20). In Dorffner, G.; Bischof, H.; Hornik, K. (eds.). *Artificial Neural Networks — ICANN 2001*. Lecture Notes in Computer Science. Vol. 2130. Springer. pp. 257–264. [doi](./Doi_(identifier)):[10.1007/3-540-44668-0_20](https://doi.org/10.1007%2F3-540-44668-0_20). Retrieved 17 November 2024.
21. [↑](./Bias–variance_tradeoff#cite_ref-21) South, Leah F.; Riabiz, Marina; Teymur, Onur; Oates, Chris J. (March 1, 2022). ["Postprocessing of MCMC"](https://ssrn.com/abstract=4065369). *Annual Review of Statistics and Its Application*. **9** (1): 529–555. [arXiv](./ArXiv_(identifier)):[2103.16048](https://arxiv.org/abs/2103.16048). [Bibcode](./Bibcode_(identifier)):[2022AnRSA...9..529S](https://ui.adsabs.harvard.edu/abs/2022AnRSA...9..529S). [doi](./Doi_(identifier)):[10.1146/annurev-statistics-040220-091727](https://doi.org/10.1146%2Fannurev-statistics-040220-091727). [PMC](./PMC_(identifier)) [7616193](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7616193). [PMID](./PMID_(identifier)) [39006247](https://pubmed.ncbi.nlm.nih.gov/39006247). Retrieved 17 November 2024.
22. [↑](./Bias–variance_tradeoff#cite_ref-22) Nemeth, C.; Fearnhead, P. (2021). ["Stochastic Gradient Markov Chain Monte Carlo"](https://doi.org/10.1080/01621459.2020.1847120). *Journal of the American Statistical Association*. **116** (533): 433–450. [arXiv](./ArXiv_(identifier)):[1907.06986](https://arxiv.org/abs/1907.06986). [doi](./Doi_(identifier)):[10.1080/01621459.2020.1847120](https://doi.org/10.1080%2F01621459.2020.1847120). Retrieved 17 November 2024.
23. [↑](./Bias–variance_tradeoff#cite_ref-23) Vazquez, M.A.; Míguez, J. (2017). ["Importance sampling with transformed weights"](https://doi.org/10.1049/el.2016.3462). *Electronics Letters*. **53** (12): 783–785. [arXiv](./ArXiv_(identifier)):[1702.01987](https://arxiv.org/abs/1702.01987). [Bibcode](./Bibcode_(identifier)):[2017ElL....53..783V](https://ui.adsabs.harvard.edu/abs/2017ElL....53..783V). [doi](./Doi_(identifier)):[10.1049/el.2016.3462](https://doi.org/10.1049%2Fel.2016.3462). Retrieved 17 November 2024.
24. [↑](./Bias–variance_tradeoff#cite_ref-24) Korba, A.; Portier, F. (2022). ["Adaptive Importance Sampling meets Mirror Descent: A Bias–Variance Tradeoff"](https://proceedings.mlr.press/v151/korba22a.html). *Proceedings of The 25th International Conference on Artificial Intelligence and Statistics*. Proceedings of Machine Learning Research. Vol. 151. pp. 11503–11527. Retrieved 17 November 2024.
25. [↑](./Bias–variance_tradeoff#cite_ref-ReferenceA_25-0) [Gigerenzer, Gerd](./Gerd_Gigerenzer); Brighton, Henry (2009). "Homo Heuristicus: Why Biased Minds Make Better Inferences". *Topics in Cognitive Science*. **1** (1): 107–143. [doi](./Doi_(identifier)):[10.1111/j.1756-8765.2008.01006.x](https://doi.org/10.1111%2Fj.1756-8765.2008.01006.x). [hdl](./Hdl_(identifier)):[11858/00-001M-0000-0024-F678-0](https://hdl.handle.net/11858%2F00-001M-0000-0024-F678-0). [PMID](./PMID_(identifier)) [25164802](https://pubmed.ncbi.nlm.nih.gov/25164802).

 


