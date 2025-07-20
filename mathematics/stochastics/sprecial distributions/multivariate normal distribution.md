### multivariate normal distribution

- Let $X = (X_1, ..., X_d)^\top$ be a [[random variable]] in $\mathbb{R}^d$
- $X$ has a [[multivariate normal distribution]] if $\mathbb{E}[X] = \mu \in \mathbb{R}^d$ and $\mathrm{Var}[X] = \Sigma \in \mathbb{R}^{d \times d}$, where $\Sigma$ is [[positive definite|positive semi definite]]

The probability density function is:
$$
f(x) 
= \frac{1}{\sqrt{(2\pi)^d \det(\Sigma)}} 
\exp\left(-\frac{1}{2} (x - \mu)^\top \Sigma^{-1} (x - \mu) \right)
$$



### linear transformations

If $X \sim \mathcal{N}(\mu, \Sigma)$, and $A \in \mathbb{R}^{k \times d}$, $b \in \mathbb{R}^k$, then:
$$
AX + b \sim \mathcal{N}(A\mu + b, A\Sigma A^\top)
$$



### addition of independent gaussians

If $X \sim \mathcal{N}(\mu_X, \Sigma_X)$, $Y \sim \mathcal{N}(\mu_Y, \Sigma_Y)$, and $X \perp\!\!\!\perp Y$, then:

$$
X + Y \sim \mathcal{N}(\mu_X + \mu_Y, \Sigma_X + \Sigma_Y)
$$
# ---------------------------


START
Basic
[[multivariate normal distribution]]
- [[probability density function (PDF)]]

Back: 
### multivariate normal distribution

- Let $X = (X_1, ..., X_d)^\top$ be a [[random variable]] in $\mathbb{R}^d$
- $X$ has a [[multivariate normal distribution]] if $\mathbb{E}[X] = \mu \in \mathbb{R}^d$ and $\mathrm{Var}[X] = \Sigma \in \mathbb{R}^{d \times d}$, where $\Sigma$ is [[positive definite|positive semi definite]]

The probability density function is:
$$
f(x) 
= \frac{1}{\sqrt{(2\pi)^d \det(\Sigma)}} 
\exp\left(-\frac{1}{2} (x - \mu)^\top \Sigma^{-1} (x - \mu) \right)
$$



### linear transformations

If $X \sim \mathcal{N}(\mu, \Sigma)$, and $A \in \mathbb{R}^{k \times d}$, $b \in \mathbb{R}^k$, then:
$$
AX + b \sim \mathcal{N}(A\mu + b, A\Sigma A^\top)
$$



### addition of independent gaussians

If $X \sim \mathcal{N}(\mu_X, \Sigma_X)$, $Y \sim \mathcal{N}(\mu_Y, \Sigma_Y)$, and $X \perp\!\!\!\perp Y$, then:

$$
X + Y \sim \mathcal{N}(\mu_X + \mu_Y, \Sigma_X + \Sigma_Y)
$$

Tags: mathematics statistics SS25
<!--ID: 1717956125284-->
END


START
Basic
[[multivariate normal distribution]]
- [[probability density function (PDF)]]
- linear transformations
- addition

Back: 
### multivariate normal distribution

- Let $X = (X_1, ..., X_d)^\top$ be a [[random variable]] in $\mathbb{R}^d$
- $X$ has a [[multivariate normal distribution]] if $\mathbb{E}[X] = \mu \in \mathbb{R}^d$ and $\mathrm{Var}[X] = \Sigma \in \mathbb{R}^{d \times d}$, where $\Sigma$ is [[positive definite|positive semi definite]]

The probability density function is:
$$
f(x) 
= \frac{1}{\sqrt{(2\pi)^d \det(\Sigma)}} 
\exp\left(-\frac{1}{2} (x - \mu)^\top \Sigma^{-1} (x - \mu) \right)
$$

---

### linear transformations

If $X \sim \mathcal{N}(\mu, \Sigma)$, and $A \in \mathbb{R}^{k \times d}$, $b \in \mathbb{R}^k$, then:
$$
AX + b \sim \mathcal{N}(A\mu + b, A\Sigma A^\top)
$$

---

### addition of independent gaussians

If $X \sim \mathcal{N}(\mu_X, \Sigma_X)$, $Y \sim \mathcal{N}(\mu_Y, \Sigma_Y)$, and $X \perp\!\!\!\perp Y$, then:

$$
X + Y \sim \mathcal{N}(\mu_X + \mu_Y, \Sigma_X + \Sigma_Y)
$$

Tags: mathematics statistics SS25
<!--ID: 1753031200144-->
END