### ridge regression
- [[ridge regression]] is a [[linear model]] with features $X \in \mathbb{R}^{n \times d}$ and parameters $\theta \in \mathbb{R}^d$ and [[white noise#gaussian white noise|gaussian white noise]] $\epsilon\sim \mathcal{N}(0, I\sigma^2)$
- in other words: [[ordinary least square estimator]] with a regularization
- the training is done with regularization term that penalizes the $L2$ [[norm]] of the parameters $\theta$ with a regularization factor $\lambda$
##### model
$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, I\sigma^2) \\
\end{split}
$$

##### objective function

$$
\begin{split}
\hat\theta_\mathrm{ridge} 
&= arg \min_\theta \frac{1}{n} ||Y - X\theta||^2 + \lambda ||\theta||^2_2 \\
\end{split}
$$
##### solution

- non centered empirical [[empirical covariance]] $\hat\Sigma$ with the [[scalar product]] $\langle a, b\rangle_\hat\Sigma=a^\top\hat\Sigma b$ and the [[norm]]$|| a||_\hat\Sigma^2 =a^\top\hat\Sigma b$ 

$$
\hat\Sigma = \frac{1}{n} X^\top X
$$

$$
\begin{split}
\nabla\left(\frac{1}{n}||Y - X\theta||^2 + \lambda ||\theta||^2_2 \right) 
&= \frac{2}{n} X^\top\left(X\theta -Y\right) + 2\lambda \theta  = 0 \\
0 &= \frac{1}{n} X^\top X\theta - \frac{1}{n} X^\top Y + \lambda \theta \\
\frac{1}{n}X^\top Y&=\left(\frac{1}{n}X^\top X + \lambda I \right)\theta  \\
\Rightarrow\theta_\mathrm{ridge} 
&=\frac{1}{n}\left(\frac{1}{n}X^\top X + \lambda I \right)^{-1}X^\top Y \\
&=\left(X^\top X + n \lambda I \right)^{-1}X^\top Y \\
&=\frac{1}{n}\left(\hat\Sigma + \lambda I \right)^{-1}X^\top Y \\
\end{split}
$$

##### expectation

$$
\begin{split}
\mathbb{E}\left[\theta_\mathrm{ridge}\right] 
&= \frac{1}{n}\left(\hat\Sigma + \lambda I \right)^{-1} X^\top \mathbb{E}[Y] \\
&= \frac{1}{n}\left(\hat\Sigma + \lambda I \right)^{-1}X^\top  X \theta\\
&= \left(\hat\Sigma + \lambda I \right)^{-1}\hat\Sigma \theta\\
&= \theta - \lambda \left(\hat\Sigma + \lambda I \right)^{-1}\theta\\
\end{split}
$$

##### variance
$$
\begin{split}
\mathbb{VAR}\left[ \theta_\mathrm{ridge}\right] 
&=\mathbb{E}\left[\left(\theta_\mathrm{ridge}-\mathbb{E}\left[\theta_\mathrm{ridge}\right]\right)\left(\theta_\mathrm{ridge}-\mathbb{E}\left[\theta_\mathrm{ridge}\right]\right)^\top\right] \\
&=\mathbb{E}\left[\frac{1}{n^2}\left(\hat\Sigma + \lambda I \right)^{-1} X^\top \left(Y-\mathbb{E}\left[Y\right]\right)\left(Y-\mathbb{E}\left[Y\right]\right)^\top X\left(\hat\Sigma + \lambda I \right)^{-1} \right] \\
&=\mathbb{E}\left[\frac{1}{n^2}\left(\hat\Sigma + \lambda I \right)^{-1} X^\top \mathbb{VAR}[Y] X\left(\hat\Sigma + \lambda I \right)^{-1} \right] \\
&=\frac{1}{n^2}\left(\hat\Sigma + \lambda I \right)^{-1} X^\top I \sigma^2 X\left(\hat\Sigma + \lambda I \right)^{-1}  \\
&=\frac{\sigma^2}{n^2}\left(\hat\Sigma + \lambda I \right)^{-1} X^\top  X\left(\hat\Sigma + \lambda I \right)^{-1}  \\
&=\frac{\sigma^2}{n}\left(\hat\Sigma + \lambda I \right)^{-1} \hat\Sigma\left(\hat\Sigma + \lambda I \right)^{-1}  \\
\end{split}
$$

#### risk
- from the [[ordinary least square estimator]] we know that that the excess [[risk]] is given by the following
- note: since the model of the [[ridge regression]] and the [[ordinary least square estimator]] is identical the calculation of the excess risk and bias variance decomposition are the same

$$
\begin{split}
\mathbb{E}\left[ \mathcal{R\left(\theta_\mathrm{ridge}\right)} \right] - \mathcal{R^*} 
&=  \mathbb{E}\left[ || \theta^* -   \theta_\mathrm{ridge}||^2_\hat\Sigma \right]   \\
&=   ||  \mathbb{E}\left[\theta_\mathrm{ridge}\right] - \theta^* ||^2_\hat\Sigma  + \mathbb{E}\left[ ||\mathbb{E}\left[\theta_\mathrm{ridge}\right] -   \theta_\mathrm{ridge}||^2_\hat\Sigma \right]  \\
&=  \lambda^2   \theta^{*\top}\left(\hat\Sigma + \lambda I \right)^{-2}  \hat\Sigma \theta^*   + \frac{\sigma^2}{n} \mathrm{TR}\left(\hat\Sigma^2\left(\hat\Sigma + \lambda I \right)^{-2} \right)  \\
\end{split}
$$

- in a fixed design setting the [[bias]] contribution to the error can be expressed as follows

$$
\begin{split}
|| \theta^* - \mathbb{E}\left[\theta_\mathrm{ridge}\right] ||^2_\hat\Sigma
&= \left|\left|\theta^* + \lambda \left(\hat\Sigma + \lambda I \right)^{-1}\theta^* - \theta^* \right|\right|^2_\hat\Sigma \\
&= \left|\left| \lambda \left(\hat\Sigma + \lambda I \right)^{-1}\theta^* \right|\right|^2_\hat\Sigma \\
&= \lambda^2   \left(\left(\hat\Sigma + \lambda I \right)^{-1}\theta^* \right)^\top \hat\Sigma \left(\hat\Sigma + \lambda I \right)^{-1}\theta^*  \\
&= \lambda^2   \theta^{*\top}\left(\hat\Sigma + \lambda I \right)^{-\top}  \hat\Sigma \left(\hat\Sigma + \lambda I \right)^{-1}\theta^*  \\
&= \lambda^2   \theta^{*\top}\left(\hat\Sigma + \lambda I \right)^{-1}  \hat\Sigma \left(\hat\Sigma + \lambda I \right)^{-1}\theta^*  \\
&= \lambda^2   \theta^{*\top}\left(\hat\Sigma + \lambda I \right)^{-2}  \hat\Sigma \theta^*  \\
&= \lambda^2   \theta^{*\top}\left(\hat\Sigma + \lambda I \right)^{-2}  \hat\Sigma \theta^*  \\
\end{split}
$$

- with the following [[variance]] contribution to the excess risk

$$
\begin{split}
\mathbb{E}\left[ ||\mathbb{E}\left[\theta_\mathrm{ridge}\right] -   \theta_\mathrm{ridge}||^2_\hat\Sigma \right] 
&= \mathbb{E}\left[ \left(\mathbb{E}\left[\theta_\mathrm{ridge}\right] -   \theta_\mathrm{ridge}\right)^\top \hat\Sigma \mathbb{E}\left[\theta_\mathrm{ridge}\right] -   \theta_\mathrm{ridge} \right]   \\
&= \mathrm{TR}\left(\mathbb{E}\left[ \left(\mathbb{E}\left[\theta_\mathrm{ridge}\right] -   \theta_\mathrm{ridge}\right)^\top \hat\Sigma \mathbb{E}\left[\theta_\mathrm{ridge}\right] -   \theta_\mathrm{ridge} \right]\right)   \\
&= \mathrm{TR}\left(\hat\Sigma\mathbb{E}\left[ \mathbb{E}\left[\theta_\mathrm{ridge}\right] -   \theta_\mathrm{ridge} \left(\mathbb{E}\left[\theta_\mathrm{ridge}\right] -   \theta_\mathrm{ridge}\right)^\top   \right]\right)   \\
&= \mathrm{TR}\left(\hat\Sigma\mathbb{VAR}\left[\theta_\mathrm{ridge}\right]\right)   \\
&= \frac{\sigma^2}{n} \mathrm{TR}\left(\hat\Sigma\left(\hat\Sigma + \lambda I \right)^{-1} \hat\Sigma\left(\hat\Sigma + \lambda I \right)^{-1}\right)   \\
&= \frac{\sigma^2}{n} \mathrm{TR}\left(\hat\Sigma^2\left(\hat\Sigma + \lambda I \right)^{-2} \right)   \\
\end{split}
$$


### ridge regression and bayesian inference
- [[ridge regression]] is equivalent to [[maximum aposteriori]] with a linear model and prior with a [[normal distribution]]
- the regularization term $\lambda=\frac{\sigma^2}{\tau^2}$ is equal to the ratio of the [[variance]] of the [[white noise]] $\epsilon\sim \mathcal{N}(0, I\sigma^2)$ and the prior $p(\theta) \sim \mathcal{N}(0, I\tau^2)$

![[maximum aposteriori#maximum aposteriori]]
# -----------

![[ordinary least square estimator#ordinary least square estimator]]

![[linear model#linear model]]




# anki

START
Basic
[[ridge regression]]
- definition
- objective function + solution with calculation
- solution based on $\hat\Sigma$
- relationship to [[maximum aposteriori]] without proof


- non centered empirical [[empirical covariance]] $\hat\Sigma$ with the [[scalar product]] $\langle a, b\rangle_\hat\Sigma=a^\top\hat\Sigma b$ and the [[norm]]$|| a||_\hat\Sigma^2 =a^\top\hat\Sigma b$ 

$$
\hat\Sigma = \frac{1}{n} X^\top X
$$

Back: 
### ridge regression
- [[ridge regression]] is a [[linear model]] with features $X \in \mathbb{R}^{n \times d}$ and parameters $\theta \in \mathbb{R}^d$ and [[white noise#gaussian white noise|gaussian white noise]] $\epsilon\sim \mathcal{N}(0, I\sigma^2)$
- in other words: [[ordinary least square estimator]] with a regularization
- the training is done with regularization term that penalizes the $L2$ [[norm]] of the parameters $\theta$ with a regularization factor $\lambda$
##### model
$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, I\sigma^2) \\
\end{split}
$$

##### objective function

$$
\begin{split}
\hat\theta_\mathrm{ridge} 
&= arg \min_\theta \frac{1}{n} ||Y - X\theta||^2 + \lambda ||\theta||^2_2 \\
\end{split}
$$
##### solution

- non centered empirical [[empirical covariance]] $\hat\Sigma$ with the [[scalar product]] $\langle a, b\rangle_\hat\Sigma=a^\top\hat\Sigma b$ and the [[norm]]$|| a||_\hat\Sigma^2 =a^\top\hat\Sigma b$ 

$$
\hat\Sigma = \frac{1}{n} X^\top X
$$

$$
\begin{split}
\nabla\left(\frac{1}{n}||Y - X\theta||^2 + \lambda ||\theta||^2_2 \right) 
&= \frac{2}{n} X^\top\left(X\theta -Y\right) + 2\lambda \theta  = 0 \\
0 &= \frac{1}{n} X^\top X\theta - \frac{1}{n} X^\top Y + \lambda \theta \\
\frac{1}{n}X^\top Y&=\left(\frac{1}{n}X^\top X + \lambda I \right)\theta  \\
\Rightarrow\theta_\mathrm{ridge} 
&=\frac{1}{n}\left(\frac{1}{n}X^\top X + \lambda I \right)^{-1}X^\top Y \\
&=\left(X^\top X + n \lambda I \right)^{-1}X^\top Y \\
&=\frac{1}{n}\left(\hat\Sigma + \lambda I \right)^{-1}X^\top Y \\
\end{split}
$$

### ridge regression and bayesian inference
- [[ridge regression]] is equivalent to [[maximum aposteriori]] with a linear model and prior with a [[normal distribution]]
- the regularization term $\lambda=\frac{\sigma^2}{\tau^2}$ is equal to the ratio of the [[variance]] of the [[white noise]] $\epsilon\sim \mathcal{N}(0, I\sigma^2)$ and the prior $p(\theta) \sim \mathcal{N}(0, I\tau^2)$

### maximum aposteriori
- [[bayesian inference]] given a [[empirical distribution of a dataset|dataset]] $\mathcal{D}$ with a [[probability density function (PDF)]] $f(\theta)$ and a model $\theta$ with a prior assumed distribution $f(\theta)$
- the model can be trained by maximizing the posterior $f\left(\theta \mid \mathcal{D}\right)$

$$
\overbrace{f\left(\theta \mid \mathcal{D}\right)}^\text{posterior}
= \frac{
\overbrace{f\left(\mathcal{D} \mid \theta\right)}^\text{likelihood}
\overbrace{f\left(\theta\right)}^\text{prior}
}
{
P(\mathcal{D})
}
$$
- for the [[maximum aposteriori]] estimation we have the following
- this works because 
	- we can assume the features $X$ to be constant and thus treat them as given
	- the [[logarithm]] is a [[monotonic function]] and thus does not change the argmax
	- the distribution of the data does not depend on the parameters

$$
\begin{split}
\theta_{MAP} 
&= arg\max_\theta f\left(\theta \mid \mathcal{D}\right) \\
&= arg\max_\theta \frac{f\left(\mathcal{D} \mid \theta\right)f\left(\theta\right)}{P(\mathcal{D})} \\
&= arg\max_\theta f\left(\mathcal{D} \mid \theta\right)f\left(\theta\right) \\
&= arg\max_\theta \log{ f\left(\mathcal{D} \mid \theta\right)f\left(\theta\right)} \\
&= arg\max_\theta \log{ f\left(\mathcal{D} \mid \theta\right)}+\log{f\left(\theta\right)} \\
&= arg\max_\theta \log{ f\left(Y \mid \theta, X\right)}+\log{f\left(\theta\right)} \\
\end{split}
$$

#### example gaussian prior with linear model
- let $\theta$ be a [[linear model]] with [[white noise]] $\epsilon \in \mathcal{N}(0, \sigma^2)$ with a dataset $\mathcal{D}=\{(x_1, y_1), ..., (x_n, y_n)\}$

$$
\begin{split}
Y &=  X^\top\theta + \epsilon \sim \mathcal{N}(X^\top\theta, \sigma^2) \\
y_i &=  x_i^\top\theta + \epsilon_i \sim \mathcal{N}(x_i^\top\theta, \sigma^2) \\
\end{split}
$$

- the [[likelihood function]] looks like the following:

$$
\begin{split}
f\left(\mathcal{D} \mid \theta\right) 
&= f\left(Y \mid X, \theta\right)  \\
&= \prod_{i = 1}^n f(y_i| x_i, \theta) \\
&= \prod_{i = 1}^n \frac{1}{\sqrt{2\pi \sigma^2}} \exp\left({\frac{-1}{2\sigma^2} \left(y_i-x_i^\top\theta \right)^2} \right) \\
\end{split}
$$

- The **prior** over the parameters is a multivariate [[normal distribution]] with a [[covariance matrix]] $\tau^2 I \in \mathbb{R}^{d \times d}$ and a mean $\mu=0$

$$
\theta \sim \mathcal{N}(0, \tau^2 I)
$$

This has the density:

$$
\begin{split}
f(\theta) 
&= \frac{1}{(2\pi)^{d/2} |\tau^2 I|^{1/2}} \exp\left(-\frac{1}{2} \theta^\top (\tau^2 I)^{-1} \theta\right) \\
&= \prod_{j=1}^d \frac{1}{\sqrt{2\pi \tau^2}} \exp\left(-\frac{\theta_j^2}{2\tau^2}\right)
\end{split}
$$

- with the regularization parameter $\lambda=\frac{\sigma^2}{\tau^2}$ we get the following for the [[maximum aposteriori]] estimation with is equal to the [[ridge regression]]

$$
\begin{split}
\theta_\mathrm{MAP} 
&= arg\max_\theta \log{ f\left(\mathcal{D} \mid \theta\right)}+\log{f\left(\theta\right)} \\
&= arg\min_\theta \frac{1}{\sigma^2} \sum_{i = 1}^n { \left(y_i-x_i^\top\theta \right)^2} + \frac{1}{\tau^2} \sum_{j=1}^d  \theta_j^2 \\
&= arg\min_\theta  \sum_{i = 1}^n { \left(y_i-x_i^\top\theta \right)^2} + \lambda \sum_{j=1}^d  \theta_j^2 \\
&= arg\min_\theta  \mathrm{MSE}(\theta) + \lambda  ||\theta||^2_2 \\
\end{split}
$$

______________

### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\theta, \sigma^2}: \theta \in \mathbb{R}^{s}, v \in (0, \infty)\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(X)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\epsilon=(\epsilon_1, ..., \epsilon_n)^\top$ with $\mathbb{E}[\epsilon_i]=0$ and $\mathbb{VAR}[\epsilon_i]=\sigma^2$
- the model parameters are a positive [[scalar]] values $v$ that is a weight for the error term and real valued [[vector]] $\theta \in \mathbb{R}^s$ 
- the $\mathbb{P}_{\theta, v}$ is the [[distribution]] of $X$

$$
\begin{split}
Y 
&= X \theta + \epsilon \\
&= \sum_{j \in [S]} X_{(*, j)} \theta_j + \epsilon \\
Y_i
&= \sum_{j \in [S]} X_{(i, j)} \theta_j + \epsilon_i \\
\end{split}
$$

### training of a linear model
$$
\begin{split}
\hat\theta 
&= arg \min_\theta ||Y - X\theta||^2 \\
&= \left(X^\top X\right)^{-1}X^\top Y \\
\end{split}
$$

#### proof

$$
\begin{split}
&D||Y - X\theta||^2(\theta)^\top 
= A^\top\left(X\theta -Y\right) = 0 \\
\Rightarrow&\theta= \left(X^\top X\right)^{-1}X^\top Y
\end{split}
$$

Tags: mathematics statistics SS25
<!--ID: 1748438225419-->
END



START
Basic
[[ridge regression]]
- [[expectation]] with calculation
- [[variance]] with calculation


- non centered empirical [[empirical covariance]] $\hat\Sigma$ with the [[scalar product]] $\langle a, b\rangle_\hat\Sigma=a^\top\hat\Sigma b$ and the [[norm]]$|| a||_\hat\Sigma^2 =a^\top\hat\Sigma b$ 

$$
\hat\Sigma = \frac{1}{n} X^\top X
$$

Back: 
### ridge regression
- [[ridge regression]] is a [[linear model]] with features $X \in \mathbb{R}^{n \times d}$ and parameters $\theta \in \mathbb{R}^d$ and [[white noise#gaussian white noise|gaussian white noise]] $\epsilon\sim \mathcal{N}(0, I\sigma^2)$
- in other words: [[ordinary least square estimator]] with a regularization
- the training is done with regularization term that penalizes the $L2$ [[norm]] of the parameters $\theta$ with a regularization factor $\lambda$
##### model
$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, I\sigma^2) \\
\end{split}
$$

##### objective function

$$
\begin{split}
\hat\theta_\mathrm{ridge} 
&= arg \min_\theta \frac{1}{n} ||Y - X\theta||^2 + \lambda ||\theta||^2_2 \\
\end{split}
$$
##### solution

- non centered empirical [[empirical covariance]] $\hat\Sigma$ with the [[scalar product]] $\langle a, b\rangle_\hat\Sigma=a^\top\hat\Sigma b$ and the [[norm]]$|| a||_\hat\Sigma^2 =a^\top\hat\Sigma b$ 

$$
\hat\Sigma = \frac{1}{n} X^\top X
$$

$$
\begin{split}
\nabla\left(\frac{1}{n}||Y - X\theta||^2 + \lambda ||\theta||^2_2 \right) 
&= \frac{2}{n} X^\top\left(X\theta -Y\right) + 2\lambda \theta  = 0 \\
0 &= \frac{1}{n} X^\top X\theta - \frac{1}{n} X^\top Y + \lambda \theta \\
\frac{1}{n}X^\top Y&=\left(\frac{1}{n}X^\top X + \lambda I \right)\theta  \\
\Rightarrow\theta_\mathrm{ridge} 
&=\frac{1}{n}\left(\frac{1}{n}X^\top X + \lambda I \right)^{-1}X^\top Y \\
&=\left(X^\top X + n \lambda I \right)^{-1}X^\top Y \\
&=\frac{1}{n}\left(\hat\Sigma + \lambda I \right)^{-1}X^\top Y \\
\end{split}
$$

##### expectation

$$
\begin{split}
\mathbb{E}\left[\theta_\mathrm{ridge}\right] 
&= \frac{1}{n}\left(\hat\Sigma + \lambda I \right)^{-1} X^\top \mathbb{E}[Y] \\
&= \frac{1}{n}\left(\hat\Sigma + \lambda I \right)^{-1}X^\top  X \theta\\
&= \left(\hat\Sigma + \lambda I \right)^{-1}\hat\Sigma \theta\\
&= \theta - \lambda \left(\hat\Sigma + \lambda I \right)^{-1}\theta\\
\end{split}
$$

##### variance
$$
\begin{split}
\mathbb{VAR}\left[ \theta_\mathrm{ridge}\right] 
&=\mathbb{E}\left[\left(\theta_\mathrm{ridge}-\mathbb{E}\left[\theta_\mathrm{ridge}\right]\right)\left(\theta_\mathrm{ridge}-\mathbb{E}\left[\theta_\mathrm{ridge}\right]\right)^\top\right] \\
&=\mathbb{E}\left[\frac{1}{n^2}\left(\hat\Sigma + \lambda I \right)^{-1} X^\top \left(Y-\mathbb{E}\left[Y\right]\right)\left(Y-\mathbb{E}\left[Y\right]\right)^\top X\left(\hat\Sigma + \lambda I \right)^{-1} \right] \\
&=\mathbb{E}\left[\frac{1}{n^2}\left(\hat\Sigma + \lambda I \right)^{-1} X^\top \mathbb{VAR}[Y] X\left(\hat\Sigma + \lambda I \right)^{-1} \right] \\
&=\frac{1}{n^2}\left(\hat\Sigma + \lambda I \right)^{-1} X^\top I \sigma^2 X\left(\hat\Sigma + \lambda I \right)^{-1}  \\
&=\frac{\sigma^2}{n^2}\left(\hat\Sigma + \lambda I \right)^{-1} X^\top  X\left(\hat\Sigma + \lambda I \right)^{-1}  \\
&=\frac{\sigma^2}{n}\left(\hat\Sigma + \lambda I \right)^{-1} \hat\Sigma\left(\hat\Sigma + \lambda I \right)^{-1}  \\
\end{split}
$$


______________

### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\theta, \sigma^2}: \theta \in \mathbb{R}^{s}, v \in (0, \infty)\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(X)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\epsilon=(\epsilon_1, ..., \epsilon_n)^\top$ with $\mathbb{E}[\epsilon_i]=0$ and $\mathbb{VAR}[\epsilon_i]=\sigma^2$
- the model parameters are a positive [[scalar]] values $v$ that is a weight for the error term and real valued [[vector]] $\theta \in \mathbb{R}^s$ 
- the $\mathbb{P}_{\theta, v}$ is the [[distribution]] of $X$

$$
\begin{split}
Y 
&= X \theta + \epsilon \\
&= \sum_{j \in [S]} X_{(*, j)} \theta_j + \epsilon \\
Y_i
&= \sum_{j \in [S]} X_{(i, j)} \theta_j + \epsilon_i \\
\end{split}
$$

### training of a linear model
$$
\begin{split}
\hat\theta 
&= arg \min_\theta ||Y - X\theta||^2 \\
&= \left(X^\top X\right)^{-1}X^\top Y \\
\end{split}
$$

#### proof

$$
\begin{split}
&D||Y - X\theta||^2(\theta)^\top 
= A^\top\left(X\theta -Y\right) = 0 \\
\Rightarrow&\theta= \left(X^\top X\right)^{-1}X^\top Y
\end{split}
$$

Tags: mathematics statistics SS25
<!--ID: 1748708321773-->
END


START
Basic
[[ridge regression]]
- given the following variance and expectation
- calculate the excess [[risk]]



- non centered empirical [[empirical covariance]] $\hat\Sigma$ with the [[scalar product]] $\langle a, b\rangle_\hat\Sigma=a^\top\hat\Sigma b$ and the [[norm]]$|| a||_\hat\Sigma^2 =a^\top\hat\Sigma b$ 

$$
\hat\Sigma = \frac{1}{n} X^\top X
$$


$$
\begin{split}
\mathbb{E}\left[\theta_\mathrm{ridge}\right] 
&= \theta - \lambda \left(\hat\Sigma + \lambda I \right)^{-1}\theta\\
\end{split}
$$

$$
\begin{split}
\mathbb{VAR}\left[ \theta_\mathrm{ridge}\right] 
&=\frac{\sigma^2}{n}\left(\hat\Sigma + \lambda I \right)^{-1} \hat\Sigma\left(\hat\Sigma + \lambda I \right)^{-1}  \\
\end{split}
$$


Back: 
### ridge regression
- [[ridge regression]] is a [[linear model]] with features $X \in \mathbb{R}^{n \times d}$ and parameters $\theta \in \mathbb{R}^d$ and [[white noise#gaussian white noise|gaussian white noise]] $\epsilon\sim \mathcal{N}(0, I\sigma^2)$
- in other words: [[ordinary least square estimator]] with a regularization
- the training is done with regularization term that penalizes the $L2$ [[norm]] of the parameters $\theta$ with a regularization factor $\lambda$
##### model
$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, I\sigma^2) \\
\end{split}
$$

##### objective function

$$
\begin{split}
\hat\theta_\mathrm{ridge} 
&= arg \min_\theta \frac{1}{n} ||Y - X\theta||^2 + \lambda ||\theta||^2_2 \\
\end{split}
$$
##### solution

- non centered empirical [[empirical covariance]] $\hat\Sigma$ with the [[scalar product]] $\langle a, b\rangle_\hat\Sigma=a^\top\hat\Sigma b$ and the [[norm]]$|| a||_\hat\Sigma^2 =a^\top\hat\Sigma b$ 

$$
\hat\Sigma = \frac{1}{n} X^\top X
$$

$$
\begin{split}
\nabla\left(\frac{1}{n}||Y - X\theta||^2 + \lambda ||\theta||^2_2 \right) 
&= \frac{2}{n} X^\top\left(X\theta -Y\right) + 2\lambda \theta  = 0 \\
0 &= \frac{1}{n} X^\top X\theta - \frac{1}{n} X^\top Y + \lambda \theta \\
\frac{1}{n}X^\top Y&=\left(\frac{1}{n}X^\top X + \lambda I \right)\theta  \\
\Rightarrow\theta_\mathrm{ridge} 
&=\frac{1}{n}\left(\frac{1}{n}X^\top X + \lambda I \right)^{-1}X^\top Y \\
&=\left(X^\top X + n \lambda I \right)^{-1}X^\top Y \\
&=\frac{1}{n}\left(\hat\Sigma + \lambda I \right)^{-1}X^\top Y \\
\end{split}
$$

##### expectation

$$
\begin{split}
\mathbb{E}\left[\theta_\mathrm{ridge}\right] 
&= \frac{1}{n}\left(\hat\Sigma + \lambda I \right)^{-1} X^\top \mathbb{E}[Y] \\
&= \frac{1}{n}\left(\hat\Sigma + \lambda I \right)^{-1}X^\top  X \theta\\
&= \left(\hat\Sigma + \lambda I \right)^{-1}\hat\Sigma \theta\\
&= \theta - \lambda \left(\hat\Sigma + \lambda I \right)^{-1}\theta\\
\end{split}
$$

##### variance
$$
\begin{split}
\mathbb{VAR}\left[ \theta_\mathrm{ridge}\right] 
&=\mathbb{E}\left[\left(\theta_\mathrm{ridge}-\mathbb{E}\left[\theta_\mathrm{ridge}\right]\right)\left(\theta_\mathrm{ridge}-\mathbb{E}\left[\theta_\mathrm{ridge}\right]\right)^\top\right] \\
&=\mathbb{E}\left[\frac{1}{n^2}\left(\hat\Sigma + \lambda I \right)^{-1} X^\top \left(Y-\mathbb{E}\left[Y\right]\right)\left(Y-\mathbb{E}\left[Y\right]\right)^\top X\left(\hat\Sigma + \lambda I \right)^{-1} \right] \\
&=\mathbb{E}\left[\frac{1}{n^2}\left(\hat\Sigma + \lambda I \right)^{-1} X^\top \mathbb{VAR}[Y] X\left(\hat\Sigma + \lambda I \right)^{-1} \right] \\
&=\frac{1}{n^2}\left(\hat\Sigma + \lambda I \right)^{-1} X^\top I \sigma^2 X\left(\hat\Sigma + \lambda I \right)^{-1}  \\
&=\frac{\sigma^2}{n^2}\left(\hat\Sigma + \lambda I \right)^{-1} X^\top  X\left(\hat\Sigma + \lambda I \right)^{-1}  \\
&=\frac{\sigma^2}{n}\left(\hat\Sigma + \lambda I \right)^{-1} \hat\Sigma\left(\hat\Sigma + \lambda I \right)^{-1}  \\
\end{split}
$$

#### risk
- from the [[ordinary least square estimator]] we know that that the excess [[risk]] is given by the following
- note: since the model of the [[ridge regression]] and the [[ordinary least square estimator]] is identical the calculation of the excess risk and bias variance decomposition are the same

$$
\begin{split}
\mathbb{E}\left[ \mathcal{R\left(\theta_\mathrm{ridge}\right)} \right] - \mathcal{R^*} 
&=  \mathbb{E}\left[ || \theta^* -   \theta_\mathrm{ridge}||^2_\hat\Sigma \right]   \\
&=   ||  \mathbb{E}\left[\theta_\mathrm{ridge}\right] - \theta^* ||^2_\hat\Sigma  + \mathbb{E}\left[ ||\mathbb{E}\left[\theta_\mathrm{ridge}\right] -   \theta_\mathrm{ridge}||^2_\hat\Sigma \right]  \\
&=  \lambda^2   \theta^{*\top}\left(\hat\Sigma + \lambda I \right)^{-2}  \hat\Sigma \theta^*   + \frac{\sigma^2}{n} \mathrm{TR}\left(\hat\Sigma^2\left(\hat\Sigma + \lambda I \right)^{-2} \right)  \\
\end{split}
$$

- in a fixed design setting the [[bias]] contribution to the error can be expressed as follows

$$
\begin{split}
|| \theta^* - \mathbb{E}\left[\theta_\mathrm{ridge}\right] ||^2_\hat\Sigma
&= \left|\left|\theta^* + \lambda \left(\hat\Sigma + \lambda I \right)^{-1}\theta^* - \theta^* \right|\right|^2_\hat\Sigma \\
&= \left|\left| \lambda \left(\hat\Sigma + \lambda I \right)^{-1}\theta^* \right|\right|^2_\hat\Sigma \\
&= \lambda^2   \left(\left(\hat\Sigma + \lambda I \right)^{-1}\theta^* \right)^\top \hat\Sigma \left(\hat\Sigma + \lambda I \right)^{-1}\theta^*  \\
&= \lambda^2   \theta^{*\top}\left(\hat\Sigma + \lambda I \right)^{-\top}  \hat\Sigma \left(\hat\Sigma + \lambda I \right)^{-1}\theta^*  \\
&= \lambda^2   \theta^{*\top}\left(\hat\Sigma + \lambda I \right)^{-1}  \hat\Sigma \left(\hat\Sigma + \lambda I \right)^{-1}\theta^*  \\
&= \lambda^2   \theta^{*\top}\left(\hat\Sigma + \lambda I \right)^{-2}  \hat\Sigma \theta^*  \\
&= \lambda^2   \theta^{*\top}\left(\hat\Sigma + \lambda I \right)^{-2}  \hat\Sigma \theta^*  \\
\end{split}
$$

- with the following [[variance]] contribution to the excess risk

$$
\begin{split}
\mathbb{E}\left[ ||\mathbb{E}\left[\theta_\mathrm{ridge}\right] -   \theta_\mathrm{ridge}||^2_\hat\Sigma \right] 
&= \mathbb{E}\left[ \left(\mathbb{E}\left[\theta_\mathrm{ridge}\right] -   \theta_\mathrm{ridge}\right)^\top \hat\Sigma \mathbb{E}\left[\theta_\mathrm{ridge}\right] -   \theta_\mathrm{ridge} \right]   \\
&= \mathrm{TR}\left(\mathbb{E}\left[ \left(\mathbb{E}\left[\theta_\mathrm{ridge}\right] -   \theta_\mathrm{ridge}\right)^\top \hat\Sigma \mathbb{E}\left[\theta_\mathrm{ridge}\right] -   \theta_\mathrm{ridge} \right]\right)   \\
&= \mathrm{TR}\left(\hat\Sigma\mathbb{E}\left[ \mathbb{E}\left[\theta_\mathrm{ridge}\right] -   \theta_\mathrm{ridge} \left(\mathbb{E}\left[\theta_\mathrm{ridge}\right] -   \theta_\mathrm{ridge}\right)^\top   \right]\right)   \\
&= \mathrm{TR}\left(\hat\Sigma\mathbb{VAR}\left[\theta_\mathrm{ridge}\right]\right)   \\
&= \frac{\sigma^2}{n} \mathrm{TR}\left(\hat\Sigma\left(\hat\Sigma + \lambda I \right)^{-1} \hat\Sigma\left(\hat\Sigma + \lambda I \right)^{-1}\right)   \\
&= \frac{\sigma^2}{n} \mathrm{TR}\left(\hat\Sigma^2\left(\hat\Sigma + \lambda I \right)^{-2} \right)   \\
\end{split}
$$


______________

### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\theta, \sigma^2}: \theta \in \mathbb{R}^{s}, v \in (0, \infty)\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(X)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\epsilon=(\epsilon_1, ..., \epsilon_n)^\top$ with $\mathbb{E}[\epsilon_i]=0$ and $\mathbb{VAR}[\epsilon_i]=\sigma^2$
- the model parameters are a positive [[scalar]] values $v$ that is a weight for the error term and real valued [[vector]] $\theta \in \mathbb{R}^s$ 
- the $\mathbb{P}_{\theta, v}$ is the [[distribution]] of $X$

$$
\begin{split}
Y 
&= X \theta + \epsilon \\
&= \sum_{j \in [S]} X_{(*, j)} \theta_j + \epsilon \\
Y_i
&= \sum_{j \in [S]} X_{(i, j)} \theta_j + \epsilon_i \\
\end{split}
$$

### training of a linear model
$$
\begin{split}
\hat\theta 
&= arg \min_\theta ||Y - X\theta||^2 \\
&= \left(X^\top X\right)^{-1}X^\top Y \\
\end{split}
$$

#### proof

$$
\begin{split}
&D||Y - X\theta||^2(\theta)^\top 
= A^\top\left(X\theta -Y\right) = 0 \\
\Rightarrow&\theta= \left(X^\top X\right)^{-1}X^\top Y
\end{split}
$$

Tags: mathematics statistics SS25
<!--ID: 1748708321779-->
END