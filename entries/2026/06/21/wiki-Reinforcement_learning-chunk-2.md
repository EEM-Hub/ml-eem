---
source: chunks/wiki-Reinforcement_learning-chunk-2.md
source_url: https://en.wikipedia.org/wiki/Reinforcement_learning
---

## Reinforcement Learning: Algorithms for Control Learning

This page covers the core algorithmic approaches for solving reinforcement learning control problems — how an agent uses past experience to find actions that maximize cumulative rewards. It spans the formal framework (policies, value functions, optimality criteria) and the major algorithm families: Monte Carlo methods, temporal difference learning, function approximation, direct policy search, and model-based methods.

## Key Concepts

- **Policy (π)**: A mapping from states to action probabilities. Can be stochastic (π(a,s) = probability) or deterministic (π(s) = single action). Without loss of generality, optimal policies can always be found among deterministic stationary policies.
- **State-value function V^π(s)**: Expected discounted return starting from state s and following policy π. Estimates "how good" it is to be in a given state.
- **Action-value function Q^π(s,a)**: Expected discounted return from taking action a in state s, then following π. Knowing Q* alone is sufficient to act optimally.
- **Discounted return G**: Sum of future rewards weighted by discount factor γ (where 0 ≤ γ < 1), so distant rewards matter less than immediate ones: G = R₁ + γR₂ + γ²R₃ + ...
- **Optimal policy**: Achieves the best expected discounted return from *any* initial state (not dependent on initial state distribution).
- **Stationary policy**: Action distribution depends only on the current state, not the full history.
- **Generalized Policy Iteration (GPI)**: Framework where policy evaluation and policy improvement alternate, possibly before values fully converge.

## Commands and Syntax

No CLI commands — this is theoretical content. Key mathematical formulations:

- **Value iteration** and **policy iteration**: Compute sequences Q_k converging to Q* using full state-space expectations (requires known MDP dynamics).
- **Q-learning**: Derived from value iteration; uses sampled transitions instead of full expectations. Deep Q-learning uses neural networks to represent Q.
- **REINFORCE (Williams)**: Policy gradient method using likelihood ratio estimates of the gradient; also known as the likelihood ratio method in simulation-based optimization.
- **Linear function approximation**: Q(s,a) = Σ θᵢ φᵢ(s,a) — weights θ are adjusted instead of individual state-action values.
- **TD(λ)**: Parameter λ ∈ [0,1] interpolates between pure Monte Carlo (λ=1, no Bellman reliance) and basic TD (λ=0, full Bellman reliance).

## Relationships

- **Monte Carlo vs. Temporal Difference**: MC requires complete episodes and averages full returns; TD updates incrementally using bootstrapped estimates via the Bellman equation. TD handles non-episodic tasks and reduces variance.
- **Value function methods vs. Direct policy search**: Value methods estimate Q*/V* then derive policy; policy search optimizes policy parameters directly (gradient-based like REINFORCE, or gradient-free like simulated annealing, cross-entropy, evolutionary methods).
- **Actor-critic methods**: Combine value function estimation (critic) with direct policy optimization (actor); belong to GPI class. Perform well when policy search alone converges slowly due to noisy returns.
- **Model-based vs. model-free**: Model-based methods (e.g., Dyna) learn transition dynamics and use simulated experience to supplement real transitions. More computationally intensive but can be more sample-efficient. Model predictive control uses the model to update behavior directly rather than updating value functions.
- **Bandit problems**: Monte Carlo RL generalizes multi-armed bandits — both average returns per action, but RL must handle non-stationarity from sequential state dependencies.
- **Dynamic programming**: Requires full MDP knowledge; RL methods approximate the same solutions using sampled experience instead.

## Exam-Relevant Points

- An optimal policy can always be found among **deterministic stationary policies** — no need to search stochastic or history-dependent policies.
- Knowing **Q* alone is sufficient** to act optimally (choose argmax_a Q*(s,a) at each state); V* alone is not sufficient without the transition model.
- **Monte Carlo methods** require episodic tasks and update only after episode completion; they do not require knowledge of environment dynamics.
- **TD(λ)** with λ=0 relies entirely on Bellman equations; λ=1 is equivalent to Monte Carlo (no Bellman reliance). λ provides continuous interpolation.
- **Batch TD methods** (e.g., least-squares TD) use sample information more efficiently; **incremental TD** is necessary when batch methods are computationally infeasible.
- **Function approximation** is required for large/continuous state-action spaces — linear approximation uses feature vectors φ(s,a) with learned weights θ.
- **Policy gradient methods** may get stuck in **local optima**; gradient-free methods (simulated annealing, evolutionary) can theoretically reach global optima.
- **Brute force** is impractical because: (1) number of policies can be infinite, (2) high variance requires many samples per policy.
- **Dyna algorithm**: Learns a model from experience and generates simulated transitions to supplement real ones for value function updates.
- **Partially supervised RL (PSRL)**: Reduces exploration cost by using supervised data to initialize Q-table intelligently instead of zeros.
