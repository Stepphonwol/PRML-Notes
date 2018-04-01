## 4 Linear Models for Classification
- **activation function** :
$$ y(x) = f (w^Tx+w_o).$$
$y(x)=constant$ : decision surfaces
(D-1) dimensional decision hyperplanes when the input vector is D dimensional

### 4.1 Discriminant Functions
#### 4.1.1 Two classes (Form)
- $y(x) = w^Tx+w_0$
    - $w$ is perpendicular to the decision surface. Therefore, w determines the direction of the decision surface.
    - $w_0$, the **bias parameter** determines the distance from the origin to the decision surface.
#### 4.1.2 Multiple classes (Form)
- build a K-class discriminant function based on 2-class function will lead to ambiguous classification. (one-versus-the-rest and one-versus-one)
- $y_k(x)=w_k^Tx+w_k$ which assigns a point $x$ to $C_k$ if $y_k(x) > y_j(x)$ for all $j\neq k$. The decision regions of this function are *singly connected and convex*.
- $y(x)=\widetilde{W^T}\widetilde{x}$ group all $y_k$ together by adding a dummy input value $x_0=1$
#### 4.1.3 Least squares for classification (parameter learning)
- *Idea* : Determine the parameter matrix by minimizing a sum-of-squares error function. Then a new input $x$ is assigned to the class for which the output is largest.
- *Problems* : too sensitive to outliers, give poor results when the input dimension is higher. **The failure of least squares should not surprise us when we recall that it corresponds to maximum likelihood under the assumption of a Gaussian conditional distribution, whereas binary target vectors clearly have a distribution that is far from Gaussian.**
#### 4.1.4 Fisher's linear discriminant
- based on **dimensionality reduction**
- for the case of two classes, project the D-dimensional input vector $x$ to one dimension using $y=w^Tx$
    - maximize a function that will give a large separation between the projected class means while also giving a small variance within each class, thereby minimizing the class overlap
    - finally, the direction of $w$ is given(**Fisher Criterion**):
    $$w\propto S_W^{-1} (m_2-m_1)$$
    where $S_W^{-1}$ is the inverse of the total within-class variance, $m_1$ and $m_2$ are projected class means
    - for the two-class problem, when choosing a different type of target coding scheme, the Fisher criterion can be obtained as a special case of least squares.
- for multiple classes, the criterion is rewritten explicitly. P192
#### 4.1.7 The perceptron algorithm
- based on a two-class model
- based on a *fixed nonlinear transformation* $\phi$ to give a feature vector. $y(x)=f(w^T\phi(x))$. 
$f(a) = +1$ when a >= 0, $f(a)=-1$ when a <= 0
- **The perceptron criterion** : where m denotes the set of all misclassified patterns 
$$ E_p(w)=-\sum_{n\in M}w^T\phi_nt_n$$
assosicates zero error with any pattern that is correctly classified, whereas for a mis-classified pattern $x_n$ it tries to minimize the quantity $-w^T\phi(x_n)t_n$
- apply the **the stochastic gradient descent algorithm** to the criterion
$$ w^{(\tau+1)}=w^{(\tau)}-\eta\nabla E_p(w)=w^{(\tau)}+\eta\phi_nt_n$$
    - In other words, **if the pattern is correctly classified, then the weight parameter remains unchanged, whereas if it is incorrectly classified, then the feature vector $\phi(x)$ will be added or subtracted from $w$ accordingly**.
- **the perceptron convergence theorem** : when the training data is linearly separable, then the perceptron algorithm is guaranteed to find an exact solution in finite steps.
- *Problems* : no probablistic outputs, couldn't be generalized to K classes, based on linear combinations of fixed basis functions.