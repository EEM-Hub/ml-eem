---
source: chunks/wiki-BiasE28093variance_tradeoff-chunk-4.md
source_url: https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff
---

## Bias-Variance Tradeoff

The bias-variance tradeoff is a fundamental concept in machine learning that describes the tension between two sources of prediction error. **Bias** is the error from overly simplistic model assumptions (underfitting), while **variance** is the error from excessive sensitivity to training data fluctuations (overfitting). Minimizing total error requires balancing the two, as reducing one typically increases the other. The provided source is primarily a navigation/index page, so this summary draws on the concept's canonical definition and its placement within the broader AI taxonomy.

## Key Concepts

- **Bias**: systematic error from a model that is too simple to capture the true relationship in the data; leads to underfitting
- **Variance**: error from a model that is too complex and fits noise in the training data; leads to overfitting
- **Total error** = Bias² + Variance + Irreducible noise (Bayes error)
- The tradeoff: increasing model complexity reduces bias but increases variance, and vice versa
- **Double descent**: a related phenomenon where test error decreases, increases, then decreases again as model complexity grows far beyond the interpolation threshold — challenges the classical U-shaped tradeoff curve
- The tradeoff applies to all supervised learning algorithms, including regression (e.g., LOESS) and classification (e.g., K-Nearest Neighbors)

## Commands and Syntax

No commands or configuration syntax are provided in this source. The referenced interactive visualization (MLU-Explain) demonstrates the tradeoff using:
- **LOESS Regression**: varying the smoothing span controls the bias-variance balance
- **K-Nearest Neighbors**: varying K controls it — small K = low bias / high variance; large K = high bias / low variance

## Relationships

- **Overfitting**: the direct consequence of high variance / low bias; the model memorizes training noise
- **Regularization**: a primary technique for managing the tradeoff by penalizing model complexity (L1, L2, dropout, etc.)
- **Loss functions**: the metric through which bias and variance manifest as measurable error
- **Hyperparameters**: tuning hyperparameters (learning rate, model capacity, K in KNN, polynomial degree) is how practitioners navigate the tradeoff in practice
- **Gradient descent / SGD**: optimization procedures whose convergence behavior interacts with model complexity choices
- **Double descent**: extends the classical tradeoff into the overparameterized regime, showing that very large models (e.g., deep neural networks) can generalize well despite interpolating the training data
- **Data augmentation / dataset size**: more data reduces variance without increasing bias, shifting the optimal complexity point

## Exam-Relevant Points

- Total prediction error decomposes into bias², variance, and irreducible error — know this decomposition formula
- High bias = underfitting; high variance = overfitting — be able to identify which from a learning curve
- Increasing training data reduces variance but does not affect bias
- Regularization reduces variance at the cost of slightly increased bias
- Simple models (e.g., linear regression) tend toward high bias / low variance; complex models (e.g., deep networks, small-K KNN) tend toward low bias / high variance
- The classical U-shaped test error curve is the visual representation of the tradeoff
- Double descent is a modern extension: test error can improve again well past the interpolation threshold in overparameterized models
- Cross-validation is the standard practical method for finding the optimal bias-variance balance point
