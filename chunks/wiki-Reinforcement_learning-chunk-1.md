---
source: sources/wiki-Reinforcement_learning.md
source_url: https://en.wikipedia.org/wiki/Reinforcement_learning
chunk: 1/6
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

 


