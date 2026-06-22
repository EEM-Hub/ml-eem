---
source: sources/wiki-Recurrent_neural_network.md
source_url: https://en.wikipedia.org/wiki/Recurrent_neural_network
chunk: 2/7
---

## Configurations

 Main article: [Layer (deep learning)](./Layer_(deep_learning)) 

An RNN-based model can be factored into two parts: configuration and architecture. Multiple RNNs can be combined in a data flow, and the data flow itself is the configuration. Each RNN itself may have any architecture, including LSTM, GRU, etc.

 

### Standard

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/b/b5/Recurrent_neural_network_unfold.svg/250px-Recurrent_neural_network_unfold.svg.png)](./File:Recurrent_neural_network_unfold.svg)Compressed (left) and unfolded (right) basic recurrent neural network 

RNNs come in many variants. Abstractly speaking, an RNN is a function      f  θ θ      {\displaystyle f_{\theta }}  ![{\displaystyle f_{\theta }}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9874ae06066a2250709085e0fb521eebff2c2fb7) of type     (  x  t   ,  h  t   ) ↦ ↦  (  y  t   ,  h  t + 1   )   {\displaystyle (x_{t},h_{t})\mapsto (y_{t},h_{t+1})}  ![{\displaystyle (x_{t},h_{t})\mapsto (y_{t},h_{t+1})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/daede0f2ff9c38ad773254c9b68cdf2846a65de6), where

 
-      x  t     {\displaystyle x_{t}}  ![{\displaystyle x_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f279a30bc8eabc788f3fe81c9cfb674e72e858db): input vector;
-      h  t     {\displaystyle h_{t}}  ![{\displaystyle h_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e8dbf3d8bfe322f68ff6400385578f8d78e1ba7c): hidden vector;
-      y  t     {\displaystyle y_{t}}  ![{\displaystyle y_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0fe9554452b93508c9d2479414a45981ecc75a2d): output vector;
-     θ θ    {\displaystyle \theta }  ![{\displaystyle \theta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/6e5ab2664b422d53eb0c7df3b87e1360d75ad9af): neural network parameters.

 

In words, it is a neural network that maps an input      x  t     {\displaystyle x_{t}}  ![{\displaystyle x_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f279a30bc8eabc788f3fe81c9cfb674e72e858db) into an output      y  t     {\displaystyle y_{t}}  ![{\displaystyle y_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0fe9554452b93508c9d2479414a45981ecc75a2d), with the hidden vector      h  t     {\displaystyle h_{t}}  ![{\displaystyle h_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e8dbf3d8bfe322f68ff6400385578f8d78e1ba7c) playing the role of "memory", a partial record of all previous input-output pairs. At each step, it transforms input to an output, and modifies its "memory" to help it to better perform future processing.

 

The illustration to the right may be misleading to many because practical neural network topologies are frequently organized in "layers" and the drawing gives that appearance. However, what appears to be [layers](./Layer_(deep_learning)) are, in fact, different steps in time, "unfolded" to produce the appearance of [layers](./Layer_(deep_learning)).

 

### Stacked RNN

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/e/e3/Stacked_RNN.png/250px-Stacked_RNN.png)](./File:Stacked_RNN.png)Stacked RNN

A **stacked RNN**, or **deep RNN**, is composed of multiple RNNs stacked one above the other. Abstractly, it is structured as follows

 
1. Layer 1 has hidden vector      h  1 , t     {\displaystyle h_{1,t}}  ![{\displaystyle h_{1,t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/41d508e0dc0b303c58fa98ac785044f0d302024c), parameters      θ θ   1     {\displaystyle \theta _{1}}  ![{\displaystyle \theta _{1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7f84b9443d095623e02fd287cd095123d70b0278), and maps      f   θ θ   1     : (  x  0 , t   ,  h  1 , t   ) ↦ ↦  (  x  1 , t   ,  h  1 , t + 1   )   {\displaystyle f_{\theta _{1}}:(x_{0,t},h_{1,t})\mapsto (x_{1,t},h_{1,t+1})}  ![{\displaystyle f_{\theta _{1}}:(x_{0,t},h_{1,t})\mapsto (x_{1,t},h_{1,t+1})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3d6c58b510835cafedab19747e1a57a95bfbbc28).
2. Layer 2 has hidden vector      h  2 , t     {\displaystyle h_{2,t}}  ![{\displaystyle h_{2,t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/30a4a50b190be9e0f1df9770bb3d42879f564aff), parameters      θ θ   2     {\displaystyle \theta _{2}}  ![{\displaystyle \theta _{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0ed6ea624b20b153403979ffaf5434fc36de2990), and maps      f   θ θ   2     : (  x  1 , t   ,  h  2 , t   ) ↦ ↦  (  x  2 , t   ,  h  2 , t + 1   )   {\displaystyle f_{\theta _{2}}:(x_{1,t},h_{2,t})\mapsto (x_{2,t},h_{2,t+1})}  ![{\displaystyle f_{\theta _{2}}:(x_{1,t},h_{2,t})\mapsto (x_{2,t},h_{2,t+1})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c936d144b72db51f32a1fc4af94e60849bfe2ffe).
3. ...
4. Layer     n   {\displaystyle n}  ![{\displaystyle n}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a601995d55609f2d9f5e233e36fbe9ea26011b3b) has hidden vector      h  n , t     {\displaystyle h_{n,t}}  ![{\displaystyle h_{n,t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/bc5bbbf6e890a622b1a1a9b492ab4f0b1c01d843), parameters      θ θ   n     {\displaystyle \theta _{n}}  ![{\displaystyle \theta _{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/79cc00920259451fc1a684ba7350b6f93ce4f08a), and maps      f   θ θ   n     : (  x  n − −  1 , t   ,  h  n , t   ) ↦ ↦  (  x  n , t   ,  h  n , t + 1   )   {\displaystyle f_{\theta _{n}}:(x_{n-1,t},h_{n,t})\mapsto (x_{n,t},h_{n,t+1})}  ![{\displaystyle f_{\theta _{n}}:(x_{n-1,t},h_{n,t})\mapsto (x_{n,t},h_{n,t+1})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ea881abbb0a57bb90425e6fe8c2cee342f8bef1c).

 

Each layer operates as a stand-alone RNN, and each layer's output sequence is used as the input sequence to the layer above. There is no conceptual limit to the depth of stacked RNN.

 

### Bidirectional

 Main article: [Bidirectional recurrent neural networks](./Bidirectional_recurrent_neural_networks) [![](//upload.wikimedia.org/wikipedia/commons/thumb/f/f0/Bidirectional_RNN.png/250px-Bidirectional_RNN.png)](./File:Bidirectional_RNN.png)Bidirectional RNN

A **bidirectional RNN** (biRNN) is composed of two RNNs, one processing the input sequence in one direction, and another in the opposite direction. Abstractly, it is structured as follows:

 
- The forward RNN processes in one direction:      f  θ θ    (  x  0   ,  h  0   ) = (  y  0   ,  h  1   ) ,  f  θ θ    (  x  1   ,  h  1   ) = (  y  1   ,  h  2   ) , … …    {\displaystyle f_{\theta }(x_{0},h_{0})=(y_{0},h_{1}),f_{\theta }(x_{1},h_{1})=(y_{1},h_{2}),\dots }  ![{\displaystyle f_{\theta }(x_{0},h_{0})=(y_{0},h_{1}),f_{\theta }(x_{1},h_{1})=(y_{1},h_{2}),\dots }](https://wikimedia.org/api/rest_v1/media/math/render/svg/f6129c199ab8b86d643b7c35e4655a42e36c0ea6)
- The backward RNN processes in the opposite direction:     f   θ θ  ′   ′  (  x  N   ,  h  N  ′  ) = (  y  N  ′  ,  h  N − −  1  ′  ) ,  f   θ θ  ′   ′  (  x  N − −  1   ,  h  N − −  1  ′  ) = (  y  N − −  1  ′  ,  h  N − −  2  ′  ) , … …    {\displaystyle f'_{\theta '}(x_{N},h_{N}')=(y'_{N},h_{N-1}'),f'_{\theta '}(x_{N-1},h_{N-1}')=(y'_{N-1},h_{N-2}'),\dots }  ![{\displaystyle f'_{\theta '}(x_{N},h_{N}')=(y'_{N},h_{N-1}'),f'_{\theta '}(x_{N-1},h_{N-1}')=(y'_{N-1},h_{N-2}'),\dots }](https://wikimedia.org/api/rest_v1/media/math/render/svg/2f5f33f98c860de2b99b57d62dd99c59ebc80fc0)

 

The two output sequences are then concatenated to give the total output:     ( (  y  0   ,  y  0  ′  ) , (  y  1   ,  y  1  ′  ) , … …  , (  y  N   ,  y  N  ′  ) )   {\displaystyle ((y_{0},y_{0}'),(y_{1},y_{1}'),\dots ,(y_{N},y_{N}'))}  ![{\displaystyle ((y_{0},y_{0}'),(y_{1},y_{1}'),\dots ,(y_{N},y_{N}'))}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6b4f2aede172075e4a2d3ef5c525448fb5e241ae).

 

Bidirectional RNN allows the model to process a token both in the context of what came before it and what came after it. By stacking multiple bidirectional RNNs together, the model can process a token increasingly contextually. The [ELMo](./ELMo) model (2018)[[48]](./Recurrent_neural_network#cite_note-48) is a stacked bidirectional [LSTM](./Long_short-term_memory) which takes character-level as inputs and produces word-level embeddings.

 

### Encoder-decoder

 Main article: [seq2seq](./Seq2seq) [![](//upload.wikimedia.org/wikipedia/commons/thumb/7/7c/Decoder_RNN.png/250px-Decoder_RNN.png)](./File:Decoder_RNN.png)A decoder without an encoder [![](//upload.wikimedia.org/wikipedia/commons/thumb/7/72/Seq2seq_RNN_encoder-decoder_with_attention_mechanism%2C_training_and_inferring.png/250px-Seq2seq_RNN_encoder-decoder_with_attention_mechanism%2C_training_and_inferring.png)](./File:Seq2seq_RNN_encoder-decoder_with_attention_mechanism,_training_and_inferring.png)Encoder-decoder RNN without attention mechanism [![](//upload.wikimedia.org/wikipedia/commons/thumb/c/c7/Seq2seq_RNN_encoder-decoder_with_attention_mechanism%2C_training.png/250px-Seq2seq_RNN_encoder-decoder_with_attention_mechanism%2C_training.png)](./File:Seq2seq_RNN_encoder-decoder_with_attention_mechanism,_training.png)Encoder-decoder RNN with attention mechanism 

Two RNNs can be run front-to-back in an **encoder-decoder** configuration. The encoder RNN processes an input sequence into a sequence of hidden vectors, and the decoder RNN processes the sequence of hidden vectors to an output sequence, with an optional [attention mechanism](./Attention_(machine_learning)). This was used to construct state of the art [neural machine translators](./Neural_machine_translation) during the 2014–2017 period. This was an instrumental step towards the development of [transformers](./Transformer_(deep_learning_architecture)).[[49]](./Recurrent_neural_network#cite_note-49)

 

### PixelRNN

 

An RNN may process data with more than one dimension. PixelRNN processes two-dimensional data, with many possible directions.[[50]](./Recurrent_neural_network#cite_note-50) For example, the row-by-row direction processes an     n × ×  n   {\displaystyle n\times n}  ![{\displaystyle n\times n}](https://wikimedia.org/api/rest_v1/media/math/render/svg/59d2b4cb72e304526cf5b5887147729ea259da78) grid of vectors      x  i , j     {\displaystyle x_{i,j}}  ![{\displaystyle x_{i,j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fd698068c9322e82d11cb2bc02cb2f51739a2cc0) in the following order:      x  1 , 1   ,  x  1 , 2   , … …  ,  x  1 , n   ,  x  2 , 1   ,  x  2 , 2   , … …  ,  x  2 , n   , … …  ,  x  n , n     {\displaystyle x_{1,1},x_{1,2},\dots ,x_{1,n},x_{2,1},x_{2,2},\dots ,x_{2,n},\dots ,x_{n,n}}  ![{\displaystyle x_{1,1},x_{1,2},\dots ,x_{1,n},x_{2,1},x_{2,2},\dots ,x_{2,n},\dots ,x_{n,n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6b9de0f040f133e51ec188e98ed9541a98705908)The **diagonal BiLSTM** uses two LSTMs to process the same grid. One processes it from the top-left corner to the bottom-right, such that it processes      x  i , j     {\displaystyle x_{i,j}}  ![{\displaystyle x_{i,j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fd698068c9322e82d11cb2bc02cb2f51739a2cc0) depending on its hidden state and cell state on the top and the left side:      h  i − −  1 , j   ,  c  i − −  1 , j     {\displaystyle h_{i-1,j},c_{i-1,j}}  ![{\displaystyle h_{i-1,j},c_{i-1,j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ec3abb324832ed758f9376976cae69702169a7df) and      h  i , j − −  1   ,  c  i , j − −  1     {\displaystyle h_{i,j-1},c_{i,j-1}}  ![{\displaystyle h_{i,j-1},c_{i,j-1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/82483890bf0f5558df1cee92b40c57d6c0e29228). The other processes it from the top-right corner to the bottom-left.

 


