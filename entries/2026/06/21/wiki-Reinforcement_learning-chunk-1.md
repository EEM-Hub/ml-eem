---
source: chunks/wiki-Reinforcement_learning-chunk-1.md
source_url: https://en.wikipedia.org/wiki/Reinforcement_learning
---

## Reinforcement Learning Fundamentals

Reinforcement learning (RL) is one of three core machine learning paradigms (alongside supervised and unsupervised learning). Rather than learning from labeled or unlabeled data, RL trains an agent to maximize cumulative reward through interactions with a dynamic environment. The environment is typically modeled as a Markov decision process (MDP), and the agent must learn a policy mapping states to actions without necessarily having a complete model of the environment.

## Key Concepts

- **Agent-Environment Loop**: At each discrete time step *t*, the agent observes state S_t and reward R_t, selects action A_t, then the environment transitions to S_{t+1} with reward R_{t+1}.
- **Policy (π)**: A mapping π: S × A → [0,1] giving the probability of taking action *a* in state *s*. The goal is to learn an optimal policy maximizing expected cumulative reward.
- **MDP Components**: State space S, action space A, transition probability P_a(s, s'), and immediate reward function R_a(s, s').
- **Exploration vs. Exploitation**: The agent must balance trying new actions (exploration) to learn about the environment versus using known-good actions (exploitation) to maximize reward. This is the exploration-exploitation dilemma.
- **ε-greedy Strategy**: With probability (1 − ε) choose the best-known action; with probability ε choose a random action. ε can be fixed, scheduled, or adaptive.
- **Full vs. Partial Observability**: If the agent sees the full state, the problem is an MDP; if it sees only a subset or noisy observations, it becomes a Partially Observable MDP (POMDP).
- **Regret**: The difference between an agent's performance and the optimal agent's performance.
- **Function Approximation**: Using neural networks or other approximators to handle large or continuous state spaces where tabular methods are infeasible.
- **Multi-armed Bandit**: A simplified RL setting used to study the exploration-exploitation trade-off most thoroughly.

## Commands and Syntax

No specific commands apply (theoretical topic), but the MDP formulation is central:

```
MDP = (S, A, P, R)

P_a(s, s') = Pr(S_{t+1} = s' | S_t = s, A_t = a)   # transition model
R_a(s, s')                                            # reward function
π(s, a) = Pr(A_t = a | S_t = s)                       # policy
```

**ε-greedy pseudocode**:
```
with probability (1 - ε):
    action = argmax_a Q(s, a)    # exploit
with probability ε:
    action = random_action()     # explore
```

## Relationships

- **Supervised / Unsupervised Learning**: RL is the third paradigm — it differs by learning from interaction and reward signals rather than from static datasets.
- **Markov Decision Processes**: The mathematical foundation; RL algorithms are essentially methods for solving MDPs without full knowledge of the model.
- **Dynamic Programming**: Classical DP solves MDPs exactly given a known model; RL relaxes this requirement, using sampling instead.
- **Optimal Control Theory**: RL overlaps with control theory; in operations research literature, RL is called "approximate dynamic programming" or "neuro-dynamic programming."
- **Multi-agent Systems**: RL extends to settings with multiple interacting agents (multi-agent RL, self-play).
- **RLHF (Reinforcement Learning from Human Feedback)**: Connects RL to the "learning with humans" branch, critical for modern LLM alignment.
- **Deep Learning**: Function approximation via neural networks enables deep RL, scaling to complex environments (AlphaGo, autonomous driving).
- **Key Algorithms**: Q-learning, SARSA, policy gradient methods, and temporal difference (TD) learning are the primary RL algorithm families.

## Exam-Relevant Points

- RL is defined by the agent-environment interaction loop, not by dataset characteristics — this is the key distinction from supervised/unsupervised learning.
- The four components of an MDP (S, A, P, R) and what each represents.
- The exploration-exploitation trade-off is fundamental; ε-greedy is the canonical simple strategy.
- RL does **not** require a complete model of the environment — this distinguishes it from classical dynamic programming.
- A **policy** maps states to action probabilities; the goal is to maximize **expected cumulative reward**, not just immediate reward.
- **Partial observability** requires POMDP formulation; full observability allows standard MDP.
- RL is also known as "approximate dynamic programming" in operations research and control literature.
- Two sources of RL's power: (1) sample-based optimization and (2) function approximation for large state spaces.
- The multi-armed bandit problem is the foundational model for studying exploration-exploitation.
- Notable applications: AlphaGo (Go), autonomous driving, robot control, energy storage — know these as examples of RL success in long-horizon planning problems.
