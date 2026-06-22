---
source: sources/wiki-Overfitting.md
source_url: https://en.wikipedia.org/wiki/Overfitting
chunk: 2/2
---

## Underfitting

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/5/55/Underfitted_Model.png/330px-Underfitted_Model.png)](./File:Underfitted_Model.png)Figure 5. The red line represents an underfitted model of the data points represented in blue. A more appropriate model would take the form of a parabola shaped line to represent the curvature of the data points. [![](//upload.wikimedia.org/wikipedia/commons/thumb/3/35/Underfitting_fitted_model.png/330px-Underfitting_fitted_model.png)](./File:Underfitting_fitted_model.png)Figure 6. The blue line represents a fitted model of the data points represented in green. 

Underfitting is the inverse of overfitting, meaning that the statistical model or machine learning algorithm is too simplistic to accurately capture the patterns in the data. A sign of underfitting is that there is a high bias and low variance detected in the current model  or algorithm used (the inverse of overfitting: low [bias](./Bias) and high [variance](./Variance)). This can be gathered from the [Bias-variance tradeoff](./Bias-variance_tradeoff), which is the method of analyzing a model or algorithm for bias error, variance error, and irreducible error. With a high bias and low variance, the result of the model is that it will inaccurately represent the data points and thus insufficiently be able to predict future data results (see [Generalization error](./Generalization_error)). As shown in Figure 5, the linear line could not represent all the given data points due to the line not resembling the curvature of the points. One would expect to see a parabola-shaped line as shown in Figure 6 and Figure 1. If Figure 5 were to be used for analysis, false predictive results would be given contrary to the results if Figure 6 was analyzed.

 

Burnham & Anderson state the following.[[3]](./Overfitting#cite_note-BA2002-3): 32 

 

... an underfitted model would ignore some important replicable (i.e., conceptually replicable in most other samples) structure in the data and thus fail to identify effects that were actually supported by the data. In this case, bias in the parameter estimators is often substantial, and the sampling variance is underestimated, both factors resulting in poor confidence interval coverage. Underfitted models tend to miss important treatment effects in experimental settings.

 

### Resolving underfitting

 

There are multiple ways to deal with underfitting:

 
1. Increase the complexity of the model: If the model is too simple, it may be necessary to increase its complexity by adding more features, increasing the number of parameters, or using a more flexible model. However, this should be done carefully to avoid overfitting.[[15]](./Overfitting#cite_note-:0-15)
2. Use a different algorithm: If the current algorithm is not able to capture the patterns in the data, it may be necessary to try a different one. For example, a neural network may be more effective than a linear regression model for some types of data.[[15]](./Overfitting#cite_note-:0-15)
3. Increase the amount of training data: If the model is underfitting due to a lack of data, increasing the amount of training data may help. This will allow the model to better capture the underlying patterns in the data.[[15]](./Overfitting#cite_note-:0-15)
4. Regularization: Regularization is a technique used to prevent overfitting by adding a penalty term to the loss function that discourages large parameter values. It can also be used to prevent underfitting by controlling the complexity of the model.[[16]](./Overfitting#cite_note-16)
5. [Ensemble Methods](./Ensemble_Methods): Ensemble methods combine multiple models to create a more accurate prediction. This can help reduce underfitting by allowing multiple models to work together to capture the underlying patterns in the data.
6. [Feature engineering](./Feature_engineering): Feature engineering involves creating new model features from the existing ones that may be more relevant to the problem at hand. This can help improve the accuracy of the model and prevent underfitting.[[15]](./Overfitting#cite_note-:0-15)

 

## Benign overfitting

 

Benign overfitting describes the phenomenon of a statistical model that seems to generalize well to unseen data, even when it has been fit perfectly on noisy training data (i.e., obtains perfect predictive accuracy on the training set). The phenomenon is of particular interest in [deep neural networks](./Deep_neural_networks), but is studied from a theoretical perspective in the context of much simpler models, such as [linear regression](./Linear_regression). In particular, it has been shown that [overparameterization](./Overparameterization?action=edit&redlink=1) is essential for benign overfitting in this setting. In other words, the number of directions in parameter space that are unimportant for prediction must significantly exceed the sample size.[[17]](./Overfitting#cite_note-17)

 

## See also

  
- [Bias–variance tradeoff](./Bias–variance_tradeoff)
- [Curve fitting](./Curve_fitting)
- [Data dredging](./Data_dredging)
- [Double descent](./Double_descent)
- [Feature selection](./Feature_selection)
- [Feature engineering](./Feature_engineering)
- [Freedman's paradox](./Freedman's_paradox)
- [Generalization error](./Generalization_error)
- [Goodness of fit](./Goodness_of_fit)
- [Grokking (machine learning)](./Grokking_(machine_learning))
- [Life-time of correlation](./Life-time_of_correlation)
- [Model selection](./Model_selection)
- [Researcher degrees of freedom](./Researcher_degrees_of_freedom)
- [Occam's razor](./Occam's_razor)
- [Primary model](./Helmut_Norpoth#"Primary_Model"_for_US_presidential_elections)
- [Vapnik–Chervonenkis dimension](./Vapnik–Chervonenkis_dimension) – larger VC dimension implies larger risk of overfitting

  

## Notes

  
1. [↑](./Overfitting#cite_ref-1) Definition of "[overfitting](https://web.archive.org/web/20171107014257/https://en.oxforddictionaries.com/definition/overfitting)" at [OxfordDictionaries.com](./OxfordDictionaries.com): this definition is specifically for statistics.
2. [1](./Overfitting#cite_ref-CDS_2-0) [2](./Overfitting#cite_ref-CDS_2-1) [3](./Overfitting#cite_ref-CDS_2-2) Everitt B.S., Skrondal A. (2010), *Cambridge Dictionary of Statistics*, [Cambridge University Press](./Cambridge_University_Press).
3. [1](./Overfitting#cite_ref-BA2002_3-0) [2](./Overfitting#cite_ref-BA2002_3-1) [3](./Overfitting#cite_ref-BA2002_3-2) [4](./Overfitting#cite_ref-BA2002_3-3) Burnham, K. P.; Anderson, D. R. (2002), *Model Selection and Multimodel Inference* (2nd ed.), Springer-Verlag.
4. [↑](./Overfitting#cite_ref-4) Bottou, Léon; Bousquet, Olivier (2011-09-30), ["The Tradeoffs of Large-Scale Learning"](https://dx.doi.org/10.7551/mitpress/8996.003.0015), *Optimization for Machine Learning*, The MIT Press, pp. 351–368, [doi](./Doi_(identifier)):[10.7551/mitpress/8996.003.0015](https://doi.org/10.7551%2Fmitpress%2F8996.003.0015), [ISBN](./ISBN_(identifier)) [978-0-262-29877-3](./Special:BookSources/978-0-262-29877-3), retrieved 2023-12-08`{{citation}}`:  CS1 maint: work parameter with ISBN ([link](./Category:CS1_maint:_work_parameter_with_ISBN))
5. [↑](./Overfitting#cite_ref-5) [Claeskens, G.](./Gerda_Claeskens); [Hjort, N.L.](./Nils_Lid_Hjort) (2008), *Model Selection and Model Averaging*, [Cambridge University Press](./Cambridge_University_Press).
6. [↑](./Overfitting#cite_ref-RMS_6-0) Harrell, F. E. Jr. (2001), *Regression Modeling Strategies*, Springer.
7. [↑](./Overfitting#cite_ref-7) Martha K. Smith (2014-06-13). ["Overfitting"](http://www.ma.utexas.edu/users/mks/statmistakes/ovefitting.html). [University of Texas at Austin](./University_of_Texas_at_Austin). Retrieved 2016-07-31.
8. [↑](./Overfitting#cite_ref-Vittinghoff_et_al._(2007)_8-0) Vittinghoff, E.; McCulloch, C. E. (2007). "Relaxing the Rule of Ten Events per Variable in Logistic and Cox Regression". *[American Journal of Epidemiology](./American_Journal_of_Epidemiology)*. **165** (6): 710–718. [doi](./Doi_(identifier)):[10.1093/aje/kwk052](https://doi.org/10.1093%2Faje%2Fkwk052). [PMID](./PMID_(identifier)) [17182981](https://pubmed.ncbi.nlm.nih.gov/17182981).
9. [↑](./Overfitting#cite_ref-9) Draper, Norman R.; Smith, Harry (1998). *Applied Regression Analysis* (3rd ed.). [Wiley](./John_Wiley_&_Sons). [ISBN](./ISBN_(identifier)) [978-0471170822](./Special:BookSources/978-0471170822).
10. [↑](./Overfitting#cite_ref-10) Jim Frost (2015-09-03). ["The Danger of Overfitting Regression Models"](http://blog.minitab.com/blog/adventures-in-statistics/the-danger-of-overfitting-regression-models). Retrieved 2016-07-31.
11. [1](./Overfitting#cite_ref-hawkins_11-0) [2](./Overfitting#cite_ref-hawkins_11-1) [3](./Overfitting#cite_ref-hawkins_11-2) [4](./Overfitting#cite_ref-hawkins_11-3) Hawkins, Douglas M (2004). "The problem of overfitting". *[Journal of Chemical Information and Modeling](./Journal_of_Chemical_Information_and_Modeling)*. **44** (1): 1–12. [doi](./Doi_(identifier)):[10.1021/ci0342472](https://doi.org/10.1021%2Fci0342472). [PMID](./PMID_(identifier)) [14741005](https://pubmed.ncbi.nlm.nih.gov/14741005). [S2CID](./S2CID_(identifier)) [12440383](https://api.semanticscholar.org/CorpusID:12440383).
12. [1](./Overfitting#cite_ref-earthquake_12-0) [2](./Overfitting#cite_ref-earthquake_12-1) Lee, Timothy B. (3 April 2023). ["Stable Diffusion copyright lawsuits could be a legal earthquake for AI"](https://arstechnica.com/tech-policy/2023/04/stable-diffusion-copyright-lawsuits-could-be-a-legal-earthquake-for-ai/). *Ars Technica*.
13. [↑](./Overfitting#cite_ref-Verge_copilot_13-0) Vincent, James (2022-11-08). ["The lawsuit that could rewrite the rules of AI copyright"](https://www.theverge.com/2022/11/8/23446821/microsoft-openai-github-copilot-class-action-lawsuit-ai-copyright-violation-training-data). *The Verge*. Retrieved 2022-12-07.
14. [↑](./Overfitting#cite_ref-14) LeCun, Yann; Denker, John; Solla, Sara (1989). ["Optimal Brain Damage"](https://proceedings.neurips.cc/paper/1989/hash/6c9882bbac1c7093bd25041881277658-Abstract.html). *Advances in Neural Information Processing Systems*. **2**. Morgan-Kaufmann.
15. [1](./Overfitting#cite_ref-:0_15-0) [2](./Overfitting#cite_ref-:0_15-1) [3](./Overfitting#cite_ref-:0_15-2) [4](./Overfitting#cite_ref-:0_15-3) ["ML | Underfitting and Overfitting"](https://www.geeksforgeeks.org/underfitting-and-overfitting-in-machine-learning/). *GeeksforGeeks*. 2017-11-23. Retrieved 2023-02-27.
16. [↑](./Overfitting#cite_ref-16) Nusrat, Ismoilov; Jang, Sung-Bong (November 2018). ["A Comparison of Regularization Techniques in Deep Neural Networks"](https://doi.org/10.3390%2Fsym10110648). *Symmetry*. **10** (11): 648. [Bibcode](./Bibcode_(identifier)):[2018Symm...10..648N](https://ui.adsabs.harvard.edu/abs/2018Symm...10..648N). [doi](./Doi_(identifier)):[10.3390/sym10110648](https://doi.org/10.3390%2Fsym10110648). [ISSN](./ISSN_(identifier)) [2073-8994](https://search.worldcat.org/issn/2073-8994).
17. [↑](./Overfitting#cite_ref-17) Bartlett, P.L., Long, P.M., Lugosi, G., & Tsigler, A. (2019). Benign overfitting in linear regression. Proceedings of the National Academy of Sciences, 117, 30063 - 30070.

 

## References

 
- [Leinweber, D. J.](./David_Leinweber) (2007). "Stupid data miner tricks". *[The Journal of Investing](./The_Journal_of_Investing)*. **16**: 15–22. [doi](./Doi_(identifier)):[10.3905/joi.2007.681820](https://doi.org/10.3905%2Fjoi.2007.681820). [S2CID](./S2CID_(identifier)) [108627390](https://api.semanticscholar.org/CorpusID:108627390).
- Tetko, I. V.; Livingstone, D. J.; Luik, A. I. (1995). ["Neural network studies. 1. Comparison of Overfitting and Overtraining"](http://www.vcclab.org/articles/jcics-overtraining.pdf) (PDF). *[Journal of Chemical Information and Modeling](./Journal_of_Chemical_Information_and_Modeling)*. **35** (5): 826–833. [doi](./Doi_(identifier)):[10.1021/ci00027a006](https://doi.org/10.1021%2Fci00027a006).

 

## Further reading

 
- [Christian, Brian](./Brian_Christian); Griffiths, Tom (April 2017), "Chapter 7: Overfitting", *Algorithms To Live By: The computer science of human decisions*, [William Collins](./William_Collins_(imprint)), pp. 149–168, [ISBN](./ISBN_(identifier)) [978-0-00-754799-9](./Special:BookSources/978-0-00-754799-9)

 

## External links

 
- [The Problem of Overfitting Data](http://www3.cs.stonybrook.edu/~skiena/jaialai/excerpts/node16.html) – [Stony Brook University](./Stony_Brook_University)
- [What is "overfitting," exactly?](https://statmodeling.stat.columbia.edu/2017/07/15/what-is-overfitting-exactly/) – [Andrew Gelman](./Andrew_Gelman) blog
- [CSE546: Linear Regression Bias / Variance Tradeoff](http://courses.cs.washington.edu/courses/cse546/12wi/slides/cse546wi12LinearRegression.pdf) – [University of Washington](./University_of_Washington)
- [What is Underfitting](https://www.ibm.com/cloud/learn/underfitting) – [IBM](./IBM)

 
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
