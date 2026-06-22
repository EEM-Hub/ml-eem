---
source: sources/wiki-Random_forest.md
source_url: https://en.wikipedia.org/wiki/Random_forest
chunk: 3/6
---

## Kernel random forest

 

In machine learning, kernel random forests (KeRF) establish the connection between random forests and [kernel methods](./Kernel_method). By slightly modifying their definition, random forests can be rewritten as [kernel methods](./Kernel_method), which are more interpretable and easier to analyze.[[43]](./Random_forest#cite_note-scornet2015random-43)

 

### History

 

[Leo Breiman](./Leo_Breiman)[[44]](./Random_forest#cite_note-breiman2000some-44) was the first person to notice the link between random forest and [kernel methods](./Kernel_methods). He pointed out that random forests trained using [i.i.d.](./I.i.d.) random vectors in the tree construction are equivalent to a kernel acting on the true margin. Lin and Jeon[[45]](./Random_forest#cite_note-lin2006random-45) established the connection between random forests and adaptive nearest neighbor, implying that random forests can be seen as adaptive kernel estimates. Davies and Ghahramani[[46]](./Random_forest#cite_note-davies2014random-46) proposed Kernel Random Forest (KeRF) and showed that it can empirically outperform state-of-art kernel methods. Scornet[[43]](./Random_forest#cite_note-scornet2015random-43) first defined KeRF estimates and gave the explicit link between KeRF estimates and random forest. He also gave explicit expressions for kernels based on centered random forest[[47]](./Random_forest#cite_note-breiman2004consistency-47) and uniform random forest,[[48]](./Random_forest#cite_note-arlot2014analysis-48) two simplified models of random forest. He named these two KeRFs Centered KeRF and Uniform KeRF, and proved upper bounds on their rates of consistency.

 

### Notations and definitions

 

#### Preliminaries: Centered forests

 

Centered forest[[47]](./Random_forest#cite_note-breiman2004consistency-47) is a simplified model for Breiman's original random forest, which uniformly selects an attribute among all attributes and performs splits at the center of the cell along the pre-chosen attribute. The algorithm stops when a fully binary tree of level     k   {\displaystyle k}  ![{\displaystyle k}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c3c9a2c7b599b37105512c5d570edc034056dd40) is built, where     k ∈ ∈   N    {\displaystyle k\in \mathbb {N} }  ![{\displaystyle k\in \mathbb {N} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/2a5bc4b7383031ba693b7433198ead7170954c1d) is a parameter of the algorithm.

 

#### Uniform forest

 

Uniform forest[[48]](./Random_forest#cite_note-arlot2014analysis-48) is another simplified model for Breiman's original random forest, which uniformly selects a feature among all features and performs splits at a point uniformly drawn on the side of the cell, along the preselected feature.

 

#### From random forest to KeRF

 

Given a training sample         D    n   = { (   X   i   ,  Y  i   )  }  i = 1   n     {\displaystyle {\mathcal {D}}_{n}=\{(\mathbf {X} _{i},Y_{i})\}_{i=1}^{n}}  ![{\displaystyle {\mathcal {D}}_{n}=\{(\mathbf {X} _{i},Y_{i})\}_{i=1}^{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c67c8cf7d7485be2a566d02284d9bc27a3f61241) of     [ 0 , 1  ]  p   × ×   R    {\displaystyle [0,1]^{p}\times \mathbb {R} }  ![{\displaystyle [0,1]^{p}\times \mathbb {R} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/6724c5c806dd7cee08c1f2133fc89f94ed0c2e91)-valued independent random variables distributed as the independent prototype pair     (  X  , Y )   {\displaystyle (\mathbf {X} ,Y)}  ![{\displaystyle (\mathbf {X} ,Y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f50eb05dacdb567fc019a3bbcd44b596a1c59a13), where     E ⁡ ⁡  [  Y  2   ] < ∞ ∞    {\displaystyle \operatorname {E} [Y^{2}]<\infty }  ![{\displaystyle \operatorname {E} [Y^{2}]<\infty }](https://wikimedia.org/api/rest_v1/media/math/render/svg/07a863a618762e9fecf30fadce90c3f6484db196). We aim at predicting the response     Y   {\displaystyle Y}  ![{\displaystyle Y}](https://wikimedia.org/api/rest_v1/media/math/render/svg/961d67d6b454b4df2301ac571808a3538b3a6d3f), associated with the random variable      X    {\displaystyle \mathbf {X} }  ![{\displaystyle \mathbf {X} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/9f75966a2f9d5672136fa9401ee1e75008f95ffd), by estimating the regression function     m (  x  ) = E ⁡ ⁡  [ Y ∣ ∣   X  =  x  ]   {\displaystyle m(\mathbf {x} )=\operatorname {E} [Y\mid \mathbf {X} =\mathbf {x} ]}  ![{\displaystyle m(\mathbf {x} )=\operatorname {E} [Y\mid \mathbf {X} =\mathbf {x} ]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0c097ce105048693746d5524ac0ef9fc514da53b). A random regression forest is an ensemble of     M   {\displaystyle M}  ![{\displaystyle M}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f82cade9898ced02fdd08712e5f0c0151758a0dd) randomized regression trees. Denote      m  n   (  x  ,   Θ Θ    j   )   {\displaystyle m_{n}(\mathbf {x} ,\mathbf {\Theta } _{j})}  ![{\displaystyle m_{n}(\mathbf {x} ,\mathbf {\Theta } _{j})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/95ad3dfa3a0ed6fc135df01b527d6be634ff9d07) the predicted value at point      x    {\displaystyle \mathbf {x} }  ![{\displaystyle \mathbf {x} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/32adf004df5eb0a8c7fd8c0b6b7405183c5a5ef2) by the     j   {\displaystyle j}  ![{\displaystyle j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f461e54f5c093e92a55547b9764291390f0b5d0)-th tree, where       Θ Θ    1   , … …  ,   Θ Θ    M     {\displaystyle \mathbf {\Theta } _{1},\ldots ,\mathbf {\Theta } _{M}}  ![{\displaystyle \mathbf {\Theta } _{1},\ldots ,\mathbf {\Theta } _{M}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8588793690df49c9b10f8c44499b1ee82106867f) are independent random variables, distributed as a generic random variable      Θ Θ     {\displaystyle \mathbf {\Theta } }  ![{\displaystyle \mathbf {\Theta } }](https://wikimedia.org/api/rest_v1/media/math/render/svg/1a15b5576ec407e52c5fdfc21c5d7bf45402406a), independent of the sample        D    n     {\displaystyle {\mathcal {D}}_{n}}  ![{\displaystyle {\mathcal {D}}_{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4ba7d8da2372a68d034e848dbd973b7f173769fe). This random variable can be used to describe the randomness induced by node splitting and the sampling procedure for tree construction. The trees are combined to form the finite forest estimate      m  M , n   (  x  ,  Θ Θ   1   , … …  ,  Θ Θ   M   ) =   1 M    ∑ ∑   j = 1   M    m  n   (  x  ,  Θ Θ   j   )   {\displaystyle m_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})={\frac {1}{M}}\sum _{j=1}^{M}m_{n}(\mathbf {x} ,\Theta _{j})}  ![{\displaystyle m_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})={\frac {1}{M}}\sum _{j=1}^{M}m_{n}(\mathbf {x} ,\Theta _{j})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e1cd03b3dba46782bb60f083359fd8e77250024c).
For regression trees, we have      m  n   =  ∑ ∑   i = 1   n       Y  i     1     X   i   ∈ ∈   A  n   (  x  ,  Θ Θ   j   )      N  n   (  x  ,  Θ Θ   j   )      {\displaystyle m_{n}=\sum _{i=1}^{n}{\frac {Y_{i}\mathbf {1} _{\mathbf {X} _{i}\in A_{n}(\mathbf {x} ,\Theta _{j})}}{N_{n}(\mathbf {x} ,\Theta _{j})}}}  ![{\displaystyle m_{n}=\sum _{i=1}^{n}{\frac {Y_{i}\mathbf {1} _{\mathbf {X} _{i}\in A_{n}(\mathbf {x} ,\Theta _{j})}}{N_{n}(\mathbf {x} ,\Theta _{j})}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d1ad1f4a5e0e849bfbf10492b08e5e9b55b6c711), where      A  n   (  x  ,  Θ Θ   j   )   {\displaystyle A_{n}(\mathbf {x} ,\Theta _{j})}  ![{\displaystyle A_{n}(\mathbf {x} ,\Theta _{j})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1811d33726c0ea70d83e6f5ee5228d82e6229300) is the cell containing      x    {\displaystyle \mathbf {x} }  ![{\displaystyle \mathbf {x} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/32adf004df5eb0a8c7fd8c0b6b7405183c5a5ef2), designed with randomness      Θ Θ   j     {\displaystyle \Theta _{j}}  ![{\displaystyle \Theta _{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/10b9d5bab99a44d98171cce92f04d0e700060512) and dataset        D    n     {\displaystyle {\mathcal {D}}_{n}}  ![{\displaystyle {\mathcal {D}}_{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4ba7d8da2372a68d034e848dbd973b7f173769fe), and      N  n   (  x  ,  Θ Θ   j   ) =  ∑ ∑   i = 1   n     1     X   i   ∈ ∈   A  n   (  x  ,  Θ Θ   j   )     {\displaystyle N_{n}(\mathbf {x} ,\Theta _{j})=\sum _{i=1}^{n}\mathbf {1} _{\mathbf {X} _{i}\in A_{n}(\mathbf {x} ,\Theta _{j})}}  ![{\displaystyle N_{n}(\mathbf {x} ,\Theta _{j})=\sum _{i=1}^{n}\mathbf {1} _{\mathbf {X} _{i}\in A_{n}(\mathbf {x} ,\Theta _{j})}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2c13629db1ca0ba725280a4f2bbf7adfc5c9f8a5).

 

Thus random forest estimates satisfy, for all      x  ∈ ∈  [ 0 , 1  ]  d     {\displaystyle \mathbf {x} \in [0,1]^{d}}  ![{\displaystyle \mathbf {x} \in [0,1]^{d}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/691c9727c059400e1d15031c7e0e08fbd6774282),      m  M , n   (  x  ,  Θ Θ   1   , … …  ,  Θ Θ   M   ) =   1 M    ∑ ∑   j = 1   M    (   ∑ ∑   i = 1   n       Y  i     1     X   i   ∈ ∈   A  n   (  x  ,  Θ Θ   j   )      N  n   (  x  ,  Θ Θ   j   )     )    {\displaystyle m_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})={\frac {1}{M}}\sum _{j=1}^{M}\left(\sum _{i=1}^{n}{\frac {Y_{i}\mathbf {1} _{\mathbf {X} _{i}\in A_{n}(\mathbf {x} ,\Theta _{j})}}{N_{n}(\mathbf {x} ,\Theta _{j})}}\right)}  ![{\displaystyle m_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})={\frac {1}{M}}\sum _{j=1}^{M}\left(\sum _{i=1}^{n}{\frac {Y_{i}\mathbf {1} _{\mathbf {X} _{i}\in A_{n}(\mathbf {x} ,\Theta _{j})}}{N_{n}(\mathbf {x} ,\Theta _{j})}}\right)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/671426d343ccaba3944706fd2517e5f7035f674c). Random regression forest has two levels of averaging, first over the samples in the target cell of a tree, then over all trees. Thus the contributions of observations that are in cells with a high density of data points are smaller than that of observations which belong to less populated cells. In order to improve the random forest methods and compensate the misestimation, Scornet[[43]](./Random_forest#cite_note-scornet2015random-43) defined KeRF by
        m ~ ~      M , n   (  x  ,  Θ Θ   1   , … …  ,  Θ Θ   M   ) =   1   ∑ ∑   j = 1   M    N  n   (  x  ,  Θ Θ   j   )     ∑ ∑   j = 1   M    ∑ ∑   i = 1   n    Y  i     1     X   i   ∈ ∈   A  n   (  x  ,  Θ Θ   j   )   ,   {\displaystyle {\tilde {m}}_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})={\frac {1}{\sum _{j=1}^{M}N_{n}(\mathbf {x} ,\Theta _{j})}}\sum _{j=1}^{M}\sum _{i=1}^{n}Y_{i}\mathbf {1} _{\mathbf {X} _{i}\in A_{n}(\mathbf {x} ,\Theta _{j})},}  ![{\displaystyle {\tilde {m}}_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})={\frac {1}{\sum _{j=1}^{M}N_{n}(\mathbf {x} ,\Theta _{j})}}\sum _{j=1}^{M}\sum _{i=1}^{n}Y_{i}\mathbf {1} _{\mathbf {X} _{i}\in A_{n}(\mathbf {x} ,\Theta _{j})},}](https://wikimedia.org/api/rest_v1/media/math/render/svg/565e75beaa1dd3b92753899bfa390abba19af5fc)
which is equal to the mean of the      Y  i     {\displaystyle Y_{i}}  ![{\displaystyle Y_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d57be496fff95ee2a97ee43c7f7fe244b4dbf8ae)'s falling in the cells containing      x    {\displaystyle \mathbf {x} }  ![{\displaystyle \mathbf {x} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/32adf004df5eb0a8c7fd8c0b6b7405183c5a5ef2) in the forest. If we define the connection function of the     M   {\displaystyle M}  ![{\displaystyle M}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f82cade9898ced02fdd08712e5f0c0151758a0dd) finite forest as      K  M , n   (  x  ,  z  ) =   1 M    ∑ ∑   j = 1   M     1    z  ∈ ∈   A  n   (  x  ,  Θ Θ   j   )     {\displaystyle K_{M,n}(\mathbf {x} ,\mathbf {z} )={\frac {1}{M}}\sum _{j=1}^{M}\mathbf {1} _{\mathbf {z} \in A_{n}(\mathbf {x} ,\Theta _{j})}}  ![{\displaystyle K_{M,n}(\mathbf {x} ,\mathbf {z} )={\frac {1}{M}}\sum _{j=1}^{M}\mathbf {1} _{\mathbf {z} \in A_{n}(\mathbf {x} ,\Theta _{j})}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7723dd64358a146a8bc819a79f9c15266b4d37dc), i.e. the proportion of cells shared between      x    {\displaystyle \mathbf {x} }  ![{\displaystyle \mathbf {x} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/32adf004df5eb0a8c7fd8c0b6b7405183c5a5ef2) and      z    {\displaystyle \mathbf {z} }  ![{\displaystyle \mathbf {z} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/82eca5d0928078d5a61b9e7e98cc73db31070909), then almost surely we have         m ~ ~      M , n   (  x  ,  Θ Θ   1   , … …  ,  Θ Θ   M   ) =     ∑ ∑   i = 1   n    Y  i    K  M , n   (  x  ,   x   i   )    ∑ ∑   ℓ ℓ  = 1   n    K  M , n   (  x  ,   x   ℓ ℓ    )      {\displaystyle {\tilde {m}}_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})={\frac {\sum _{i=1}^{n}Y_{i}K_{M,n}(\mathbf {x} ,\mathbf {x} _{i})}{\sum _{\ell =1}^{n}K_{M,n}(\mathbf {x} ,\mathbf {x} _{\ell })}}}  ![{\displaystyle {\tilde {m}}_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})={\frac {\sum _{i=1}^{n}Y_{i}K_{M,n}(\mathbf {x} ,\mathbf {x} _{i})}{\sum _{\ell =1}^{n}K_{M,n}(\mathbf {x} ,\mathbf {x} _{\ell })}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7ea4edc4c4ad2b30acfe0b5898862397424612eb), which defines the KeRF.

 

#### Centered KeRF

 

The construction of Centered KeRF of level     k   {\displaystyle k}  ![{\displaystyle k}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c3c9a2c7b599b37105512c5d570edc034056dd40) is the same as for centered forest, except that predictions are made by         m ~ ~      M , n   (  x  ,  Θ Θ   1   , … …  ,  Θ Θ   M   )   {\displaystyle {\tilde {m}}_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})}  ![{\displaystyle {\tilde {m}}_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3939edfe84d8ece5969248f08b77f0b23843ad3e), the corresponding kernel function, or connection function is
     K  k   c c   (  x  ,  z  ) =  ∑ ∑    k  1   , … …  ,  k  d   ,  ∑ ∑   j = 1   d    k  j   = k      k !    k  1   ! ⋯ ⋯   k  d   !      (   1 d   )   k    ∏ ∏   j = 1   d     1   ⌈ ⌈   2   k  j      x  j   ⌉ ⌉  = ⌈ ⌈   2   k  j      z  j   ⌉ ⌉    ,    for all    x  ,  z  ∈ ∈  [ 0 , 1  ]  d   .   {\displaystyle K_{k}^{cc}(\mathbf {x} ,\mathbf {z} )=\sum _{k_{1},\ldots ,k_{d},\sum _{j=1}^{d}k_{j}=k}{\frac {k!}{k_{1}!\cdots k_{d}!}}\left({\frac {1}{d}}\right)^{k}\prod _{j=1}^{d}\mathbf {1} _{\lceil 2^{k_{j}}x_{j}\rceil =\lceil 2^{k_{j}}z_{j}\rceil },\qquad {\text{ for all }}\mathbf {x} ,\mathbf {z} \in [0,1]^{d}.}  ![{\displaystyle K_{k}^{cc}(\mathbf {x} ,\mathbf {z} )=\sum _{k_{1},\ldots ,k_{d},\sum _{j=1}^{d}k_{j}=k}{\frac {k!}{k_{1}!\cdots k_{d}!}}\left({\frac {1}{d}}\right)^{k}\prod _{j=1}^{d}\mathbf {1} _{\lceil 2^{k_{j}}x_{j}\rceil =\lceil 2^{k_{j}}z_{j}\rceil },\qquad {\text{ for all }}\mathbf {x} ,\mathbf {z} \in [0,1]^{d}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b4b7a16a2bcfb63020d9081379559d5fcd82a7a5)

 

#### Uniform KeRF

 

Uniform KeRF is built in the same way as uniform forest, except that predictions are made by         m ~ ~      M , n   (  x  ,  Θ Θ   1   , … …  ,  Θ Θ   M   )   {\displaystyle {\tilde {m}}_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})}  ![{\displaystyle {\tilde {m}}_{M,n}(\mathbf {x} ,\Theta _{1},\ldots ,\Theta _{M})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3939edfe84d8ece5969248f08b77f0b23843ad3e), the corresponding kernel function, or connection function is
     K  k   u f   (  0  ,  x  ) =  ∑ ∑    k  1   , … …  ,  k  d   ,  ∑ ∑   j = 1   d    k  j   = k      k !    k  1   ! … …   k  d   !      (   1 d   )   k    ∏ ∏   m = 1   d    (  1 − −   |   x  m    |   ∑ ∑   j = 0    k  m   − −  1       (  − −  ln ⁡ ⁡   |   x  m    |   )   j    j !     )    for all    x  ∈ ∈  [ 0 , 1  ]  d   .   {\displaystyle K_{k}^{uf}(\mathbf {0} ,\mathbf {x} )=\sum _{k_{1},\ldots ,k_{d},\sum _{j=1}^{d}k_{j}=k}{\frac {k!}{k_{1}!\ldots k_{d}!}}\left({\frac {1}{d}}\right)^{k}\prod _{m=1}^{d}\left(1-|x_{m}|\sum _{j=0}^{k_{m}-1}{\frac {\left(-\ln |x_{m}|\right)^{j}}{j!}}\right){\text{ for all }}\mathbf {x} \in [0,1]^{d}.}  ![{\displaystyle K_{k}^{uf}(\mathbf {0} ,\mathbf {x} )=\sum _{k_{1},\ldots ,k_{d},\sum _{j=1}^{d}k_{j}=k}{\frac {k!}{k_{1}!\ldots k_{d}!}}\left({\frac {1}{d}}\right)^{k}\prod _{m=1}^{d}\left(1-|x_{m}|\sum _{j=0}^{k_{m}-1}{\frac {\left(-\ln |x_{m}|\right)^{j}}{j!}}\right){\text{ for all }}\mathbf {x} \in [0,1]^{d}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e06f4c0b6697dda0b20263456b511570143a7785)

 

### Properties

 

#### Relation between KeRF and random forest

 

Predictions given by KeRF and random forests are close if the number of points in each cell is controlled:

  

Assume that there exist sequences     (  a  n   ) , (  b  n   )   {\displaystyle (a_{n}),(b_{n})}  ![{\displaystyle (a_{n}),(b_{n})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6d8157b9b64afbd714b16ed6b8de06c32afb696a) such that, almost surely,
     a  n   ≤ ≤   N  n   (  x  , Θ Θ  ) ≤ ≤   b  n     and    a  n   ≤ ≤    1 M    ∑ ∑   m = 1   M    N  n     x  ,  Θ Θ   m    ≤ ≤   b  n   .   {\displaystyle a_{n}\leq N_{n}(\mathbf {x} ,\Theta )\leq b_{n}{\text{ and }}a_{n}\leq {\frac {1}{M}}\sum _{m=1}^{M}N_{n}{\mathbf {x} ,\Theta _{m}}\leq b_{n}.}  ![{\displaystyle a_{n}\leq N_{n}(\mathbf {x} ,\Theta )\leq b_{n}{\text{ and }}a_{n}\leq {\frac {1}{M}}\sum _{m=1}^{M}N_{n}{\mathbf {x} ,\Theta _{m}}\leq b_{n}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/139dc876ec018ffab1c1d499f269b95a6e8c245a)
Then almost surely,
     |   m  M , n   (  x  ) − −      m ~ ~      M , n   (  x  )  |  ≤ ≤      b  n   − −   a  n     a  n         m ~ ~      M , n   (  x  ) .   {\displaystyle |m_{M,n}(\mathbf {x} )-{\tilde {m}}_{M,n}(\mathbf {x} )|\leq {\frac {b_{n}-a_{n}}{a_{n}}}{\tilde {m}}_{M,n}(\mathbf {x} ).}  ![{\displaystyle |m_{M,n}(\mathbf {x} )-{\tilde {m}}_{M,n}(\mathbf {x} )|\leq {\frac {b_{n}-a_{n}}{a_{n}}}{\tilde {m}}_{M,n}(\mathbf {x} ).}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ad592965613268c7026f8f57701caba977fd34ed)

  

#### Relation between infinite KeRF and infinite random forest

 

When the number of trees     M   {\displaystyle M}  ![{\displaystyle M}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f82cade9898ced02fdd08712e5f0c0151758a0dd) goes to infinity, then we have infinite random forest and infinite KeRF. Their estimates are close if the number of observations in each cell is bounded:

  

Assume that there exist sequences     (  ε ε   n   ) , (  a  n   ) , (  b  n   )   {\displaystyle (\varepsilon _{n}),(a_{n}),(b_{n})}  ![{\displaystyle (\varepsilon _{n}),(a_{n}),(b_{n})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/67e5f769151263bad5a8d716a2c6af2686687855) such that, almost surely

 
-     E ⁡ ⁡  [  N  n   (  x  , Θ Θ  ) ] ≥ ≥  1 ,   {\displaystyle \operatorname {E} [N_{n}(\mathbf {x} ,\Theta )]\geq 1,}  ![{\displaystyle \operatorname {E} [N_{n}(\mathbf {x} ,\Theta )]\geq 1,}](https://wikimedia.org/api/rest_v1/media/math/render/svg/07f5beb5ef7860bc9f527fb5b01fbed3dc0fc716)
-     P ⁡ ⁡  [  a  n   ≤ ≤   N  n   (  x  , Θ Θ  ) ≤ ≤   b  n   ∣ ∣     D    n   ] ≥ ≥  1 − −   ε ε   n    /  2 ,   {\displaystyle \operatorname {P} [a_{n}\leq N_{n}(\mathbf {x} ,\Theta )\leq b_{n}\mid {\mathcal {D}}_{n}]\geq 1-\varepsilon _{n}/2,}  ![{\displaystyle \operatorname {P} [a_{n}\leq N_{n}(\mathbf {x} ,\Theta )\leq b_{n}\mid {\mathcal {D}}_{n}]\geq 1-\varepsilon _{n}/2,}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4bad78155a4139322247009072e48d6b7bf8c5b9)
-     P ⁡ ⁡  [  a  n   ≤ ≤   E  Θ Θ    ⁡ ⁡  [  N  n   (  x  , Θ Θ  ) ] ≤ ≤   b  n   ∣ ∣     D    n   ] ≥ ≥  1 − −   ε ε   n    /  2 ,   {\displaystyle \operatorname {P} [a_{n}\leq \operatorname {E} _{\Theta }[N_{n}(\mathbf {x} ,\Theta )]\leq b_{n}\mid {\mathcal {D}}_{n}]\geq 1-\varepsilon _{n}/2,}  ![{\displaystyle \operatorname {P} [a_{n}\leq \operatorname {E} _{\Theta }[N_{n}(\mathbf {x} ,\Theta )]\leq b_{n}\mid {\mathcal {D}}_{n}]\geq 1-\varepsilon _{n}/2,}](https://wikimedia.org/api/rest_v1/media/math/render/svg/71711062ff59f3d2075162074e8f94f917a0cdad)

 

Then almost surely,
     |   m  ∞ ∞  , n   (  x  ) − −      m ~ ~      ∞ ∞  , n   (  x  )  |  ≤ ≤      b  n   − −   a  n     a  n         m ~ ~      ∞ ∞  , n   (  x  ) + n  ε ε   n    (   max  1 ≤ ≤  i ≤ ≤  n    Y  i    )  .   {\displaystyle |m_{\infty ,n}(\mathbf {x} )-{\tilde {m}}_{\infty ,n}(\mathbf {x} )|\leq {\frac {b_{n}-a_{n}}{a_{n}}}{\tilde {m}}_{\infty ,n}(\mathbf {x} )+n\varepsilon _{n}\left(\max _{1\leq i\leq n}Y_{i}\right).}  ![{\displaystyle |m_{\infty ,n}(\mathbf {x} )-{\tilde {m}}_{\infty ,n}(\mathbf {x} )|\leq {\frac {b_{n}-a_{n}}{a_{n}}}{\tilde {m}}_{\infty ,n}(\mathbf {x} )+n\varepsilon _{n}\left(\max _{1\leq i\leq n}Y_{i}\right).}](https://wikimedia.org/api/rest_v1/media/math/render/svg/26197c8d5ca305f9a7a922c4227c5daa11350e76)

  

### Consistency results

 

Assume that     Y = m (  X  ) + ε ε    {\displaystyle Y=m(\mathbf {X} )+\varepsilon }  ![{\displaystyle Y=m(\mathbf {X} )+\varepsilon }](https://wikimedia.org/api/rest_v1/media/math/render/svg/d8617bcdd783f680a6c45c9d8c627a5730a878e5), where     ε ε    {\displaystyle \varepsilon }  ![{\displaystyle \varepsilon }](https://wikimedia.org/api/rest_v1/media/math/render/svg/a30c89172e5b88edbd45d3e2772c7f5e562e5173) is a centered Gaussian noise, independent of      X    {\displaystyle \mathbf {X} }  ![{\displaystyle \mathbf {X} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/9f75966a2f9d5672136fa9401ee1e75008f95ffd), with finite variance      σ σ   2   < ∞ ∞    {\displaystyle \sigma ^{2}<\infty }  ![{\displaystyle \sigma ^{2}<\infty }](https://wikimedia.org/api/rest_v1/media/math/render/svg/f9c01c50d5825dbb5b11add552a422af72a9664f). Moreover,      X    {\displaystyle \mathbf {X} }  ![{\displaystyle \mathbf {X} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/9f75966a2f9d5672136fa9401ee1e75008f95ffd) is uniformly distributed on     [ 0 , 1  ]  d     {\displaystyle [0,1]^{d}}  ![{\displaystyle [0,1]^{d}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e13ae4917276744b214714a20b3cb8ee305e309d) and     m   {\displaystyle m}  ![{\displaystyle m}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0a07d98bb302f3856cbabc47b2b9016692e3f7bc) is [Lipschitz](./Lipschitz_continuity). Scornet[[43]](./Random_forest#cite_note-scornet2015random-43) proved upper bounds on the rates of consistency for centered KeRF and uniform KeRF.

 

#### Consistency of centered KeRF

 

Providing     k → →  ∞ ∞    {\displaystyle k\rightarrow \infty }  ![{\displaystyle k\rightarrow \infty }](https://wikimedia.org/api/rest_v1/media/math/render/svg/612a3ec99f1c9f12de1cfab011e306ae799858ce) and     n  /   2  k   → →  ∞ ∞    {\displaystyle n/2^{k}\rightarrow \infty }  ![{\displaystyle n/2^{k}\rightarrow \infty }](https://wikimedia.org/api/rest_v1/media/math/render/svg/9fbec163fbc2ac671e4c9f78bdc70a985599dc19), there exists a constant      C  1   > 0   {\displaystyle C_{1}>0}  ![{\displaystyle C_{1}>0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c7f2ff302742806f4db7411f29e54944b4d9bda7) such that, for all     n   {\displaystyle n}  ![{\displaystyle n}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a601995d55609f2d9f5e233e36fbe9ea26011b3b),
     E  [     m ~ ~      n   c c   (  X  ) − −  m (  X  )  ]  2   ≤ ≤   C  1    n  − −  1  /  ( 3 + d log ⁡ ⁡  2 )   ( log ⁡ ⁡  n  )  2     {\displaystyle \mathbb {E} [{\tilde {m}}_{n}^{cc}(\mathbf {X} )-m(\mathbf {X} )]^{2}\leq C_{1}n^{-1/(3+d\log 2)}(\log n)^{2}}  ![{\displaystyle \mathbb {E} [{\tilde {m}}_{n}^{cc}(\mathbf {X} )-m(\mathbf {X} )]^{2}\leq C_{1}n^{-1/(3+d\log 2)}(\log n)^{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/bbd76dd80031cfdb1b8042faeab38ecaafefa2e3).

 

#### Consistency of uniform KeRF

 

Providing     k → →  ∞ ∞    {\displaystyle k\rightarrow \infty }  ![{\displaystyle k\rightarrow \infty }](https://wikimedia.org/api/rest_v1/media/math/render/svg/612a3ec99f1c9f12de1cfab011e306ae799858ce) and     n  /   2  k   → →  ∞ ∞    {\displaystyle n/2^{k}\rightarrow \infty }  ![{\displaystyle n/2^{k}\rightarrow \infty }](https://wikimedia.org/api/rest_v1/media/math/render/svg/9fbec163fbc2ac671e4c9f78bdc70a985599dc19), there exists a constant     C > 0   {\displaystyle C>0}  ![{\displaystyle C>0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c84d4126c6df243734f9355927c026df6b0d3859) such that,
     E  [     m ~ ~      n   u f   (  X  ) − −  m (  X  )  ]  2   ≤ ≤  C  n  − −  2  /  ( 6 + 3 d log ⁡ ⁡  2 )   ( log ⁡ ⁡  n  )  2     {\displaystyle \mathbb {E} [{\tilde {m}}_{n}^{uf}(\mathbf {X} )-m(\mathbf {X} )]^{2}\leq Cn^{-2/(6+3d\log 2)}(\log n)^{2}}  ![{\displaystyle \mathbb {E} [{\tilde {m}}_{n}^{uf}(\mathbf {X} )-m(\mathbf {X} )]^{2}\leq Cn^{-2/(6+3d\log 2)}(\log n)^{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/51b3c9f4980f936fc01a73621cc56e9857059da4).

 


