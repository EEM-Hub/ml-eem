---
source: sources/wiki-Reinforcement_learning.md
source_url: https://en.wikipedia.org/wiki/Reinforcement_learning
chunk: 2/6
---

## Algorithms for control learning

 

Even if the issue of exploration is disregarded and even if the state was observable (assumed hereafter), the problem remains to use past experience to find out which actions lead to higher cumulative rewards.

 

### Criterion of optimality

 

#### Policy

 

The agent's action selection is modeled as a map called *policy*:
         π π  :   A   × ×    S   → →  [ 0 , 1 ]      π π  ( a , s ) = Pr (  A  t    =  a ∣ ∣   S  t    =  s )       {\displaystyle {\begin{aligned}&\pi :{\mathcal {A}}\times {\mathcal {S}}\to [0,1]\\&\pi (a,s)=\Pr(A_{t}{=}a\mid S_{t}{=}s)\end{aligned}}}  ![{\displaystyle {\begin{aligned}&\pi :{\mathcal {A}}\times {\mathcal {S}}\to [0,1]\\&\pi (a,s)=\Pr(A_{t}{=}a\mid S_{t}{=}s)\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/faf86ca6e9ac691c88adc9e5181f49aa9c8ed658)

 

The policy map gives the probability of taking action     a   {\displaystyle a}  ![{\displaystyle a}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ffd2487510aa438433a2579450ab2b3d557e5edc) when in state     s   {\displaystyle s}  ![{\displaystyle s}](https://wikimedia.org/api/rest_v1/media/math/render/svg/01d131dfd7673938b947072a13a9744fe997e632).[[14]](./Reinforcement_learning#cite_note-:0-14): 61  There are also deterministic policies      π π    {\displaystyle \pi }  ![{\displaystyle \pi }](https://wikimedia.org/api/rest_v1/media/math/render/svg/9be4ba0bb8df3af72e90a0535fabcc17431e540a) for which     π π  ( s )   {\displaystyle \pi (s)}  ![{\displaystyle \pi (s)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a3df25793e1e7a06faa8e939a794c8de8b4459bf) denotes the action that should be played at state     s   {\displaystyle s}  ![{\displaystyle s}](https://wikimedia.org/api/rest_v1/media/math/render/svg/01d131dfd7673938b947072a13a9744fe997e632).

 

#### State-value function

 

The state-value function      V  π π    ( s )   {\displaystyle V_{\pi }(s)}  ![{\displaystyle V_{\pi }(s)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/04f08b168d05891950e565017e284abee8bf7cf1) is defined as, *expected discounted return* starting with state     s   {\displaystyle s}  ![{\displaystyle s}](https://wikimedia.org/api/rest_v1/media/math/render/svg/01d131dfd7673938b947072a13a9744fe997e632), i.e.      S  0   = s   {\displaystyle S_{0}=s}  ![{\displaystyle S_{0}=s}](https://wikimedia.org/api/rest_v1/media/math/render/svg/76b9df1ecbdbd4dbae77931a7aa185959d3b55f3), and successively following policy     π π    {\displaystyle \pi }  ![{\displaystyle \pi }](https://wikimedia.org/api/rest_v1/media/math/render/svg/9be4ba0bb8df3af72e90a0535fabcc17431e540a). Hence, roughly speaking, the value function estimates "how good" it is to be in a given state.[[14]](./Reinforcement_learning#cite_note-:0-14): 60 

 

     V  π π    ( s ) =   E   ⁡ ⁡  [ G ∣ ∣   S  0    =  s ] =   E   ⁡ ⁡   [   ∑ ∑   t = 0   ∞ ∞     γ γ   t    R  t + 1   ∣ ∣   S  0    =  s  ]  ,   {\displaystyle V_{\pi }(s)=\operatorname {\mathbb {E} } [G\mid S_{0}{=}s]=\operatorname {\mathbb {E} } \left[\sum _{t=0}^{\infty }\gamma ^{t}R_{t+1}\mid S_{0}{=}s\right],}  ![{\displaystyle V_{\pi }(s)=\operatorname {\mathbb {E} } [G\mid S_{0}{=}s]=\operatorname {\mathbb {E} } \left[\sum _{t=0}^{\infty }\gamma ^{t}R_{t+1}\mid S_{0}{=}s\right],}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2996eb96d86d3825a44865cba9f412f447f5066d)

 

where the random variable     G   {\displaystyle G}  ![{\displaystyle G}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f5f3c8921a3b352de45446a6789b104458c9f90b) denotes the **discounted return**, and is defined as the sum of future discounted rewards:

 

    G =  ∑ ∑   t = 0   ∞ ∞     γ γ   t    R  t + 1   =  R  1   + γ γ   R  2   +  γ γ   2    R  3   + ⋯ ⋯  ,   {\displaystyle G=\sum _{t=0}^{\infty }\gamma ^{t}R_{t+1}=R_{1}+\gamma R_{2}+\gamma ^{2}R_{3}+\cdots ,}  ![{\displaystyle G=\sum _{t=0}^{\infty }\gamma ^{t}R_{t+1}=R_{1}+\gamma R_{2}+\gamma ^{2}R_{3}+\cdots ,}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2ea5e83239be695abb7fef3a349fda8063852820)

 

where      R  t + 1     {\displaystyle R_{t+1}}  ![{\displaystyle R_{t+1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/78bc3f077c19f7db4e89b5529a5861b06ae782b7) is the reward for transitioning from state      S  t     {\displaystyle S_{t}}  ![{\displaystyle S_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7e2391e6e796fbf718be3828080775ac2ac3d3d4) to      S  t + 1     {\displaystyle S_{t+1}}  ![{\displaystyle S_{t+1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7fde0b9d29bcb7e8d3eee3a8f42ead14aa3b8cee),     0 ≤ ≤  γ γ  < 1   {\displaystyle 0\leq \gamma <1}  ![{\displaystyle 0\leq \gamma <1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/84796b874665109176d8773a2e6495f00c7cc360) is the [discount rate](./Q-learning#Discount_factor).     γ γ    {\displaystyle \gamma }  ![{\displaystyle \gamma }](https://wikimedia.org/api/rest_v1/media/math/render/svg/a223c880b0ce3da8f64ee33c4f0010beee400b1a) is less than 1, so rewards in the distant future are weighted less than rewards in the immediate future.

 

The algorithm must find a policy with maximum expected discounted return. From the theory of Markov decision processes it is known that, without loss of generality, the search can be restricted to the set of so-called *stationary* policies. A policy is *stationary* if the action-distribution returned by it depends only on the last state visited (from the observation agent's history). The search can be further restricted to *deterministic* stationary policies. A *deterministic stationary* policy deterministically selects actions based on the current state. Since any such policy can be identified with a mapping from the set of states to the set of actions, these policies can be identified with such mappings with no loss of generality.

 

### Brute force

 

The [brute force](./Brute-force_search) approach entails two steps:

 
- For each possible policy, sample returns while following it
- Choose the policy with the largest expected discounted return

 

One problem with this is that the number of policies can be large, or even infinite. Another is that the variance of the returns may be large, which requires many samples to accurately estimate the discounted return of each policy.

 

These problems can be ameliorated if we assume some structure and allow samples generated from one policy to influence the estimates made for others. The two main approaches for achieving this are [value function estimation](./Reinforcement_learning#Value_function) and [direct policy search](./Reinforcement_learning#Direct_policy_search).

 

### Value function

 See also: [Value function](./Value_function) 

Value function approaches attempt to find a policy that maximizes the discounted return by maintaining a set of estimates of expected discounted returns       E   ⁡ ⁡  [ G ]   {\displaystyle \operatorname {\mathbb {E} } [G]}  ![{\displaystyle \operatorname {\mathbb {E} } [G]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c17deb2341b047040bbddcbb56bae20d587311cb) for some policy (usually either the "current" [on-policy] or the optimal [off-policy] one).

 

These methods rely on the theory of Markov decision processes, where optimality is defined in a sense stronger than the one above: A policy is optimal if it achieves the best-expected discounted return from *any* initial state (i.e., initial distributions play no role in this definition). Again, an optimal policy can always be found among stationary policies.

 

To define optimality in a formal manner, define the state-value of a policy     π π    {\displaystyle \pi }  ![{\displaystyle \pi }](https://wikimedia.org/api/rest_v1/media/math/render/svg/9be4ba0bb8df3af72e90a0535fabcc17431e540a) by

 

     V  π π    ( s ) =   E   ⁡ ⁡  [ G ∣ ∣  s , π π  ] ,   {\displaystyle V^{\pi }(s)=\operatorname {\mathbb {E} } [G\mid s,\pi ],}  ![{\displaystyle V^{\pi }(s)=\operatorname {\mathbb {E} } [G\mid s,\pi ],}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f79fad295cbb4d688fe27b8e58110fddde33549f)

 

where     G   {\displaystyle G}  ![{\displaystyle G}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f5f3c8921a3b352de45446a6789b104458c9f90b) stands for the discounted return associated with following     π π    {\displaystyle \pi }  ![{\displaystyle \pi }](https://wikimedia.org/api/rest_v1/media/math/render/svg/9be4ba0bb8df3af72e90a0535fabcc17431e540a) from the initial state     s   {\displaystyle s}  ![{\displaystyle s}](https://wikimedia.org/api/rest_v1/media/math/render/svg/01d131dfd7673938b947072a13a9744fe997e632). Defining      V  ∗ ∗    ( s )   {\displaystyle V^{*}(s)}  ![{\displaystyle V^{*}(s)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b0c55d312621b3ac9cbd28f1af88d01d4cb4d110) as the maximum possible state-value of      V  π π    ( s )   {\displaystyle V^{\pi }(s)}  ![{\displaystyle V^{\pi }(s)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a42ff0c4c2e0d6e3bbfc997e81544641805798a4), where     π π    {\displaystyle \pi }  ![{\displaystyle \pi }](https://wikimedia.org/api/rest_v1/media/math/render/svg/9be4ba0bb8df3af72e90a0535fabcc17431e540a) is allowed to change,

 

     V  ∗ ∗    ( s ) =  max  π π     V  π π    ( s ) .   {\displaystyle V^{*}(s)=\max _{\pi }V^{\pi }(s).}  ![{\displaystyle V^{*}(s)=\max _{\pi }V^{\pi }(s).}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3a1364980b05ea95dedcefb2082869eab54dd1cc)

 

A policy that achieves these optimal state-values in each state is called *optimal*. Clearly, a policy that is optimal in this sense is also optimal in the sense that it maximizes the expected discounted return, since      V  ∗ ∗    ( s ) =  max  π π     E  [ G ∣ ∣  s , π π  ]   {\displaystyle V^{*}(s)=\max _{\pi }\mathbb {E} [G\mid s,\pi ]}  ![{\displaystyle V^{*}(s)=\max _{\pi }\mathbb {E} [G\mid s,\pi ]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/83afb99d87052615899fbc3413a1e02467143957), where     s   {\displaystyle s}  ![{\displaystyle s}](https://wikimedia.org/api/rest_v1/media/math/render/svg/01d131dfd7673938b947072a13a9744fe997e632) is a state randomly sampled from the distribution     μ μ    {\displaystyle \mu }  ![{\displaystyle \mu }](https://wikimedia.org/api/rest_v1/media/math/render/svg/9fd47b2a39f7a7856952afec1f1db72c67af6161) of initial states (so     μ μ  ( s ) = Pr (  S  0   = s )   {\displaystyle \mu (s)=\Pr(S_{0}=s)}  ![{\displaystyle \mu (s)=\Pr(S_{0}=s)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/de42c6766fe6d309149deb462214e1d2c9f5fa36)).

 

Although state-values suffice to define optimality, it is useful to define action-values. Given a state     s   {\displaystyle s}  ![{\displaystyle s}](https://wikimedia.org/api/rest_v1/media/math/render/svg/01d131dfd7673938b947072a13a9744fe997e632), an action     a   {\displaystyle a}  ![{\displaystyle a}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ffd2487510aa438433a2579450ab2b3d557e5edc) and a policy     π π    {\displaystyle \pi }  ![{\displaystyle \pi }](https://wikimedia.org/api/rest_v1/media/math/render/svg/9be4ba0bb8df3af72e90a0535fabcc17431e540a), the action-value of the pair     ( s , a )   {\displaystyle (s,a)}  ![{\displaystyle (s,a)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9e483c36a133514a0cd6d604f5cce56d2fd4cae9) under     π π    {\displaystyle \pi }  ![{\displaystyle \pi }](https://wikimedia.org/api/rest_v1/media/math/render/svg/9be4ba0bb8df3af72e90a0535fabcc17431e540a) is defined by

 

     Q  π π    ( s , a ) =   E   ⁡ ⁡  [ G ∣ ∣  s , a , π π  ] ,   {\displaystyle Q^{\pi }(s,a)=\operatorname {\mathbb {E} } [G\mid s,a,\pi ],}  ![{\displaystyle Q^{\pi }(s,a)=\operatorname {\mathbb {E} } [G\mid s,a,\pi ],}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a26e4d47d3b8c180b9fe6050106afe85755c6f99)

 

where     G   {\displaystyle G}  ![{\displaystyle G}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f5f3c8921a3b352de45446a6789b104458c9f90b) now stands for the random discounted return associated with first taking action     a   {\displaystyle a}  ![{\displaystyle a}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ffd2487510aa438433a2579450ab2b3d557e5edc) in state     s   {\displaystyle s}  ![{\displaystyle s}](https://wikimedia.org/api/rest_v1/media/math/render/svg/01d131dfd7673938b947072a13a9744fe997e632) and following     π π    {\displaystyle \pi }  ![{\displaystyle \pi }](https://wikimedia.org/api/rest_v1/media/math/render/svg/9be4ba0bb8df3af72e90a0535fabcc17431e540a), thereafter.

 

The theory of Markov decision processes states that if      π π   ∗ ∗      {\displaystyle \pi ^{*}}  ![{\displaystyle \pi ^{*}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f44ad69ec033a9a86437b2edaf620ea0b2c3f494) is an optimal policy, we act optimally (take the optimal action) by choosing the action from      Q   π π   ∗ ∗      ( s , ⋅ ⋅  )   {\displaystyle Q^{\pi ^{*}}(s,\cdot )}  ![{\displaystyle Q^{\pi ^{*}}(s,\cdot )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fafa0cb84fd68dbe99e9b5baa0b421837c2835d8) with the highest action-value at each state,     s   {\displaystyle s}  ![{\displaystyle s}](https://wikimedia.org/api/rest_v1/media/math/render/svg/01d131dfd7673938b947072a13a9744fe997e632). The *action-value function* of such an optimal policy (     Q   π π   ∗ ∗        {\displaystyle Q^{\pi ^{*}}}  ![{\displaystyle Q^{\pi ^{*}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/efdae1153bf5fc57c8777369756d7c5cc20fd90a)) is called the *optimal action-value function* and is commonly denoted by      Q  ∗ ∗      {\displaystyle Q^{*}}  ![{\displaystyle Q^{*}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c1785c0a77ab5a06684e8a7ac4f5e59d59ec0319). In summary, the knowledge of the optimal action-value function alone suffices to know how to act optimally.

 

Assuming full knowledge of the Markov decision process, the two basic approaches to compute the optimal action-value function are [value iteration](./Value_iteration) and [policy iteration](./Policy_iteration). Both algorithms compute a sequence of functions      Q  k     {\displaystyle Q_{k}}  ![{\displaystyle Q_{k}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2fa6cb6cf7ffc157202e52dd5711e755892d1015) (    k = 0 , 1 , 2 , … …    {\displaystyle k=0,1,2,\ldots }  ![{\displaystyle k=0,1,2,\ldots }](https://wikimedia.org/api/rest_v1/media/math/render/svg/b6d4b81efe1ce928c56c7b143cb2591f2100246c)) that converge to      Q  ∗ ∗      {\displaystyle Q^{*}}  ![{\displaystyle Q^{*}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c1785c0a77ab5a06684e8a7ac4f5e59d59ec0319). Computing these functions involves computing expectations over the whole state-space, which is impractical for all but the smallest (finite) Markov decision processes. In reinforcement learning methods, expectations are approximated by averaging over samples and using function approximation techniques to cope with the need to represent value functions over large state-action spaces.

 

#### Monte Carlo methods

 

[Monte Carlo methods](./Monte_Carlo_sampling)[[15]](./Reinforcement_learning#cite_note-15) are used to solve reinforcement learning problems by averaging sample returns. Unlike methods that require full knowledge of the environment's dynamics, Monte Carlo methods rely solely on actual or [simulated](./Simulation) experience—sequences of states, actions, and rewards obtained from interaction with an environment. This makes them applicable in situations where the complete dynamics are unknown. Learning from actual experience does not require prior knowledge of the environment and can still lead to optimal behavior. When using simulated experience, only a model capable of generating sample transitions is required, rather than a full specification of [transition probabilities](./Markov_chain), which is necessary for [dynamic programming](./Dynamic_programming) methods.

 

Monte Carlo methods apply to episodic tasks, where experience is divided into episodes that eventually terminate. Policy and value function updates occur only after the completion of an episode, making these methods incremental on an episode-by-episode basis, though not on a step-by-step (online) basis. The term "Monte Carlo" generally refers to any method involving [random sampling](./Random_sampling); however, in this context, it specifically refers to methods that compute averages from *complete* returns, rather than *partial* returns.

 

These methods function similarly to the [bandit algorithms](./Multi-armed_bandit), in which returns are averaged for each state-action pair. The key difference is that actions taken in one state affect the returns of subsequent states within the same episode, making the problem [non-stationary](./Non-stationary). To address this non-stationarity, Monte Carlo methods use the framework of general policy iteration (GPI). While dynamic programming computes [value functions](./Value_function) using full knowledge of the Markov decision process, Monte Carlo methods learn these functions through sample returns. The value functions and policies interact similarly to dynamic programming to achieve [optimality](./Mathematical_optimization), first addressing the prediction problem and then extending to policy improvement and control, all based on sampled experience.[[14]](./Reinforcement_learning#cite_note-:0-14)

 

#### Temporal difference methods

 Main article: [Temporal difference learning](./Temporal_difference_learning) 

The first problem is corrected by allowing the procedure to change the policy (at some or all states) before the values settle. This too may be problematic as it might prevent convergence. Most current algorithms do this, giving rise to the class of *generalized policy iteration* algorithms. Many [*actor-critic* methods](./Actor-critic_algorithm) belong to this category.

 

The second issue can be corrected by allowing trajectories to contribute to any state-action pair in them. This may also help to some extent with the third problem, although a better solution when returns have high variance is Sutton's [temporal difference](./Temporal_difference) (TD) methods that are based on the recursive [Bellman equation](./Bellman_equation).[[16]](./Reinforcement_learning#cite_note-16)[[17]](./Reinforcement_learning#cite_note-FOOTNOTESuttonBarto2018[httpincompleteideasnetsuttonbookebooknode60html_§6._Temporal-Difference_Learning]-17) The computation in TD methods can be incremental (when after each transition the memory is changed and the transition is thrown away), or batch (when the transitions are batched and the estimates are computed once based on the batch). Batch methods, such as the least-squares temporal difference method,[[18]](./Reinforcement_learning#cite_note-18) may use the information in the samples better, while incremental methods are the only choice when batch methods are infeasible due to their high computational or memory complexity. Some methods try to combine the two approaches. Methods based on temporal differences also overcome the fourth issue.

 

Another problem specific to TD comes from their reliance on the recursive Bellman equation. Most TD methods have a so-called     λ λ    {\displaystyle \lambda }  ![{\displaystyle \lambda }](https://wikimedia.org/api/rest_v1/media/math/render/svg/b43d0ea3c9c025af1be9128e62a18fa74bedda2a) parameter     ( 0 ≤ ≤  λ λ  ≤ ≤  1 )   {\displaystyle (0\leq \lambda \leq 1)}  ![{\displaystyle (0\leq \lambda \leq 1)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/65907c1d6a086eeb039ebeca34502f7463d06b56) that can continuously interpolate between Monte Carlo methods that do not rely on the Bellman equations and the basic TD methods that rely entirely on the Bellman equations. This can be effective in palliating this issue.

 

#### Function approximation methods

 

In order to address the fifth issue, *function approximation methods* are used. *Linear function approximation* starts with a mapping     ϕ ϕ    {\displaystyle \phi }  ![{\displaystyle \phi }](https://wikimedia.org/api/rest_v1/media/math/render/svg/72b1f30316670aee6270a28334bdf4f5072cdde4) that assigns a finite-dimensional vector to each state-action pair. Then, the action values of a state-action pair     ( s , a )   {\displaystyle (s,a)}  ![{\displaystyle (s,a)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9e483c36a133514a0cd6d604f5cce56d2fd4cae9) are obtained by linearly combining the components of     ϕ ϕ  ( s , a )   {\displaystyle \phi (s,a)}  ![{\displaystyle \phi (s,a)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/679d681f66578f81accbbebe2598038097c95965) with some *weights*     θ θ    {\displaystyle \theta }  ![{\displaystyle \theta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/6e5ab2664b422d53eb0c7df3b87e1360d75ad9af):

 

    Q ( s , a ) =  ∑ ∑   i = 1   d    θ θ   i    ϕ ϕ   i   ( s , a ) .   {\displaystyle Q(s,a)=\sum _{i=1}^{d}\theta _{i}\phi _{i}(s,a).}  ![{\displaystyle Q(s,a)=\sum _{i=1}^{d}\theta _{i}\phi _{i}(s,a).}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b8fb9c17e9850dfa123aac5cf0541b629df47de7)

 

The algorithms then adjust the weights, instead of adjusting the values associated with the individual state-action pairs. Methods based on ideas from [nonparametric statistics](./Nonparametric_statistics) (which can be seen to construct their own features) have been explored.

 

Value iteration can also be used as a starting point, giving rise to the [Q-learning](./Q-learning) algorithm and its many variants.[[19]](./Reinforcement_learning#cite_note-19) Including Deep Q-learning methods when a neural network is used to represent Q, with various applications in stochastic search problems.[[20]](./Reinforcement_learning#cite_note-MBK-20)

 

The problem with using action-values is that they may need highly precise estimates of the competing action values that can be hard to obtain when the returns are noisy, though this problem is mitigated to some extent by temporal difference methods. Using the so-called compatible function approximation method compromises generality and efficiency.

 

### Direct policy search

 Main article: [Policy gradient method](./Policy_gradient_method) 

An alternative method is to search directly in (some subset of) the policy space, in which case the problem becomes a case of [stochastic optimization](./Stochastic_optimization). The two approaches available are gradient-based and gradient-free methods.

 

[Gradient](./Gradient)-based methods (*policy gradient methods*) start with a mapping from a finite-dimensional (parameter) space to the space of policies: given the parameter vector     θ θ    {\displaystyle \theta }  ![{\displaystyle \theta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/6e5ab2664b422d53eb0c7df3b87e1360d75ad9af), let      π π   θ θ      {\displaystyle \pi _{\theta }}  ![{\displaystyle \pi _{\theta }}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2a9f6266b9302e47ccd37e867f4a364ff52fb8af) denote the policy associated to     θ θ    {\displaystyle \theta }  ![{\displaystyle \theta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/6e5ab2664b422d53eb0c7df3b87e1360d75ad9af). Defining the performance function by     ρ ρ  ( θ θ  ) =  ρ ρ    π π   θ θ        {\displaystyle \rho (\theta )=\rho ^{\pi _{\theta }}}  ![{\displaystyle \rho (\theta )=\rho ^{\pi _{\theta }}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a66bf6220d37e57309930a00168cf36d105393b9) under mild conditions this function will be differentiable as a function of the parameter vector     θ θ    {\displaystyle \theta }  ![{\displaystyle \theta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/6e5ab2664b422d53eb0c7df3b87e1360d75ad9af). If the gradient of     ρ ρ    {\displaystyle \rho }  ![{\displaystyle \rho }](https://wikimedia.org/api/rest_v1/media/math/render/svg/1f7d439671d1289b6a816e6af7a304be40608d64) was known, one could use [gradient ascent](./Gradient_descent). Since an analytic expression for the gradient is not available, only a noisy estimate is available. Such an estimate can be constructed in many ways, giving rise to algorithms such as Williams's REINFORCE method[[21]](./Reinforcement_learning#cite_note-21) (which is known as the likelihood ratio method in the [simulation-based optimization](./Simulation-based_optimization) literature).[[22]](./Reinforcement_learning#cite_note-22)

 

A large class of methods avoids relying on gradient information. These include [simulated annealing](./Simulated_annealing), [cross-entropy search](./Cross-entropy_method) or methods of [evolutionary computation](./Evolutionary_computation). Many gradient-free methods can achieve (in theory and in the limit) a global optimum.

 

Policy search methods may converge slowly given noisy data. For example, this happens in episodic problems when the trajectories are long and the variance of the returns is large. Value-function based methods that rely on temporal differences might help in this case. In recent years, *actor–critic methods* have been proposed and performed well on various problems.[[23]](./Reinforcement_learning#cite_note-23)

 

Policy search methods have been used in the [robotics](./Robotics) context.[[24]](./Reinforcement_learning#cite_note-24) Many policy search methods may get stuck in local optima (as they are based on [local search](./Local_search_(optimization))).

 

### Model-based algorithms

 

Finally, all of the above methods can be combined with algorithms that first learn a model of the [Markov decision process](./Markov_decision_process), the probability of each next state given an action taken from an existing state. For instance, the Dyna algorithm learns a model from experience, and uses that to provide more modelled transitions for a value function, in addition to the real transitions.[[25]](./Reinforcement_learning#cite_note-25) Such methods can sometimes be extended to use of non-parametric models, such as when the transitions are simply stored and "replayed" to the learning algorithm.[[26]](./Reinforcement_learning#cite_note-26)

 

Model-based methods can be more computationally intensive than model-free approaches, and their utility can be limited by the extent to which the Markov decision process can be learnt.[[27]](./Reinforcement_learning#cite_note-27)

 

There are other ways to use models than to update a value function.[[28]](./Reinforcement_learning#cite_note-28) For instance, in [model predictive control](./Model_predictive_control) the model is used to update the behavior directly.

 

### Partially supervised RL (PSRL)

 

The costly exploration needed to learn an optimal policy can be reduced if some supervised data is available. This can be achieved for instance by learning a crude control policy and using this to initialize the Q table intelligently instead of with zeros.[[29]](./Reinforcement_learning#cite_note-29)

 


