### 1.1 Introduction
#### machine learning process:
- a function : y = f(x)
- **training phase** : to determine the precise form of f(x)
- **generalization** : to make the function work beyond train set
- **pre-processing** : feature extraction
- **supervised machine learning** : training data contain input vectors and also the target vectors, related to **classification** problems
- **unsupervised machine learning** : no target vectors in training data, related to **clustering** problems and **density estimation** problems and **visualization** problems
- **regression** : output consists of one or more continuous variables
- **reinforcement learning** : a process of trial and error, a trade-off between exploration and exploitation
---
### 1.1 Example: Polynomial Curve Fitting
- *Input:* generating training data based on certain distribution added by a small level of random noise capturing the property of many real data sets
- **Probability theory** help us express the uncertainty in the problem, on the other hand **decision theory** help us  exploit the probablistic representation to make optimal predictions
- **over-fitting** could be seen a general property of **maximum likelihood** which could avoided by using a **Bayesian approach** because the effective number of parameters adapts automatically to the size of data set
- **Regularization** could be used to control over-fitting by adding a penalty term to prevent the coefficients from reaching large values
