---
source: sources/wiki-Support_vector_machine.md
source_url: https://en.wikipedia.org/wiki/Support_vector_machine
chunk: 3/7
---

## Computing the SVM classifier

 

Computing the (soft-margin) SVM classifier amounts to minimizing an expression of the form

 
| [1n∑i=1nmax(0,1−yi(wTxi−b))]+λ‖w‖2.{\displaystyle \left[{\frac {1}{n}}\sum _{i=1}^{n}\max \left(0,1-y_{i}(\mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-b)\right)\right]+\lambda \|\mathbf {w} \|^{2}.} |  | 2 |
| --- | --- | --- |

 

We focus on the soft-margin classifier since, as noted above, choosing a sufficiently small value for     λ λ    {\displaystyle \lambda }  ![{\displaystyle \lambda }](https://wikimedia.org/api/rest_v1/media/math/render/svg/b43d0ea3c9c025af1be9128e62a18fa74bedda2a) yields the hard-margin classifier for linearly classifiable input data. The classical approach, which involves reducing **[(2)](./Support_vector_machine#math_2)** to a [quadratic programming](./Quadratic_programming) problem, is detailed below. Then, more recent approaches such as sub-gradient descent and coordinate descent will be discussed.

 

### Primal

 

Minimizing **[(2)](./Support_vector_machine#math_2)** can be rewritten as a constrained optimization problem with a differentiable objective function in the following way.

 

For each     i ∈ ∈  { 1 ,  … …  ,  n }   {\displaystyle i\in \{1,\,\ldots ,\,n\}}  ![{\displaystyle i\in \{1,\,\ldots ,\,n\}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2b16335bac1f89284abe32d0deb82682b38ecd94) we introduce a variable      ζ ζ   i   = max  (  0 , 1 − −   y  i   (   w    T      x   i   − −  b )  )    {\displaystyle \zeta _{i}=\max \left(0,1-y_{i}(\mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-b)\right)}  ![{\displaystyle \zeta _{i}=\max \left(0,1-y_{i}(\mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-b)\right)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/47ce7c7aac83c15e7ea058a27d477939d7da0b35). Note that      ζ ζ   i     {\displaystyle \zeta _{i}}  ![{\displaystyle \zeta _{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/aab3f49d01957ab74f9581cd34ba72cc7efc4bdc) is the smallest nonnegative number satisfying      y  i   (   w    T      x   i   − −  b ) ≥ ≥  1 − −   ζ ζ   i   .   {\displaystyle y_{i}(\mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-b)\geq 1-\zeta _{i}.}  ![{\displaystyle y_{i}(\mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-b)\geq 1-\zeta _{i}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8c615ea126daa1a792ed2301275f12d45b5bfb92)

 

Thus we can rewrite the optimization problem as follows

 

          minimize     1 n    ∑ ∑   i = 1   n    ζ ζ   i   + λ λ  ‖ ‖   w   ‖ ‖   2         subject to    y  i    (    w    T      x   i   − −  b  )  ≥ ≥  1 − −   ζ ζ   i      and     ζ ζ   i   ≥ ≥  0 ,   for all   i .       {\displaystyle {\begin{aligned}&{\text{minimize }}{\frac {1}{n}}\sum _{i=1}^{n}\zeta _{i}+\lambda \|\mathbf {w} \|^{2}\\[0.5ex]&{\text{subject to }}y_{i}\left(\mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-b\right)\geq 1-\zeta _{i}\,{\text{ and }}\,\zeta _{i}\geq 0,\,{\text{for all }}i.\end{aligned}}}  ![{\displaystyle {\begin{aligned}&{\text{minimize }}{\frac {1}{n}}\sum _{i=1}^{n}\zeta _{i}+\lambda \|\mathbf {w} \|^{2}\\[0.5ex]&{\text{subject to }}y_{i}\left(\mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-b\right)\geq 1-\zeta _{i}\,{\text{ and }}\,\zeta _{i}\geq 0,\,{\text{for all }}i.\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/55f31fe5bcd9363b51ab5a4c4387202f32f047ee)

 

This is called the *primal* problem.

 

### Dual

 

By solving for the [Lagrangian dual](./Duality_(optimization)) of the above problem, one obtains the simplified problem

 

          maximize    f (  c  1   … …   c  n   ) =  ∑ ∑   i = 1   n    c  i   − −    1 2    ∑ ∑   i = 1   n    ∑ ∑   j = 1   n    y  i    c  i   (   x   i    T      x   j   )  y  j    c  j   ,       subject to    ∑ ∑   i = 1   n    c  i    y  i   = 0 ,   and   0 ≤ ≤   c  i   ≤ ≤    1  2 n λ λ       for all   i .       {\displaystyle {\begin{aligned}&{\text{maximize}}\,\,f(c_{1}\ldots c_{n})=\sum _{i=1}^{n}c_{i}-{\frac {1}{2}}\sum _{i=1}^{n}\sum _{j=1}^{n}y_{i}c_{i}(\mathbf {x} _{i}^{\mathsf {T}}\mathbf {x} _{j})y_{j}c_{j},\\&{\text{subject to }}\sum _{i=1}^{n}c_{i}y_{i}=0,\,{\text{and }}0\leq c_{i}\leq {\frac {1}{2n\lambda }}\;{\text{for all }}i.\end{aligned}}}  ![{\displaystyle {\begin{aligned}&{\text{maximize}}\,\,f(c_{1}\ldots c_{n})=\sum _{i=1}^{n}c_{i}-{\frac {1}{2}}\sum _{i=1}^{n}\sum _{j=1}^{n}y_{i}c_{i}(\mathbf {x} _{i}^{\mathsf {T}}\mathbf {x} _{j})y_{j}c_{j},\\&{\text{subject to }}\sum _{i=1}^{n}c_{i}y_{i}=0,\,{\text{and }}0\leq c_{i}\leq {\frac {1}{2n\lambda }}\;{\text{for all }}i.\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/90ec65706ca90aa8b5aad2d9bb4c767f5487cb56)

 

This is called the *dual* problem. Since the dual maximization problem is a quadratic function of the      c  i     {\displaystyle c_{i}}  ![{\displaystyle c_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/01acb7953ba52c2aa44264b5d0f8fd223aa178a2) subject to linear constraints, it is efficiently solvable by [quadratic programming](./Quadratic_programming) algorithms.

 

Here, the variables      c  i     {\displaystyle c_{i}}  ![{\displaystyle c_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/01acb7953ba52c2aa44264b5d0f8fd223aa178a2) are defined such that

 

     w  =  ∑ ∑   i = 1   n    c  i    y  i     x   i   .   {\displaystyle \mathbf {w} =\sum _{i=1}^{n}c_{i}y_{i}\mathbf {x} _{i}.}  ![{\displaystyle \mathbf {w} =\sum _{i=1}^{n}c_{i}y_{i}\mathbf {x} _{i}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c4a707abda1076fbe1c29bb689034cd3cf0bdf9c)

 

Moreover,      c  i   = 0   {\displaystyle c_{i}=0}  ![{\displaystyle c_{i}=0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/06dbc33495a748ad5067cb6ff07cba653cffaf2c) exactly when       x   i     {\displaystyle \mathbf {x} _{i}}  ![{\displaystyle \mathbf {x} _{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/57d2ef3df60acdb53bdf90535264041fea7231cd) lies on the correct side of the margin, and     0 <  c  i   < ( 2 n λ λ   )  − −  1     {\displaystyle 0<c_{i}<(2n\lambda )^{-1}}  ![{\displaystyle 0<c_{i}<(2n\lambda )^{-1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ac59f447ace7b665f4bff3f047611b25eed26226)  when       x   i     {\displaystyle \mathbf {x} _{i}}  ![{\displaystyle \mathbf {x} _{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/57d2ef3df60acdb53bdf90535264041fea7231cd) lies on the margin's boundary. It follows that      w    {\displaystyle \mathbf {w} }  ![{\displaystyle \mathbf {w} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/20795664b5b048744a2fd88977851104cc5816f8) can be written as a linear combination of the support vectors.

 

The offset,     b   {\displaystyle b}  ![{\displaystyle b}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f11423fbb2e967f986e36804a8ae4271734917c3), can be recovered by finding an       x   i     {\displaystyle \mathbf {x} _{i}}  ![{\displaystyle \mathbf {x} _{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/57d2ef3df60acdb53bdf90535264041fea7231cd) on the margin's boundary and solving
     y  i   (   w    T      x   i   − −  b ) = 1  ⟺ ⟺   b =   w    T      x   i   − −   y  i   .   {\displaystyle y_{i}(\mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-b)=1\iff b=\mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-y_{i}.}  ![{\displaystyle y_{i}(\mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-b)=1\iff b=\mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-y_{i}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b47ab52ef7a24e6fbf07ff7cc3b549677e4d8413)

 

(Note that      y  i   − −  1   =  y  i     {\displaystyle y_{i}^{-1}=y_{i}}  ![{\displaystyle y_{i}^{-1}=y_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fdb3f52ac1c7e8a452147480c68ab77669cf6f95) since      y  i   = ± ±  1   {\displaystyle y_{i}=\pm 1}  ![{\displaystyle y_{i}=\pm 1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5603fac8c4038df3f4299323c0cbc0a311040424).)

 

### Kernel trick

 Main article: [Kernel method](./Kernel_method) [![](//upload.wikimedia.org/wikipedia/commons/thumb/c/cc/Kernel_trick_idea.svg/250px-Kernel_trick_idea.svg.png)](./File:Kernel_trick_idea.svg)A training example of SVM with kernel given by φ((*a*, *b*)) = (*a*, *b*, *a*2 + *b*2) 

Suppose now that we would like to learn a nonlinear classification rule which corresponds to a linear classification rule for the transformed data points     φ φ  (   x   i   ) .   {\displaystyle \varphi (\mathbf {x} _{i}).}  ![{\displaystyle \varphi (\mathbf {x} _{i}).}](https://wikimedia.org/api/rest_v1/media/math/render/svg/842b8ca2760c01ba5ed6552bb9e9d8174d7a45a3) Moreover, we are given a kernel function     k   {\displaystyle k}  ![{\displaystyle k}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c3c9a2c7b599b37105512c5d570edc034056dd40) which satisfies     k (   x   i   ,   x   j   ) = φ φ  (   x   i   ) ⋅ ⋅  φ φ  (   x   j   )   {\displaystyle k(\mathbf {x} _{i},\mathbf {x} _{j})=\varphi (\mathbf {x} _{i})\cdot \varphi (\mathbf {x} _{j})}  ![{\displaystyle k(\mathbf {x} _{i},\mathbf {x} _{j})=\varphi (\mathbf {x} _{i})\cdot \varphi (\mathbf {x} _{j})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9bfee6115949f816688bf33929829d9dda810c9b).

 

We know the classification vector      w    {\displaystyle \mathbf {w} }  ![{\displaystyle \mathbf {w} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/20795664b5b048744a2fd88977851104cc5816f8) in the transformed space satisfies

 

     w  =  ∑ ∑   i = 1   n    c  i    y  i   φ φ  (   x   i   ) ,   {\displaystyle \mathbf {w} =\sum _{i=1}^{n}c_{i}y_{i}\varphi (\mathbf {x} _{i}),}  ![{\displaystyle \mathbf {w} =\sum _{i=1}^{n}c_{i}y_{i}\varphi (\mathbf {x} _{i}),}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e117c6d8f5519f2fa57159033ff856f7a1b58221)

 

where, the      c  i     {\displaystyle c_{i}}  ![{\displaystyle c_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/01acb7953ba52c2aa44264b5d0f8fd223aa178a2) are obtained by solving the optimization problem

 

         maximize    f (  c  1   … …   c  n   )    =  ∑ ∑   i = 1   n    c  i   − −    1 2    ∑ ∑   i = 1   n    ∑ ∑   j = 1   n    y  i    c  i   ( φ φ  (   x   i   ) ⋅ ⋅  φ φ  (   x   j   ) )  y  j    c  j         =  ∑ ∑   i = 1   n    c  i   − −    1 2    ∑ ∑   i = 1   n    ∑ ∑   j = 1   n    y  i    c  i   k (   x   i   ,   x   j   )  y  j    c  j        subject to    ∑ ∑   i = 1   n    c  i    y  i      = 0 ,   and   0 ≤ ≤   c  i   ≤ ≤    1  2 n λ λ       for all   i .       {\displaystyle {\begin{aligned}{\text{maximize}}\,\,f(c_{1}\ldots c_{n})&=\sum _{i=1}^{n}c_{i}-{\frac {1}{2}}\sum _{i=1}^{n}\sum _{j=1}^{n}y_{i}c_{i}(\varphi (\mathbf {x} _{i})\cdot \varphi (\mathbf {x} _{j}))y_{j}c_{j}\\&=\sum _{i=1}^{n}c_{i}-{\frac {1}{2}}\sum _{i=1}^{n}\sum _{j=1}^{n}y_{i}c_{i}k(\mathbf {x} _{i},\mathbf {x} _{j})y_{j}c_{j}\\{\text{subject to }}\sum _{i=1}^{n}c_{i}y_{i}&=0,\,{\text{and }}0\leq c_{i}\leq {\frac {1}{2n\lambda }}\;{\text{for all }}i.\end{aligned}}}  ![{\displaystyle {\begin{aligned}{\text{maximize}}\,\,f(c_{1}\ldots c_{n})&=\sum _{i=1}^{n}c_{i}-{\frac {1}{2}}\sum _{i=1}^{n}\sum _{j=1}^{n}y_{i}c_{i}(\varphi (\mathbf {x} _{i})\cdot \varphi (\mathbf {x} _{j}))y_{j}c_{j}\\&=\sum _{i=1}^{n}c_{i}-{\frac {1}{2}}\sum _{i=1}^{n}\sum _{j=1}^{n}y_{i}c_{i}k(\mathbf {x} _{i},\mathbf {x} _{j})y_{j}c_{j}\\{\text{subject to }}\sum _{i=1}^{n}c_{i}y_{i}&=0,\,{\text{and }}0\leq c_{i}\leq {\frac {1}{2n\lambda }}\;{\text{for all }}i.\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/cbaeb993c2f9bcf9d046ce72bc9bd72e1a7ac05e)

 

The coefficients      c  i     {\displaystyle c_{i}}  ![{\displaystyle c_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/01acb7953ba52c2aa44264b5d0f8fd223aa178a2) can be solved for using quadratic programming, as before. Again, we can find some index     i   {\displaystyle i}  ![{\displaystyle i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/add78d8608ad86e54951b8c8bd6c8d8416533d20) such that     0 <  c  i   < ( 2 n λ λ   )  − −  1     {\displaystyle 0<c_{i}<(2n\lambda )^{-1}}  ![{\displaystyle 0<c_{i}<(2n\lambda )^{-1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ac59f447ace7b665f4bff3f047611b25eed26226), so that     φ φ  (   x   i   )   {\displaystyle \varphi (\mathbf {x} _{i})}  ![{\displaystyle \varphi (\mathbf {x} _{i})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/76218776e3a23ed7df619f158290314bbe6b800f) lies on the boundary of the margin in the transformed space, and then solve

 

        b =   w    T    φ φ  (   x   i   ) − −   y  i      =  [   ∑ ∑   j = 1   n    c  j    y  j   φ φ  (   x   j   ) ⋅ ⋅  φ φ  (   x   i   )  ]  − −   y  i         =  [   ∑ ∑   j = 1   n    c  j    y  j   k (   x   j   ,   x   i   )  ]  − −   y  i   .       {\displaystyle {\begin{aligned}b=\mathbf {w} ^{\mathsf {T}}\varphi (\mathbf {x} _{i})-y_{i}&=\left[\sum _{j=1}^{n}c_{j}y_{j}\varphi (\mathbf {x} _{j})\cdot \varphi (\mathbf {x} _{i})\right]-y_{i}\\&=\left[\sum _{j=1}^{n}c_{j}y_{j}k(\mathbf {x} _{j},\mathbf {x} _{i})\right]-y_{i}.\end{aligned}}}  ![{\displaystyle {\begin{aligned}b=\mathbf {w} ^{\mathsf {T}}\varphi (\mathbf {x} _{i})-y_{i}&=\left[\sum _{j=1}^{n}c_{j}y_{j}\varphi (\mathbf {x} _{j})\cdot \varphi (\mathbf {x} _{i})\right]-y_{i}\\&=\left[\sum _{j=1}^{n}c_{j}y_{j}k(\mathbf {x} _{j},\mathbf {x} _{i})\right]-y_{i}.\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/84f72e9d29c896b17db3c3640ed94a2395ef5ce8)

 

Finally,

 

     z  ↦ ↦  sgn ⁡ ⁡  (   w    T    φ φ  (  z  ) − −  b ) = sgn ⁡ ⁡   (   [   ∑ ∑   i = 1   n    c  i    y  i   k (   x   i   ,  z  )  ]  − −  b  )  .   {\displaystyle \mathbf {z} \mapsto \operatorname {sgn}(\mathbf {w} ^{\mathsf {T}}\varphi (\mathbf {z} )-b)=\operatorname {sgn} \left(\left[\sum _{i=1}^{n}c_{i}y_{i}k(\mathbf {x} _{i},\mathbf {z} )\right]-b\right).}  ![{\displaystyle \mathbf {z} \mapsto \operatorname {sgn} (\mathbf {w} ^{\mathsf {T}}\varphi (\mathbf {z} )-b)=\operatorname {sgn} \left(\left[\sum _{i=1}^{n}c_{i}y_{i}k(\mathbf {x} _{i},\mathbf {z} )\right]-b\right).}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5ad3c52254fc4372047bc849648b0b8554e47ab4)

 

### Modern methods

 

Recent algorithms for finding the SVM classifier include sub-gradient descent and coordinate descent. Both techniques have proven to offer significant advantages over the traditional approach when dealing with large, sparse datasets—sub-gradient methods are especially efficient when there are many training examples, and coordinate descent when the dimension of the feature space is high.

 

#### Sub-gradient descent

 

[Sub-gradient descent](./Subgradient_method) algorithms for the SVM work directly with the expression

 

    f (  w  , b ) =  [    1 n    ∑ ∑   i = 1   n   max  (  0 , 1 − −   y  i   (   w    T      x   i   − −  b )  )   ]  + λ λ  ‖ ‖   w   ‖ ‖   2   .   {\displaystyle f(\mathbf {w} ,b)=\left[{\frac {1}{n}}\sum _{i=1}^{n}\max \left(0,1-y_{i}(\mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-b)\right)\right]+\lambda \|\mathbf {w} \|^{2}.}  ![{\displaystyle f(\mathbf {w} ,b)=\left[{\frac {1}{n}}\sum _{i=1}^{n}\max \left(0,1-y_{i}(\mathbf {w} ^{\mathsf {T}}\mathbf {x} _{i}-b)\right)\right]+\lambda \|\mathbf {w} \|^{2}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/458eaac43a20c151eb9c977c96b6df2d6066bae9)

 

Note that     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) is a [convex function](./Convex_function) of      w    {\displaystyle \mathbf {w} }  ![{\displaystyle \mathbf {w} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/20795664b5b048744a2fd88977851104cc5816f8) and     b   {\displaystyle b}  ![{\displaystyle b}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f11423fbb2e967f986e36804a8ae4271734917c3). As such, traditional [gradient descent](./Gradient_descent) (or [SGD](./Stochastic_gradient_descent)) methods can be adapted, where instead of taking a step in the direction of the function's gradient, a step is taken in the direction of a vector selected from the function's [sub-gradient](./Subderivative). This approach has the advantage that, for certain implementations, the number of iterations does not scale with     n   {\displaystyle n}  ![{\displaystyle n}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a601995d55609f2d9f5e233e36fbe9ea26011b3b), the number of data points.[[24]](./Support_vector_machine#cite_note-24)

 

#### Coordinate descent

 

[Coordinate descent](./Coordinate_descent) algorithms for the SVM work from the dual problem

 

          maximize    f (  c  1   … …   c  n   ) =  ∑ ∑   i = 1   n    c  i   − −    1 2    ∑ ∑   i = 1   n    ∑ ∑   j = 1   n    y  i    c  i   (  x  i   ⋅ ⋅   x  j   )  y  j    c  j   ,       subject to    ∑ ∑   i = 1   n    c  i    y  i   = 0 ,   and   0 ≤ ≤   c  i   ≤ ≤    1  2 n λ λ       for all   i .       {\displaystyle {\begin{aligned}&{\text{maximize}}\,\,f(c_{1}\ldots c_{n})=\sum _{i=1}^{n}c_{i}-{\frac {1}{2}}\sum _{i=1}^{n}\sum _{j=1}^{n}y_{i}c_{i}(x_{i}\cdot x_{j})y_{j}c_{j},\\&{\text{subject to }}\sum _{i=1}^{n}c_{i}y_{i}=0,\,{\text{and }}0\leq c_{i}\leq {\frac {1}{2n\lambda }}\;{\text{for all }}i.\end{aligned}}}  ![{\displaystyle {\begin{aligned}&{\text{maximize}}\,\,f(c_{1}\ldots c_{n})=\sum _{i=1}^{n}c_{i}-{\frac {1}{2}}\sum _{i=1}^{n}\sum _{j=1}^{n}y_{i}c_{i}(x_{i}\cdot x_{j})y_{j}c_{j},\\&{\text{subject to }}\sum _{i=1}^{n}c_{i}y_{i}=0,\,{\text{and }}0\leq c_{i}\leq {\frac {1}{2n\lambda }}\;{\text{for all }}i.\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ac2cee0a2ea9c264de1c4a81224489b666a2cb50)

 

For each     i ∈ ∈  { 1 ,  … …  ,  n }   {\displaystyle i\in \{1,\,\ldots ,\,n\}}  ![{\displaystyle i\in \{1,\,\ldots ,\,n\}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2b16335bac1f89284abe32d0deb82682b38ecd94), iteratively, the coefficient      c  i     {\displaystyle c_{i}}  ![{\displaystyle c_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/01acb7953ba52c2aa44264b5d0f8fd223aa178a2) is adjusted in the direction of     ∂ ∂  f  /  ∂ ∂   c  i     {\displaystyle \partial f/\partial c_{i}}  ![{\displaystyle \partial f/\partial c_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/36ed38d3ef346e0e67f1c4e306c6dfad3ff4a03f). Then, the resulting vector of coefficients     (  c  1  ′  ,  … …  ,   c  n  ′  )   {\displaystyle (c_{1}',\,\ldots ,\,c_{n}')}  ![{\displaystyle (c_{1}',\,\ldots ,\,c_{n}')}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6d62cfdb4596f4eb5ef503e371cda2673a21a417) is projected onto the nearest vector of coefficients that satisfies the given constraints. (Typically Euclidean distances are used.) The process is then repeated until a near-optimal vector of coefficients is obtained. The resulting algorithm is extremely fast in practice, although few performance guarantees have been proven.[[25]](./Support_vector_machine#cite_note-25)

 


