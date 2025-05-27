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

# ---------

![[linear model#linear model]]

![[empirical distribution of a dataset#empirical distribution of a dataset]]

![[maximum likelihood estimator#calculation of the maximum likelihood estimator]]

![[bayesian inference#Single Bayesian Update]]

![[bayes theorem#bayes theorem]]


# anki

START
Basic
[[maximum aposteriori]] estimator
- definition
- interpretation

Back: 
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

_________________


### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\gamma, v}: \gamma \in \mathbb{R}^{s}, v \in (0, \infty)\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(A)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\xi=(\xi_1, ..., \xi_n)^\top$ with $\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$
- the model parameters are a positive [[scalar]] values $v$ that is a weight for the error term and real valued [[vector]] $\gamma \in \mathbb{R}^s$ 
- the $\mathbb{P}_{\gamma, v}$ is the [[distribution]] of $X$

$$
\begin{split}
X 
&= A \gamma + \sqrt{v} \xi \\
&= \sum_{j \in [S]} A_{(*, j)} \gamma_j + \sqrt{v} \xi \\
X_i
&= \sum_{j \in [S]} A_{(i, j)} \gamma_j + \sqrt{v} \xi_i \\
\end{split}
$$

### Bayesian interference

For a [[partitioned sample space]] $\{B_i \mid i = 1,2...,k\}$ and general [[event space|event]] $A$ the [[bayes theorem]] states the following.
$$
P\left(B_i \mid A\right) 
= \frac{
\overbrace{P\left(A \mid B_i\right)}^\text{likelihood}
\overbrace{P\left(B_i\right)}^\text{prior}
}
{
\underbrace{\sum\limits_{j=1}^k P\left(A \mid B_j\right)P\left(B_j\right)}_{P(A)}
}
$$
We are interested in the [[probability]] of [[event]] $B_i$, and we have a prior [[hypothesis]] $P(B_i)$. Then we observe the occurrence of and [[stochastic independent|dependent]] [[event]] $A$, and we want to update our [[hypothesis]]. For this we need the [[likelihood function]] that [[event]] $A$ happened under the assumption that $B_i$ is true and divide it by the [[probability]] of the observed [[event]] $A$. The [[partitioned sample space]] $\{B_i \mid i = 1,2...,k\}$ is still normalized $\left(\sum P(B_i) = 1 \right)$.  


Tags: mathematics statistics SS25
<!--ID: 1748356498013-->
END


START
Basic
- let $\theta$ be a [[linear model]] with [[white noise]] $\epsilon \in \mathcal{N}(0, \sigma^2)$ with a dataset $\mathcal{D}=\{(x_1, y_1), ..., (x_n, y_n)\}$
- calculate the [[maximum aposteriori]] estimator
- how is this called?

Back: 

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

_________________

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

### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\gamma, v}: \gamma \in \mathbb{R}^{s}, v \in (0, \infty)\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(A)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\xi=(\xi_1, ..., \xi_n)^\top$ with $\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$
- the model parameters are a positive [[scalar]] values $v$ that is a weight for the error term and real valued [[vector]] $\gamma \in \mathbb{R}^s$ 
- the $\mathbb{P}_{\gamma, v}$ is the [[distribution]] of $X$

$$
\begin{split}
X 
&= A \gamma + \sqrt{v} \xi \\
&= \sum_{j \in [S]} A_{(*, j)} \gamma_j + \sqrt{v} \xi \\
X_i
&= \sum_{j \in [S]} A_{(i, j)} \gamma_j + \sqrt{v} \xi_i \\
\end{split}
$$

### Bayesian interference

For a [[partitioned sample space]] $\{B_i \mid i = 1,2...,k\}$ and general [[event space|event]] $A$ the [[bayes theorem]] states the following.
$$
P\left(B_i \mid A\right) 
= \frac{
\overbrace{P\left(A \mid B_i\right)}^\text{likelihood}
\overbrace{P\left(B_i\right)}^\text{prior}
}
{
\underbrace{\sum\limits_{j=1}^k P\left(A \mid B_j\right)P\left(B_j\right)}_{P(A)}
}
$$
We are interested in the [[probability]] of [[event]] $B_i$, and we have a prior [[hypothesis]] $P(B_i)$. Then we observe the occurrence of and [[stochastic independent|dependent]] [[event]] $A$, and we want to update our [[hypothesis]]. For this we need the [[likelihood function]] that [[event]] $A$ happened under the assumption that $B_i$ is true and divide it by the [[probability]] of the observed [[event]] $A$. The [[partitioned sample space]] $\{B_i \mid i = 1,2...,k\}$ is still normalized $\left(\sum P(B_i) = 1 \right)$.  


Tags: mathematics statistics SS25
<!--ID: 1748356498017-->
END