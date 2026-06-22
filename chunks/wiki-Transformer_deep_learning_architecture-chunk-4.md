---
source: sources/wiki-Transformer_deep_learning_architecture.md
source_url: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)
chunk: 4/8
---

## Full transformer architecture

 

### Sublayers

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/7/7a/Transformer%2C_stacked_multilayers.png/250px-Transformer%2C_stacked_multilayers.png)](./File:Transformer,_stacked_multilayers.png)(a) One encoder layer and one decoder layer. (b) Two encoder layers and two decoder layers. The sublayers are labelled as well. 

Each encoder layer contains 2 sublayers: the self-attention and the feedforward network. Each decoder layer contains 3 sublayers: the causally masked self-attention, the cross-attention, and the feedforward network.

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/4/4d/Transformer_encoder%2C_with_norm-first_and_norm-last.png/250px-Transformer_encoder%2C_with_norm-first_and_norm-last.png)](./File:Transformer_encoder,_with_norm-first_and_norm-last.png)Transformer encoder with norm-first and norm-last [![](//upload.wikimedia.org/wikipedia/commons/thumb/c/c9/Transformer_decoder%2C_with_norm-first_and_norm-last.png/250px-Transformer_decoder%2C_with_norm-first_and_norm-last.png)](./File:Transformer_decoder,_with_norm-first_and_norm-last.png)Transformer decoder with norm-first and norm-last [![](//upload.wikimedia.org/wikipedia/commons/thumb/3/34/Transformer%2C_full_architecture.png/250px-Transformer%2C_full_architecture.png)](./File:Transformer,_full_architecture.png)Block diagram for the full transformer architecture[![](//upload.wikimedia.org/wikipedia/commons/thumb/b/ba/Transformer%2C_schematic_object_hierarchy%2C_for_implementation_in_object-oriented_programming.png/250px-Transformer%2C_schematic_object_hierarchy%2C_for_implementation_in_object-oriented_programming.png)](./File:Transformer,_schematic_object_hierarchy,_for_implementation_in_object-oriented_programming.png)Schematic [object hierarchy](./Object_hierarchy) for the full transformer architecture, in [object-oriented programming](./Object-oriented_programming) style

The final points of detail are the [residual connections](./Residual_neural_network) and [layer normalization](./Layer_normalization), (denoted as "LayerNorm", or "LN" in the following), which while conceptually unnecessary, are necessary for numerical stability and convergence.

 

The residual connections are introduced to avoid vanishing gradient issues and stabilize the training process. They can be expressed by     x ↦ ↦  F ( x ) + x   {\displaystyle x\mapsto F(x)+x}  ![{\displaystyle x\mapsto F(x)+x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/719f3aa9beae48510eaf9354754057a463770bc0), where     F   {\displaystyle F}  ![{\displaystyle F}](https://wikimedia.org/api/rest_v1/media/math/render/svg/545fd099af8541605f7ee55f08225526be88ce57) is a given component of the transformer. Adding the input     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4) can preserve the input information and avoid issues when the gradient of     F ( x )   {\displaystyle F(x)}  ![{\displaystyle F(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/71a82805d469cdfa7856c11d6ee756acd1dc7174) is close to zero.

 

Similarly to how the feedforward network modules are applied individually to each vector, the LayerNorm is also applied individually to each vector.

 

There are two common conventions in use: the *post-LN* and the *pre-LN* convention. In the post-LN convention, the output of each sublayer is      L a y e r N o r m  ( x +  S u b l a y e r  ( x ) )   {\displaystyle \mathrm {LayerNorm} (x+\mathrm {Sublayer} (x))}  ![{\displaystyle \mathrm {LayerNorm} (x+\mathrm {Sublayer} (x))}](https://wikimedia.org/api/rest_v1/media/math/render/svg/dbfd5ef346a396976d4b6cea30408e27192b4ca8)where      S u b l a y e r  ( x )   {\displaystyle \mathrm {Sublayer} (x)}  ![{\displaystyle \mathrm {Sublayer} (x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a8c8327dbca36935f9f5f157967e6df5603880c9) is the function implemented by the sublayer itself.

 

In the pre-LN convention, the output of each sublayer is    x +  S u b l a y e r  (  L a y e r N o r m  ( x ) )   {\displaystyle x+\mathrm {Sublayer} (\mathrm {LayerNorm} (x))}  ![{\displaystyle x+\mathrm {Sublayer} (\mathrm {LayerNorm} (x))}](https://wikimedia.org/api/rest_v1/media/math/render/svg/14a098c27734ee53b1efbf41656e1797f9ed2874)The original 2017 transformer used the post-LN convention. It was difficult to train and required careful hyperparameter tuning and a "warm-up" in learning rate, where it starts small and gradually increases. The pre-LN convention, proposed several times in 2018,[[65]](./Transformer_(deep_learning)#cite_note-67) was found to be easier to train, requiring no warm-up, leading to faster convergence.[[53]](./Transformer_(deep_learning)#cite_note-auto1-55)

 

### Pseudocode

 

The following is the pseudocode for a standard pre-LN encoder–decoder transformer, adapted from *Formal Algorithms for Transformers*[[66]](./Transformer_(deep_learning)#cite_note-68)

 
```
input: Encoder input t_e
       Decoder input t_d
output: Array of probability distributions, with shape (decoder vocabulary size x length(decoder output sequence))

/* encoder */
z_e ← encoder.tokenizer(t_e)

for each t in 1:length(z_e) do
    z_e[t] ← encoder.embedding(z_e[t]) + encoder.positional_embedding(t)

for each l in 1:length(encoder.layers) do
    layer ← encoder.layers[l]

    /* first sublayer */
    z_e_copy ← copy(z_e)
    for each t in 1:length(z_e) do
        z_e[t] ← layer.layer_norm(z_e[t])
    z_e ← layer.multihead_attention(z_e, z_e, z_e)
    for each t in 1:length(z_e) do
        z_e[t] ← z_e[t] + z_e_copy[t]

    /* second sublayer */
    z_e_copy ← copy(z_e)
    for each t in 1:length(z_e) do
        z_e[t] ← layer.layer_norm(z_e[t])
    z_e ← layer.feedforward(z_e)
    for each t in 1:length(z_e) do
        z_e[t] ← z_e[t] + z_e_copy[t]

for each t in 1:length(z_e) do
    z_e[t] ← encoder.final_layer_norm(z_e[t])

/* decoder */
z_d ← decoder.tokenizer(t_d)

for each t in 1:length(z_d) do
    z_d[t] ← decoder.embedding(z_d[t]) + decoder.positional_embedding(t)

for each l in 1:length(decoder.layers) do
        layer ← decoder.layers[l]

        /* first sublayer */
        z_d_copy ← copy(z_d)
        for each t in 1:length(z_d) do
            z_d[t] ← layer.layer_norm(z_d[t])
        z_d ← layer.masked_multihead_attention(z_d, z_d, z_d)
        for each t in 1:length(z_d) do
            z_d[t] ← z_d[t] + z_d_copy[t]

        /* second sublayer */
        z_d_copy ← copy(z_d)
        for each t in 1:length(z_d) do
            z_d[t] ← layer.layer_norm(z_d[t])
        z_d ← layer.multihead_attention(z_d, z_e, z_e) 
       for each t in 1:length(z_d) do
           z_d[t] ← z_d[t] + z_d_copy[t]

        /* third sublayer */
        z_d_copy ← copy(z_d)
        for each t in 1:length(z_d) do
            z_d[t] ← layer.layer_norm(z_d[t])
        z_d ← layer.feedforward(z_d)
        for each t in 1:length(z_d) do
            z_d[t] ← z_d[t] + z_d_copy[t]

z_d ← decoder.final_layer_norm(z_d)

output_distributions ← []
for each t in 1:length(z_d) do
    output_distributions.append(decoder.unembed(z_d[t]))

return output_distributions
```
 

### Terminology

 

The transformer architecture, being modular, allows variations. Several common variations are described here.[[54]](./Transformer_(deep_learning)#cite_note-Raffel_Shazeer_2020_Exploring_the_Limits-56)

 

An "encoder-only" transformer applies the encoder to map an input text into a sequence of vectors that represent the input text. This is usually used for text embedding and [representation learning](./Feature_learning) for downstream applications. [BERT](./BERT_(language_model)) is encoder-only. They are less often used currently, as they were found to be not significantly better than training an encoder–decoder transformer, then taking just the encoder.[[58]](./Transformer_(deep_learning)#cite_note-:4-60) They are also referred to as "all-to-all" or "BERT-like".

 

A "decoder-only" transformer is not literally decoder-only, since without an encoder, the cross-attention mechanism has nothing to attend to. Thus, the decoder layers in a decoder-only transformer is composed of just two sublayers: the causally masked self-attention, and the feedforward network. This is usually used for [text generation](./Natural_language_generation) and [instruction following](./Large_language_model#Instruction_tuning). The models in the [GPT series](./Generative_pre-trained_transformer) and [Chinchilla series](./Chinchilla_(language_model)) are decoder-only. They are also referred to as "autoregressive" or "causal".

 

An "encoder–decoder" transformer is generally the same as the original transformer, with 2 sublayers per encoder layer and 3 sublayers per decoder layer, etc. They might have minor architectural improvements, such as [alternative activation functions](./Transformer_(deep_learning)#Alternative_activation_functions), [changing the location of normalization](./Transformer_(deep_learning)#pre-LN), etc. This is also usually used for text generation and instruction following. The models in the [T5 series](./T5_(language_model)) are encoder–decoder.[[54]](./Transformer_(deep_learning)#cite_note-Raffel_Shazeer_2020_Exploring_the_Limits-56)

 

A "prefixLM" (prefix language model) is a decoder-only architecture, but with prefix masking, which is different from causal masking. Specifically, it has mask of the form[[54]](./Transformer_(deep_learning)#cite_note-Raffel_Shazeer_2020_Exploring_the_Limits-56): Figure 3      M  prefixLM   =   [     0    − −  ∞ ∞       0     M  causal      ]     {\displaystyle M_{\text{prefixLM}}={\begin{bmatrix}\mathbf {0} &-\infty \\\mathbf {0} &M_{\text{causal}}\end{bmatrix}}}  ![{\displaystyle M_{\text{prefixLM}}={\begin{bmatrix}\mathbf {0} &-\infty \\\mathbf {0} &M_{\text{causal}}\end{bmatrix}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/55dde3d4ea5e6d9e321ca34ebfdd37268558e1aa)where the first columns correspond to the "prefix", and the subsequent columns correspond to the autoregressively generated text based on the prefix. They resemble encoder–decoder models, but has less "sparsity". Such models are rarely used, though they are cited as theoretical possibilities and benchmarked comparisons.[[58]](./Transformer_(deep_learning)#cite_note-:4-60)

 

There are also mixed seq2seq models. For example, in 2020, Google Translate replaced the previous RNN-encoder–RNN-decoder model with a transformer-encoder–RNN-decoder model, as transformer-based decoders did not appear to significantly increase quality unlike the encoder, while the RNN decoder was much faster.[[42]](./Transformer_(deep_learning)#cite_note-gtrans-44)

 


