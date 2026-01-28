### full gradient descent
- given a [[neural network]] $f_\theta$ and a [[loss function]] $\ell$
- with the [[backpropagation]] algorithm we can calculate the [[gradient]] of the [[risk]] $\mathcal{R}(\theta)$ with respect to the parameters $\theta$
- this works because the [[risk]] is just a linear function of the [[loss function]] of the samples

$$
\nabla_\theta\mathcal{R}(\theta) = \frac{1}{n} \sum_{i=1}^n \nabla_\theta \ell\left(y_i, f_\theta(x_i)\right)
$$

1) calculate $\nabla_\theta\mathcal{R}(\theta)$ for the complete [[training dataset]]
2) update the parameters

$$
\theta_{t+1} = \theta_{t} - \alpha \nabla_\theta\mathcal{R}(\theta_t)
$$

3) repeat iteratively until stopping criterion satisfied

# -------------


![[neural network#neural network]]


![[gradient descent#gradient descent]]

![[backpropagation#backpropagation]]

