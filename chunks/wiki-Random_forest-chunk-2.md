---
source: sources/wiki-Random_forest.md
source_url: https://en.wikipedia.org/wiki/Random_forest
chunk: 2/6
---

## Properties

 

### Variable importance

 

Random forests can be used to rank the importance of variables in a regression or classification problem in a natural way.  The following technique was described in Breiman's original paper[[7]](./Random_forest#cite_note-breiman2001-7) and is implemented in the [R](./R_(programming_language)) package `randomForest`.[[8]](./Random_forest#cite_note-rpackage-8)

 

#### Permutation importance

 

To measure a feature's importance in a data set        D    n   = { (  X  i   ,  Y  i   )  }  i = 1   n     {\displaystyle {\mathcal {D}}_{n}=\{(X_{i},Y_{i})\}_{i=1}^{n}}  ![{\displaystyle {\mathcal {D}}_{n}=\{(X_{i},Y_{i})\}_{i=1}^{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ee98824c21c5539b16d0c560a1445101f74898ba), first a random forest is trained on the data.  During training, the [out-of-bag error](./Out-of-bag_error) for each data point is recorded and averaged over the forest. (If bagging is not used during training, we can instead compute errors on an independent test set.)

 

After training, the values of the feature are permuted in the out-of-bag samples and the out-of-bag error is again computed on this perturbed data set. The importance for the feature is computed by averaging the difference in out-of-bag error before and after the permutation over all trees.  The score is normalized by the standard deviation of these differences.

 

Features which produce large values for this score are ranked as more important than features which produce small values. The statistical definition of the variable importance measure was given and analyzed by Zhu *et al.*[[25]](./Random_forest#cite_note-25)

 

This method of determining variable importance has some drawbacks:

 
- When features have different numbers of values, random forests favor features with more values. Solutions to this problem include [partial permutations](./Partial_permutation)[[26]](./Random_forest#cite_note-26)[[27]](./Random_forest#cite_note-27)[[28]](./Random_forest#cite_note-:02-28) and growing unbiased trees.[[29]](./Random_forest#cite_note-29)[[30]](./Random_forest#cite_note-30)
- If the data contain groups of correlated features of similar relevance, then smaller groups are favored over large groups.[[31]](./Random_forest#cite_note-31)
- If there are collinear features, the procedure may fail to identify important features. A solution is to permute groups of correlated features together.[[32]](./Random_forest#cite_note-:2-32)

 

#### Mean decrease in impurity feature importance

 

This approach to feature importance for random forests considers as important the variables which decrease a lot the impurity during splitting.[[33]](./Random_forest#cite_note-33) It is described in the book *Classification and Regression Trees* by Leo Breiman[[34]](./Random_forest#cite_note-34) and is the default implementation in [`scikit learn`](./Scikit-learn) and [R](./R_(programming_language)). The definition is:     unormalized average importance  ( x ) =   1  n  T      ∑ ∑   i = 1    n  T      ∑ ∑    node   j ∈ ∈   T  i    |   split variable  ( j ) = x    p   T  i     ( j ) Δ Δ   i   T  i     ( j ) ,   {\displaystyle {\text{unormalized average importance}}(x)={\frac {1}{n_{T}}}\sum _{i=1}^{n_{T}}\sum _{{\text{node }}j\in T_{i}|{\text{split variable}}(j)=x}p_{T_{i}}(j)\Delta i_{T_{i}}(j),}  ![{\displaystyle {\text{unormalized average importance}}(x)={\frac {1}{n_{T}}}\sum _{i=1}^{n_{T}}\sum _{{\text{node }}j\in T_{i}|{\text{split variable}}(j)=x}p_{T_{i}}(j)\Delta i_{T_{i}}(j),}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f5b9e74f891d6049b82bc70ad12aa30cfb554ce0)where 

 
-     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4) is a feature
-      n  T     {\displaystyle n_{T}}  ![{\displaystyle n_{T}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1972fb23b45426057388210f0927fb46d6ff64ca) is the number of trees in the forest
-      T  i     {\displaystyle T_{i}}  ![{\displaystyle T_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a8dd1c50cb9436474f83624c3f679ccf3eebbfef) is tree     i   {\displaystyle i}  ![{\displaystyle i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/add78d8608ad86e54951b8c8bd6c8d8416533d20)
-      p   T  i     ( j ) =    n  j   n     {\displaystyle p_{T_{i}}(j)={\frac {n_{j}}{n}}}  ![{\displaystyle p_{T_{i}}(j)={\frac {n_{j}}{n}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ca9b544909fc0fbe2a859aef500749359f53ec41) is the fraction of samples reaching node     j   {\displaystyle j}  ![{\displaystyle j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f461e54f5c093e92a55547b9764291390f0b5d0)
-     Δ Δ   i   T  i     ( j )   {\displaystyle \Delta i_{T_{i}}(j)}  ![{\displaystyle \Delta i_{T_{i}}(j)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9766461fceef705ca580069d807ece0cff9b89f5) is the change in impurity in tree     i   {\displaystyle i}  ![{\displaystyle i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/add78d8608ad86e54951b8c8bd6c8d8416533d20) at node     j   {\displaystyle j}  ![{\displaystyle j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f461e54f5c093e92a55547b9764291390f0b5d0).

 

As impurity measure for samples falling in a node e.g. the following statistics can be used:

 
- [Entropy](./Entropy_(information_theory))
- [Gini coefficient](./Gini_coefficient)
- [Mean squared error](./Mean_squared_error)

 

The normalized importance is then obtained by normalizing over all features, so that the sum of normalized feature importances is 1.

 

The `scikit learn` default implementation can report misleading feature importance:[[32]](./Random_forest#cite_note-:2-32)

 
- it favors high cardinality features
- it uses training statistics and so does not reflect a feature's usefulness for predictions on a test set[[35]](./Random_forest#cite_note-35)

 

### Relationship to nearest neighbors

 

A relationship between random forests and the [k-nearest neighbor algorithm](./K-nearest_neighbor_algorithm) (k-NN) was pointed out by Lin and Jeon in 2002.[[36]](./Random_forest#cite_note-linjeon02-36) Both can be viewed as so-called *weighted neighborhoods schemes*. These are models built from a training set     { (  x  i   ,  y  i   )  }  i = 1   n     {\displaystyle \{(x_{i},y_{i})\}_{i=1}^{n}}  ![{\displaystyle \{(x_{i},y_{i})\}_{i=1}^{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0a9e0a59cd73d8fb11a10caa787512bf93af04b4) that make predictions        y ^ ^       {\displaystyle {\hat {y}}}  ![{\displaystyle {\hat {y}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3dc8de3d8ea01304329ef9518fad7a6d196c4c01) for new points x' by looking at the "neighborhood" of the point, formalized by a weight function W:       y ^ ^     =  ∑ ∑   i = 1   n   W (  x  i   ,  x ′  )   y  i   .   {\displaystyle {\hat {y}}=\sum _{i=1}^{n}W(x_{i},x')\,y_{i}.}  ![{\displaystyle {\hat {y}}=\sum _{i=1}^{n}W(x_{i},x')\,y_{i}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f9cd87e3168f0200bd67d04530ab9124dcb8cafc)Here,     W (  x  i   ,  x ′  )   {\displaystyle W(x_{i},x')}  ![{\displaystyle W(x_{i},x')}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f87df356c5a2445516fca56d2df6eb73e64e48ce) is the non-negative weight of the i'th training point relative to the new point x' in the same tree. For any x', the weights for points      x  i     {\displaystyle x_{i}}  ![{\displaystyle x_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e87000dd6142b81d041896a30fe58f0c3acb2158) must sum to 1. Weight functions are as follows:

 
- In k-NN,     W (  x  i   ,  x ′  ) =   1 k     {\displaystyle W(x_{i},x')={\frac {1}{k}}}  ![{\displaystyle W(x_{i},x')={\frac {1}{k}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ae3098adcbde36fd1253a0ee85a3868d67b1861f) if xi is one of the k points closest to x', and zero otherwise.
- In a tree,     W (  x  i   ,  x ′  ) =   1  k ′      {\displaystyle W(x_{i},x')={\frac {1}{k'}}}  ![{\displaystyle W(x_{i},x')={\frac {1}{k'}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d80899c24f8d4488f56290ae99cfe61558667873) if xi is one of the k' points in the same leaf as x', and zero otherwise.

 

Since a forest averages the predictions of a set of m trees with individual weight functions      W  j     {\displaystyle W_{j}}  ![{\displaystyle W_{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fa98874e6beb16373e8d0e056ba550cf653676a1), its predictions are       y ^ ^     =   1 m    ∑ ∑   j = 1   m    ∑ ∑   i = 1   n    W  j   (  x  i   ,  x ′  )   y  i   =  ∑ ∑   i = 1   n    (    1 m    ∑ ∑   j = 1   m    W  j   (  x  i   ,  x ′  )  )    y  i   .   {\displaystyle {\hat {y}}={\frac {1}{m}}\sum _{j=1}^{m}\sum _{i=1}^{n}W_{j}(x_{i},x')\,y_{i}=\sum _{i=1}^{n}\left({\frac {1}{m}}\sum _{j=1}^{m}W_{j}(x_{i},x')\right)\,y_{i}.}  ![{\displaystyle {\hat {y}}={\frac {1}{m}}\sum _{j=1}^{m}\sum _{i=1}^{n}W_{j}(x_{i},x')\,y_{i}=\sum _{i=1}^{n}\left({\frac {1}{m}}\sum _{j=1}^{m}W_{j}(x_{i},x')\right)\,y_{i}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8b819eff4f3bb5ee472825d9996c3fd5f6b18ed7)

 

This shows that the whole forest is again a weighted neighborhood scheme, with weights that average those of the individual trees. The neighbors of x' in this interpretation are the points      x  i     {\displaystyle x_{i}}  ![{\displaystyle x_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e87000dd6142b81d041896a30fe58f0c3acb2158) sharing the same leaf in any tree     j   {\displaystyle j}  ![{\displaystyle j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f461e54f5c093e92a55547b9764291390f0b5d0). In this way, the neighborhood of x' depends in a complex way on the structure of the trees, and thus on the structure of the training set. Lin and Jeon show that the shape of the neighborhood used by a random forest adapts to the local importance of each feature.[[36]](./Random_forest#cite_note-linjeon02-36)

 

## Unsupervised learning

 

As part of their construction, random forest predictors naturally lead to a dissimilarity measure among observations. One can analogously define dissimilarity between unlabeled data, by training a forest to distinguish original "observed" data from suitably generated synthetic data drawn from a reference distribution.[[7]](./Random_forest#cite_note-breiman2001-7)[[37]](./Random_forest#cite_note-37) A random forest dissimilarity is attractive because it handles mixed variable types very well, is invariant to monotonic transformations of the input variables, and is robust to outlying observations. Random forest dissimilarity easily deals with a large number of semi-continuous variables due to its intrinsic variable selection; for example, the "Addcl 1" random forest dissimilarity weighs the contribution of each variable according to how dependent it is on other variables. Random forest dissimilarity has been used in a variety of applications, e.g. to find clusters of patients based on tissue marker data.[[38]](./Random_forest#cite_note-38)

 

## Variants

 

Instead of decision trees, linear models have been proposed and evaluated as base estimators in random forests, in particular [multinomial logistic regression](./Multinomial_logistic_regression) and [naive Bayes classifiers](./Naive_Bayes_classifier).[[39]](./Random_forest#cite_note-:0-39)[[40]](./Random_forest#cite_note-40)[[41]](./Random_forest#cite_note-41) In cases that the relationship between the predictors and the target variable is linear, the base learners may have an equally high accuracy as the ensemble learner.[[42]](./Random_forest#cite_note-:1-42)[[39]](./Random_forest#cite_note-:0-39)

 


