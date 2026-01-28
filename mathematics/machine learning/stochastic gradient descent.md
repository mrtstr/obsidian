### stochastic gradient descent
- given a [[neural network]] $f_\theta$ and a [[loss function]] $\ell$
- with the [[backpropagation]] algorithm we can calculate the [[gradient]] of the [[risk]] $\mathcal{R}(\theta)$ with respect to the parameters $\theta$
- this works because the [[risk]] is just a linear function of the [[loss function]] of the samples

$$
\nabla_\theta\mathcal{R}(\theta) = \frac{1}{n} \sum_{i=1}^n \nabla_\theta \ell\left(y_i, f_\theta(x_i)\right)
$$

1) pick a single random sample
2) calculate $\nabla_\theta\mathcal{R}(\theta)$ for that sample
3) update the parameters $\theta_{t+1} = \theta_{t} - \alpha \nabla_\theta\mathcal{R}(\theta_t)$
4) repeat iteratively until stopping criterion satisfied

- let $\mathcal{R}^*$ be the [[risk|true risk]] defined as follows

$$
\begin{split}
\mathcal{R}^*(\theta) 
&= \mathbb{E}_{(x,y) \sim \mathcal{P}_{XY}}\left[\ell\left( y, f_\theta(x)\right)\right] \\
\end{split}
$$

- when calculating the [[gradient]] of a random sample, we are basically calculating the [[expectation|expected]] gradient
- because if the linearity of the [[risk]] (assuming i.i.d. training samples) we can pull in the [[expectation]]
- this shows that the gradient of a random sample is an unbiased estimator of the true risk

$$
\begin{split}
\mathbb{E} \left[\nabla_\theta \ell\left(y, f_\theta(x)\right)\right]
&=  \nabla_\theta  \mathbb{E}\left[\ell\left(y, f_\theta(x)\right)\right] \\
&=\nabla_\theta\mathcal{R}^*(\theta) \\
\end{split}
$$

# -------------


![[neural network#neural network]]


![[gradient descent#gradient descent]]

![[backpropagation#backpropagation]]

