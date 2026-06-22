---
source: sources/wiki-Generative_adversarial_network.md
source_url: https://en.wikipedia.org/wiki/Generative_adversarial_network
chunk: 3/7
---

## Training and evaluating GAN

 

### Training

 

#### Unstable convergence

 

While the GAN game has a unique global equilibrium point when both the generator and discriminator have access to their entire strategy sets, the equilibrium is no longer guaranteed when they have a restricted strategy set.[[12]](./Generative_adversarial_network#cite_note-:2-12)

 

In practice, the generator has access only to measures of form      μ μ   Z   ∘ ∘   G  θ θ    − −  1     {\displaystyle \mu _{Z}\circ G_{\theta }^{-1}}  ![{\displaystyle \mu _{Z}\circ G_{\theta }^{-1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f04987cbb022c086a8f3196e1236616e9d692de9), where      G  θ θ      {\displaystyle G_{\theta }}  ![{\displaystyle G_{\theta }}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ffa3c7733aa7f041e39b270a656112f132a95fb3) is a function computed by a neural network with parameters     θ θ    {\displaystyle \theta }  ![{\displaystyle \theta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/6e5ab2664b422d53eb0c7df3b87e1360d75ad9af), and      μ μ   Z     {\displaystyle \mu _{Z}}  ![{\displaystyle \mu _{Z}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4dfd7b88be4d0e36a21cb6d4a486bcaf0128a324) is an easily sampled distribution, such as the uniform or normal distribution. Similarly, the discriminator has access only to functions of form      D  ζ ζ      {\displaystyle D_{\zeta }}  ![{\displaystyle D_{\zeta }}](https://wikimedia.org/api/rest_v1/media/math/render/svg/eb2221422911a45f6c56c65806becf8a76d46f96), a function computed by a neural network with parameters     ζ ζ    {\displaystyle \zeta }  ![{\displaystyle \zeta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/d5c3916703cae7938143d38865f78f27faadd4ae). These restricted strategy sets take up a *vanishingly small proportion* of their entire strategy sets.[[13]](./Generative_adversarial_network#cite_note-:3-13)

 

Further, even if an equilibrium still exists, it can only be found by searching in the high-dimensional space of all possible neural network functions. The standard strategy of using [gradient descent](./Gradient_descent) to find the equilibrium often does not work for GAN, and often the game "collapses" into one of several failure modes. To improve the convergence stability, some training strategies start with an easier task, such as generating low-resolution images[[14]](./Generative_adversarial_network#cite_note-:1-14) or simple images (one object with uniform background),[[15]](./Generative_adversarial_network#cite_note-15) and gradually increase the difficulty of the task during training. This essentially translates to applying a curriculum learning scheme.[[16]](./Generative_adversarial_network#cite_note-16)

 

#### Mode collapse

 Main article: [Mode collapse](./Mode_collapse) 

GANs often suffer from **mode collapse** where they fail to generalize properly, missing entire modes from the input data. For example, a GAN trained on the [MNIST](./MNIST) dataset containing many samples of each digit might only generate pictures of digit 0. This was termed "the Helvetica scenario".[[1]](./Generative_adversarial_network#cite_note-GANnips-1)

 

A typical mechanism for mode collapse is the generator only generating one or a few of the likely values, or a very incomplete picture of the target distribution. As the discriminator is only trained to distinguish real from fake samples, it will correctly identify the generated samples as real, but no penalty is imposed on the GAN's ability to generate data that represents the full range of the target distribution.

 

Weak discriminators, for instance underparametrized ones, or ones trained too slow compared to the generator, may as well be unable to fully discriminate over the entire support of the distribution, and only become able to correctly discriminate a very incomplete part of the target distribution.

 

Some researchers perceive the root problem to be a weak discriminative network that fails to notice the pattern of omission, while others assign blame to a bad choice of [objective function](./Objective_function). Many solutions have been proposed, but it is still an open problem.[[17]](./Generative_adversarial_network#cite_note-17)[[18]](./Generative_adversarial_network#cite_note-18)

 

Even the state-of-the-art architecture, BigGAN (2019), could not avoid mode collapse. The authors resorted to "allowing collapse to occur at the later stages of training, by which time a model is sufficiently trained to achieve good results".[[19]](./Generative_adversarial_network#cite_note-:0-19)

 

#### Two time-scale update rule

 

The **two time-scale update rule (TTUR)** is proposed to make GAN convergence more stable by making the learning rate of the generator lower than that of the discriminator. They prove that when trained this way, GANs "converge, under mild assumptions to a stationary local Nash equilibrium".[[20]](./Generative_adversarial_network#cite_note-20) They further show that this property extends to the use of the Adam optimizer, which is commonly used in stochastic gradient descent.

 

It is important to note, however, that a local Nash equilibrium in no way signifies an absence of mode collapse - for instance, a GAN trained on MNIST collapsed to generating a single digit may satisfy the hypotheses of the paper, while still presenting mode collapse.

 

#### Vanishing gradient

 

Conversely, if the discriminator learns too fast compared to the generator, then the discriminator could almost perfectly distinguish      μ μ    G  θ θ      ,  μ μ   ref     {\displaystyle \mu _{G_{\theta }},\mu _{\text{ref}}}  ![{\displaystyle \mu _{G_{\theta }},\mu _{\text{ref}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/dbfb20b0979d23c6d22593c7af113b01402911a7). In such case, the generator      G  θ θ      {\displaystyle G_{\theta }}  ![{\displaystyle G_{\theta }}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ffa3c7733aa7f041e39b270a656112f132a95fb3) could be stuck with a very high loss no matter which direction it changes its     θ θ    {\displaystyle \theta }  ![{\displaystyle \theta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/6e5ab2664b422d53eb0c7df3b87e1360d75ad9af), meaning that the gradient      ∇ ∇   θ θ    L (  G  θ θ    ,  D  ζ ζ    )   {\displaystyle \nabla _{\theta }L(G_{\theta },D_{\zeta })}  ![{\displaystyle \nabla _{\theta }L(G_{\theta },D_{\zeta })}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f352a89b55badf2662e56a7531565f7452692664) would be close to zero. In such case, the generator cannot learn, a case of the [**vanishing gradient** problem](./Vanishing_gradient_problem).[[13]](./Generative_adversarial_network#cite_note-:3-13)

 

Intuitively speaking, the discriminator is too good, and since the generator cannot take any small step (only small steps are considered in gradient descent) to improve its payoff, it does not even try.

 

One important method for solving this problem is the [Wasserstein GAN](./Wasserstein_GAN).

 

### Evaluation

 

GANs are usually evaluated by [Inception score](./Inception_score) (IS), which measures how varied the generator's outputs are (as classified by an image classifier, usually [Inception-v3](./Inceptionv3)), or [Fréchet inception distance](./Fréchet_inception_distance) (FID), which measures how similar the generator's outputs are to a reference set (as classified by a learned image featurizer, such as Inception-v3 without its final layer). Many papers that propose new GAN architectures for image generation report how their architectures break the [state of the art](./State_of_the_art) on FID or IS.

 

Another evaluation method is the Learned Perceptual Image Patch Similarity (LPIPS), which starts with a learned image featurizer      f  θ θ    :  Image  → →    R   n     {\displaystyle f_{\theta }:{\text{Image}}\to \mathbb {R} ^{n}}  ![{\displaystyle f_{\theta }:{\text{Image}}\to \mathbb {R} ^{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/cb99bc553ef0aa2f8dfc0840c92373e0edce560f), and finetunes it by supervised learning on a set of     ( x ,  x ′  ,  p e r c e p t u a l   d i f f e r e n c e  ⁡ ⁡  ( x ,  x ′  ) )   {\displaystyle (x,x',\operatorname {perceptual~difference} (x,x'))}  ![{\displaystyle (x,x',\operatorname {perceptual~difference} (x,x'))}](https://wikimedia.org/api/rest_v1/media/math/render/svg/209193a4dd3a9151b3109ab5e55428174b3be525), where     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4) is an image,      x ′    {\displaystyle x'}  ![{\displaystyle x'}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0ac74959896052e160a5953102e4bc3850fe93b2) is a perturbed version of it, and      p e r c e p t u a l   d i f f e r e n c e  ⁡ ⁡  ( x ,  x ′  )   {\displaystyle \operatorname {perceptual~difference} (x,x')}  ![{\displaystyle \operatorname {perceptual~difference} (x,x')}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9403aa2a8a894495003e76d815d80f3752494a80) is how much they differ, as reported by human subjects. The model is finetuned so that it can approximate     ‖ ‖   f  θ θ    ( x ) − −   f  θ θ    (  x ′  ) ‖ ‖  ≈ ≈   p e r c e p t u a l   d i f f e r e n c e  ⁡ ⁡  ( x ,  x ′  )   {\displaystyle \|f_{\theta }(x)-f_{\theta }(x')\|\approx \operatorname {perceptual~difference} (x,x')}  ![{\displaystyle \|f_{\theta }(x)-f_{\theta }(x')\|\approx \operatorname {perceptual~difference} (x,x')}](https://wikimedia.org/api/rest_v1/media/math/render/svg/57ac4c9e74bf6c05ec55044665c54995878fe773). This finetuned model is then used to define     LPIPS ⁡ ⁡  ( x ,  x ′  ) := ‖ ‖   f  θ θ    ( x ) − −   f  θ θ    (  x ′  ) ‖ ‖    {\displaystyle \operatorname {LPIPS} (x,x'):=\|f_{\theta }(x)-f_{\theta }(x')\|}  ![{\displaystyle \operatorname {LPIPS} (x,x'):=\|f_{\theta }(x)-f_{\theta }(x')\|}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7a3b0d9e2b6ffa7195ff208e29c181b1d7cf1869).[[21]](./Generative_adversarial_network#cite_note-21)

 

Other evaluation methods are reviewed in.[[22]](./Generative_adversarial_network#cite_note-22)

 


