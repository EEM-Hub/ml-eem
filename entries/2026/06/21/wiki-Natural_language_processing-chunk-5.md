---
source: chunks/wiki-Natural_language_processing-chunk-5.md
source_url: https://en.wikipedia.org/wiki/Natural_language_processing
---

## Natural Language Processing — Taxonomy and Key References

This page provides the canonical taxonomy of Natural Language Processing (NLP) as a field, along with foundational references. It serves as a map of the entire NLP domain, organizing subtopics into categories: text analysis, text segmentation, summarization, machine translation, distributional semantics, language resources, speech processing, topic modeling, computer-assisted reviewing, natural language interfaces, and visual-linguistic processing.

## Key Concepts

- **NLP is classified as AI-complete** — meaning full NLP requires solving the general AI problem.
- **Core building blocks**: bag-of-words, n-grams (bigrams, trigrams), stop words, text processing.
- **Text analysis** spans a wide range: named-entity recognition, sentiment analysis, coreference resolution, parsing (semantic and syntactic), part-of-speech tagging, word-sense disambiguation.
- **Text segmentation** includes: lemmatization, stemming, tokenization (word/sentence segmentation), text chunking, compound-term processing.
- **Distributional semantics models** represent the modern ML backbone: BERT, Word2Vec, GloVe, fastText, Transformers, LSTM, Seq2Seq, and language models (large and small).
- **Machine translation approaches**: rule-based, statistical, example-based, transfer-based, neural, and computer-assisted.
- **NLP context limitations**: even advanced models are constrained by the amount of context they receive — a significant limitation for domains with sparse training data (e.g., ancient languages).

## Commands and Syntax

No commands on this page. Key resources for tooling:

- **NLTK** (Natural Language Toolkit) — Python library for NLP
- **spaCy** — industrial-strength NLP library
- **Gensim** — topic modeling and document similarity

Foundational textbooks (ordered by practical relevance):
- Jurafsky & Martin, *Speech and Language Processing* (2nd ed., 2008) — the standard graduate textbook
- Manning & Schütze, *Foundations of Statistical NLP* (1999) — statistical methods reference
- Bird, Klein & Loper, *Natural Language Processing with Python* (2009) — hands-on NLTK guide
- Manning, Raghavan & Schütze, *Introduction to Information Retrieval* (2008) — free online at nlp.stanford.edu/IR-book/

## Relationships

- **Distributional semantics** connects to deep learning: Transformers, BERT, Word2Vec are the bridge between NLP and modern ML.
- **Language resources** (WordNet, FrameNet, BabelNet, Universal Dependencies, PropBank) are foundational datasets that NLP models depend on.
- **Topic modeling** (LDA, Pachinko allocation) connects NLP to unsupervised learning.
- **Speech recognition/synthesis** bridges NLP with signal processing.
- **Visual-linguistic** processing (CLIP, VLMs, VLAMs) bridges NLP with computer vision — a growing area.
- **Hallucination** is listed as a related concern — linking NLP to LLM reliability/safety.
- **Prompt engineering** appears under natural language user interfaces — connecting traditional NLP to modern LLM interaction patterns.

## Exam-Relevant Points

- Know the NLP taxonomy categories: text analysis, segmentation, summarization, MT, distributional semantics, topic modeling, speech, NL interfaces, visual-linguistic.
- **AI-complete** classification of NLP is a testable definition.
- Distinguish machine translation approaches: rule-based vs. statistical vs. neural vs. transfer-based.
- Key distributional semantics models to know: **BERT**, **Word2Vec**, **GloVe**, **fastText**, **Transformer**, **LSTM**, **Seq2Seq**.
- Text segmentation pipeline: lexical analysis → stemming/lemmatization → sentence segmentation → word segmentation → chunking.
- Standard language resources: **WordNet** (lexical database), **FrameNet** (semantic frames), **Universal Dependencies** (syntactic annotation), **PropBank** (predicate-argument structures).
- Context limitation is a known weakness — NLP models struggle with low-resource domains where training data is sparse.
- **Hallucination** is formally recognized as a related problem in the NLP field taxonomy.
