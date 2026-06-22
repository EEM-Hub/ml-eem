---
source: sources/wiki-Gradient_descent.md
source_url: https://en.wikipedia.org/wiki/Gradient_descent
chunk: 5/6
---

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

 


