---
source: sources/wiki-Transformer_deep_learning_architecture.md
source_url: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)
chunk: 2/8
---

## History

 
|  | This section'stone or style may not reflect theencyclopedic toneused on Wikipedia.See Wikipedia'sguide to writing better articlesfor suggestions.(February 2026)(Learn how and when to remove this message) |
| --- | --- |

 See also: [Timeline of machine learning](./Timeline_of_machine_learning) 

### Predecessors

 

For many years, sequence modelling and generation was done by using plain [recurrent neural networks](./Recurrent_neural_network) (RNNs). A well-cited early example was the [Elman network](./Elman_network) (1990). In theory, the information from one token can propagate arbitrarily far down the sequence, but in practice the [vanishing-gradient problem](./Vanishing-gradient_problem) leaves the model's state at the end of a long sentence without precise, extractable information about preceding tokens.

 

A key breakthrough was [LSTM](./Long_short-term_memory) (originally described in a 1995 technical report and formally published in 1997),[[3]](./Transformer_(deep_learning)#cite_note-lstm1997-3)[[note 1]](./Transformer_(deep_learning)#cite_note-16) an RNN that introduced gating mechanisms to mitigate the vanishing gradient problem, allowing efficient learning of long-sequence modelling. One key architectural element was the use of *multiplicative gating units*, in which the outputs of some neurons modulate the outputs of others. These multiplicative units are conceptually distinct from the additive attention mechanism later introduced for sequence-to-sequence models.
[[16]](./Transformer_(deep_learning)#cite_note-17) Neural networks using multiplicative units were later called *sigma-pi networks*[[17]](./Transformer_(deep_learning)#cite_note-PDP-18) or *[higher-order networks](./Higher-order_neural_network?action=edit&redlink=1)*.[[18]](./Transformer_(deep_learning)#cite_note-19) LSTM became the standard architecture for long sequence modelling until the 2017 publication of transformers. However, LSTM still used sequential processing, like most other RNNs.[[note 2]](./Transformer_(deep_learning)#cite_note-20) Specifically, RNNs operate one token at a time from first to last; they cannot operate in parallel over all tokens in a sequence.

 

Modern transformers overcome this problem, but unlike RNNs, they require computation time that is [quadratic](./Quadratic_function) in the size of the context window. The linearly scaling [fast weight](./Fast_weight?action=edit&redlink=1) controller (1992) learns to compute a weight matrix for further processing depending on the input.[[19]](./Transformer_(deep_learning)#cite_note-transform19922-21) One of its two networks has "fast weights" or "dynamic links" (1981).[[20]](./Transformer_(deep_learning)#cite_note-malsburg1981-22)[[21]](./Transformer_(deep_learning)#cite_note-feldman1982-23)[[22]](./Transformer_(deep_learning)#cite_note-24) A slow neural network learns by gradient descent to generate keys and values for computing the weight changes of the fast neural network which computes answers to queries.[[19]](./Transformer_(deep_learning)#cite_note-transform19922-21) This was later shown to be equivalent to the unnormalized linear transformer.[[23]](./Transformer_(deep_learning)#cite_note-fastlinear20202-25)[[24]](./Transformer_(deep_learning)#cite_note-schlag20212-26)

 

### Attention with seq2seq

 Main article: [Seq2seq § History](./Seq2seq#History) 

The idea of encoder–decoder sequence transduction had been developed in the early 2010s; commonly cited as the originators that produced seq2seq are two concurrently published papers from 2014.[[25]](./Transformer_(deep_learning)#cite_note-:22-27)[[26]](./Transformer_(deep_learning)#cite_note-sequence-28)[*[original research?](./Wikipedia:No_original_research)*]

 

A 380M-parameter model for machine translation uses two [long short-term memories](./Long_short-term_memory) (LSTM).[[26]](./Transformer_(deep_learning)#cite_note-sequence-28) Its architecture consists of two parts. The *encoder* is an LSTM that takes in a sequence of tokens and turns it into a vector. The *decoder* is another LSTM that converts the vector into a sequence of tokens. Similarly, another 130M-parameter model used [gated recurrent units](./Gated_recurrent_unit) (GRU) instead of LSTM.[[25]](./Transformer_(deep_learning)#cite_note-:22-27) Later research showed that GRUs are neither better nor worse than LSTMs for seq2seq.[[27]](./Transformer_(deep_learning)#cite_note-MyUser_Arxiv.org_May_18_2016c-29)[[28]](./Transformer_(deep_learning)#cite_note-gruber_jockisch-30)

 

These early seq2seq models had no attention mechanism, and the state vector is accessible only after the *last* word of the source text was processed. Although in theory such a vector retains the information about the whole original sentence, in practice the information is poorly preserved. This is because the input is processed sequentially by one recurrent network into a *fixed*-size output vector, which is then processed by another recurrent network into an output. If the input is long, then the output vector would not be able to contain all relevant information, degrading the output. As evidence, reversing the input sentence improved seq2seq translation.[[29]](./Transformer_(deep_learning)#cite_note-31)

 

The *RNN search* model introduced an attention mechanism to seq2seq for machine translation to solve the bottleneck problem (of the *fixed-size* output vector), allowing the model to process long-distance dependencies more easily. The name is because it "emulates searching through a source sentence during decoding a translation".[[6]](./Transformer_(deep_learning)#cite_note-inventors-6)

 

The relative performances were compared between global (that of *RNN search*) and local (sliding window) attention model architectures for machine translation, finding that mixed attention had higher quality than global attention, while local attention reduced translation time.[[30]](./Transformer_(deep_learning)#cite_note-32)

 

In 2016, [Google Translate](./Google_Translate) was revamped to [Google Neural Machine Translation](./Google_Neural_Machine_Translation), which replaced the previous model based on [statistical machine translation](./Statistical_machine_translation). The new model was a seq2seq model where the encoder and the decoder were both 8 layers of bidirectional LSTM.[[31]](./Transformer_(deep_learning)#cite_note-Y4moj-33) It took nine months to develop, and it outperformed the statistical approach, which took ten years to develop.[[32]](./Transformer_(deep_learning)#cite_note-UJDu8-34)

 

### Parallelizing attention

 Main article: [Attention (machine learning) § History](./Attention_(machine_learning)#History) 

Seq2seq models with attention (including self-attention) still suffered from the same issue with recurrent networks, which is that they are hard to [parallelize](./Parallel_computing), which prevented them from being accelerated on GPUs. In 2016, *decomposable attention* applied a self-attention mechanism to [feedforward networks](./Feedforward_neural_network), which are easy to parallelize, and achieved [SOTA](./State_of_the_art) result in [textual entailment](./Textual_entailment) with an order of magnitude fewer parameters than LSTMs.[[33]](./Transformer_(deep_learning)#cite_note-35) One of its authors, Jakob Uszkoreit, suspected that attention *without* recurrence would be sufficient for language translation, thus the title "attention is *all* you need".[[34]](./Transformer_(deep_learning)#cite_note-:11-36) That hypothesis was against conventional wisdom at the time, and even his father [Hans Uszkoreit](./Hans_Uszkoreit), a well-known computational linguist, was skeptical.[[34]](./Transformer_(deep_learning)#cite_note-:11-36) In the same year, self-attention (called *intra-attention or* *intra-sentence attention*) was proposed for LSTMs.[[35]](./Transformer_(deep_learning)#cite_note-37)

 

On 2017-06-12, the original (100M-parameter) encoder–decoder transformer model was published in the "[Attention is all you need](./Attention_is_all_you_need)" paper. At the time, the focus of the research was on improving [seq2seq](./Seq2seq) for [machine translation](./Machine_translation), by removing its recurrence to process all tokens in parallel, but preserving its dot-product attention mechanism to keep its text processing performance.[[1]](./Transformer_(deep_learning)#cite_note-2017_Attention_Is_All_You_Need-1) This led to the introduction of a multi-head attention model that was easier to parallelize due to the use of independent heads and the lack of recurrence. Its parallelizability was an important factor to its widespread use in large neural networks.[[36]](./Transformer_(deep_learning)#cite_note-38)

 

### AI boom era

 

As early as spring 2017, even before the "Attention is all you need" preprint was published, one of the co-authors applied the "decoder-only" variation of the architecture to generate fictitious Wikipedia articles.[[37]](./Transformer_(deep_learning)#cite_note-39) Transformer architecture is now used alongside many [generative models](./Generative_artificial_intelligence) that contribute to the ongoing [AI boom](./AI_boom).

 

The "reference implementation" of the original Transformer was written in a TensorFlow library.[[38]](./Transformer_(deep_learning)#cite_note-40)[[39]](./Transformer_(deep_learning)#cite_note-41) In language modelling, [ELMo](./ELMo) (2018) was a bi-directional LSTM that produces contextualized [word embeddings](./Word_embedding), improving upon the line of research from [bag of words](./Bag-of-words_model) and [word2vec](./Word2vec). It was followed by [BERT](./BERT_(language_model)) (2018), an encoder-only transformer model.[[40]](./Transformer_(deep_learning)#cite_note-:03-42) In October 2019, Google started using BERT to process search queries.[[41]](./Transformer_(deep_learning)#cite_note-43) In 2020, Google Translate replaced the previous RNN-encoder–RNN-decoder model by a transformer-encoder–RNN-decoder model.[[42]](./Transformer_(deep_learning)#cite_note-gtrans-44)

 

Starting in 2018, the OpenAI [GPT series](./Generative_pre-trained_transformer) of decoder-only transformers became state of the art in [natural language generation](./Natural_language_generation). At the end of 2022, [ChatGPT](./ChatGPT), a chatbot based on a fine-tuned variant of GPT-3.5, became unexpectedly[[43]](./Transformer_(deep_learning)#cite_note-45)[[44]](./Transformer_(deep_learning)#cite_note-46) popular, triggering a boom around [large language models](./Large_language_model).[[45]](./Transformer_(deep_learning)#cite_note-gpt12-47)[[46]](./Transformer_(deep_learning)#cite_note-ngEG3-48)

 

Transformers have been applied in modalities beyond text. Four days after the publication of "Attention is All You Need", a [multimodal](./Multimodal_learning) transformer architecture, MultiModel, was published by most authors of that paper.[[47]](./Transformer_(deep_learning)#cite_note-49) Other examples include the [vision transformer](./Vision_transformer),[[48]](./Transformer_(deep_learning)#cite_note-auto2-50) speech recognition,[[49]](./Transformer_(deep_learning)#cite_note-Gulati2020-51) robotics,[[8]](./Transformer_(deep_learning)#cite_note-:10-8) and multimodal.[[50]](./Transformer_(deep_learning)#cite_note-choromanski2020-52) The vision transformer, in turn, stimulated new developments in [convolutional neural networks](./Convolutional_neural_network).[[51]](./Transformer_(deep_learning)#cite_note-53) Image and video generators like [DALL-E](./DALL-E) (2021), [Stable Diffusion 3](./Stable_Diffusion) (2024),[[52]](./Transformer_(deep_learning)#cite_note-:62-54) and [Sora](./Sora_(text-to-video_model)) (2024), use transformers to analyse input data (like text prompts) by breaking it down into "tokens" and then calculating the relevance between each token using self-attention, which helps the model understand the context and relationships within the data.

 

## Training

 

### Methods for stabilizing training

 

The plain transformer architecture had difficulty in converging. In the original paper,[[1]](./Transformer_(deep_learning)#cite_note-2017_Attention_Is_All_You_Need-1) the authors recommended using [learning rate](./Learning_rate) warmup. That is, the learning rate should linearly scale up from 0 to maximal value for the first part of the training (usually recommended to be 2% of the total number of training steps), before decaying again.

 

A 2020 paper found that using [layer normalization](./Layer_normalization) *before* (instead of after) multihead attention and feedforward layers stabilizes training, not requiring learning rate warmup.[[53]](./Transformer_(deep_learning)#cite_note-auto1-55) This is the "pre-LN Transformer" and is more commonly used, compared to the original "post-LN Transformer".

 

### Pretrain-finetune

 

Transformers typically are first pretrained by [self-supervised learning](./Self-supervised_learning) on a large generic dataset, followed by [supervised](./Supervised_learning) [fine-tuning](./Fine-tuning_(deep_learning)) on a small task-specific dataset. The pretrain dataset is typically an unlabeled large corpus, such as [The Pile](./The_Pile_(dataset)). Tasks for pretraining and fine-tuning commonly include:

 
- [language modeling](./Language_modeling)[[15]](./Transformer_(deep_learning)#cite_note-:6-15)
- next-sentence prediction[[15]](./Transformer_(deep_learning)#cite_note-:6-15)
- [question answering](./Question_answering)[[4]](./Transformer_(deep_learning)#cite_note-:7-4)
- [reading comprehension](./Natural-language_understanding)
- [sentiment analysis](./Sentiment_analysis)[[1]](./Transformer_(deep_learning)#cite_note-2017_Attention_Is_All_You_Need-1)
- [paraphrasing](./Text_Summaries)[[1]](./Transformer_(deep_learning)#cite_note-2017_Attention_Is_All_You_Need-1)

 

The [T5 transformer](./T5_(language_model)) report[[54]](./Transformer_(deep_learning)#cite_note-Raffel_Shazeer_2020_Exploring_the_Limits-56) documents a large number of [natural language](./Natural_language) pretraining tasks. Some examples are:

 
- restoring or repairing incomplete or corrupted text. For example, the input, *"Thank you ~~ me to your party ~~ week",* might generate the output, *"Thank you **for inviting** me to your party **last** week".*
- translation between natural languages ([machine translation](./Machine_translation))
- judging the pragmatic acceptability of natural language. For example, the following sentence might be judged "not acceptable",[[55]](./Transformer_(deep_learning)#cite_note-57) because even though it is syntactically well-formed, it is improbable in ordinary human usage: *The course is jumping well.*

 

Note that while each of these tasks is trivial or obvious for human native speakers of the language (or languages), they have typically proved challenging for previous generations of machine learning architecture.

 

### Tasks

 See also: [Large language model § Evaluation](./Large_language_model#Evaluation) 

In general, there are 3 classes of language modelling tasks: "masked",[[56]](./Transformer_(deep_learning)#cite_note-:5-58) "autoregressive",[[57]](./Transformer_(deep_learning)#cite_note-:8-59) and "prefixLM".[[58]](./Transformer_(deep_learning)#cite_note-:4-60) These classes are independent of a specific modeling architecture such as transformer, but they are often discussed in the context of transformer.

 

In a masked task,[[56]](./Transformer_(deep_learning)#cite_note-:5-58) one or more of the tokens is masked out, and the model would produce a probability distribution predicting what the masked-out tokens are based on the context. The [loss function](./Loss_function) for the task is typically sum of [log-perplexities](./Perplexity) for the masked-out tokens:      Loss  = − −   ∑ ∑   t ∈ ∈   masked tokens    ln ⁡ ⁡  (  probability of   t   conditional on its context  )   {\displaystyle {\text{Loss}}=-\sum _{t\in {\text{masked tokens}}}\ln({\text{probability of }}t{\text{ conditional on its context}})}  ![{\displaystyle {\text{Loss}}=-\sum _{t\in {\text{masked tokens}}}\ln({\text{probability of }}t{\text{ conditional on its context}})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/55f0855cde2d171c96b77251ce43de9ee3cfd4e8)and the model is trained to minimize this loss function. The [BERT series of models](./BERT_(language_model)) are trained for masked token prediction and another task.

 

In an autoregressive task,[[57]](./Transformer_(deep_learning)#cite_note-:8-59) the entire sequence is masked at first, and the model produces a probability distribution for the first token. Then the first token is revealed and the model predicts the second token, and so on. The loss function for the task is still typically the same. The [GPT series of models](./Generative_pre-trained_transformer) are trained by autoregressive tasks.

 

In a prefixLM task,[[58]](./Transformer_(deep_learning)#cite_note-:4-60) the sequence is divided into two parts. The first part is presented as context, and the model predicts the first token of the second part. Then that would be revealed, and the model predicts the second token, and so on. The loss function for the task is still typically the same. The [T5 series of models](./T5_(language_model)) are trained by prefixLM tasks.

 

Note that "masked" as in "masked language modelling" is not "masked" as in "[masked attention](./Transformer_(deep_learning)#Masked_attention)", and "prefixLM" as in 
"prefix language modeling" is not "prefixLM" as in " [prefix language model](./Transformer_(deep_learning)#prefixLM)".

 


