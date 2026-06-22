---
source: chunks/wiki-Natural_language_processing-chunk-2.md
source_url: https://en.wikipedia.org/wiki/Natural_language_processing
---

## Common NLP Tasks — Taxonomy and Definitions

This page provides a comprehensive taxonomy of natural language processing tasks, organized by linguistic level of analysis — from low-level text/speech processing up through morphology, syntax, semantics, discourse, and high-level applications. Many tasks serve as subtasks for others, forming a layered dependency structure.

## Key Concepts

- **NLP tasks form a hierarchy**: low-level tasks (tokenization, POS tagging) feed into higher-level tasks (parsing, NER, machine translation)
- **Tokenization** splits text into words/subwords and maps them to numerical IDs, producing a word index and tokenized text — trivial for space-delimited languages (English), hard for Chinese, Japanese, Thai
- **Stemming vs. Lemmatization**: stemming applies rules to strip affixes; lemmatization uses a dictionary to return the true base form (lemma)
- **Morphological segmentation** difficulty varies drastically by language — English is simple; agglutinative languages like Turkish have thousands of word forms per dictionary entry
- **POS tagging** is complicated by ambiguity — "book" can be noun or verb; "set" can be noun, verb, or adjective
- **Parsing** has two major types: **dependency parsing** (relationships between words) and **constituency parsing** (building parse trees, often using PCFGs)
- **Named Entity Recognition (NER)** identifies proper names and their types (person, location, organization) — also called token classification
- **Sentiment analysis** classifies emotional tone (positive/negative/neutral) using n-grams, TF-IDF, or deep learning
- **Word-sense disambiguation (WSD)** selects the correct meaning of a polysemous word in context
- **Entity linking** maps mentions to specific real-world entities (distinct from NER which just identifies and types them)
- **Coreference resolution** determines which mentions refer to the same entity; **anaphora resolution** is the pronoun-specific subtask
- **Semantic role labeling (SRL)** identifies predicates and their argument roles (agent, patient, etc.)
- **Textual entailment** determines whether one text fragment logically entails another, entails its negation, or is neutral
- **Machine translation** and **speech recognition** are considered "AI-complete" — requiring grammar, semantics, and world knowledge
- **Grammatical error correction** is largely solved (as of 2019) for orthography, morphology, and syntax due to powerful neural language models like GPT-2

## Commands and Syntax

No specific commands or configuration syntax — this is a conceptual taxonomy. However, key technical constructs referenced:

- **Bag of Words (BOW)**: representation used in data mining, relies on tokenization
- **TF-IDF features**: used as input for sentiment analysis models
- **Word n-grams**: sequential word groupings used as features
- **PCFG (Probabilistic Context-Free Grammar)**: used in constituency parsing
- **AMR (Abstract Meaning Representation)**: graph-based semantic representation used in semantic parsing
- **DRT (Discourse Representation Theory)**: logical formalism for semantic parsing
- **First-order logic**: target representation for Natural Language Understanding (NLU)

## Relationships

- **Speech recognition** depends on **speech segmentation** as a subtask; **text-to-speech** is its inverse
- **Tokenization** is foundational to nearly all downstream NLP tasks
- **Stemming** and **lemmatization** are alternative approaches to word normalization; lemmatization is more accurate but requires a dictionary
- **NER** feeds into **entity linking** (identify, then resolve to knowledge base)
- **Semantic role labeling** feeds into **semantic parsing**, which also depends on **WSD**
- **Coreference resolution** extends into **implicit SRL** and **zero anaphora resolution** for pro-drop languages
- **Automatic summarization**, **question answering**, **dialogue management**, and **machine translation** are higher-level applications that compose many lower-level tasks
- **NLG (Natural Language Generation)** is the inverse of **NLU (Natural Language Understanding)**
- **Document AI** sits on top of NLP as an application layer enabling non-technical users

## Exam-Relevant Points

- Know the difference between **stemming** (rule-based, approximate) and **lemmatization** (dictionary-based, returns true lemma)
- **Dependency parsing** focuses on word relationships; **constituency parsing** builds tree structures using PCFGs
- **NER** is also called **token classification**
- **Speech recognition** and **machine translation** are classified as **AI-complete** problems
- Tokenization is trivial for English but a significant challenge for Chinese, Japanese, and Thai (no space-delimited word boundaries)
- **Coreference resolution** is broader than **anaphora resolution** — it includes bridging relationships, not just pronoun matching
- **Textual entailment** has three outcomes: entails, contradicts, or neutral
- Morphological complexity varies by language — English has simple inflectional morphology; Turkish is highly agglutinative
- **Sentiment analysis** can use traditional features (n-grams, TF-IDF) or deep learning
- **Grammatical error correction** is considered largely solved for major structural dimensions as of 2019
- **WSD** requires selecting among known senses (e.g., from WordNet); **entity linking** requires resolving to a specific real-world entity — these are related but distinct tasks
