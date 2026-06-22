---
source: sources/wiki-Natural_language_processing.md
source_url: https://en.wikipedia.org/wiki/Natural_language_processing
chunk: 3/5
---

## General tendencies and (possible) future directions

 

Based on long-standing trends in the field, it is possible to extrapolate future directions of NLP. As of 2020, three trends among the topics of the long-standing series of CoNLL Shared Tasks can be observed:[[49]](./Natural_language_processing#cite_note-49)

 
- Interest in increasingly abstract, "cognitive" aspects of natural language (1999–2001: shallow parsing, 2002–03: named entity recognition, 2006–09/2017–18: dependency syntax, 2004–05/2008–09 semantic role labelling, 2011–12 coreference, 2015–16: discourse parsing, 2019: semantic parsing).
- Increasing interest in multilinguality, and, potentially, multimodality (English since 1999; Spanish, Dutch since 2002; German since 2003; Bulgarian, Danish, Japanese, Portuguese, Slovenian, Swedish, Turkish since 2006; Basque, Catalan, Chinese, Greek, Hungarian, Italian, Turkish since 2007; Czech since 2009; Arabic since 2012; 2017: 40+ languages; 2018: 60+/100+ languages)
- Elimination of symbolic representations (rule-based over supervised towards weakly supervised methods, representation learning and end-to-end systems)

 

### Cognition

 

Most higher-level NLP applications involve aspects that emulate intelligent behavior and apparent comprehension of natural language. More broadly speaking, the technical operationalization of increasingly advanced aspects of cognitive behavior represents one of the developmental trajectories of NLP(see trends among CoNLL shared tasks above).

 

[Cognition](./Cognition) refers to "the mental action or process of acquiring knowledge and understanding through thought, experience, and the senses."[[50]](./Natural_language_processing#cite_note-50) [Cognitive science](./Cognitive_science) is the interdisciplinary, scientific study of the mind and its processes.[[51]](./Natural_language_processing#cite_note-51) [Cognitive linguistics](./Cognitive_linguistics) is an interdisciplinary branch of linguistics, combining knowledge and research from both psychology and linguistics.[[52]](./Natural_language_processing#cite_note-52) Especially during the age of [symbolic NLP](./Natural_language_processing#Symbolic_NLP_(1950s_–_early_1990s)), the area of computational linguistics maintained strong ties with cognitive studies.

 

As an example, [George Lakoff](./George_Lakoff) offers a methodology to build natural language processing (NLP) algorithms through the perspective of cognitive science, along with the findings of cognitive linguistics,[[53]](./Natural_language_processing#cite_note-53) with two defining aspects:

 
1. Apply the theory of [conceptual metaphor](./Conceptual_metaphor), explained by Lakoff as "the understanding of one idea, in terms of another" which provides an idea of the intent of the author.[[54]](./Natural_language_processing#cite_note-54) For example, consider the English word *big*. When used in a comparison ("That is a big tree"), the author intends to imply that the tree is *physically large* relative to other trees or the author's experience. When used metaphorically ("Tomorrow is a big day"), the author intends to imply *importance*. The intent behind other usages, like in "She is a big person", will remain somewhat ambiguous to a person and a cognitive NLP algorithm alike without additional information.
2. Assign relative measures of meaning to a word, phrase, sentence or piece of text based on the information presented before and after the piece of text being analyzed, e.g., by means of a [probabilistic context-free grammar](./Probabilistic_context-free_grammar) (PCFG). The mathematical equation for such algorithms is presented in [US Patent 9269353](https://worldwide.espacenet.com/patent/search/family/055314712/publication/US9269353B1?q=pn%3DUS9269353):[[55]](./Natural_language_processing#cite_note-55)

      R M M ( t o k e  n  N   )  =  P M M ( t o k e  n  N   )  × ×    1  2 d     (   ∑ ∑   i = − −  d   d    ( ( P M M ( t o k e  n  N   )  × ×   P F ( t o k e  n  N − −  i   , t o k e  n  N   , t o k e  n  N + i   )  )  i     )    {\displaystyle {RMM(token_{N})}={PMM(token_{N})}\times {\frac {1}{2d}}\left(\sum _{i=-d}^{d}{((PMM(token_{N})}\times {PF(token_{N-i},token_{N},token_{N+i}))_{i}}\right)}  ![{\displaystyle {RMM(token_{N})}={PMM(token_{N})}\times {\frac {1}{2d}}\left(\sum _{i=-d}^{d}{((PMM(token_{N})}\times {PF(token_{N-i},token_{N},token_{N+i}))_{i}}\right)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/43ccadd794a4b84e20d1209997a463342e0dfbfe) *Where* **RMM** is the relative measure of meaning **token** is any block of text, sentence, phrase or word **N** is the number of tokens being analyzed **PMM** is the probable measure of meaning based on a corpora **d** is the non-zero location of the token along the sequence of **N** tokens **PF** is the probability function specific to a language 

Ties with cognitive linguistics are part of the historical heritage of NLP, but they have been less frequently addressed since the statistical turn during the 1990s. Nevertheless, approaches to develop cognitive models towards technically operationalizable frameworks have been pursued in the context of various frameworks, e.g., of cognitive grammar,[[56]](./Natural_language_processing#cite_note-56) functional grammar,[[57]](./Natural_language_processing#cite_note-57) construction grammar,[[58]](./Natural_language_processing#cite_note-58) computational psycholinguistics and cognitive neuroscience (e.g., [ACT-R](./ACT-R)), however, with limited uptake in mainstream NLP (as measured by presence on major conferences[[59]](./Natural_language_processing#cite_note-59) of the [ACL](./Association_for_Computational_Linguistics)). More recently, ideas of cognitive NLP have been revived as an approach to achieve [explainability](./Explainable_artificial_intelligence), e.g., under the notion of "cognitive AI".[[60]](./Natural_language_processing#cite_note-60) Likewise, ideas of cognitive NLP are inherent to neural models [multimodal](./Multimodal_interaction) NLP (although rarely made explicit)[[61]](./Natural_language_processing#cite_note-61) and developments in [artificial intelligence](./Artificial_intelligence), specifically tools and technologies using [large language model](./Large_language_model) approaches[[62]](./Natural_language_processing#cite_note-62) and new directions in [artificial general intelligence](./Artificial_general_intelligence) based on the [free energy principle](./Free_energy_principle)[[63]](./Natural_language_processing#cite_note-63) by British neuroscientist and theoretician at University College London [Karl J. Friston](./Karl_J._Friston).

 

## See also

  
- *[1 the Road](./1_the_Road)*
- [Artificial intelligence detection software](./Artificial_intelligence_detection_software)
- [Automated essay scoring](./Automated_essay_scoring)
- [Biomedical text mining](./Biomedical_text_mining)
- [Compound term processing](./Compound_term_processing)
- [Computational linguistics](./Computational_linguistics)
- [Computer-assisted reviewing](./Computer-assisted_reviewing)
- [Controlled natural language](./Controlled_natural_language)
- [Deep learning](./Deep_learning)
- [Deep linguistic processing](./Deep_linguistic_processing)
- [Distributional semantics](./Distributional_semantics)
- [Foreign language reading aid](./Foreign_language_reading_aid)
- [Foreign language writing aid](./Foreign_language_writing_aid)
- [Information extraction](./Information_extraction)
- [Information retrieval](./Information_retrieval)
- [Language and Communication Technologies](./Language_and_Communication_Technologies)
- [Language model](./Language_model)
- [Language technology](./Language_technology)
- [Latent semantic indexing](./Latent_semantic_indexing)
- [Multi-agent system](./Multi-agent_system)
- [Native-language identification](./Native-language_identification)
- [Natural-language programming](./Natural-language_programming)
- [Natural-language understanding](./Natural-language_understanding)
- [Natural-language search](./Natural-language_user_interface)
- [Outline of natural language processing](./Outline_of_natural_language_processing)
- [Query expansion](./Query_expansion)
- [Query understanding](./Query_understanding)
- [Reification (linguistics)](./Reification_(linguistics))
- [Speech processing](./Speech_processing)
- [Spoken dialogue systems](./Spoken_dialogue_systems)
- [Text-proofing](./Text-proofing)
- [Text simplification](./Text_simplification)
- [Transformer (machine learning model)](./Transformer_(machine_learning_model))
- [Truecasing](./Truecasing)
- [Question answering](./Question_answering)
- [Word2vec](./Word2vec)

  


