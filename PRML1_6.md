### 1.6 Information Theory
#### entropy
- *heuristic motivation* : If the probability of certain event is higher, then the information we get will be less, vice versa. (negative logarithm)
- *definition* : the average amount of information of the process that the value of a random variable is tranmitted to its receiver.
$$ H[x]=-\int_{x}p(x)log_2p(x)$$
- The entropy of a nonuniform probability distribution is less than a uniform one because the information could be coded in a rather shorter length.
- **The noiseless coding theorem** : the entropy is a lower bound on the number of bits needed to transmit the state of a random variable.
#### entropy for discrete random variables
- The situation could be seen as trying to allocate N identical objects into n bins where each bin could be interpreted as the states $x_i$ of each variable. In the ith bin, there are $n_i$ objects.
- **multiplicy** : the total number of different ways of allocating the objects
$$ W=\frac{N!}{\prod_in_i!}$$
- The entropy is defined as the logarithm of multiplicy. After a long series of operation including Strling's approximation, we have:
$$ H[p] = -\sum_ip(x_i)lnp(x_i)$$
    - minimum : 0 when one $p_i=1$, and all others equal zero. 
    - maximum : $lnM$ when all $p_i=\frac{1}{M}$ where M is the number of states(using a *Lagrange multiplier*)
#### entropy for continuous random variable(differential entropy)
- divide the input space into bins of width △, then apply the *mean value theorem* to reduce the continuous variable to a discrete one.
$$ \lim_{\Delta \to 0}\{\sum_ip(x_i)\Delta lnp(x_i)\}=-\int p(x)lnp(x)dx$$
    - differs from the discrete entropy by a quantity $ln\Delta$ which diverges in the limit
    - maximum : Gaussian distribution(using three Lagrange operators)
    - the entropy increases as the distribution becomes broader
#### conditional entropy
- assuming we have a joint distribution $p(x, y)$, when x is known, then the average information we need to determine y is :
    $$ H[y|x]=-\int\int p(y, x)lnp(y|x)dydx$$
- we could also get the following formula easily:
$$ H[x, y]=H[y|x] + H[x]$$
#### Applications : Relative entropy and mutual information
##### situation : an unknown distribution $p(x)$ which we have modeled using $q(x)$
- **Kullback and Leibler divergence** : the additional information needed to specify the value of x using $q(x)$ when the real one is $p(x)$
$$ KL(p||q)=-\int p(x)ln\{ \frac{q(x)}{p(x)} \}dx$$
- using **Jensen's inequality** for convex function
$$ f(E|x|)\le E|f(x)|$$
we can find that $KL(p||q)\ge 0$ if and only if $p(x) = q(x)$
- minimizing *KL divergence* is equivalent to maximizing the likelihood function
- **mutual information** : represents the reduction of uncertainty about y as a consequence of the new observation x by the process of determining whether x and y are independent in their joint distribution
$$ I[x, y]=KL(p(x, y) || p(x)p(y))$$
$I[x, y] \ge 0$ if and only if x and y are independent.
- From a bayesian prospective:
$$ I[x, y]=H[y]-H[y|x]$$
where $p(y)$ is the prior probability, and $p(y|x)$ is the posterior probability.