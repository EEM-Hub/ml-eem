---
source: https://en.wikipedia.org/wiki/Reinforcement_learning
fetched: 2026-06-21
---

Field of machine learning For reinforcement learning in psychology, see [Reinforcement](./Reinforcement) and [Operant conditioning](./Operant_conditioning). [![](//upload.wikimedia.org/wikipedia/commons/thumb/1/1b/Reinforcement_learning_diagram.svg/250px-Reinforcement_learning_diagram.svg.png)](./File:Reinforcement_learning_diagram.svg) The typical framing of a reinforcement learning (RL) scenario: an agent takes actions in an environment, which is interpreted into a reward and a state representation, which are fed back to the agent. 
| Part of a series on |
| --- |
| Machine learninganddata mining |
| ParadigmsSupervised learningUnsupervised learningSemi-supervised learningSelf-supervised learningReinforcement learningMeta-learningOnline learningBatch learningCurriculum learningRule-based learningNeuro-symbolic AINeuromorphic engineeringQuantum machine learning |
| ProblemsClassificationGenerative modelingRegressionClusteringDimensionality reductionDensity estimationAnomaly detectionData cleaningAutoMLAssociation rulesSemantic analysisStructured predictionFeature engineeringFeature learningLearning to rankGrammar inductionOntology learningMultimodal learning |
| Supervised learning(classification•regression)Apprenticeship learningDecision treesEnsemblesBaggingBoostingRandom forestk-NNLinear regressionNaive BayesArtificial neural networksLogistic regressionPerceptronRelevance vector machine (RVM)Support vector machine (SVM) |
| ClusteringBIRCHCUREHierarchicalk-meansFuzzyExpectation–maximization (EM)DBSCANOPTICSMean shift |
| Dimensionality reductionFactor analysisCCAICALDANMFPCAPGDt-SNESDL |
| Structured predictionGraphical modelsBayes netConditional random fieldHidden Markov |
| Anomaly detectionRANSACk-NNLocal outlier factorIsolation forest |
| Neural networksAutoencoderDeep learningFeedforward neural networkRecurrent neural networkLSTMGRUESNreservoir computingBoltzmann machineRestrictedGANDiffusion modelSOMConvolutional neural networkU-NetLeNetAlexNetDeepDreamNeural fieldNeural radiance fieldPhysics-informed neural networksTransformerVisionMambaSpiking neural networkMemtransistorElectrochemical RAM(ECRAM) |
| Reinforcement learningQ-learningPolicy gradientSARSATemporal difference (TD)Multi-agentSelf-play |
| Learning with humansActive learningCrowdsourcingHuman-in-the-loopMechanistic interpretabilityRLHF |
| Model diagnosticsCoefficient of determinationConfusion matrixLearning curveROC curve |
| Mathematical foundationsKernel machinesBias–variance tradeoffComputational learning theoryEmpirical risk minimizationOccam learningPAC learningStatistical learningVC theoryTopological deep learning |
| Journals and conferencesAAAICVPRECCVECML PKDDEMNLPICCVNeurIPSICMLICLRIJCAIMLJMLR |
| Related articlesGlossary of artificial intelligenceList of datasets for machine-learning researchList of datasets in computer vision and image processingOutline of machine learning |
| vte |

 

In [machine learning](./Machine_learning) and [optimal control](./Optimal_control), **reinforcement learning** (**RL**) is concerned with how an [intelligent agent](./Intelligent_agent) should [take actions](./Action_selection) in a dynamic environment in order to [maximize a reward](./Reward-based_selection) signal. Reinforcement learning is one of the [three basic machine learning paradigms](./Machine_learning#Approaches), alongside [supervised learning](./Supervised_learning) and [unsupervised learning](./Unsupervised_learning).

 

While supervised learning and unsupervised learning algorithms respectively attempt to discover patterns in labeled and unlabeled data, reinforcement learning involves training an agent through interactions with its environment. To learn to maximize rewards from these interactions, the agent makes decisions between trying new actions to learn more about the environment (exploration), or using current knowledge of the environment to take the best action (exploitation).[[1]](./Reinforcement_learning#cite_note-kaelbling-1) The search for the optimal balance between these two strategies is known as the [exploration–exploitation dilemma](./Exploration–exploitation_dilemma).

The environment is typically stated in the form of a [Markov decision process](./Markov_decision_process), as many reinforcement learning algorithms use [dynamic programming](./Dynamic_programming) techniques.[[2]](./Reinforcement_learning#cite_note-2) The main difference between classical dynamic programming methods and reinforcement learning algorithms is that the latter do not assume knowledge of an exact mathematical model of the Markov decision process, and they target large Markov decision processes where exact methods become infeasible.[[3]](./Reinforcement_learning#cite_note-Li-2023-3)

  

## Principles

 

Due to its generality, reinforcement learning is studied in many disciplines, such as [game theory](./Game_theory), [control theory](./Control_theory), [operations research](./Operations_research), [information theory](./Information_theory), [simulation-based optimization](./Simulation-based_optimization), [multi-agent systems](./Multi-agent_system), [swarm intelligence](./Swarm_intelligence), and [statistics](./Statistics). In the operations research and control literature, RL is called *approximate dynamic programming*, or *neuro-dynamic programming.* The problems of interest in RL have also been studied in the [theory of optimal control](./Optimal_control_theory), which is concerned mostly with the existence and characterization of optimal solutions, and algorithms for their exact computation, and less with learning or approximation (particularly in the absence of a mathematical model of the environment).

 

Basic reinforcement learning is modeled as a [Markov decision process](./Markov_decision_process):

 
- A set of environment and agent states (the state space),       S     {\displaystyle {\mathcal {S}}}  ![{\displaystyle {\mathcal {S}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2302a18e269dbecc43c57c0c2aced3bfae15278d);
- A set of actions (the action space),       A     {\displaystyle {\mathcal {A}}}  ![{\displaystyle {\mathcal {A}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/280ae03440942ab348c2ca9b8db6b56ffa9618f8), of the agent;
-      P  a   ( s ,  s ′  ) = Pr (  S  t + 1    =   s ′  ∣ ∣   S  t    =  s ,  A  t    =  a )   {\displaystyle P_{a}(s,s')=\Pr(S_{t+1}{=}s'\mid S_{t}{=}s,A_{t}{=}a)}  ![{\displaystyle P_{a}(s,s')=\Pr(S_{t+1}{=}s'\mid S_{t}{=}s,A_{t}{=}a)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b4c578518bab14f7217e765bdea0b50df07a7138), the transition probability (at time     t   {\displaystyle t}  ![{\displaystyle t}](https://wikimedia.org/api/rest_v1/media/math/render/svg/65658b7b223af9e1acc877d848888ecdb4466560)) from state     s   {\displaystyle s}  ![{\displaystyle s}](https://wikimedia.org/api/rest_v1/media/math/render/svg/01d131dfd7673938b947072a13a9744fe997e632) to state      s ′    {\displaystyle s'}  ![{\displaystyle s'}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5136680c63706cfd17ceddb4acddbfdd0ba5ef2d) under action     a   {\displaystyle a}  ![{\displaystyle a}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ffd2487510aa438433a2579450ab2b3d557e5edc).
-      R  a   ( s ,  s ′  )   {\displaystyle R_{a}(s,s')}  ![{\displaystyle R_{a}(s,s')}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5f842d4a4b1340e194d8014d63163e5e27f94215), the immediate reward after transitioning from     s   {\displaystyle s}  ![{\displaystyle s}](https://wikimedia.org/api/rest_v1/media/math/render/svg/01d131dfd7673938b947072a13a9744fe997e632) to      s ′    {\displaystyle s'}  ![{\displaystyle s'}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5136680c63706cfd17ceddb4acddbfdd0ba5ef2d) under action     a   {\displaystyle a}  ![{\displaystyle a}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ffd2487510aa438433a2579450ab2b3d557e5edc).

 

The purpose of reinforcement learning is for the agent to learn an optimal (or near-optimal) policy that maximizes the reward function or other user-provided reinforcement signal that accumulates from immediate rewards. This is similar to [processes](./Reinforcement) that appear to occur in animal psychology. For example, biological brains are hardwired to interpret signals such as pain and hunger as negative reinforcements, and interpret pleasure and food intake as positive reinforcements. In some circumstances, animals learn to adopt behaviors that optimize these rewards. This suggests that animals are capable of reinforcement learning.[[4]](./Reinforcement_learning#cite_note-4)[[5]](./Reinforcement_learning#cite_note-5)

 

A basic reinforcement learning agent interacts with its environment in discrete time steps. At each time step t, the agent receives the current state      S  t     {\displaystyle S_{t}}  ![{\displaystyle S_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7e2391e6e796fbf718be3828080775ac2ac3d3d4) and reward      R  t     {\displaystyle R_{t}}  ![{\displaystyle R_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d65b678ee539ac36de96b554af181ac03b7f16a8). It then chooses an action      A  t     {\displaystyle A_{t}}  ![{\displaystyle A_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/265483c517cb98cde609f03a31964d86cdcb05c9) from the set of available actions, which is subsequently sent to the environment. The environment moves to a new state      S  t + 1     {\displaystyle S_{t+1}}  ![{\displaystyle S_{t+1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7fde0b9d29bcb7e8d3eee3a8f42ead14aa3b8cee) and the reward      R  t + 1     {\displaystyle R_{t+1}}  ![{\displaystyle R_{t+1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/78bc3f077c19f7db4e89b5529a5861b06ae782b7) associated with the *transition*     (  S  t   ,  A  t   ,  S  t + 1   )   {\displaystyle (S_{t},A_{t},S_{t+1})}  ![{\displaystyle (S_{t},A_{t},S_{t+1})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/efa800ac9fbf81e68eb97515e04cf99ef35b730d) is determined. The goal of a reinforcement learning agent is to learn a *policy*:

 

         π π  :   S   × ×    A   → →  [ 0 , 1 ]      π π  ( s , a ) = Pr (  A  t    =  a ∣ ∣   S  t    =  s )       {\displaystyle {\begin{aligned}&\pi :{\mathcal {S}}\times {\mathcal {A}}\to [0,1]\\&\pi (s,a)=\Pr(A_{t}{=}a\mid S_{t}{=}s)\end{aligned}}}  ![{\displaystyle {\begin{aligned}&\pi :{\mathcal {S}}\times {\mathcal {A}}\to [0,1]\\&\pi (s,a)=\Pr(A_{t}{=}a\mid S_{t}{=}s)\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ee75e84787ca0c966a0e9f0211d5cc6d7e620cbd)

 

that maximizes the expected cumulative reward.

 

Formulating the problem as a Markov decision process assumes the agent directly observes the current environmental state; in this case, the problem is said to have *full observability*. If the agent only has access to a subset of states, or if the observed states are corrupted by noise, the agent is said to have *partial observability*, and formally the problem must be formulated as a [partially observable Markov decision process](./Partially_observable_Markov_decision_process). In both cases, the set of actions available to the agent can be restricted. For example, the state of an account balance could be restricted to be positive; if the current value of the state is 3 and the state transition attempts to reduce the value by 4, the transition will not be allowed.

 

When the agent's performance is compared to that of an agent that acts optimally, the difference in performance yields the notion of [regret](./Regret_(decision_theory)). In order to act near optimally, the agent must reason about long-term consequences of its actions (i.e., maximize future rewards), although the immediate reward associated with this might be negative.

 

Thus, reinforcement learning is particularly well-suited to problems that include a long-term versus short-term reward trade-off. It has been applied successfully to various problems, including [energy storage](./Energy_storage),[[6]](./Reinforcement_learning#cite_note-6) [robot control](./Robot_control),[[7]](./Reinforcement_learning#cite_note-7) [photovoltaic generators](./Photovoltaic_system),[[8]](./Reinforcement_learning#cite_note-8) [backgammon](./Backgammon), [checkers](./Checkers),[[9]](./Reinforcement_learning#cite_note-FOOTNOTESuttonBarto2018Chapter_11-9) [Go](./Go_(game)) ([AlphaGo](./AlphaGo)), and [autonomous driving systems](./Self-driving_car).[[10]](./Reinforcement_learning#cite_note-Ren-2022-10)

 

Two elements make reinforcement learning powerful: the use of samples to optimize performance, and the use of [function approximation](./Neural_network_(machine_learning)) to deal with large environments. Thanks to these two key components, RL can be used in large environments in the following situations:

 
- A model of the environment is known, but an [analytic solution](./Closed-form_expression) is not available;
- Only a simulation model of the environment is given (the subject of [simulation-based optimization](./Simulation-based_optimization));[[11]](./Reinforcement_learning#cite_note-11)
- The only way to collect information about the environment is to interact with it.

 

The first two of these problems could be considered planning problems (since some form of model is available), while the last one could be considered to be a genuine learning problem. However, reinforcement learning converts both planning problems to [machine learning](./Machine_learning) problems.

 

## Exploration

 

The [trade-off between exploration and exploitation](./Exploration–exploitation_dilemma) has been most thoroughly studied through the [multi-armed bandit](./Multi-armed_bandit) problem and for finite state space Markov decision processes in Burnetas and Katehakis (1997).[[12]](./Reinforcement_learning#cite_note-Optimal_adaptive_policies_for_Marko-12)

 

Reinforcement learning requires clever exploration mechanisms; randomly selecting actions, without reference to an estimated probability distribution, shows poor performance. The case of (small) finite Markov decision processes is relatively well understood. However, due to the lack of algorithms that scale well with the number of states (or scale to problems with infinite state spaces), simple exploration methods are the most practical.

 

One such method is     ε ε    {\displaystyle \varepsilon }  ![{\displaystyle \varepsilon }](https://wikimedia.org/api/rest_v1/media/math/render/svg/a30c89172e5b88edbd45d3e2772c7f5e562e5173)-greedy, where     0 < ε ε  < 1   {\displaystyle 0<\varepsilon <1}  ![{\displaystyle 0<\varepsilon <1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a62c0bbc36352f492bde6217430cfe342032487d) is a parameter controlling the amount of exploration vs. exploitation. With probability     1 − −  ε ε    {\displaystyle 1-\varepsilon }  ![{\displaystyle 1-\varepsilon }](https://wikimedia.org/api/rest_v1/media/math/render/svg/09646b74d0bca9befab4b7e9456a44a20d250ace), exploitation is chosen, and the agent chooses the action that it believes has the best long-term effect (ties between actions are broken uniformly at random). Alternatively, with probability     ε ε    {\displaystyle \varepsilon }  ![{\displaystyle \varepsilon }](https://wikimedia.org/api/rest_v1/media/math/render/svg/a30c89172e5b88edbd45d3e2772c7f5e562e5173), exploration is chosen, and the action is chosen uniformly at random.     ε ε    {\displaystyle \varepsilon }  ![{\displaystyle \varepsilon }](https://wikimedia.org/api/rest_v1/media/math/render/svg/a30c89172e5b88edbd45d3e2772c7f5e562e5173) is usually a fixed parameter but can be adjusted either according to a schedule (making the agent explore progressively less), or adaptively based on heuristics.[[13]](./Reinforcement_learning#cite_note-13)

 

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

  

## References

  
1. [↑](./Reinforcement_learning#cite_ref-kaelbling_1-0) [Kaelbling, Leslie P.](./Leslie_P._Kaelbling); [Littman, Michael L.](./Michael_L._Littman); [Moore, Andrew W.](./Andrew_W._Moore) (1996). ["Reinforcement Learning: A Survey"](http://webarchive.loc.gov/all/20011120234539/http://www.cs.washington.edu/research/jair/abstracts/kaelbling96a.html). *Journal of Artificial Intelligence Research*. **4**: 237–285. [arXiv](./ArXiv_(identifier)):[cs/9605103](https://arxiv.org/abs/cs/9605103). [doi](./Doi_(identifier)):[10.1613/jair.301](https://doi.org/10.1613%2Fjair.301). [S2CID](./S2CID_(identifier)) [1708582](https://api.semanticscholar.org/CorpusID:1708582). Archived from [the original](http://www.cs.washington.edu/research/jair/abstracts/kaelbling96a.html) on 2001-11-20.
2. [↑](./Reinforcement_learning#cite_ref-2) van Otterlo, M.; Wiering, M. (2012). "Reinforcement Learning and Markov Decision Processes". *Reinforcement Learning*. Adaptation, Learning, and Optimization. Vol. 12. pp. 3–42. [doi](./Doi_(identifier)):[10.1007/978-3-642-27645-3_1](https://doi.org/10.1007%2F978-3-642-27645-3_1). [ISBN](./ISBN_(identifier)) [978-3-642-27644-6](./Special:BookSources/978-3-642-27644-6).
3. [1](./Reinforcement_learning#cite_ref-Li-2023_3-0) [2](./Reinforcement_learning#cite_ref-Li-2023_3-1) Li, Shengbo (2023). [*Reinforcement Learning for Sequential Decision and Optimal Control*](https://link.springer.com/book/10.1007/978-981-19-7784-8) (First ed.). Springer Verlag, Singapore. pp. 1–460. [doi](./Doi_(identifier)):[10.1007/978-981-19-7784-8](https://doi.org/10.1007%2F978-981-19-7784-8). [ISBN](./ISBN_(identifier)) [978-9-811-97783-1](./Special:BookSources/978-9-811-97783-1). [S2CID](./S2CID_(identifier)) [257928563](https://api.semanticscholar.org/CorpusID:257928563).`{{cite book}}`:  CS1 maint: location missing publisher ([link](./Category:CS1_maint:_location_missing_publisher))
4. [↑](./Reinforcement_learning#cite_ref-4) Russell, Stuart J.; Norvig, Peter (2010). *Artificial intelligence: a modern approach* (Third ed.). Upper Saddle River, New Jersey: [Prentice Hall](./Prentice_Hall). pp. 830, 831. [ISBN](./ISBN_(identifier)) [978-0-13-604259-4](./Special:BookSources/978-0-13-604259-4).
5. [↑](./Reinforcement_learning#cite_ref-5) Lee, Daeyeol; Seo, Hyojung; Jung, Min Whan (21 July 2012). ["Neural Basis of Reinforcement Learning and Decision Making"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3490621). *Annual Review of Neuroscience*. **35** (1): 287–308. [doi](./Doi_(identifier)):[10.1146/annurev-neuro-062111-150512](https://doi.org/10.1146%2Fannurev-neuro-062111-150512). [PMC](./PMC_(identifier)) [3490621](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3490621). [PMID](./PMID_(identifier)) [22462543](https://pubmed.ncbi.nlm.nih.gov/22462543).
6. [↑](./Reinforcement_learning#cite_ref-6) Salazar Duque, Edgar Mauricio; Giraldo, Juan S.; Vergara, Pedro P.; Nguyen, Phuong; Van Der Molen, Anne; Slootweg, Han (2022). ["Community energy storage operation via reinforcement learning with eligibility traces"](https://doi.org/10.1016%2Fj.epsr.2022.108515). *Electric Power Systems Research*. **212** 108515. [Bibcode](./Bibcode_(identifier)):[2022EPSR..21208515S](https://ui.adsabs.harvard.edu/abs/2022EPSR..21208515S). [doi](./Doi_(identifier)):[10.1016/j.epsr.2022.108515](https://doi.org/10.1016%2Fj.epsr.2022.108515). [S2CID](./S2CID_(identifier)) [250635151](https://api.semanticscholar.org/CorpusID:250635151).
7. [↑](./Reinforcement_learning#cite_ref-7) Xie, Zhaoming; Hung Yu Ling; Nam Hee Kim; Michiel van de Panne (2020). "ALLSTEPS: Curriculum-driven Learning of Stepping Stone Skills". [arXiv](./ArXiv_(identifier)):[2005.04323](https://arxiv.org/abs/2005.04323) [[cs.GR](https://arxiv.org/archive/cs.GR)].
8. [↑](./Reinforcement_learning#cite_ref-8) Vergara, Pedro P.; Salazar, Mauricio; Giraldo, Juan S.; Palensky, Peter (2022). ["Optimal dispatch of PV inverters in unbalanced distribution systems using Reinforcement Learning"](https://doi.org/10.1016%2Fj.ijepes.2021.107628). *International Journal of Electrical Power & Energy Systems*. **136** 107628. [Bibcode](./Bibcode_(identifier)):[2022IJEPE.13607628V](https://ui.adsabs.harvard.edu/abs/2022IJEPE.13607628V). [doi](./Doi_(identifier)):[10.1016/j.ijepes.2021.107628](https://doi.org/10.1016%2Fj.ijepes.2021.107628). [S2CID](./S2CID_(identifier)) [244099841](https://api.semanticscholar.org/CorpusID:244099841).
9. [↑](./Reinforcement_learning#cite_ref-FOOTNOTESuttonBarto2018Chapter_11_9-0) [Sutton & Barto 2018](./Reinforcement_learning#CITEREFSuttonBarto2018), Chapter 11.
10. [↑](./Reinforcement_learning#cite_ref-Ren-2022_10-0) Ren, Yangang; Jiang, Jianhua; Zhan, Guojian; Li, Shengbo Eben; Chen, Chen; Li, Keqiang; Duan, Jingliang (2026). "Self-Learned Intelligence for Integrated Decision and Control of Automated Vehicles at Signalized Intersections". *IEEE Transactions on Intelligent Transportation Systems*. **23** (12): 24145–24156. [arXiv](./ArXiv_(identifier)):[2110.12359](https://arxiv.org/abs/2110.12359). [Bibcode](./Bibcode_(identifier)):[2022ITITr..2324145R](https://ui.adsabs.harvard.edu/abs/2022ITITr..2324145R). [doi](./Doi_(identifier)):[10.1109/TITS.2022.3196167](https://doi.org/10.1109%2FTITS.2022.3196167).
11. [↑](./Reinforcement_learning#cite_ref-11) [Gosavi, Abhijit](./Abhijit_Gosavi?action=edit&redlink=1) (2003). [*Simulation-based Optimization: Parametric Optimization Techniques and Reinforcement*](https://www.springer.com/mathematics/applications/book/978-1-4020-7454-7). Operations Research/Computer Science Interfaces Series. Springer. [ISBN](./ISBN_(identifier)) [978-1-4020-7454-7](./Special:BookSources/978-1-4020-7454-7).
12. [1](./Reinforcement_learning#cite_ref-Optimal_adaptive_policies_for_Marko_12-0) [2](./Reinforcement_learning#cite_ref-Optimal_adaptive_policies_for_Marko_12-1) Burnetas, Apostolos N.; [Katehakis, Michael N.](./Michael_N._Katehakis) (1997), "Optimal adaptive policies for Markov Decision Processes", *[Mathematics of Operations Research](./Mathematics_of_Operations_Research)*, **22** (1): 222–255, [doi](./Doi_(identifier)):[10.1287/moor.22.1.222](https://doi.org/10.1287%2Fmoor.22.1.222), [JSTOR](./JSTOR_(identifier)) [3690147](https://www.jstor.org/stable/3690147)
13. [↑](./Reinforcement_learning#cite_ref-13) Tokic, Michel; Palm, Günther (2011), ["Value-Difference Based Exploration: Adaptive Control Between Epsilon-Greedy and Softmax"](http://www.tokic.com/www/tokicm/publikationen/papers/KI2011.pdf) (PDF), *KI 2011: Advances in Artificial Intelligence*, Lecture Notes in Computer Science, vol. 7006, Springer, pp. 335–346, [ISBN](./ISBN_(identifier)) [978-3-642-24455-1](./Special:BookSources/978-3-642-24455-1)
14. [1](./Reinforcement_learning#cite_ref-:0_14-0) [2](./Reinforcement_learning#cite_ref-:0_14-1) [3](./Reinforcement_learning#cite_ref-:0_14-2) ["Reinforcement learning: An introduction"](https://web.archive.org/web/20170712170739/http://people.inf.elte.hu/lorincz/Files/RL_2006/SuttonBook.pdf) (PDF). Archived from [the original](http://people.inf.elte.hu/lorincz/Files/RL_2006/SuttonBook.pdf) (PDF) on 2017-07-12. Retrieved 2017-07-23.
15. [↑](./Reinforcement_learning#cite_ref-15) Singh, Satinder P.; Sutton, Richard S. (1996-03-01). ["Reinforcement learning with replacing eligibility traces"](https://link.springer.com/article/10.1007/BF00114726). *Machine Learning*. **22** (1): 123–158. [doi](./Doi_(identifier)):[10.1007/BF00114726](https://doi.org/10.1007%2FBF00114726). [ISSN](./ISSN_(identifier)) [1573-0565](https://search.worldcat.org/issn/1573-0565).
16. [↑](./Reinforcement_learning#cite_ref-16) [Sutton, Richard S.](./Richard_S._Sutton) (1984). [*Temporal Credit Assignment in Reinforcement Learning*](https://web.archive.org/web/20170330002227/http://incompleteideas.net/sutton/publications.html#PhDthesis) (PhD thesis). University of Massachusetts, Amherst, MA. Archived from [the original](http://incompleteideas.net/sutton/publications.html#PhDthesis) on 2017-03-30. Retrieved 2017-03-29.
17. [↑](./Reinforcement_learning#cite_ref-FOOTNOTESuttonBarto2018[httpincompleteideasnetsuttonbookebooknode60html_§6._Temporal-Difference_Learning]_17-0) [Sutton & Barto 2018](./Reinforcement_learning#CITEREFSuttonBarto2018), [§6. Temporal-Difference Learning](http://incompleteideas.net/sutton/book/ebook/node60.html).
18. [↑](./Reinforcement_learning#cite_ref-18) [Bradtke, Steven J.](./Steven_J._Bradtke?action=edit&redlink=1); [Barto, Andrew G.](./Andrew_G._Barto) (1996). "Learning to predict by the method of temporal differences". *Machine Learning*. **22**: 33–57. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.143.857](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.143.857). [doi](./Doi_(identifier)):[10.1023/A:1018056104778](https://doi.org/10.1023%2FA%3A1018056104778). [S2CID](./S2CID_(identifier)) [20327856](https://api.semanticscholar.org/CorpusID:20327856).
19. [↑](./Reinforcement_learning#cite_ref-19) [Watkins, Christopher J.C.H.](./Christopher_J.C.H._Watkins?action=edit&redlink=1) (1989). [*Learning from Delayed Rewards*](http://www.cs.rhul.ac.uk/~chrisw/new_thesis.pdf) (PDF) (PhD thesis). King's College, Cambridge, UK.
20. [↑](./Reinforcement_learning#cite_ref-MBK_20-0) Matzliach, Barouch; Ben-Gal, Irad; Kagan, Evgeny (2022). ["Detection of Static and Mobile Targets by an Autonomous Agent with Deep Q-Learning Abilities"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9407070). *Entropy*. **24** (8): 1168. [Bibcode](./Bibcode_(identifier)):[2022Entrp..24.1168M](https://ui.adsabs.harvard.edu/abs/2022Entrp..24.1168M). [doi](./Doi_(identifier)):[10.3390/e24081168](https://doi.org/10.3390%2Fe24081168). [PMC](./PMC_(identifier)) [9407070](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9407070). [PMID](./PMID_(identifier)) [36010832](https://pubmed.ncbi.nlm.nih.gov/36010832).
21. [↑](./Reinforcement_learning#cite_ref-21) [Williams, Ronald J.](./Ronald_J._Williams) (1987). "A class of gradient-estimating algorithms for reinforcement learning in neural networks". *Proceedings of the IEEE First International Conference on Neural Networks*. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.129.8871](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.129.8871).
22. [↑](./Reinforcement_learning#cite_ref-22) [Peters, Jan](./Jan_Peters_(computer_scientist)); [Vijayakumar, Sethu](./Sethu_Vijayakumar); [Schaal, Stefan](./Stefan_Schaal) (2003). [*Reinforcement Learning for Humanoid Robotics*](https://web.archive.org/web/20130512223911/http://www-clmc.usc.edu/publications/p/peters-ICHR2003.pdf) (PDF). IEEE-RAS International Conference on Humanoid Robots. Archived from [the original](http://www-clmc.usc.edu/publications/p/peters-ICHR2003.pdf) (PDF) on 2013-05-12. Retrieved 2006-05-08.
23. [↑](./Reinforcement_learning#cite_ref-23) Juliani, Arthur (2016-12-17). ["Simple Reinforcement Learning with Tensorflow Part 8: Asynchronous Actor-Critic Agents (A3C)"](https://medium.com/emergent-future/simple-reinforcement-learning-with-tensorflow-part-8-asynchronous-actor-critic-agents-a3c-c88f72a5e9f2). *Medium*. Retrieved 2018-02-22.
24. [↑](./Reinforcement_learning#cite_ref-24) [Deisenroth, Marc Peter](./Marc_Peter_Deisenroth?action=edit&redlink=1); Neumann, Gerhard; [Peters, Jan](./Jan_Peters_(computer_scientist)) (2013). [*A Survey on Policy Search for Robotics*](http://eprints.lincoln.ac.uk/28029/1/PolicySearchReview.pdf) (PDF). Foundations and Trends in Robotics. Vol. 2. NOW Publishers. pp. 1–142. [doi](./Doi_(identifier)):[10.1561/2300000021](https://doi.org/10.1561%2F2300000021). [hdl](./Hdl_(identifier)):[10044/1/12051](https://hdl.handle.net/10044%2F1%2F12051).
25. [↑](./Reinforcement_learning#cite_ref-25) Sutton, Richard (1990). "Integrated Architectures for Learning, Planning and Reacting based on Dynamic Programming". *Machine Learning: Proceedings of the Seventh International Workshop*.
26. [↑](./Reinforcement_learning#cite_ref-26) Lin, Long-Ji (1992). ["Self-improving reactive agents based on reinforcement learning, planning and teaching"](https://link.springer.com/content/pdf/10.1007/BF00992699.pdf) (PDF). *Machine Learning*. Vol. 8. [doi](./Doi_(identifier)):[10.1007/BF00992699](https://doi.org/10.1007%2FBF00992699).
27. [↑](./Reinforcement_learning#cite_ref-27) Zou, Lan (2023-01-01), Zou, Lan (ed.), ["Chapter 7 - Meta-reinforcement learning"](https://www.sciencedirect.com/science/article/pii/B9780323899314000110), *Meta-Learning*, Academic Press, pp. 267–297, [doi](./Doi_(identifier)):[10.1016/b978-0-323-89931-4.00011-0](https://doi.org/10.1016%2Fb978-0-323-89931-4.00011-0), [ISBN](./ISBN_(identifier)) [978-0-323-89931-4](./Special:BookSources/978-0-323-89931-4), retrieved 2023-11-08`{{citation}}`:  CS1 maint: work parameter with ISBN ([link](./Category:CS1_maint:_work_parameter_with_ISBN))
28. [↑](./Reinforcement_learning#cite_ref-28) van Hasselt, Hado; Hessel, Matteo; Aslanides, John (2019). ["When to use parametric models in reinforcement learning?"](https://proceedings.neurips.cc/paper/2019/file/1b742ae215adf18b75449c6e272fd92d-Paper.pdf) (PDF). *Advances in Neural Information Processing Systems*. Vol. 32.
29. [↑](./Reinforcement_learning#cite_ref-29) Khuat, Thanh Tung; Bassett, Robert; Otte, Ellen; Grevis-James, Alistair; Gabrys, Bogdan (2024-03-01). ["Applications of machine learning in antibody discovery, process development, manufacturing and formulation: Current trends, challenges, and opportunities"](https://www.sciencedirect.com/science/article/pii/S0098135424000036). *Computers & Chemical Engineering*. **182** 108585. [doi](./Doi_(identifier)):[10.1016/j.compchemeng.2024.108585](https://doi.org/10.1016%2Fj.compchemeng.2024.108585). [ISSN](./ISSN_(identifier)) [0098-1354](https://search.worldcat.org/issn/0098-1354).
30. [↑](./Reinforcement_learning#cite_ref-30) Grondman, Ivo; Vaandrager, Maarten; Busoniu, Lucian; Babuska, Robert; Schuitema, Erik (2012-06-01). ["Efficient Model Learning Methods for Actor–Critic Control"](https://dl.acm.org/doi/10.1109/TSMCB.2011.2170565). *IEEE Transactions on Systems, Man, and Cybernetics - Part B: Cybernetics*. **42** (3): 591–602. [Bibcode](./Bibcode_(identifier)):[2012ITSMC..42..591G](https://ui.adsabs.harvard.edu/abs/2012ITSMC..42..591G). [doi](./Doi_(identifier)):[10.1109/TSMCB.2011.2170565](https://doi.org/10.1109%2FTSMCB.2011.2170565). [ISSN](./ISSN_(identifier)) [1083-4419](https://search.worldcat.org/issn/1083-4419). [PMID](./PMID_(identifier)) [22156998](https://pubmed.ncbi.nlm.nih.gov/22156998).
31. [↑](./Reinforcement_learning#cite_ref-31) ["On the Use of Reinforcement Learning for Testing Game Mechanics: ACM - Computers in Entertainment"](https://cie.acm.org/articles/use-reinforcements-learning-testing-game-mechanics/). *cie.acm.org*. Retrieved 2018-11-27.
32. [↑](./Reinforcement_learning#cite_ref-32) Li, Xiao; Vasile, Cristian-Ioan; Belta, Calin (2017). ["Reinforcement Learning with Temporal Logic Rewards"](https://dl.acm.org/doi/10.1109/IROS.2017.8206234). *2017 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS)*. pp. 3834–3839. [doi](./Doi_(identifier)):[10.1109/IROS.2017.8206234](https://doi.org/10.1109%2FIROS.2017.8206234).
33. [↑](./Reinforcement_learning#cite_ref-33) Toro Icarte, Rodrigo; Klassen, Toryn Q.; Valenzano, Richard; McIlraith, Sheila A. (2022). ["Reward Machines: Exploiting Reward Function Structure in Reinforcement Learning"](https://dl.acm.org/doi/10.1613/jair.1.12440). *Journal of Artificial Intelligence Research*. **73**: 173–208. [arXiv](./ArXiv_(identifier)):[2010.03950](https://arxiv.org/abs/2010.03950). [doi](./Doi_(identifier)):[10.1613/jair.1.12440](https://doi.org/10.1613%2Fjair.1.12440).
34. [↑](./Reinforcement_learning#cite_ref-34) Riveret, Régis; Gao, Yang; Governatori, Guido; Rotolo, Antonino; Pitt, Jeremy; Sartor, Giovanni (2019). ["A probabilistic argumentation framework for reinforcement learning agents"](https://link.springer.com/article/10.1007/s10458-019-09404-2). *Autonomous Agents and Multi-Agent Systems*. **33** (1–2): 216–274. [doi](./Doi_(identifier)):[10.1007/s10458-019-09404-2](https://doi.org/10.1007%2Fs10458-019-09404-2).
35. [↑](./Reinforcement_learning#cite_ref-35) Haramati, Dan; Daniel, Tal; Tamar, Aviv (2024). "Entity-Centric Reinforcement Learning for Object Manipulation from Pixels". [arXiv](./ArXiv_(identifier)):[2404.01220](https://arxiv.org/abs/2404.01220) [[cs.RO](https://arxiv.org/archive/cs.RO)].
36. [↑](./Reinforcement_learning#cite_ref-36) Thompson, Isaac Symes; Caron, Alberto; Hicks, Chris; Mavroudis, Vasilios (2024-11-07). "Entity-based Reinforcement Learning for Autonomous Cyber Defence". *Proceedings of the Workshop on Autonomous Cybersecurity (AutonomousCyber '24)*. ACM. pp. 56–67. [arXiv](./ArXiv_(identifier)):[2410.17647](https://arxiv.org/abs/2410.17647). [doi](./Doi_(identifier)):[10.1145/3689933.3690835](https://doi.org/10.1145%2F3689933.3690835).
37. [↑](./Reinforcement_learning#cite_ref-37) Winter, Clemens (2023-04-14). ["Entity-Based Reinforcement Learning"](https://clemenswinter.com/2023/04/14/entity-based-reinforcement-learning/). *Clemens Winter's Blog*.
38. [↑](./Reinforcement_learning#cite_ref-38) Yamagata, Taku; McConville, Ryan; Santos-Rodriguez, Raul (2021-11-16). "Reinforcement Learning with Feedback from Multiple Humans with Diverse Skills". [arXiv](./ArXiv_(identifier)):[2111.08596](https://arxiv.org/abs/2111.08596) [[cs.LG](https://arxiv.org/archive/cs.LG)].
39. [↑](./Reinforcement_learning#cite_ref-39) Kulkarni, Tejas D.; Narasimhan, Karthik R.; Saeedi, Ardavan; Tenenbaum, Joshua B. (2016). ["Hierarchical Deep Reinforcement Learning: Integrating Temporal Abstraction and Intrinsic Motivation"](http://dl.acm.org/citation.cfm?id=3157382.3157509). *Proceedings of the 30th International Conference on Neural Information Processing Systems*. NIPS'16. USA: Curran Associates Inc.: 3682–3690. [arXiv](./ArXiv_(identifier)):[1604.06057](https://arxiv.org/abs/1604.06057). [Bibcode](./Bibcode_(identifier)):[2016arXiv160406057K](https://ui.adsabs.harvard.edu/abs/2016arXiv160406057K). [ISBN](./ISBN_(identifier)) [978-1-5108-3881-9](./Special:BookSources/978-1-5108-3881-9).
40. [↑](./Reinforcement_learning#cite_ref-40) ["Reinforcement Learning / Successes of Reinforcement Learning"](http://umichrl.pbworks.com/Successes-of-Reinforcement-Learning/). *umichrl.pbworks.com*. Retrieved 2017-08-06.
41. [↑](./Reinforcement_learning#cite_ref-41) Dey, Somdip; Singh, Amit Kumar; Wang, Xiaohang; McDonald-Maier, Klaus (March 2020). ["User Interaction Aware Reinforcement Learning for Power and Thermal Efficiency of CPU-GPU Mobile MPSoCs"](https://ieeexplore.ieee.org/document/9116294). [*2020 Design, Automation & Test in Europe Conference & Exhibition (DATE)*](http://repository.essex.ac.uk/27546/1/User%20Interaction%20Aware%20Reinforcement%20Learning.pdf) (PDF). pp. 1728–1733. [doi](./Doi_(identifier)):[10.23919/DATE48585.2020.9116294](https://doi.org/10.23919%2FDATE48585.2020.9116294). [ISBN](./ISBN_(identifier)) [978-3-9819263-4-7](./Special:BookSources/978-3-9819263-4-7). [S2CID](./S2CID_(identifier)) [219858480](https://api.semanticscholar.org/CorpusID:219858480).
42. [↑](./Reinforcement_learning#cite_ref-42) Quested, Tony. ["Smartphones get smarter with Essex innovation"](https://www.businessweekly.co.uk/news/academia-research/smartphones-get-smarter-essex-innovation). *Business Weekly*. Retrieved 2021-06-17.
43. [↑](./Reinforcement_learning#cite_ref-43) Williams, Rhiannon (2020-07-21). ["Future smartphones 'will prolong their own battery life by monitoring owners' behaviour'"](https://inews.co.uk/news/technology/future-smartphones-prolong-battery-life-monitoring-behaviour-558689). *[i](./I_(British_newspaper))*. Retrieved 2021-06-17.
44. [↑](./Reinforcement_learning#cite_ref-kaplan2004_44-0) Kaplan, F.; Oudeyer, P. (2004). "Maximizing Learning Progress: An Internal Reward System for Development". In Iida, F.; Pfeifer, R.; Steels, L.; Kuniyoshi, Y. (eds.). *Embodied Artificial Intelligence*. Lecture Notes in Computer Science. Vol. 3139. Berlin; Heidelberg: Springer. pp. 259–270. [doi](./Doi_(identifier)):[10.1007/978-3-540-27833-7_19](https://doi.org/10.1007%2F978-3-540-27833-7_19). [ISBN](./ISBN_(identifier)) [978-3-540-22484-6](./Special:BookSources/978-3-540-22484-6). [S2CID](./S2CID_(identifier)) [9781221](https://api.semanticscholar.org/CorpusID:9781221).
45. [↑](./Reinforcement_learning#cite_ref-klyubin2008_45-0) Klyubin, A.; Polani, D.; Nehaniv, C. (2008). ["Keep your options open: an information-based driving principle for sensorimotor systems"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2607028). *PLOS ONE*. **3** (12) e4018. [Bibcode](./Bibcode_(identifier)):[2008PLoSO...3.4018K](https://ui.adsabs.harvard.edu/abs/2008PLoSO...3.4018K). [doi](./Doi_(identifier)):[10.1371/journal.pone.0004018](https://doi.org/10.1371%2Fjournal.pone.0004018). [PMC](./PMC_(identifier)) [2607028](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2607028). [PMID](./PMID_(identifier)) [19107219](https://pubmed.ncbi.nlm.nih.gov/19107219).
46. [↑](./Reinforcement_learning#cite_ref-barto2013_46-0) Barto, A. G. (2013). "Intrinsic motivation and reinforcement learning". [*Intrinsically Motivated Learning in Natural and Artificial Systems*](https://people.cs.umass.edu/~barto/IMCleVer-chapter-totypeset2.pdf) (PDF). Berlin; Heidelberg: Springer. pp. 17–47.
47. [↑](./Reinforcement_learning#cite_ref-47) Dabérius, Kevin; Granat, Elvin; Karlsson, Patrik (2020). "Deep Execution - Value and Policy Based Reinforcement Learning for Trading and Beating Market Benchmarks". *The Journal of Machine Learning in Finance*. **1**. [SSRN](./SSRN_(identifier)) [3374766](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3374766).
48. [↑](./Reinforcement_learning#cite_ref-48) George Karimpanal, Thommen; Bouffanais, Roland (2019). "Self-organizing maps for storage and transfer of knowledge in reinforcement learning". *Adaptive Behavior*. **27** (2): 111–126. [arXiv](./ArXiv_(identifier)):[1811.08318](https://arxiv.org/abs/1811.08318). [doi](./Doi_(identifier)):[10.1177/1059712318818568](https://doi.org/10.1177%2F1059712318818568). [ISSN](./ISSN_(identifier)) [1059-7123](https://search.worldcat.org/issn/1059-7123). [S2CID](./S2CID_(identifier)) [53774629](https://api.semanticscholar.org/CorpusID:53774629).
49. [↑](./Reinforcement_learning#cite_ref-49) cf. [Sutton & Barto 2018](./Reinforcement_learning#CITEREFSuttonBarto2018), Section 5.4, p. 100
50. [↑](./Reinforcement_learning#cite_ref-Mnih_50-0) Mnih, Volodymyr; Badia, Adrià; Mirza, Mehdi; Graves, Alex; Lillicrap, Timothy; Harley, Tim; Silver, David; Kavukcuoglu, Koray (16 June 2016). ["Asynchronous Methods for Deep Reinforcement Learning"](https://proceedings.mlr.press/v48/mniha16.html). *Proceedings of Machine Learning Research (PMLR)*. **48**. PMLR: 1928–1937. Retrieved 15 June 2026.
51. [↑](./Reinforcement_learning#cite_ref-51) J Duan; Y Guan; S Li (2021). "Distributional Soft Actor-Critic: Off-policy reinforcement learning for addressing value estimation errors". *IEEE Transactions on Neural Networks and Learning Systems*. **33** (11): 6584–6598. [arXiv](./ArXiv_(identifier)):[2001.02811](https://arxiv.org/abs/2001.02811). [doi](./Doi_(identifier)):[10.1109/TNNLS.2021.3082568](https://doi.org/10.1109%2FTNNLS.2021.3082568). [PMID](./PMID_(identifier)) [34101599](https://pubmed.ncbi.nlm.nih.gov/34101599). [S2CID](./S2CID_(identifier)) [211259373](https://api.semanticscholar.org/CorpusID:211259373).
52. [↑](./Reinforcement_learning#cite_ref-52) Y Ren; J Duan; S Li (2020). "Improving Generalization of Reinforcement Learning with Minimax Distributional Soft Actor-Critic". *2020 IEEE 23rd International Conference on Intelligent Transportation Systems (ITSC)*. pp. 1–6. [arXiv](./ArXiv_(identifier)):[2002.05502](https://arxiv.org/abs/2002.05502). [doi](./Doi_(identifier)):[10.1109/ITSC45102.2020.9294300](https://doi.org/10.1109%2FITSC45102.2020.9294300). [ISBN](./ISBN_(identifier)) [978-1-7281-4149-7](./Special:BookSources/978-1-7281-4149-7). [S2CID](./S2CID_(identifier)) [211096594](https://api.semanticscholar.org/CorpusID:211096594).
53. [↑](./Reinforcement_learning#cite_ref-53) Duan, J; Wang, W; Xiao, L (2025). "Distributional Soft Actor-Critic with Three Refinements". *IEEE Transactions on Pattern Analysis and Machine Intelligence*. **PP** (5): 3935–3946. [arXiv](./ArXiv_(identifier)):[2310.05858](https://arxiv.org/abs/2310.05858). [Bibcode](./Bibcode_(identifier)):[2025ITPAM..47.3935D](https://ui.adsabs.harvard.edu/abs/2025ITPAM..47.3935D). [doi](./Doi_(identifier)):[10.1109/TPAMI.2025.3537087](https://doi.org/10.1109%2FTPAMI.2025.3537087). [PMID](./PMID_(identifier)) [40031258](https://pubmed.ncbi.nlm.nih.gov/40031258).
54. [↑](./Reinforcement_learning#cite_ref-54) Soucek, Branko (6 May 1992). *Dynamic, Genetic and Chaotic Programming: The Sixth-Generation Computer Technology Series*. John Wiley & Sons, Inc. p. 38. [ISBN](./ISBN_(identifier)) [0-471-55717-X](./Special:BookSources/0-471-55717-X).
55. [↑](./Reinforcement_learning#cite_ref-intro_deep_RL_55-0) Francois-Lavet, Vincent; et al. (2018). "An Introduction to Deep Reinforcement Learning". *Foundations and Trends in Machine Learning*. **11** (3–4): 219–354. [arXiv](./ArXiv_(identifier)):[1811.12560](https://arxiv.org/abs/1811.12560). [Bibcode](./Bibcode_(identifier)):[2018arXiv181112560F](https://ui.adsabs.harvard.edu/abs/2018arXiv181112560F). [doi](./Doi_(identifier)):[10.1561/2200000071](https://doi.org/10.1561%2F2200000071). [S2CID](./S2CID_(identifier)) [54434537](https://api.semanticscholar.org/CorpusID:54434537).
56. [↑](./Reinforcement_learning#cite_ref-DQN2_56-0) Mnih, Volodymyr; et al. (2015). "Human-level control through deep reinforcement learning". *Nature*. **518** (7540): 529–533. [Bibcode](./Bibcode_(identifier)):[2015Natur.518..529M](https://ui.adsabs.harvard.edu/abs/2015Natur.518..529M). [doi](./Doi_(identifier)):[10.1038/nature14236](https://doi.org/10.1038%2Fnature14236). [PMID](./PMID_(identifier)) [25719670](https://pubmed.ncbi.nlm.nih.gov/25719670). [S2CID](./S2CID_(identifier)) [205242740](https://api.semanticscholar.org/CorpusID:205242740).
57. [↑](./Reinforcement_learning#cite_ref-57) Goodfellow, Ian; Shlens, Jonathan; Szegedy, Christian (2015). "Explaining and Harnessing Adversarial Examples". *International Conference on Learning Representations*. [arXiv](./ArXiv_(identifier)):[1412.6572](https://arxiv.org/abs/1412.6572).
58. [↑](./Reinforcement_learning#cite_ref-58) Behzadan, Vahid; Munir, Arslan (2017). "Vulnerability of Deep Reinforcement Learning to Policy Induction Attacks". *Machine Learning and Data Mining in Pattern Recognition*. Lecture Notes in Computer Science. Vol. 10358. pp. 262–275. [arXiv](./ArXiv_(identifier)):[1701.04143](https://arxiv.org/abs/1701.04143). [doi](./Doi_(identifier)):[10.1007/978-3-319-62416-7_19](https://doi.org/10.1007%2F978-3-319-62416-7_19). [ISBN](./ISBN_(identifier)) [978-3-319-62415-0](./Special:BookSources/978-3-319-62415-0). [S2CID](./S2CID_(identifier)) [1562290](https://api.semanticscholar.org/CorpusID:1562290).
59. [↑](./Reinforcement_learning#cite_ref-59) Huang, Sandy; Papernot, Nicolas; Goodfellow, Ian; Duan, Yan; Abbeel, Pieter (2017-02-07). *Adversarial Attacks on Neural Network Policies*. [OCLC](./OCLC_(identifier)) [1106256905](https://search.worldcat.org/oclc/1106256905).
60. [↑](./Reinforcement_learning#cite_ref-60) Korkmaz, Ezgi (2022). ["Deep Reinforcement Learning Policies Learn Shared Adversarial Features Across MDPs"](https://doi.org/10.1609%2Faaai.v36i7.20684). *Thirty-Sixth AAAI Conference on Artificial Intelligence (AAAI-22)*. **36** (7): 7229–7238. [arXiv](./ArXiv_(identifier)):[2112.09025](https://arxiv.org/abs/2112.09025). [doi](./Doi_(identifier)):[10.1609/aaai.v36i7.20684](https://doi.org/10.1609%2Faaai.v36i7.20684). [S2CID](./S2CID_(identifier)) [245219157](https://api.semanticscholar.org/CorpusID:245219157).
61. [↑](./Reinforcement_learning#cite_ref-61) Berenji, H.R. (1994). "Fuzzy Q-learning: A new approach for fuzzy dynamic programming". *Proceedings of 1994 IEEE 3rd International Fuzzy Systems Conference*. Orlando, FL, USA: IEEE. pp. 486–491. [doi](./Doi_(identifier)):[10.1109/FUZZY.1994.343737](https://doi.org/10.1109%2FFUZZY.1994.343737). [ISBN](./ISBN_(identifier)) [0-7803-1896-X](./Special:BookSources/0-7803-1896-X). [S2CID](./S2CID_(identifier)) [56694947](https://api.semanticscholar.org/CorpusID:56694947).
62. [↑](./Reinforcement_learning#cite_ref-62) Vincze, David (2017). ["Fuzzy rule interpolation and reinforcement learning"](http://users.iit.uni-miskolc.hu/~vinczed/research/vinczed_sami2017_author_draft.pdf) (PDF). *2017 IEEE 15th International Symposium on Applied Machine Intelligence and Informatics (SAMI)*. IEEE. pp. 173–178. [doi](./Doi_(identifier)):[10.1109/SAMI.2017.7880298](https://doi.org/10.1109%2FSAMI.2017.7880298). [ISBN](./ISBN_(identifier)) [978-1-5090-5655-2](./Special:BookSources/978-1-5090-5655-2). [S2CID](./S2CID_(identifier)) [17590120](https://api.semanticscholar.org/CorpusID:17590120).
63. [↑](./Reinforcement_learning#cite_ref-63) Ng, A. Y.; Russell, S. J. (2000). ["Algorithms for Inverse Reinforcement Learning"](https://ai.stanford.edu/~ang/papers/icml00-irl.pdf) (PDF). *Proceeding ICML '00 Proceedings of the Seventeenth International Conference on Machine Learning*. Morgan Kaufmann Publishers. pp. 663–670. [ISBN](./ISBN_(identifier)) [1-55860-707-2](./Special:BookSources/1-55860-707-2).
64. [↑](./Reinforcement_learning#cite_ref-64) Ziebart, Brian D.; Maas, Andrew; Bagnell, J. Andrew; Dey, Anind K. (2008-07-13). ["Maximum entropy inverse reinforcement learning"](https://dl.acm.org/doi/10.5555/1620270.1620297). *Proceedings of the 23rd National Conference on Artificial Intelligence - Volume 3*. AAAI'08. Chicago, Illinois: AAAI Press: 1433–1438. [ISBN](./ISBN_(identifier)) [978-1-57735-368-3](./Special:BookSources/978-1-57735-368-3). [S2CID](./S2CID_(identifier)) [336219](https://api.semanticscholar.org/CorpusID:336219).
65. [↑](./Reinforcement_learning#cite_ref-65) Pitombeira-Neto, Anselmo R.; Santos, Helano P.; Coelho da Silva, Ticiana L.; de Macedo, José Antonio F. (March 2024). "Trajectory modeling via random utility inverse reinforcement learning". *Information Sciences*. **660** 120128. [arXiv](./ArXiv_(identifier)):[2105.12092](https://arxiv.org/abs/2105.12092). [doi](./Doi_(identifier)):[10.1016/j.ins.2024.120128](https://doi.org/10.1016%2Fj.ins.2024.120128). [ISSN](./ISSN_(identifier)) [0020-0255](https://search.worldcat.org/issn/0020-0255). [S2CID](./S2CID_(identifier)) [235187141](https://api.semanticscholar.org/CorpusID:235187141).
66. [↑](./Reinforcement_learning#cite_ref-66) Hayes C, Radulescu R, Bargiacchi E, et al. (2022). ["A practical guide to multi-objective reinforcement learning and planning"](https://doi.org/10.1007%2Fs10458-022-09552-y). *Autonomous Agents and Multi-Agent Systems*. **36** 26. [arXiv](./ArXiv_(identifier)):[2103.09568](https://arxiv.org/abs/2103.09568). [doi](./Doi_(identifier)):[10.1007/s10458-022-09552-y](https://doi.org/10.1007%2Fs10458-022-09552-y). [S2CID](./S2CID_(identifier)) [254235920](https://api.semanticscholar.org/CorpusID:254235920).,
67. [↑](./Reinforcement_learning#cite_ref-67) Tzeng, Gwo-Hshiung; Huang, Jih-Jeng (2011). *Multiple Attribute Decision Making: Methods and Applications* (1st ed.). CRC Press. [ISBN](./ISBN_(identifier)) [978-1-4398-6157-8](./Special:BookSources/978-1-4398-6157-8).
68. [↑](./Reinforcement_learning#cite_ref-68) Gu, Shangding; Yang, Long; Du, Yali; Chen, Guang; Walter, Florian; Wang, Jun; Knoll, Alois (10 September 2024). ["A review of safe reinforcement learning: Methods, theories and applications"](https://kclpure.kcl.ac.uk/portal/files/300373453/A_Review_of_Safe_Reinforcement_Learning_Methods_Theories_and_Applications_2_.pdf) (PDF). *IEEE Transactions on Pattern Analysis and Machine Intelligence*. **46** (12): 11216–11235. [Bibcode](./Bibcode_(identifier)):[2024ITPAM..4611216G](https://ui.adsabs.harvard.edu/abs/2024ITPAM..4611216G). [doi](./Doi_(identifier)):[10.1109/TPAMI.2024.3457538](https://doi.org/10.1109%2FTPAMI.2024.3457538). [PMID](./PMID_(identifier)) [39255180](https://pubmed.ncbi.nlm.nih.gov/39255180).
69. [↑](./Reinforcement_learning#cite_ref-69) García, Javier; Fernández, Fernando (1 January 2015). ["A comprehensive survey on safe reinforcement learning"](https://jmlr.org/papers/volume16/garcia15a/garcia15a.pdf) (PDF). *The Journal of Machine Learning Research*. **16** (1): 1437–1480.
70. [↑](./Reinforcement_learning#cite_ref-70) Dabney, Will; Ostrovski, Georg; Silver, David; Munos, Remi (2018-07-03). ["Implicit Quantile Networks for Distributional Reinforcement Learning"](https://proceedings.mlr.press/v80/dabney18a.html). *Proceedings of the 35th International Conference on Machine Learning*. PMLR: 1096–1105. [arXiv](./ArXiv_(identifier)):[1806.06923](https://arxiv.org/abs/1806.06923).
71. [↑](./Reinforcement_learning#cite_ref-71) Chow, Yinlam; Tamar, Aviv; Mannor, Shie; Pavone, Marco (2015). ["Risk-Sensitive and Robust Decision-Making: a CVaR Optimization Approach"](https://proceedings.neurips.cc/paper/2015/hash/64223ccf70bbb65a3a4aceac37e21016-Abstract.html). *Advances in Neural Information Processing Systems*. **28**. Curran Associates, Inc. [arXiv](./ArXiv_(identifier)):[1506.02188](https://arxiv.org/abs/1506.02188).
72. [↑](./Reinforcement_learning#cite_ref-72) ["Train Hard, Fight Easy: Robust Meta Reinforcement Learning"](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=LnwyFkkAAAAJ&citation_for_view=LnwyFkkAAAAJ:eQOLeE2rZwMC). *scholar.google.com*. Retrieved 2024-06-21.
73. [↑](./Reinforcement_learning#cite_ref-73) Tamar, Aviv; Glassner, Yonatan; Mannor, Shie (2015-02-21). ["Optimizing the CVaR via Sampling"](https://ojs.aaai.org/index.php/AAAI/article/view/9561). *Proceedings of the AAAI Conference on Artificial Intelligence*. **29** (1). [arXiv](./ArXiv_(identifier)):[1404.3862](https://arxiv.org/abs/1404.3862). [doi](./Doi_(identifier)):[10.1609/aaai.v29i1.9561](https://doi.org/10.1609%2Faaai.v29i1.9561). [ISSN](./ISSN_(identifier)) [2374-3468](https://search.worldcat.org/issn/2374-3468).
74. [↑](./Reinforcement_learning#cite_ref-74) Greenberg, Ido; Chow, Yinlam; Ghavamzadeh, Mohammad; Mannor, Shie (2022-12-06). ["Efficient Risk-Averse Reinforcement Learning"](https://proceedings.neurips.cc/paper_files/paper/2022/hash/d2511dfb731fa336739782ba825cd98c-Abstract-Conference.html). *Advances in Neural Information Processing Systems*. **35**: 32639–32652. [arXiv](./ArXiv_(identifier)):[2205.05138](https://arxiv.org/abs/2205.05138).
75. [↑](./Reinforcement_learning#cite_ref-75) Bozinovski, S. (1982). "A self-learning system using secondary reinforcement". In Trappl, Robert (ed.). Cybernetics and Systems Research: Proceedings of the Sixth European Meeting on Cybernetics and Systems Research. North-Holland. pp. 397–402. ISBN 978-0-444-86488-8
76. [↑](./Reinforcement_learning#cite_ref-76) Bozinovski S. (1995) "Neuro genetic agents and structural theory of self-reinforcement learning systems". CMPSCI Technical Report 95-107, University of Massachusetts at Amherst [](https://web.cs.umass.edu/publication/docs/1995/UM-CS-1995-107.pdf)
77. [↑](./Reinforcement_learning#cite_ref-77) Bozinovski, S. (2014) "Modeling mechanisms of cognition-emotion interaction in artificial neural networks, since 1981." Procedia Computer Science p. 255–263
78. [↑](./Reinforcement_learning#cite_ref-78) Engstrom, Logan; Ilyas, Andrew; Santurkar, Shibani; Tsipras, Dimitris; Janoos, Firdaus; Rudolph, Larry; Madry, Aleksander (2019-09-25). ["Implementation Matters in Deep RL: A Case Study on PPO and TRPO"](https://openreview.net/forum?id=r1etN1rtPB). *ICLR*.
79. [↑](./Reinforcement_learning#cite_ref-79) Colas, Cédric (2019-03-06). ["Distributional Soft Actor-Critic with Three Refinements"](https://openreview.net/forum?id=ryx0N3IaIV). *IEEE Transactions on Pattern Analysis and Machine Intelligence*. **47** (5): 3935–3946. [arXiv](./ArXiv_(identifier)):[1904.06979](https://arxiv.org/abs/1904.06979). [Bibcode](./Bibcode_(identifier)):[2025ITPAM..47.3935D](https://ui.adsabs.harvard.edu/abs/2025ITPAM..47.3935D). [doi](./Doi_(identifier)):[10.1109/TPAMI.2025.3537087](https://doi.org/10.1109%2FTPAMI.2025.3537087). [PMID](./PMID_(identifier)) [40031258](https://pubmed.ncbi.nlm.nih.gov/40031258).
80. [↑](./Reinforcement_learning#cite_ref-80) Greenberg, Ido; Mannor, Shie (2021-07-01). ["Reward Machines: Exploiting Reward Function Structure in Reinforcement Learning"](https://proceedings.mlr.press/v139/greenberg21a.html). *Journal of Artificial Intelligence Research*. **73**. PMLR: 3842–3853. [arXiv](./ArXiv_(identifier)):[2010.11660](https://arxiv.org/abs/2010.11660). [doi](./Doi_(identifier)):[10.1613/jair.1.12440](https://doi.org/10.1613%2Fjair.1.12440).
81. [↑](./Reinforcement_learning#cite_ref-81) Uc-Cetina, Víctor; Navarro-Guerrero, Nicolás; Martin-Gonzalez, Anabel; Weber, Cornelius; Wermter, Stefan (2022). "Survey on reinforcement learning for language processing". *Artificial Intelligence Review*. **56**: 1543–1575. [doi](./Doi_(identifier)):[10.1007/s10462-022-10205-5](https://doi.org/10.1007%2Fs10462-022-10205-5).
82. [↑](./Reinforcement_learning#cite_ref-82) ["An API for reinforcement learning"](https://gymnasium.farama.org/). January 22, 2025. Retrieved January 22, 2025.
83. [↑](./Reinforcement_learning#cite_ref-83) DeepSeek-AI; et al. (January 22, 2025). ["DeepSeek-R1 incentivizes reasoning in LLMS through reinforcement learning"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC12443585). *Nature*. **645** (8081): 633–638. [arXiv](./ArXiv_(identifier)):[2501.12948](https://arxiv.org/abs/2501.12948). [Bibcode](./Bibcode_(identifier)):[2025Natur.645..633G](https://ui.adsabs.harvard.edu/abs/2025Natur.645..633G). [doi](./Doi_(identifier)):[10.1038/s41586-025-09422-z](https://doi.org/10.1038%2Fs41586-025-09422-z). [PMC](./PMC_(identifier)) [12443585](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC12443585). [PMID](./PMID_(identifier)) [40962978](https://pubmed.ncbi.nlm.nih.gov/40962978).

 

## Further reading

 
- Annaswamy, Anuradha M. (3 May 2023). ["Adaptive Control and Intersections with Reinforcement Learning"](https://doi.org/10.1146%2Fannurev-control-062922-090153). *Annual Review of Control, Robotics, and Autonomous Systems*. **6** (1): 65–93. [doi](./Doi_(identifier)):[10.1146/annurev-control-062922-090153](https://doi.org/10.1146%2Fannurev-control-062922-090153). [ISSN](./ISSN_(identifier)) [2573-5144](https://search.worldcat.org/issn/2573-5144). [S2CID](./S2CID_(identifier)) [255702873](https://api.semanticscholar.org/CorpusID:255702873).
- [Auer, Peter](./Peter_Auer); Jaksch, Thomas; Ortner, Ronald (2010). ["Near-optimal regret bounds for reinforcement learning"](http://jmlr.csail.mit.edu/papers/v11/jaksch10a.html). *Journal of Machine Learning Research*. **11**: 1563–1600.
- Bertsekas, Dimitri P. (2023) [2019]. [*Reinforcement Learning and Optimal Control*](http://www.mit.edu/~dimitrib/RLbook.html) (1st ed.). Athena Scientific. [ISBN](./ISBN_(identifier)) [978-1-886-52939-7](./Special:BookSources/978-1-886-52939-7).
- Busoniu, Lucian; Babuska, Robert; [De Schutter, Bart](./Bart_De_Schutter); Ernst, Damien (2010). [*Reinforcement Learning and Dynamic Programming using Function Approximators*](http://www.dcsc.tudelft.nl/rlbook/). Taylor & Francis CRC Press. [ISBN](./ISBN_(identifier)) [978-1-4398-2108-4](./Special:BookSources/978-1-4398-2108-4).
- François-Lavet, Vincent; Henderson, Peter; Islam, Riashat; Bellemare, Marc G.; Pineau, Joelle (2018). "An Introduction to Deep Reinforcement Learning". *Foundations and Trends in Machine Learning*. **11** (3–4): 219–354. [arXiv](./ArXiv_(identifier)):[1811.12560](https://arxiv.org/abs/1811.12560). [Bibcode](./Bibcode_(identifier)):[2018arXiv181112560F](https://ui.adsabs.harvard.edu/abs/2018arXiv181112560F). [doi](./Doi_(identifier)):[10.1561/2200000071](https://doi.org/10.1561%2F2200000071). [S2CID](./S2CID_(identifier)) [54434537](https://api.semanticscholar.org/CorpusID:54434537).
- Li, Shengbo Eben (2023). [*Reinforcement Learning for Sequential Decision and Optimal Control*](https://link.springer.com/book/10.1007/978-981-19-7784-8) (1st ed.). Springer Verlag, Singapore. [doi](./Doi_(identifier)):[10.1007/978-981-19-7784-8](https://doi.org/10.1007%2F978-981-19-7784-8). [ISBN](./ISBN_(identifier)) [978-9-811-97783-1](./Special:BookSources/978-9-811-97783-1).
- Powell, Warren (2011). [*Approximate dynamic programming: solving the curses of dimensionality*](https://web.archive.org/web/20160731230325/http://castlelab.princeton.edu/adp.htm). Wiley-Interscience. Archived from [the original](http://www.castlelab.princeton.edu/adp.htm) on 2016-07-31. Retrieved 2010-09-08.
- [Sutton, Richard S.](./Richard_S._Sutton) (1988). ["Learning to predict by the method of temporal differences"](https://doi.org/10.1007%2FBF00115009). *Machine Learning*. **3** (1): 9–44. [Bibcode](./Bibcode_(identifier)):[1988MLear...3....9S](https://ui.adsabs.harvard.edu/abs/1988MLear...3....9S). [doi](./Doi_(identifier)):[10.1007/BF00115009](https://doi.org/10.1007%2FBF00115009).
- [Sutton, Richard S.](./Richard_S._Sutton); [Barto, Andrew G.](./Andrew_Barto) (2018) [1998]. [*Reinforcement Learning: An Introduction*](http://incompleteideas.net/sutton/book/the-book.html) (2nd ed.). MIT Press. [ISBN](./ISBN_(identifier)) [978-0-262-03924-6](./Special:BookSources/978-0-262-03924-6).
- Szita, Istvan; Szepesvari, Csaba (2010). ["Model-based Reinforcement Learning with Nearly Tight Exploration Complexity Bounds"](https://web.archive.org/web/20100714095438/http://www.icml2010.org/papers/546.pdf) (PDF). *ICML 2010*. Omnipress. pp. 1031–1038. Archived from [the original](http://www.icml2010.org/papers/546.pdf) (PDF) on 2010-07-14.

 

## External links

 
- [Dissecting Reinforcement Learning](https://mpatacchiola.github.io/blog/2016/12/09/dissecting-reinforcement-learning.html) Series of blog post on reinforcement learning with Python code
- [A (Long) Peek into Reinforcement Learning](https://lilianweng.github.io/posts/2018-02-19-rl-overview/)
- [QSMM – reinforcement learning through adaptive probabilistic assembler programs](http://qsmm.org)

 
| vteArtificial intelligence(AI) |
| --- |
| HistorytimelineGlossaryCompaniesProjectsList of open-source AI software |
| Concepts | Automated reasoningParameterHyperparameterLoss functionsRegressionBias–variance tradeoffDouble descentOverfittingClusteringGradient descentSGDQuasi-Newton methodConjugate gradient methodBackpropagationAttentionConvolutionNormalizationBatchnormActivationSoftmaxSigmoidRectifierGatingWeight initializationRegularizationDatasetsAugmentationPrompt engineeringReinforcement learningQ-learningSARSAImitationPolicy gradientDiffusionLatent diffusion modelAutoregressionAdversaryRAGUncanny valleyRLHFSelf-supervised learningReflectionRecursive self-improvementHallucinationWord embeddingVibe codingSymbolic AINeuro-symbolic AI |
| Applications | Automated theorem provingMachine learningIn-context learningArtificial neural networkDeep learningLanguage modelLargeNMTReasoningModel Context ProtocolIntelligent agentAI agentArtificial human companionHumanity's Last ExamLethal autonomous weapons (LAWs)Generative AIWeak AIHypotheticalArtificial general intelligence (AGI)Artificial superintelligence (ASI)Agent2Agent protocol |
| Implementations | Audio–visualAlexNetWaveNetHuman image synthesisHWROCRComputer visionSpeech synthesis15.aiElevenLabsSpeech recognitionWhisperFacial recognitionAlphaFoldText-to-image modelsAuroraDALL-EFireflyFluxGPT ImageIdeogramImagenMidjourneyRecraftStable DiffusionText-to-video modelsDream MachineRunway GenHailuo AIKlingSoraSeedanceVeoMusic generationRiffusionSunoUdioWorld modelsGenieOasisTextList of large language modelsProject DebaterIBM WatsonIBM WatsonxDecisionalAlphaGoAlphaZeroOpenAI FiveSelf-driving carMuZeroAction selectionAutoGPTRobot controlReasoning systemsDeductive classifiersExpert systemsInference enginesKnowledge-based systemsLogic programsProcedural reasoning systemsSemantic reasonersRule-based systemsCognitive architecturesACT-RSoarCLARIONLIDAOpenCogKnowledge basesConceptNetWikidataDBpediaYAGO | Audio–visual | AlexNetWaveNetHuman image synthesisHWROCRComputer visionSpeech synthesis15.aiElevenLabsSpeech recognitionWhisperFacial recognitionAlphaFoldText-to-image modelsAuroraDALL-EFireflyFluxGPT ImageIdeogramImagenMidjourneyRecraftStable DiffusionText-to-video modelsDream MachineRunway GenHailuo AIKlingSoraSeedanceVeoMusic generationRiffusionSunoUdioWorld modelsGenieOasis | Text | List of large language modelsProject DebaterIBM WatsonIBM Watsonx | Decisional | AlphaGoAlphaZeroOpenAI FiveSelf-driving carMuZeroAction selectionAutoGPTRobot control | Reasoning systems | Deductive classifiersExpert systemsInference enginesKnowledge-based systemsLogic programsProcedural reasoning systemsSemantic reasonersRule-based systems | Cognitive architectures | ACT-RSoarCLARIONLIDAOpenCog | Knowledge bases | ConceptNetWikidataDBpediaYAGO |
| Audio–visual | AlexNetWaveNetHuman image synthesisHWROCRComputer visionSpeech synthesis15.aiElevenLabsSpeech recognitionWhisperFacial recognitionAlphaFoldText-to-image modelsAuroraDALL-EFireflyFluxGPT ImageIdeogramImagenMidjourneyRecraftStable DiffusionText-to-video modelsDream MachineRunway GenHailuo AIKlingSoraSeedanceVeoMusic generationRiffusionSunoUdioWorld modelsGenieOasis |
| Text | List of large language modelsProject DebaterIBM WatsonIBM Watsonx |
| Decisional | AlphaGoAlphaZeroOpenAI FiveSelf-driving carMuZeroAction selectionAutoGPTRobot control |
| Reasoning systems | Deductive classifiersExpert systemsInference enginesKnowledge-based systemsLogic programsProcedural reasoning systemsSemantic reasonersRule-based systems |
| Cognitive architectures | ACT-RSoarCLARIONLIDAOpenCog |
| Knowledge bases | ConceptNetWikidataDBpediaYAGO |
| People | Alan TuringWarren Sturgis McCullochWalter PittsJohn von NeumannChristopher D. ManningClaude ShannonShun'ichi AmariKunihiko FukushimaTakeo KanadeMarvin MinskyJohn McCarthyNathaniel RochesterAllen NewellCliff ShawHerbert A. SimonOliver SelfridgeFrank RosenblattBernard WidrowJoseph WeizenbaumSeymour PapertSeppo LinnainmaaPaul WerbosGeoffrey HintonJohn HopfieldJürgen SchmidhuberYann LeCunYoshua BengioLotfi A. ZadehStephen GrossbergAlex GravesJames GoodnightAndrew NgFei-Fei LiAlex KrizhevskyIlya SutskeverOriol VinyalsQuoc V. LeIan GoodfellowDemis HassabisDavid SilverAndrej KarpathyAshish VaswaniNoam ShazeerAidan GomezJohn SchulmanMustafa SuleymanJan LeikeDaniel KokotajloFrançois Chollet |
| Neural network architectures | Neural Turing machineDifferentiable neural computerTransformerVision transformer (ViT)Recurrent neural network (RNN)Long short-term memory (LSTM)Gated recurrent unit (GRU)Echo state networkMultilayer perceptron (MLP)Convolutional neural network (CNN)Residual neural network (RNN)Highway networkMambaAutoencoderVariational autoencoder (VAE)Generative adversarial network (GAN)Graph neural network (GNN) |
| Political | AI Cold WarAI safety(Alignment)AI takeoverElectionsEthics of AIEUAI ActNationalismPrecautionary principleRegulation of AIUSVirtual politicianPropaganda |
| Social and economic | AI boomAI bubbleAI data centerAI effectAI literacyAI slopAI veganismAI winterAnthropomorphismArms raceCompetitionEnvironmental impactExplainable AIGenerative engine optimizationIn architectureIn educationIn fictionIn healthcareChatbot psychosisIn marketingIn video gamesIn visual artMilitary applicationsAI warfareWorkplace impact |
| Category |

 
| vteComputer science |
| --- |
| This template follows roughly the 2012ACM Computing Classification System |
| Hardware | Printed circuit boardPeripheralIntegrated circuitVery-large-scale integrationSystem on a chip(SoC)Energy consumption(green computing)Electronic design automationHardware accelerationProcessorSize–Form |
| Systemsorganization | Computer architectureComputational complexityDependabilityEmbedded systemReal-time computingCyber-physical systemFault toleranceWireless sensor network |
| Networks | Network architectureNetwork protocolNetwork componentsNetwork schedulerNetwork performance evaluationNetwork service |
| Softwareorganization | InterpreterMiddlewareVirtual machineOperating systemSoftware quality |
| Softwarenotations,tools | Programming paradigmProgramming languageCompilerDomain-specific languageModeling languageSoftware frameworkIntegrated development environmentSoftware configuration managementSoftware librarySoftware repository |
| Softwaredevelopment | Control flowSoftware development processRequirements analysisSoftware designSoftware constructionSoftware deploymentSoftware engineeringSoftware maintenanceProgramming teamOpen sourcemodel |
| Theory ofcomputing | Model of computationStochasticFormal languageAutomata theoryComputability theoryComputational complexity theoryLogicSemantics |
| Algorithms | Algorithm designAnalysis of algorithmsAlgorithmic efficiencyRandomized algorithmComputational geometry |
| Mathematicsofcomputing | Discrete mathematicsProbabilityStatisticsMathematical softwareInformation theoryMathematical analysisNumerical analysisTheoretical computer scienceComputational problem |
| Informationsystems | DatabasemanagementInformation storageEnterprise informationSocial informationGeographic informationDecision supportProcess controlMultimedia informationData miningDigital libraryComputing platformDigital marketingWorld Wide WebInformation retrieval |
| Security | CryptographyFormal methodsSecurity hackerSecurityservicesIntrusion detection systemHardware securityNetwork securityInformation securityApplication security |
| Human-centeredcomputing | AccessibilityExtended realityaugmentedvirtualHuman–computer interactionInteraction designMobile computingSocial computingUbiquitous computingVisualization |
| Concurrency | Concurrent computingParallel computingDistributed computingMultithreadingMultiprocessing |
| Artificialintelligence | Computational intelligenceNatural language processingKnowledge representation and reasoningComputer visionAutomated planning and schedulingSearch methodologyControl methodPhilosophy ofDistributedMachinelearningSupervisedUnsupervisedReinforcementMulti-taskCross-validation | Computational intelligenceNatural language processingKnowledge representation and reasoningComputer visionAutomated planning and schedulingSearch methodologyControl methodPhilosophy ofDistributed | Machinelearning | SupervisedUnsupervisedReinforcementMulti-taskCross-validation |
| Computational intelligenceNatural language processingKnowledge representation and reasoningComputer visionAutomated planning and schedulingSearch methodologyControl methodPhilosophy ofDistributed |
| Machinelearning | SupervisedUnsupervisedReinforcementMulti-taskCross-validation |
| Graphics | AnimationRenderingPhotograph manipulationGraphics processing unitImage compressionSolid modeling |
| Appliedcomputing | Quantum computingE-commerceEnterprise softwareComputational mathematicsComputational physicsComputational chemistryComputational biologyComputational social scienceComputational engineeringDifferentiable computingComputational healthcareDigital artElectronic publishingCyberwarfareElectronic votingVideo gamesWord processingOperations researchEducational technologyDocument management |
| OutlineGlossariesCategory |

| vteRobotics |
| --- |
| Main articles | OutlineGlossaryIndexHistoryGeographyHall of FameEthicsLawsCompetitionsAI competitions |  |
| Types | AerobotAnthropomorphicHumanoidAndroidCyborgGynoidClaytronicsCompanionAutomatonAnimatronicAudio-AnimatronicsIndustrialArticulatedarmDeliveryDomesticEducationalEntertainmentJugglingMilitaryMedicalServiceDisabilityAgriculturalFood serviceRetailBEAM roboticsSoft robotics |
| Classifications | BioroboticsCloud roboticsContinuum robotUnmanned vehicleaerialgroundMobile robotMicroboticsNanoroboticsNecroboticsRobotic spacecraftSpace probeSwarmTeleroboticsUnderwaterremotely-operatedRobotic fish |
| Locomotion | TracksWalkingHexapodClimbingElectric unicycleRobotic fins |
| Navigationandmapping | Motion planningSimultaneous localization and mappingVisual odometryVision-guided robot systems |
| Algorithms | Reinforcement learningVision-language-action modelArtificial neural network |
| Research | EvolutionaryKitsSimulatorSuiteOpen-sourceSoftwareAdaptableDevelopmentalHuman–robot interactionParadigmsPerceptualSituatedUbiquitous |
| Companies | ABBAmazon RoboticsAnybotsBarrett TechnologyBoston DynamicsDaxbotDoosan RoboticsEnergid TechnologiesFarmWiseFANUCFigure AIFoster-MillerFourier (company)Harvest AutomationHD Hyundai RoboticsHoneybee RoboticsIntuitive SurgicalIRobotKUKARainbow RoboticsRobomowStarship TechnologiesStäubliSymboticUniversal RoboticsWolf RoboticsWaymoZooxYaskawaAgility RoboticsUnitree Robotics1X TechnologiesAgiBotDeep RoboticsEngine AIRoborockUBtech RoboticsNeura RoboticsFastbrick RoboticsUniversal RobotsWhite Box RoboticsTesla inc.WelltecKUKA |
| Related | Critique of workPowered exoskeletonWorkplace robotics safetyRobotic tech vestTechnological unemploymentTerrainabilityFictional robotsList of robotics softwareMoravec's paradoxArtificial general intelligence |
| CategoryOutline |