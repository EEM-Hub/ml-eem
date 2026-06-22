---
source: sources/wiki-Natural_language_processing.md
source_url: https://en.wikipedia.org/wiki/Natural_language_processing
chunk: 1/5
---

Processing of natural language by a computer 
|  | This article has multiple issues.Please helpimprove itor discuss these issues on thetalk page.(Learn how and when to remove these messages)This articleneeds additional citations forverification.Please helpimprove this articlebyadding citations to reliable sources. Unsourced material may be challenged and removed.Find sources:"Natural language processing"–news·newspapers·books·scholar·JSTOR(May 2024)(Learn how and when to remove this message)This articlemay need to be rewrittento comply with Wikipedia'squality standards.Relevant discussion may be found on thetalk page.You can help. The talk page may contain suggestions.(July 2025)This articlemay be in need of reorganization to comply with Wikipedia'slayout guidelines.Please help byediting the articleto make improvements to the overall structure.(July 2025)(Learn how and when to remove this message)(Learn how and when to remove this message) |  | This articleneeds additional citations forverification.Please helpimprove this articlebyadding citations to reliable sources. Unsourced material may be challenged and removed.Find sources:"Natural language processing"–news·newspapers·books·scholar·JSTOR(May 2024)(Learn how and when to remove this message) |  | This articlemay need to be rewrittento comply with Wikipedia'squality standards.Relevant discussion may be found on thetalk page.You can help. The talk page may contain suggestions.(July 2025) |  | This articlemay be in need of reorganization to comply with Wikipedia'slayout guidelines.Please help byediting the articleto make improvements to the overall structure.(July 2025)(Learn how and when to remove this message) |
| --- | --- | --- | --- | --- | --- | --- | --- |
|  | This articleneeds additional citations forverification.Please helpimprove this articlebyadding citations to reliable sources. Unsourced material may be challenged and removed.Find sources:"Natural language processing"–news·newspapers·books·scholar·JSTOR(May 2024)(Learn how and when to remove this message) |
|  | This articlemay need to be rewrittento comply with Wikipedia'squality standards.Relevant discussion may be found on thetalk page.You can help. The talk page may contain suggestions.(July 2025) |
|  | This articlemay be in need of reorganization to comply with Wikipedia'slayout guidelines.Please help byediting the articleto make improvements to the overall structure.(July 2025)(Learn how and when to remove this message) |

 
| Part ofa serieson |
| --- |
| Artificial intelligence (AI) |
| Major goalsArtificial general intelligenceIntelligent agentRecursive self-improvementPlanningComputer visionGeneral game playingKnowledge representationNatural language processingRoboticsAI safety |
| ApproachesMachine learningSymbolicDeep learningBayesian networksEvolutionary algorithmsNeuro-symbolic AISystems integrationOpen-sourceAI data centers |
| ApplicationsBioinformaticsDeepfakeEarth sciencesFinanceGenerative AIArtAudioMusicGovernmentHealthcareIndustrySoftware developmentTranslationMilitaryPhysicsProjects |
| PhilosophyAI alignmentArtificial consciousnessThe bitter lessonChinese roomFriendly AIEthicsExistential riskTuring testUncanny valleyHuman–AI interaction |
| HistoryTimelineProgressAI winterAI boomAI bubble |
| ControversiesDeepfake pornographyTaylor Swift deepfake pornography controversyGrok sexual deepfake scandalGoogle Gemini image generation controversyIt's the Most Terrible Time of the YearPause Giant AI ExperimentsRemoval of Sam Altman from OpenAIStatement on AI RiskTay (chatbot)Théâtre D'opéra SpatialVoiceverse NFT plagiarism scandal |
| GlossaryGlossary |
| vte |

 

**Natural language processing** (**NLP**) is the processing of [natural language](./Natural_language) information by a [computer](./Computer). NLP is a subfield of [computer science](./Computer_science) and is closely associated with [artificial intelligence](./Artificial_intelligence). NLP is also related to [information retrieval](./Information_retrieval), [knowledge representation](./Knowledge_representation_and_reasoning), [computational linguistics](./Computational_linguistics), and [linguistics](./Linguistics) more broadly.[[1]](./Natural_language_processing#cite_note-nlpintro-1)

 

Major processing tasks in an NLP system include: [speech recognition](./Speech_recognition), [text classification](./Text_classification), [natural language understanding](./Natural_language_understanding), and [natural language generation](./Natural_language_generation).

 

## History

 Further information: [History of natural language processing](./History_of_natural_language_processing) 

Natural language processing has its roots in the 1950s.[[2]](./Natural_language_processing#cite_note-2) Already in 1950, [Alan Turing](./Alan_Turing) published an article titled "[Computing Machinery and Intelligence](./Computing_Machinery_and_Intelligence)," which proposed what is now called the [Turing test](./Turing_test) as a criterion of intelligence, though at the time that was not articulated as a problem separate from artificial intelligence. The proposed test includes a task that involves the automated interpretation and generation of natural language.

 

### Symbolic NLP (1950s – early 1990s)

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/0/09/AST_Document.svg/250px-AST_Document.svg.png)](./File:AST_Document.svg)A document parsed into an abstract syntax tree 

The premise of symbolic NLP is often illustrated using [John Searle's Chinese room](./John_Searle_(American_philosopher)) thought experiment: Given a collection of rules (e.g., a Chinese phrasebook, with questions and matching answers), the computer emulates natural language understanding (or other NLP tasks) by applying those rules to the data it confronts.

 
- **1950s**: The [Georgetown experiment](./Georgetown-IBM_experiment) in 1954 involved fully [automatic translation](./Automatic_translation) of more than sixty Russian sentences into English. The authors claimed that within three or five years, machine translation would be a solved problem.[[3]](./Natural_language_processing#cite_note-3)  However, real progress was much slower, and after the [ALPAC report](./ALPAC) in 1966, which found that ten years of research had failed to fulfill the expectations, funding for machine translation was dramatically reduced. Little further research in machine translation was conducted in America (though some research continued elsewhere, such as Japan and Europe[[4]](./Natural_language_processing#cite_note-4)) until the late 1980s when the first [statistical machine translation](./Statistical_machine_translation) systems were developed.
- **1960s**: Some notably successful natural language processing systems developed in the 1960s were [SHRDLU](./SHRDLU), a natural language system working in restricted "[blocks worlds](./Blocks_world)" with restricted vocabularies, and [ELIZA](./ELIZA), a simulation of Rogerian psychotherapy, written by [Joseph Weizenbaum](./Joseph_Weizenbaum) between 1964 and 1966. Despite using minimal information about human thought or emotion, ELIZA was able to produce interactions that appeared human-like. When the "patient" exceeded the very small knowledge base, ELIZA might provide a generic response, for example, responding to "My head hurts" with "Why do you say your head hurts?". Ross Quillian's successful work on natural language was demonstrated with a vocabulary of only *twenty* words, because that was all that would fit in a computer memory at the time.[[5]](./Natural_language_processing#cite_note-5)
- **1970s**: During the 1970s, many programmers began to write "conceptual [ontologies](./Ontology_(information_science))", which structured real-world information into computer-understandable data.  Examples are MARGIE (Schank, 1975), SAM (Cullingford, 1978), PAM (Wilensky, 1978), TaleSpin (Meehan, 1976), QUALM (Lehnert, 1977), Politics (Carbonell, 1979), and Plot Units (Lehnert 1981). During this time, the first [chatterbots](./Chatterbots) were written (e.g., [PARRY](./PARRY)).
- **1980s**: The 1980s and early 1990s mark the heyday of symbolic methods in NLP. Focus areas of the time included research on rule-based parsing (e.g., the development of [HPSG](./Head-driven_phrase_structure_grammar) as a computational operationalization of [generative grammar](./Generative_grammar)), morphology (e.g., two-level morphology[[6]](./Natural_language_processing#cite_note-6)), semantics (e.g., [Lesk algorithm](./Lesk_algorithm)), reference (e.g., within Centering Theory[[7]](./Natural_language_processing#cite_note-7)) and other areas of natural language understanding (e.g., in the [Rhetorical Structure Theory](./Rhetorical_structure_theory)). Other lines of research were continued, e.g., the development of chatterbots with [Racter](./Racter) and [Jabberwacky](./Jabberwacky). An important development (that eventually led to the statistical turn in the 1990s) was the rising importance of quantitative evaluation in this period.[[8]](./Natural_language_processing#cite_note-8)

 

### Statistical NLP (1990s–present)

 

Up until the 1980s, most natural language processing systems were based on complex sets of hand-written rules. Starting in the late 1980s, however, there was a revolution in natural language processing with the introduction of [machine learning](./Machine_learning) algorithms for language processing. This shift was influenced by increasing computational power (see [Moore's law](./Moore's_law)) and a decline in the dominance of [Chomskyan](./Chomskyan) linguistic theories (e.g. [transformational grammar](./Transformational_grammar)), whose theoretical underpinnings discouraged the sort of [corpus linguistics](./Corpus_linguistics) that underlies the machine-learning approach to language processing.[[9]](./Natural_language_processing#cite_note-9)

 
- **1990s**: Many of the notable early successes in statistical methods in NLP occurred in the field of [machine translation](./Machine_translation), due especially to work at IBM Research, such as [IBM alignment models](./IBM_alignment_models). These systems were able to take advantage of existing multilingual [textual corpora](./Text_corpus) that had been produced by the [Parliament of Canada](./Parliament_of_Canada) and the [European Union](./European_Union) as a result of laws calling for the translation of all governmental proceedings into all official languages of the corresponding systems of government. However, many systems relied on corpora that were specifically developed for the tasks they were designed to perform. This reliance has been a major limitation to their broader effectiveness and continues to affect similar systems. Consequently, significant research has focused on methods for learning effectively from limited amounts of data.
- **2000s**: With the growth of the web, increasing amounts of raw (unannotated) language data have become available since the mid-1990s. Research has thus increasingly focused on [unsupervised](./Unsupervised_learning) and [semi-supervised learning](./Semi-supervised_learning) algorithms. Such algorithms can learn from data that has not been hand-annotated with the desired answers or using a combination of annotated and non-annotated data. Generally, this task is much more difficult than [supervised learning](./Supervised_learning), and typically produces less accurate results for a given amount of input data. However, large quantities of non-annotated data are available (including, among other things, the entire content of the [World Wide Web](./World_Wide_Web)), which can often make up for the worse efficiency if the algorithm used has a low enough [time complexity](./Time_complexity) to be practical.
- **2003:** [word n-gram model](./Word_n-gram_language_model), at the time the best statistical algorithm, is outperformed by a [multi-layer perceptron](./Multi-layer_perceptron) (with a single hidden layer and context length of several words, trained on up to 14 million words, by [Bengio](./Yoshua_Bengio) et al.)[[10]](./Natural_language_processing#cite_note-10)
- **2010:** [Tomáš Mikolov](./Tomáš_Mikolov) (then a PhD student at [Brno University of Technology](./Brno_University_of_Technology)) with co-authors applied a simple [recurrent neural network](./Recurrent_neural_network) with a single hidden layer to language modeling,[[11]](./Natural_language_processing#cite_note-11) and in the following years he went on to develop [Word2vec](./Word2vec). In the 2010s, [representation learning](./Representation_learning) and [deep neural network](./Deep_learning)-style (featuring many hidden layers) machine learning methods became widespread in natural language processing. This shift gained momentum due to results showing that such techniques[[12]](./Natural_language_processing#cite_note-goldberg:nnlp17-12)[[13]](./Natural_language_processing#cite_note-goodfellow:book16-13) can achieve state-of-the-art results in many natural language tasks, e.g., in [language modeling](./Language_modeling)[[14]](./Natural_language_processing#cite_note-jozefowicz:lm16-14) and parsing.[[15]](./Natural_language_processing#cite_note-choe:emnlp16-15)[[16]](./Natural_language_processing#cite_note-vinyals:nips15-16) This is increasingly important [in medicine and healthcare](./Artificial_intelligence_in_healthcare), where NLP helps analyze notes and text in [electronic health records](./Electronic_health_record) that would otherwise be inaccessible for study when seeking to improve care[[17]](./Natural_language_processing#cite_note-17) or protect patient privacy.[[18]](./Natural_language_processing#cite_note-18)

 

## Approaches: Symbolic, statistical, neural networks

 

Symbolic approach, i.e., the hand-coding of a set of rules for manipulating symbols, coupled with a dictionary lookup, was historically the first approach used both by AI in general and by NLP in particular:[[19]](./Natural_language_processing#cite_note-winograd:shrdlu71-19)[[20]](./Natural_language_processing#cite_note-schank77-20) such as by writing grammars or devising heuristic rules for [stemming](./Stemming).

 

[Machine learning](./Machine_learning) approaches, which include both statistical and neural networks, on the other hand, have many advantages over the symbolic approach:

 
- both statistical and neural network methods tend to focus more on the most common cases extracted from a corpus of texts, whereas the rule-based approach needs to provide rules for both rare and common cases equally.
- [language models](./Language_model), produced by either statistical or neural network methods, are more robust to both unfamiliar (e.g. containing words or structures that have not been seen before) and erroneous input (e.g. with misspelled words or words accidentally omitted) in comparison to the rule-based systems, which are also more costly to produce.
- the larger such a (probabilistic) language model is, the more accurate it becomes, in contrast to rule-based systems that can gain accuracy only by increasing the amount and complexity of the rules leading to [intractability](./Intractable_problem) problems.

 

Rule-based systems are commonly used:

 
- when the amount of training data is insufficient to successfully apply machine learning methods, e.g., for the machine translation of low-resource languages such as provided by the [Apertium](./Apertium) system,
- for preprocessing in NLP pipelines, e.g., [tokenization](./Tokenization_(lexical_analysis)), or
- for post-processing and transforming the output of NLP pipelines, e.g., for [knowledge extraction](./Knowledge_extraction) from syntactic parses.

 

### Statistical approach

 

In the late 1980s and mid-1990s, the statistical approach ended a period of [AI winter](./AI_winter), which was caused by the inefficiencies of the rule-based approaches.[[21]](./Natural_language_processing#cite_note-johnson:eacl:ilcl09-21)[[22]](./Natural_language_processing#cite_note-resnik:langlog11-22)

 

The earliest [decision trees](./Decision_tree), producing systems of hard [if–then rules](./Conditional_(computer_programming)#If–then(–else)), were still very similar to the old rule-based approaches.
Only the introduction of hidden [Markov models](./Markov_model), applied to part-of-speech tagging, announced the end of the old rule-based approach.

 

### Neural networks

 Further information: [Artificial neural network](./Artificial_neural_network) 

A major drawback of statistical methods is that they require elaborate [feature engineering](./Feature_engineering). Since 2015,[[23]](./Natural_language_processing#cite_note-23) [neural network](./Neural_network_(machine_learning))–based methods have increasingly replaced traditional statistical approaches, using [semantic networks](./Semantic_networks)[[24]](./Natural_language_processing#cite_note-24) and [word embeddings](./Word_embedding) to capture semantic properties of words.

 

Intermediate tasks (e.g., part-of-speech tagging and dependency parsing) are not needed anymore.

 

[Neural machine translation](./Neural_machine_translation), based on the then-newly invented [sequence-to-sequence](./Seq2seq) transformations, made obsolete the intermediate steps, such as word alignment, previously necessary for [statistical machine translation](./Statistical_machine_translation).

 


