### multivariate normal distribution
- let $X = (X_1, ..., X_d)$ be a [[random variable]] in $\mathbb{R}^d$
- $X$ has a [[multivariate normal distribution]] if there exists $\mu \in \mathbb{R}^d$ and a [[positive definite]] [[matrix]] $A \in \mathbb{R}^{d \times d}$ duch that

$$
\mathbb{P}(X \leq x) = \int_{-\infty}^x \frac{1}{\sqrt{\det(2 \pi A)}} e^{1\frac{1}{2} \left\langle y - \mu , A^{-1} (y - \mu) \right\rangle}
$$

- with the [[expectation]] $\mu$ and the [[covariance]] [[matrix]] $A = \left(\mathbb{COV}[X_i, X_j]\right)_{i,j \in [d]}$


$$
X \sim \mathcal{N}(\mu, A) \Leftrightarrow \langle \lambda, X \rangle \sim \mathcal{N}\left(\langle \lambda, \mu \rangle, \langle \lambda, A \lambda \rangle\right)
$$


$$
X \sim \mathcal{N}\left(\mu_X, A_X\right), X \sim \mathcal{N}\left(\mu_Y, A_Y\right)
\Leftrightarrow 
X + Y \sim \mathcal{N}\left(\mu_X + \mu_Y, A_X + A_Y\right)
$$

### gaussian vectors

# ---------------------------


START
Basic
[[multivariate normal distribution]]
- definition
- properties regarding [[multiplication]] and [[addition]]
Back: 
### multivariate normal distribution
- let $X = (X_1, ..., X_d)$ be a [[random variable]] in $\mathbb{R}^d$
- $X$ has a [[multivariate normal distribution]] if there exists $\mu \in \mathbb{R}^d$ and a [[positive definite]] [[matrix]] $A \in \mathbb{R}^{d \times d}$ duch that

$$
\mathbb{P}(X \leq x) = \int_{-\infty}^x \frac{1}{\sqrt{\det(2 \pi A)}} e^{1\frac{1}{2} \left\langle y - \mu , A^{-1} (y - \mu) \right\rangle}
$$

- with the [[expectation]] $\mu$ and the [[covariance]] [[matrix]] $A = \left(\mathbb{COV}[X_i, X_j]\right)_{i,j \in [d]}$


$$
X \sim \mathcal{N}(\mu, A) \Leftrightarrow \langle \lambda, X \rangle \sim \mathcal{N}\left(\langle \lambda, \mu \rangle, \langle \lambda, A \lambda \rangle\right)
$$


$$
X \sim \mathcal{N}\left(\mu_X, A_X\right), X \sim \mathcal{N}\left(\mu_Y, A_Y\right)
\Leftrightarrow 
X + Y \sim \mathcal{N}\left(\mu_X + \mu_Y, A_X + A_Y\right)
$$

Tags: mathematics statistics
<!--ID: 1717956125284-->
END