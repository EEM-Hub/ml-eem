---
source: chunks/wiki-Unsupervised_learning-chunk-1.md
source_url: https://en.wikipedia.org/wiki/Unsupervised_learning
---

## Unsupervised Learning

Unsupervised learning is a machine learning paradigm where algorithms learn patterns exclusively from unlabeled data, in contrast to supervised learning which requires labeled datasets. It encompasses data collection (typically harvested cheaply "in the wild," such as web-crawled text corpora), specialized algorithms, training procedures, and downstream applications. The paradigm is foundational to modern large-scale AI, including generative pretraining methods like GPT and representation learning via autoencoders.

## Key Concepts

- **Definition**: Learning patterns from unlabeled data — no target labels or classifications are provided during training
- **Supervision spectrum**: Unsupervised sits alongside supervised, semi-supervised (small portion labeled), weak supervision, and self-supervised learning; some researchers classify self-supervised learning as a form of unsupervised learning
- **Data advantage**: Datasets can be harvested cheaply at scale (e.g., Common Crawl) versus the expensive manual construction required for supervised datasets (e.g., ImageNet)
- **Discriminative vs. generative tasks**: Discriminative tasks (recognition) tend toward supervised methods; generative tasks (imagination) tend toward unsupervised — but the boundary is blurred and tasks often employ both
- **Generative task pattern**: Sample a datapoint, remove part of the data, and the model must infer the removed part (e.g., denoising autoencoders, BERT's masked language modeling)
- **Transfer learning pattern**: Models trained unsupervised are often fine-tuned for downstream supervised tasks (generative pretraining → fine-tuning for classification)
- **Feature learning**: Autoencoders trained unsupervised produce useful feature representations that serve as modules in other models (e.g., latent diffusion models)

## Commands and Syntax

No specific commands — this is a conceptual/theoretical topic. Key algorithmic categories include:

- **Clustering**: k-means, DBSCAN, OPTICS, hierarchical clustering, BIRCH, CURE, fuzzy clustering, expectation-maximization (EM), mean shift
- **Dimensionality reduction**: PCA, t-SNE, ICA, LDA, NMF, factor analysis, CCA
- **Generative models**: Boltzmann machines (restricted), autoencoders (including denoising), GANs, diffusion models
- **Training approach for deep learning**: General-purpose neural network architectures trained via gradient descent with unsupervised training procedures

## Relationships

- **Supervised learning**: Opposite end of the supervision spectrum; requires labeled data; often used for discriminative tasks
- **Semi-supervised / weak supervision**: Hybrid approach using a small amount of labeled data alongside unlabeled data
- **Self-supervised learning**: Closely related — generates its own supervision signal from data structure; sometimes classified as unsupervised
- **Clustering** (k-means, DBSCAN, etc.): Core unsupervised algorithm family for grouping similar data points
- **Dimensionality reduction** (PCA, t-SNE): Core unsupervised technique for reducing feature space
- **Autoencoders / Generative pretraining**: Key architectures that bridge unsupervised pretraining with supervised fine-tuning
- **BERT**: Uses unsupervised denoising (masked language modeling) as its pretraining objective
- **Latent diffusion models**: Use autoencoder-learned features as a component

## Exam-Relevant Points

- Unsupervised learning uses **no labeled data** — this is the defining characteristic
- The supervision spectrum from most to least labeled: supervised → semi-supervised → self-supervised → unsupervised
- **k-means** and **PCA** are the canonical examples of unsupervised clustering and dimensionality reduction, respectively
- Unsupervised data collection is significantly **cheaper** than supervised (web crawling vs. manual annotation)
- The **generative pretraining** paradigm (train unsupervised, then fine-tune supervised) is the foundation of modern LLMs
- The discriminative/generative divide does **not** map cleanly onto supervised/unsupervised — tasks increasingly use hybrid approaches
- **Denoising autoencoders** and **BERT** exemplify the generative task pattern: remove part of input, predict what was removed
- Self-supervised learning's classification (as unsupervised or distinct) is **debated** among researchers
- Historical trajectory of image recognition: supervised → hybrid (unsupervised pretraining) → back to supervised (dropout, ReLU, adaptive learning rates)
