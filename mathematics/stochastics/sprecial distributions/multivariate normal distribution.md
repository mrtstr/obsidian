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

### gaussian conditional distribution

given a gaussian vectors 

$$
\left[\begin{matrix}
X \\ Y
\end{matrix}\right]
\sim \mathcal{N}\left(
\left[\begin{matrix}
\mu_X \\ \mu_Y
\end{matrix}\right],
\left[\begin{matrix}
\Sigma_{XX} & \Sigma_{XY} \\
\Sigma_{YX} & \Sigma_{YY} \\
\end{matrix}\right]
\right)
$$

the parameters of the condition distribution $P_{Y|X}$ are as follows

$$
\begin{split}
\mu_{Y|X=x} &= \mu_{Y} + \Sigma_{YX}\Sigma_{XX}^{-1}(x-\mu_X) \\
\Sigma_{Y|X=x} &= \Sigma_{YY} + \Sigma_{YX}\Sigma_{XX}^{-1}\Sigma_{XY}
\end{split}
$$
# ---------------------------

START
Basic
[[multivariate normal distribution]]
- given the joint distribution of two gaussian vectos
- hat are the parameters of the joint distribution  $P_{Y|X}$ 

Back: 
### gaussian conditional distribution

given a gaussian vectors 

$$
\left[\begin{matrix}
X \\ Y
\end{matrix}\right]
\sim \mathcal{N}\left(
\left[\begin{matrix}
\mu_X \\ \mu_Y
\end{matrix}\right],
\left[\begin{matrix}
\Sigma_{XX} & \Sigma_{XY} \\
\Sigma_{YX} & \Sigma_{YY} \\
\end{matrix}\right]
\right)
$$

the parameters of the condition distribution $P_{Y|X}$ are as follows

$$
\begin{split}
\mu_{Y|X=x} &= \mu_{Y} + \Sigma_{YX}\Sigma_{XX}^{-1}(x-\mu_X) \\
\Sigma_{Y|X=x} &= \Sigma_{YY} + \Sigma_{YX}\Sigma_{XX}^{-1}\Sigma_{XY}
\end{split}
$$
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
<!--ID: 1753277456047-->
END

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