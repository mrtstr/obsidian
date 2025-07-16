### maximum aposteriori
- [[bayesian inference]] given a [[empirical distribution of a dataset|dataset]] $\mathcal{D}$ with a [[probability density function (PDF)]] $f(\theta)$ and a model $\theta$ with a prior assumed distribution $f(\theta)$
- with a full [[bayesian inference]] approach we would model $f\left(\theta \mid \mathcal{D}\right)$ which would require to calculate $P(\mathcal{D})$ which is often not possible
- with the [[maximum aposteriori]] approach we train the model by maximizing the posterior $f\left(\theta \mid \mathcal{D}\right)$

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

### advantages against the MLE
- [[maximum aposteriori]] is like a [[regularization|regularized]] version of the [[maximum likelihood estimator]]
- the prior can be seen as a [[regularization]] which prevents [[overfitting]]
- the smaller the [[variance]] of the chosen prior [[distribution]] the stronger the effect
- this especially important for high dimensional problems which are prone to [[overfitting]]
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

![[bayesian inference#bayesian inference]]

![[bayes theorem#bayes theorem]]


# anki

START
Basic
[[maximum aposteriori]]
- difference to [[bayesian inference]]
- difference to the [[maximum likelihood estimator]]

Back: 
### advantages against the MLE
- [[maximum aposteriori]] is like a [[regularization|regularized]] version of the [[maximum likelihood estimator]]
- the prior can be seen as a [[regularization]] which prevents [[overfitting]]
- the smaller the [[variance]] of the chosen prior [[distribution]] the stronger the effect
- this especially important for high dimensional problems which are prone to [[overfitting]]

### maximum aposteriori
- [[bayesian inference]] given a [[empirical distribution of a dataset|dataset]] $\mathcal{D}$ with a [[probability density function (PDF)]] $f(\theta)$ and a model $\theta$ with a prior assumed distribution $f(\theta)$
- with a full [[bayesian inference]] approach we would model $f\left(\theta \mid \mathcal{D}\right)$ which would require to calculate $P(\mathcal{D})$ which is often not possible
- with the [[maximum aposteriori]] approach we train the model by maximizing the posterior $f\left(\theta \mid \mathcal{D}\right)$

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

### maximum likelihood estimator
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[likelihood function]] $\varrho: \mathfrak{X} \times \Theta \to (0,\infty)$  
- a [[statistical estimator]] $T: \mathfrak{X} \to \Omega$ for a [[statistics]] with a characteristics $\tau(\vartheta)=\vartheta$ for an observation $x \in \mathfrak{X}$ is called the [[maximum likelihood estimator]] if it's maximizing the [[likelihood function]]
$$
T(x) = arg\max  \varrho(x, \vartheta)
$$
- the maximum likelihood [[statistical estimator]] can be interpreted the parameter [[set]] out of the [[parameter space]] that explained the observation best


### bayesian inference
- [[hierarchical model]] that assumes that the parameters $\theta \sim P_\theta$ as well as the data $\mathcal{D}\subset \mathcal{X} \times \mathcal{Y} \sim P_\mathcal{D}(. \mid \theta)$ are [[random variable]] with a [[distribution]] 
- then the [[bayes theorem]] is used to model the [[conditional distribution]] of the parameters $p(\theta\mid \mathcal{D})$ 

$$
p(\theta\mid \mathcal{D}) = \frac{p(\mathcal{D}\mid \theta)p(\theta)}{p(\mathcal{D})}
$$
- however it is very difficult to compute the $p(\mathcal{D})$ which requires integrating out the parameter conditioning, but we still can maximize $p(\theta\mid \mathcal{D})$ in which case we can ignore $p(\mathcal{D})$ because it doesn't depend on the parameters and is just a constant which leads to the [[maximum aposteriori]] method

$$
p(\mathcal{D}) = \int p(\mathcal{D}\mid \theta)p(\theta) d\theta
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



Tags: mathematics statistics SS25
<!--ID: 1752653738325-->
END

START
Basic
[[maximum aposteriori]] estimator
- definition and difference to general [[bayesian inference]]
- interpretation

Back: 
### maximum aposteriori
- [[bayesian inference]] given a [[empirical distribution of a dataset|dataset]] $\mathcal{D}$ with a [[probability density function (PDF)]] $f(\theta)$ and a model $\theta$ with a prior assumed distribution $f(\theta)$
- with a full [[bayesian inference]] approach we would model $f\left(\theta \mid \mathcal{D}\right)$ which would require to calculate $P(\mathcal{D})$ which is often not possible
- with the [[maximum aposteriori]] approach we train the model by maximizing the posterior $f\left(\theta \mid \mathcal{D}\right)$

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

### bayesian inference
- [[hierarchical model]] that assumes that the parameters $\theta \sim P_\theta$ as well as the data $\mathcal{D}\subset \mathcal{X} \times \mathcal{Y} \sim P_\mathcal{D}(. \mid \theta)$ are [[random variable]] with a [[distribution]] 
- then the [[bayes theorem]] is used to model the [[conditional distribution]] of the parameters $p(\theta\mid \mathcal{D})$ 

$$
p(\theta\mid \mathcal{D}) = \frac{p(\mathcal{D}\mid \theta)p(\theta)}{p(\mathcal{D})}
$$
- however it is very difficult to compute the $p(\mathcal{D})$ which requires integrating out the parameter conditioning, but we still can maximize $p(\theta\mid \mathcal{D})$ in which case we can ignore $p(\mathcal{D})$ because it doesn't depend on the parameters and is just a constant which leads to the [[maximum aposteriori]] method

$$
p(\mathcal{D}) = \int p(\mathcal{D}\mid \theta)p(\theta) d\theta
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
- with a full [[bayesian inference]] approach we would model $f\left(\theta \mid \mathcal{D}\right)$ which would require to calculate $P(\mathcal{D})$ which is often not possible
- with the [[maximum aposteriori]] approach we train the model by maximizing the posterior $f\left(\theta \mid \mathcal{D}\right)$

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

### bayesian inference
- [[hierarchical model]] that assumes that the parameters $\theta \sim P_\theta$ as well as the data $\mathcal{D}\subset \mathcal{X} \times \mathcal{Y} \sim P_\mathcal{D}(. \mid \theta)$ are [[random variable]] with a [[distribution]] 
- then the [[bayes theorem]] is used to model the [[conditional distribution]] of the parameters $p(\theta\mid \mathcal{D})$ 

$$
p(\theta\mid \mathcal{D}) = \frac{p(\mathcal{D}\mid \theta)p(\theta)}{p(\mathcal{D})}
$$
- however it is very difficult to compute the $p(\mathcal{D})$ which requires integrating out the parameter conditioning, but we still can maximize $p(\theta\mid \mathcal{D})$ in which case we can ignore $p(\mathcal{D})$ because it doesn't depend on the parameters and is just a constant which leads to the [[maximum aposteriori]] method

$$
p(\mathcal{D}) = \int p(\mathcal{D}\mid \theta)p(\theta) d\theta
$$


Tags: mathematics statistics SS25
<!--ID: 1748356498017-->
END