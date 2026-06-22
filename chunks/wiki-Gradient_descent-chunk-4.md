---
source: sources/wiki-Gradient_descent.md
source_url: https://en.wikipedia.org/wiki/Gradient_descent
chunk: 4/6
---

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

 


