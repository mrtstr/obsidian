### hierarchical model
- [[probabilistic model]] that use internally multiple [[distribution]] 
- given the following model with a [[hyperparameter]] $\lambda$ 

$$
(X, \theta) \sim \mathcal{M}(\lambda)
$$

- $\mathcal{M}$ can internally consist of multiple probability laws - one that models the distribution of the parameters $\theta$ and one that models the input as a [[random variable]] $X$

$$
\begin{split}
\theta &\sim L(.\mid\lambda) \\
X &\sim L_X(.\mid\theta) \\
\end{split}
$$

##### example

$$
\begin{split}
\theta &\sim \mathcal{N}(0, \lambda) \\
X &\sim \mathcal{N}(\theta, \sigma^2) \\
\end{split}
$$

- this is equivalent to the following structural equation which models the observed [[random variable]] $X$ as a combination of a dependent component $\theta$ and an [[stochastic independent]] component $\epsilon$ often [[white noise]]

$$
\begin{split}
X = \theta + \epsilon, \epsilon &\sim \mathcal{N}(\theta, \sigma^2) \\
\end{split}
$$


# -----------------
![[probabilistic model#probabilistic model]]
# anki


START
Basic
[[hierarchical model]]
- definition
- example

Back: 
### hierarchical models
- [[probabilistic model]] that use internally multiple [[distribution]] 
- given the following model with a [[hyperparameter]] $\lambda$ 

$$
(X, \theta) \sim \mathcal{M}(\lambda)
$$

- $\mathcal{M}$ can internally consist of multiple probability laws - one that models the distribution of the parameters $\theta$ and one that models the input as a [[random variable]] $X$

$$
\begin{split}
\theta &\sim L(.\mid\lambda) \\
X &\sim L_X(.\mid\theta) \\
\end{split}
$$

##### example

$$
\begin{split}
\theta &\sim \mathcal{N}(0, \lambda) \\
X &\sim \mathcal{N}(\theta, \sigma^2) \\
\end{split}
$$

- this is equivalent to the following structural equation which models the observed [[random variable]] $X$ as a combination of a dependent component $\theta$ and an [[stochastic independent]] component $\epsilon$ often [[white noise]]

$$
\begin{split}
X = \theta + \epsilon, \epsilon &\sim \mathcal{N}(\theta, \sigma^2) \\
\end{split}
$$

___________

### probabilistic model
- a [[probabilistic model]] models the [[distribution]] of output [[random variable]] $Y$

##### input $X$ and the output $Y$ is random
- assumes that both input $X$ and the output $Y$ and [[random variable]] with a [[joint distribution]] $P(Y, X)$ which is approximated
- for example joint gaussian models there the full model models $P(X, Y)$ but $P(Y \mid X)$ is derived, naive bayes, or some generative models
##### only $Y$ is random
- $X$ is assumed to be fixed/observed then 
- usually the [[conditional probability]] $P(Y|X)$ is modeled
- examples: [[neural networks]] with [[softmax]], [[logistic regession]] 

##### bayesian: $Y$ and the parameters are random
- [[bayesian inference]]: used in the [[maximum aposteriori]] estimator where $f\left(\theta \mid \mathcal{D}\right)=f\left(\theta \mid X, Y\right)$ and $f\left(Y \mid X, \theta\right)$ are modeled


Tags: mathematics statistics SS25
<!--ID: 1752652160588-->
END
