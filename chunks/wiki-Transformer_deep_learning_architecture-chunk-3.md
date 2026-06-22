---
source: sources/wiki-Transformer_deep_learning_architecture.md
source_url: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)
chunk: 3/8
---

## Architecture

 

All transformers have the same primary components:

 
- Tokenizers, which convert text into tokens.
- Embedding layer, which converts tokens and positions of the tokens into vector representations.
- Transformer layers, which carry out repeated transformations on the vector representations, extracting more and more linguistic information. These consist of alternating attention and feedforward layers. There are two major types of transformer layers: encoder layers and decoder layers, with further variants.
- Un-embedding layer, which converts the final vector representations back to a probability distribution over the tokens.

 

The following description follows exactly the transformer as described in the original paper. There are variants, described in the [following section](./Transformer_(deep_learning)#Subsequent_work).

 

By convention, we write all vectors as row vectors. For example, pushing a vector through a linear layer means multiplying it by a weight matrix on the right, as     x W   {\displaystyle xW}  ![{\displaystyle xW}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b366d97326adb9cbb74e22c5ee0966dd055cd2dc).

 

### Tokenization

 

As the transformer architecture natively consists of operations over numbers (matrix multiplications, dot products, activation functions) rather than over text, there must first be a mapping from any input text to some numerical representation. This happens in three steps.

 

First, the input text is treated by a *preprocessor*, which performs both textual transformations and splits the text into coarse-grained segments called *pretokens*. The latter is referred to as *pretokenization*. Second, each pretoken is segmented further into *tokens* by a *tokenizer* that expects to only see pretokens output by its preprocessor. Each token it produces is a string of one or more characters belonging to a finite set of strings called the *vocabulary*     V   {\displaystyle V}  ![{\displaystyle V}](https://wikimedia.org/api/rest_v1/media/math/render/svg/af0f6064540e84211d0ffe4dac72098adfa52845). Third, because the vocabulary is finite and known beforehand, each token can be assigned an integer identifier, and this mapping is applied to the sequence of tokens to represent any input text as a numerical sequence. Since this mapping is bijective, the output side can produce a sequence of integer identifiers which can then be turned back into tokens. After undoing some of the preprocessing, the result is again legible text.

 

Training a tokenizer (sometimes referred to as *vocabularization*) means finding a suitable vocabulary     V   {\displaystyle V}  ![{\displaystyle V}](https://wikimedia.org/api/rest_v1/media/math/render/svg/af0f6064540e84211d0ffe4dac72098adfa52845), but also learning how to use it, since any given string     s   {\displaystyle s}  ![{\displaystyle s}](https://wikimedia.org/api/rest_v1/media/math/render/svg/01d131dfd7673938b947072a13a9744fe997e632) of length      |  s  |    {\displaystyle |s|}  ![{\displaystyle |s|}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0ae65dea0cc836140252292ee9adf2d8b5102055) has      2   |  s  |  − −  1     {\displaystyle 2^{|s|-1}}  ![{\displaystyle 2^{|s|-1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3d844850486603030caed10d1c3d330d604770b8) hypothetical segmentations, some of which containing segments that are not in the vocabulary. The most important hyperparameter during vocabularization is the *vocabulary size*      |  V  |    {\displaystyle |V|}  ![{\displaystyle |V|}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9ddcffc28643ac01a14dd0fb32c3157859e365a7): when it is small, the learned vocabulary generally consists of characters and smaller strings, and words will be segmented into many tokens. At larger sizes, it becomes affordable to dedicate tokens to full words, although depending on the preprocessor and tokenizer, it is not necessarily the case that large vocabularies will always use the largest token(s) available to segment a word.

 

Because tokens are not always full words, they may also be referred to as *subwords* and tokenization algorithms may be referred to as *subword tokenizers*. This is also to differentiate these systems from [traditional terminology](./Lexical_analysis) used in older information retrieval and natural language processing systems, where "tokenization" was used to denote what is today called "pretokenization" (very crudely: splitting into words). In tokenizers that produce tokens that are *not* part of the vocabulary, a special token that does belong to the vocabulary is used as a generic stand-in, written as "[UNK]" for "unknown". In principle, any string could be hidden by such an [UNK]. Indeed, in information retrieval, pretokenizers were themselves used as tokenizers (and also called "tokenizers") with a word-level vocabulary that contained an [UNK].

 

Commonly used subword tokenization algorithms are [byte pair encoding](./Byte_pair_encoding) (BPE) and the unigram language model (ULM), which each include a vocabularization algorithm and a dedicated segmentation algorithm. There also exist several segmentation algorithms that require no learning and can be applied given a vocabulary (produced by BPE or ULM, for example), like greedily recognising tokens in a pretoken by moving through it left-to-right. Well-known software implementations of subword tokenizers are [Hugging Face](./Hugging_Face)'s `tokenizers` Python package implemented in Rust, and the `sentencepiece` Python package implemented in C++. The latter package is named as such because one of its configuration options allows disabling the built-in pretokenizer, hence effectively making entire sentences a pretoken and thus having the tokenizer see entire sentences, rather than individual words.

 

### Embedding

 Further information: [Word embedding](./Word_embedding) 

Each integer token identifier is converted into an embedding vector via a [lookup table](./Lookup_table). Equivalently stated, it multiplies a [one-hot](./One-hot) representation of the token identifier by an embedding matrix     M   {\displaystyle M}  ![{\displaystyle M}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f82cade9898ced02fdd08712e5f0c0151758a0dd). For example, if the input token's identifier is     3   {\displaystyle 3}  ![{\displaystyle 3}](https://wikimedia.org/api/rest_v1/media/math/render/svg/991e33c6e207b12546f15bdfee8b5726eafbbb2f), then the one-hot representation is     [ 0 , 0 , 0 , 1 , 0 , 0 , … …  ]   {\displaystyle [0,0,0,1,0,0,\dots ]}  ![{\displaystyle [0,0,0,1,0,0,\dots ]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a5a20e2ecac4d6b6e2e9fa0f965758e488c1d70f), and its embedding vector is     E m b e d  ( 3 ) = [ 0 , 0 , 0 , 1 , 0 , 0 , … …  ] M   {\displaystyle \mathrm {Embed} (3)=[0,0,0,1,0,0,\dots ]M}  ![{\displaystyle \mathrm {Embed} (3)=[0,0,0,1,0,0,\dots ]M}](https://wikimedia.org/api/rest_v1/media/math/render/svg/66ba0293d96eeea4e56e92c73333349bc813855c)The token embedding vectors are added to their respective positional encoding vectors (see below), producing the sequence of input vectors.

 

The dimension of an embedding vector is called *hidden size* or *embedding size* and written as      d  emb     {\displaystyle d_{\text{emb}}}  ![{\displaystyle d_{\text{emb}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4bf3df2909758ee1d69be67380da3263cfba984e).[[40]](./Transformer_(deep_learning)#cite_note-:03-42) This size is written as      d  model     {\displaystyle d_{\text{model}}}  ![{\displaystyle d_{\text{model}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/aefdfb00976a3a5c5ec3c8fcbcc166e82ceb6268) in the original transformer paper.[[1]](./Transformer_(deep_learning)#cite_note-2017_Attention_Is_All_You_Need-1)

 

### Un-embedding

 

An un-embedding layer is almost the reverse of an embedding layer. Whereas an embedding layer converts a token identifier into a vector, an un-embedding layer converts a vector into a probability distribution over tokens.

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/5/51/Top_token_probabilities%2C_chain_of_thought_response_only%2C_for_GPT-OSS_%2820b%29.svg/960px-Top_token_probabilities%2C_chain_of_thought_response_only%2C_for_GPT-OSS_%2820b%29.svg.png)](./File:Top_token_probabilities,_chain_of_thought_response_only,_for_GPT-OSS_(20b).svg)An illustration of the top 16 token probabilities at temperature 1, for each output token in the chain-of-thought response, with colour representing how that output differs from the same prompt but at temperature 0. 

The un-embedding layer is a linear-[softmax](./Softmax_function) layer:     U n E m b e d  ( x ) =  s o f t m a x  ( x W + b )   {\displaystyle \mathrm {UnEmbed} (x)=\mathrm {softmax} (xW+b)}  ![{\displaystyle \mathrm {UnEmbed} (x)=\mathrm {softmax} (xW+b)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/df5d49f6baaf8081c203cd3613765a48f0a23da5)The matrix has shape     (  d  emb   ,  |  V  |  )   {\displaystyle (d_{\text{emb}},|V|)}  ![{\displaystyle (d_{\text{emb}},|V|)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9dcb9b66af8f800d469cf5dfeb06c64ffbf2ab59). Some architectures use the transpose of the embedding matrix     M   {\displaystyle M}  ![{\displaystyle M}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f82cade9898ced02fdd08712e5f0c0151758a0dd) as the un-embedding matrix     W   {\displaystyle W}  ![{\displaystyle W}](https://wikimedia.org/api/rest_v1/media/math/render/svg/54a9c4c547f4d6111f81946cad242b18298d70b7) in order to avoid needing double the amount of embedding-related parameters and to avoid divergence during training. This practice is called *weight tying*.[[59]](./Transformer_(deep_learning)#cite_note-61)

 

### Positional encoding

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/a/a9/Absolute_positional_encoding.png/250px-Absolute_positional_encoding.png)](./File:Absolute_positional_encoding.png)Illustration of (absolute) positional encoding with parameters     N = 10000 , d = 100   {\displaystyle N=10000,d=100}  ![{\displaystyle N=10000,d=100}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fe83017b9728026bf6d2bae4a357041d198ac494) 

A positional encoding is a fixed-size vector representation of the relative positions of tokens within a sequence: it provides the transformer model with information about *where* the words are in the input sequence. This induces a [bias](./Inductive_bias) towards the order of the input sequence, so that, for example, the input sequence "[man bites dog](./Man_bites_dog)" is processed differently from "dog bites man".

 

The positional encoding is defined as a function of type     f :  R  → →    R   d     {\displaystyle f:\mathbb {R} \to \mathbb {R} ^{d}}  ![{\displaystyle f:\mathbb {R} \to \mathbb {R} ^{d}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ff4df0a644d47d52c00ba8ca23edbabb9c8c4749), where     d   {\displaystyle d}  ![{\displaystyle d}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e85ff03cbe0c7341af6b982e47e9f90d235c66ab) is a positive even [integer](./Integer). The full positional encoding defined in the original paper[[1]](./Transformer_(deep_learning)#cite_note-2017_Attention_Is_All_You_Need-1) is:    ( f ( t  )  2 k   , f ( t  )  2 k + 1   ) = ( sin ⁡ ⁡  ( θ θ  ) , cos ⁡ ⁡  ( θ θ  ) )  ∀ ∀  k ∈ ∈  { 0 , 1 , … …  , d  /  2 − −  1 }   {\displaystyle (f(t)_{2k},f(t)_{2k+1})=(\sin(\theta ),\cos(\theta ))\quad \forall k\in \{0,1,\ldots ,d/2-1\}}  ![{\displaystyle (f(t)_{2k},f(t)_{2k+1})=(\sin(\theta ),\cos(\theta ))\quad \forall k\in \{0,1,\ldots ,d/2-1\}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/cbca45061217292a4920ea20881b77a1b39a41ea)where     θ θ  =   t  r  k     , r =  N  2  /  d     {\displaystyle \theta ={\frac {t}{r^{k}}},r=N^{2/d}}  ![{\displaystyle \theta ={\frac {t}{r^{k}}},r=N^{2/d}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8ba16328b4d94e923d80ad257002a6d18deb2edb).

 

Here,     N   {\displaystyle N}  ![{\displaystyle N}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f5e3890c981ae85503089652feb48b191b57aae3) is a free parameter that should be significantly larger than the biggest     k   {\displaystyle k}  ![{\displaystyle k}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c3c9a2c7b599b37105512c5d570edc034056dd40) that would be input into the positional encoding function. The original paper uses     N = 10000   {\displaystyle N=10000}  ![{\displaystyle N=10000}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8f13b17e1a7fbe046ab619ccc5167809d04872c2).

 

The function is in a simpler form when written as a complex function of type     f :  R  → →    C   d  /  2     {\displaystyle f:\mathbb {R} \to \mathbb {C} ^{d/2}}  ![{\displaystyle f:\mathbb {R} \to \mathbb {C} ^{d/2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/52c816b7a3f4f0855fc1cc7bafb9dbce1efc09d0)    f ( t ) =   (  e  i t  /   r  k     )   k = 0 , 1 , … …  ,   d 2   − −  1     {\displaystyle f(t)=\left(e^{it/r^{k}}\right)_{k=0,1,\ldots ,{\frac {d}{2}}-1}}  ![{\displaystyle f(t)=\left(e^{it/r^{k}}\right)_{k=0,1,\ldots ,{\frac {d}{2}}-1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4887fec07bd9ef29ad5783f32651b1e503a88130)where     r =  N  2  /  d     {\displaystyle r=N^{2/d}}  ![{\displaystyle r=N^{2/d}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/11cb2cfb2ab25e2e0cb3ed51071f1e7f38060c99).

 

The main reason for using this positional encoding function is that using it, shifts are linear transformations:    f ( t + Δ Δ  t ) =  d i a g  ( f ( Δ Δ  t ) ) f ( t )   {\displaystyle f(t+\Delta t)=\mathrm {diag} (f(\Delta t))f(t)}  ![{\displaystyle f(t+\Delta t)=\mathrm {diag} (f(\Delta t))f(t)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/cce4053e6d0f3e225b153bc362be4970c3e9b535)where     Δ Δ  t ∈ ∈   R    {\displaystyle \Delta t\in \mathbb {R} }  ![{\displaystyle \Delta t\in \mathbb {R} }](https://wikimedia.org/api/rest_v1/media/math/render/svg/40be374d0e9f96fefe0a14ddb46218a42409b2a6) is the distance one wishes to shift. This allows the transformer to take any encoded position, and find the encoding of the position n-steps-ahead or n-steps-behind, by a matrix multiplication.

 

By taking a linear sum, any convolution can also be implemented as linear transformations:     ∑ ∑   j    c  j   f ( t + Δ Δ   t  j   ) =  (   ∑ ∑   j    c  j     d i a g  ( f ( Δ Δ   t  j   ) )  )  f ( t )   {\displaystyle \sum _{j}c_{j}f(t+\Delta t_{j})=\left(\sum _{j}c_{j}\,\mathrm {diag} (f(\Delta t_{j}))\right)f(t)}  ![{\displaystyle \sum _{j}c_{j}f(t+\Delta t_{j})=\left(\sum _{j}c_{j}\,\mathrm {diag} (f(\Delta t_{j}))\right)f(t)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/14a5ba5df2e142a7c6812dd345b2001550cfa3f0)for any constants      c  j     {\displaystyle c_{j}}  ![{\displaystyle c_{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a844d180d176af828d1636d4e85aa534d0b77baa). This allows the transformer to take any encoded position and find a linear sum of the encoded locations of its neighbors. This sum of encoded positions, when fed into the attention mechanism, would create attention weights on its neighbors, much like what happens in a [convolutional neural network](./Convolutional_neural_network) [language model](./Language_model). In the author's words, "we hypothesized it would allow the model to easily learn to attend by relative position."

 

In typical implementations, all operations are done over the real numbers, not the complex numbers, but since [complex multiplication can be implemented as real 2-by-2 matrix multiplication](./Complex_number#Matrix_representation_of_complex_numbers), this is a mere notational difference.

 

### Encoder–decoder (overview)

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/5/53/Transformer%2C_one_encoder-decoder_block.png/250px-Transformer%2C_one_encoder-decoder_block.png)](./File:Transformer,_one_encoder-decoder_block.png)One encoder–decoder block [![](//upload.wikimedia.org/wikipedia/commons/thumb/5/5f/Transformer%2C_stacked_layers_and_sublayers.png/250px-Transformer%2C_stacked_layers_and_sublayers.png)](./File:Transformer,_stacked_layers_and_sublayers.png)A transformer is composed of stacked encoder layers and decoder layers. 

Like earlier [seq2seq](./Seq2seq) models, the original transformer model used an **encoder–decoder** architecture. The encoder consists of encoding layers that process all the input tokens together one layer after another, while the decoder consists of decoding layers that iteratively process the encoder's output and the decoder's output tokens so far.

 

The purpose of each encoder layer is to create contextualized representations of the tokens, where each representation corresponds to a token that "mixes" information from other input tokens via self-attention mechanism. Each decoder layer contains two attention sublayers: (1) cross-attention for incorporating the output of encoder (contextualized input token representations), and (2) self-attention for "mixing" information among the input tokens to the decoder (i.e. the tokens generated so far during inference time).[[60]](./Transformer_(deep_learning)#cite_note-62)[[61]](./Transformer_(deep_learning)#cite_note-:1-63)

 

Both the encoder and decoder layers have a [feed-forward neural network](./Feedforward_neural_network) for additional processing of their outputs and contain residual connections and layer normalization steps.[[61]](./Transformer_(deep_learning)#cite_note-:1-63) These feed-forward layers contain most of the parameters in a transformer model.

 

### Feedforward network

 

[![](//upload.wikimedia.org/wikipedia/commons/thumb/5/59/Transformer_architecture_-_FFN_module.png/250px-Transformer_architecture_-_FFN_module.png)](./File:Transformer_architecture_-_FFN_module.png)The feedforward network module. It is a two-layered network that maps      d  emb     {\displaystyle d_{\text{emb}}}  ![{\displaystyle d_{\text{emb}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4bf3df2909758ee1d69be67380da3263cfba984e)-dimensional vectors into      d  emb     {\displaystyle d_{\text{emb}}}  ![{\displaystyle d_{\text{emb}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4bf3df2909758ee1d69be67380da3263cfba984e)-dimensional vectors. 

The feedforward network (FFN) modules in a transformer are 2-layered [multilayer perceptrons](./Feedforward_neural_network):     F F N  ( x ) = ϕ ϕ  ( x  W  ( 1 )   +  b  ( 1 )   )  W  ( 2 )   +  b  ( 2 )     {\displaystyle \mathrm {FFN} (x)=\phi (xW^{(1)}+b^{(1)})W^{(2)}+b^{(2)}}  ![{\displaystyle \mathrm {FFN} (x)=\phi (xW^{(1)}+b^{(1)})W^{(2)}+b^{(2)}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3018d1cafd676461ec6a1927aff651d73ce78377)where      W  ( 1 )     {\displaystyle W^{(1)}}  ![{\displaystyle W^{(1)}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/351c8e7ea5512879f0b5762c284792c760b4a70e) and      W  ( 2 )     {\displaystyle W^{(2)}}  ![{\displaystyle W^{(2)}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2196a6b93c1ae79e6b2b6cbe9c6c411cf1420513) are weight matrices and      b  ( 1 )     {\displaystyle b^{(1)}}  ![{\displaystyle b^{(1)}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6abb02f6ce2b97279afa53deca31b9436df25421) and       b  ( 2 )     {\displaystyle b^{(2)}}  ![{\displaystyle b^{(2)}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3b10499e26db8834d9306ad4deb7f1a095e8ff27) are bias vectors, and     ϕ ϕ    {\displaystyle \phi }  ![{\displaystyle \phi }](https://wikimedia.org/api/rest_v1/media/math/render/svg/72b1f30316670aee6270a28334bdf4f5072cdde4) is its activation function. The original transformer used [ReLU](./Rectifier_(neural_networks)) activation.

 

The number of neurons in the middle layer is called *intermediate size* (GPT),[[62]](./Transformer_(deep_learning)#cite_note-64) *filter size* (BERT),[[40]](./Transformer_(deep_learning)#cite_note-:03-42) or *feedforward size* (BERT).[[40]](./Transformer_(deep_learning)#cite_note-:03-42) It is typically larger than the embedding size. For example, in both GPT-2 series and BERT series, the intermediate size of a model is 4 times its embedding size:      d  ffn   = 4  d  emb     {\displaystyle d_{\text{ffn}}=4d_{\text{emb}}}  ![{\displaystyle d_{\text{ffn}}=4d_{\text{emb}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/11c9e89a82cdff80cd9e03abfef22730a29bf958).

 

### Scaled dot-product attention

 Main article: [Dot-product attention](./Dot-product_attention) 

#### Attention head

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/1/1b/Transformer%2C_attention_block_diagram.png/250px-Transformer%2C_attention_block_diagram.png)](./File:Transformer,_attention_block_diagram.png)Scaled dot-product attention, block diagram [![](//upload.wikimedia.org/wikipedia/commons/thumb/c/c4/Transformer_architecture_-_Attention_Head_module.png/250px-Transformer_architecture_-_Attention_Head_module.png)](./File:Transformer_architecture_-_Attention_Head_module.png)Exact dimension counts within an attention head module 

The attention mechanism used in the transformer architecture are scaled [dot-product](./Dot_product) [attention](./Attention_(machine_learning)) units. For each unit, the transformer model learns three weight matrices: the query weights      W  Q     {\displaystyle W^{Q}}  ![{\displaystyle W^{Q}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/12fad024825b554ffb621d5385460ffce533f1bb), the key weights      W  K     {\displaystyle W^{K}}  ![{\displaystyle W^{K}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/060b854f3f44615cefb8441780e6c31742f5dbd2), and the value weights      W  V     {\displaystyle W^{V}}  ![{\displaystyle W^{V}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ef0a2e5fb27e9e6d1fc86901833d40d7e685a460).

 

The module takes three sequences, a query sequence, a key sequence, and a value sequence. The query sequence is a sequence of length      ℓ ℓ   seq, query     {\displaystyle \ell _{\text{seq, query}}}  ![{\displaystyle \ell _{\text{seq, query}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fe514b95a8db1105db6bcdf5a7148d8014461e59), and each entry is a vector of dimension      d  emb, query     {\displaystyle d_{\text{emb, query}}}  ![{\displaystyle d_{\text{emb, query}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/569324b1ee8814a09242042f2fffdbac51e922bd). Similarly for the key and value sequences.

 

For each vector      x  i ,  query      {\displaystyle x_{i,{\text{query}}}}  ![{\displaystyle x_{i,{\text{query}}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0d096bf3997e6d4d12626058f5747fa4a19f0ca8) in the query sequence, it is multiplied by a matrix      W  Q     {\displaystyle W^{Q}}  ![{\displaystyle W^{Q}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/12fad024825b554ffb621d5385460ffce533f1bb) to produce a query vector      q  i   =  x  i ,  query     W  Q     {\displaystyle q_{i}=x_{i,{\text{query}}}W^{Q}}  ![{\displaystyle q_{i}=x_{i,{\text{query}}}W^{Q}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ad0056fecb11a213583cff46a83e331050830a13). The matrix of all query vectors is the query matrix:    Q =  X  query    W  Q     {\displaystyle Q=X_{\text{query}}W^{Q}}  ![{\displaystyle Q=X_{\text{query}}W^{Q}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1fdcfa516a1e0a158286801715d89368d2d8a948)Similarly, we construct the key matrix     K =  X  key    W  K     {\displaystyle K=X_{\text{key}}W^{K}}  ![{\displaystyle K=X_{\text{key}}W^{K}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/25cdd16edf96b2453753c8d73d9b86bd7acee034) and the value matrix     V =  X  value    W  V     {\displaystyle V=X_{\text{value}}W^{V}}  ![{\displaystyle V=X_{\text{value}}W^{V}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4a44f4ff55f3ba2722b925af1e749c37936c88a6).

 

It is usually the case that all      W  Q   ,  W  K   ,  W  V     {\displaystyle W^{Q},W^{K},W^{V}}  ![{\displaystyle W^{Q},W^{K},W^{V}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f5c6380cb67a00550ee5dfb91733a9bfdad94b42) are square matrices, meaning      d  emb, query   =  d  query     {\displaystyle d_{\text{emb, query}}=d_{\text{query}}}  ![{\displaystyle d_{\text{emb, query}}=d_{\text{query}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ed9f9eea42977c0cab83ddcf2f1de48138e007c6), etc.

 

Attention weights are calculated using the query and key vectors: the attention weight      a  i j     {\displaystyle a_{ij}}  ![{\displaystyle a_{ij}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ebea6cd2813c330c798921a2894b358f7b643917) from token     i   {\displaystyle i}  ![{\displaystyle i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/add78d8608ad86e54951b8c8bd6c8d8416533d20) to token     j   {\displaystyle j}  ![{\displaystyle j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f461e54f5c093e92a55547b9764291390f0b5d0) is the [dot product](./Dot_product) between      q  i     {\displaystyle q_{i}}  ![{\displaystyle q_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2752dcbff884354069fe332b8e51eb0a70a531b6) and      k  j     {\displaystyle k_{j}}  ![{\displaystyle k_{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/05ddf2c6d7759ac955e001a7cfafb2abfca41b0b). The attention weights are divided by the square root of the dimension of the key vectors,        d  k       {\displaystyle {\sqrt {d_{k}}}}  ![{\displaystyle {\sqrt {d_{k}}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0be678d1b945828faecd56b29927f5a60011be37), which stabilizes gradients during training, and passed through a [softmax](./Softmax_function) which normalizes the weights. The fact that      W  Q     {\displaystyle W^{Q}}  ![{\displaystyle W^{Q}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/12fad024825b554ffb621d5385460ffce533f1bb) and      W  K     {\displaystyle W^{K}}  ![{\displaystyle W^{K}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/060b854f3f44615cefb8441780e6c31742f5dbd2) are different matrices allows attention to be non-symmetric: if token     i   {\displaystyle i}  ![{\displaystyle i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/add78d8608ad86e54951b8c8bd6c8d8416533d20) attends to token     j   {\displaystyle j}  ![{\displaystyle j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f461e54f5c093e92a55547b9764291390f0b5d0) (i.e.      q  i   ⋅ ⋅   k  j     {\displaystyle q_{i}\cdot k_{j}}  ![{\displaystyle q_{i}\cdot k_{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7de4219a59ace005d92f8d0a13466dbdb5fd6d9c) is large), this does not necessarily mean that token     j   {\displaystyle j}  ![{\displaystyle j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f461e54f5c093e92a55547b9764291390f0b5d0) will attend to token     i   {\displaystyle i}  ![{\displaystyle i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/add78d8608ad86e54951b8c8bd6c8d8416533d20) (i.e.      q  j   ⋅ ⋅   k  i     {\displaystyle q_{j}\cdot k_{i}}  ![{\displaystyle q_{j}\cdot k_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d40445a57203e20510d7b629e0567957524700e4) could be small). The output of the attention unit for token     i   {\displaystyle i}  ![{\displaystyle i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/add78d8608ad86e54951b8c8bd6c8d8416533d20) is the weighted sum of the value vectors of all tokens, weighted by      a  i j     {\displaystyle a_{ij}}  ![{\displaystyle a_{ij}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ebea6cd2813c330c798921a2894b358f7b643917), the attention from token     i   {\displaystyle i}  ![{\displaystyle i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/add78d8608ad86e54951b8c8bd6c8d8416533d20) to each token.

 

The attention calculation for all tokens can be expressed as one large matrix calculation using the [softmax function](./Softmax_function), which is useful for training due to computational matrix operation optimizations that quickly compute matrix operations. The matrices     Q   {\displaystyle Q}  ![{\displaystyle Q}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8752c7023b4b3286800fe3238271bbca681219ed),     K   {\displaystyle K}  ![{\displaystyle K}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2b76fce82a62ed5461908f0dc8f037de4e3686b0) and     V   {\displaystyle V}  ![{\displaystyle V}](https://wikimedia.org/api/rest_v1/media/math/render/svg/af0f6064540e84211d0ffe4dac72098adfa52845) are defined as the matrices where the     i   {\displaystyle i}  ![{\displaystyle i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/add78d8608ad86e54951b8c8bd6c8d8416533d20)th rows are vectors      q  i     {\displaystyle q_{i}}  ![{\displaystyle q_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2752dcbff884354069fe332b8e51eb0a70a531b6),      k  i     {\displaystyle k_{i}}  ![{\displaystyle k_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f29138ed3ad54ffce527daccadc49c520459b0b0), and      v  i     {\displaystyle v_{i}}  ![{\displaystyle v_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7dffe5726650f6daac54829972a94f38eb8ec127) respectively. Then we can represent the attention as         Attention  ( Q , K , V ) =  softmax   (    Q  K   T       d  k      )  V       {\displaystyle {\begin{aligned}{\text{Attention}}(Q,K,V)={\text{softmax}}\left({\frac {QK^{\mathrm {T} }}{\sqrt {d_{k}}}}\right)V\end{aligned}}}  ![{\displaystyle {\begin{aligned}{\text{Attention}}(Q,K,V)={\text{softmax}}\left({\frac {QK^{\mathrm {T} }}{\sqrt {d_{k}}}}\right)V\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0b2afc7240eb97375a384b1628c18438e3068e3f)

 

where the softmax is applied over each of the rows of the matrix.

 

The number of dimensions in a query vector is *query size*      d  query     {\displaystyle d_{\text{query}}}  ![{\displaystyle d_{\text{query}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a08e7abd7e328c9458c6522b8c0746f27c2d8b53) and similarly for the *key size*      d  key     {\displaystyle d_{\text{key}}}  ![{\displaystyle d_{\text{key}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fb86df1f34f41a6100f5569f3b0ab489a14b7136) and *value size*      d  value     {\displaystyle d_{\text{value}}}  ![{\displaystyle d_{\text{value}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/046c86fdb216cdea1d8ee121df3b755763001ab1). The output dimension of an attention head is its *head dimension*      d  head     {\displaystyle d_{\text{head}}}  ![{\displaystyle d_{\text{head}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/dc21fc3863abb48214d18eeb00efa0c3ae102896). The attention mechanism requires the following three equalities to hold:     ℓ ℓ   seq, key   =  ℓ ℓ   seq, value   ,   d  query   =  d  key   ,   d  value   =  d  head     {\displaystyle \ell _{\text{seq, key}}=\ell _{\text{seq, value}},\;d_{\text{query}}=d_{\text{key}},\;d_{\text{value}}=d_{\text{head}}}  ![{\displaystyle \ell _{\text{seq, key}}=\ell _{\text{seq, value}},\;d_{\text{query}}=d_{\text{key}},\;d_{\text{value}}=d_{\text{head}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b25b25f22a8a09c26350d2f065628dd4b3911669)but is otherwise unconstrained.

 

If the attention head is used in a self-attention fashion, then      X  query   =  X  key   =  X  value     {\displaystyle X_{\text{query}}=X_{\text{key}}=X_{\text{value}}}  ![{\displaystyle X_{\text{query}}=X_{\text{key}}=X_{\text{value}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/05e0578cf40298283b50d5e5874308d529fc6ec7). If the attention head is used in a cross-attention fashion, then usually      X  query   ≠ ≠   X  key   =  X  value     {\displaystyle X_{\text{query}}\neq X_{\text{key}}=X_{\text{value}}}  ![{\displaystyle X_{\text{query}}\neq X_{\text{key}}=X_{\text{value}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/398ed1ae2490d963661a8ae37d94c04bfc732f9f). It is theoretically possible for all three to be different, but that is rarely the case in practice.

 

#### Multihead attention

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/d/d2/Multiheaded_attention%2C_block_diagram.png/250px-Multiheaded_attention%2C_block_diagram.png)](./File:Multiheaded_attention,_block_diagram.png)Multihead attention, block diagram [![](//upload.wikimedia.org/wikipedia/commons/thumb/1/15/Transformer_architecture_-_Multiheaded_Attention_module.png/250px-Transformer_architecture_-_Multiheaded_Attention_module.png)](./File:Transformer_architecture_-_Multiheaded_Attention_module.png)Exact dimension counts within a multihead attention module 

One set of      (   W  Q   ,  W  K   ,  W  V    )    {\displaystyle \left(W^{Q},W^{K},W^{V}\right)}  ![{\displaystyle \left(W^{Q},W^{K},W^{V}\right)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1306697728f261e1803778d1b2e042c7df652ae7) matrices is called an *attention head*, and each layer in a transformer model has multiple attention heads. While each attention head attends to the tokens that are relevant to each token, multiple attention heads allow the model to do this for different definitions of "relevance". Specifically, the query and key projection matrices,      W  Q     {\displaystyle W^{Q}}  ![{\displaystyle W^{Q}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/12fad024825b554ffb621d5385460ffce533f1bb) and      W  K     {\displaystyle W^{K}}  ![{\displaystyle W^{K}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/060b854f3f44615cefb8441780e6c31742f5dbd2) , which are involved in the attention score computation, defines the "relevance". Meanwhile, the value [projection matrix](./Projection_matrix)      W  V     {\displaystyle W^{V}}  ![{\displaystyle W^{V}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ef0a2e5fb27e9e6d1fc86901833d40d7e685a460), in combination with the part of the output projection matrix      W  O     {\displaystyle W^{O}}  ![{\displaystyle W^{O}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7f0f376fd1863b3a195a6bf34b56ff43ec5d695f), determines how the attended tokens influence what information is passed to subsequent layers and ultimately the output logits. In addition, the scope of attention, or the range of token relationships captured by each attention head, can expand as tokens pass through successive layers. This allows the model to capture more complex and long-range dependencies in deeper layers. Many transformer attention heads encode relevance relations that are meaningful to humans. For example, some attention heads can attend mostly to the next word, while others mainly attend from verbs to their direct objects.[[63]](./Transformer_(deep_learning)#cite_note-65) The computations for each attention head can be performed in [parallel](./Parallel_computing), which allows for fast processing. The outputs for the attention layer are concatenated to pass into the [feedforward neural network](./Feedforward_neural_network) layers.

 

Concretely, let the multiple attention heads be indexed by     i   {\displaystyle i}  ![{\displaystyle i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/add78d8608ad86e54951b8c8bd6c8d8416533d20), then we have     MultiheadAttention  ( Q , K , V ) =   Concat   i ∈ ∈  [  n  heads   ]   (  Attention  ( X  W  i   Q   , X  W  i   K   , X  W  i   V   ) )  W  O     {\displaystyle {\text{MultiheadAttention}}(Q,K,V)={\text{Concat}}_{i\in [n_{\text{heads}}]}({\text{Attention}}(XW_{i}^{Q},XW_{i}^{K},XW_{i}^{V}))W^{O}}  ![{\displaystyle {\text{MultiheadAttention}}(Q,K,V)={\text{Concat}}_{i\in [n_{\text{heads}}]}({\text{Attention}}(XW_{i}^{Q},XW_{i}^{K},XW_{i}^{V}))W^{O}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/266365c28eb10c53cf80eb9703447d3a8233414d) where the matrix     X   {\displaystyle X}  ![{\displaystyle X}](https://wikimedia.org/api/rest_v1/media/math/render/svg/68baa052181f707c662844a465bfeeb135e82bab) is the concatenation of word embeddings, and the matrices      W  i   Q   ,  W  i   K   ,  W  i   V     {\displaystyle W_{i}^{Q},W_{i}^{K},W_{i}^{V}}  ![{\displaystyle W_{i}^{Q},W_{i}^{K},W_{i}^{V}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3087f1739ddc134719d701163d3a75af985498b1) are "projection matrices" owned by individual attention head     i   {\displaystyle i}  ![{\displaystyle i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/add78d8608ad86e54951b8c8bd6c8d8416533d20), and      W  O     {\displaystyle W^{O}}  ![{\displaystyle W^{O}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7f0f376fd1863b3a195a6bf34b56ff43ec5d695f) is a final projection matrix owned by the whole multihead attention head.

 

It is theoretically possible for each attention head to have a different head dimension      d  head     {\displaystyle d_{\text{head}}}  ![{\displaystyle d_{\text{head}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/dc21fc3863abb48214d18eeb00efa0c3ae102896), but that is rarely the case in practice.

 

As an example, in the smallest GPT-2 model, there are only self-attention mechanisms. It has the following dimensions:     d  emb   = 768 ,  n  head   = 12 ,  d  head   = 64   {\displaystyle d_{\text{emb}}=768,n_{\text{head}}=12,d_{\text{head}}=64}  ![{\displaystyle d_{\text{emb}}=768,n_{\text{head}}=12,d_{\text{head}}=64}](https://wikimedia.org/api/rest_v1/media/math/render/svg/dd3bb7b2294f3753ad86ffa754b8840b002bd63f)Since     12 × ×  64 = 768   {\displaystyle 12\times 64=768}  ![{\displaystyle 12\times 64=768}](https://wikimedia.org/api/rest_v1/media/math/render/svg/27d429c67c8d2bb230091a87d8f4b000de427bb3), its output projection matrix      W  O   ∈ ∈    R   ( 12 × ×  64 ) × ×  768     {\displaystyle W^{O}\in \mathbb {R} ^{(12\times 64)\times 768}}  ![{\displaystyle W^{O}\in \mathbb {R} ^{(12\times 64)\times 768}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/be9cea988019d5b7d190ec9592f3c7912eb5efd9) is a square matrix.

 

#### Masked attention

 

The transformer architecture is constructed to calculate output tokens iteratively. Assuming     t = 0   {\displaystyle t=0}  ![{\displaystyle t=0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/43469ec032d858feae5aa87029e22eaaf0109e9c) refers to the calculation of the first output token     i = 0   {\displaystyle i=0}  ![{\displaystyle i=0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/31a682d568ee6a5fe51d76423186057f625ada5c), for step     t > 0   {\displaystyle t>0}  ![{\displaystyle t>0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/29a2960e88369263fe3cfe00ccbfeb83daee212a), the output token     i = 0   {\displaystyle i=0}  ![{\displaystyle i=0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/31a682d568ee6a5fe51d76423186057f625ada5c) shall remain constant. This ensures properties of the model similar to [autoregressive models](./Autoregressive_models).[[1]](./Transformer_(deep_learning)#cite_note-2017_Attention_Is_All_You_Need-1) Therefore, at every time step     t   {\displaystyle t}  ![{\displaystyle t}](https://wikimedia.org/api/rest_v1/media/math/render/svg/65658b7b223af9e1acc877d848888ecdb4466560), the calculation for all outputs     i   {\displaystyle i}  ![{\displaystyle i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/add78d8608ad86e54951b8c8bd6c8d8416533d20) should not have access to tokens at position     j   {\displaystyle j}  ![{\displaystyle j}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f461e54f5c093e92a55547b9764291390f0b5d0) for     j >= i   {\displaystyle j>=i}  ![{\displaystyle j>=i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0962580a4b2002cf7038e5f3529763c32044a040) (as it naturally is the case for time step     t = i   {\displaystyle t=i}  ![{\displaystyle t=i}](https://wikimedia.org/api/rest_v1/media/math/render/svg/211e2471862f32d3a3ab7718688b739056c20adc), when tokens     j > t   {\displaystyle j>t}  ![{\displaystyle j>t}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8b16985b39fa0ca2efcd29a2ea745312c6ee7915) are not yet calculated). This behavior may be accomplished before the softmax stage by adding a mask matrix     M   {\displaystyle M}  ![{\displaystyle M}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f82cade9898ced02fdd08712e5f0c0151758a0dd) that is     − −  ∞ ∞    {\displaystyle -\infty }  ![{\displaystyle -\infty }](https://wikimedia.org/api/rest_v1/media/math/render/svg/ca2608c4b5fd3bffc73585f8c67e379b4e99b6f1) at entries where the attention link must be cut, and     0   {\displaystyle 0}  ![{\displaystyle 0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2aae8864a3c1fec9585261791a809ddec1489950) at other places:         MaskedAttention  ( Q , K , V ) =  softmax   (  M +    Q  K   T       d  k       )  V       {\displaystyle {\begin{aligned}{\text{MaskedAttention}}(Q,K,V)={\text{softmax}}\left(M+{\frac {QK^{\mathrm {T} }}{\sqrt {d_{k}}}}\right)V\end{aligned}}}  ![{\displaystyle {\begin{aligned}{\text{MaskedAttention}}(Q,K,V)={\text{softmax}}\left(M+{\frac {QK^{\mathrm {T} }}{\sqrt {d_{k}}}}\right)V\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8d99a80dbf8da6e52c37ba3c9965387a19f82975) The following matrix is commonly used in decoder self-attention modules, called "causal masking":     M  causal   =   [    0   − −  ∞ ∞    − −  ∞ ∞    … …    − −  ∞ ∞      0   0   − −  ∞ ∞    … …    − −  ∞ ∞      0   0   0   … …    − −  ∞ ∞      ⋮ ⋮    ⋮ ⋮    ⋮ ⋮    ⋱ ⋱    ⋮ ⋮      0   0   0   … …    0    ]     {\displaystyle M_{\text{causal}}={\begin{bmatrix}0&-\infty &-\infty &\dots &-\infty \\0&0&-\infty &\dots &-\infty \\0&0&0&\dots &-\infty \\\vdots &\vdots &\vdots &\ddots &\vdots \\0&0&0&\dots &0\end{bmatrix}}}  ![{\displaystyle M_{\text{causal}}={\begin{bmatrix}0&-\infty &-\infty &\dots &-\infty \\0&0&-\infty &\dots &-\infty \\0&0&0&\dots &-\infty \\\vdots &\vdots &\vdots &\ddots &\vdots \\0&0&0&\dots &0\end{bmatrix}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/981c71d86645b9f71d314dc671903905c0c30a9a)

 

In words, it means that each token can pay attention to itself, and every token before it, but not any after it. A non-masked attention module can be thought of as a masked attention module where the mask has all entries zero. As an example of an uncommon use of mask matrix, the [XLNet](./XLNet) considers all masks of the form     P  M  causal    P  − −  1     {\displaystyle PM_{\text{causal}}P^{-1}}  ![{\displaystyle PM_{\text{causal}}P^{-1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/08430a7d86ac20f4e73548c704aff43512d88f46), where     P   {\displaystyle P}  ![{\displaystyle P}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b4dc73bf40314945ff376bd363916a738548d40a) is a random [permutation matrix](./Permutation_matrix).[[64]](./Transformer_(deep_learning)#cite_note-66)

 

### Encoder

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/9/92/Transformer%2C_one_encoder_block.png/250px-Transformer%2C_one_encoder_block.png)](./File:Transformer,_one_encoder_block.png)One encoder layer 

An encoder consists of an embedding layer, followed by multiple encoder layers.

 

Each encoder layer consists of two major components: a self-attention mechanism and a feed-forward layer. It takes an input as a sequence of input vectors, applies the self-attention mechanism, to produce an intermediate sequence of vectors, then applies the feed-forward layer for each vector individually. Schematically, we have:         given input vectors      h  0   ,  h  1   , … …       combine them into a matrix   H    =   [     h  0        h  1       ⋮ ⋮     ]        EncoderLayer  ( H )    =   [     FFN  (  MultiheadAttention  ( H , H , H  )  0   )      FFN  (  MultiheadAttention  ( H , H , H  )  1   )     ⋮ ⋮     ]         {\displaystyle {\begin{aligned}{\text{given input vectors }}&h_{0},h_{1},\dots \\{\text{combine them into a matrix }}H&={\begin{bmatrix}h_{0}\\h_{1}\\\vdots \end{bmatrix}}\\{\text{EncoderLayer}}(H)&={\begin{bmatrix}{\text{FFN}}({\text{MultiheadAttention}}(H,H,H)_{0})\\{\text{FFN}}({\text{MultiheadAttention}}(H,H,H)_{1})\\\vdots \end{bmatrix}}\\\end{aligned}}}  ![{\displaystyle {\begin{aligned}{\text{given input vectors }}&h_{0},h_{1},\dots \\{\text{combine them into a matrix }}H&={\begin{bmatrix}h_{0}\\h_{1}\\\vdots \end{bmatrix}}\\{\text{EncoderLayer}}(H)&={\begin{bmatrix}{\text{FFN}}({\text{MultiheadAttention}}(H,H,H)_{0})\\{\text{FFN}}({\text{MultiheadAttention}}(H,H,H)_{1})\\\vdots \end{bmatrix}}\\\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fd9a9a11a953fbb54e9a41092b2fd5e0e04da7e8)

 

where      FFN    {\displaystyle {\text{FFN}}}  ![{\displaystyle {\text{FFN}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ad653c6de611b65e2c8f58ac99a27bb4406b1ed8) stands for "feed-forward network". We can more succinctly write it as     EncoderLayer  ( H ) =  FFN  (  MultiheadAttention  ( H , H , H ) )   {\displaystyle {\text{EncoderLayer}}(H)={\text{FFN}}({\text{MultiheadAttention}}(H,H,H))}  ![{\displaystyle {\text{EncoderLayer}}(H)={\text{FFN}}({\text{MultiheadAttention}}(H,H,H))}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6c181dfb3b1a62638c2a05462827bbe405dc63d7)with the implicit convention that the      FFN    {\displaystyle {\text{FFN}}}  ![{\displaystyle {\text{FFN}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ad653c6de611b65e2c8f58ac99a27bb4406b1ed8) is applied to each row of the matrix individually.

 

The encoder layers are stacked. The first encoder layer takes the sequence of input vectors from the embedding layer, producing a sequence of vectors. This sequence of vectors is processed by the second encoder, and so on. The output from the final encoder layer is then used by the decoder.

 

As the encoder processes the entire input all at once, every token can attend to every other token (all-to-all attention), so there is no need for causal masking.

 

### Decoder

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/5/55/Transformer%2C_one_decoder_block.png/250px-Transformer%2C_one_decoder_block.png)](./File:Transformer,_one_decoder_block.png)One decoder layer 

A decoder consists of an embedding layer, followed by multiple decoder layers, followed by an un-embedding layer.

 

Each decoder consists of three major components: a causally masked self-attention mechanism, a cross-attention mechanism, and a feed-forward neural network. The decoder functions in a similar fashion to the encoder, but an additional attention mechanism is inserted which instead draws relevant information from the encodings generated by the encoders. This mechanism can also be called the *encoder–decoder attention*.[[1]](./Transformer_(deep_learning)#cite_note-2017_Attention_Is_All_You_Need-1)[[61]](./Transformer_(deep_learning)#cite_note-:1-63)

 

Like the first encoder, the first decoder takes positional information and embeddings of the output sequence as its input, rather than encodings. The transformer must not use the current or future output to predict an output, so the output sequence must be partially masked to prevent this reverse information flow.[[1]](./Transformer_(deep_learning)#cite_note-2017_Attention_Is_All_You_Need-1) This allows for [autoregressive](./Autoregressive_model) text generation. For decoding, all-to-all attention is inappropriate, because a token cannot attend to tokens not yet generated. Thus, the self-attention module in the decoder is causally masked.

 

In contrast, the cross-attention mechanism attends to the output vectors of the encoder, which is computed before the decoder starts decoding. Consequently, there is no need for masking in the cross-attention mechanism.

 

Schematically, we have:         H ′     =  MaskedMultiheadAttention  ( H , H , H )      DecoderLayer  ( H )    =  FFN  (  MultiheadAttention  (  H ′  ,  H  E   ,  H  E   ) )       {\displaystyle {\begin{aligned}H'&={\text{MaskedMultiheadAttention}}(H,H,H)\\{\text{DecoderLayer}}(H)&={\text{FFN}}({\text{MultiheadAttention}}(H',H^{E},H^{E}))\end{aligned}}}  ![{\displaystyle {\begin{aligned}H'&={\text{MaskedMultiheadAttention}}(H,H,H)\\{\text{DecoderLayer}}(H)&={\text{FFN}}({\text{MultiheadAttention}}(H',H^{E},H^{E}))\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7be5264b442c0f99ef6d3c6e8a8bccf78902ade6)where      H  E     {\displaystyle H^{E}}  ![{\displaystyle H^{E}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ca07d5c8fe45403067683c7e75a5e1e50d461dea) is the matrix with rows being the output vectors from the encoder.

 

The last decoder is followed by a final un-embedding layer to produce the output probabilities over the vocabulary. Then, one of the tokens is sampled according to the probability, and the decoder can be run again to produce the next token, etc., autoregressively generating output text.

 


