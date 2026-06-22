---
source: sources/wiki-Backpropagation.md
source_url: https://en.wikipedia.org/wiki/Backpropagation
chunk: 4/8
---

## Derivation

 

The gradient descent method involves calculating the derivative of the loss function with respect to the weights of the network. This is normally done using backpropagation. Assuming one output neuron,[[h]](./Backpropagation#cite_note-13) the squared error function is

     E = L ( t , y )   {\displaystyle E=L(t,y)}  ![{\displaystyle E=L(t,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9db5e7ae55377b930b4bdaa8821d33fef2217792) 

where

     L   {\displaystyle L}  ![{\displaystyle L}](https://wikimedia.org/api/rest_v1/media/math/render/svg/103168b86f781fe6e9a4a87b8ea1cebe0ad4ede8) is the loss for the output     y   {\displaystyle y}  ![{\displaystyle y}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b8a6208ec717213d4317e666f1ae872e00620a0d) and target value     t   {\displaystyle t}  ![{\displaystyle t}](https://wikimedia.org/api/rest_v1/media/math/render/svg/65658b7b223af9e1acc877d848888ecdb4466560),     t   {\displaystyle t}  ![{\displaystyle t}](https://wikimedia.org/api/rest_v1/media/math/render/svg/65658b7b223af9e1acc877d848888ecdb4466560) is the target output for a training sample, and     y   {\displaystyle y}  ![{\displaystyle y}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b8a6208ec717213d4317e666f1ae872e00620a0d) is the actual output of the output neuron. 

In this section, the order of the weight indexes are reversed relative to the prior section:      w  i j     {\displaystyle w_{ij}}  ![{\displaystyle w_{ij}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3302ff355269436b43bc2fbe180303881c09321) is weight from the     i   {\displaystyle i}  ![{\displaystyle i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/add78d8608ad86e54951b8c8bd6c8d8416533d20)th to the
    j   {\displaystyle j}  ![{\displaystyle j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f461e54f5c093e92a55547b9764291390f0b5d0)th unit. [[i]](./Backpropagation#cite_note-14) For each neuron     j   {\displaystyle j}  ![{\displaystyle j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f461e54f5c093e92a55547b9764291390f0b5d0), its output      o  j     {\displaystyle o_{j}}  ![{\displaystyle o_{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0229f31d42e856d5af6aa970042abed37bce87f9) is defined as

      o  j   = φ φ  (   net   j   ) = φ φ   (   ∑ ∑   k = 1   n    w  k j    x  k    )  ,   {\displaystyle o_{j}=\varphi ({\text{net}}_{j})=\varphi \left(\sum _{k=1}^{n}w_{kj}x_{k}\right),}  ![{\displaystyle o_{j}=\varphi ({\text{net}}_{j})=\varphi \left(\sum _{k=1}^{n}w_{kj}x_{k}\right),}](https://wikimedia.org/api/rest_v1/media/math/render/svg/538346d8b13891ef0ca6ae18e6e4ccd68964458a) 

where the [activation function](./Activation_function)     φ φ    {\displaystyle \varphi }  ![{\displaystyle \varphi }](https://wikimedia.org/api/rest_v1/media/math/render/svg/33ee699558d09cf9d653f6351f9fda0b2f4aaa3e) is [non-linear](./Non-linear) and [differentiable](./Differentiable_function) over the activation region (the ReLU is not differentiable at one point). A historically used activation function is the [logistic function](./Logistic_function):

     φ φ  ( z ) =   1  1 +  e  − −  z        {\displaystyle \varphi (z)={\frac {1}{1+e^{-z}}}}  ![{\displaystyle \varphi (z)={\frac {1}{1+e^{-z}}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3d4d1a31c11f8fc840738cf30326c08cfcdba81) 

which has a [convenient](./Logistic_function#Mathematical_properties) derivative of:

        d φ φ    d z    = φ φ  ( z ) ( 1 − −  φ φ  ( z ) )   {\displaystyle {\frac {d\varphi }{dz}}=\varphi (z)(1-\varphi (z))}  ![{\displaystyle {\frac {d\varphi }{dz}}=\varphi (z)(1-\varphi (z))}](https://wikimedia.org/api/rest_v1/media/math/render/svg/52ed6ebbb4540ca08b3be2f1dbddd08d43304a83) 

The input       net   j     {\displaystyle {\text{net}}_{j}}  ![{\displaystyle {\text{net}}_{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ac5fc6b518b9eb768d6dfd4946640ea28f217dd3) to a neuron is the weighted sum of outputs      o  k     {\displaystyle o_{k}}  ![{\displaystyle o_{k}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1e57d19af3dbdeb11490339d1e35976411d5dc35) of previous neurons. If the neuron is in the first layer after the input layer, the      o  k     {\displaystyle o_{k}}  ![{\displaystyle o_{k}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1e57d19af3dbdeb11490339d1e35976411d5dc35) of the input layer are simply the inputs      x  k     {\displaystyle x_{k}}  ![{\displaystyle x_{k}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6d2b88c64c76a03611549fb9b4cf4ed060b56002) to the network. The number of input units to the neuron is     n   {\displaystyle n}  ![{\displaystyle n}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a601995d55609f2d9f5e233e36fbe9ea26011b3b). The variable      w  k j     {\displaystyle w_{kj}}  ![{\displaystyle w_{kj}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f648fa9eb42b941e1320b741cbb73467a5bffcb3) denotes the weight between neuron     k   {\displaystyle k}  ![{\displaystyle k}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c3c9a2c7b599b37105512c5d570edc034056dd40) of the previous layer and neuron     j   {\displaystyle j}  ![{\displaystyle j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f461e54f5c093e92a55547b9764291390f0b5d0) of the current layer.

 

### Finding the derivative of the error

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/6/60/ArtificialNeuronModel_english.png/500px-ArtificialNeuronModel_english.png)](./File:ArtificialNeuronModel_english.png)Diagram of an artificial neural network to illustrate the notation used here 

Calculating the [partial derivative](./Partial_derivative) of the error with respect to a weight      w  i j     {\displaystyle w_{ij}}  ![{\displaystyle w_{ij}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3302ff355269436b43bc2fbe180303881c09321) is done using the [chain rule](./Chain_rule) twice:

 
| ∂E∂wij=∂E∂oj∂oj∂wij=∂E∂oj∂oj∂netj∂netj∂wij{\displaystyle {\frac {\partial E}{\partial w_{ij}}}={\frac {\partial E}{\partial o_{j}}}{\frac {\partial o_{j}}{\partial w_{ij}}}={\frac {\partial E}{\partial o_{j}}}{\frac {\partial o_{j}}{\partial {\text{net}}_{j}}}{\frac {\partial {\text{net}}_{j}}{\partial w_{ij}}}} |  | Eq. 1 |
| --- | --- | --- |

 

In the last factor of the right-hand side of the above, only one term in the sum       net   j     {\displaystyle {\text{net}}_{j}}  ![{\displaystyle {\text{net}}_{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ac5fc6b518b9eb768d6dfd4946640ea28f217dd3) depends on      w  i j     {\displaystyle w_{ij}}  ![{\displaystyle w_{ij}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3302ff355269436b43bc2fbe180303881c09321), so that

 
| ∂netj∂wij=∂∂wij(∑k=1nwkjok)=∂∂wijwijoi=oi.{\displaystyle {\frac {\partial {\text{net}}_{j}}{\partial w_{ij}}}={\frac {\partial }{\partial w_{ij}}}\left(\sum _{k=1}^{n}w_{kj}o_{k}\right)={\frac {\partial }{\partial w_{ij}}}w_{ij}o_{i}=o_{i}.} |  | Eq. 2 |
| --- | --- | --- |

 

If the neuron is in the first layer after the input layer,      o  i     {\displaystyle o_{i}}  ![{\displaystyle o_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c81b6f1251a0d2e12011a746b586c5fa9a132d48) is just      x  i     {\displaystyle x_{i}}  ![{\displaystyle x_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e87000dd6142b81d041896a30fe58f0c3acb2158).

 

The derivative of the output of neuron     j   {\displaystyle j}  ![{\displaystyle j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f461e54f5c093e92a55547b9764291390f0b5d0) with respect to its input is simply the partial derivative of the activation function:

 
| ∂oj∂netj=∂φ(netj)∂netj{\displaystyle {\frac {\partial o_{j}}{\partial {\text{net}}_{j}}}={\frac {\partial \varphi ({\text{net}}_{j})}{\partial {\text{net}}_{j}}}} |  | Eq. 3 |
| --- | --- | --- |

 

which for the [logistic activation function](./Logistic_function)

        ∂ ∂   o  j     ∂ ∂    net   j      =   ∂ ∂   ∂ ∂    net   j      φ φ  (   net   j   ) = φ φ  (   net   j   ) ( 1 − −  φ φ  (   net   j   ) ) =  o  j   ( 1 − −   o  j   )   {\displaystyle {\frac {\partial o_{j}}{\partial {\text{net}}_{j}}}={\frac {\partial }{\partial {\text{net}}_{j}}}\varphi ({\text{net}}_{j})=\varphi ({\text{net}}_{j})(1-\varphi ({\text{net}}_{j}))=o_{j}(1-o_{j})}  ![{\displaystyle {\frac {\partial o_{j}}{\partial {\text{net}}_{j}}}={\frac {\partial }{\partial {\text{net}}_{j}}}\varphi ({\text{net}}_{j})=\varphi ({\text{net}}_{j})(1-\varphi ({\text{net}}_{j}))=o_{j}(1-o_{j})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ed36b5ea1321f0aca92fcb00068a8d083ec006f1) 

This is the reason why backpropagation requires that the activation function be [differentiable](./Differentiable_function). (Nevertheless, the [ReLU](./ReLU) activation function, which is non-differentiable at 0, has become quite popular, e.g. in [AlexNet](./AlexNet))

 

The first factor is straightforward to evaluate if the neuron is in the output layer, because then      o  j   = y   {\displaystyle o_{j}=y}  ![{\displaystyle o_{j}=y}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0543b379df7f7599d89d6317e7e11013941e2885) and

 
| ∂E∂oj=∂E∂y{\displaystyle {\frac {\partial E}{\partial o_{j}}}={\frac {\partial E}{\partial y}}} |  | Eq. 4 |
| --- | --- | --- |

 

If half of the square error is used as loss function we can rewrite it as

        ∂ ∂  E   ∂ ∂   o  j      =    ∂ ∂  E   ∂ ∂  y    =   ∂ ∂   ∂ ∂  y      1 2   ( t − −  y  )  2   = y − −  t   {\displaystyle {\frac {\partial E}{\partial o_{j}}}={\frac {\partial E}{\partial y}}={\frac {\partial }{\partial y}}{\frac {1}{2}}(t-y)^{2}=y-t}  ![{\displaystyle {\frac {\partial E}{\partial o_{j}}}={\frac {\partial E}{\partial y}}={\frac {\partial }{\partial y}}{\frac {1}{2}}(t-y)^{2}=y-t}](https://wikimedia.org/api/rest_v1/media/math/render/svg/39d55b81fdb2681ab5957f3e03b9150b6d043c36) 

However, if     j   {\displaystyle j}  ![{\displaystyle j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f461e54f5c093e92a55547b9764291390f0b5d0) is in an arbitrary inner layer of the network, finding the derivative     E   {\displaystyle E}  ![{\displaystyle E}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4232c9de2ee3eec0a9c0a19b15ab92daa6223f9b) with respect to      o  j     {\displaystyle o_{j}}  ![{\displaystyle o_{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0229f31d42e856d5af6aa970042abed37bce87f9) is less obvious.

 

Considering     E   {\displaystyle E}  ![{\displaystyle E}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4232c9de2ee3eec0a9c0a19b15ab92daa6223f9b) as a function with the inputs being all neurons     L = { u , v , … …  , w }   {\displaystyle L=\{u,v,\dots ,w\}}  ![{\displaystyle L=\{u,v,\dots ,w\}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c4abf35b7ef5693f8765266665cb87e9819cb2a7) receiving input from neuron     j   {\displaystyle j}  ![{\displaystyle j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f461e54f5c093e92a55547b9764291390f0b5d0),

        ∂ ∂  E (  o  j   )   ∂ ∂   o  j      =    ∂ ∂  E (   n e t   u   ,   net   v   , … …  ,   n e t   w   )   ∂ ∂   o  j        {\displaystyle {\frac {\partial E(o_{j})}{\partial o_{j}}}={\frac {\partial E(\mathrm {net} _{u},{\text{net}}_{v},\dots ,\mathrm {net} _{w})}{\partial o_{j}}}}  ![{\displaystyle {\frac {\partial E(o_{j})}{\partial o_{j}}}={\frac {\partial E(\mathrm {net} _{u},{\text{net}}_{v},\dots ,\mathrm {net} _{w})}{\partial o_{j}}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e660d78517bc99de7a438a69171dcdb7dd88740b) 

and taking the [total derivative](./Total_derivative) with respect to      o  j     {\displaystyle o_{j}}  ![{\displaystyle o_{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0229f31d42e856d5af6aa970042abed37bce87f9), a recursive expression for the derivative is obtained:

 
| ∂E∂oj=∑ℓ∈L(∂E∂netℓ∂netℓ∂oj)=∑ℓ∈L(∂E∂oℓ∂oℓ∂netℓ∂netℓ∂oj)=∑ℓ∈L(∂E∂oℓ∂oℓ∂netℓwjℓ){\displaystyle {\frac {\partial E}{\partial o_{j}}}=\sum _{\ell \in L}\left({\frac {\partial E}{\partial {\text{net}}_{\ell }}}{\frac {\partial {\text{net}}_{\ell }}{\partial o_{j}}}\right)=\sum _{\ell \in L}\left({\frac {\partial E}{\partial o_{\ell }}}{\frac {\partial o_{\ell }}{\partial {\text{net}}_{\ell }}}{\frac {\partial {\text{net}}_{\ell }}{\partial o_{j}}}\right)=\sum _{\ell \in L}\left({\frac {\partial E}{\partial o_{\ell }}}{\frac {\partial o_{\ell }}{\partial {\text{net}}_{\ell }}}w_{j\ell }\right)} |  | Eq. 5 |
| --- | --- | --- |

 

Therefore, the derivative with respect to      o  j     {\displaystyle o_{j}}  ![{\displaystyle o_{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0229f31d42e856d5af6aa970042abed37bce87f9) can be calculated if all the derivatives with respect to the outputs      o  ℓ ℓ      {\displaystyle o_{\ell }}  ![{\displaystyle o_{\ell }}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c2901ae7228e6fb253eb223344d54c70ccccaf00) of the next layer – the ones closer to the output neuron – are known. [Note, if any of the neurons in set     L   {\displaystyle L}  ![{\displaystyle L}](https://wikimedia.org/api/rest_v1/media/math/render/svg/103168b86f781fe6e9a4a87b8ea1cebe0ad4ede8) were not connected to neuron     j   {\displaystyle j}  ![{\displaystyle j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f461e54f5c093e92a55547b9764291390f0b5d0), they would be independent of      w  i j     {\displaystyle w_{ij}}  ![{\displaystyle w_{ij}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3302ff355269436b43bc2fbe180303881c09321) and the corresponding partial derivative under the summation would vanish to 0.]

 

Substituting **[Eq. 2](./Backpropagation#math_Eq._2)**, **[Eq. 3](./Backpropagation#math_Eq._3)** **[Eq.4](./Backpropagation#math_Eq.4)** and **[Eq. 5](./Backpropagation#math_Eq._5)** in **[Eq. 1](./Backpropagation#math_Eq._1)** we obtain:

        ∂ ∂  E   ∂ ∂   w  i j      =    ∂ ∂  E   ∂ ∂   o  j         ∂ ∂   o  j     ∂ ∂    net   j         ∂ ∂    net   j     ∂ ∂   w  i j      =    ∂ ∂  E   ∂ ∂   o  j         ∂ ∂   o  j     ∂ ∂    net   j       o  i     {\displaystyle {\frac {\partial E}{\partial w_{ij}}}={\frac {\partial E}{\partial o_{j}}}{\frac {\partial o_{j}}{\partial {\text{net}}_{j}}}{\frac {\partial {\text{net}}_{j}}{\partial w_{ij}}}={\frac {\partial E}{\partial o_{j}}}{\frac {\partial o_{j}}{\partial {\text{net}}_{j}}}o_{i}}  ![{\displaystyle {\frac {\partial E}{\partial w_{ij}}}={\frac {\partial E}{\partial o_{j}}}{\frac {\partial o_{j}}{\partial {\text{net}}_{j}}}{\frac {\partial {\text{net}}_{j}}{\partial w_{ij}}}={\frac {\partial E}{\partial o_{j}}}{\frac {\partial o_{j}}{\partial {\text{net}}_{j}}}o_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ae55d1c0135131a9b5c0db89f5e20ffae8bc7040)        ∂ ∂  E   ∂ ∂   w  i j      =  o  i    δ δ   j     {\displaystyle {\frac {\partial E}{\partial w_{ij}}}=o_{i}\delta _{j}}  ![{\displaystyle {\frac {\partial E}{\partial w_{ij}}}=o_{i}\delta _{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e86f74f9e33c38bc1d5664ddd9794da381976af3) 

with

      δ δ   j   =    ∂ ∂  E   ∂ ∂   o  j         ∂ ∂   o  j     ∂ ∂    net   j      =   {       ∂ ∂  L ( t ,  o  j   )   ∂ ∂   o  j         d φ φ  (   net   j   )   d   net   j         if   j   is an output neuron,      (  ∑ ∑   ℓ ℓ  ∈ ∈  L    w  j ℓ ℓ     δ δ   ℓ ℓ    )    d φ φ  (   net   j   )   d   net   j         if   j   is an inner neuron.          {\displaystyle \delta _{j}={\frac {\partial E}{\partial o_{j}}}{\frac {\partial o_{j}}{\partial {\text{net}}_{j}}}={\begin{cases}{\frac {\partial L(t,o_{j})}{\partial o_{j}}}{\frac {d\varphi ({\text{net}}_{j})}{d{\text{net}}_{j}}}&{\text{if }}j{\text{ is an output neuron,}}\\(\sum _{\ell \in L}w_{j\ell }\delta _{\ell }){\frac {d\varphi ({\text{net}}_{j})}{d{\text{net}}_{j}}}&{\text{if }}j{\text{ is an inner neuron.}}\end{cases}}}  ![{\displaystyle \delta _{j}={\frac {\partial E}{\partial o_{j}}}{\frac {\partial o_{j}}{\partial {\text{net}}_{j}}}={\begin{cases}{\frac {\partial L(t,o_{j})}{\partial o_{j}}}{\frac {d\varphi ({\text{net}}_{j})}{d{\text{net}}_{j}}}&{\text{if }}j{\text{ is an output neuron,}}\\(\sum _{\ell \in L}w_{j\ell }\delta _{\ell }){\frac {d\varphi ({\text{net}}_{j})}{d{\text{net}}_{j}}}&{\text{if }}j{\text{ is an inner neuron.}}\end{cases}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/54de826820eed0648c7dba5e345120bb23483261) 

if     φ φ    {\displaystyle \varphi }  ![{\displaystyle \varphi }](https://wikimedia.org/api/rest_v1/media/math/render/svg/33ee699558d09cf9d653f6351f9fda0b2f4aaa3e) is the logistic function, and the error is the square error:

      δ δ   j   =    ∂ ∂  E   ∂ ∂   o  j         ∂ ∂   o  j     ∂ ∂    net   j      =   {    (  o  j   − −   t  j   )  o  j   ( 1 − −   o  j   )    if   j   is an output neuron,      (  ∑ ∑   ℓ ℓ  ∈ ∈  L    w  j ℓ ℓ     δ δ   ℓ ℓ    )  o  j   ( 1 − −   o  j   )    if   j   is an inner neuron.          {\displaystyle \delta _{j}={\frac {\partial E}{\partial o_{j}}}{\frac {\partial o_{j}}{\partial {\text{net}}_{j}}}={\begin{cases}(o_{j}-t_{j})o_{j}(1-o_{j})&{\text{if }}j{\text{ is an output neuron,}}\\(\sum _{\ell \in L}w_{j\ell }\delta _{\ell })o_{j}(1-o_{j})&{\text{if }}j{\text{ is an inner neuron.}}\end{cases}}}  ![{\displaystyle \delta _{j}={\frac {\partial E}{\partial o_{j}}}{\frac {\partial o_{j}}{\partial {\text{net}}_{j}}}={\begin{cases}(o_{j}-t_{j})o_{j}(1-o_{j})&{\text{if }}j{\text{ is an output neuron,}}\\(\sum _{\ell \in L}w_{j\ell }\delta _{\ell })o_{j}(1-o_{j})&{\text{if }}j{\text{ is an inner neuron.}}\end{cases}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/991c8f020800ec1da130849e20a3a415613e9bdb) 

To update the weight      w  i j     {\displaystyle w_{ij}}  ![{\displaystyle w_{ij}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3302ff355269436b43bc2fbe180303881c09321) using gradient descent, one must choose a [learning rate](./Learning_rate),     η η  > 0   {\displaystyle \eta >0}  ![{\displaystyle \eta >0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ce70a0b6474dcb5aaeea68b799038e8f60b54ef1). The change in weight needs to reflect the impact on     E   {\displaystyle E}  ![{\displaystyle E}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4232c9de2ee3eec0a9c0a19b15ab92daa6223f9b) of an increase or decrease in      w  i j     {\displaystyle w_{ij}}  ![{\displaystyle w_{ij}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3302ff355269436b43bc2fbe180303881c09321). If        ∂ ∂  E   ∂ ∂   w  i j      > 0   {\displaystyle {\frac {\partial E}{\partial w_{ij}}}>0}  ![{\displaystyle {\frac {\partial E}{\partial w_{ij}}}>0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/52a50d4d1cc9a82d13f38ab6317adcbdb24b9112), an increase in      w  i j     {\displaystyle w_{ij}}  ![{\displaystyle w_{ij}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3302ff355269436b43bc2fbe180303881c09321) increases     E   {\displaystyle E}  ![{\displaystyle E}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4232c9de2ee3eec0a9c0a19b15ab92daa6223f9b); conversely, if        ∂ ∂  E   ∂ ∂   w  i j      < 0   {\displaystyle {\frac {\partial E}{\partial w_{ij}}}<0}  ![{\displaystyle {\frac {\partial E}{\partial w_{ij}}}<0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5669ee0bda9e01723c570b9496abbe4bdbd96357), an increase in      w  i j     {\displaystyle w_{ij}}  ![{\displaystyle w_{ij}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3302ff355269436b43bc2fbe180303881c09321) decreases     E   {\displaystyle E}  ![{\displaystyle E}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4232c9de2ee3eec0a9c0a19b15ab92daa6223f9b). The new     Δ Δ   w  i j     {\displaystyle \Delta w_{ij}}  ![{\displaystyle \Delta w_{ij}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/75343e68050b7d0bc74986719687a845095ad59f) is added to the old weight, and the product of the [learning rate](./Learning_rate) and the gradient, multiplied by     − −  1   {\displaystyle -1}  ![{\displaystyle -1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/704fb0427140d054dd267925495e78164fee9aac) guarantees that      w  i j     {\displaystyle w_{ij}}  ![{\displaystyle w_{ij}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3302ff355269436b43bc2fbe180303881c09321) changes in a way that always decreases     E   {\displaystyle E}  ![{\displaystyle E}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4232c9de2ee3eec0a9c0a19b15ab92daa6223f9b). In other words, in the equation immediately below,     − −  η η     ∂ ∂  E   ∂ ∂   w  i j        {\displaystyle -\eta {\frac {\partial E}{\partial w_{ij}}}}  ![{\displaystyle -\eta {\frac {\partial E}{\partial w_{ij}}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f5f908b3074295c5281b9f6363c4dd65cca7476c) always changes      w  i j     {\displaystyle w_{ij}}  ![{\displaystyle w_{ij}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3302ff355269436b43bc2fbe180303881c09321) in such a way that     E   {\displaystyle E}  ![{\displaystyle E}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4232c9de2ee3eec0a9c0a19b15ab92daa6223f9b) is decreased:

     Δ Δ   w  i j   = − −  η η     ∂ ∂  E   ∂ ∂   w  i j      = − −  η η   o  i    δ δ   j     {\displaystyle \Delta w_{ij}=-\eta {\frac {\partial E}{\partial w_{ij}}}=-\eta o_{i}\delta _{j}}  ![{\displaystyle \Delta w_{ij}=-\eta {\frac {\partial E}{\partial w_{ij}}}=-\eta o_{i}\delta _{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/19e12758145196a841af866e8dfa2437d35c82e8) 


