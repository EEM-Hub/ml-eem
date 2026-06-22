---
source: sources/wiki-Transformer_deep_learning_architecture.md
source_url: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)
chunk: 5/8
---

## Subsequent work

 

### Alternative activation functions

 

The original transformer uses [ReLU](./ReLU) [activation function](./Activation_function). Other activation functions were developed. The [Llama series](./Llama_(language_model)) and [PaLM](./PaLM) used SwiGLU;[[67]](./Transformer_(deep_learning)#cite_note-:14-69) both GPT-1 and BERT[[40]](./Transformer_(deep_learning)#cite_note-:03-42) used GELU.[[68]](./Transformer_(deep_learning)#cite_note-70)

 

Alternative activation functions are often used in combination with [Gated Linear Units](./Gated_Linear_Unit) in the feedforward module.[[67]](./Transformer_(deep_learning)#cite_note-:14-69)

 

### Alternative normalizations

 

The normalization used in the transformer can be different from LayerNorm. One example is [RMSNorm](./RMSNorm)[[69]](./Transformer_(deep_learning)#cite_note-71) which is used in the [Llama series](./Llama_(language_model)). Other examples include ScaleNorm[[70]](./Transformer_(deep_learning)#cite_note-:9-72) and FixNorm.[[70]](./Transformer_(deep_learning)#cite_note-:9-72)

 

### Alternative positional encodings

 

Transformers may use other positional encoding methods than sinusoidal.[[71]](./Transformer_(deep_learning)#cite_note-73)

 

The original transformer paper reported using a learned positional encoding,[[72]](./Transformer_(deep_learning)#cite_note-74) but finding it not superior to the sinusoidal one.[[1]](./Transformer_(deep_learning)#cite_note-2017_Attention_Is_All_You_Need-1) Later,[[73]](./Transformer_(deep_learning)#cite_note-75) found that causal masking itself provides enough signal to a transformer decoder that it can learn to implicitly perform absolute positional encoding without the positional encoding module.

 

#### RoPE

 

RoPE (rotary positional embedding),[[74]](./Transformer_(deep_learning)#cite_note-76) is best explained by considering a list of 2-dimensional vectors     [ (  x  1   ( 1 )   ,  x  1   ( 2 )   ) , (  x  2   ( 1 )   ,  x  2   ( 2 )   ) , (  x  3   ( 1 )   ,  x  3   ( 2 )   ) , . . . ]   {\displaystyle [(x_{1}^{(1)},x_{1}^{(2)}),(x_{2}^{(1)},x_{2}^{(2)}),(x_{3}^{(1)},x_{3}^{(2)}),...]}  ![{\displaystyle [(x_{1}^{(1)},x_{1}^{(2)}),(x_{2}^{(1)},x_{2}^{(2)}),(x_{3}^{(1)},x_{3}^{(2)}),...]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/08b00c812263b798fed7b345975d49dbebdfada5). Now pick some angle     θ θ    {\displaystyle \theta }  ![{\displaystyle \theta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/6e5ab2664b422d53eb0c7df3b87e1360d75ad9af). Then RoPE encoding is     RoPE    (    x  m   ( 1 )   ,  x  m   ( 2 )   , m   )   =   (    cos ⁡ ⁡  m θ θ    − −  sin ⁡ ⁡  m θ θ      sin ⁡ ⁡  m θ θ    cos ⁡ ⁡  m θ θ     )     (     x  m   ( 1 )        x  m   ( 2 )      )   =   (     x  m   ( 1 )   cos ⁡ ⁡  m θ θ  − −   x  m   ( 2 )   sin ⁡ ⁡  m θ θ       x  m   ( 2 )   cos ⁡ ⁡  m θ θ  +  x  m   ( 1 )   sin ⁡ ⁡  m θ θ     )     {\displaystyle {\text{RoPE}}{\big (}x_{m}^{(1)},x_{m}^{(2)},m{\big )}={\begin{pmatrix}\cos m\theta &-\sin m\theta \\\sin m\theta &\cos m\theta \end{pmatrix}}{\begin{pmatrix}x_{m}^{(1)}\\x_{m}^{(2)}\\\end{pmatrix}}={\begin{pmatrix}x_{m}^{(1)}\cos m\theta -x_{m}^{(2)}\sin m\theta \\x_{m}^{(2)}\cos m\theta +x_{m}^{(1)}\sin m\theta \\\end{pmatrix}}}  ![{\displaystyle {\text{RoPE}}{\big (}x_{m}^{(1)},x_{m}^{(2)},m{\big )}={\begin{pmatrix}\cos m\theta &-\sin m\theta \\\sin m\theta &\cos m\theta \end{pmatrix}}{\begin{pmatrix}x_{m}^{(1)}\\x_{m}^{(2)}\\\end{pmatrix}}={\begin{pmatrix}x_{m}^{(1)}\cos m\theta -x_{m}^{(2)}\sin m\theta \\x_{m}^{(2)}\cos m\theta +x_{m}^{(1)}\sin m\theta \\\end{pmatrix}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0a15ebe8d780e084275a5115ab1bd66867b2df86)Equivalently, if we write the 2-dimensional vectors as complex numbers      z  m   :=  x  m   ( 1 )   + i  x  m   ( 2 )     {\displaystyle z_{m}:=x_{m}^{(1)}+ix_{m}^{(2)}}  ![{\displaystyle z_{m}:=x_{m}^{(1)}+ix_{m}^{(2)}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ed57dd02fd5aafea96a4ee28322e10ca6883249f), then RoPE encoding is just multiplication by an angle:     RoPE    (    z  m   , m   )   =  e  i m θ θ     z  m     {\displaystyle {\text{RoPE}}{\big (}z_{m},m{\big )}=e^{im\theta }z_{m}}  ![{\displaystyle {\text{RoPE}}{\big (}z_{m},m{\big )}=e^{im\theta }z_{m}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/de13aa67381dcfbf189a2beca91c14aa914c1d62)For a list of     2 n   {\displaystyle 2n}  ![{\displaystyle 2n}](https://wikimedia.org/api/rest_v1/media/math/render/svg/134afa8ff09fdddd24b06f289e92e3a045092bd1)-dimensional vectors, a RoPE encoder is defined by a sequence of angles      θ θ   ( 1 )   , . . . ,  θ θ   ( n )     {\displaystyle \theta ^{(1)},...,\theta ^{(n)}}  ![{\displaystyle \theta ^{(1)},...,\theta ^{(n)}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/cf7ced81707daa22c51c4294a84b3f9d14d30eef). Then the RoPE encoding is applied to each pair of coordinates.

 

The benefit of RoPE is that the dot-product between two vectors depends on their relative location only:     RoPE    (   x , m    )    T    RoPE    (   y , n   )   =  RoPE    (   x , m + k    )    T    RoPE    (   y , n + k   )     {\displaystyle {\text{RoPE}}{\big (}x,m{\big )}^{T}{\text{RoPE}}{\big (}y,n{\big )}={\text{RoPE}}{\big (}x,m+k{\big )}^{T}{\text{RoPE}}{\big (}y,n+k{\big )}}  ![{\displaystyle {\text{RoPE}}{\big (}x,m{\big )}^{T}{\text{RoPE}}{\big (}y,n{\big )}={\text{RoPE}}{\big (}x,m+k{\big )}^{T}{\text{RoPE}}{\big (}y,n+k{\big )}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e31c0d3482350f84642a7ec384650ab781eda79d)
for any integer     k   {\displaystyle k}  ![{\displaystyle k}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c3c9a2c7b599b37105512c5d570edc034056dd40).

 

#### ALiBi

 

ALiBi (Attention with Linear Biases)[[75]](./Transformer_(deep_learning)#cite_note-77) is not a *replacement* for the positional encoder on the original transformer. Instead, it is an *additional* positional encoder that is directly plugged into the attention mechanism. Specifically, the ALiBi attention mechanism is         Attention  ( Q , K , V ) =  softmax   (     Q  K   T       d  k      + s B  )  V       {\displaystyle {\begin{aligned}{\text{Attention}}(Q,K,V)={\text{softmax}}\left({\frac {QK^{\mathrm {T} }}{\sqrt {d_{k}}}}+sB\right)V\end{aligned}}}  ![{\displaystyle {\begin{aligned}{\text{Attention}}(Q,K,V)={\text{softmax}}\left({\frac {QK^{\mathrm {T} }}{\sqrt {d_{k}}}}+sB\right)V\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/bffa099b8703700a9c48178b2158edb858fc58b9)Here,     s   {\displaystyle s}  ![{\displaystyle s}](https://wikimedia.org/api/rest_v1/media/math/render/svg/01d131dfd7673938b947072a13a9744fe997e632) is a real number ("scalar"), and     B   {\displaystyle B}  ![{\displaystyle B}](https://wikimedia.org/api/rest_v1/media/math/render/svg/47136aad860d145f75f3eed3022df827cee94d7a) is the *linear bias* matrix defined by    B =   (    0   1   2   3   ⋯ ⋯      − −  1   0   1   2   ⋯ ⋯      − −  2   − −  1   0   1   ⋯ ⋯      − −  3   − −  2   − −  1   0   ⋯ ⋯      ⋮ ⋮    ⋮ ⋮    ⋮ ⋮    ⋮ ⋮    ⋱ ⋱     )     {\displaystyle B={\begin{pmatrix}0&1&2&3&\cdots \\-1&0&1&2&\cdots \\-2&-1&0&1&\cdots \\-3&-2&-1&0&\cdots \\\vdots &\vdots &\vdots &\vdots &\ddots \\\end{pmatrix}}}  ![{\displaystyle B={\begin{pmatrix}0&1&2&3&\cdots \\-1&0&1&2&\cdots \\-2&-1&0&1&\cdots \\-3&-2&-1&0&\cdots \\\vdots &\vdots &\vdots &\vdots &\ddots \\\end{pmatrix}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/12fa6edca20501fef7d70c74860db1e2fc70068a)in other words,      B  i , j   = j − −  i   {\displaystyle B_{i,j}=j-i}  ![{\displaystyle B_{i,j}=j-i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1be4dbbb894617d7ae4dd3118e0be60cd018aec7). The idea being that the linear bias matrix is a softened mask. Just as     0   {\displaystyle 0}  ![{\displaystyle 0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2aae8864a3c1fec9585261791a809ddec1489950) represent full attention paid, and     − −  ∞ ∞    {\displaystyle -\infty }  ![{\displaystyle -\infty }](https://wikimedia.org/api/rest_v1/media/math/render/svg/ca2608c4b5fd3bffc73585f8c67e379b4e99b6f1) represents no attention paid, the linear bias matrix increases attention paid in one direction and decreases attention paid in the other direction.

 

ALiBi allows pretraining on short context windows, then fine-tuning on longer context windows. Since it is directly plugged into the attention mechanism, it can be combined with any positional encoder that is plugged into the "bottom" of the entire network (which is where the sinusoidal encoder on the original transformer, as well as RoPE and many others, are located).

 

#### Relative Position Encodings

 

Relative Position Encodings[[76]](./Transformer_(deep_learning)#cite_note-78) is similar to ALiBi, but more generic:         Attention  ( Q , K , V ) =  softmax   (     Q  K   T       d  k      + B  )  V       {\displaystyle {\begin{aligned}{\text{Attention}}(Q,K,V)={\text{softmax}}\left({\frac {QK^{\mathrm {T} }}{\sqrt {d_{k}}}}+B\right)V\end{aligned}}}  ![{\displaystyle {\begin{aligned}{\text{Attention}}(Q,K,V)={\text{softmax}}\left({\frac {QK^{\mathrm {T} }}{\sqrt {d_{k}}}}+B\right)V\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f15684ca2a0019fc697c04d62cea397b8f47dbb2)where     B   {\displaystyle B}  ![{\displaystyle B}](https://wikimedia.org/api/rest_v1/media/math/render/svg/47136aad860d145f75f3eed3022df827cee94d7a) is a [Toeplitz matrix](./Toeplitz_matrix), that is,      B  i , j   =  B   i ′  ,  j ′      {\displaystyle B_{i,j}=B_{i',j'}}  ![{\displaystyle B_{i,j}=B_{i',j'}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fe7155b71c5f6c6f726c49a3c7f3a9047414171d) whenever     i − −  j =  i ′  − −   j ′    {\displaystyle i-j=i'-j'}  ![{\displaystyle i-j=i'-j'}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a421740142156ea5322442d9d58cf47412bd30bf). This is contrasted with the original sinusoidal positional encoding, which is an "absolute positional encoding".[[77]](./Transformer_(deep_learning)#cite_note-79)

 

### Efficient implementation

 

The transformer model has been implemented in standard deep learning [frameworks](./Framework_(computer_science)) such as [TensorFlow](./TensorFlow) and [PyTorch](./PyTorch). *Transformers* is a library produced by [Hugging Face](./Hugging_Face) that supplies transformer-based architectures and pretrained models.[[14]](./Transformer_(deep_learning)#cite_note-wolf2020-14)

 

#### KV caching

 

When an autoregressive transformer is used for inference, such as generating text, the query vector is different at each step, but the already-computed key and value vectors are always the same. The **KV caching** method saves the computed key and value vectors at each attention block, so that they are not recomputed at each new token. [PagedAttention](./PagedAttention) applies [memory paging](./Memory_paging) to KV caching.[[78]](./Transformer_(deep_learning)#cite_note-80)[[79]](./Transformer_(deep_learning)#cite_note-81)[[80]](./Transformer_(deep_learning)#cite_note-82)

 

If a transformer is used with a baked-in prompt, such as ["You are a customer support agent..."], then the key and value vectors can be computed for the prompt, and saved on disk. The saving in compute is significant when the model is used for many short real-time interactions, such as in online chatbots.

 

In general, when a user uses an autoregressive transformer to generate a continuation to a sequence of tokens, the model would first perform a forward-pass on this sequence, whereby the KV caches over this sequence are computed. This is called **prefilling**. [Hyperscalers](./Hyperscale_computing) serving large Transformer models may use **disaggregated inference**, wherein prefilling and decoding are performed on separately specialized hardware.[[81]](./Transformer_(deep_learning)#cite_note-83)

 

#### FlashAttention

 

FlashAttention[[82]](./Transformer_(deep_learning)#cite_note-84) is an algorithm that implements the transformer attention mechanism efficiently on a [GPU](./Graphics_processing_unit). It is a communication-avoiding algorithm that performs [matrix multiplications in blocks](./Block_matrix#Block_matrix_operations), such that each block fits within the [cache](./Cache_(computing)) of a GPU, and by careful management of the blocks it minimizes data copying between GPU caches (as data movement is slow). See the page on [softmax](./Softmax_function#Numerical_algorithms) for details.

 

An improved version, FlashAttention-2,[[83]](./Transformer_(deep_learning)#cite_note-85)[[84]](./Transformer_(deep_learning)#cite_note-86)[[85]](./Transformer_(deep_learning)#cite_note-87) was developed to cater to the rising demand for language models capable of handling longer context lengths. It offers enhancements in work partitioning and parallelism, enabling it to achieve up to 230 TFLOPs/s on [A100](./Nvidia_A100) GPUs ([FP16](./FP16)/[BF16](./BF16)), a 2x speed increase over the original FlashAttention.

 

Key advancements in FlashAttention-2 include the reduction of non-matmul FLOPs, improved parallelism over the sequence length dimension, better work partitioning between GPU warps, and added support for head dimensions up to 256 and multi-query attention (MQA) and grouped-query attention (GQA).[[86]](./Transformer_(deep_learning)#cite_note-88)

 

Benchmarks revealed FlashAttention-2 to be up to 2x faster than FlashAttention and up to 9x faster than a standard attention implementation in PyTorch. Future developments include optimization for new hardware like [H100](./Nvidia_H100) GPUs and new data types like [FP8](./Floating-point_arithmetic).

 

FlashAttention-4 focuses on [pipelining](./Pipeline_(Unix)) to increase instruction [throughput](./Network_throughput), and was developed to perform particularly well on [Blackwell GPUs](./Blackwell_(microarchitecture)).[[87]](./Transformer_(deep_learning)#cite_note-89)

 

#### Multi-Query Attention

 

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/8/83/DeepSeek_KV_cache_comparison_between_MHA%2C_GQA%2C_MQA%2C_MLA.svg/250px-DeepSeek_KV_cache_comparison_between_MHA%2C_GQA%2C_MQA%2C_MLA.svg.png)](./File:DeepSeek_KV_cache_comparison_between_MHA,_GQA,_MQA,_MLA.svg)Comparison between several different forms of attention mechanism and the amount of KV caching necessary for each 

Multi-Query Attention changes the Multihead Attention mechanism.[[88]](./Transformer_(deep_learning)#cite_note-90) Whereas normally,

 

     MultiheadAttention  ( Q , K , V ) =   Concat   i ∈ ∈  [  n  heads   ]    (   Attention  ( X  W  i   Q   , X  W  i   K   , X  W  i   V   )  )   W  O     {\displaystyle {\text{MultiheadAttention}}(Q,K,V)={\text{Concat}}_{i\in [n_{\text{heads}}]}\left({\text{Attention}}(XW_{i}^{Q},XW_{i}^{K},XW_{i}^{V})\right)W^{O}}  ![{\displaystyle {\text{MultiheadAttention}}(Q,K,V)={\text{Concat}}_{i\in [n_{\text{heads}}]}\left({\text{Attention}}(XW_{i}^{Q},XW_{i}^{K},XW_{i}^{V})\right)W^{O}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/02afa45e87322c7c0b4919c8ba934861b54fc06e)with Multi-Query Attention, there is just one      W  K   ,  W  V     {\displaystyle W^{K},W^{V}}  ![{\displaystyle W^{K},W^{V}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d4e0456602ee9f229ab1286d5f486eb5f71332ae), thus:

 

     MultiQueryAttention  ( Q , K , V ) =   Concat   i ∈ ∈  [  n  heads   ]    (   Attention  ( X  W  i   Q   , X  W  K   , X  W  V   )  )   W  O     {\displaystyle {\text{MultiQueryAttention}}(Q,K,V)={\text{Concat}}_{i\in [n_{\text{heads}}]}\left({\text{Attention}}(XW_{i}^{Q},XW^{K},XW^{V})\right)W^{O}}  ![{\displaystyle {\text{MultiQueryAttention}}(Q,K,V)={\text{Concat}}_{i\in [n_{\text{heads}}]}\left({\text{Attention}}(XW_{i}^{Q},XW^{K},XW^{V})\right)W^{O}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2eb0939568b3364f0c300eca805463355ce6d554)

 

This has a neutral effect on model quality and training speed, but increases inference speed.

 

More generally, grouped-query attention (GQA) partitions attention heads into groups, each of which shares the key-value pair. MQA is GQA with one group, while standard Multihead Attention is GQA with the maximal number of groups.[[89]](./Transformer_(deep_learning)#cite_note-91)

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/2/20/DeepSeek_MoE_and_MLA_%28DeepSeek-V2%29.svg/250px-DeepSeek_MoE_and_MLA_%28DeepSeek-V2%29.svg.png)](./File:DeepSeek_MoE_and_MLA_(DeepSeek-V2).svg)The architecture of V2, showing both MLA and a variant of [mixture of experts](./Mixture_of_experts)[[90]](./Transformer_(deep_learning)#cite_note-:73-92): Figure 2  

Multihead Latent Attention (MLA) is a [low-rank approximation](./Low-rank_approximation) to standard MHA. Specifically, each hidden vector, before entering the attention mechanism, is first projected to two low-dimensional spaces ("latent space"), one for query and one for key-value (KV vector). This design minimizes the KV cache, as only the low-dimensional KV vector needs to be cached.[[90]](./Transformer_(deep_learning)#cite_note-:73-92)

 

#### Speculative decoding

 Main article: [Speculative decoding](./Speculative_decoding) 

Speculative decoding[[91]](./Transformer_(deep_learning)#cite_note-:2-93)[[92]](./Transformer_(deep_learning)#cite_note-94) is a method to accelerate token decoding. Similarly to [speculative execution](./Speculative_execution) in CPUs, future tokens are computed quickly, then verified. If the quickly computed tokens are incorrect, they are discarded and computed slowly.

 

The key factor in speculative decoding is that a transformer decoder can verify faster than it can decode, in the following sense.

 

Suppose we have two transformer models like GPT-3 and GPT-3-small, both with a context window size of 512. To generate an entire context window autoregressively with greedy decoding with GPT-3, it must be run for 512 times, each time generating a token      x  1   ,  x  2   , . . . ,  x  512     {\displaystyle x_{1},x_{2},...,x_{512}}  ![{\displaystyle x_{1},x_{2},...,x_{512}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fd0b4677bb81d2d8af40d42edf0c42d0b2eaa34e), taking time     512  T  GPT-3     {\displaystyle 512T_{\text{GPT-3}}}  ![{\displaystyle 512T_{\text{GPT-3}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/68cfccf622ab2cc50786ad9bcdc7ed5ab1dff812). However, if we had some educated guess for the values of these tokens, we could verify all of them in parallel, in one run of the model, by checking that each      x  t     {\displaystyle x_{t}}  ![{\displaystyle x_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f279a30bc8eabc788f3fe81c9cfb674e72e858db) is indeed the token with the largest log-likelihood in the     t   {\displaystyle t}  ![{\displaystyle t}](https://wikimedia.org/api/rest_v1/media/math/render/svg/65658b7b223af9e1acc877d848888ecdb4466560)-th output.

 

In speculative decoding, a smaller model or some other simple heuristic is used to generate a few speculative tokens that are subsequently verified by the larger model. For example, suppose we use GPT-3-small to generate four speculative tokens:         x ~ ~      1   ,     x ~ ~      2   ,     x ~ ~      3   ,     x ~ ~      4     {\displaystyle {\tilde {x}}_{1},{\tilde {x}}_{2},{\tilde {x}}_{3},{\tilde {x}}_{4}}  ![{\displaystyle {\tilde {x}}_{1},{\tilde {x}}_{2},{\tilde {x}}_{3},{\tilde {x}}_{4}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d8db060dad8f25abc632d0c847694d10943fefc0). This only takes     4  T  GPT-3-small     {\displaystyle 4T_{\text{GPT-3-small}}}  ![{\displaystyle 4T_{\text{GPT-3-small}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f27766b2e3974a6b36c1a34989690d453598eedd). These tokens are then run through the larger GPT-3 in one go. Suppose that         x ~ ~      1     {\displaystyle {\tilde {x}}_{1}}  ![{\displaystyle {\tilde {x}}_{1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/bd6433a2811e7287025f60332718fe31d72003a7) and         x ~ ~      2     {\displaystyle {\tilde {x}}_{2}}  ![{\displaystyle {\tilde {x}}_{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e6c8b294488a1ddcc0380c8a8cb75b3410fe7ede) are verified by GPT-3 as what it would have picked, then those are kept, but         x ~ ~      3     {\displaystyle {\tilde {x}}_{3}}  ![{\displaystyle {\tilde {x}}_{3}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2de3175aa437329b2c5b3a3fc1167be15882b81d) is not, so         x ~ ~      3   ,     x ~ ~      4     {\displaystyle {\tilde {x}}_{3},{\tilde {x}}_{4}}  ![{\displaystyle {\tilde {x}}_{3},{\tilde {x}}_{4}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fa75c04dd4b830a3f8686e81cc88136365640db8) are discarded, and GPT-3 is run on those. This would take     4  T  GPT-3-small   + 3  T  GPT-3     {\displaystyle 4T_{\text{GPT-3-small}}+3T_{\text{GPT-3}}}  ![{\displaystyle 4T_{\text{GPT-3-small}}+3T_{\text{GPT-3}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4c60c2a824e236297f444a500e8c324540dfd24d), which might be shorter than     4  T  GPT-3     {\displaystyle 4T_{\text{GPT-3}}}  ![{\displaystyle 4T_{\text{GPT-3}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e2bf07e1b17f4de6fb7480487563b3a31613dfd7).

 

For non-greedy decoding, similar ideas apply, except the speculative tokens are accepted or rejected stochastically, in a way that guarantees the final output distribution is the same as if speculative decoding was not used.[[91]](./Transformer_(deep_learning)#cite_note-:2-93)[[93]](./Transformer_(deep_learning)#cite_note-95)

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/0/0b/Multi-Token_Prediction_%28DeepSeek%29_01.svg/250px-Multi-Token_Prediction_%28DeepSeek%29_01.svg.png)](./File:Multi-Token_Prediction_(DeepSeek)_01.svg)Multi-token prediction 

In Multi-Token Prediction, a single forward pass creates a final embedding vector, which then is un-embedded into a token probability. However, that vector can then be further processed by another transformer block to predict the *next* token, and so on for arbitrarily many steps into the future. This trades off accuracy for speed, since each new token costs just one more transformer block, rather than the entire stack.[[94]](./Transformer_(deep_learning)#cite_note-96)[[95]](./Transformer_(deep_learning)#cite_note-97)

 

### Sub-quadratic transformers

 

Training transformer-based architectures can be expensive, especially for long inputs.[[96]](./Transformer_(deep_learning)#cite_note-reformer-98) Many methods have been developed to attempt to address the issue. In the image domain, Swin transformer is an efficient architecture that performs attention inside shifting windows.[[97]](./Transformer_(deep_learning)#cite_note-99) In the audio domain, SepTr decouples the attention in time and frequency domains.[[98]](./Transformer_(deep_learning)#cite_note-100) *Long Range Arena* (2020)[[99]](./Transformer_(deep_learning)#cite_note-101) is a standard benchmark for comparing the behavior of transformer architectures over long inputs.

 

#### Alternative attention graphs

 

The standard attention graph is either all-to-all or causal, both of which scales as     O (  N  2   )   {\displaystyle O(N^{2})}  ![{\displaystyle O(N^{2})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e5d43a3df904fa4d7220f5b86285298aa36d969b) where     N   {\displaystyle N}  ![{\displaystyle N}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f5e3890c981ae85503089652feb48b191b57aae3) is the number of tokens in a sequence.

 

Reformer (2020)[[96]](./Transformer_(deep_learning)#cite_note-reformer-98)[[100]](./Transformer_(deep_learning)#cite_note-102) reduces the computational load from     O (  N  2   )   {\displaystyle O(N^{2})}  ![{\displaystyle O(N^{2})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e5d43a3df904fa4d7220f5b86285298aa36d969b) to     O ( N ln ⁡ ⁡  N )   {\displaystyle O(N\ln N)}  ![{\displaystyle O(N\ln N)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3d19d1f2923ba0d7170ade3df165c0de1d2423e) by using [locality-sensitive hashing](./Locality-sensitive_hashing) and reversible layers.[[101]](./Transformer_(deep_learning)#cite_note-103)

 

Sparse attention[[102]](./Transformer_(deep_learning)#cite_note-104) uses attention graphs that grows slower than     O (  N  2   )   {\displaystyle O(N^{2})}  ![{\displaystyle O(N^{2})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e5d43a3df904fa4d7220f5b86285298aa36d969b). For example, BigBird (2020)[[103]](./Transformer_(deep_learning)#cite_note-105) uses random [small-world networks](./Small-world_network) which grows as     O ( N )   {\displaystyle O(N)}  ![{\displaystyle O(N)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/78484c5c26cfc97bb3b915418caa09454421e80b).

 

Ordinary transformers require a memory size that is quadratic in the size of the context window. Attention-free transformers[[104]](./Transformer_(deep_learning)#cite_note-106) reduce this to a linear dependence while still retaining the advantages of a transformer by linking the key to the value.

 

#### Random Feature Attention

 

Random Feature Attention (2021)[[105]](./Transformer_(deep_learning)#cite_note-107) uses [Fourier random features](./Radial_basis_function_kernel#Fourier_random_features):    φ φ  ( x ) =   1  D    [ cos ⁡ ⁡  ⟨ ⟨   w  1   , x ⟩ ⟩  , sin ⁡ ⁡  ⟨ ⟨   w  1   , x ⟩ ⟩  , ⋯ ⋯  cos ⁡ ⁡  ⟨ ⟨   w  D   , x ⟩ ⟩  , sin ⁡ ⁡  ⟨ ⟨   w  D   , x ⟩ ⟩   ]  T     {\displaystyle \varphi (x)={\frac {1}{\sqrt {D}}}[\cos \langle w_{1},x\rangle ,\sin \langle w_{1},x\rangle ,\cdots \cos \langle w_{D},x\rangle ,\sin \langle w_{D},x\rangle ]^{T}}  ![{\displaystyle \varphi (x)={\frac {1}{\sqrt {D}}}[\cos \langle w_{1},x\rangle ,\sin \langle w_{1},x\rangle ,\cdots \cos \langle w_{D},x\rangle ,\sin \langle w_{D},x\rangle ]^{T}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/243ed0310c01dc8193d985ea838e92191cec4fac)where      w  1   , . . . ,  w  D     {\displaystyle w_{1},...,w_{D}}  ![{\displaystyle w_{1},...,w_{D}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c97fcd8d8f90947efda4e03b5ffc293c61cb094c) are independent samples from the normal distribution     N ( 0 ,  σ σ   2   I )   {\displaystyle N(0,\sigma ^{2}I)}  ![{\displaystyle N(0,\sigma ^{2}I)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9d30d920f052b8230e76c64a55f2cddc963b201f). This choice of parameters satisfy      E  [ ⟨ ⟨  φ φ  ( x ) , φ φ  ( y ) ⟩ ⟩  ] =  e  − −     ‖ ‖  x − −  y  ‖ ‖   2     2  σ σ   2          {\displaystyle \mathbb {E} [\langle \varphi (x),\varphi (y)\rangle ]=e^{-{\frac {\|x-y\|^{2}}{2\sigma ^{2}}}}}  ![{\displaystyle \mathbb {E} [\langle \varphi (x),\varphi (y)\rangle ]=e^{-{\frac {\|x-y\|^{2}}{2\sigma ^{2}}}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2e0f85eabd1581c50b848cf5d2d73ce4e7ac6e1d), or      e  ⟨ ⟨  x , y ⟩ ⟩   /   σ σ   2     =  E  [ ⟨ ⟨   e  ‖ ‖  x  ‖ ‖   2    /  2  σ σ   2     φ φ  ( x ) ,  e  ‖ ‖  y  ‖ ‖   2    /  2  σ σ   2     φ φ  ( y ) ⟩ ⟩  ] ≈ ≈  ⟨ ⟨   e  ‖ ‖  x  ‖ ‖   2    /  2  σ σ   2     φ φ  ( x ) ,  e  ‖ ‖  y  ‖ ‖   2    /  2  σ σ   2     φ φ  ( y ) ⟩ ⟩    {\displaystyle e^{\langle x,y\rangle /\sigma ^{2}}=\mathbb {E} [\langle e^{\|x\|^{2}/2\sigma ^{2}}\varphi (x),e^{\|y\|^{2}/2\sigma ^{2}}\varphi (y)\rangle ]\approx \langle e^{\|x\|^{2}/2\sigma ^{2}}\varphi (x),e^{\|y\|^{2}/2\sigma ^{2}}\varphi (y)\rangle }  ![{\displaystyle e^{\langle x,y\rangle /\sigma ^{2}}=\mathbb {E} [\langle e^{\|x\|^{2}/2\sigma ^{2}}\varphi (x),e^{\|y\|^{2}/2\sigma ^{2}}\varphi (y)\rangle ]\approx \langle e^{\|x\|^{2}/2\sigma ^{2}}\varphi (x),e^{\|y\|^{2}/2\sigma ^{2}}\varphi (y)\rangle }](https://wikimedia.org/api/rest_v1/media/math/render/svg/bfb56111453c9e03415021c39d21ed88a37d2ea1)Consequently, the one-headed attention, with one query, can be written as      Attention  ( q , K , V ) =  softmax   (    q  K   T       d  k      )  V ≈ ≈     φ φ  ( q  )  T    ∑ ∑   i    e  ‖ ‖   k  i    ‖ ‖   2    /  2  σ σ   2     φ φ  (  k  i   )  v  i   T     φ φ  ( q  )  T    ∑ ∑   i    e  ‖ ‖   k  i    ‖ ‖   2    /  2  σ σ   2     φ φ  (  k  i   )      {\displaystyle {\text{Attention}}(q,K,V)={\text{softmax}}\left({\frac {qK^{\mathrm {T} }}{\sqrt {d_{k}}}}\right)V\approx {\frac {\varphi (q)^{T}\sum _{i}e^{\|k_{i}\|^{2}/2\sigma ^{2}}\varphi (k_{i})v_{i}^{T}}{\varphi (q)^{T}\sum _{i}e^{\|k_{i}\|^{2}/2\sigma ^{2}}\varphi (k_{i})}}}  ![{\displaystyle {\text{Attention}}(q,K,V)={\text{softmax}}\left({\frac {qK^{\mathrm {T} }}{\sqrt {d_{k}}}}\right)V\approx {\frac {\varphi (q)^{T}\sum _{i}e^{\|k_{i}\|^{2}/2\sigma ^{2}}\varphi (k_{i})v_{i}^{T}}{\varphi (q)^{T}\sum _{i}e^{\|k_{i}\|^{2}/2\sigma ^{2}}\varphi (k_{i})}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/bca1667ac7c453bd1979496b1b951fc9c09d3b08)where     σ σ  =  d  K   1  /  4     {\displaystyle \sigma =d_{K}^{1/4}}  ![{\displaystyle \sigma =d_{K}^{1/4}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d2571d23e3b9162609ece1399f4abf50811e4eb6). Similarly for multiple queries, and for multihead attention.

 

This approximation can be computed in linear time, as we can compute the matrix     φ φ  (  k  i   )  v  i   T     {\displaystyle \varphi (k_{i})v_{i}^{T}}  ![{\displaystyle \varphi (k_{i})v_{i}^{T}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6276b79cd088813503ec00ae5eab91ab02d8a7f0) first, then multiply it with the query. In essence, we have managed to obtain a more precise version of      Attention  ( Q , K , V ) =  softmax   (    Q  K   T       d  k      )  V ≈ ≈  Q (  K  T   V  /     d  k     )   {\displaystyle {\text{Attention}}(Q,K,V)={\text{softmax}}\left({\frac {QK^{\mathrm {T} }}{\sqrt {d_{k}}}}\right)V\approx Q(K^{T}V/{\sqrt {d_{k}}})}  ![{\displaystyle {\text{Attention}}(Q,K,V)={\text{softmax}}\left({\frac {QK^{\mathrm {T} }}{\sqrt {d_{k}}}}\right)V\approx Q(K^{T}V/{\sqrt {d_{k}}})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7da7e0c09e0f526924af6c95f7c0d2c6fb34b910)Performer (2022)[[106]](./Transformer_(deep_learning)#cite_note-108) uses the same Random Feature Attention, but      w  1   , . . . ,  w  D     {\displaystyle w_{1},...,w_{D}}  ![{\displaystyle w_{1},...,w_{D}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c97fcd8d8f90947efda4e03b5ffc293c61cb094c) are first independently sampled from the normal distribution     N ( 0 ,  σ σ   2   I )   {\displaystyle N(0,\sigma ^{2}I)}  ![{\displaystyle N(0,\sigma ^{2}I)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9d30d920f052b8230e76c64a55f2cddc963b201f), then they are [Gram–Schmidt processed](./Gram–Schmidt_process).

 

### Multimodality

 

Transformers can also be used/adapted for modalities (input or output) beyond just text, usually by finding a way to "tokenize" the modality.

 

Multimodal models can either be trained from scratch, or by finetuning. A 2022 study found that transformers pretrained only on natural language can be finetuned on only 0.03% of parameters and become competitive with [LSTMs](./LSTMs) on a variety of logical and visual tasks, demonstrating [transfer learning](./Transfer_learning).[[107]](./Transformer_(deep_learning)#cite_note-109) The LLaVA was a vision-language model composed of a language model (Vicuna-13B)[[108]](./Transformer_(deep_learning)#cite_note-110) and a vision model ([ViT](./Vision_transformer)-L/14), connected by a linear layer. Only the linear layer is finetuned.[[109]](./Transformer_(deep_learning)#cite_note-111)

 

[Vision transformers](./Vision_transformer)[[48]](./Transformer_(deep_learning)#cite_note-auto2-50) adapt the transformer to computer vision by breaking down input images as a series of patches, turning them into vectors, and treating them like embedding vector of tokens in a standard transformer.

 

Conformer[[49]](./Transformer_(deep_learning)#cite_note-Gulati2020-51) and later [Whisper](./Whisper_(speech_recognition_system))[[110]](./Transformer_(deep_learning)#cite_note-Radford_Kim_Xu_Brockman_p.-112) follow the same pattern for [speech recognition](./Speech_recognition), first turning the speech signal into a [spectrogram](./Spectrogram), which is then treated like an image, i.e. broken down into a series of patches, turned into vectors and treated like embedding vector of tokens in a standard transformer.

 

[Perceivers](./Perceiver)[[111]](./Transformer_(deep_learning)#cite_note-perceiver2021-113)[[112]](./Transformer_(deep_learning)#cite_note-jaegle2021b-114) are a variant of transformers designed for multimodality.

 

For image generation, notable architectures are [DALL-E 1](./DALL-E) (2021), Parti (2022),[[113]](./Transformer_(deep_learning)#cite_note-115) Phenaki (2023),[[114]](./Transformer_(deep_learning)#cite_note-:13-116) and Muse (2023).[[115]](./Transformer_(deep_learning)#cite_note-:12-117) Unlike later models, DALL-E is not a [diffusion model](./Diffusion_model). Instead, it uses a decoder-only transformer that autoregressively generates a text, followed by the token representation of an image, which is then converted by a [variational autoencoder](./Variational_autoencoder) to an image.[[116]](./Transformer_(deep_learning)#cite_note-118) Parti is an encoder–decoder transformer, where the encoder processes a text prompt, and the decoder generates a token representation of an image.[[117]](./Transformer_(deep_learning)#cite_note-119) Muse is an encoder-only transformer that is trained to predict masked image tokens from unmasked image tokens. During generation, all input tokens are masked, and the highest-confidence predictions are included for the next iteration, until all tokens are predicted.[[115]](./Transformer_(deep_learning)#cite_note-:12-117) Phenaki is a text-to-video model. It is a bidirectional masked transformer conditioned on pre-computed text tokens. The generated tokens are then decoded to a video.[[114]](./Transformer_(deep_learning)#cite_note-:13-116)

 


