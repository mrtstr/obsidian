### mini batch gradient descent
- given a [[neural network]] $f_\theta$ and a [[loss function]] $\ell$
- with the [[backpropagation]] algorithm we can calculate the [[gradient]] of the [[risk]] $\mathcal{R}(\theta)$ with respect to the parameters $\theta$
- this works because the [[risk]] is just a linear function of the [[loss function]] of the samples

$$
\nabla_\theta\mathcal{R}(\theta) = \frac{1}{n} \sum_{i=1}^n \nabla_\theta \ell\left(y_i, f_\theta(x_i)\right)
$$

1) pick and random subset of $\{1, ..., m\}$ $B_t$ with $|B_t|=s$
2) calculate the gradient on the batch

$$\nabla_\theta\mathcal{R}^{B_t}(\theta) = \frac{1}{n} \sum_{i\in B_t}^s \nabla_\theta \ell\left(y_i, f_\theta(x_i)\right)$$

3) update the parameters $\theta_{t+1} = \theta_{t} - \alpha \nabla_\theta\mathcal{R}(\theta_t)$
4) repeat iteratively until stopping criterion satisfied

- for $s=1$ we have **stochastic gradient descent** and for $s=m$ we have **full gradient descent**
- high batch size:
	- faster calculation because it can be parallelized
	- leads to [[regularization]]
	- but increases the memory requirements

# -------------


![[neural network#neural network]]


![[gradient descent#gradient descent]]

![[backpropagation#backpropagation]]

