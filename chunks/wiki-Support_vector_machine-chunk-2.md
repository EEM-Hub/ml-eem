---
source: sources/wiki-Support_vector_machine.md
source_url: https://en.wikipedia.org/wiki/Support_vector_machine
chunk: 2/7
---

## Linear SVM

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/7/72/SVM_margin.png/330px-SVM_margin.png)](./File:SVM_margin.png)Maximum-margin hyperplane and margins for an SVM trained with samples from two classes. Samples on the margin are called the support vectors. 

We are given a training dataset of     n   {\displaystyle n}  ![{\displaystyle n}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a601995d55609f2d9f5e233e36fbe9ea26011b3b) points of the form
    (   x   1   ,  y  1   ) , … …  , (   x   n   ,  y  n   ) ,   {\displaystyle (\mathbf {x} _{1},y_{1}),\ldots ,(\mathbf {x} _{n},y_{n}),}  ![{\displaystyle (\mathbf {x} _{1},y_{1}),\ldots ,(\mathbf {x} _{n},y_{n}),}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3851f21b1d94ed988a19e869b7993ae18296837c)
where the      y  i     {\displaystyle y_{i}}  ![{\displaystyle y_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/67d30d30b6c2dbe4d6f150d699de040937ecc95f) are either 1 or −1, each indicating the class to which the point       x   i     {\displaystyle \mathbf {x} _{i}}  ![{\displaystyle \mathbf {x} _{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/57d2ef3df60acdb53bdf90535264041fea7231cd) belongs. Each       x   i     {\displaystyle \mathbf {x} _{i}}  ![{\displaystyle \mathbf {x} _{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/57d2ef3df60acdb53bdf90535264041fea7231cd) is a     p   {\displaystyle p}  ![{\displaystyle p}](https://wikimedia.org/api/rest_v1/media/math/render/svg/81eac1e205430d1f40810df36a0edffdc367af36)-dimensional [real](./Real_number) vector. We want to find the "maximum-margin hyperplane" that divides the group of points       x   i     {\displaystyle \mathbf {x} _{i}}  ![{\displaystyle \mathbf {x} _{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/57d2ef3df60acdb53bdf90535264041fea7231cd) for which      y  i   = 1   {\displaystyle y_{i}=1}  ![{\displaystyle y_{i}=1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/13864bfc60110b9306a50b300d2d72b22fa1e371) from the group of points for which      y  i   = − −  1   {\displaystyle y_{i}=-1}  ![{\displaystyle y_{i}=-1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ba5a48e97f8d3c62221dc8eceb13d7c1a66ea89a), which is defined so that the distance between the hyperplane and the nearest point       x   i     {\displaystyle \mathbf {x} _{i}}  ![{\displaystyle \mathbf {x} _{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/57d2ef3df60acdb53bdf90535264041fea7231cd) from either group is maximized.

 

Any [hyperplane](./Hyperplane) can be written as the set of points      x    {\displaystyle \mathbf {x} }  ![{\displaystyle \mathbf {x} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/32adf004df5eb0a8c7fd8c0b6b7405183c5a5ef2) satisfying
      w    T     x  − −  b = 0 ,   {\displaystyle \mathbf {w} ^{\mathsf {T}}\mathbf {x} -b=0,}  ![{\displaystyle \mathbf {w} ^{\mathsf {T}}\mathbf {x} -b=0,}](https://wikimedia.org/api/rest_v1/media/math/render/svg/25fc9adce0ffd096592cc24d4d6a58eca8d72dd0)
where      w    {\displaystyle \mathbf {w} }  ![{\displaystyle \mathbf {w} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/20795664b5b048744a2fd88977851104cc5816f8) is the (not necessarily normalized) [normal vector](./Normal_(geometry)) to the hyperplane. This is much like [Hesse normal form](./Hesse_normal_form), except that      w    {\displaystyle \mathbf {w} }  ![{\displaystyle \mathbf {w} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/20795664b5b048744a2fd88977851104cc5816f8) is not necessarily a unit vector. The parameter        b  ‖ ‖   w  ‖ ‖        {\displaystyle {\tfrac {b}{\|\mathbf {w} \|}}}  ![{\displaystyle {\tfrac {b}{\|\mathbf {w} \|}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/905afdc8c606dc1629d3145153f18b30f8d1cead) determines the offset of the hyperplane from the origin along the normal vector      w    {\displaystyle \mathbf {w} }  ![{\displaystyle \mathbf {w} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/20795664b5b048744a2fd88977851104cc5816f8).

 

Warning: most of the literature on the subject defines the bias so that
      w    T     x  + b = 0.   {\displaystyle \mathbf {w} ^{\mathsf {T}}\mathbf {x} +b=0.}  ![{\displaystyle \mathbf {w} ^{\mathsf {T}}\mathbf {x} +b=0.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/02050652c3997d41fd957dd8c20fa9a33304da1f)

 

### Hard-margin

 

If the training data is [linearly separable](./Linearly_separable), we can select two parallel hyperplanes that separate the two classes of data, so that the distance between them is as large as possible. The region bounded by these two hyperplanes is called the "margin", and the maximum-margin hyperplane is the hyperplane that lies halfway between them. With a normalized or standardized dataset, these hyperplanes can be described by the equations

       w    T     x  − −  b = 1   {\displaystyle \mathbf {w} ^{\mathsf {T}}\mathbf {x} -b=1}  ![{\displaystyle \mathbf {w} ^{\mathsf {T}}\mathbf {x} -b=1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/93dcc30fa2db57f0ea6786dbf52359140ee95e0a) (anything on or above this boundary is of one class, with label 1) 

and

       w    T     x  − −  b = − −  1   {\displaystyle \mathbf {w} ^{\mathsf {T}}\mathbf {x} -b=-1}  ![{\displaystyle \mathbf {w} ^{\mathsf {T}}\mathbf {x} -b=-1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3447b9ee30d70638aa895dca267f4a476e3aaf45) (anything on or below this boundary is of the other class, with label −1). 

Geometrically, the distance between these two hyperplanes is        2  ‖ ‖   w  ‖ ‖        {\displaystyle {\tfrac {2}{\|\mathbf {w} \|}}}  ![{\displaystyle {\tfrac {2}{\|\mathbf {w} \|}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d9e7c92a256c5f7e31b06e7a547eb431f863000d),[[21]](./Support_vector_machine#cite_note-21) so to maximize the distance between the planes we want to minimize     ‖ ‖   w  ‖ ‖    {\displaystyle \|\mathbf {w} \|}  ![{\displaystyle \|\mathbf {w} \|}](https://wikimedia.org/api/rest_v1/media/math/render/svg/16826300cd1c90dfa25572e6a1b3f3f5239557b7). The distance is computed using the [distance from a point to a plane](./Distance_from_a_point_to_a_plane) equation. We also have to prevent data points from falling into the margin, we add the following constraint: for each     i   {\displaystyle i}  ![{\displaystyle i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/add78d8608ad86e54951b8c8bd6c8d8416533d20) either
      w    T      x   i   − −  b ≥ ≥  1  ,   if    y  i   = 1 ,   {\displaystyle \mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-b\geq 1\,,{\text{ if }}y_{i}=1,}  ![{\displaystyle \mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-b\geq 1\,,{\text{ if }}y_{i}=1,}](https://wikimedia.org/api/rest_v1/media/math/render/svg/293ad9400f667cfa7b1ba4891ba586ba1f95b63e)
or
      w    T      x   i   − −  b ≤ ≤  − −  1  ,   if    y  i   = − −  1.   {\displaystyle \mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-b\leq -1\,,{\text{ if }}y_{i}=-1.}  ![{\displaystyle \mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-b\leq -1\,,{\text{ if }}y_{i}=-1.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4b81be87ecd083b666d1b41b70957e9e7a55b07f)
These constraints state that each data point must lie on the correct side of the margin.

 

This can be rewritten as

 
| yi(wTxi−b)≥1,for all1≤i≤n.{\displaystyle y_{i}(\mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-b)\geq 1,\quad {\text{ for all }}1\leq i\leq n.} |  | 1 |
| --- | --- | --- |

 

We can put this together to get the optimization problem:

 

           minimize   w  ,  b         1 2   ‖ ‖   w   ‖ ‖   2         subject to      y  i   (   w   ⊤ ⊤      x   i   − −  b ) ≥ ≥  1  ∀ ∀  i ∈ ∈  { 1 , … …  , n }       {\displaystyle {\begin{aligned}&{\underset {\mathbf {w} ,\;b}{\operatorname {minimize} }}&&{\frac {1}{2}}\|\mathbf {w} \|^{2}\\&{\text{subject to}}&&y_{i}(\mathbf {w} ^{\top }\mathbf {x} _{i}-b)\geq 1\quad \forall i\in \{1,\dots ,n\}\end{aligned}}}  ![{\displaystyle {\begin{aligned}&{\underset {\mathbf {w} ,\;b}{\operatorname {minimize} }}&&{\frac {1}{2}}\|\mathbf {w} \|^{2}\\&{\text{subject to}}&&y_{i}(\mathbf {w} ^{\top }\mathbf {x} _{i}-b)\geq 1\quad \forall i\in \{1,\dots ,n\}\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5864d6dee2beaf117b56da17c6f47e3e54d2b7d7)

 

The      w    {\displaystyle \mathbf {w} }  ![{\displaystyle \mathbf {w} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/20795664b5b048744a2fd88977851104cc5816f8) and     b   {\displaystyle b}  ![{\displaystyle b}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f11423fbb2e967f986e36804a8ae4271734917c3) that solve this problem determine the final classifier,      x  ↦ ↦  sgn ⁡ ⁡  (   w    T     x  − −  b )   {\displaystyle \mathbf {x} \mapsto \operatorname {sgn}(\mathbf {w} ^{\mathsf {T}}\mathbf {x} -b)}  ![{\displaystyle \mathbf {x} \mapsto \operatorname {sgn} (\mathbf {w} ^{\mathsf {T}}\mathbf {x} -b)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7383ad6f1f176a758e6d8fcd8b9bae95d95a2887), where     sgn ⁡ ⁡  ( ⋅ ⋅  )   {\displaystyle \operatorname {sgn}(\cdot )}  ![{\displaystyle \operatorname {sgn} (\cdot )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3d470ff7790cfdb63cfeed4bb4cb8367146e9ae5) is the [sign function](./Sign_function).

 

An important consequence of this geometric description is that the max-margin hyperplane is completely determined by those       x   i     {\displaystyle \mathbf {x} _{i}}  ![{\displaystyle \mathbf {x} _{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/57d2ef3df60acdb53bdf90535264041fea7231cd) that lie nearest to it (explained below). These       x   i     {\displaystyle \mathbf {x} _{i}}  ![{\displaystyle \mathbf {x} _{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/57d2ef3df60acdb53bdf90535264041fea7231cd) are called *support vectors*.

 

### Soft-margin

 

To extend SVM to cases in which the data are not linearly separable, the *[hinge loss](./Hinge_loss)* function is helpful
    max  (  0 , 1 − −   y  i   (   w    T      x   i   − −  b )  )  .   {\displaystyle \max \left(0,1-y_{i}(\mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-b)\right).}  ![{\displaystyle \max \left(0,1-y_{i}(\mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-b)\right).}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a3ff19421060aed95bddead6de77743d48a67303)

 

Note that      y  i     {\displaystyle y_{i}}  ![{\displaystyle y_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/67d30d30b6c2dbe4d6f150d699de040937ecc95f) is the *i*-th target (i.e., in this case, 1 or −1), and       w    T      x   i   − −  b   {\displaystyle \mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-b}  ![{\displaystyle \mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-b}](https://wikimedia.org/api/rest_v1/media/math/render/svg/bb10a3e93a7905dc61c06ad6b9c7d41625ad1918) is the *i*-th output.

 

This function is zero if the constraint in **[(1)](./Support_vector_machine#math_1)** is satisfied, in other words, if       x   i     {\displaystyle \mathbf {x} _{i}}  ![{\displaystyle \mathbf {x} _{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/57d2ef3df60acdb53bdf90535264041fea7231cd) lies on the correct side of the margin. For data on the wrong side of the margin, the function's value is proportional to the distance from the margin.

 

The goal of the optimization then is to minimize:

 

    ‖ ‖   w   ‖ ‖   2   + C  [    1 n    ∑ ∑   i = 1   n   max  (  0 , 1 − −   y  i   (   w    T      x   i   − −  b )  )   ]  ,   {\displaystyle \lVert \mathbf {w} \rVert ^{2}+C\left[{\frac {1}{n}}\sum _{i=1}^{n}\max \left(0,1-y_{i}(\mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-b)\right)\right],}  ![{\displaystyle \lVert \mathbf {w} \rVert ^{2}+C\left[{\frac {1}{n}}\sum _{i=1}^{n}\max \left(0,1-y_{i}(\mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-b)\right)\right],}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b5dc624654eef8f3a8994da013e19dd98774e28f)

 

where the parameter     C > 0   {\displaystyle C>0}  ![{\displaystyle C>0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c84d4126c6df243734f9355927c026df6b0d3859) determines the trade-off between increasing the margin size and ensuring that the       x   i     {\displaystyle \mathbf {x} _{i}}  ![{\displaystyle \mathbf {x} _{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/57d2ef3df60acdb53bdf90535264041fea7231cd) lie on the correct side of the margin (Note we can add a weight to either term in the equation above). By deconstructing the hinge loss, this optimization problem can be formulated into the following:

 

           minimize   w  ,  b ,   ζ ζ          ‖ ‖   w   ‖ ‖   2   2   + C  ∑ ∑   i = 1   n    ζ ζ   i         subject to      y  i   (   w   ⊤ ⊤      x   i   − −  b ) ≥ ≥  1 − −   ζ ζ   i   ,   ζ ζ   i   ≥ ≥  0  ∀ ∀  i ∈ ∈  { 1 , … …  , n }       {\displaystyle {\begin{aligned}&{\underset {\mathbf {w} ,\;b,\;\mathbf {\zeta } }{\operatorname {minimize} }}&&\|\mathbf {w} \|_{2}^{2}+C\sum _{i=1}^{n}\zeta _{i}\\&{\text{subject to}}&&y_{i}(\mathbf {w} ^{\top }\mathbf {x} _{i}-b)\geq 1-\zeta _{i},\quad \zeta _{i}\geq 0\quad \forall i\in \{1,\dots ,n\}\end{aligned}}}  ![{\displaystyle {\begin{aligned}&{\underset {\mathbf {w} ,\;b,\;\mathbf {\zeta } }{\operatorname {minimize} }}&&\|\mathbf {w} \|_{2}^{2}+C\sum _{i=1}^{n}\zeta _{i}\\&{\text{subject to}}&&y_{i}(\mathbf {w} ^{\top }\mathbf {x} _{i}-b)\geq 1-\zeta _{i},\quad \zeta _{i}\geq 0\quad \forall i\in \{1,\dots ,n\}\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5dc1df921ad8a6eb065617d4445a697dabf323fc)

 

Thus, for large values of     C   {\displaystyle C}  ![{\displaystyle C}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4fc55753007cd3c18576f7933f6f089196732029), it will behave similar to the hard-margin SVM, if the input data are linearly classifiable, but will still learn if a classification rule is viable or not.

 

## Nonlinear kernels

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/f/fe/Kernel_Machine.svg/250px-Kernel_Machine.svg.png)](./File:Kernel_Machine.svg)Kernel machine 

The original maximum-margin hyperplane algorithm proposed by Vapnik in 1963 constructed a [linear classifier](./Linear_classifier). However, in 1992, [Bernhard Boser](./Bernhard_Boser?action=edit&redlink=1), [Isabelle Guyon](./Isabelle_Guyon) and [Vladimir Vapnik](./Vladimir_Vapnik) suggested a way to create nonlinear classifiers by applying the [kernel trick](./Kernel_trick) (originally proposed by Aizerman et al.[[22]](./Support_vector_machine#cite_note-22)) to maximum-margin hyperplanes.[[9]](./Support_vector_machine#cite_note-ReferenceA-9) The kernel trick, where [dot products](./Dot_product) are replaced by kernels, is easily derived in the dual representation of the SVM problem. This allows the algorithm to fit the maximum-margin hyperplane in a transformed [feature space](./Feature_space). The transformation may be nonlinear and the transformed space high-dimensional; although the classifier is a hyperplane in the transformed feature space, it may be nonlinear in the original input space.

 

It is noteworthy that working in a higher-dimensional feature space increases the [generalization error](./Generalization_error) of support vector machines, although given enough samples the algorithm still performs well.[[23]](./Support_vector_machine#cite_note-23)

 

Some common kernels include:

 
- [Polynomial (homogeneous)](./Homogeneous_polynomial):     k (   x   i   ,   x   j   ) = (   x   i   ⋅ ⋅    x   j    )  d     {\displaystyle k(\mathbf {x} _{i},\mathbf {x} _{j})=(\mathbf {x} _{i}\cdot \mathbf {x} _{j})^{d}}  ![{\displaystyle k(\mathbf {x} _{i},\mathbf {x} _{j})=(\mathbf {x} _{i}\cdot \mathbf {x} _{j})^{d}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6bf5a463f18d498ecd5a1dbad23c6a9cd5aefcac). Particularly, when     d = 1   {\displaystyle d=1}  ![{\displaystyle d=1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/958b426c5ace91d4fb7f5a3becd7b21dba288d50), this becomes the linear kernel.
- [Polynomial](./Polynomial_kernel) (inhomogeneous):     k (   x   i   ,   x   j   ) = (   x   i   ⋅ ⋅    x   j   + r  )  d     {\displaystyle k(\mathbf {x} _{i},\mathbf {x} _{j})=(\mathbf {x} _{i}\cdot \mathbf {x} _{j}+r)^{d}}  ![{\displaystyle k(\mathbf {x} _{i},\mathbf {x} _{j})=(\mathbf {x} _{i}\cdot \mathbf {x} _{j}+r)^{d}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1ae443fe0a081824fee0c2981f3315fc61c34f9d).
- Gaussian [radial basis function](./Radial_basis_function_kernel):     k (   x   i   ,   x   j   ) = exp ⁡ ⁡   (  − −  γ γ    ‖    x   i   − −    x   j    ‖   2    )    {\displaystyle k(\mathbf {x} _{i},\mathbf {x} _{j})=\exp \left(-\gamma \left\|\mathbf {x} _{i}-\mathbf {x} _{j}\right\|^{2}\right)}  ![{\displaystyle k(\mathbf {x} _{i},\mathbf {x} _{j})=\exp \left(-\gamma \left\|\mathbf {x} _{i}-\mathbf {x} _{j}\right\|^{2}\right)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5f77e4fc13db08ef81b79ca6e2c3d279ecdec38a) for     γ γ  > 0   {\displaystyle \gamma >0}  ![{\displaystyle \gamma >0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/775a6435e4270cddf2cd7dcb486c20f7f4bb8cee). Sometimes parametrized using     γ γ  = 1  /  ( 2  σ σ   2   )   {\displaystyle \gamma =1/(2\sigma ^{2})}  ![{\displaystyle \gamma =1/(2\sigma ^{2})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/895cbf591da9a695ffd1daec88a86ae0e50e8079).
- [Sigmoid function](./Sigmoid_function) ([Hyperbolic tangent](./Hyperbolic_tangent)):     k (   x  i    ,   x  j    ) = tanh ⁡ ⁡  ( κ κ    x   i   ⋅ ⋅    x   j   + c )   {\displaystyle k(\mathbf {x_{i}} ,\mathbf {x_{j}} )=\tanh(\kappa \mathbf {x} _{i}\cdot \mathbf {x} _{j}+c)}  ![{\displaystyle k(\mathbf {x_{i}} ,\mathbf {x_{j}} )=\tanh(\kappa \mathbf {x} _{i}\cdot \mathbf {x} _{j}+c)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/410bae228c88d942888ee20927f337918a4578f9) for some (not every)     κ κ  > 0   {\displaystyle \kappa >0}  ![{\displaystyle \kappa >0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f2d8b6e1180bd22cf9e92b0295ede259cb80db64) and     c < 0   {\displaystyle c<0}  ![{\displaystyle c<0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/26a48dc798956117afd8c429c39886678c0e7204).

 

The kernel is related to the transform     φ φ  (   x   i   )   {\displaystyle \varphi (\mathbf {x} _{i})}  ![{\displaystyle \varphi (\mathbf {x} _{i})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/76218776e3a23ed7df619f158290314bbe6b800f) by the equation     k (   x   i   ,   x   j   ) = φ φ  (   x   i   ) ⋅ ⋅  φ φ  (   x   j   )   {\displaystyle k(\mathbf {x} _{i},\mathbf {x} _{j})=\varphi (\mathbf {x} _{i})\cdot \varphi (\mathbf {x} _{j})}  ![{\displaystyle k(\mathbf {x} _{i},\mathbf {x} _{j})=\varphi (\mathbf {x} _{i})\cdot \varphi (\mathbf {x} _{j})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9bfee6115949f816688bf33929829d9dda810c9b). The value **w** is also in the transformed space, with      w  =  ∑ ∑   i    α α   i    y  i   φ φ  (   x   i   )   {\textstyle \mathbf {w} =\sum _{i}\alpha _{i}y_{i}\varphi (\mathbf {x} _{i})}  ![{\textstyle \mathbf {w} =\sum _{i}\alpha _{i}y_{i}\varphi (\mathbf {x} _{i})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c137c44077af44fafda3a182628ab924d5cedde7). Dot products with **w** for classification can again be computed by the kernel trick, i.e.      w  ⋅ ⋅  φ φ  (  x  ) =  ∑ ∑   i    α α   i    y  i   k (   x   i   ,  x  )   {\textstyle \mathbf {w} \cdot \varphi (\mathbf {x} )=\sum _{i}\alpha _{i}y_{i}k(\mathbf {x} _{i},\mathbf {x} )}  ![{\textstyle \mathbf {w} \cdot \varphi (\mathbf {x} )=\sum _{i}\alpha _{i}y_{i}k(\mathbf {x} _{i},\mathbf {x} )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/525bec723a8dc180e229457c2a92d13bf1f9e137).

 


