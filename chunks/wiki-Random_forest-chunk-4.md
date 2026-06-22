---
source: sources/wiki-Random_forest.md
source_url: https://en.wikipedia.org/wiki/Random_forest
chunk: 4/6
---

## Disadvantages

 

While random forests often achieve higher accuracy than a single decision tree, they sacrifice the intrinsic [interpretability](./Interpretability) of decision trees. Decision trees are among a fairly small family of machine learning models that are easily interpretable along with linear models, [rule-based](./Rule-based_machine_learning) models, and [attention](./Attention_(machine_learning))-based models. This interpretability is one of the main advantages of decision trees. It allows developers to confirm that the model has learned realistic information from the data and allows end-users to have trust and confidence in the decisions made by the model.[[39]](./Random_forest#cite_note-:0-39)[[3]](./Random_forest#cite_note-elemstatlearn-3) For example, following the path that a decision tree takes to make its decision is quite trivial, but following the paths of tens or hundreds of trees is much harder. To achieve both performance and interpretability, some model compression techniques allow transforming a random forest into a minimal "born-again" decision tree that faithfully reproduces the same decision function.[[39]](./Random_forest#cite_note-:0-39)[[49]](./Random_forest#cite_note-49)[[50]](./Random_forest#cite_note-50)

 

Another limitation of random forests is that if features are linearly correlated with the target, random forest may not enhance the accuracy of the base learner.[[39]](./Random_forest#cite_note-:0-39)[[42]](./Random_forest#cite_note-:1-42) Likewise in problems with multiple categorical variables.[[51]](./Random_forest#cite_note-:3-51)

 

## See also

 
- [Boosting](./Boosting_(machine_learning)) – Ensemble learning method
- [Decision tree learning](./Decision_tree_learning) – Machine learning algorithm
- [Ensemble learning](./Ensemble_learning) – Statistics and machine learning technique
- [Gradient boosting](./Gradient_boosting) – Machine learning technique
- [Non-parametric statistics](./Non-parametric_statistics) – Type of statistical analysisPages displaying short descriptions of redirect targets
- [Randomized algorithm](./Randomized_algorithm) – Algorithm that employs a degree of randomness as part of its logic or procedure

 


