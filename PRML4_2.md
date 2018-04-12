### 4.2 Probabilistic Generative Models
#### basic form
- for two classes
$$ p(C_1|x)=\frac{p(x|C_1)p(C_1)}{p(x|C_1)p(C_1)+p(x|C_2)p(C_2)}$$
define $a=ln\frac{p(x|C_1)p(C_1)}{p(x|C_2)p(C_2)}$
thus $p(C_1|x)=\sigma(a)=\frac{1}{1+exp(-a)}$ known as **sigmoid function** or **squashing function** which maps the whole real axis into a finite interval
- for k classes
$$ p(C_k|x)=\frac{exp(a_k)}{\sum_jexp(a_j)}$$ which is known as the **softmax function**
define $a_k=lnp(x|C_k)p(C_k)$
#### Model Selection
- assume the class-conditional densities $p(x|C_k)$ are Gaussian (the same holds trues for discrete features and exponential family)
- assume all class-conditional densities share the same covariance matrix
- then for two classes:
$$ p(C_1|x)=\sigma(w^Tx+w_0)$$
when the value of $p(C_1|x)$ is constant, we will get the decision surface as a linear function of x
- for k classes, the result is similar
- one option is to use a maximum likelihood method to optimize the parameters

### 4.3 Probabilistic Discriminative Models
#### fixed basis function
- using a nonlinear basis function $\phi(x)$, therefore, the resulting decision boundary will be linear in the feature space $\phi$
#### Logistic regression
$$ p(C_1|\phi)=y(\phi)=\sigma(w^T\phi)$$
*likelihood function* : $p(t|w)=\prod_{n=1}^Ny_n^{t_n}{1-y_n}^{1-t_n}$
*error function* : the negative logarithm of the likelihood function (**cross-entropy**)
- using maximum likelihood method would lead to severe over-fitting for linearly separable problems.
#### Iterative reweighted least squares
- using **Newton-Raphson update** to minimize the error function
$$ w^{new}=w^{old}-H^{-1}\nabla E(w)$$
where $H$ is the **Hessian Matrix** whose elements comprise the second derivatives of $E(w)$ with respect to the components of $w$
    - when applying Newton-Raphson update to the cross-entropy error function, the Hessian matrix would no longer be a constant, but depends on w through a weighting matrix $R$
    - each time, using the weight parameter $w$ to reivise the weighting matrix $R$
#### Probit regression
- exploring other types of discriminative model:
$$ p(t=1|a)=f(a)$$
$$ a=w^T\phi$$
where the activation function $f(·)$ could be defined as:
$t_n=1$ if $a_n\geq\theta$ and $t_n=0$ otherwise
- assuming the threshold value $\theta$ is drawn from a probability density $p(\theta)$ and $p(\theta)$ is a zero mean,unit variance Gaussian:
$$ \Phi(a)=\int_{-\infty}^aN(\theta|0, 1)d\theta$$
which is known as **probit function**
- using the *erf function*, 
$$ \Phi(a)=\frac{1}{2}(1+\frac{1}{\sqrt{2}}erf(a))$$
- compared with logistic sigmoid, probit regression is significanyly more sensitive to outliers
- a probability $\epsilon$ could be introduced to tackle the problem of mislabelling.
$$p(t|x)=(1-\epsilon)\sigma(x)+\epsilon(1-\sigma(x))$$
- maximum likelihood method or IRLS method could be used to determine the parameters
#### Canonical link functions
$$\nabla E(w) = \sum_{n=1}^N(y_n-t_n)\phi_n$$
- where $y_n = w^T\phi_n$
- this is a general result of assuming a conditional distribution for the target variable from the exponential family, along with a corresponding choice for the activation function known as **canonical link function**.
