---
source: chunks/wiki-Reinforcement_learning-chunk-5.md
source_url: https://en.wikipedia.org/wiki/Reinforcement_learning
---

## Reinforcement Learning — Key References and Foundational Literature

This page collects the primary academic references underpinning reinforcement learning (RL) theory and practice. The citations span foundational surveys, algorithm-defining papers, and application-specific works, providing a bibliography map of the field from the 1984 origins through modern deep RL and its extensions.

## Key Concepts

- **Foundational surveys**: Kaelbling, Littman & Moore (1996) is the canonical early RL survey; Sutton & Barto (2018, 2nd ed.) remains the standard textbook
- **MDP formalism**: van Otterlo & Wiering (2012) and Burnetas & Katehakis (1997) establish the Markov Decision Process foundations and optimal adaptive policies
- **Temporal-difference learning**: Sutton's 1984 PhD thesis introduced temporal credit assignment; Bradtke & Barto (1996) formalized TD prediction
- **Q-learning**: Watkins (1989) PhD thesis is the origin; Mnih et al. (2015) extended it to Deep Q-Networks (DQN) achieving human-level Atari play
- **Policy gradient methods**: Williams (1987) introduced REINFORCE; Peters, Vijayakumar & Schaal (2003) applied policy search to humanoid robotics
- **Actor-critic methods**: Mnih et al. (2016) introduced A3C (Asynchronous Advantage Actor-Critic); Duan et al. (2021) developed Distributional Soft Actor-Critic (DSAC)
- **Eligibility traces**: Singh & Sutton (1996) formalized replacing eligibility traces as a unifying mechanism between TD and Monte Carlo methods
- **Exploration strategies**: Tokic & Palm (2011) proposed Value-Difference Based Exploration, adaptive between epsilon-greedy and softmax
- **Model-based RL**: Sutton (1990) introduced Dyna architecture integrating learning, planning, and acting; van Hasselt et al. (2019) analyzed when parametric models help
- **Deep RL**: Francois-Lavet et al. (2018) provides the comprehensive introduction; adversarial vulnerability explored by Behzadan & Munir (2017), Huang et al. (2017), and Korkmaz (2022)
- **Inverse RL**: Ng & Russell (2000) defined the problem; Ziebart et al. (2008) introduced maximum entropy IRL
- **Intrinsic motivation**: Kaplan & Oudeyer (2004) on learning progress as internal reward; Barto (2013) on intrinsically motivated learning
- **Hierarchical RL**: Kulkarni et al. (2016) integrated temporal abstraction with intrinsic motivation
- **Meta-RL**: Zou (2023) covers meta-reinforcement learning approaches
- **Entity-based RL**: Haramati et al. (2024) and Winter (2023) on entity-centric state representations

## Commands and Syntax

No commands in this reference list, but key resources for implementation:

- **Sutton & Barto (2018)** — free online textbook at `incompleteideas.net`, covers TD learning (Ch. 6), off-policy methods (Ch. 11), eligibility traces, and Monte Carlo methods (§5.4)
- **Francois-Lavet et al. (2018)** — arXiv:1811.12560, comprehensive deep RL tutorial
- **Deisenroth, Neumann & Peters (2013)** — policy search survey for robotics (Foundations and Trends in Robotics, Vol. 2)

## Relationships

- **RL ↔ MDPs**: RL is the solution framework for MDPs; optimal policy theory from Burnetas & Katehakis underpins exploration-exploitation tradeoffs
- **TD Learning ↔ Q-Learning ↔ Deep Q-Networks**: A direct lineage — Sutton (1984) → Watkins (1989) → Mnih et al. (2015)
- **Policy Gradient ↔ Actor-Critic ↔ A3C/SAC**: Williams (1987) → Grondman et al. (2012) → Mnih et al. (2016) / Duan et al. (2021)
- **RL ↔ Neuroscience**: Lee, Seo & Jung (2012) establishes the neural basis, linking dopaminergic reward signals to TD error
- **RL ↔ Inverse RL**: IRL recovers the reward function from observed behavior, enabling imitation learning
- **RL ↔ Fuzzy Logic**: Berenji (1994) and Vincze (2017) combine fuzzy systems with Q-learning for continuous/imprecise domains
- **RL ↔ Robotics**: Peters et al. (2003) and Deisenroth et al. (2013) bridge RL theory to physical control
- **RL ↔ Transfer Learning**: Karimpanal & Bouffanais (2019) use self-organizing maps for knowledge transfer between RL tasks

## Exam-Relevant Points

- **Watkins (1989)** originated Q-learning; **Mnih et al. (2015)** is the DQN paper demonstrating human-level Atari performance — know both dates and contributions
- **Sutton & Barto** is THE reference text; Chapter 6 covers TD learning, Chapter 11 covers off-policy methods, Section 5.4 covers importance sampling for Monte Carlo
- **A3C** (Mnih et al., 2016) introduced asynchronous parallel training for actor-critic; key innovation was multiple parallel agents updating a shared model
- **DSAC** (Duan et al., 2021) addresses value estimation errors in continuous control via distributional critic
- **Exploration-exploitation**: Burnetas & Katehakis (1997) proved optimal adaptive policies for MDPs; Tokic & Palm (2011) proposed practical adaptive exploration
- **Experience replay**: Lin (1992) introduced experience replay for self-improving agents — a precursor to DQN's replay buffer
- **Inverse RL**: Ng & Russell (2000) defined recovering rewards from demonstrations; Ziebart et al. (2008) added maximum entropy formulation — both are foundational
- **Adversarial robustness**: Deep RL policies share adversarial features across MDPs (Korkmaz 2022) — a key limitation of deep RL
- **Temporal credit assignment**: Sutton's 1984 thesis — the problem of determining which past actions led to current rewards is the defining challenge that motivated TD learning
- **Reward shaping/specification**: Li et al. (2017) and Toro Icarte et al. (2022) on temporal logic rewards and reward machines — structured alternatives to scalar reward design
