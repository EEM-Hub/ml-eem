---
source: sources/wiki-Reinforcement_learning.md
source_url: https://en.wikipedia.org/wiki/Reinforcement_learning
chunk: 3/6
---

## Theory

 

Both the asymptotic and finite-sample behaviors of most algorithms are well understood. Algorithms with provably (i.e. in a way that can be proved) good online performance (addressing the exploration issue) are known.

 

Efficient exploration of Markov decision processes is given in Burnetas and Katehakis (1997).[[12]](./Reinforcement_learning#cite_note-Optimal_adaptive_policies_for_Marko-12) Finite-time performance bounds have also appeared for many algorithms, but these bounds are expected to be rather loose and thus more work is needed to better understand the relative advantages and limitations.

 

For incremental algorithms, asymptotic convergence issues have been settled.[*[clarification needed](./Wikipedia:Please_clarify)*] Temporal-difference-based algorithms converge under a wider set of conditions than was previously possible (for example, when used with arbitrary, smooth function approximation).

 

## Research

 
|  | This sectionneeds additional citations forverification.Please helpimprove this articlebyadding citations to reliable sourcesin this section. Unsourced material may be challenged and removed.(October 2022)(Learn how and when to remove this message) |
| --- | --- |

 

Research topics include:

 
- actor-critic architecture[[30]](./Reinforcement_learning#cite_note-30)
- actor-critic-scenery architecture[[3]](./Reinforcement_learning#cite_note-Li-2023-3)
- adaptive methods that work with fewer (or no) parameters under a large number of conditions
- bug detection in software projects[[31]](./Reinforcement_learning#cite_note-31)
- continuous learning
- combinations with logic-based frameworks (e.g., temporal-logic specifications,[[32]](./Reinforcement_learning#cite_note-32) reward machines,[[33]](./Reinforcement_learning#cite_note-33) and probabilistic argumentation).[[34]](./Reinforcement_learning#cite_note-34)
- exploration in large Markov decision processes
- entity-based reinforcement learning[[35]](./Reinforcement_learning#cite_note-35)[[36]](./Reinforcement_learning#cite_note-36)[[37]](./Reinforcement_learning#cite_note-37)
- [human feedback](./Reinforcement_learning_from_human_feedback)[[38]](./Reinforcement_learning#cite_note-38)
- interaction between implicit and explicit learning in skill acquisition
- [intrinsic motivation](./Intrinsic_motivation_(artificial_intelligence)) which differentiates information-seeking, curiosity-type behaviours from task-dependent goal-directed behaviours large-scale empirical evaluations
- large (or continuous) action spaces
- modular and hierarchical reinforcement learning[[39]](./Reinforcement_learning#cite_note-39)
- multiagent/distributed reinforcement learning is a topic of interest. Applications are expanding.[[40]](./Reinforcement_learning#cite_note-40)
- occupant-centric control
- optimization of computing resources[[41]](./Reinforcement_learning#cite_note-41)[[42]](./Reinforcement_learning#cite_note-42)[[43]](./Reinforcement_learning#cite_note-43)
- [partial information](./Partially_observable_Markov_decision_process) (e.g., using [predictive state representation](./Predictive_state_representation))
- reward function based on maximising novel information[[44]](./Reinforcement_learning#cite_note-kaplan2004-44)[[45]](./Reinforcement_learning#cite_note-klyubin2008-45)[[46]](./Reinforcement_learning#cite_note-barto2013-46)
- sample-based planning (e.g., based on [Monte Carlo tree search](./Monte_Carlo_tree_search)).
- securities trading[[47]](./Reinforcement_learning#cite_note-47)
- [transfer learning](./Transfer_learning)[[48]](./Reinforcement_learning#cite_note-48)
- TD learning modeling [dopamine](./Dopamine)-based learning in the brain. [Dopaminergic](./Dopaminergic) projections from the [substantia nigra](./Substantia_nigra) to the [basal ganglia](./Basal_ganglia) function are the prediction error.
- value-function and policy search methods

 

## Comparison of key algorithms

 

The following table lists the key algorithms for learning a policy depending on several criteria:

 
- The algorithm can be on-policy (it performs policy updates using trajectories sampled via the current policy)[[49]](./Reinforcement_learning#cite_note-49) or off-policy.
- The action space may be discrete (e.g. the action space could be "going up", "going left", "going right", "going down", "stay") or continuous (e.g. moving the arm with a given angle).
- The state space may be discrete (e.g. the agent could be in a cell in a grid) or continuous (e.g. the agent could be located at a given position in the plane).

 
| Algorithm | Description | Policy | Action space | State space | Operator |
| --- | --- | --- | --- | --- | --- |
| Monte Carlo | Every visit to Monte Carlo | Either | Discrete | Discrete | Sample-means of state-values or action-values |
| TD learning | State–action–reward–state | Off-policy | Discrete | Discrete | State-value |
| Q-learning | State–action–reward–state | Off-policy | Discrete | Discrete | Action-value |
| SARSA | State–action–reward–state–action | On-policy | Discrete | Discrete | Action-value |
| DQN | Deep Q Network | Off-policy | Discrete | Continuous | Action-value |
| DDPG | Deep Deterministic Policy Gradient | Off-policy | Continuous | Continuous | Action-value |
| A3C | Asynchronous Advantage Actor-Critic Algorithm | On-policy | Continuous[50]or Discrete | Continuous | Advantage (=action-value - state-value) |
| TRPO | Trust Region Policy Optimization | On-policy | Continuous or Discrete | Continuous | Advantage |
| PPO | Proximal Policy Optimization | On-policy | Continuous or Discrete | Continuous | Advantage |
| TD3 | Twin Delayed Deep Deterministic Policy Gradient | Off-policy | Continuous | Continuous | Action-value |
| SAC | Soft Actor-Critic | Off-policy | Continuous | Continuous | Advantage |
| DSAC[51][52][53] | Distributional Soft Actor Critic | Off-policy | Continuous | Continuous | Action-value distribution |

 

### Associative reinforcement learning

 

Associative reinforcement learning tasks combine facets of stochastic learning automata tasks and supervised learning pattern classification tasks. In associative reinforcement learning tasks, the learning system interacts in a closed loop with its environment.[[54]](./Reinforcement_learning#cite_note-54)

 

### Deep reinforcement learning

 

This approach extends reinforcement learning by using a deep neural network and without explicitly designing the state space.[[55]](./Reinforcement_learning#cite_note-intro_deep_RL-55) The work on learning ATARI games by Google [DeepMind](./DeepMind) increased attention to [deep reinforcement learning](./Deep_reinforcement_learning) or [end-to-end reinforcement learning](./End-to-end_reinforcement_learning).[[56]](./Reinforcement_learning#cite_note-DQN2-56)

 

### Adversarial deep reinforcement learning

 

Adversarial deep reinforcement learning is an active area of research in reinforcement learning focusing on vulnerabilities of learned policies. In this research area some studies initially showed that reinforcement learning policies are susceptible to imperceptible adversarial manipulations.[[57]](./Reinforcement_learning#cite_note-57)[[58]](./Reinforcement_learning#cite_note-58)[[59]](./Reinforcement_learning#cite_note-59) While some methods have been proposed to overcome these susceptibilities, in the most recent studies it has been shown that these proposed solutions are far from providing an accurate representation of current vulnerabilities of deep reinforcement learning policies.[[60]](./Reinforcement_learning#cite_note-60)

 

### Fuzzy reinforcement learning

 

By introducing [fuzzy inference](./Fuzzy_control_system) in reinforcement learning,[[61]](./Reinforcement_learning#cite_note-61) approximating the state-action value function with [fuzzy rules](./Fuzzy_rule) in continuous space becomes possible. The IF - THEN form of fuzzy rules make this approach suitable for expressing the results in a form close to natural language. Extending FRL with Fuzzy Rule Interpolation[[62]](./Reinforcement_learning#cite_note-62) allows the use of reduced size sparse fuzzy rule-bases to emphasize cardinal rules (most important state-action values).

 

### Inverse reinforcement learning

 

In inverse reinforcement learning (IRL), no reward function is given. Instead, the reward function is inferred given an observed behavior from an expert. The idea is to mimic observed behavior, which is often optimal or close to optimal.[[63]](./Reinforcement_learning#cite_note-63) One popular IRL paradigm is named maximum entropy inverse reinforcement learning (MaxEnt IRL).[[64]](./Reinforcement_learning#cite_note-64) MaxEnt IRL estimates the parameters of a linear model of the reward function by maximizing the entropy of the probability distribution of observed trajectories subject to constraints related to matching expected feature counts. Recently it has been shown that MaxEnt IRL is a particular case of a more general framework named random utility inverse reinforcement learning (RU-IRL).[[65]](./Reinforcement_learning#cite_note-65) RU-IRL is based on [random utility theory](./Random_utility_model) and Markov decision processes. While prior IRL approaches assume that the apparent random behavior of an observed agent is due to it following a random policy, RU-IRL assumes that the observed agent follows a deterministic policy but randomness in observed behavior is due to the fact that an observer only has partial access to the features the observed agent uses in decision making. The utility function is modeled as a random variable to account for the ignorance of the observer regarding the features the observed agent actually considers in its utility function.

 

### Multi-objective reinforcement learning

 

Multi-objective reinforcement learning (MORL) is a form of reinforcement learning concerned with conflicting alternatives. It is distinct from [multi-objective optimization](./Multi-objective_optimization) in that it is concerned with agents acting in environments.[[66]](./Reinforcement_learning#cite_note-66)[[67]](./Reinforcement_learning#cite_note-67)

 

### Safe reinforcement learning

 

Safe reinforcement learning (SRL) can be defined as the process of learning policies that maximize the expectation of the return in problems in which it is important to ensure reasonable system performance and/or respect safety constraints during the learning and/or deployment processes.[[68]](./Reinforcement_learning#cite_note-68)[[69]](./Reinforcement_learning#cite_note-69) An alternative approach is risk-averse reinforcement learning, where instead of the *expected* return, a *risk-measure* of the return is optimized, such as the [conditional value at risk](./Expected_shortfall) (CVaR).[[70]](./Reinforcement_learning#cite_note-70) In addition to mitigating risk, the CVaR objective increases robustness to model uncertainties.[[71]](./Reinforcement_learning#cite_note-71)[[72]](./Reinforcement_learning#cite_note-72) However, CVaR optimization in risk-averse RL requires special care, to prevent gradient bias[[73]](./Reinforcement_learning#cite_note-73) and blindness to success.[[74]](./Reinforcement_learning#cite_note-74)

 

### Self-reinforcement learning

 

Self-reinforcement learning (or self-learning), is a learning paradigm which does not use the concept of immediate reward      R  a   ( s ,  s ′  )   {\displaystyle R_{a}(s,s')}  ![{\displaystyle R_{a}(s,s')}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5f842d4a4b1340e194d8014d63163e5e27f94215) after transition from     s   {\displaystyle s}  ![{\displaystyle s}](https://wikimedia.org/api/rest_v1/media/math/render/svg/01d131dfd7673938b947072a13a9744fe997e632) to      s ′    {\displaystyle s'}  ![{\displaystyle s'}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5136680c63706cfd17ceddb4acddbfdd0ba5ef2d) with action     a   {\displaystyle a}  ![{\displaystyle a}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ffd2487510aa438433a2579450ab2b3d557e5edc). It does not use an external reinforcement, it only uses the agent internal self-reinforcement. The internal self-reinforcement is provided by mechanism of feelings and emotions. In the learning process emotions are backpropagated by a mechanism of secondary reinforcement. The learning equation does not include the immediate reward, it only includes the state evaluation.

 

The self-reinforcement algorithm updates a memory matrix     W = ‖ ‖  w ( a , s ) ‖ ‖    {\displaystyle W=\|w(a,s)\|}  ![{\displaystyle W=\|w(a,s)\|}](https://wikimedia.org/api/rest_v1/media/math/render/svg/329554a7334e799c6e87c0327520b1f3b3eadadb) such that in each iteration executes the following machine learning routine:

 
1. In situation     s   {\displaystyle s}  ![{\displaystyle s}](https://wikimedia.org/api/rest_v1/media/math/render/svg/01d131dfd7673938b947072a13a9744fe997e632) perform action     a   {\displaystyle a}  ![{\displaystyle a}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ffd2487510aa438433a2579450ab2b3d557e5edc).
2. Receive a consequence situation      s ′    {\displaystyle s'}  ![{\displaystyle s'}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5136680c63706cfd17ceddb4acddbfdd0ba5ef2d).
3. Compute state evaluation     v (  s ′  )   {\displaystyle v(s')}  ![{\displaystyle v(s')}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ecf627d0e9748f5a2a33f97488e76dbb2c939324) of how good it is to be in the consequence situation      s ′    {\displaystyle s'}  ![{\displaystyle s'}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5136680c63706cfd17ceddb4acddbfdd0ba5ef2d).
4. Update crossbar memory      w ′  ( a , s ) = w ( a , s ) + v (  s ′  )   {\displaystyle w'(a,s)=w(a,s)+v(s')}  ![{\displaystyle w'(a,s)=w(a,s)+v(s')}](https://wikimedia.org/api/rest_v1/media/math/render/svg/20975b3e3137f878d335f418c87381fd44cf1e4d).

 

Initial conditions of the memory are received as input from the genetic environment. It is a system with only one input (situation), and only one output (action, or behavior).

 

Self-reinforcement (self-learning) was introduced in 1982 along with a neural network capable of self-reinforcement learning, named Crossbar Adaptive Array (CAA).[[75]](./Reinforcement_learning#cite_note-75)[[76]](./Reinforcement_learning#cite_note-76) The CAA computes, in a crossbar fashion, both decisions about actions and emotions (feelings) about consequence states. The system is driven by the interaction between cognition and emotion.[[77]](./Reinforcement_learning#cite_note-77)

 

## Statistical comparison of reinforcement learning algorithms

 

Efficient comparison of RL algorithms is essential for research, deployment and monitoring of RL systems. To compare different algorithms on a given environment, an agent can be trained for each algorithm. Since the performance is sensitive to implementation details, all algorithms should be implemented as closely as possible to each other.[[78]](./Reinforcement_learning#cite_note-78) After the training is finished, the agents can be run on a sample of test episodes, and their scores (returns) can be compared. Since episodes are typically assumed to be [i.i.d](./I.i.d), standard statistical tools can be used for hypothesis testing, such as [T-test](./Student's_t-test) and [permutation test](./Permutation_test).[[79]](./Reinforcement_learning#cite_note-79) This requires to accumulate all the rewards within an episode into a single number—the episodic return. However, this causes a loss of information, as different time-steps are averaged together, possibly with different levels of noise. Whenever the noise level varies across the episode, the statistical power can be improved significantly, by weighting the rewards according to their estimated noise.[[80]](./Reinforcement_learning#cite_note-80)

 

## Challenges and limitations

 

Despite significant advancements, reinforcement learning (RL) continues to face several challenges and limitations that hinder its widespread application in real-world scenarios.

 

### Sample inefficiency

 

RL algorithms often require a large number of interactions with the environment to learn effective policies, leading to high computational costs and time-intensive to train the agent. For instance, [OpenAI's](./OpenAI) Dota-playing bot utilized thousands of years of simulated gameplay to achieve human-level performance. Techniques like experience replay and [curriculum learning](./Curriculum_learning) have been proposed to reduce sample inefficiency, but these techniques add more complexity and are not always sufficient for real-world applications.

 

### Stability and convergence issues

 

Training RL models, particularly for [deep neural network-based models](./Deep_learning), can be unstable and prone to divergence. A small change in the policy or environment can lead to extreme fluctuations in performance, making it difficult to achieve consistent results. This instability is further enhanced in the case of the continuous or high-dimensional action space, where the learning step becomes more complex and less predictable.

 

### Generalization and transferability

 

The RL agents trained in specific environments often struggle to generalize their learned policies to new, unseen scenarios. This is the major setback preventing the application of RL to dynamic real-world environments where adaptability is crucial. The challenge is to develop such algorithms that can transfer knowledge across tasks and environments without extensive retraining.

 

### Bias and reward function issues

 

Designing appropriate reward functions is critical in RL because poorly designed reward functions can lead to unintended behaviors. In addition, RL systems trained on biased data may perpetuate existing biases and lead to discriminatory or unfair outcomes. Both of these issues requires careful consideration of reward structures and data sources to ensure fairness and desired behaviors.

 


