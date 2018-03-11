### 1.2.1&1.2.2
- **sum rule** and **product rule**
- **Bayesian Formula**
<<<<<<< HEAD
- **Expectation and covariances**

### 1.2.3&1.2.4
- **Bayesian prospective** : describe uncertainty in model parameters
- right-hand side of Bayes's theorem, *p(D|w)* is called the **likelihood function**
- Bayes's theorem : *posterior is proportional to the product of likelihood and prior*
- frequentists and bayesians differ on the likelihood function
    - frequentists : maximum likelihood, bootstrap
    - problems of bayesians : prior distribution is often selected on the basis of mathematical convenience rather than reflections of prior beliefs
- **Mode** : maximum of a distribution, for a Gaussian distribution, the mode coincides with the mean
- **i.i.d.** : independent and identically distributed(data points that are drawn independently from the same distribution)
- **Likelihood function of Gaussian distribution** : p(x | μ, δ2) = products of N(x |μ, δ2) from one to n
- Maximum likelihood approach underestimates the variance of distribution(bias) -> over-fitting

### 1.2.5&1.2.6(curve fitting from a probablistic view)
- **frequentists**: express our uncertainty over the target variable using a probablity distribution
    - *A Gaussian distribution* with a mean equal to the value of *y(x, w)*(polynominal curve) and β as the inverse variance
    - using *Maximum likelihood* to determine the values of w and β
- **semi-bayesian**:
    - construct a *prior distribution* : p(w | α) *(α : hyperparameter)*
    - the posterior distribution is proportional to the product of likelihood function and the prior distribution:
    *p(w | **x**, **t**, α, β) is proportional to p(**t** | **x**, w, β) * p(w | α)*
    - maximize the posterior distribution(MAP)
- **bayesian**: applying only sum and product rules;integrate over all values of w(marginalization)
    - *predictive distribution*:
    $$ p(t |x, \bold {x}, \bold {t}) = \int p(t | x, w)p(w | \bold {x}, \bold {t})dw $$
    α and β are omitted assuming they have been known in advance
    - The *predictive distribution* canbe evaluated analytically. It is a Gaussian distribution.
    $$ p(t | x, \bold {x}, \bold {t}) = N(t|m(x), s^2(x)) $$
    $$ m(x) = βψ(x)^TS\sum_{n=1}^Nψ(x_n)t_n $$
    $$ s^2(x) = β^{-1} + ψ(x)^TSψ(x) $$
    $$ S^{-1} = αI + β\sum_{n=1}^Nψ(x_n)ψ(x)^T $$
    - the mean and the variance are both dependent on x
=======
- **Expectations and covariances**

### 1.2.3&1.2.4
- **Bayesian Prospective** : describe uncertainty in model parameters
- right-hand side of Bayes's theorem, *p(D|w)* is called the **likelihood function**
- Bayes's thorem : *posterior <- likelihood x prior*
- frequentists and bayesians differ on the likelihood function
    - frequentists : maximum likelihood, bootstrap
    - problems of bayesians : prior distribution is often selected on the basis of mathematical convenience rathen than reflections of prior beliefs
- **Mode** : maximum of a dstribution, for a Gaussian distribution, the mode coincides with the mean
- **i.i.d.** : independent and identically distributed(data points that are drawn independently from the same distribution)
- **Likelihood function of Gaussian distribution** : p(x | μ,σ2) = products of N(x | μ,σ2) from one to N
- Maximum likelihood approach underestimates the variance of the distribution(bias) -> over-fitting
>>>>>>> 7466e235fd06358527026b9c05cdd833c0e5ff37
