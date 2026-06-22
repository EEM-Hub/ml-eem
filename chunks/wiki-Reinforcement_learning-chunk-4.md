---
source: sources/wiki-Reinforcement_learning.md
source_url: https://en.wikipedia.org/wiki/Reinforcement_learning
chunk: 4/6
---

## In natural language processing

 

In recent years Since the early 2020s,[[81]](./Reinforcement_learning#cite_note-81) reinforcement learning has become a significant concept in [natural language processing](./Natural_language_processing) (NLP), where tasks are often sequential decision-making rather than static classification. Reinforcement learning is where an agent take actions in an environment to maximize the accumulation of rewards. This framework is best fit for many NLP tasks, including dialogue generation, text summarization, and machine translation, where the quality of the output depends on optimizing long-term or human-centered goals rather than the prediction of single correct label.

 

Early application of RL in NLP emerged in dialogue systems, where conversation was determined as a series of actions optimized for fluency and coherence. These early attempts, including policy gradient and sequence-level training techniques, laid a foundation for the broader application of reinforcement learning to other areas of NLP.

 

A major breakthrough happened with the introduction of [reinforcement learning from human feedback](./Reinforcement_learning_from_human_feedback) (RLHF), a method in which human feedback ratings are used to train a reward model that guides the RL agent. Unlike traditional rule-based or supervised systems, RLHF allows models to align their behavior with human judgments on complex and subjective tasks. This technique was initially used in the development of [InstructGPT](./InstructGPT), an effective language model trained to follow human instructions and later in [ChatGPT](./ChatGPT) which incorporates RLHF for improving output responses and ensuring safety.

 

More recently[*[when?](./Wikipedia:Manual_of_Style/Dates_and_numbers#Chronological_items)*], researchers have explored the use of offline RL in NLP to improve dialogue systems without the need of live human interaction. These methods optimize for user engagement, coherence, and diversity based on past conversation logs and pre-trained reward models.[[82]](./Reinforcement_learning#cite_note-82)

 

One example is DeepSeek-R1, which incorporates multi-stage training and cold-start data before RL. DeepSeek-R1 achieves performance comparable to OpenAI-o1-1217 on reasoning tasks. This model was trained via large-scale RL without supervised fine-tuning (SFT) as a preliminary step.
[[83]](./Reinforcement_learning#cite_note-83)

 

## See also

  
- [Active learning (machine learning)](./Active_learning_(machine_learning))
- [Apprenticeship learning](./Apprenticeship_learning)
- [Error-driven learning](./Error-driven_learning)
- [Model-free (reinforcement learning)](./Model-free_(reinforcement_learning))
- [Multi-agent reinforcement learning](./Multi-agent_reinforcement_learning)
- [Optimal control](./Optimal_control)
- [Q-learning](./Q-learning)
- [Reinforcement learning from human feedback](./Reinforcement_learning_from_human_feedback)
- [State–action–reward–state–action](./State–action–reward–state–action) (SARSA)
- [Temporal difference learning](./Temporal_difference_learning)

  


