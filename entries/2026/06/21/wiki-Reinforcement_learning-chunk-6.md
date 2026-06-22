---
source: chunks/wiki-Reinforcement_learning-chunk-6.md
source_url: https://en.wikipedia.org/wiki/Reinforcement_learning
---

## Reinforcement Learning — Key References and Resources

This page is a bibliography and link collection for reinforcement learning (RL), listing the foundational textbooks, seminal papers, and external learning resources most frequently cited in the field. It serves as a reading list rather than a conceptual explainer.

## Key Concepts

- **Foundational textbook**: Sutton & Barto, *Reinforcement Learning: An Introduction* (2nd ed., 2018) — the canonical reference for RL theory, algorithms, and notation.
- **Temporal difference learning**: Sutton (1988) introduced TD learning, one of the core algorithmic ideas in RL.
- **Regret bounds**: Auer, Jaksch & Ortner (2010) established near-optimal regret bounds, a key theoretical result for understanding exploration-exploitation tradeoffs.
- **Model-based RL**: Szita & Szepesvari (2010) addressed exploration complexity bounds in model-based approaches.
- **Deep RL**: François-Lavet et al. (2018) provide a comprehensive introduction to deep reinforcement learning, bridging classical RL with neural network function approximation.
- **Function approximation in RL**: Busoniu et al. (2010) cover RL and dynamic programming with function approximators, addressing the curse of dimensionality.
- **Approximate dynamic programming**: Powell (2011) focuses on solving the "curses of dimensionality" in dynamic programming.
- **Adaptive control and RL intersection**: Annaswamy (2023) surveys where adaptive control theory and RL converge.
- **RL for optimal control**: Bertsekas (2023) and Li (2023) connect RL with optimal control theory, bridging control engineering and ML.

## Commands and Syntax

No commands or configuration syntax — this is a reference bibliography. Key resources for hands-on learning:
- **Sutton & Barto textbook**: freely available at `incompleteideas.net/sutton/book/the-book.html`
- **Dissecting Reinforcement Learning blog series**: Python implementations at `mpatacchiola.github.io/blog/`
- **Deep RL survey (arXiv:1811.12560)**: open-access introduction to deep RL

## Relationships

- **Q-learning, SARSA, policy gradient**: The bibliography supports the core RL algorithms listed in the AI taxonomy on the same page.
- **Optimal control**: Bertsekas and Li explicitly connect RL to control theory, linking to automated planning and scheduling.
- **Function approximation / deep learning**: François-Lavet et al. and Busoniu et al. bridge RL with neural networks and deep learning.
- **Supervised/unsupervised learning**: RL is positioned alongside supervised and unsupervised learning in the ACM Computing Classification System taxonomy.
- **Robotics**: RL appears as a core algorithm for robotics alongside vision-language-action models.
- **RLHF**: Reinforcement learning from human feedback is listed as a related AI concept, connecting RL to language model alignment.
- **Imitation learning, diffusion models**: Listed alongside RL in the broader AI concepts taxonomy.

## Exam-Relevant Points

- **Sutton & Barto (2018)** is the standard reference — expect exam questions to use its notation and framework.
- **TD learning (Sutton, 1988)** is a foundational algorithm; know that it predates deep RL by decades.
- **Regret bounds** measure the cumulative cost of suboptimal decisions during learning — Auer et al. (2010) established near-optimal bounds.
- **Model-based vs. model-free RL** is a core distinction; Szita & Szepesvari (2010) address model-based exploration complexity.
- **Deep RL** combines RL with deep neural networks for function approximation — François-Lavet et al. (2018) is the standard survey.
- **RL sits in the ACM classification** under Artificial Intelligence > Machine Learning, alongside supervised, unsupervised, multi-task, and cross-validation.
- **RL applications span**: robotics (navigation, control), games (AlphaGo, AlphaZero, MuZero, OpenAI Five), self-driving cars, and action selection.
