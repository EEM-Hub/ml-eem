---
source: chunks/wiki-Natural_language_processing-chunk-3.md
source_url: https://en.wikipedia.org/wiki/Natural_language_processing
---

## NLP Future Directions: Cognition, Multilinguality, and End-to-End Learning

This page covers the general trends and possible future directions of Natural Language Processing, as extrapolated from long-standing patterns in the field (particularly CoNLL Shared Tasks through 2020). It also explores the relationship between NLP and cognitive science, including specific frameworks for integrating cognitive linguistics into NLP algorithms.

## Key Concepts

- **Three major NLP trends** (observed from CoNLL Shared Tasks):
  1. Movement toward increasingly abstract, cognitive aspects of language (from shallow parsing to semantic parsing)
  2. Growing multilinguality and potential multimodality (from English-only in 1999 to 100+ languages by 2018)
  3. Elimination of symbolic representations (shift from rule-based to supervised, then weakly supervised methods, with representation learning and end-to-end systems)
- **Cognitive NLP** emulates intelligent behavior and apparent comprehension of natural language; it operationalizes increasingly advanced cognitive behavior
- **Conceptual metaphor theory** (George Lakoff): understanding one idea in terms of another to infer author intent (e.g., "big" as physical size vs. metaphorical importance)
- **Relative Measure of Meaning (RMM)**: a mathematical framework that assigns meaning to tokens based on surrounding context, using probable measure of meaning (PMM) and language-specific probability functions
- **Probabilistic Context-Free Grammar (PCFG)**: used to assign relative measures of meaning based on surrounding textual context
- **Cognitive linguistics** declined in NLP influence after the 1990s statistical turn but has seen revival through explainability ("cognitive AI") and multimodal NLP

## Commands and Syntax

- **RMM Formula**: RMM(token_N) = PMM(token_N) x (1/2d) x sum over i from -d to d of (PMM(token_N) x PF(token_{N-i}, token_N, token_{N+i}))
  - RMM = relative measure of meaning
  - PMM = probable measure of meaning (corpus-derived)
  - PF = language-specific probability function
  - d = non-zero position offset in the token sequence
  - N = number of tokens being analyzed

## Relationships

- **Cognitive science / cognitive linguistics**: historical foundation of NLP; computational linguistics maintained strong ties during the symbolic NLP era (1950s–early 1990s)
- **CoNLL Shared Tasks**: primary evidence source for tracking NLP trend trajectories over two decades
- **Explainable AI (XAI)**: cognitive NLP ideas revived as a path to model explainability
- **Large language models**: implicitly incorporate cognitive NLP ideas, though rarely made explicit
- **Artificial general intelligence (AGI)**: new directions based on Karl Friston's free energy principle connect to cognitive NLP
- **Related frameworks**: cognitive grammar, functional grammar, construction grammar, computational psycholinguistics, ACT-R — all attempted to bridge cognition and NLP with limited mainstream adoption
- **Broader NLP ecosystem**: connects to deep learning, transformers, distributional semantics, information extraction, question answering, language models, and speech processing

## Exam-Relevant Points

- The three CoNLL trend lines (cognitive abstraction, multilinguality, end-to-end learning) represent the canonical summary of NLP's trajectory through 2020
- The progression from shallow parsing (1999) through named entity recognition, dependency syntax, semantic role labeling, coreference, discourse parsing, to semantic parsing (2019) illustrates increasing cognitive abstraction
- Lakoff's conceptual metaphor theory is a named framework for resolving lexical ambiguity through cognitive modeling
- The statistical turn of the 1990s marks the historical point where cognitive linguistics lost influence in mainstream NLP
- RMM is a patented (US Patent 9269353) context-dependent meaning assignment algorithm
- Multilinguality scale expanded from 1 language (1999) to 100+ languages (2018) in CoNLL tasks
- The shift from symbolic to statistical to neural methods represents the "elimination of symbolic representations" trend
- Karl Friston's free energy principle is cited as a basis for new AGI directions connected to cognitive NLP
