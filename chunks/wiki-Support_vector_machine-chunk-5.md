---
source: sources/wiki-Support_vector_machine.md
source_url: https://en.wikipedia.org/wiki/Support_vector_machine
chunk: 5/7
---

## Extensions

 

### Multiclass SVM

 

Multiclass SVM aims to assign labels to instances by using support vector machines, where the labels are drawn from a finite set of several elements.

 

The dominant approach for doing so is to reduce the single [multiclass problem](./Multiclass_problem) into multiple [binary classification](./Binary_classification) problems.[[30]](./Support_vector_machine#cite_note-duan2005-30) Common methods for such reduction include:[[30]](./Support_vector_machine#cite_note-duan2005-30)[[31]](./Support_vector_machine#cite_note-hsu2002-31)

 
- Building binary classifiers that distinguish between one of the labels and the rest (*one-versus-all*) or between every pair of classes (*one-versus-one*). Classification of new instances for the one-versus-all case is done by a winner-takes-all strategy, in which the classifier with the highest-output function assigns the class (it is important that the output functions be calibrated to produce comparable scores). For the one-versus-one approach, classification is done by a max-wins voting strategy, in which every classifier assigns the instance to one of the two classes, then the vote for the assigned class is increased by one vote, and finally the class with the most votes determines the instance classification.
- [Directed acyclic graph](./Directed_acyclic_graph) SVM (DAGSVM)[[32]](./Support_vector_machine#cite_note-32)
- [Error-correcting output codes](./Error_correcting_code)[[33]](./Support_vector_machine#cite_note-33)

 

Crammer and Singer proposed a multiclass SVM method which casts the [multiclass classification](./Multiclass_classification) problem into a single optimization problem, rather than decomposing it into multiple binary classification problems.[[34]](./Support_vector_machine#cite_note-34) See also Lee, Lin and Wahba[[35]](./Support_vector_machine#cite_note-35)[[36]](./Support_vector_machine#cite_note-36) and Van den Burg and Groenen.[[37]](./Support_vector_machine#cite_note-37)

 

### Transductive support vector machines

 

Transductive support vector machines extend SVMs in that they could also treat partially labeled data in [semi-supervised learning](./Semi-supervised_learning) by following the principles of [transduction](./Transduction_(machine_learning)). Here, in addition to the training set       D     {\displaystyle {\mathcal {D}}}  ![{\displaystyle {\mathcal {D}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3277962e1959c3241fb1b70c7f0ac6dcefebd966), the learner is also given a set

 

       D    ⋆ ⋆    = {   x   i   ⋆ ⋆    ∣ ∣    x   i   ⋆ ⋆    ∈ ∈    R   p    }  i = 1   k     {\displaystyle {\mathcal {D}}^{\star }=\{\mathbf {x} _{i}^{\star }\mid \mathbf {x} _{i}^{\star }\in \mathbb {R} ^{p}\}_{i=1}^{k}}  ![{\displaystyle {\mathcal {D}}^{\star }=\{\mathbf {x} _{i}^{\star }\mid \mathbf {x} _{i}^{\star }\in \mathbb {R} ^{p}\}_{i=1}^{k}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a85548a3b6819a8e9899f7228286674cc457f824)

 

of test examples to be classified. Formally, a transductive support vector machine is defined by the following primal optimization problem:[[38]](./Support_vector_machine#cite_note-38)

 

Minimize (in      w  , b ,   y   ⋆ ⋆      {\displaystyle \mathbf {w} ,b,\mathbf {y} ^{\star }}  ![{\displaystyle \mathbf {w} ,b,\mathbf {y} ^{\star }}](https://wikimedia.org/api/rest_v1/media/math/render/svg/bb4e853e9c2307487503db429df9c87f8812811d))

 

      1 2   ‖ ‖   w   ‖ ‖   2     {\displaystyle {\frac {1}{2}}\|\mathbf {w} \|^{2}}  ![{\displaystyle {\frac {1}{2}}\|\mathbf {w} \|^{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/69a34c96227f9003e853c0c6f8ce15445ede7be1)

 

subject to (for any     i = 1 , … …  , n   {\displaystyle i=1,\dots ,n}  ![{\displaystyle i=1,\dots ,n}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f3f269b2f3b2f87fec0168426652a5ea80b56112) and any     j = 1 , … …  , k   {\displaystyle j=1,\dots ,k}  ![{\displaystyle j=1,\dots ,k}](https://wikimedia.org/api/rest_v1/media/math/render/svg/17b9f8d6a741f04e9280f1aa8ad318057beff36f))

 

          y  i   (  w  ⋅ ⋅    x   i   − −  b ) ≥ ≥  1 ,       y  j   ⋆ ⋆    (  w  ⋅ ⋅    x   j   ⋆ ⋆    − −  b ) ≥ ≥  1 ,       {\displaystyle {\begin{aligned}&y_{i}(\mathbf {w} \cdot \mathbf {x} _{i}-b)\geq 1,\\&y_{j}^{\star }(\mathbf {w} \cdot \mathbf {x} _{j}^{\star }-b)\geq 1,\end{aligned}}}  ![{\displaystyle {\begin{aligned}&y_{i}(\mathbf {w} \cdot \mathbf {x} _{i}-b)\geq 1,\\&y_{j}^{\star }(\mathbf {w} \cdot \mathbf {x} _{j}^{\star }-b)\geq 1,\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2884901096701ede8aad45888b214ff5e423e0dc)

 

and

 

     y  j   ⋆ ⋆    ∈ ∈  { − −  1 , 1 } .   {\displaystyle y_{j}^{\star }\in \{-1,1\}.}  ![{\displaystyle y_{j}^{\star }\in \{-1,1\}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ed01a216a1487a2e935fdfe3bbcae451bacae940)

 

Transductive support vector machines were introduced by Vladimir N. Vapnik in 1998.

 

### Structured SVM

 Main article: [structured SVM](./Structured_SVM) 

Structured support-vector machine is an extension of the traditional SVM model. While the SVM model is primarily designed for binary classification, multiclass classification, and regression tasks, structured SVM broadens its application to handle general structured output labels, for example parse trees, classification with taxonomies, sequence alignment and many more.[[39]](./Support_vector_machine#cite_note-39)

 

### Regression

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/7/7a/Svr_epsilons_demo.svg/250px-Svr_epsilons_demo.svg.png)](./File:Svr_epsilons_demo.svg)Support vector regression (prediction) with different thresholds *ε*. As *ε* increases, the prediction becomes less sensitive to errors. 

A version of SVM for [regression](./Regression_analysis) was proposed in 1996 by [Vladimir N. Vapnik](./Vladimir_N._Vapnik), Harris Drucker, Christopher J. C. Burges, Linda Kaufman and Alexander J. Smola.[[40]](./Support_vector_machine#cite_note-40) This method is called support vector regression (SVR). The model produced by support vector classification (as described above) depends only on a subset of the training data, because the cost function for building the model does not care about training points that lie beyond the margin. Analogously, the model produced by SVR depends only on a subset of the training data, because the cost function for building the model ignores any training data close to the model prediction. Another SVM version known as [least-squares support vector machine](./Least-squares_support_vector_machine) (LS-SVM) has been proposed by Suykens and Vandewalle.[[41]](./Support_vector_machine#cite_note-41)

 

Training the original SVR means solving[[42]](./Support_vector_machine#cite_note-42)

 minimize        1 2    ‖ ‖  w  ‖ ‖   2     {\displaystyle {\tfrac {1}{2}}\|w\|^{2}}  ![{\displaystyle {\tfrac {1}{2}}\|w\|^{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7e57eb5af0505ace268f4e239bec5a5e45b265fd) subject to      |   y  i   − −  ⟨ ⟨  w ,  x  i   ⟩ ⟩  − −  b  |  ≤ ≤  ε ε    {\displaystyle |y_{i}-\langle w,x_{i}\rangle -b|\leq \varepsilon }  ![{\displaystyle |y_{i}-\langle w,x_{i}\rangle -b|\leq \varepsilon }](https://wikimedia.org/api/rest_v1/media/math/render/svg/8e5c77b2ab4ab6c23dc93202502574592354d40d) 

where      x  i     {\displaystyle x_{i}}  ![{\displaystyle x_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e87000dd6142b81d041896a30fe58f0c3acb2158) is a training sample with target value      y  i     {\displaystyle y_{i}}  ![{\displaystyle y_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/67d30d30b6c2dbe4d6f150d699de040937ecc95f). The inner product plus intercept     ⟨ ⟨  w ,  x  i   ⟩ ⟩  + b   {\displaystyle \langle w,x_{i}\rangle +b}  ![{\displaystyle \langle w,x_{i}\rangle +b}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6edf655afe55c88493246d8a6017750083c31de5) is the prediction for that sample, and     ε ε    {\displaystyle \varepsilon }  ![{\displaystyle \varepsilon }](https://wikimedia.org/api/rest_v1/media/math/render/svg/a30c89172e5b88edbd45d3e2772c7f5e562e5173) is a free parameter that serves as a threshold: all predictions have to be within an     ε ε    {\displaystyle \varepsilon }  ![{\displaystyle \varepsilon }](https://wikimedia.org/api/rest_v1/media/math/render/svg/a30c89172e5b88edbd45d3e2772c7f5e562e5173) range of the true predictions. Slack variables are usually added into the above to allow for errors and to allow approximation in the case the above problem is infeasible.

 

### Bayesian SVM

 

In 2011 it was shown by Polson and Scott that the SVM admits a [Bayesian](./Bayesian_probability) interpretation through the technique of [data augmentation](./Data_augmentation).[[43]](./Support_vector_machine#cite_note-43) In this approach the SVM is viewed as a [graphical model](./Graphical_model) (where the parameters are connected via probability distributions). This extended view allows the application of [Bayesian](./Bayesian_probability) techniques to SVMs, such as flexible feature modeling, automatic [hyperparameter](./Hyperparameter_(machine_learning)) tuning, and [predictive uncertainty quantification](./Posterior_predictive_distribution). In 2017, a scalable version of the Bayesian SVM was developed by [Florian Wenzel](https://arxiv.org/search/stat?searchtype=author&query=Wenzel%2C+F), enabling the application of Bayesian SVMs to [big data](./Big_data).[[44]](./Support_vector_machine#cite_note-44) Florian Wenzel developed two different versions, a variational inference (VI) scheme for the Bayesian kernel support vector machine (SVM) and a stochastic version (SVI) for the linear Bayesian SVM.[[45]](./Support_vector_machine#cite_note-45)

 

## Implementation

 

The parameters of the maximum-margin hyperplane are derived by solving the optimization. There exist several specialized algorithms for quickly solving the [quadratic programming](./Quadratic_programming) (QP) problem that arises from SVMs, mostly relying on heuristics for breaking the problem down into smaller, more manageable chunks.

 

Another approach is to use an [interior-point method](./Interior-point_method) that uses [Newton](./Newton's_method)-like iterations to find a solution of the [Karush–Kuhn–Tucker conditions](./Karush–Kuhn–Tucker_conditions) of the primal and dual problems.[[46]](./Support_vector_machine#cite_note-46)
Instead of solving a sequence of broken-down problems, this approach directly solves the problem altogether. To avoid solving a linear system involving the large kernel matrix, a low-rank approximation to the matrix is often used in the kernel trick.

 

Another common method is Platt's [sequential minimal optimization](./Sequential_minimal_optimization) (SMO) algorithm, which breaks the problem down into 2-dimensional sub-problems that are solved analytically, eliminating the need for a numerical optimization algorithm and matrix storage. This algorithm is conceptually simple, easy to implement, generally faster, and has better scaling properties for difficult SVM problems.[[47]](./Support_vector_machine#cite_note-47)

 

The special case of linear support vector machines can be solved more efficiently by the same kind of algorithms used to optimize its close cousin, [logistic regression](./Logistic_regression); this class of algorithms includes [sub-gradient descent](./Stochastic_gradient_descent) (e.g., PEGASOS[[48]](./Support_vector_machine#cite_note-48)) and [coordinate descent](./Coordinate_descent) (e.g., LIBLINEAR[[49]](./Support_vector_machine#cite_note-49)). LIBLINEAR has some attractive training-time properties. Each convergence iteration takes time linear in the time taken to read the train data, and the iterations also have a [Q-linear convergence](./Rate_of_convergence) property, making the algorithm extremely fast.

 

The general kernel SVMs can also be solved more efficiently using [sub-gradient descent](./Stochastic_gradient_descent) (e.g. P-packSVM[[50]](./Support_vector_machine#cite_note-50)), especially when [parallelization](./Parallelization) is allowed.

 

Kernel SVMs are available in many machine-learning toolkits, including [LIBSVM](./LIBSVM), [MATLAB](./MATLAB), [SAS](http://support.sas.com/documentation/cdl/en/whatsnew/64209/HTML/default/viewer.htm#emdocwhatsnew71.htm), SVMlight, [kernlab](https://cran.r-project.org/package=kernlab), [scikit-learn](./Scikit-learn), [Shogun](./Shogun_(toolbox)), [Weka](./Weka_(machine_learning)), [Shark](http://image.diku.dk/shark/), [JKernelMachines](https://mloss.org/software/view/409/), [OpenCV](./OpenCV) and others.

 

Preprocessing of data (standardization) is highly recommended to enhance accuracy of classification.[[51]](./Support_vector_machine#cite_note-51) There are a few methods of standardization, such as min-max, normalization by decimal scaling, Z-score.[[52]](./Support_vector_machine#cite_note-52) Subtraction of mean and division by variance of each feature is usually used for SVM.[[53]](./Support_vector_machine#cite_note-53)

 

## See also

 
- [In situ adaptive tabulation](./In_situ_adaptive_tabulation)
- [Kernel machines](./Kernel_machines)
- [Fisher kernel](./Fisher_kernel)
- [Platt scaling](./Platt_scaling)
- [Polynomial kernel](./Polynomial_kernel)
- [Predictive analytics](./Predictive_analytics)
- [Regularization perspectives on support vector machines](./Regularization_perspectives_on_support_vector_machines)
- [Relevance vector machine](./Relevance_vector_machine), a probabilistic sparse-kernel model identical in functional form to SVM
- [Sequential minimal optimization](./Sequential_minimal_optimization)
- [Space mapping](./Space_mapping)
- [Winnow (algorithm)](./Winnow_(algorithm))
- [Radial basis function network](./Radial_basis_function_network)

 


