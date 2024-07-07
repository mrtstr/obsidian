### students t test
- given a sample $X_1, ..., X_n \sim \mathcal{N}(\mu, \sigma^2)$  
- with the following [[statistical estimator]] of $\mu$ and $\sigma^2$
$$
\begin{split}
\bar{X}_n &= \frac{1}{n} \sum_{i=1}^n X_i \\
S^2_n &= \frac{1}{n-1} \sum_{i=1}^n \left(X_i - \bar{X}_n\right)^2 \\
\end{split}
$$

### two sided
$$
\begin{split}
H_0: \mu = \mu_0 \\
H_1: \mu \neq \mu_0 \\
\end{split}
$$

$$
\varphi(X_1, ..., X_n) = 
\left\{\begin{matrix}
1 &\qquad \text{if } \sqrt{n} \frac{|\bar X_n - \mu|}{S_n} > t_{n-1,1-\alpha} \\
0 &
\end{matrix}
\right.
$$

#### right sided
$$
\begin{split}
H_0: \mu \leq \mu_0 \\
H_1: \mu > \mu_0 \\
\end{split}
$$


$$
\varphi(X_1, ..., X_n) = 
\left\{\begin{matrix}
1 &\qquad \text{if } \bar X_n > \mu_o + \frac{t_{n-1,1-\alpha} S_n}{\sqrt{n}} \\
0 &
\end{matrix}
\right.
$$

#### left sided
$$
\begin{split}
H_0: \mu \geq \mu_0 \\
H_1: \mu < \mu_0 \\
\end{split}
$$

$$
\varphi(X_1, ..., X_n) = 
\left\{\begin{matrix}
1 &\qquad \text{if } \bar X_n < \mu_o - \frac{t_{n-1,1-\alpha} S_n}{\sqrt{n}} \\
0 &
\end{matrix}
\right.
$$

# -------------------------


![[two sided gauss test#two sided gauss test]]





START
Basic
[[students t test]]:
- $H_0$
- $H_1$
- $\varphi(X)$
for
- two sided
- left sided
- right sided
Back: 
### students t test
- given a sample $X_1, ..., X_n \sim \mathcal{N}(\mu, \sigma^2)$  
- with the following [[statistical estimator]] of $\mu$ and $\sigma^2$
$$
\begin{split}
\bar{X}_n &= \frac{1}{n} \sum_{i=1}^n X_i \\
S^2_n &= \frac{1}{n-1} \sum_{i=1}^n \left(X_i - \bar{X}_n\right)^2 \\
\end{split}
$$

### two sided
$$
\begin{split}
H_0: \mu = \mu_0 \\
H_1: \mu \neq \mu_0 \\
\end{split}
$$

$$
\varphi(X_1, ..., X_n) = 
\left\{\begin{matrix}
1 &\qquad \text{if } \sqrt{n} \frac{|\bar X_n - \mu|}{S_n} > t_{n-1,1-\alpha} \\
0 &
\end{matrix}
\right.
$$

#### right sided
$$
\begin{split}
H_0: \mu \leq \mu_0 \\
H_1: \mu > \mu_0 \\
\end{split}
$$


$$
\varphi(X_1, ..., X_n) = 
\left\{\begin{matrix}
1 &\qquad \text{if } \bar X_n > \mu_o + \frac{t_{n-1,1-\alpha} S_n}{\sqrt{n}} \\
0 &
\end{matrix}
\right.
$$

#### left sided
$$
\begin{split}
H_0: \mu \geq \mu_0 \\
H_1: \mu < \mu_0 \\
\end{split}
$$

$$
\varphi(X_1, ..., X_n) = 
\left\{\begin{matrix}
1 &\qquad \text{if } \bar X_n < \mu_o - \frac{t_{n-1,1-\alpha} S_n}{\sqrt{n}} \\
0 &
\end{matrix}
\right.
$$

_________________________________

### statistical test
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ 
- with a [[disjoint]] seperated [[parameter space]] $\Theta_0$ and $\Theta_1 = \Theta \setminus \Theta_0$ 
- every [[statistics]] $\varphi: \mathfrak{X} \to [0,1]$ is called a [[statistical test]] of the **nullhypothesis** $\Theta_0$ against $\Theta_1$
- given an observation $x \in \mathfrak{X}$ the [[statistics]] $\varphi(x) \in [0,1]$ one if $H_1$ is true and zero otherwise

#### randomized vs non-random tests
- non-random tests if $\forall x \in \mathfrak{X}: \varphi(x) \in \{0,1\}$ and random otherwise ($\varphi(x) \in [0,1]$)
- for a non-random test $\varphi$ will look like this:

$$
\varphi\left(X_1, ..., X_n\right) = 
\left\{
\begin{matrix}
1 & \Leftrightarrow & \qquad\text{reject } H_0\\
0 & \Leftrightarrow & \qquad\text{dont reject } H_0\\
\end{matrix} \right.
$$
- for a randomized test $\varphi$ will look like this:
$$
\varphi\left(X_1, ..., X_n\right) = 
\left\{
\begin{matrix}
1 & \Leftrightarrow & \qquad\text{reject } H_0\\
\gamma(x) & \Leftrightarrow &  \\
0 & \Leftrightarrow & \qquad\text{dont reject } H_0\\
\end{matrix} \right.
$$


##### effective level of a [[statistical test]] $\varphi$
- the **effective level** of a [[statistical test]] $\varphi$ is defined as follows
$$
\sup_{\vartheta \in \Theta} \mathbb{E}_{\vartheta} [\varphi]
= \sup_{\vartheta \in \Theta} \mathbb{E}_{x \sim \mathbb{P}_\vartheta} [\varphi(x)]
$$
- it is the maximal value the [[expectation]] of the [[statistical test]] $\varphi$ can take with parameters from the nullhypothesis $\Theta_0$
- thus it is the maximal **expected rejection rate** that is possible with parameters from the nullhypothesis $\Theta_0$ (if the obervations are sampled $x \sim \mathbb{P}_\vartheta$ from the [[distribution]] $\mathbb{P}_\vartheta$)

##### test level of a [[statistical test]] $\varphi$
- a [[statistical test]] $\varphi$ is a test of level $\alpha$ if the following is true
$$
\sup_{\vartheta \in \Theta} \mathbb{E}_{\vartheta} [\varphi] \leq \alpha
$$
- the test level can be interpreted as the confidence level or an **upper bound for the expected rejection rate**

##### power function of a [[statistical test]] $\varphi$
- for a [[statistical test]] $\varphi$ the power function $\beta_\varphi: \Theta \to [0,1]$ is defined as follows 
$$
\beta_\varphi (\vartheta) = \mathbb{E}_{\vartheta} [\varphi] = \mathbb{E}_{x \sim \mathbb{P}_\vartheta} [\varphi(x)] = \mathbb{P}_\vartheta\left(H_1 | X\right)
$$

- the power function $\beta_\varphi$ can be interpreted as the **expected rejection rate** for a given parameter [[set]] $\vartheta$ if the obervations are sampled $x \sim \mathbb{P}_\vartheta$ from the [[distribution]] $\mathbb{P}_\vartheta$
- ideally $\beta_\varphi (\vartheta)$ should be close to $0$ for $\vartheta \in \Theta_0$ and close to $1$ for $\vartheta \in \Theta_1$

#### power function $\beta_\varphi (\vartheta)$ vs [[statistics]] $\varphi(x) \in [0,1]$ 
- $\varphi$ is a [[random variable]] that is one if $H_1$ is true and zero otherwise given the observation $X \in \mathfrak{X}$ 
$$
\varphi\left(X_1, ..., X_n\right) = 
\left\{
\begin{matrix}
1 & \Leftrightarrow & \qquad\text{reject } H_0\\
0 & \Leftrightarrow & \qquad\text{dont reject } H_0\\
\end{matrix} \right.
$$

- the power function is a deterministic $\beta_\varphi (\vartheta)$ evaluates $\mathbb{P}_\vartheta\left(H_1 | X\right)$ for a specific parameter $\vartheta$ 
- this is needed because we want to calculate the [[supremum]] of $\beta_\varphi (\vartheta)$ to extract a specific parameter $\vartheta_0$

$$
\beta_\varphi (\vartheta) = \mathbb{E}_{\vartheta} [\varphi] = \mathbb{E}_{x \sim \mathbb{P}_\vartheta} [\varphi(x)] = \mathbb{P}_\vartheta\left(H_1 | X\right)
$$


Tags: mathematics statistics
<!--ID: 1720361311122-->
END