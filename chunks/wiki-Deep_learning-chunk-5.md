---
source: sources/wiki-Deep_learning.md
source_url: https://en.wikipedia.org/wiki/Deep_learning
chunk: 5/7
---

## Relation to human cognitive and brain development

 

Deep learning is closely related to a class of theories of [brain development](./Brain_development) (specifically, neocortical development) proposed by [cognitive neuroscientists](./Cognitive_neuroscientist) in the early 1990s.[[252]](./Deep_learning#cite_note-UTGOFF-252)[[253]](./Deep_learning#cite_note-ELMAN-253)[[254]](./Deep_learning#cite_note-SHRAGER-254)[[255]](./Deep_learning#cite_note-QUARTZ-255) These developmental theories were instantiated in computational models, making them predecessors of deep learning systems. These developmental models share the property that various proposed learning dynamics in the brain (e.g., a wave of [nerve growth factor](./Nerve_growth_factor)) support the [self-organization](./Self-organization) somewhat analogous to the neural networks utilized in deep learning models. Like the [neocortex](./Neocortex), neural networks employ a hierarchy of layered filters in which each layer considers information from a prior layer (or the operating environment), and then passes its output (and possibly the original input), to other layers. This process yields a self-organizing stack of [transducers](./Transducer), well-tuned to their operating environment. A 1995 description stated, "...the infant's brain seems to organize itself under the influence of waves of so-called trophic-factors ... different regions of the brain become connected sequentially, with one layer of tissue maturing before another and so on until the whole brain is mature".[[256]](./Deep_learning#cite_note-BLAKESLEE-256)

 

A variety of approaches have been used to investigate the plausibility of deep learning models from a neurobiological perspective. On the one hand, several variants of the [backpropagation](./Backpropagation) algorithm have been proposed in order to increase its processing realism.[[257]](./Deep_learning#cite_note-257)[[258]](./Deep_learning#cite_note-258) Other researchers have argued that unsupervised forms of deep learning, such as those based on hierarchical [generative models](./Generative_model) and [deep belief networks](./Deep_belief_network), may be closer to biological reality.[[259]](./Deep_learning#cite_note-259)[[260]](./Deep_learning#cite_note-260) In this respect, generative neural network models have been related to neurobiological evidence about sampling-based processing in the cerebral cortex.[[261]](./Deep_learning#cite_note-261)

 

Although a systematic comparison between the human brain organization and the neuronal encoding in deep networks has not yet been established, several analogies have been reported. For example, the computations performed by deep learning units could be similar to those of actual neurons[[262]](./Deep_learning#cite_note-262) and neural populations.[[263]](./Deep_learning#cite_note-263) Similarly, the representations developed by deep learning models are similar to those measured in the primate visual system[[264]](./Deep_learning#cite_note-264) both at the single-unit[[265]](./Deep_learning#cite_note-265) and at the population[[266]](./Deep_learning#cite_note-266) levels.

 

## Commercial activity

 

[Facebook](./Facebook)'s AI lab performs tasks such as [automatically tagging uploaded pictures](./Automatic_image_annotation) with the names of the people in them.[[267]](./Deep_learning#cite_note-METZ2013-267)

 

Google's [DeepMind Technologies](./DeepMind_Technologies) developed a system capable of learning how to play [Atari](./Atari) video games using only pixels as data input. In 2015 they demonstrated their [AlphaGo](./AlphaGo) system, which learned the game of [Go](./Go_(game)) well enough to beat a professional Go player.[[268]](./Deep_learning#cite_note-268)[[269]](./Deep_learning#cite_note-269)[[270]](./Deep_learning#cite_note-270) [Google Translate](./Google_Translate) uses a neural network to translate between more than 100 languages.

 

In 2017, Covariant.ai was launched, which focuses on integrating deep learning into factories.[[271]](./Deep_learning#cite_note-271)

 

As of 2008,[[272]](./Deep_learning#cite_note-272) researchers at [The University of Texas at Austin](./University_of_Texas_at_Austin) (UT) developed a machine learning framework called Training an Agent Manually via Evaluative Reinforcement, or TAMER, which proposed new methods for robots or computer programs to learn how to perform tasks by interacting with a human instructor.[[241]](./Deep_learning#cite_note-:12-241) First developed as TAMER, a new algorithm called Deep TAMER was later introduced in 2018 during a collaboration between [U.S. Army Research Laboratory](./U.S._Army_Research_Laboratory) (ARL) and UT researchers. Deep TAMER used deep learning to provide a robot with the ability to learn new tasks through observation.[[241]](./Deep_learning#cite_note-:12-241) Using Deep TAMER, a robot learned a task with a human trainer, watching video streams or observing a human perform a task in-person. The robot later practiced the task with the help of some coaching from the trainer, who provided feedback such as "good job" and "bad job".[[273]](./Deep_learning#cite_note-273)

 

## Criticism and comment

 

Deep learning has attracted both criticism and comment, in some cases from outside the field of computer science.

 

### Theory

 See also: [Explainable artificial intelligence](./Explainable_artificial_intelligence) 

A main criticism concerns the lack of theory surrounding some methods.[[274]](./Deep_learning#cite_note-274) Learning in the most common deep architectures is implemented using well-understood gradient descent. However, the theory surrounding other algorithms, such as contrastive divergence is less clear.[*[citation needed](./Wikipedia:Citation_needed)*] (e.g., Does it converge? If so, how fast? What is it approximating?) Deep learning methods are often looked at as a [black box](./Black_box), with most confirmations done empirically, rather than theoretically.[[275]](./Deep_learning#cite_note-Knight_2017-275)

 

In further reference to the idea that artistic sensitivity might be inherent in relatively low levels of the cognitive hierarchy, a published series of graphic representations of the internal states of deep (20-30 layers) neural networks attempting to discern within essentially random data the images on which they were trained[[276]](./Deep_learning#cite_note-276) demonstrate a visual appeal: the original research notice received well over 1,000 comments, and was the subject of what was for a time the most frequently accessed article on *[The Guardian](./The_Guardian)'s*[[277]](./Deep_learning#cite_note-277) website.

 

With the support of [Innovation Diffusion Theory](./Diffusion_of_innovations) (IDT), a study analyzed the diffusion of Deep Learning[[278]](./Deep_learning#cite_note-278) in BRICS and OECD countries using data from [Google Trends](./Google_Trends).

 

### Errors

 

Some deep learning architectures display problematic behaviors,[[279]](./Deep_learning#cite_note-goertzel-279) such as confidently classifying unrecognizable images as belonging to a familiar category of ordinary images (2014)[[280]](./Deep_learning#cite_note-280) and misclassifying minuscule perturbations of correctly classified images (2013).[[281]](./Deep_learning#cite_note-281) [Goertzel](./Ben_Goertzel) hypothesized that these behaviors are due to limitations in their internal representations and that these limitations would inhibit integration into heterogeneous multi-component [artificial general intelligence](./Artificial_general_intelligence) (AGI) architectures.[[279]](./Deep_learning#cite_note-goertzel-279) These issues may possibly be addressed by deep learning architectures that internally form states homologous to image-grammar[[282]](./Deep_learning#cite_note-282) decompositions of observed entities and events.[[279]](./Deep_learning#cite_note-goertzel-279) [Learning a grammar](./Grammar_induction) (visual or linguistic) from training data would be equivalent to restricting the system to [commonsense reasoning](./Commonsense_reasoning) that operates on concepts in terms of grammatical [production rules](./Production_(computer_science)) and is a basic goal of both human language acquisition[[283]](./Deep_learning#cite_note-283) and [artificial intelligence](./Artificial_intelligence) (AI).[[284]](./Deep_learning#cite_note-284)

 

### Cyber threat

 

As deep learning moves from the lab into the world, research and experience show that artificial neural networks are vulnerable to hacks and deception.[[285]](./Deep_learning#cite_note-285) By identifying patterns that these systems use to function, attackers can modify inputs to ANNs in such a way that the ANN finds a match that human observers would not recognize. For example, an attacker can make subtle changes to an image such that the ANN finds a match even though the image looks to a human nothing like the search target. Such manipulation is termed an "[adversarial attack](./Adversarial_machine_learning)".[[286]](./Deep_learning#cite_note-286)

 

In 2016 researchers used one ANN to doctor images in trial and error fashion, identify another's focal points, and thereby generate images that deceived it. The modified images looked no different to human eyes. Another group showed that printouts of doctored images then photographed successfully tricked an image classification system.[[287]](./Deep_learning#cite_note-:4-287) One defense is reverse image search, in which a possible fake image is submitted to a site such as [TinEye](./TinEye) that can then find other instances of it. A refinement is to search using only parts of the image, to identify images from which that piece may have been taken**.**[[288]](./Deep_learning#cite_note-288)

 

Another group showed that certain [psychedelic](./Psychedelic_art) spectacles could fool a [facial recognition system](./Facial_recognition_system) into thinking ordinary people were celebrities, potentially allowing one person to impersonate another. In 2017 researchers added stickers to [stop signs](./Stop_sign) and caused an ANN to misclassify them.[[287]](./Deep_learning#cite_note-:4-287)

 

ANNs can however be further trained to detect attempts at [deception](./Deception), potentially leading attackers and defenders into an arms race similar to the kind that already defines the [malware](./Malware) defense industry. ANNs have been trained to defeat ANN-based anti-malware software by repeatedly attacking a defense with malware that was continually altered by a [genetic algorithm](./Genetic_algorithm) until it tricked the anti-malware while retaining its ability to damage the target.[[287]](./Deep_learning#cite_note-:4-287)

 

In 2016, another group demonstrated that certain sounds could make the [Google Now](./Google_Now) voice command system open a particular web address, and hypothesized that this could "serve as a stepping stone for further attacks (e.g., opening a web page hosting drive-by malware)".[[287]](./Deep_learning#cite_note-:4-287)

 

In "[data poisoning](./Adversarial_machine_learning#Data_poisoning)", false data is continually smuggled into a machine learning system's training set to prevent it from achieving mastery.[[287]](./Deep_learning#cite_note-:4-287)

 

### Data collection ethics

 

The deep learning systems that are trained using supervised learning often rely on data that is created or annotated by humans, or both.[[289]](./Deep_learning#cite_note-289) It has been argued that not only low-paid [clickwork](./Clickworkers) (such as on [Amazon Mechanical Turk](./Amazon_Mechanical_Turk)) is regularly deployed for this purpose, but also implicit forms of human [microwork](./Microwork) that are often not recognized as such.[[290]](./Deep_learning#cite_note-:13-290) The philosopher [Rainer Mühlhoff](./Rainer_Mühlhoff) distinguishes five types of "machinic capture" of human microwork to generate training data: (1) [gamification](./Gamification) (the embedding of annotation or computation tasks in the flow of a game), (2) "trapping and tracking" (e.g. [CAPTCHAs](./CAPTCHA) for image recognition or click-tracking on Google [search results pages](./Search_engine_results_page)), (3) exploitation of social motivations (e.g. [tagging faces](./Tag_(Facebook)) on [Facebook](./Facebook) to obtain labeled facial images), (4) [information mining](./Information_mining) (e.g. by leveraging [quantified-self](./Quantified_self) devices such as [activity trackers](./Activity_tracker)) and (5) clickwork.[[290]](./Deep_learning#cite_note-:13-290)

 

## See also

  
- [Applications of artificial intelligence](./Applications_of_artificial_intelligence)
- [Comparison of deep learning software](./Comparison_of_deep_learning_software)
- [Compressed sensing](./Compressed_sensing)
- [Differentiable programming](./Differentiable_programming)
- [Echo state network](./Echo_state_network)
- [List of artificial intelligence projects](./List_of_artificial_intelligence_projects)
- [Liquid state machine](./Liquid_state_machine)
- [List of datasets for machine-learning research](./List_of_datasets_for_machine-learning_research)
- [Outline of deep learning](./Outline_of_deep_learning)
- [Reservoir computing](./Reservoir_computing)
- [Scale space and deep learning](./Scale_space#Deep_learning_and_scale_space)
- [Sparse coding](./Sparse_coding)
- [Stochastic parrot](./Stochastic_parrot)
- [Topological deep learning](./Topological_deep_learning)

  


