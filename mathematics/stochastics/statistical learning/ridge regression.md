### ridge regression
- [[ridge regression]] is a [[linear model]] with features $X \in \mathbb{R}^{n \times d}$ and parameters $\theta \in \mathbb{R}^d$ and [[white noise#gaussian white noise|gaussian white noise]] $\epsilon\sim \mathcal{N}(0, I\sigma^2)$
- the training is done with regularization term that penalizes the $L2$ [[norm]] of the parameters $\theta$ with a regularization factor $\lambda$

$$
\begin{split}
Y 
&= X \theta + \epsilon \\
\end{split}
$$

$$
\begin{split}
\hat\theta_\mathrm{ridge} 
&= arg \min_\theta ||Y - X\theta||^2 + \lambda ||\theta||^2_2 \\
&= \left(X^\top X + \lambda I\right)^{-1}X^\top Y \\
\end{split}
$$



$$
\begin{split}
&D||Y - X\theta||^2(\theta)^\top 
= A^\top\left(X\theta -Y\right) = 0 \\
\Rightarrow&\theta= \left(X^\top X\right)^{-1}X^\top Y
\end{split}
$$

$$
\begin{split}
\mathbb{E}[\hat\theta] 
&= \left(X^\top X\right)^{-1}X^\top \mathbb{E}[Y] \\
&= \left(X^\top X\right)^{-1}X^\top Y\theta \\
&= \theta \\
\end{split}
$$


### ridge regression and bayesian inference
- [[ridge regression]] is equivalent to [[maximum aposteriori]] with a linear model and prior with a [[normal distribution]]
- the regularization term $\lambda=\frac{\sigma^2}{\tau^2}$ is equal to the ratio of the [[variance]] of the [[white noise]] $\epsilon\sim \mathcal{N}(0, I\sigma^2)$ and the prior $p(\theta) \sim \mathcal{N}(0, I\tau^2)$

![[maximum aposteriori#maximum aposteriori]]
# -----------

![[linear model#linear model]]

![[linear model#training of a linear model]]