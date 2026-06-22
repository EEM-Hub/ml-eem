---
source: sources/wiki-Gradient_descent.md
source_url: https://en.wikipedia.org/wiki/Gradient_descent
chunk: 3/6
---

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

 


