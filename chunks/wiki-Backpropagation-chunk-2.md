---
source: sources/wiki-Backpropagation.md
source_url: https://en.wikipedia.org/wiki/Backpropagation
chunk: 2/8
---

## Matrix multiplication

 

For the basic case of a feedforward network, where nodes in each layer are connected only to nodes in the immediate next layer (without skipping any layers), and there is a loss function that computes a scalar loss for the final output, backpropagation can be understood simply by matrix multiplication.[[c]](./Backpropagation#cite_note-7) Essentially, backpropagation evaluates the expression for the derivative of the cost function as a product of derivatives between each layer *from right to left* – "backwards" – with the gradient of the weights between each layer being a simple modification of the partial products (the "backwards propagated error").

 

Given an input–output pair     ( x , y )   {\displaystyle (x,y)}  ![{\displaystyle (x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/41cf50e4a314ca8e2c30964baa8d26e5be7a9386), the loss is:

     C ( y ,  f  L   (  W  L    f  L − −  1   (  W  L − −  1   ⋯ ⋯   f  2   (  W  2    f  1   (  W  1   x ) ) ⋯ ⋯  ) ) )   {\displaystyle C(y,f^{L}(W^{L}f^{L-1}(W^{L-1}\cdots f^{2}(W^{2}f^{1}(W^{1}x))\cdots )))}  ![{\displaystyle C(y,f^{L}(W^{L}f^{L-1}(W^{L-1}\cdots f^{2}(W^{2}f^{1}(W^{1}x))\cdots )))}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3ca8768a6ab49c9e52086741f958221b56b6d03e) 

To compute this, one starts with the input     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4) and works forward; denote the weighted input of each hidden layer as      z  l     {\displaystyle z^{l}}  ![{\displaystyle z^{l}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3ea4d56d1c5e8fe66b402ea0d1b92368902531dd) and the output of hidden layer     l   {\displaystyle l}  ![{\displaystyle l}](https://wikimedia.org/api/rest_v1/media/math/render/svg/829091f745070b9eb97a80244129025440a1cfac) as the activation      a  l     {\displaystyle a^{l}}  ![{\displaystyle a^{l}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/975d9aa9ed78016e94e7438c5af2a6ec8b97a0e9). For backpropagation, the activation      a  l     {\displaystyle a^{l}}  ![{\displaystyle a^{l}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/975d9aa9ed78016e94e7438c5af2a6ec8b97a0e9) as well as the derivatives     (  f  l    ) ′    {\displaystyle (f^{l})'}  ![{\displaystyle (f^{l})'}](https://wikimedia.org/api/rest_v1/media/math/render/svg/75a2f054b20672fb790ed501c4a39873233d4745) (evaluated at      z  l     {\displaystyle z^{l}}  ![{\displaystyle z^{l}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3ea4d56d1c5e8fe66b402ea0d1b92368902531dd)) must be cached for use during the backwards pass.

 

The derivative of the loss in terms of the inputs is given by the chain rule; note that each term is a [total derivative](./Total_derivative), evaluated at the value of the network (at each node) on the input     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4):

        d C   d  a  L      ⋅ ⋅     d  a  L     d  z  L      ⋅ ⋅     d  z  L     d  a  L − −  1      ⋅ ⋅     d  a  L − −  1     d  z  L − −  1      ⋅ ⋅     d  z  L − −  1     d  a  L − −  2      ⋅ ⋅  … …  ⋅ ⋅     d  a  1     d  z  1      ⋅ ⋅     ∂ ∂   z  1     ∂ ∂  x    ,   {\displaystyle {\frac {dC}{da^{L}}}\cdot {\frac {da^{L}}{dz^{L}}}\cdot {\frac {dz^{L}}{da^{L-1}}}\cdot {\frac {da^{L-1}}{dz^{L-1}}}\cdot {\frac {dz^{L-1}}{da^{L-2}}}\cdot \ldots \cdot {\frac {da^{1}}{dz^{1}}}\cdot {\frac {\partial z^{1}}{\partial x}},}  ![{\displaystyle {\frac {dC}{da^{L}}}\cdot {\frac {da^{L}}{dz^{L}}}\cdot {\frac {dz^{L}}{da^{L-1}}}\cdot {\frac {da^{L-1}}{dz^{L-1}}}\cdot {\frac {dz^{L-1}}{da^{L-2}}}\cdot \ldots \cdot {\frac {da^{1}}{dz^{1}}}\cdot {\frac {\partial z^{1}}{\partial x}},}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b758730620b9e4d0b2018f99c3cc270fa8e3bd31) 

where        d  a  L     d  z  L        {\displaystyle {\frac {da^{L}}{dz^{L}}}}  ![{\displaystyle {\frac {da^{L}}{dz^{L}}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e72728161114c81bdf209852a4157264296326fb) is a [diagonal matrix](./Diagonal_matrix).

 

These terms are: the derivative of the loss function;[[d]](./Backpropagation#cite_note-8) the derivatives of the activation functions;[[e]](./Backpropagation#cite_note-9) and the matrices of weights:[[f]](./Backpropagation#cite_note-10)

        d C   d  a  L      ∘ ∘  (  f  L    ) ′  ⋅ ⋅   W  L   ∘ ∘  (  f  L − −  1    ) ′  ⋅ ⋅   W  L − −  1   ∘ ∘  ⋯ ⋯  ∘ ∘  (  f  1    ) ′  ⋅ ⋅   W  1   .   {\displaystyle {\frac {dC}{da^{L}}}\circ (f^{L})'\cdot W^{L}\circ (f^{L-1})'\cdot W^{L-1}\circ \cdots \circ (f^{1})'\cdot W^{1}.}  ![{\displaystyle {\frac {dC}{da^{L}}}\circ (f^{L})'\cdot W^{L}\circ (f^{L-1})'\cdot W^{L-1}\circ \cdots \circ (f^{1})'\cdot W^{1}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f46ed48b7054ef8629f889782c3ffbf953818ca) 

The gradient     ∇ ∇    {\displaystyle \nabla }  ![{\displaystyle \nabla }](https://wikimedia.org/api/rest_v1/media/math/render/svg/a3d0e93b78c50237f9ea83d027e4ebbdaef354b2) is the [transpose](./Transpose) of the derivative of the output in terms of the input, so the matrices are transposed and the order of multiplication is reversed, but the entries are the same:

      ∇ ∇   x   C = (  W  1    )  T   ⋅ ⋅  (  f  1    ) ′  ∘ ∘  … …  ∘ ∘  (  W  L − −  1    )  T   ⋅ ⋅  (  f  L − −  1    ) ′  ∘ ∘  (  W  L    )  T   ⋅ ⋅  (  f  L    ) ′  ∘ ∘   ∇ ∇    a  L     C .   {\displaystyle \nabla _{x}C=(W^{1})^{T}\cdot (f^{1})'\circ \ldots \circ (W^{L-1})^{T}\cdot (f^{L-1})'\circ (W^{L})^{T}\cdot (f^{L})'\circ \nabla _{a^{L}}C.}  ![{\displaystyle \nabla _{x}C=(W^{1})^{T}\cdot (f^{1})'\circ \ldots \circ (W^{L-1})^{T}\cdot (f^{L-1})'\circ (W^{L})^{T}\cdot (f^{L})'\circ \nabla _{a^{L}}C.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6ef269aa176ce5488ce5f6038eebcb9c8fe3c728) 

Backpropagation then consists essentially of evaluating this expression from right to left (equivalently, multiplying the previous expression for the derivative from left to right), computing the gradient at each layer on the way; there is an added step, because the gradient of the weights is not just a subexpression: there's an extra multiplication.

 

Introducing the auxiliary quantity      δ δ   l     {\displaystyle \delta ^{l}}  ![{\displaystyle \delta ^{l}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/249b787ef6af0149f7d71b951651c43633e0d56d) for the partial products (multiplying from right to left), interpreted as the "error at level     l   {\displaystyle l}  ![{\displaystyle l}](https://wikimedia.org/api/rest_v1/media/math/render/svg/829091f745070b9eb97a80244129025440a1cfac)" and defined as the gradient of the input values at level     l   {\displaystyle l}  ![{\displaystyle l}](https://wikimedia.org/api/rest_v1/media/math/render/svg/829091f745070b9eb97a80244129025440a1cfac):

      δ δ   l   := (  f  l    ) ′  ∘ ∘  (  W  l + 1    )  T   ⋅ ⋅  (  f  l + 1    ) ′  ∘ ∘  ⋯ ⋯  ∘ ∘  (  W  L − −  1    )  T   ⋅ ⋅  (  f  L − −  1    ) ′  ∘ ∘  (  W  L    )  T   ⋅ ⋅  (  f  L    ) ′  ∘ ∘   ∇ ∇    a  L     C .   {\displaystyle \delta ^{l}:=(f^{l})'\circ (W^{l+1})^{T}\cdot (f^{l+1})'\circ \cdots \circ (W^{L-1})^{T}\cdot (f^{L-1})'\circ (W^{L})^{T}\cdot (f^{L})'\circ \nabla _{a^{L}}C.}  ![{\displaystyle \delta ^{l}:=(f^{l})'\circ (W^{l+1})^{T}\cdot (f^{l+1})'\circ \cdots \circ (W^{L-1})^{T}\cdot (f^{L-1})'\circ (W^{L})^{T}\cdot (f^{L})'\circ \nabla _{a^{L}}C.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/85f95e97ceff3617728642e31c4090869970cad9) 

Note that      δ δ   l     {\displaystyle \delta ^{l}}  ![{\displaystyle \delta ^{l}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/249b787ef6af0149f7d71b951651c43633e0d56d) is a vector, of length equal to the number of nodes in level     l   {\displaystyle l}  ![{\displaystyle l}](https://wikimedia.org/api/rest_v1/media/math/render/svg/829091f745070b9eb97a80244129025440a1cfac); each component is interpreted as the "cost attributable to (the value of) that node".

 

The gradient of the weights in layer     l   {\displaystyle l}  ![{\displaystyle l}](https://wikimedia.org/api/rest_v1/media/math/render/svg/829091f745070b9eb97a80244129025440a1cfac) is then:

      ∇ ∇    W  l     C =  δ δ   l   (  a  l − −  1    )  T   .   {\displaystyle \nabla _{W^{l}}C=\delta ^{l}(a^{l-1})^{T}.}  ![{\displaystyle \nabla _{W^{l}}C=\delta ^{l}(a^{l-1})^{T}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ef23e829ba87604d15ab01965708906c2baa1e4d) 

The factor of      a  l − −  1     {\displaystyle a^{l-1}}  ![{\displaystyle a^{l-1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5a66d0e6ecb4f486f7e1b63c6ae0a91448624163) is because the weights      W  l     {\displaystyle W^{l}}  ![{\displaystyle W^{l}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/60b87bc8138a82f110491bb1abd0ea6eefe84c22) between level     l − −  1   {\displaystyle l-1}  ![{\displaystyle l-1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4e0d448948a353d0b2469b88ca918f34e32c8752) and     l   {\displaystyle l}  ![{\displaystyle l}](https://wikimedia.org/api/rest_v1/media/math/render/svg/829091f745070b9eb97a80244129025440a1cfac) affect level     l   {\displaystyle l}  ![{\displaystyle l}](https://wikimedia.org/api/rest_v1/media/math/render/svg/829091f745070b9eb97a80244129025440a1cfac) proportionally to the inputs (activations): the inputs are fixed, the weights vary.

 

The      δ δ   l     {\displaystyle \delta ^{l}}  ![{\displaystyle \delta ^{l}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/249b787ef6af0149f7d71b951651c43633e0d56d) can easily be computed recursively, going from right to left, as:

      δ δ   l − −  1   := (  f  l − −  1    ) ′  ∘ ∘  (  W  l    )  T   ⋅ ⋅   δ δ   l   .   {\displaystyle \delta ^{l-1}:=(f^{l-1})'\circ (W^{l})^{T}\cdot \delta ^{l}.}  ![{\displaystyle \delta ^{l-1}:=(f^{l-1})'\circ (W^{l})^{T}\cdot \delta ^{l}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/16ccb3d3b717f3fa8e1aa72c3a46bbc70945e4cf) 

The gradients of the weights can thus be computed using a few matrix multiplications for each level; this is backpropagation.

 

Compared with naively computing forwards (using the      δ δ   l     {\displaystyle \delta ^{l}}  ![{\displaystyle \delta ^{l}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/249b787ef6af0149f7d71b951651c43633e0d56d) for illustration):

          δ δ   1      = (  f  1    ) ′  ∘ ∘  (  W  2    )  T   ⋅ ⋅  (  f  2    ) ′  ∘ ∘  ⋯ ⋯  ∘ ∘  (  W  L − −  1    )  T   ⋅ ⋅  (  f  L − −  1    ) ′  ∘ ∘  (  W  L    )  T   ⋅ ⋅  (  f  L    ) ′  ∘ ∘   ∇ ∇    a  L     C      δ δ   2      = (  f  2    ) ′  ∘ ∘  ⋯ ⋯  ∘ ∘  (  W  L − −  1    )  T   ⋅ ⋅  (  f  L − −  1    ) ′  ∘ ∘  (  W  L    )  T   ⋅ ⋅  (  f  L    ) ′  ∘ ∘   ∇ ∇    a  L     C       ⋮ ⋮       δ δ   L − −  1      = (  f  L − −  1    ) ′  ∘ ∘  (  W  L    )  T   ⋅ ⋅  (  f  L    ) ′  ∘ ∘   ∇ ∇    a  L     C      δ δ   L      = (  f  L    ) ′  ∘ ∘   ∇ ∇    a  L     C ,       {\displaystyle {\begin{aligned}\delta ^{1}&=(f^{1})'\circ (W^{2})^{T}\cdot (f^{2})'\circ \cdots \circ (W^{L-1})^{T}\cdot (f^{L-1})'\circ (W^{L})^{T}\cdot (f^{L})'\circ \nabla _{a^{L}}C\\\delta ^{2}&=(f^{2})'\circ \cdots \circ (W^{L-1})^{T}\cdot (f^{L-1})'\circ (W^{L})^{T}\cdot (f^{L})'\circ \nabla _{a^{L}}C\\&\vdots \\\delta ^{L-1}&=(f^{L-1})'\circ (W^{L})^{T}\cdot (f^{L})'\circ \nabla _{a^{L}}C\\\delta ^{L}&=(f^{L})'\circ \nabla _{a^{L}}C,\end{aligned}}}  ![{\displaystyle {\begin{aligned}\delta ^{1}&=(f^{1})'\circ (W^{2})^{T}\cdot (f^{2})'\circ \cdots \circ (W^{L-1})^{T}\cdot (f^{L-1})'\circ (W^{L})^{T}\cdot (f^{L})'\circ \nabla _{a^{L}}C\\\delta ^{2}&=(f^{2})'\circ \cdots \circ (W^{L-1})^{T}\cdot (f^{L-1})'\circ (W^{L})^{T}\cdot (f^{L})'\circ \nabla _{a^{L}}C\\&\vdots \\\delta ^{L-1}&=(f^{L-1})'\circ (W^{L})^{T}\cdot (f^{L})'\circ \nabla _{a^{L}}C\\\delta ^{L}&=(f^{L})'\circ \nabla _{a^{L}}C,\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/65693d61321a41ee6a79f9e24e944f581a33240a) 

There are two key differences with backpropagation:

 
1. Computing      δ δ   l − −  1     {\displaystyle \delta ^{l-1}}  ![{\displaystyle \delta ^{l-1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e4ff3faf90011d3ed813a4ac2fe31904765e2963) in terms of      δ δ   l     {\displaystyle \delta ^{l}}  ![{\displaystyle \delta ^{l}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/249b787ef6af0149f7d71b951651c43633e0d56d) avoids the obvious duplicate multiplication of layers     l   {\displaystyle l}  ![{\displaystyle l}](https://wikimedia.org/api/rest_v1/media/math/render/svg/829091f745070b9eb97a80244129025440a1cfac) and beyond.
2. Multiplying starting from      ∇ ∇    a  L     C   {\displaystyle \nabla _{a^{L}}C}  ![{\displaystyle \nabla _{a^{L}}C}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0a3491216364a8fe84026d9f114a9477be761c2c) – propagating the error *backwards* – means that each step simply multiplies a vector (     δ δ   l     {\displaystyle \delta ^{l}}  ![{\displaystyle \delta ^{l}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/249b787ef6af0149f7d71b951651c43633e0d56d)) by the matrices of weights     (  W  l    )  T     {\displaystyle (W^{l})^{T}}  ![{\displaystyle (W^{l})^{T}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/95ded7046a67e4ea5039c86405383ff82c74308e) and derivatives of activations     (  f  l − −  1    ) ′    {\displaystyle (f^{l-1})'}  ![{\displaystyle (f^{l-1})'}](https://wikimedia.org/api/rest_v1/media/math/render/svg/89d6b56875a57b50369e097a55fe50f1be7b9aaf). By contrast, multiplying forwards, starting from the changes at an earlier layer, means that each multiplication multiplies a *matrix* by a *matrix*. This is much more expensive, and corresponds to tracking every possible path of a change in one layer     l   {\displaystyle l}  ![{\displaystyle l}](https://wikimedia.org/api/rest_v1/media/math/render/svg/829091f745070b9eb97a80244129025440a1cfac) forward to changes in the layer     l + 2   {\displaystyle l+2}  ![{\displaystyle l+2}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f96df20468aecf3a1b6dfedd08982cb6edc489bb) (for multiplying      W  l + 1     {\displaystyle W^{l+1}}  ![{\displaystyle W^{l+1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2d3f3b2ac57d2c95e81aafd230d2065e8f8cc401) by      W  l + 2     {\displaystyle W^{l+2}}  ![{\displaystyle W^{l+2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/74caba7e74227959403a15dfc8041720dae8817d), with additional multiplications for the derivatives of the activations), which unnecessarily computes the intermediate quantities of how weight changes affect the values of hidden nodes.

 

## Adjoint graph

 
|  | This sectionneeds expansion. You can help byadding missing information.(November 2019) |
| --- | --- |

 

For more general graphs, and other advanced variations, backpropagation can be understood in terms of [automatic differentiation](./Automatic_differentiation), where backpropagation is a special case of [reverse accumulation](./Reverse_accumulation) (or "reverse mode").[[2]](./Backpropagation#cite_note-DL-reverse-mode-2)

 


