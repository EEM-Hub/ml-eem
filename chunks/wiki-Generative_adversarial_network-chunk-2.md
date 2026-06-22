---
source: sources/wiki-Generative_adversarial_network.md
source_url: https://en.wikipedia.org/wiki/Generative_adversarial_network
chunk: 2/7
---

## Mathematical properties

 

### Measure-theoretic considerations

 

This section provides some of the mathematical theory behind these methods.

In [modern probability theory](./Probability_axioms) based on [measure theory](./Measure_theory), a probability space also needs to be equipped with a [σ-algebra](./Σ-algebra). As a result, a more rigorous definition of the GAN game would make the following changes:

Each probability space     ( Ω Ω  ,   B   ,  μ μ   ref   )   {\displaystyle (\Omega ,{\mathcal {B}},\mu _{\text{ref}})}  ![{\displaystyle (\Omega ,{\mathcal {B}},\mu _{\text{ref}})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8199802d29ba172d426b0c355f6bd1ee4f1ca2b7) defines a GAN game.

 

The generator's strategy set is       P   ( Ω Ω  ,   B   )   {\displaystyle {\mathcal {P}}(\Omega ,{\mathcal {B}})}  ![{\displaystyle {\mathcal {P}}(\Omega ,{\mathcal {B}})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/cb03d702198c4033de8ede7e8c8375115e55e739), the set of all probability measures      μ μ   G     {\displaystyle \mu _{G}}  ![{\displaystyle \mu _{G}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/dda577f83b0f673b3c59652dfcd8c195b965030f) on the measure-space     ( Ω Ω  ,   B   )   {\displaystyle (\Omega ,{\mathcal {B}})}  ![{\displaystyle (\Omega ,{\mathcal {B}})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3c71c3b681b11d672fb4712a121dc140ff810ef).

The discriminator's strategy set is the set of [Markov kernels](./Markov_kernel)      μ μ   D   : ( Ω Ω  ,   B   ) → →    P   ( [ 0 , 1 ] ,   B   ( [ 0 , 1 ] ) )   {\displaystyle \mu _{D}:(\Omega ,{\mathcal {B}})\to {\mathcal {P}}([0,1],{\mathcal {B}}([0,1]))}  ![{\displaystyle \mu _{D}:(\Omega ,{\mathcal {B}})\to {\mathcal {P}}([0,1],{\mathcal {B}}([0,1]))}](https://wikimedia.org/api/rest_v1/media/math/render/svg/54c054944874a3a2751d0c67770b8af5d0425425), where       B   ( [ 0 , 1 ] )   {\displaystyle {\mathcal {B}}([0,1])}  ![{\displaystyle {\mathcal {B}}([0,1])}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2a2035d78993071419aef7ec2b3f1b7df235173f) is the [Borel σ-algebra](./Borel_Algebra) on     [ 0 , 1 ]   {\displaystyle [0,1]}  ![{\displaystyle [0,1]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/738f7d23bb2d9642bab520020873cccbef49768d).

Since issues of measurability never arise in practice, these will not concern us further.

 

### Choice of the strategy set

 

In the most generic version of the GAN game described above, the strategy set for the discriminator contains all Markov kernels      μ μ   D   : Ω Ω  → →    P   [ 0 , 1 ]   {\displaystyle \mu _{D}:\Omega \to {\mathcal {P}}[0,1]}  ![{\displaystyle \mu _{D}:\Omega \to {\mathcal {P}}[0,1]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/dce97271df1c30e57ae96f72c566661f1bae9dad), and the strategy set for the generator contains arbitrary [probability distributions](./Probability_distribution)      μ μ   G     {\displaystyle \mu _{G}}  ![{\displaystyle \mu _{G}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/dda577f83b0f673b3c59652dfcd8c195b965030f) on     Ω Ω    {\displaystyle \Omega }  ![{\displaystyle \Omega }](https://wikimedia.org/api/rest_v1/media/math/render/svg/24b0d5ca6f381068d756f6337c08e0af9d1eeb6f).

 

However, as shown below, the optimal discriminator strategy against any      μ μ   G     {\displaystyle \mu _{G}}  ![{\displaystyle \mu _{G}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/dda577f83b0f673b3c59652dfcd8c195b965030f) is deterministic, so there is no loss of generality in restricting the discriminator's strategies to deterministic functions     D : Ω Ω  → →  [ 0 , 1 ]   {\displaystyle D:\Omega \to [0,1]}  ![{\displaystyle D:\Omega \to [0,1]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/298d9bf50461bcde11bd77e61e9048b0eaabbc12). In most applications,     D   {\displaystyle D}  ![{\displaystyle D}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f34a0c600395e5d4345287e21fb26efd386990e6) is a [deep neural network](./Deep_neural_network) function.

 

As for the generator, while      μ μ   G     {\displaystyle \mu _{G}}  ![{\displaystyle \mu _{G}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/dda577f83b0f673b3c59652dfcd8c195b965030f) could theoretically be any computable probability distribution, in practice, it is usually implemented as a [pushforward](./Pushforward_measure):      μ μ   G   =  μ μ   Z   ∘ ∘   G  − −  1     {\displaystyle \mu _{G}=\mu _{Z}\circ G^{-1}}  ![{\displaystyle \mu _{G}=\mu _{Z}\circ G^{-1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8ab37d81cd40b907ad6c73294e256fbb7b3d0daa). That is, start with a random variable     z ∼ ∼   μ μ   Z     {\displaystyle z\sim \mu _{Z}}  ![{\displaystyle z\sim \mu _{Z}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d0bc23402cf269f4cb481c696feede26eb43acb7), where      μ μ   Z     {\displaystyle \mu _{Z}}  ![{\displaystyle \mu _{Z}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4dfd7b88be4d0e36a21cb6d4a486bcaf0128a324) is a probability distribution that is easy to compute (such as the [uniform distribution](./Continuous_uniform_distribution), or the [Gaussian distribution](./Normal_distribution)), then define a function     G :  Ω Ω   Z   → →  Ω Ω    {\displaystyle G:\Omega _{Z}\to \Omega }  ![{\displaystyle G:\Omega _{Z}\to \Omega }](https://wikimedia.org/api/rest_v1/media/math/render/svg/040cac2259b446fc3c032b683b8e7c9fb57aaea5). Then the distribution      μ μ   G     {\displaystyle \mu _{G}}  ![{\displaystyle \mu _{G}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/dda577f83b0f673b3c59652dfcd8c195b965030f) is the distribution of     G ( z )   {\displaystyle G(z)}  ![{\displaystyle G(z)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c56c297de4b4d6b42f3bdbfa47ffe1a81c45c147).

 

Consequently, the generator's strategy is usually defined as just     G   {\displaystyle G}  ![{\displaystyle G}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f5f3c8921a3b352de45446a6789b104458c9f90b), leaving     z ∼ ∼   μ μ   Z     {\displaystyle z\sim \mu _{Z}}  ![{\displaystyle z\sim \mu _{Z}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d0bc23402cf269f4cb481c696feede26eb43acb7) implicit. In this formalism, the GAN game objective is    L ( G , D ) :=  E  x ∼ ∼   μ μ   ref     ⁡ ⁡  [ ln ⁡ ⁡  D ( x ) ] +  E  z ∼ ∼   μ μ   Z     ⁡ ⁡  [ ln ⁡ ⁡  ( 1 − −  D ( G ( z ) ) ) ] .   {\displaystyle L(G,D):=\operatorname {E} _{x\sim \mu _{\text{ref}}}[\ln D(x)]+\operatorname {E} _{z\sim \mu _{Z}}[\ln(1-D(G(z)))].}  ![{\displaystyle L(G,D):=\operatorname {E} _{x\sim \mu _{\text{ref}}}[\ln D(x)]+\operatorname {E} _{z\sim \mu _{Z}}[\ln(1-D(G(z)))].}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2b7e0c94d6ab9885dfc1e432cda9d39a8e1f29b0)

 

### Generative reparametrization

 

The GAN architecture has two main components. One is casting optimization into a game, of form      min  G    max  D   L ( G , D )   {\displaystyle \min _{G}\max _{D}L(G,D)}  ![{\displaystyle \min _{G}\max _{D}L(G,D)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e9563e238ceb863fb98c258aa56b16873cb30514), which is different from the usual kind of optimization, of form      min  θ θ    L ( θ θ  )   {\displaystyle \min _{\theta }L(\theta )}  ![{\displaystyle \min _{\theta }L(\theta )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c4be030d0fbd7d7ccceb9d12b30e59f0a824327e). The other is the decomposition of      μ μ   G     {\displaystyle \mu _{G}}  ![{\displaystyle \mu _{G}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/dda577f83b0f673b3c59652dfcd8c195b965030f) into      μ μ   Z   ∘ ∘   G  − −  1     {\displaystyle \mu _{Z}\circ G^{-1}}  ![{\displaystyle \mu _{Z}\circ G^{-1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/74f0b05f29a2e4abca5208276c4bf7d7b6e80ace), which can be understood as a reparametrization trick.

 

To see its significance, one must compare GAN with previous methods for learning generative models, which were plagued with "intractable probabilistic computations that arise in maximum likelihood estimation and related strategies".[[1]](./Generative_adversarial_network#cite_note-GANnips-1)

 

At the same time, Kingma and Welling[[10]](./Generative_adversarial_network#cite_note-10) and Rezende et al.[[11]](./Generative_adversarial_network#cite_note-11) developed the same idea of reparametrization into a general stochastic backpropagation method. Among its first applications was the [variational autoencoder](./Variational_autoencoder).

 

### Move order and strategic equilibria

 

In the original paper, as well as most subsequent papers, it is usually assumed that the generator *moves first*, and the discriminator *moves second*, thus giving the following minimax game:     min   μ μ   G      max   μ μ   D     L (  μ μ   G   ,  μ μ   D   ) :=  E  x ∼ ∼   μ μ   ref   , y ∼ ∼   μ μ   D   ( x )   ⁡ ⁡  [ ln ⁡ ⁡  y ] +  E  x ∼ ∼   μ μ   G   , y ∼ ∼   μ μ   D   ( x )   ⁡ ⁡  [ ln ⁡ ⁡  ( 1 − −  y ) ] .   {\displaystyle \min _{\mu _{G}}\max _{\mu _{D}}L(\mu _{G},\mu _{D}):=\operatorname {E} _{x\sim \mu _{\text{ref}},y\sim \mu _{D}(x)}[\ln y]+\operatorname {E} _{x\sim \mu _{G},y\sim \mu _{D}(x)}[\ln(1-y)].}  ![{\displaystyle \min _{\mu _{G}}\max _{\mu _{D}}L(\mu _{G},\mu _{D}):=\operatorname {E} _{x\sim \mu _{\text{ref}},y\sim \mu _{D}(x)}[\ln y]+\operatorname {E} _{x\sim \mu _{G},y\sim \mu _{D}(x)}[\ln(1-y)].}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c339b2edc936a7769d08924365decd79dec73165)

 

If both the generator's and the discriminator's strategy sets are spanned by a finite number of strategies, then by the [minimax theorem](./Minimax_theorem),     min   μ μ   G      max   μ μ   D     L (  μ μ   G   ,  μ μ   D   ) =  max   μ μ   D      min   μ μ   G     L (  μ μ   G   ,  μ μ   D   )   {\displaystyle \min _{\mu _{G}}\max _{\mu _{D}}L(\mu _{G},\mu _{D})=\max _{\mu _{D}}\min _{\mu _{G}}L(\mu _{G},\mu _{D})}  ![{\displaystyle \min _{\mu _{G}}\max _{\mu _{D}}L(\mu _{G},\mu _{D})=\max _{\mu _{D}}\min _{\mu _{G}}L(\mu _{G},\mu _{D})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/62ff1981dfa6b88c4280b870ad78a494b3a5f1c0)that is, the move order does not matter.

 

However, since the strategy sets are both not finitely spanned, the minimax theorem does not apply, and the idea of an "equilibrium" becomes delicate. To wit, there are the following different concepts of equilibrium:

 
- Equilibrium when generator moves first, and discriminator moves second:        μ μ  ^ ^      G   ∈ ∈  arg ⁡ ⁡   min   μ μ   G      max   μ μ   D     L (  μ μ   G   ,  μ μ   D   ) ,      μ μ  ^ ^      D   ∈ ∈  arg ⁡ ⁡   max   μ μ   D     L (     μ μ  ^ ^      G   ,  μ μ   D   ) ,    {\displaystyle {\hat {\mu }}_{G}\in \arg \min _{\mu _{G}}\max _{\mu _{D}}L(\mu _{G},\mu _{D}),\quad {\hat {\mu }}_{D}\in \arg \max _{\mu _{D}}L({\hat {\mu }}_{G},\mu _{D}),\quad }  ![{\displaystyle {\hat {\mu }}_{G}\in \arg \min _{\mu _{G}}\max _{\mu _{D}}L(\mu _{G},\mu _{D}),\quad {\hat {\mu }}_{D}\in \arg \max _{\mu _{D}}L({\hat {\mu }}_{G},\mu _{D}),\quad }](https://wikimedia.org/api/rest_v1/media/math/render/svg/aa056df879862edd13b98ba12bec9a613e52eb77)
- Equilibrium when discriminator moves first, and generator moves second:        μ μ  ^ ^      D   ∈ ∈  arg ⁡ ⁡   max   μ μ   D      min   μ μ   G     L (  μ μ   G   ,  μ μ   D   ) ,      μ μ  ^ ^      G   ∈ ∈  arg ⁡ ⁡   min   μ μ   G     L (  μ μ   G   ,     μ μ  ^ ^      D   ) ,   {\displaystyle {\hat {\mu }}_{D}\in \arg \max _{\mu _{D}}\min _{\mu _{G}}L(\mu _{G},\mu _{D}),\quad {\hat {\mu }}_{G}\in \arg \min _{\mu _{G}}L(\mu _{G},{\hat {\mu }}_{D}),}  ![{\displaystyle {\hat {\mu }}_{D}\in \arg \max _{\mu _{D}}\min _{\mu _{G}}L(\mu _{G},\mu _{D}),\quad {\hat {\mu }}_{G}\in \arg \min _{\mu _{G}}L(\mu _{G},{\hat {\mu }}_{D}),}](https://wikimedia.org/api/rest_v1/media/math/render/svg/08032237cedf412aacc7a95b5c69bea9de1b17d9)
- [Nash equilibrium](./Nash_equilibrium)     (     μ μ  ^ ^      D   ,     μ μ  ^ ^      G   )   {\displaystyle ({\hat {\mu }}_{D},{\hat {\mu }}_{G})}  ![{\displaystyle ({\hat {\mu }}_{D},{\hat {\mu }}_{G})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ac9ac97217a832bb60a5756d2e60f83e9fddf73e), which is stable under simultaneous move order:        μ μ  ^ ^      D   ∈ ∈  arg ⁡ ⁡   max   μ μ   D     L (     μ μ  ^ ^      G   ,  μ μ   D   ) ,      μ μ  ^ ^      G   ∈ ∈  arg ⁡ ⁡   min   μ μ   G     L (  μ μ   G   ,     μ μ  ^ ^      D   )   {\displaystyle {\hat {\mu }}_{D}\in \arg \max _{\mu _{D}}L({\hat {\mu }}_{G},\mu _{D}),\quad {\hat {\mu }}_{G}\in \arg \min _{\mu _{G}}L(\mu _{G},{\hat {\mu }}_{D})}  ![{\displaystyle {\hat {\mu }}_{D}\in \arg \max _{\mu _{D}}L({\hat {\mu }}_{G},\mu _{D}),\quad {\hat {\mu }}_{G}\in \arg \min _{\mu _{G}}L(\mu _{G},{\hat {\mu }}_{D})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/29ff8bfcd5fc1f619a8526c325a0d9c44f0a9673)

 

For general games, these equilibria do not have to agree, or even to exist. For the original GAN game, these equilibria all exist, and are all equal. However, for more general GAN games, these do not necessarily exist, or agree.[[12]](./Generative_adversarial_network#cite_note-:2-12)

 

### Main theorems for GAN game

The original GAN paper proved the following two theorems:[[1]](./Generative_adversarial_network#cite_note-GANnips-1)

 

**Theorem** (the optimal discriminator computes the Jensen–Shannon divergence)—For any fixed generator strategy      μ μ   G     {\displaystyle \mu _{G}}  ![{\displaystyle \mu _{G}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/dda577f83b0f673b3c59652dfcd8c195b965030f), let the optimal reply be      D  ∗ ∗    = arg ⁡ ⁡   max  D   L (  μ μ   G   , D )   {\displaystyle D^{*}=\arg \max _{D}L(\mu _{G},D)}  ![{\displaystyle D^{*}=\arg \max _{D}L(\mu _{G},D)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f2cfb932c958232bd3c37ee1b8adf287157b6aed), then

 

         D  ∗ ∗    ( x )    =    d  μ μ   ref     d (  μ μ   ref   +  μ μ   G   )        L (  μ μ   G   ,  D  ∗ ∗    )    = 2  D  J S   (  μ μ   ref   ;  μ μ   G   ) − −  2 ln ⁡ ⁡  2       {\displaystyle {\begin{aligned}D^{*}(x)&={\frac {d\mu _{\text{ref}}}{d(\mu _{\text{ref}}+\mu _{G})}}\\[6pt]L(\mu _{G},D^{*})&=2D_{JS}(\mu _{\text{ref}};\mu _{G})-2\ln 2\end{aligned}}}  ![{\displaystyle {\begin{aligned}D^{*}(x)&={\frac {d\mu _{\text{ref}}}{d(\mu _{\text{ref}}+\mu _{G})}}\\[6pt]L(\mu _{G},D^{*})&=2D_{JS}(\mu _{\text{ref}};\mu _{G})-2\ln 2\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e64425ce6861c6462719ccf0a1f6783afbe369cb)

 

where the derivative is the [Radon–Nikodym derivative](./Radon–Nikodym_derivative), and      D  J S     {\displaystyle D_{JS}}  ![{\displaystyle D_{JS}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3ac9a4b47b552666c5597114ce9d57e81e5d627a) is the [Jensen–Shannon divergence](./Jensen–Shannon_divergence).

 **Proof** 

By Jensen's inequality,

 

     E  x ∼ ∼   μ μ   ref   , y ∼ ∼   μ μ   D   ( x )   ⁡ ⁡  [ ln ⁡ ⁡  y ] ≤ ≤   E  x ∼ ∼   μ μ   ref     ⁡ ⁡  [ ln ⁡ ⁡   E  y ∼ ∼   μ μ   D   ( x )   ⁡ ⁡  [ y ] ]   {\displaystyle \operatorname {E} _{x\sim \mu _{\text{ref}},y\sim \mu _{D}(x)}[\ln y]\leq \operatorname {E} _{x\sim \mu _{\text{ref}}}[\ln \operatorname {E} _{y\sim \mu _{D}(x)}[y]]}  ![{\displaystyle \operatorname {E} _{x\sim \mu _{\text{ref}},y\sim \mu _{D}(x)}[\ln y]\leq \operatorname {E} _{x\sim \mu _{\text{ref}}}[\ln \operatorname {E} _{y\sim \mu _{D}(x)}[y]]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/91edf51ddaeb0c19e5ccf5ab46abc29c272faf4c)
and similarly for the other term. Therefore, the optimal reply can be deterministic, i.e.      μ μ   D   ( x ) =  δ δ   D ( x )     {\displaystyle \mu _{D}(x)=\delta _{D(x)}}  ![{\displaystyle \mu _{D}(x)=\delta _{D(x)}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e7abeefe38a8088fa2f56360c90b005c9ac6d8d0) for some function     D : Ω Ω  → →  [ 0 , 1 ]   {\displaystyle D:\Omega \to [0,1]}  ![{\displaystyle D:\Omega \to [0,1]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/298d9bf50461bcde11bd77e61e9048b0eaabbc12), in which case

 

    L (  μ μ   G   ,  μ μ   D   ) :=  E  x ∼ ∼   μ μ   ref     ⁡ ⁡  [ ln ⁡ ⁡  D ( x ) ] +  E  x ∼ ∼   μ μ   G     ⁡ ⁡  [ ln ⁡ ⁡  ( 1 − −  D ( x ) ) ] .   {\displaystyle L(\mu _{G},\mu _{D}):=\operatorname {E} _{x\sim \mu _{\text{ref}}}[\ln D(x)]+\operatorname {E} _{x\sim \mu _{G}}[\ln(1-D(x))].}  ![{\displaystyle L(\mu _{G},\mu _{D}):=\operatorname {E} _{x\sim \mu _{\text{ref}}}[\ln D(x)]+\operatorname {E} _{x\sim \mu _{G}}[\ln(1-D(x))].}](https://wikimedia.org/api/rest_v1/media/math/render/svg/83f31aa6db727ba20dece445805a8766c604db49)

 

To define suitable density functions, we define a base measure     μ μ  :=  μ μ   ref   +  μ μ   G     {\displaystyle \mu :=\mu _{\text{ref}}+\mu _{G}}  ![{\displaystyle \mu :=\mu _{\text{ref}}+\mu _{G}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e47ede353bcaa3bd0775f1eeda1b41a278dbffae), which allows us to take the Radon–Nikodym derivatives

 

     ρ ρ   ref   =    d  μ μ   ref     d μ μ       ρ ρ   G   =    d  μ μ   G     d μ μ       {\displaystyle \rho _{\text{ref}}={\frac {d\mu _{\text{ref}}}{d\mu }}\quad \rho _{G}={\frac {d\mu _{G}}{d\mu }}}  ![{\displaystyle \rho _{\text{ref}}={\frac {d\mu _{\text{ref}}}{d\mu }}\quad \rho _{G}={\frac {d\mu _{G}}{d\mu }}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/498e23c33acc8415de79f689dbeea2c073b57b92)
with      ρ ρ   ref   +  ρ ρ   G   = 1   {\displaystyle \rho _{\text{ref}}+\rho _{G}=1}  ![{\displaystyle \rho _{\text{ref}}+\rho _{G}=1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ab72e7aa08e9a98f1415a76cac3d988695aff194).

 

We then have

 

    L (  μ μ   G   ,  μ μ   D   ) := ∫ ∫  μ μ  ( d x )  [   ρ ρ   ref   ( x ) ln ⁡ ⁡  ( D ( x ) ) +  ρ ρ   G   ( x ) ln ⁡ ⁡  ( 1 − −  D ( x ) )  ]  .   {\displaystyle L(\mu _{G},\mu _{D}):=\int \mu (dx)\left[\rho _{\text{ref}}(x)\ln(D(x))+\rho _{G}(x)\ln(1-D(x))\right].}  ![{\displaystyle L(\mu _{G},\mu _{D}):=\int \mu (dx)\left[\rho _{\text{ref}}(x)\ln(D(x))+\rho _{G}(x)\ln(1-D(x))\right].}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3d89762c883725af3a4781671c0e33a4a9c5050d)

 

The integrand is just the negative [cross-entropy](./Cross-entropy) between two Bernoulli random variables with parameters      ρ ρ   ref   ( x )   {\displaystyle \rho _{\text{ref}}(x)}  ![{\displaystyle \rho _{\text{ref}}(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2c24183a1ea795eeb6f5738fb38c5c433f4692b7) and     D ( x )   {\displaystyle D(x)}  ![{\displaystyle D(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/be208da111170920787fb435ff586d2377b43cc5). We can write this as     − −  H (  ρ ρ   ref   ( x ) ) − −   D  K L   (  ρ ρ   ref   ( x ) ∥ ∥  D ( x ) )   {\displaystyle -H(\rho _{\text{ref}}(x))-D_{KL}(\rho _{\text{ref}}(x)\parallel D(x))}  ![{\displaystyle -H(\rho _{\text{ref}}(x))-D_{KL}(\rho _{\text{ref}}(x)\parallel D(x))}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9fcb8a5a6709b09fc5e67ac2a08c02db08d6f709), where     H   {\displaystyle H}  ![{\displaystyle H}](https://wikimedia.org/api/rest_v1/media/math/render/svg/75a9edddcca2f782014371f75dca39d7e13a9c1b) is the [binary entropy function](./Binary_entropy_function), so

 

    L (  μ μ   G   ,  μ μ   D   ) = − −  ∫ ∫  μ μ  ( d x ) ( H (  ρ ρ   ref   ( x ) ) +  D  K L   (  ρ ρ   ref   ( x ) ∥ ∥  D ( x ) ) ) .   {\displaystyle L(\mu _{G},\mu _{D})=-\int \mu (dx)(H(\rho _{\text{ref}}(x))+D_{KL}(\rho _{\text{ref}}(x)\parallel D(x))).}  ![{\displaystyle L(\mu _{G},\mu _{D})=-\int \mu (dx)(H(\rho _{\text{ref}}(x))+D_{KL}(\rho _{\text{ref}}(x)\parallel D(x))).}](https://wikimedia.org/api/rest_v1/media/math/render/svg/bdba9505b9bc7f993c50a7dad0ecda304423f27c)

 

This means that the optimal strategy for the discriminator is     D ( x ) =  ρ ρ   ref   ( x )   {\displaystyle D(x)=\rho _{\text{ref}}(x)}  ![{\displaystyle D(x)=\rho _{\text{ref}}(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6e93c4bc7c015371251dc55233307f48a857ad1d), with   
    L (  μ μ   G   ,  μ μ   D   ∗ ∗    ) = − −  ∫ ∫  μ μ  ( d x ) H (  ρ ρ   ref   ( x ) ) =  D  J S   (  μ μ   ref   ∥ ∥   μ μ   G   ) − −  2 ln ⁡ ⁡  2   {\displaystyle L(\mu _{G},\mu _{D}^{*})=-\int \mu (dx)H(\rho _{\text{ref}}(x))=D_{JS}(\mu _{\text{ref}}\parallel \mu _{G})-2\ln 2}  ![{\displaystyle L(\mu _{G},\mu _{D}^{*})=-\int \mu (dx)H(\rho _{\text{ref}}(x))=D_{JS}(\mu _{\text{ref}}\parallel \mu _{G})-2\ln 2}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f3f8db4253085401eac2874bee92788d383e5f92)

 

after routine calculation.

  

**Interpretation**: For any fixed generator strategy      μ μ   G     {\displaystyle \mu _{G}}  ![{\displaystyle \mu _{G}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/dda577f83b0f673b3c59652dfcd8c195b965030f), the optimal discriminator keeps track of the likelihood ratio between the reference distribution and the generator distribution:       D ( x )   1 − −  D ( x )    =    d  μ μ   ref     d  μ μ   G      ( x ) =     μ μ   ref   ( d x )    μ μ   G   ( d x )    ;  D ( x ) = σ σ  ( ln ⁡ ⁡   μ μ   ref   ( d x ) − −  ln ⁡ ⁡   μ μ   G   ( d x ) )   {\displaystyle {\frac {D(x)}{1-D(x)}}={\frac {d\mu _{\text{ref}}}{d\mu _{G}}}(x)={\frac {\mu _{\text{ref}}(dx)}{\mu _{G}(dx)}};\quad D(x)=\sigma (\ln \mu _{\text{ref}}(dx)-\ln \mu _{G}(dx))}  ![{\displaystyle {\frac {D(x)}{1-D(x)}}={\frac {d\mu _{\text{ref}}}{d\mu _{G}}}(x)={\frac {\mu _{\text{ref}}(dx)}{\mu _{G}(dx)}};\quad D(x)=\sigma (\ln \mu _{\text{ref}}(dx)-\ln \mu _{G}(dx))}](https://wikimedia.org/api/rest_v1/media/math/render/svg/912e087f37cd261a2117d553b66b788d75423160)where     σ σ    {\displaystyle \sigma }  ![{\displaystyle \sigma }](https://wikimedia.org/api/rest_v1/media/math/render/svg/59f59b7c3e6fdb1d0365a494b81fb9a696138c36) is the [logistic function](./Logistic_function).
In particular, if the prior probability for an image     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4) to come from the reference distribution is equal to       1 2     {\displaystyle {\frac {1}{2}}}  ![{\displaystyle {\frac {1}{2}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a11cfb2fdb143693b1daf78fcb5c11a023cb1c55), then     D ( x )   {\displaystyle D(x)}  ![{\displaystyle D(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/be208da111170920787fb435ff586d2377b43cc5) is just the posterior probability that     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4) came from the reference distribution:    D ( x ) = Pr ( x   came from reference distribution  ∣ ∣  x ) .   {\displaystyle D(x)=\Pr(x{\text{ came from reference distribution}}\mid x).}  ![{\displaystyle D(x)=\Pr(x{\text{ came from reference distribution}}\mid x).}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fbd4a6148a4be2debb7c126f60d9fae746f12a4e)

  

**Theorem** (the unique equilibrium point)—For any GAN game, there exists a pair     (     μ μ  ^ ^      D   ,     μ μ  ^ ^      G   )   {\displaystyle ({\hat {\mu }}_{D},{\hat {\mu }}_{G})}  ![{\displaystyle ({\hat {\mu }}_{D},{\hat {\mu }}_{G})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ac9ac97217a832bb60a5756d2e60f83e9fddf73e) that is both a sequential equilibrium and a Nash equilibrium:

 

         L (     μ μ  ^ ^      G   ,     μ μ  ^ ^      D   ) =  min   μ μ   G      max   μ μ   D     L (  μ μ   G   ,  μ μ   D   ) =    max   μ μ   D      min   μ μ   G     L (  μ μ   G   ,  μ μ   D   ) = − −  2 ln ⁡ ⁡  2          μ μ  ^ ^      D   ∈ ∈  arg ⁡ ⁡   max   μ μ   D      min   μ μ   G     L (  μ μ   G   ,  μ μ   D   ) ,        μ μ  ^ ^      G   ∈ ∈  arg ⁡ ⁡   min   μ μ   G      max   μ μ   D     L (  μ μ   G   ,  μ μ   D   )          μ μ  ^ ^      D   ∈ ∈  arg ⁡ ⁡   max   μ μ   D     L (     μ μ  ^ ^      G   ,  μ μ   D   ) ,        μ μ  ^ ^      G   ∈ ∈  arg ⁡ ⁡   min   μ μ   G     L (  μ μ   G   ,     μ μ  ^ ^      D   )      ∀ ∀  x ∈ ∈  Ω Ω  ,     μ μ  ^ ^      D   ( x ) =  δ δ    1 2    ,        μ μ  ^ ^      G   =  μ μ   ref         {\displaystyle {\begin{aligned}&L({\hat {\mu }}_{G},{\hat {\mu }}_{D})=\min _{\mu _{G}}\max _{\mu _{D}}L(\mu _{G},\mu _{D})=&\max _{\mu _{D}}\min _{\mu _{G}}L(\mu _{G},\mu _{D})=-2\ln 2\\[6pt]&{\hat {\mu }}_{D}\in \arg \max _{\mu _{D}}\min _{\mu _{G}}L(\mu _{G},\mu _{D}),&\quad {\hat {\mu }}_{G}\in \arg \min _{\mu _{G}}\max _{\mu _{D}}L(\mu _{G},\mu _{D})\\[6pt]&{\hat {\mu }}_{D}\in \arg \max _{\mu _{D}}L({\hat {\mu }}_{G},\mu _{D}),&\quad {\hat {\mu }}_{G}\in \arg \min _{\mu _{G}}L(\mu _{G},{\hat {\mu }}_{D})\\[6pt]&\forall x\in \Omega ,{\hat {\mu }}_{D}(x)=\delta _{\frac {1}{2}},&\quad {\hat {\mu }}_{G}=\mu _{\text{ref}}\end{aligned}}}  ![{\displaystyle {\begin{aligned}&L({\hat {\mu }}_{G},{\hat {\mu }}_{D})=\min _{\mu _{G}}\max _{\mu _{D}}L(\mu _{G},\mu _{D})=&\max _{\mu _{D}}\min _{\mu _{G}}L(\mu _{G},\mu _{D})=-2\ln 2\\[6pt]&{\hat {\mu }}_{D}\in \arg \max _{\mu _{D}}\min _{\mu _{G}}L(\mu _{G},\mu _{D}),&\quad {\hat {\mu }}_{G}\in \arg \min _{\mu _{G}}\max _{\mu _{D}}L(\mu _{G},\mu _{D})\\[6pt]&{\hat {\mu }}_{D}\in \arg \max _{\mu _{D}}L({\hat {\mu }}_{G},\mu _{D}),&\quad {\hat {\mu }}_{G}\in \arg \min _{\mu _{G}}L(\mu _{G},{\hat {\mu }}_{D})\\[6pt]&\forall x\in \Omega ,{\hat {\mu }}_{D}(x)=\delta _{\frac {1}{2}},&\quad {\hat {\mu }}_{G}=\mu _{\text{ref}}\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5424defe94c1d2065643a2a789670aefb0a99d33)

 

That is, the generator perfectly mimics the reference, and the discriminator outputs       1 2     {\displaystyle {\frac {1}{2}}}  ![{\displaystyle {\frac {1}{2}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a11cfb2fdb143693b1daf78fcb5c11a023cb1c55) deterministically on all inputs.

  **Proof** 

From the previous proposition,

 

    arg ⁡ ⁡   min   μ μ   G      max   μ μ   D     L (  μ μ   G   ,  μ μ   D   ) =  μ μ   ref   ;   min   μ μ   G      max   μ μ   D     L (  μ μ   G   ,  μ μ   D   ) = − −  2 ln ⁡ ⁡  2.   {\displaystyle \arg \min _{\mu _{G}}\max _{\mu _{D}}L(\mu _{G},\mu _{D})=\mu _{\text{ref}};\quad \min _{\mu _{G}}\max _{\mu _{D}}L(\mu _{G},\mu _{D})=-2\ln 2.}  ![{\displaystyle \arg \min _{\mu _{G}}\max _{\mu _{D}}L(\mu _{G},\mu _{D})=\mu _{\text{ref}};\quad \min _{\mu _{G}}\max _{\mu _{D}}L(\mu _{G},\mu _{D})=-2\ln 2.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/162cb63a68a77df367a773d14f9c2368dbbfa17e)

 

For any fixed discriminator strategy      μ μ   D     {\displaystyle \mu _{D}}  ![{\displaystyle \mu _{D}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/72eb88f5dfff02030f9f7e820387548e6d3675db), any      μ μ   G     {\displaystyle \mu _{G}}  ![{\displaystyle \mu _{G}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/dda577f83b0f673b3c59652dfcd8c195b965030f) concentrated on the set

 

    { x ∣ ∣   E  y ∼ ∼   μ μ   D   ( x )   ⁡ ⁡  [ ln ⁡ ⁡  ( 1 − −  y ) ] =  inf  x    E  y ∼ ∼   μ μ   D   ( x )   ⁡ ⁡  [ ln ⁡ ⁡  ( 1 − −  y ) ] }   {\displaystyle \{x\mid \operatorname {E} _{y\sim \mu _{D}(x)}[\ln(1-y)]=\inf _{x}\operatorname {E} _{y\sim \mu _{D}(x)}[\ln(1-y)]\}}  ![{\displaystyle \{x\mid \operatorname {E} _{y\sim \mu _{D}(x)}[\ln(1-y)]=\inf _{x}\operatorname {E} _{y\sim \mu _{D}(x)}[\ln(1-y)]\}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2cf7cd23c4a4db6f757e07f73d4f0c6d61189ce1)
is an optimal strategy for the generator. Thus,

 

    arg ⁡ ⁡   max   μ μ   D      min   μ μ   G     L (  μ μ   G   ,  μ μ   D   ) = arg ⁡ ⁡   max   μ μ   D      E  x ∼ ∼   μ μ   ref   , y ∼ ∼   μ μ   D   ( x )   ⁡ ⁡  [ ln ⁡ ⁡  y ] +  inf  x    E  y ∼ ∼   μ μ   D   ( x )   ⁡ ⁡  [ ln ⁡ ⁡  ( 1 − −  y ) ] .   {\displaystyle \arg \max _{\mu _{D}}\min _{\mu _{G}}L(\mu _{G},\mu _{D})=\arg \max _{\mu _{D}}\operatorname {E} _{x\sim \mu _{\text{ref}},y\sim \mu _{D}(x)}[\ln y]+\inf _{x}\operatorname {E} _{y\sim \mu _{D}(x)}[\ln(1-y)].}  ![{\displaystyle \arg \max _{\mu _{D}}\min _{\mu _{G}}L(\mu _{G},\mu _{D})=\arg \max _{\mu _{D}}\operatorname {E} _{x\sim \mu _{\text{ref}},y\sim \mu _{D}(x)}[\ln y]+\inf _{x}\operatorname {E} _{y\sim \mu _{D}(x)}[\ln(1-y)].}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9d9fd6d2d2bed77978a32a70f0d3a003776ffa7f)

 

By Jensen's inequality, the discriminator can only improve by adopting the deterministic strategy of always playing     D ( x ) =  E  y ∼ ∼   μ μ   D   ( x )   ⁡ ⁡  [ y ]   {\displaystyle D(x)=\operatorname {E} _{y\sim \mu _{D}(x)}[y]}  ![{\displaystyle D(x)=\operatorname {E} _{y\sim \mu _{D}(x)}[y]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e59b025f251fffa8f05275b28fafb45dff6aa879). Therefore,

 

    arg ⁡ ⁡   max   μ μ   D      min   μ μ   G     L (  μ μ   G   ,  μ μ   D   ) = arg ⁡ ⁡   max  D    E  x ∼ ∼   μ μ   ref     ⁡ ⁡  [ ln ⁡ ⁡  D ( x ) ] +  inf  x   ln ⁡ ⁡  ( 1 − −  D ( x ) )   {\displaystyle \arg \max _{\mu _{D}}\min _{\mu _{G}}L(\mu _{G},\mu _{D})=\arg \max _{D}\operatorname {E} _{x\sim \mu _{\text{ref}}}[\ln D(x)]+\inf _{x}\ln(1-D(x))}  ![{\displaystyle \arg \max _{\mu _{D}}\min _{\mu _{G}}L(\mu _{G},\mu _{D})=\arg \max _{D}\operatorname {E} _{x\sim \mu _{\text{ref}}}[\ln D(x)]+\inf _{x}\ln(1-D(x))}](https://wikimedia.org/api/rest_v1/media/math/render/svg/43074b8f1f4bd64ca524f6dcec8ccc11ed0c7efd)

 

By Jensen's inequality,

 

         ln ⁡ ⁡   E  x ∼ ∼   μ μ   ref     ⁡ ⁡  [ D ( x ) ] +  inf  x   ln ⁡ ⁡  ( 1 − −  D ( x ) )     =     ln ⁡ ⁡   E  x ∼ ∼   μ μ   ref     ⁡ ⁡  [ D ( x ) ] + ln ⁡ ⁡  ( 1 − −   sup  x   D ( x ) )     =     ln ⁡ ⁡  [  E  x ∼ ∼   μ μ   ref     ⁡ ⁡  [ D ( x ) ] ( 1 − −   sup  x   D ( x ) ) ] ≤ ≤  ln ⁡ ⁡  [  sup  x   D ( x ) ) ( 1 − −   sup  x   D ( x ) ) ] ≤ ≤  ln ⁡ ⁡    1 4   ,       {\displaystyle {\begin{aligned}&\ln \operatorname {E} _{x\sim \mu _{\text{ref}}}[D(x)]+\inf _{x}\ln(1-D(x))\\[6pt]={}&\ln \operatorname {E} _{x\sim \mu _{\text{ref}}}[D(x)]+\ln(1-\sup _{x}D(x))\\[6pt]={}&\ln[\operatorname {E} _{x\sim \mu _{\text{ref}}}[D(x)](1-\sup _{x}D(x))]\leq \ln[\sup _{x}D(x))(1-\sup _{x}D(x))]\leq \ln {\frac {1}{4}},\end{aligned}}}  ![{\displaystyle {\begin{aligned}&\ln \operatorname {E} _{x\sim \mu _{\text{ref}}}[D(x)]+\inf _{x}\ln(1-D(x))\\[6pt]={}&\ln \operatorname {E} _{x\sim \mu _{\text{ref}}}[D(x)]+\ln(1-\sup _{x}D(x))\\[6pt]={}&\ln[\operatorname {E} _{x\sim \mu _{\text{ref}}}[D(x)](1-\sup _{x}D(x))]\leq \ln[\sup _{x}D(x))(1-\sup _{x}D(x))]\leq \ln {\frac {1}{4}},\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/906e0c7cdd6490755c48080b0a2d3129d88afbcd)

 

with equality if     D ( x ) =   1 2     {\displaystyle D(x)={\frac {1}{2}}}  ![{\displaystyle D(x)={\frac {1}{2}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0b973611b59fecbac4f096cae1a652716edb8133), so

 

    ∀ ∀  x ∈ ∈  Ω Ω  ,     μ μ  ^ ^      D   ( x ) =  δ δ    1 2    ;   max   μ μ   D      min   μ μ   G     L (  μ μ   G   ,  μ μ   D   ) = − −  2 ln ⁡ ⁡  2.   {\displaystyle \forall x\in \Omega ,{\hat {\mu }}_{D}(x)=\delta _{\frac {1}{2}};\quad \max _{\mu _{D}}\min _{\mu _{G}}L(\mu _{G},\mu _{D})=-2\ln 2.}  ![{\displaystyle \forall x\in \Omega ,{\hat {\mu }}_{D}(x)=\delta _{\frac {1}{2}};\quad \max _{\mu _{D}}\min _{\mu _{G}}L(\mu _{G},\mu _{D})=-2\ln 2.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8f2daa485f652357ef90393d0a20fbea122e6842)

 

Finally, to check that this is a Nash equilibrium, note that when      μ μ   G   =  μ μ   ref     {\displaystyle \mu _{G}=\mu _{\text{ref}}}  ![{\displaystyle \mu _{G}=\mu _{\text{ref}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c987d9732bee595e0ffd791b4133c824d9661825), we have

 

    L (  μ μ   G   ,  μ μ   D   ) :=  E  x ∼ ∼   μ μ   ref   , y ∼ ∼   μ μ   D   ( x )   ⁡ ⁡  [ ln ⁡ ⁡  ( y ( 1 − −  y ) ) ]   {\displaystyle L(\mu _{G},\mu _{D}):=\operatorname {E} _{x\sim \mu _{\text{ref}},y\sim \mu _{D}(x)}[\ln(y(1-y))]}  ![{\displaystyle L(\mu _{G},\mu _{D}):=\operatorname {E} _{x\sim \mu _{\text{ref}},y\sim \mu _{D}(x)}[\ln(y(1-y))]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/08127c83475a214c7db542905d70831971cdacbb)
which is always maximized by     y =   1 2     {\displaystyle y={\frac {1}{2}}}  ![{\displaystyle y={\frac {1}{2}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/52dc902fc1d3a9d6137bfe986703bb9a2a99cffd).

 

When     ∀ ∀  x ∈ ∈  Ω Ω  ,  μ μ   D   ( x ) =  δ δ    1 2      {\displaystyle \forall x\in \Omega ,\mu _{D}(x)=\delta _{\frac {1}{2}}}  ![{\displaystyle \forall x\in \Omega ,\mu _{D}(x)=\delta _{\frac {1}{2}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7ecabdb51eb106d620377f80b5680dcb9fb7d042), any strategy is optimal for the generator.

  


