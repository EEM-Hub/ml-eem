---
source: sources/wiki-Unsupervised_learning.md
source_url: https://en.wikipedia.org/wiki/Unsupervised_learning
chunk: 3/3
---

## Probabilistic methods

 

Two of the main methods used in unsupervised learning are [principal component](./Principal_component_analysis) and [cluster analysis](./Cluster_analysis). Cluster analysis is used in unsupervised learning to group, or segment, datasets with shared attributes in order to extrapolate algorithmic relationships.[[11]](./Unsupervised_learning#cite_note-tds-ul-11) Cluster analysis is a branch of [machine learning](./Machine_learning) that groups the data that has not been [labelled](./Labeled_data), classified or categorized. Instead of responding to feedback, cluster analysis identifies commonalities in the data and reacts based on the presence or absence of such commonalities in each new piece of data. This approach helps detect anomalous data points that do not fit into either group.

 

A central application of unsupervised learning is in the field of [density estimation](./Density_estimation) in [statistics](./Statistics),[[12]](./Unsupervised_learning#cite_note-JordanBishop2004-12) though unsupervised learning encompasses many other domains involving summarizing and explaining data features. It can be contrasted with supervised learning by saying that whereas supervised learning intends to infer a [conditional probability distribution](./Conditional_probability_distribution)  conditioned on the label  of input data; unsupervised learning intends to infer an [a priori probability](./A_priori_probability) distribution .

 

### Approaches

 

Some of the most common algorithms used in unsupervised learning include: (1) Clustering, (2) Anomaly detection, (3) Approaches for learning latent variable models. Each approach uses several methods as follows:

 
- [Clustering](./Data_clustering) methods include: [hierarchical clustering](./Hierarchical_clustering),[[13]](./Unsupervised_learning#cite_note-Hastie-13) [k-means](./K-means),[[14]](./Unsupervised_learning#cite_note-tds-kmeans-14) [mixture models](./Mixture_models), [model-based clustering](./Model-based_clustering), [DBSCAN](./DBSCAN), and [OPTICS algorithm](./OPTICS_algorithm)
- [Anomaly detection](./Anomaly_detection) methods include: [local outlier factor](./Local_outlier_factor), and [isolation forest](./Isolation_forest)
- Approaches for learning [latent variable models](./Latent_variable_model) such as [expectation–maximization algorithm](./Expectation–maximization_algorithm) (EM), [method of moments](./Method_of_moments_(statistics)), and [blind signal separation](./Blind_signal_separation) techniques (principal component analysis, [independent component analysis](./Independent_component_analysis), [non-negative matrix factorization](./Non-negative_matrix_factorization), [singular value decomposition](./Singular_value_decomposition))

 

### Method of moments

 

One of the statistical approaches for unsupervised learning is the [method of moments](./Method_of_moments_(statistics)). In the method of moments, the unknown parameters (of interest) in the model are related to the moments of one or more random variables, and thus, these unknown parameters can be estimated given the moments. The moments are usually estimated from samples empirically. The basic moments are first and second order moments. For a random vector, the first order moment is the [mean](./Mean) vector, and the second order moment is the [covariance matrix](./Covariance_matrix) (when the mean is zero). Higher order moments are usually represented using [tensors](./Tensors) which are the generalization of matrices to higher orders as multi-dimensional arrays.

 

In particular, the method of moments is shown to be effective in learning the parameters of [latent variable models](./Latent_variable_model). Latent variable models are statistical models where in addition to the observed variables, a set of latent variables also exists which is not observed. A highly practical example of latent variable models in machine learning is the [topic modeling](./Topic_modeling) which is a statistical model for generating the words (observed variables) in the document based on the topic (latent variable) of the document. In the topic modeling, the words in the document are generated according to different statistical parameters when the topic of the document is changed. It is shown that method of moments (tensor decomposition techniques) consistently recover the parameters of a large class of latent variable models under some assumptions.[[15]](./Unsupervised_learning#cite_note-TensorLVMs-15)

 

The [Expectation–maximization algorithm](./Expectation–maximization_algorithm) (EM) is also one of the most practical methods for learning latent variable models. However, it can get stuck in local optima, and it is not guaranteed that the algorithm will converge to the true unknown parameters of the model. In contrast, for the method of moments, the global convergence is guaranteed under some conditions.

 

## See also

 
- [Automated machine learning](./Automated_machine_learning)
- [Cluster analysis](./Cluster_analysis)
- [Model-based clustering](./Model-based_clustering)
- [Anomaly detection](./Anomaly_detection)
- [Expectation–maximization algorithm](./Expectation–maximization_algorithm)
- [Generative topographic map](./Generative_topographic_map)
- [Meta-learning (computer science)](./Meta-learning_(computer_science))
- [Multivariate analysis](./Multivariate_analysis)
- [Radial basis function network](./Radial_basis_function_network)
- [Weak supervision](./Weak_supervision)

 

## References

  
1. [↑](./Unsupervised_learning#cite_ref-WeiWu_1-0) Wu, Wei. ["Unsupervised Learning"](https://na.uni-tuebingen.de/ex/ml_seminar_ss2022/Unsupervised_Learning%20Final.pdf) (PDF). [Archived](https://web.archive.org/web/20240414213810/https://na.uni-tuebingen.de/ex/ml_seminar_ss2022/Unsupervised_Learning%20Final.pdf) (PDF) from the original on 14 April 2024. Retrieved 26 April 2024.
2. [↑](./Unsupervised_learning#cite_ref-2) Liu, Xiao; Zhang, Fanjin; Hou, Zhenyu; Mian, Li; Wang, Zhaoyu; Zhang, Jing; Tang, Jie (2021). "Self-supervised Learning: Generative or Contrastive". *IEEE Transactions on Knowledge and Data Engineering*: 1. [arXiv](./ArXiv_(identifier)):[2006.08218](https://arxiv.org/abs/2006.08218). [doi](./Doi_(identifier)):[10.1109/TKDE.2021.3090866](https://doi.org/10.1109%2FTKDE.2021.3090866). [ISSN](./ISSN_(identifier)) [1041-4347](https://search.worldcat.org/issn/1041-4347).
3. [↑](./Unsupervised_learning#cite_ref-gpt1paper_3-0) Radford, Alec; Narasimhan, Karthik; Salimans, Tim; Sutskever, Ilya (11 June 2018). ["Improving Language Understanding by Generative Pre-Training"](https://cdn.openai.com/research-covers/language-unsupervised/language_understanding_paper.pdf) (PDF). [OpenAI](./OpenAI). p. 12. [Archived](https://web.archive.org/web/20210126024542/https://cdn.openai.com/research-covers/language-unsupervised/language_understanding_paper.pdf) (PDF) from the original on 26 January 2021. Retrieved 23 January 2021.
4. [↑](./Unsupervised_learning#cite_ref-4) Li, Zhuohan; Wallace, Eric; Shen, Sheng; Lin, Kevin; Keutzer, Kurt; Klein, Dan; Gonzalez, Joey (2020-11-21). ["Train Big, Then Compress: Rethinking Model Size for Efficient Training and Inference of Transformers"](https://proceedings.mlr.press/v119/li20m.html). *Proceedings of the 37th International Conference on Machine Learning*. PMLR: 5958–5968.
5. [↑](./Unsupervised_learning#cite_ref-Hinton2010_5-0) Hinton, G. (2012). ["A Practical Guide to Training Restricted Boltzmann Machines"](http://www.cs.utoronto.ca/~hinton/absps/guideTR.pdf) (PDF). *Neural Networks: Tricks of the Trade*. Lecture Notes in Computer Science. Vol. 7700. Springer. pp. 599–619. [doi](./Doi_(identifier)):[10.1007/978-3-642-35289-8_32](https://doi.org/10.1007%2F978-3-642-35289-8_32). [ISBN](./ISBN_(identifier)) [978-3-642-35289-8](./Special:BookSources/978-3-642-35289-8). [Archived](https://web.archive.org/web/20220903215809/http://www.cs.utoronto.ca/~hinton/absps/guideTR.pdf) (PDF) from the original on 2022-09-03. Retrieved 2022-11-03.
6. [↑](./Unsupervised_learning#cite_ref-HintonMlss2009_6-0) ["Deep Belief Nets"](https://videolectures.net/mlss09uk_hinton_dbn) (video). September 2009. [Archived](https://web.archive.org/web/20220308022539/http://videolectures.net/mlss09uk_hinton_dbn/) from the original on 2022-03-08. Retrieved 2022-03-27.
7. [↑](./Unsupervised_learning#cite_ref-nc95_7-0) [Peter, Dayan](./Peter_Dayan); [Hinton, Geoffrey E.](./Geoffrey_Hinton); [Neal, Radford M.](./Radford_M._Neal); [Zemel, Richard S.](./Richard_Zemel) (1995). "The Helmholtz machine". *Neural Computation*. **7** (5): 889–904. [doi](./Doi_(identifier)):[10.1162/neco.1995.7.5.889](https://doi.org/10.1162%2Fneco.1995.7.5.889). [hdl](./Hdl_(identifier)):[21.11116/0000-0002-D6D3-E](https://hdl.handle.net/21.11116%2F0000-0002-D6D3-E). [PMID](./PMID_(identifier)) [7584891](https://pubmed.ncbi.nlm.nih.gov/7584891). [S2CID](./S2CID_(identifier)) [1890561](https://api.semanticscholar.org/CorpusID:1890561). [![Closed access icon](//upload.wikimedia.org/wikipedia/commons/thumb/0/0e/Closed_Access_logo_transparent.svg/20px-Closed_Access_logo_transparent.svg.png)](./Paywall)
8. [↑](./Unsupervised_learning#cite_ref-Buhmann_8-0) Buhmann, J.; Kuhnel, H. (1992). "Unsupervised and supervised data clustering with competitive neural networks". *[Proceedings 1992] IJCNN International Joint Conference on Neural Networks*. Vol. 4. IEEE. pp. 796–801. [doi](./Doi_(identifier)):[10.1109/ijcnn.1992.227220](https://doi.org/10.1109%2Fijcnn.1992.227220). [ISBN](./ISBN_(identifier)) [0780305590](./Special:BookSources/0780305590). [S2CID](./S2CID_(identifier)) [62651220](https://api.semanticscholar.org/CorpusID:62651220).
9. [↑](./Unsupervised_learning#cite_ref-Comesana_9-0) Comesaña-Campos, Alberto; Bouza-Rodríguez, José Benito (June 2016). "An application of Hebbian learning in the design process decision-making". *Journal of Intelligent Manufacturing*. **27** (3): 487–506. [doi](./Doi_(identifier)):[10.1007/s10845-014-0881-z](https://doi.org/10.1007%2Fs10845-014-0881-z). [ISSN](./ISSN_(identifier)) [0956-5515](https://search.worldcat.org/issn/0956-5515). [S2CID](./S2CID_(identifier)) [207171436](https://api.semanticscholar.org/CorpusID:207171436).
10. [↑](./Unsupervised_learning#cite_ref-Carpenter_10-0) Carpenter, G.A. & Grossberg, S. (1988). ["The ART of adaptive pattern recognition by a self-organizing neural network"](https://web.archive.org/web/20180516131553/http://www.cns.bu.edu/Profiles/Grossberg/CarGro1988Computer.pdf) (PDF). *Computer*. **21** (3): 77–88. [doi](./Doi_(identifier)):[10.1109/2.33](https://doi.org/10.1109%2F2.33). [S2CID](./S2CID_(identifier)) [14625094](https://api.semanticscholar.org/CorpusID:14625094). Archived from [the original](http://www.cns.bu.edu/Profiles/Grossberg/CarGro1988Computer.pdf) (PDF) on 2018-05-16. Retrieved 2013-09-16.
11. [↑](./Unsupervised_learning#cite_ref-tds-ul_11-0) Roman, Victor (2019-04-21). ["Unsupervised Machine Learning: Clustering Analysis"](https://towardsdatascience.com/unsupervised-machine-learning-clustering-analysis-d40f2b34ae7e). *Medium*. [Archived](https://web.archive.org/web/20200821132257/https://towardsdatascience.com/unsupervised-machine-learning-clustering-analysis-d40f2b34ae7e) from the original on 2020-08-21. Retrieved 2019-10-01.
12. [↑](./Unsupervised_learning#cite_ref-JordanBishop2004_12-0) Jordan, Michael I.; Bishop, Christopher M. (2004). "7. Intelligent Systems §Neural Networks". In Tucker, Allen B. (ed.). [*Computer Science Handbook*](https://www.taylorfrancis.com/books/mono/10.1201/9780203494455/computer-science-handbook-allen-tucker) (2nd ed.). Chapman & Hall/CRC Press. [doi](./Doi_(identifier)):[10.1201/9780203494455](https://doi.org/10.1201%2F9780203494455). [ISBN](./ISBN_(identifier)) [1-58488-360-X](./Special:BookSources/1-58488-360-X). [Archived](https://web.archive.org/web/20221103234201/https://www.taylorfrancis.com/books/mono/10.1201/9780203494455/computer-science-handbook-allen-tucker) from the original on 2022-11-03. Retrieved 2022-11-03.
13. [↑](./Unsupervised_learning#cite_ref-Hastie_13-0) [Hastie, Tibshirani & Friedman 2009](./Unsupervised_learning#CITEREFHastieTibshiraniFriedman2009), pp. 485–586
14. [↑](./Unsupervised_learning#cite_ref-tds-kmeans_14-0) Garbade, Dr Michael J. (2018-09-12). ["Understanding K-means Clustering in Machine Learning"](https://towardsdatascience.com/understanding-k-means-clustering-in-machine-learning-6a6e67336aa1). *Medium*. [Archived](https://web.archive.org/web/20190528183913/https://towardsdatascience.com/understanding-k-means-clustering-in-machine-learning-6a6e67336aa1) from the original on 2019-05-28. Retrieved 2019-10-31.
15. [↑](./Unsupervised_learning#cite_ref-TensorLVMs_15-0) Anandkumar, Animashree; Ge, Rong; Hsu, Daniel; Kakade, Sham; Telgarsky, Matus (2014). ["Tensor Decompositions for Learning Latent Variable Models"](http://www.jmlr.org/papers/volume15/anandkumar14b/anandkumar14b.pdf) (PDF). *Journal of Machine Learning Research*. **15**: 2773–2832. [arXiv](./ArXiv_(identifier)):[1210.7559](https://arxiv.org/abs/1210.7559). [Bibcode](./Bibcode_(identifier)):[2012arXiv1210.7559A](https://ui.adsabs.harvard.edu/abs/2012arXiv1210.7559A). [Archived](https://web.archive.org/web/20150320201108/http://jmlr.org/papers/volume15/anandkumar14b/anandkumar14b.pdf) (PDF) from the original on 2015-03-20. Retrieved 2015-04-10.

 

## Further reading

  
- Bousquet, O.; [von Luxburg, U.](./Ulrike_von_Luxburg); Raetsch, G., eds. (2004). [*Advanced Lectures on Machine Learning*](https://archive.org/details/springer_10.1007-b100712). Springer. [ISBN](./ISBN_(identifier)) [978-3540231226](./Special:BookSources/978-3540231226).
- [Duda, Richard O.](./Richard_O._Duda); [Hart, Peter E.](./Peter_E._Hart); Stork, David G. (2001). "Unsupervised Learning and Clustering". [*Pattern classification*](./Pattern_classification) (2nd ed.). Wiley. [ISBN](./ISBN_(identifier)) [0-471-05669-3](./Special:BookSources/0-471-05669-3).
- [Hastie, Trevor](./Trevor_Hastie); [Tibshirani, Robert](./Robert_Tibshirani); Friedman, Jerome (2009). ["Unsupervised Learning"](https://link.springer.com/chapter/10.1007/978-0-387-84858-7_14). *The Elements of Statistical Learning: Data mining, Inference, and Prediction*. Springer. pp. 485–586. [doi](./Doi_(identifier)):[10.1007/978-0-387-84858-7_14](https://doi.org/10.1007%2F978-0-387-84858-7_14). [ISBN](./ISBN_(identifier)) [978-0-387-84857-0](./Special:BookSources/978-0-387-84857-0). [Archived](https://web.archive.org/web/20221103234204/https://link.springer.com/chapter/10.1007/978-0-387-84858-7_14) from the original on 2022-11-03. Retrieved 2022-11-03.
- [Hinton, Geoffrey](./Geoffrey_Hinton); [Sejnowski, Terrence J.](./Terrence_J._Sejnowski), eds. (1999). *Unsupervised Learning: Foundations of Neural Computation*. [MIT Press](./MIT_Press). [ISBN](./ISBN_(identifier)) [0-262-58168-X](./Special:BookSources/0-262-58168-X).

  
| vteDifferentiable computing |
| --- |
| General | Differentiable programmingInformation geometryStatistical manifoldAutomatic differentiationNeuromorphic computingPattern recognitionRicci calculusComputational learning theoryInductive bias |
| Hardware | IPUTPUVPUMemristorSpiNNaker |
| Software libraries | TensorFlowPyTorchKerasscikit-learnTheanoJAXFlux.jlMindSpore |
| PortalsComputer programmingTechnology |

 
| Authority control databases | GND |
| --- | --- |
