### kl divergence
- KL divergence is a measure of how much the **assumed distribution $Q$**
  diverges from the **true distribution $P$**.
#### Continuous Case

$$
D_{KL}(P \parallel Q) = \int_{\mathbb{R}} p(x) \log \left( \frac{p(x)}{q(x)} \right) dx
$$

#### Discrete Case

$$
D_{KL}(P \parallel Q) = \sum_{x \in \mathcal{X}} p(x) \log \left( \frac{p(x)}{q(x)} \right)
$$

- $D_{KL}(P \parallel Q) \in [0, \infty]$
- $D_{KL}(P \parallel Q) = 0$ if and only if $P = Q$
- $D_{KL}(P \parallel Q) = \infty$ if there exists any $x$ such that $p(x) > 0$ and $q(x) = 0$ because this would make the [[cross entropy]] go to infinity



### Relationship to Entropy and Cross-Entropy

- KL divergence is the difference between the **cross-entropy** $H(P, Q)$ and the **entropy** $H(P)$ of the true distribution:

$$
\begin{split}
D_{KL}(P \parallel Q)
&= \int_{\mathbb{R}} p(x) \log \left( \frac{p(x)}{q(x)} \right) dx \\
&= \int_{\mathbb{R}} p(x) \log p(x) \, dx - \int_{\mathbb{R}} p(x) \log q(x) \, dx \\
&= H(P, Q) - H(P)
\end{split}
$$

### one hot encoded labels
- if $P$ is one hot encoded meaning that just one value $x_0$ with $P(x_0) = 1$ and $P(x) = 0$ for all $x \ne x_0$


$$
\begin{split}
H\left(P , Q \right) 
&= - \sum_{x \in \mathcal{X}} p(x) \log \left( q(x) \right)  \\
&= -\log \left( q(x_0) \right) 
\end{split}
$$

### prove that the kl divergence is positive
- using the fact that for all $u>0$ the following is true

$$
-\log(u) \geq 1-u
$$

$$
\begin{split}
D_{KL}(P \parallel Q) 
&= \int_{\mathbb{R}} p(x) \log \left( \frac{p(x)}{q(x)} \right) dx \\
&= - \int_{\mathbb{R}} p(x) \log \left( \frac{q(x)}{p(x)} \right) dx \\
&\leq  \int_{\mathbb{R}} p(x) \left( 1 - \frac{q(x)}{p(x)} \right) dx \\
&=  \int_{\mathbb{R}} p(x) dx - \int_{\mathbb{R}} p(x)  \frac{q(x)}{p(x)}  dx \\
&=  1 - \int_{\mathbb{R}}q(x)  dx \\
&= 0 \\
\end{split}
$$

### kl divergence of the standard normal distribution
- given a [[random variable]] $Q\sim \mathcal{N}(0,1)$ and a [[random variable]] $P$ with $\mathbb{E}[P] = 0$ and $\mathbb{VAR}[P] = 1$

$$
\begin{split}
D_{KL}(P \parallel Q)
&= \int_{\mathbb{R}} p(x) \log \left( \frac{p(x)}{q(x)} \right) dx \\
&= -H(P) - \int_{\mathbb{R}} p(x) \log q(x) \, dx \\
&= -H(P) - \int_{\mathbb{R}} p(x) \ln\left(\frac{1}{\sqrt{2 \pi }}\exp{\left[-\frac{x^2}{2}\right]}\right) \, dx \\
&= -H(P) - \int_{\mathbb{R}} p(x) \left( \frac{-1}{2} \ln\left(2 \pi\right) -\frac{x^2}{2} \right) \, dx \\
&= -H(P) + \frac{1}{2} \int_{\mathbb{R}} p(x) \left(  \ln\left(2 \pi\right) + x^2\right) \, dx \\
&= -H(P) + \frac{1}{2} \left(\ln\left(2 \pi\right) + 1 \right) \\
&= -H(P) + H(Q) \\
\end{split}
$$

- since $D_{KL}(P \parallel Q) \geq 0 \Rightarrow H(Q) \geq H(P)$ 

![[entropy#standard normal distribution]]

### kl divergence and maximum likelihood
- the log [[likelihood function]] is proportional to the negative [[kl divergence]]

$$
\begin{split}
\mathbb{E}_{(X, Y)\sim P_\theta^*}\left[\log\left(p\left(Y|X, \theta\right)\right)\right] 
=& \int\int \log\left(p\left(Y|X, \theta\right)\right) p\left(Y,X\right) dydx \\
=& \int\int \log\left(p\left(Y|X, \theta\right)\right) p\left(Y|X\right) p\left(X\right) dydx \\
=& \int\int \log\left(p\left(Y|X, \theta\right)\right) p\left(Y|X, \theta^*\right) p\left(X\right) dydx \\
=& \mathbb{E}_{X\sim P_\theta^*}\left[ \int  \log\left(p\left(Y|X, \theta\right)\right) p\left(Y|X, \theta^*\right) dy \right] \\
=& \mathbb{E}_{X\sim P_\theta^*}\left[ -H\left(p\left(Y|X, \theta^*\right)||p\left(Y|X, \theta\right)\right) \right] \\
=& \mathbb{E}_{X\sim P_\theta^*}\left[ \int  \log\left(p\left(Y|X, \theta\right) \frac{p\left(Y|X, \theta^*\right)}{p\left(Y|X, \theta^*\right)}\right) p\left(Y|X, \theta^*\right) dy \right] \\
=& \mathbb{E}_{X\sim P_\theta^*}\left[ \int - \log\left( \frac{p\left(Y|X, \theta^*\right)}{p\left(Y|X, \theta\right)}\right) p\left(Y|X, \theta^*\right) + H(p\left(Y|X, \theta^*\right)) dy \right]  \\
=& \mathbb{E}_{X\sim P_\theta^*}\left[- D_{KL}\left(p\left(Y|X, \theta^*\right)||p\left(Y|X, \theta\right)\right) + C \right] \\
\end{split}
$$


- thus maximizing the [[likelihood function]] is equivalent to minimizing the [[kl divergence]] between the true distribution and the [[distribution]] parameterized by the learned parameters $\theta$

$$
\begin{split}
&\mathrm{arg}\max_\theta \mathbb{E}_{(X, Y)\sim P_\theta^*}\left[\log\left(p\left(Y|X, \theta\right)\right)\right] \\
&= \mathrm{arg}\min_\theta \mathbb{E}_{X\sim P_\theta^*}\left[- D_{KL}\left(p\left(Y|X, \theta^*\right)||p\left(Y|X, \theta\right)\right) + C \right] \\
&= \theta^* \\
\end{split}
$$

- because the [[kl divergence]] is zero exactly if both distributions are identical, we can be sure to find a parameter vector with the same [[distribution]] as the true parameter vector

### summary: kl divergence as a loss function

- in general minimizing the [[kl divergence]] leads to the maximum [[maximum likelihood estimator]]

$$
\begin{split}
&\mathrm{arg}\min_\theta \mathbb{E}_{X\sim P_\theta^*}\left[ D_{KL}\left(p\left(Y|X, \theta^*\right)||p\left(Y|X, \theta\right)\right) \right]\\
&=  \mathrm{arg}\max_\theta \mathbb{E}_{(X, Y)\sim P_\theta^*}\left[\log\left(p\left(Y|X, \theta\right)\right)\right]\\
\end{split}
$$

- if the [[white noise|noise]] of the model is [[normal distribution|normal distributed]] with zero mean its also equivalent to minimizing the [[mean square error]]

$$
Y = f_{\theta^*}(X) + \epsilon, \quad \epsilon \sim \mathcal{N}(0, \sigma^2)
$$

$$
\begin{split}
&\mathrm{arg}\min_\theta \mathbb{E}_{X\sim P_\theta^*}\left[ D_{KL}\left(p\left(Y|X, \theta^*\right)||p\left(Y|X, \theta\right)\right) \right]\\
&=  \mathrm{arg}\max_\theta \mathbb{E}_{(X, Y)\sim P_\theta^*}\left[\log\left(p\left(Y|X, \theta\right)\right)\right]\\
&= \mathrm{arg}\min_\theta \mathbb{E}_{(X, Y)\sim P_\theta^*}\left[\left(\mathrm{MSE}(Y, f_\theta(X))\right)\right] \\
\end{split}
$$

# anki

START
Basic
summary: [[kl divergence]] as a loss function
- relationship to [[maximum likelihood estimator]]
- relationship to [[mean square error]] loss

Back: 

### summary: kl divergence as a loss function

- in general minimizing the [[kl divergence]] leads to the maximum [[maximum likelihood estimator]]

$$
\begin{split}
&\mathrm{arg}\min_\theta \mathbb{E}_{X\sim P_\theta^*}\left[ D_{KL}\left(p\left(Y|X, \theta^*\right)||p\left(Y|X, \theta\right)\right) \right]\\
&=  \mathrm{arg}\max_\theta \mathbb{E}_{(X, Y)\sim P_\theta^*}\left[\log\left(p\left(Y|X, \theta\right)\right)\right]\\
\end{split}
$$

- if the [[white noise|noise]] of the model is [[normal distribution|normal distributed]] with zero mean its also equivalent to minimizing the [[mean square error]]

$$
Y = f_{\theta^*}(X) + \epsilon, \quad \epsilon \sim \mathcal{N}(0, \sigma^2)
$$

$$
\begin{split}
&\mathrm{arg}\min_\theta \mathbb{E}_{X\sim P_\theta^*}\left[ D_{KL}\left(p\left(Y|X, \theta^*\right)||p\left(Y|X, \theta\right)\right) \right]\\
&=  \mathrm{arg}\max_\theta \mathbb{E}_{(X, Y)\sim P_\theta^*}\left[\log\left(p\left(Y|X, \theta\right)\right)\right]\\
&= \mathrm{arg}\min_\theta \mathbb{E}_{(X, Y)\sim P_\theta^*}\left[\left(\mathrm{MSE}(Y, f_\theta(X))\right)\right] \\
\end{split}
$$


### kl divergence and maximum likelihood
- the log [[likelihood function]] is proportional to the negative [[kl divergence]]

$$
\begin{split}
\mathbb{E}_{(X, Y)\sim P_\theta^*}\left[\log\left(p\left(Y|X, \theta\right)\right)\right] 
=& \int\int \log\left(p\left(Y|X, \theta\right)\right) p\left(Y,X\right) dydx \\
=& \int\int \log\left(p\left(Y|X, \theta\right)\right) p\left(Y|X\right) p\left(X\right) dydx \\
=& \int\int \log\left(p\left(Y|X, \theta\right)\right) p\left(Y|X, \theta^*\right) p\left(X\right) dydx \\
=& \mathbb{E}_{X\sim P_\theta^*}\left[ \int  \log\left(p\left(Y|X, \theta\right)\right) p\left(Y|X, \theta^*\right) dy \right] \\
=& \mathbb{E}_{X\sim P_\theta^*}\left[ -H\left(p\left(Y|X, \theta^*\right)||p\left(Y|X, \theta\right)\right) \right] \\
=& \mathbb{E}_{X\sim P_\theta^*}\left[ \int  \log\left(p\left(Y|X, \theta\right) \frac{p\left(Y|X, \theta^*\right)}{p\left(Y|X, \theta^*\right)}\right) p\left(Y|X, \theta^*\right) dy \right] \\
=& \mathbb{E}_{X\sim P_\theta^*}\left[ \int - \log\left( \frac{p\left(Y|X, \theta^*\right)}{p\left(Y|X, \theta\right)}\right) p\left(Y|X, \theta^*\right) + H(p\left(Y|X, \theta^*\right)) dy \right]  \\
=& \mathbb{E}_{X\sim P_\theta^*}\left[- D_{KL}\left(p\left(Y|X, \theta^*\right)||p\left(Y|X, \theta\right)\right) + C \right] \\
\end{split}
$$

- thus maximizing the [[likelihood function]] is equivalent to minimizing the [[kl divergence]] between the true distribution and the [[distribution]] parameterized by the learned parameters $\theta$

$$
\begin{split}
&\mathrm{arg}\max_\theta \mathbb{E}_{(X, Y)\sim P_\theta^*}\left[\log\left(p\left(Y|X, \theta\right)\right)\right] \\
&= \mathrm{arg}\min_\theta \mathbb{E}_{X\sim P_\theta^*}\left[- D_{KL}\left(p\left(Y|X, \theta^*\right)||p\left(Y|X, \theta\right)\right) + C \right] \\
&= \theta^* \\
\end{split}
$$

- because the [[kl divergence]] is zero exactly if both distributions are identical, we can be sure to find a parameter vector with the same [[distribution]] as the true parameter vector

#### mean square error and the maximum likelihood estimator
- if the following is true 

$$
Y \sim \mathcal{N}\left(f_{\theta^*}(X), \sigma^2\right) \Leftrightarrow \epsilon = Y - f_{\theta^*}(X) \sim \mathcal{N}\left(0, \sigma^2\right)
$$

- minimizing is [[mean square error]] leads to the [[maximum likelihood estimator]]

$$
\theta_{MLE} = arg\max_\theta \mathbb{E}_{(X,Y) \sim \mathcal{D}}\left[\log p(Y|X,\theta)\right]  = arg\min_\theta \mathbb{E}_{(X,Y) \sim \mathcal{D}}\left[\mathrm{MSE}(f_{\theta}(X), Y)\right]
$$

- if this condition is true and then the relationship between the [[mean square error]] and the [[likelihood function|log likelihood]] of the mse and ll minimizing parameters $\theta^*$ is as follows

$$
\begin{split}
\hat{\mathcal{L}}({\theta^*}) 
&= \sum_{i=1}^N \log{\left(\frac{1}{\sqrt{2\pi \sigma^2}}\right)} -\frac{1}{2} \frac{\left(y_i - f_{\theta^*}(x_i) \right)^2}{\sigma^2} \\
&=  -\frac{N}{2}\log{\left(2\pi \sigma^2\right)} - \frac{1}{2\sigma^2}\sum_{i=1}^N\left(y_i - f_{\theta^*}(x_i) \right)^2 \\
&=  -\frac{N}{2}\log{\left(2\pi \sigma^2\right)} - \frac{N}{2\sigma^2}  \mathrm{MSE}(f_{\theta^*}(X), Y) \\
\end{split}
$$



_______________

### kl divergence
- KL divergence is a measure of how much the **assumed distribution $Q$**
  diverges from the **true distribution $P$**.
#### Continuous Case

$$
D_{KL}(P \parallel Q) = \int_{\mathbb{R}} p(x) \log \left( \frac{p(x)}{q(x)} \right) dx
$$


- $D_{KL}(P \parallel Q) \in [0, \infty]$
- $D_{KL}(P \parallel Q) = 0$ if and only if $P = Q$
- $D_{KL}(P \parallel Q) = \infty$ if there exists any $x$ such that $p(x) > 0$ and $q(x) = 0$ because this would make the [[cross entropy]] go to infinity



### entropy
- measure of the **average amount of information** contained in an observation of a [[random variable]] in bits (if the $\log_2$ is used)
- in other words the average amount of removed uncertainty by an observation 
- for a discrete random variable with the [[probability function]] $p_X$ the [[entropy]] is defined as follows

$$
H(X) = \mathbb{E}\left[-\log\left(p_X(X)\right)\right] = - \sum p_X(x_i) \log\left(p_X(x_i)\right)
$$

- $H(X)$ is positive, and its maximum value depends on the [[distribution]] of $X$

Tags: mathematics statistics SS25
<!--ID: 1752996087241-->
END

START
Basic

- relationship between the (conditional) [[kl divergence]] and the (conditional) [[likelihood function]] with proof
- implications

Back: 
### kl divergence and maximum likelihood
- the log [[likelihood function]] is proportional to the negative [[kl divergence]]

$$
\begin{split}
\mathbb{E}_{(X, Y)\sim P_\theta^*}\left[\log\left(p\left(Y|X, \theta\right)\right)\right] 
=& \int\int \log\left(p\left(Y|X, \theta\right)\right) p\left(Y,X\right) dydx \\
=& \int\int \log\left(p\left(Y|X, \theta\right)\right) p\left(Y|X\right) p\left(X\right) dydx \\
=& \int\int \log\left(p\left(Y|X, \theta\right)\right) p\left(Y|X, \theta^*\right) p\left(X\right) dydx \\
=& \mathbb{E}_{X\sim P_\theta^*}\left[ \int  \log\left(p\left(Y|X, \theta\right)\right) p\left(Y|X, \theta^*\right) dy \right] \\
=& \mathbb{E}_{X\sim P_\theta^*}\left[ -H\left(p\left(Y|X, \theta^*\right)||p\left(Y|X, \theta\right)\right) \right] \\
=& \mathbb{E}_{X\sim P_\theta^*}\left[ \int  \log\left(p\left(Y|X, \theta\right) \frac{p\left(Y|X, \theta^*\right)}{p\left(Y|X, \theta^*\right)}\right) p\left(Y|X, \theta^*\right) dy \right] \\
=& \mathbb{E}_{X\sim P_\theta^*}\left[ \int - \log\left( \frac{p\left(Y|X, \theta^*\right)}{p\left(Y|X, \theta\right)}\right) p\left(Y|X, \theta^*\right) + H(p\left(Y|X, \theta^*\right)) dy \right]  \\
=& \mathbb{E}_{X\sim P_\theta^*}\left[- D_{KL}\left(p\left(Y|X, \theta^*\right)||p\left(Y|X, \theta\right)\right) + C \right] \\
\end{split}
$$

- thus maximizing the [[likelihood function]] is equivalent to minimizing the [[kl divergence]] between the true distribution and the [[distribution]] parameterized by the learned parameters $\theta$

$$
\begin{split}
&\mathrm{arg}\max_\theta \mathbb{E}_{(X, Y)\sim P_\theta^*}\left[\log\left(p\left(Y|X, \theta\right)\right)\right] \\
&= \mathrm{arg}\min_\theta \mathbb{E}_{X\sim P_\theta^*}\left[- D_{KL}\left(p\left(Y|X, \theta^*\right)||p\left(Y|X, \theta\right)\right) + C \right] \\
&= \theta^* \\
\end{split}
$$

- because the [[kl divergence]] is zero exactly if both distributions are identical, we can be sure to find a parameter vector with the same [[distribution]] as the true parameter vector

_______________

### kl divergence
- KL divergence is a measure of how much the **assumed distribution $Q$**
  diverges from the **true distribution $P$**.
#### Continuous Case

$$
D_{KL}(P \parallel Q) = \int_{\mathbb{R}} p(x) \log \left( \frac{p(x)}{q(x)} \right) dx
$$

#### Discrete Case

$$
D_{KL}(P \parallel Q) = \sum_{x \in \mathcal{X}} p(x) \log \left( \frac{p(x)}{q(x)} \right)
$$

- $D_{KL}(P \parallel Q) \in [0, \infty]$
- $D_{KL}(P \parallel Q) = 0$ if and only if $P = Q$
- $D_{KL}(P \parallel Q) = \infty$ if there exists any $x$ such that $p(x) > 0$ and $q(x) = 0$ because this would make the [[cross entropy]] go to infinity



### entropy
- measure of the **average amount of information** contained in an observation of a [[random variable]] in bits (if the $\log_2$ is used)
- in other words the average amount of removed uncertainty by an observation 
- for a discrete random variable with the [[probability function]] $p_X$ the [[entropy]] is defined as follows

$$
H(X) = \mathbb{E}\left[-\log\left(p_X(X)\right)\right] = - \sum p_X(x_i) \log\left(p_X(x_i)\right)
$$

- $H(X)$ is positive, and its maximum value depends on the [[distribution]] of $X$

Tags: mathematics statistics SS25
<!--ID: 1752683537373-->
END

START
Basic
- given a [[random variable]] $Q\sim \mathcal{N}(0,1)$ and a [[random variable]] $P$ with $\mathbb{E}[P] = 0$ and $\mathbb{VAR}[P] = 1$
- prove that $H(Q) \geq H(P)$


Back: 

### kl divergence of the standard normal distribution
- given a [[random variable]] $Q\sim \mathcal{N}(0,1)$ and a [[random variable]] $P$ with $\mathbb{E}[P] = 0$ and $\mathbb{VAR}[P] = 1$

$$
\begin{split}
D_{KL}(P \parallel Q)
&= \int_{\mathbb{R}} p(x) \log \left( \frac{p(x)}{q(x)} \right) dx \\
&= -H(P) - \int_{\mathbb{R}} p(x) \log q(x) \, dx \\
&= -H(P) - \int_{\mathbb{R}} p(x) \ln\left(\frac{1}{\sqrt{2 \pi }}\exp{\left[-\frac{x^2}{2}\right]}\right) \, dx \\
&= -H(P) - \int_{\mathbb{R}} p(x) \left( \frac{-1}{2} \ln\left(2 \pi\right) -\frac{x^2}{2} \right) \, dx \\
&= -H(P) + \frac{1}{2} \int_{\mathbb{R}} p(x) \left(  \ln\left(2 \pi\right) + x^2\right) \, dx \\
&= -H(P) + \frac{1}{2} \left(\ln\left(2 \pi\right) + 1 \right) \\
&= -H(P) + H(Q) \\
\end{split}
$$

- since $D_{KL}(P \parallel Q) \geq 0 \Rightarrow H(Q) \geq H(P)$ 

### entropy of the standard normal distribution
- [[normal distribution]] with $\mu=0$ and $\sigma^2=1$

$$
\begin{split}
H(X) 
&= - \int_\mathbb{R} f(x) \ln\left(\frac{1}{\sqrt{2 \pi }}\exp{\left[-\frac{x^2}{2}\right]}\right) dx \\
&= - \int_\mathbb{R} f(x) \left( \frac{-1}{2} \ln\left(2 \pi\right) -\frac{x^2}{2} \right) dx \\
&= \frac{1}{2} \ln\left(2 \pi\right) \int_\mathbb{R} f(x) dx +  \frac{1}{2}\int_\mathbb{R} x^2 f(x) dx \\
&= \frac{1}{2} \ln\left(2 \pi\right)  +  \frac{1}{2} \mathbb{VAR}[X] \\
&= \frac{1}{2} \left(\ln\left(2 \pi\right) + 1 \right) \\
\end{split}
$$

### prove that the kl divergence is positive
- using the fact that for all $u>0$ the following is true

$$
-\log(u) \geq 1-u
$$

$$
\begin{split}
D_{KL}(P \parallel Q) 
&= \int_{\mathbb{R}} p(x) \log \left( \frac{p(x)}{q(x)} \right) dx \\
&= - \int_{\mathbb{R}} p(x) \log \left( \frac{q(x)}{p(x)} \right) dx \\
&\leq  \int_{\mathbb{R}} p(x) \left( 1 - \frac{q(x)}{p(x)} \right) dx \\
&=  \int_{\mathbb{R}} p(x) dx - \int_{\mathbb{R}} p(x)  \frac{q(x)}{p(x)}  dx \\
&=  1 - \int_{\mathbb{R}}q(x)  dx \\
&= 0 \\
\end{split}
$$


_______________

### kl divergence
- KL divergence is a measure of how much the **assumed distribution $Q$**
  diverges from the **true distribution $P$**.
#### Continuous Case

$$
D_{KL}(P \parallel Q) = \int_{\mathbb{R}} p(x) \log \left( \frac{p(x)}{q(x)} \right) dx
$$

#### Discrete Case

$$
D_{KL}(P \parallel Q) = \sum_{x \in \mathcal{X}} p(x) \log \left( \frac{p(x)}{q(x)} \right)
$$

- $D_{KL}(P \parallel Q) \in [0, \infty]$
- $D_{KL}(P \parallel Q) = 0$ if and only if $P = Q$
- $D_{KL}(P \parallel Q) = \infty$ if there exists any $x$ such that $p(x) > 0$ and $q(x) = 0$ because this would make the [[cross entropy]] go to infinity

### cross entropy
- [[cross entropy]] is a measure of the dissimilarity between two probability distributions: a **true distribution** $P$ and an **estimated (or assumed) distribution** $Q$
- It quantifies the **expected number of bits** needed to encode samples from $P$
  using a code that is optimized for $Q$
- It is defined as the **expected negative log-likelihood** under $Q$
  when the data is actually drawn from $P$

#### Continuous Case

$$
\begin{split}
H\left(P , Q \right) 
&= - \int_\mathbb{R} p(x) \log \left( q(x) \right) dx \\
&= - \mathbb{E}_p\left[\log \left( q(x) \right)\right] \\
\end{split}
$$

#### Discrete Case

$$
\begin{split}
H\left(P , Q \right) 
&= - \sum_{x \in \mathcal{X}} p(x) \log \left( q(x) \right) dx \\
&= - \mathbb{E}_p\left[\log \left( q(x) \right)\right] \\
\end{split}
$$

#### range
- The **minimum** cross-entropy is reached when $P=Q$ in which case it reduces to the **entropy** of $P$:

$$
H(P, Q) = H(P) \quad \text{if and only if} \quad P = Q
$$

- can go to infinity if there are regions where  $p(x) > 0$ but $q(x) = 0$ because $\log \left(q(x)\right)=\log \left(0\right) = -\infty$, and thus the expectation $-\mathbb{E}_{x \sim P}[\log q(x)]$ becomes infinite.

$$
\text{supp}(P) \nsubseteq \text{supp}(Q)
$$




### entropy
- measure of the **average amount of information** contained in an observation of a [[random variable]] in bits (if the $\log_2$ is used)
- in other words the average amount of removed uncertainty by an observation 
- for a discrete random variable with the [[probability function]] $p_X$ the [[entropy]] is defined as follows

$$
H(X) = \mathbb{E}\left[-\log\left(p_X(X)\right)\right] = - \sum p_X(x_i) \log\left(p_X(x_i)\right)
$$

- $H(X)$ is positive, and its maximum value depends on the [[distribution]] of $X$
##### example
- [[bernoulli distribution]] with $p=0.9$ and $p=0.5$
- We see that the entropy is **higher** when $p=0.5$, indicating that this outcome is **more uncertain** and thus contains **more information per observation**.

$$
\begin{split}
H(X) &= - 0.1 \cdot \log_2(0.1) - 0.9 \cdot \log_2(0.9) = 0.33 + 0.14 = 0.47 \\
H(X) &= - 0.5 \cdot \log_2(0.5) - 0.5 \cdot \log_2(0.5) = \frac{1}{2} + \frac{1}{2} = 1 \\
\end{split}
$$

### differential entropy
- for continuous random variables the concept of [[entropy]] can be extended
- does not have an intuitive interpretation other than **measurement for uncertainty or spread**
- other than the [[entropy]] the differential entropy can be negative and is sensitive to scaling

- for a continuous random variable with the [[probability density function (PDF)]] $f_X$ the differential entropy is defined as follows

$$
H(X) = \mathbb{E}\left[-\log\left(f_X(X)\right)\right] = - \int_\mathbb{R} f_X(x) \log\left(f_X(x)\right) dx
$$
##### example
- [[exponential distribution]]

$$
\begin{split}
H(X) 
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \ln\left(\lambda e^{-\lambda x})\right) dx \\
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \left(\ln(\lambda)  -\lambda x\right) dx \\
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \ln(\lambda) dx + \lambda \int_\mathbb{R} \lambda e^{-\lambda x}  x dx \\
&= - \ln(\lambda) + \lambda \int_\mathbb{R}  \mathbb{E}[X] \\
&= - \ln(\lambda) + \frac{\lambda}{\lambda} \\
&= 1 - \ln(\lambda) \\
\end{split}
$$

- the higher $\lambda$ is the less the PDF spreads thus $1-\ln(2)=0.3<1-\ln(1)=1$

Tags: mathematics statistics SS25
<!--ID: 1748332893442-->
END

START
Basic
[[kl divergence]]
- prove that the kl divergence is positive

Back: 

- using the fact that for all $u>0$ the following is true

$$
-\log(u) \geq 1-u
$$

$$
\begin{split}
D_{KL}(P \parallel Q) 
&= \int_{\mathbb{R}} p(x) \log \left( \frac{p(x)}{q(x)} \right) dx \\
&= - \int_{\mathbb{R}} p(x) \log \left( \frac{q(x)}{p(x)} \right) dx \\
&\leq  \int_{\mathbb{R}} p(x) \left( 1 - \frac{q(x)}{p(x)} \right) dx \\
&=  \int_{\mathbb{R}} p(x) dx - \int_{\mathbb{R}} p(x)  \frac{q(x)}{p(x)}  dx \\
&=  1 - \int_{\mathbb{R}}q(x)  dx \\
&= 0 \\
\end{split}
$$


### kl divergence
- KL divergence is a measure of how much the **assumed distribution $Q$**
  diverges from the **true distribution $P$**.
#### Continuous Case

$$
D_{KL}(P \parallel Q) = \int_{\mathbb{R}} p(x) \log \left( \frac{p(x)}{q(x)} \right) dx
$$

#### Discrete Case

$$
D_{KL}(P \parallel Q) = \sum_{x \in \mathcal{X}} p(x) \log \left( \frac{p(x)}{q(x)} \right)
$$

- $D_{KL}(P \parallel Q) \in [0, \infty]$
- $D_{KL}(P \parallel Q) = 0$ if and only if $P = Q$
- $D_{KL}(P \parallel Q) = \infty$ if there exists any $x$ such that $p(x) > 0$ and $q(x) = 0$ because this would make the [[cross entropy]] go to infinity


_______________
### cross entropy
- [[cross entropy]] is a measure of the dissimilarity between two probability distributions: a **true distribution** $P$ and an **estimated (or assumed) distribution** $Q$
- It quantifies the **expected number of bits** needed to encode samples from $P$
  using a code that is optimized for $Q$
- It is defined as the **expected negative log-likelihood** under $Q$
  when the data is actually drawn from $P$

#### Continuous Case

$$
\begin{split}
H\left(P , Q \right) 
&= - \int_\mathbb{R} p(x) \log \left( q(x) \right) dx \\
&= - \mathbb{E}_p\left[\log \left( q(x) \right)\right] \\
\end{split}
$$

#### Discrete Case

$$
\begin{split}
H\left(P , Q \right) 
&= - \sum_{x \in \mathcal{X}} p(x) \log \left( q(x) \right) dx \\
&= - \mathbb{E}_p\left[\log \left( q(x) \right)\right] \\
\end{split}
$$

#### range
- The **minimum** cross-entropy is reached when $P=Q$ in which case it reduces to the **entropy** of $P$:

$$
H(P, Q) = H(P) \quad \text{if and only if} \quad P = Q
$$

- can go to infinity if there are regions where  $p(x) > 0$ but $q(x) = 0$ because $\log \left(q(x)\right)=\log \left(0\right) = -\infty$, and thus the expectation $-\mathbb{E}_{x \sim P}[\log q(x)]$ becomes infinite.

$$
\text{supp}(P) \nsubseteq \text{supp}(Q)
$$




### entropy
- measure of the **average amount of information** contained in an observation of a [[random variable]] in bits (if the $\log_2$ is used)
- in other words the average amount of removed uncertainty by an observation 
- for a discrete random variable with the [[probability function]] $p_X$ the [[entropy]] is defined as follows

$$
H(X) = \mathbb{E}\left[-\log\left(p_X(X)\right)\right] = - \sum p_X(x_i) \log\left(p_X(x_i)\right)
$$

- $H(X)$ is positive, and its maximum value depends on the [[distribution]] of $X$
##### example
- [[bernoulli distribution]] with $p=0.9$ and $p=0.5$
- We see that the entropy is **higher** when $p=0.5$, indicating that this outcome is **more uncertain** and thus contains **more information per observation**.

$$
\begin{split}
H(X) &= - 0.1 \cdot \log_2(0.1) - 0.9 \cdot \log_2(0.9) = 0.33 + 0.14 = 0.47 \\
H(X) &= - 0.5 \cdot \log_2(0.5) - 0.5 \cdot \log_2(0.5) = \frac{1}{2} + \frac{1}{2} = 1 \\
\end{split}
$$

### differential entropy
- for continuous random variables the concept of [[entropy]] can be extended
- does not have an intuitive interpretation other than **measurement for uncertainty or spread**
- other than the [[entropy]] the differential entropy can be negative and is sensitive to scaling

- for a continuous random variable with the [[probability density function (PDF)]] $f_X$ the differential entropy is defined as follows

$$
H(X) = \mathbb{E}\left[-\log\left(f_X(X)\right)\right] = - \int_\mathbb{R} f_X(x) \log\left(f_X(x)\right) dx
$$
##### example
- [[exponential distribution]]

$$
\begin{split}
H(X) 
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \ln\left(\lambda e^{-\lambda x})\right) dx \\
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \left(\ln(\lambda)  -\lambda x\right) dx \\
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \ln(\lambda) dx + \lambda \int_\mathbb{R} \lambda e^{-\lambda x}  x dx \\
&= - \ln(\lambda) + \lambda \int_\mathbb{R}  \mathbb{E}[X] \\
&= - \ln(\lambda) + \frac{\lambda}{\lambda} \\
&= 1 - \ln(\lambda) \\
\end{split}
$$

- the higher $\lambda$ is the less the PDF spreads thus $1-\ln(2)=0.3<1-\ln(1)=1$

Tags: mathematics statistics SS25
<!--ID: 1748332617287-->
END


START
Basic
[[kl divergence]]
- definition
- intuition
- range with edge cases

Back: 
### kl divergence
- KL divergence is a measure of how much the **assumed distribution $Q$**
  diverges from the **true distribution $P$**.
#### Continuous Case

$$
D_{KL}(P \parallel Q) = \int_{\mathbb{R}} p(x) \log \left( \frac{p(x)}{q(x)} \right) dx
$$

#### Discrete Case

$$
D_{KL}(P \parallel Q) = \sum_{x \in \mathcal{X}} p(x) \log \left( \frac{p(x)}{q(x)} \right)
$$

- $D_{KL}(P \parallel Q) \in [0, \infty]$
- $D_{KL}(P \parallel Q) = 0$ if and only if $P = Q$
- $D_{KL}(P \parallel Q) = \infty$ if there exists any $x$ such that $p(x) > 0$ and $q(x) = 0$ because this would make the [[cross entropy]] go to infinity


_______________
### cross entropy
- [[cross entropy]] is a measure of the dissimilarity between two probability distributions: a **true distribution** $P$ and an **estimated (or assumed) distribution** $Q$
- It quantifies the **expected number of bits** needed to encode samples from $P$
  using a code that is optimized for $Q$
- It is defined as the **expected negative log-likelihood** under $Q$
  when the data is actually drawn from $P$

#### Continuous Case

$$
\begin{split}
H\left(P , Q \right) 
&= - \int_\mathbb{R} p(x) \log \left( q(x) \right) dx \\
&= - \mathbb{E}_p\left[\log \left( q(x) \right)\right] \\
\end{split}
$$

#### Discrete Case

$$
\begin{split}
H\left(P , Q \right) 
&= - \sum_{x \in \mathcal{X}} p(x) \log \left( q(x) \right) dx \\
&= - \mathbb{E}_p\left[\log \left( q(x) \right)\right] \\
\end{split}
$$

#### range
- The **minimum** cross-entropy is reached when $P=Q$ in which case it reduces to the **entropy** of $P$:

$$
H(P, Q) = H(P) \quad \text{if and only if} \quad P = Q
$$

- can go to infinity if there are regions where  $p(x) > 0$ but $q(x) = 0$ because $\log \left(q(x)\right)=\log \left(0\right) = -\infty$, and thus the expectation $-\mathbb{E}_{x \sim P}[\log q(x)]$ becomes infinite.

$$
\text{supp}(P) \nsubseteq \text{supp}(Q)
$$




### entropy
- measure of the **average amount of information** contained in an observation of a [[random variable]] in bits (if the $\log_2$ is used)
- in other words the average amount of removed uncertainty by an observation 
- for a discrete random variable with the [[probability function]] $p_X$ the [[entropy]] is defined as follows

$$
H(X) = \mathbb{E}\left[-\log\left(p_X(X)\right)\right] = - \sum p_X(x_i) \log\left(p_X(x_i)\right)
$$

- $H(X)$ is positive, and its maximum value depends on the [[distribution]] of $X$
##### example
- [[bernoulli distribution]] with $p=0.9$ and $p=0.5$
- We see that the entropy is **higher** when $p=0.5$, indicating that this outcome is **more uncertain** and thus contains **more information per observation**.

$$
\begin{split}
H(X) &= - 0.1 \cdot \log_2(0.1) - 0.9 \cdot \log_2(0.9) = 0.33 + 0.14 = 0.47 \\
H(X) &= - 0.5 \cdot \log_2(0.5) - 0.5 \cdot \log_2(0.5) = \frac{1}{2} + \frac{1}{2} = 1 \\
\end{split}
$$

### differential entropy
- for continuous random variables the concept of [[entropy]] can be extended
- does not have an intuitive interpretation other than **measurement for uncertainty or spread**
- other than the [[entropy]] the differential entropy can be negative and is sensitive to scaling

- for a continuous random variable with the [[probability density function (PDF)]] $f_X$ the differential entropy is defined as follows

$$
H(X) = \mathbb{E}\left[-\log\left(f_X(X)\right)\right] = - \int_\mathbb{R} f_X(x) \log\left(f_X(x)\right) dx
$$
##### example
- [[exponential distribution]]

$$
\begin{split}
H(X) 
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \ln\left(\lambda e^{-\lambda x})\right) dx \\
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \left(\ln(\lambda)  -\lambda x\right) dx \\
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \ln(\lambda) dx + \lambda \int_\mathbb{R} \lambda e^{-\lambda x}  x dx \\
&= - \ln(\lambda) + \lambda \int_\mathbb{R}  \mathbb{E}[X] \\
&= - \ln(\lambda) + \frac{\lambda}{\lambda} \\
&= 1 - \ln(\lambda) \\
\end{split}
$$

- the higher $\lambda$ is the less the PDF spreads thus $1-\ln(2)=0.3<1-\ln(1)=1$

Tags: mathematics statistics SS25
<!--ID: 1748278959145-->
END


START
Basic
[[kl divergence]]
- definition
- intuition
- relationship to [[cross entropy]] and [[entropy]]
- one hot encoded labels

Back: 
### kl divergence
- KL divergence is a measure of how much the **assumed distribution $Q$**
  diverges from the **true distribution $P$**.
#### Continuous Case

$$
D_{KL}(P \parallel Q) = \int_{\mathbb{R}} p(x) \log \left( \frac{p(x)}{q(x)} \right) dx
$$

#### Discrete Case

$$
D_{KL}(P \parallel Q) = \sum_{x \in \mathcal{X}} p(x) \log \left( \frac{p(x)}{q(x)} \right)
$$

- $D_{KL}(P \parallel Q) \in [0, \infty]$
- $D_{KL}(P \parallel Q) = 0$ if and only if $P = Q$
- $D_{KL}(P \parallel Q) = \infty$ if there exists any $x$ such that $p(x) > 0$ and $q(x) = 0$ because this would make the [[cross entropy]] go to infinity



### Relationship to Entropy and Cross-Entropy

- KL divergence is the difference between the **cross-entropy** $H(P, Q)$ and the **entropy** $H(P)$ of the true distribution:

$$
\begin{split}
D_{KL}(P \parallel Q)
&= \int_{\mathbb{R}} p(x) \log \left( \frac{p(x)}{q(x)} \right) dx \\
&= \int_{\mathbb{R}} p(x) \log p(x) \, dx - \int_{\mathbb{R}} p(x) \log q(x) \, dx \\
&= H(P, Q) - H(P)
\end{split}
$$
### one hot encoded labels
- if $P$ is one hot encoded meaning that just one value $x_0$ with $P(x_0) = 1$ and $P(x) = 0$ for all $x \ne x_0$


$$
\begin{split}
H\left(P , Q \right) 
&= - \sum_{x \in \mathcal{X}} p(x) \log \left( q(x) \right)  \\
&= -\log \left( q(x_0) \right) 
\end{split}
$$


_______________
### cross entropy
- [[cross entropy]] is a measure of the dissimilarity between two probability distributions: a **true distribution** $P$ and an **estimated (or assumed) distribution** $Q$
- It quantifies the **expected number of bits** needed to encode samples from $P$
  using a code that is optimized for $Q$
- It is defined as the **expected negative log-likelihood** under $Q$
  when the data is actually drawn from $P$

#### Continuous Case

$$
\begin{split}
H\left(P , Q \right) 
&= - \int_\mathbb{R} p(x) \log \left( q(x) \right) dx \\
&= - \mathbb{E}_p\left[\log \left( q(x) \right)\right] \\
\end{split}
$$

#### Discrete Case

$$
\begin{split}
H\left(P , Q \right) 
&= - \sum_{x \in \mathcal{X}} p(x) \log \left( q(x) \right) dx \\
&= - \mathbb{E}_p\left[\log \left( q(x) \right)\right] \\
\end{split}
$$

#### range
- The **minimum** cross-entropy is reached when $P=Q$ in which case it reduces to the **entropy** of $P$:

$$
H(P, Q) = H(P) \quad \text{if and only if} \quad P = Q
$$

- can go to infinity if there are regions where  $p(x) > 0$ but $q(x) = 0$ because $\log \left(q(x)\right)=\log \left(0\right) = -\infty$, and thus the expectation $-\mathbb{E}_{x \sim P}[\log q(x)]$ becomes infinite.

$$
\text{supp}(P) \nsubseteq \text{supp}(Q)
$$




### entropy
- measure of the **average amount of information** contained in an observation of a [[random variable]] in bits (if the $\log_2$ is used)
- in other words the average amount of removed uncertainty by an observation 
- for a discrete random variable with the [[probability function]] $p_X$ the [[entropy]] is defined as follows

$$
H(X) = \mathbb{E}\left[-\log\left(p_X(X)\right)\right] = - \sum p_X(x_i) \log\left(p_X(x_i)\right)
$$

- $H(X)$ is positive, and its maximum value depends on the [[distribution]] of $X$
##### example
- [[bernoulli distribution]] with $p=0.9$ and $p=0.5$
- We see that the entropy is **higher** when $p=0.5$, indicating that this outcome is **more uncertain** and thus contains **more information per observation**.

$$
\begin{split}
H(X) &= - 0.1 \cdot \log_2(0.1) - 0.9 \cdot \log_2(0.9) = 0.33 + 0.14 = 0.47 \\
H(X) &= - 0.5 \cdot \log_2(0.5) - 0.5 \cdot \log_2(0.5) = \frac{1}{2} + \frac{1}{2} = 1 \\
\end{split}
$$

### differential entropy
- for continuous random variables the concept of [[entropy]] can be extended
- does not have an intuitive interpretation other than **measurement for uncertainty or spread**
- other than the [[entropy]] the differential entropy can be negative and is sensitive to scaling

- for a continuous random variable with the [[probability density function (PDF)]] $f_X$ the differential entropy is defined as follows

$$
H(X) = \mathbb{E}\left[-\log\left(f_X(X)\right)\right] = - \int_\mathbb{R} f_X(x) \log\left(f_X(x)\right) dx
$$
##### example
- [[exponential distribution]]

$$
\begin{split}
H(X) 
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \ln\left(\lambda e^{-\lambda x})\right) dx \\
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \left(\ln(\lambda)  -\lambda x\right) dx \\
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \ln(\lambda) dx + \lambda \int_\mathbb{R} \lambda e^{-\lambda x}  x dx \\
&= - \ln(\lambda) + \lambda \int_\mathbb{R}  \mathbb{E}[X] \\
&= - \ln(\lambda) + \frac{\lambda}{\lambda} \\
&= 1 - \ln(\lambda) \\
\end{split}
$$

- the higher $\lambda$ is the less the PDF spreads thus $1-\ln(2)=0.3<1-\ln(1)=1$

Tags: mathematics statistics SS25
<!--ID: 1748278959148-->
END