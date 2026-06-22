---
source: chunks/wiki-Deep_learning-chunk-5.md
source_url: https://en.wikipedia.org/wiki/Deep_learning
---

## Deep Learning: Neuroscience Connections, Commercial Applications, and Criticisms

This page covers the relationship between deep learning and biological brain development theories, major commercial applications of deep learning, and key criticisms including theoretical gaps, adversarial vulnerabilities, and data collection ethics.

## Key Concepts

- **Neocortical development parallels**: Deep learning architectures mirror theories of brain development from the early 1990s, where hierarchical layered filters process information sequentially — analogous to how the neocortex self-organizes under waves of trophic factors.
- **Self-organizing transducers**: Both biological neural networks and deep learning models produce hierarchical stacks of transducers tuned to their operating environment through layered maturation.
- **Biological plausibility debate**: Unsupervised methods (hierarchical generative models, deep belief networks) may be more biologically realistic than backpropagation; generative models relate to sampling-based processing in the cerebral cortex.
- **Representational similarity**: Deep learning representations resemble those measured in the primate visual system at both single-unit and population levels.
- **Black box problem**: Deep learning methods lack comprehensive theoretical foundations; most validation is empirical rather than theoretical. Gradient descent is well-understood, but algorithms like contrastive divergence lack convergence guarantees.
- **Adversarial attacks**: Neural networks are vulnerable to inputs subtly modified to cause misclassification — imperceptible perturbations to images, doctored stop signs, psychedelic spectacles fooling facial recognition.
- **Data poisoning**: Injecting false data into training sets to degrade model performance.
- **TAMER / Deep TAMER**: Framework for learning tasks via human evaluative feedback; Deep TAMER (2018) added deep learning for observational learning from video or in-person demonstration.

## Commands and Syntax

No specific commands or configuration syntax — this section is conceptual and historical.

## Relationships

- **Backpropagation**: Central training algorithm whose biological plausibility is debated; variants proposed for greater neural realism.
- **Generative models / Deep belief networks**: Unsupervised alternatives argued to be closer to biological processing.
- **Adversarial machine learning**: Encompasses adversarial attacks and data poisoning as security threats to deep learning systems.
- **Reinforcement learning**: TAMER/Deep TAMER connects deep learning to human-in-the-loop RL training paradigms.
- **Explainable AI (XAI)**: Directly relates to the theoretical criticism that deep learning operates as a black box.
- **Artificial general intelligence (AGI)**: Goertzel argues adversarial vulnerabilities reflect representational limitations that hinder AGI integration.
- **Grammar induction / commonsense reasoning**: Proposed as potential solutions to adversarial robustness through structured internal representations.

## Exam-Relevant Points

- Deep learning's layered hierarchy is analogous to neocortical self-organization driven by trophic factors — a connection established in computational models from the early 1990s.
- Unsupervised deep learning (generative models, deep belief networks) is considered more biologically plausible than supervised backpropagation.
- **Adversarial examples** are a critical vulnerability: small, human-imperceptible perturbations can cause confident misclassification.
- Key commercial milestones: DeepMind's AlphaGo (2015) beating professional Go players; Google Translate using neural networks for 100+ languages; Facebook's automatic photo tagging.
- Deep TAMER (2018, ARL + UT Austin) combined deep learning with human evaluative reinforcement for robot task learning.
- **Data poisoning** is an attack where adversaries corrupt training data to prevent model mastery.
- Five types of "machinic capture" for training data (Mühlhoff): gamification, trapping/tracking (CAPTCHAs), social motivation exploitation, information mining, and clickwork.
- The adversarial arms race parallel: ANNs can be trained to detect adversarial attacks, but attackers (e.g., using genetic algorithms) can co-evolve malware to bypass ANN-based defenses.
- Contrastive divergence lacks the theoretical guarantees (convergence, approximation quality) that gradient descent has.
