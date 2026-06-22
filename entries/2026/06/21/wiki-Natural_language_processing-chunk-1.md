---
source: chunks/wiki-Natural_language_processing-chunk-1.md
source_url: https://en.wikipedia.org/wiki/Natural_language_processing
---

## Natural Language Processing (NLP): Foundations, History, and Approaches

Natural language processing (NLP) is the subfield of computer science concerned with enabling computers to process, understand, and generate human (natural) language. It sits at the intersection of AI, computational linguistics, information retrieval, and knowledge representation. Major NLP tasks include speech recognition, text classification, natural language understanding (NLU), and natural language generation (NLG).

## Key Concepts

- **NLP** is processing natural language information by computer — a subfield of CS closely tied to AI, linguistics, and information retrieval.
- **Three major paradigms** have driven NLP historically: symbolic (rule-based), statistical (ML on corpora), and neural network approaches.
- **Symbolic NLP (1950s–early 1990s)**: Hand-coded rules, grammars, dictionary lookups. Illustrated by Searle's Chinese Room — applying rules without understanding. Key systems: SHRDLU, ELIZA, PARRY.
- **Statistical NLP (1990s–present)**: Machine learning replaces hand-written rules. Driven by increased compute (Moore's law), decline of Chomskyan dominance, and availability of multilingual corpora (e.g., EU/Canadian parliamentary proceedings).
- **Neural NLP (2010s–present)**: Deep learning with representation learning (Word2vec, sequence-to-sequence models) eliminates need for hand-crafted features and intermediate pipeline steps (e.g., word alignment in MT).
- **Rule-based systems still useful** for: low-resource languages, preprocessing (tokenization), and post-processing (knowledge extraction from parses).
- **Statistical/neural advantages over symbolic**: better handling of common cases, more robust to unseen/erroneous input, accuracy scales with data size rather than rule complexity.
- **Key historical milestone**: In 2003, a multi-layer perceptron outperformed the best statistical n-gram model for language modeling (Bengio et al., trained on up to 14M words).
- **Word2vec** (Mikolov, ~2013) grew from applying simple RNNs to language modeling (2010), catalyzing the deep learning wave in NLP.

## Commands and Syntax

No specific commands or configuration syntax — this is a conceptual/historical overview. However, relevant pipeline concepts include:

- **Tokenization** — segmenting text into tokens (preprocessing step)
- **Stemming** — reducing words to root forms (historically rule-based)
- **POS tagging** — labeling parts of speech (early use of Hidden Markov Models)
- **Dependency parsing** — syntactic structure analysis
- **Sequence-to-sequence (seq2seq)** — neural architecture that maps input sequences to output sequences, key to neural machine translation

## Relationships

- **Parent field**: Artificial Intelligence
- **Sibling fields**: Computer Vision, Robotics, Knowledge Representation
- **Overlapping disciplines**: Computational Linguistics, Information Retrieval, Linguistics
- **Enabling technologies**: Machine Learning, Deep Learning, Neural Networks
- **Key applications**: Machine Translation, Healthcare/EHR analysis, Chatbots
- **Historical connection**: Statistical NLP ended the AI Winter caused by limitations of symbolic approaches
- **Evolution path**: Symbolic → Statistical → Neural, with each paradigm building on and eventually supplanting the previous
- **Language modeling** connects NLP to modern large language models (LLMs) — the progression from n-gram models → MLP → RNN → transformers

## Exam-Relevant Points

- NLP's four major tasks: speech recognition, text classification, natural language understanding, natural language generation
- The **Georgetown experiment (1954)** was the first automatic translation demo (Russian → English); the **ALPAC report (1966)** dramatically cut MT funding after a decade of unmet expectations
- **ELIZA** (Weizenbaum, 1964–66) simulated Rogerian psychotherapy with minimal knowledge; **SHRDLU** operated in restricted "blocks worlds"
- **Hidden Markov Models** applied to POS tagging marked the real transition away from rule-based NLP
- **Statistical MT** was enabled by existing multilingual parliamentary corpora (Canada, EU)
- The shift from statistical to neural methods (~2015) eliminated the need for **feature engineering** and intermediate pipeline tasks
- **Seq2seq models** made word alignment (a staple of statistical MT) obsolete
- Rule-based approaches are still preferred when training data is insufficient (low-resource languages, e.g., Apertium system)
- Probabilistic language models improve with scale; rule-based systems hit intractability as rules grow
- **Unsupervised/semi-supervised learning** became important in the 2000s due to vast unannotated web data
