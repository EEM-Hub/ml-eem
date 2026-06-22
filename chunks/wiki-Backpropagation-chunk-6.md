---
source: sources/wiki-Backpropagation.md
source_url: https://en.wikipedia.org/wiki/Backpropagation
chunk: 6/8
---

## Notes

  
1. [↑](./Backpropagation#cite_ref-3) Use     C   {\displaystyle C}  ![{\displaystyle C}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4fc55753007cd3c18576f7933f6f089196732029) for the loss function to allow     L   {\displaystyle L}  ![{\displaystyle L}](https://wikimedia.org/api/rest_v1/media/math/render/svg/103168b86f781fe6e9a4a87b8ea1cebe0ad4ede8) to be used for the number of layers
2. [↑](./Backpropagation#cite_ref-4) This follows [Nielsen (2015)](./Backpropagation#CITEREFNielsen2015), and means (left) multiplication by the matrix      W  l     {\displaystyle W^{l}}  ![{\displaystyle W^{l}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/60b87bc8138a82f110491bb1abd0ea6eefe84c22) corresponds to converting output values of layer     l − −  1   {\displaystyle l-1}  ![{\displaystyle l-1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4e0d448948a353d0b2469b88ca918f34e32c8752) to input values of layer     l   {\displaystyle l}  ![{\displaystyle l}](https://wikimedia.org/api/rest_v1/media/math/render/svg/829091f745070b9eb97a80244129025440a1cfac): columns correspond to input coordinates, rows correspond to output coordinates.
3. [↑](./Backpropagation#cite_ref-7) This section largely follows and summarizes [Nielsen (2015)](./Backpropagation#CITEREFNielsen2015).
4. [↑](./Backpropagation#cite_ref-8) The derivative of the loss function is a [covector](./Covector), since the loss function is a [scalar-valued function](./Scalar-valued_function) of several variables.
5. [↑](./Backpropagation#cite_ref-9) The activation function is applied to each node separately, so the derivative is just the diagonal matrix of the derivative on each node. This is often represented as the [Hadamard product](./Hadamard_product_(matrices)) with the vector of derivatives, denoted by     (  f  l    ) ′  ⊙ ⊙    {\displaystyle (f^{l})'\odot }  ![{\displaystyle (f^{l})'\odot }](https://wikimedia.org/api/rest_v1/media/math/render/svg/ee57033dfe04a65842e5260c85240f9295cb464c), which is mathematically identical but better matches the internal representation of the derivatives as a vector, rather than a diagonal matrix.
6. [↑](./Backpropagation#cite_ref-10) Since matrix multiplication is linear, the derivative of multiplying by a matrix is just the matrix:     ( W x  ) ′  = W   {\displaystyle (Wx)'=W}  ![{\displaystyle (Wx)'=W}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0beeadf03249427d72b4c95732f23143fdfd6c30).
7. [↑](./Backpropagation#cite_ref-12) One may notice that multi-layer neural networks use non-linear activation functions, so an example with linear neurons seems obscure. However, even though the error surface of multi-layer networks are much more complicated, locally they can be approximated by a paraboloid. Therefore, linear neurons are used for simplicity and easier understanding.
8. [↑](./Backpropagation#cite_ref-13) There can be multiple output neurons, in which case the error is the squared norm of the difference vector.
9. [↑](./Backpropagation#cite_ref-14) This order follows (Rumelhart, Hinton & Williams, 1986a):[[5]](./Backpropagation#cite_note-RumelhartHintonWilliams1986a-11) "    Δ Δ   w  i   j   {\displaystyle \Delta w_{i}j}  ![{\displaystyle \Delta w_{i}j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/06827536202e269493d147fd8987b9918f7a4aab) is the change to be made to the weight from the     i   {\displaystyle i}  ![{\displaystyle i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/add78d8608ad86e54951b8c8bd6c8d8416533d20)th to the
    j   {\displaystyle j}  ![{\displaystyle j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f461e54f5c093e92a55547b9764291390f0b5d0)th unit"

 


