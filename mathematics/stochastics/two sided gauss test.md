### two sided gauss test
- given a sample $X_1, ..., X_n \sim \mathcal{N}(\mu, \sigma^2)$ with a known $\sigma$ and $\Theta = \{\mu \in \mathbb{R}\}$ 

$$
\begin{split}
H_0: \mu = \mu_0 \\
H_1: \mu \neq \mu_0 \\
\end{split}
$$

- we want that $\mathbb{E}[\varphi(X)]=\mathbb{P}\left(H_1\right |X)= \alpha$ because we want to be $1-\alpha$ sure that $H_0$ is wrong

![[IMG-20240707-WA0000.jpg]]

$$
\begin{split}
\mathbb{P}\left(H_1\right | X) 
&=\mathbb{P}\left(\mu \neq \mu_0 \right | X) \\ 
&=\mathbb{P}\left(\bar X_n \neq \mu_0\right ) \\ 
&=\mathbb{P}\left(\sqrt{n} \frac{\bar X_n - \mu}{\sigma_0} \neq \sqrt{n} \frac{\mu_0 - \mu}{\sigma_0} \right)  \\
&=\mathbb{P}\left(\sqrt{n} \frac{|\bar X_n - \mu|}{\sigma_0} > \sqrt{n} \frac{\mu_0 - \mu}{\sigma_0} \right)  \\
&=\alpha\\
\frac{\alpha}{2} 
&=\mathbb{P}\left(\sqrt{n} \frac{\bar X_n - \mu}{\sigma_0} > \sqrt{n} \frac{\mu_0 - \mu}{\sigma_0} \right)  \\
&=1-\mathbb{P}\left(\sqrt{n} \frac{\bar X_n - \mu}{\sigma_0} \leq \sqrt{n} \frac{\mu_0 - \mu}{\sigma_0} \right)  \\
&=1-\Phi\left(\sqrt{n} \frac{\mu_0 - \mu}{\sigma_0}\right)  \\
\end{split}
$$


- resolving the quation to find the theshold $\mu$ for $\varphi(X)$ to have a test level $\alpha$
$$
\begin{split}
&1- \frac{\alpha}{2}
=\Phi\left(\sqrt{n} \frac{\mu_0 - \mu}{\sigma_0}\right) 
 \\
\Rightarrow& \Phi\left(1-\frac{\alpha}{2}\right) = \sqrt{n} \frac{\mu_0 - \mu}{\sigma_0} \\
\Rightarrow& \mu 
= \mu_0 - \frac{\Phi\left(1-\alpha\right)\sigma_0}{\sqrt{n}} \\
&= \mu_0 - \frac{z_{1-\alpha}\sigma_0}{\sqrt{n}} \\
\end{split}
$$


$$
\begin{split}


&\mathbb{P}\left(\sqrt{n} \frac{|\bar X_n - \mu|}{\sigma_0} > \sqrt{n} \frac{\mu_0 - \mu_0 + \frac{z_{1-\alpha}\sigma_0}{\sqrt{n}}}{\sigma_0} \right)  \\
=&\mathbb{P}\left(\sqrt{n} \frac{|\bar X_n - \mu|}{\sigma_0} > z_{1-\alpha} \right)  \\

\end{split}
$$

$$
\varphi(X_1, ..., X_n) = 
\left\{\begin{matrix}
1 &\qquad \text{if } \sqrt{n} \frac{|\bar X_n - \mu|}{\sigma_0} > z_{1-\frac{\alpha}{2}} \\
0 &
\end{matrix}
\right.
$$

- the power function of $\varphi$:
$$
\begin{split}
\beta_\varphi(\mu) 
&= \mathbb{E}_\mu [\varphi] \\
&= 1 \cdot \mathbb{P}_\mu\left(\sqrt{n} \frac{|\bar X_n - \mu|}{\sigma_0} > z_{1-\frac{\alpha}{2}}\right) + 0 \cdot \mathbb{P}(...)\\
&= \mathbb{P}_\mu\left(\sqrt{n} \frac{|\bar X_n - \mu|}{\sigma_0} > z_{1-\frac{\alpha}{2}}\right)\\
\end{split}
$$

# -----------------------

![[statistical test#statistical test]]





START
Basic
[[two sided gauss test]]
- given a sample $X_1, ..., X_n \sim \mathcal{N}(\mu, \sigma^2)$ with a known $\sigma$ and $\Theta = \{\mu \in \mathbb{R}\}$ 

$$
\begin{split}
H_0: \mu = \mu_0 \\
H_1: \mu \neq \mu_0 \\
\end{split}
$$

Back: 
### two sided gauss test
- given a sample $X_1, ..., X_n \sim \mathcal{N}(\mu, \sigma^2)$ with a known $\sigma$ and $\Theta = \{\mu \in \mathbb{R}\}$ 

$$
\begin{split}
H_0: \mu = \mu_0 \\
H_1: \mu \neq \mu_0 \\
\end{split}
$$

![[IMG-20240707-WA0000 1.jpg]]

- we want that $\mathbb{E}[\varphi(X)]=\mathbb{P}\left(H_1\right |X)=1 - \alpha$ because we want to be $1-\alpha$ sure that $H_0$ is wrong


$$
\varphi(X_1, ..., X_n) = 
\left\{\begin{matrix}
1 &\qquad \text{if } \sqrt{n} \frac{|\bar X_n - \mu|}{\sigma_0} > z_{1-\frac{\alpha}{2}} \\
0 &
\end{matrix}
\right.
$$

- the power function of $\varphi$:
$$
\begin{split}
\beta_\varphi(\mu) 
&= \mathbb{E}_\mu [\varphi] \\
&= 1 \cdot \mathbb{P}_\mu\left(\sqrt{n} \frac{|\bar X_n - \mu|}{\sigma_0} > z_{1-\frac{\alpha}{2}}\right) + 0 \cdot \mathbb{P}(...)\\
&= \mathbb{P}_\mu\left(\sqrt{n} \frac{|\bar X_n - \mu|}{\sigma_0} > z_{1-\frac{\alpha}{2}}\right)\\
\end{split}
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

### error types

##### type I error
- type I error if $H_0$ is rejected but $H_0$ is correct
- for a given parameter set $\vartheta \in \Theta_0$ the **type I error probability** is given by $\beta_\varphi (\vartheta)$
- thus the **type I error probability** is bounded by the **test level** $\alpha$
- concidered more servere and thus controlled by $\alpha$
→ only the rejection of a hypothesis $H_0$ is reliable

##### type II error
- type II error if $H_0$ is accepted but $H_1$ is correct
- for a given parameter set $\vartheta \in \Theta_1$ the **type II error probability** is given by $1-\beta_\varphi (\vartheta)$
- theoreticly bounded by $1 - \alpha$ but practicly uncontrolled
→ acceptence of $H_0$ is not reliable



### calculation
- given $\alpha$ and an observation $X$ and the [[random variable]] $\varphi$

$$
\varphi\left(X_1, ..., X_n\right) = 
\left\{
\begin{matrix}
1 & & \qquad\text{if } H_1\\
0 & & \qquad\text{else} \\
\end{matrix} \right.
$$

- we want that $\beta_\varphi=1 - \alpha$ with a hypothesis $H_1\left(\tau(\vartheta)\right)$ that is based on some characteristics $\tau(\vartheta)$ of $\mathbb{P}_\vartheta$

$$
\begin{split}
\mathbb{E}[\varphi]
&=1 \cdot\mathbb{P}\left(H_1\right |X) + 0 \cdot \mathbb{P}(...) \\
&=\mathbb{P}\left(H_1\right |X)  \\
&=1 - \alpha
\end{split}
$$

- we replace the characteristics $\tau(\vartheta)$ in the hypothesis $H_1$ with an [[statistical estimator]] $T(X)$ in the equation for the [[statistical test]] 
$$
\mathbb{P}\left(H_1\left(T(X)\right)|X\right )=1 - \alpha
$$ 
- we extract some kind of theshold from the equation for $\varphi$ to be a test of level $\alpha$ and plug the theshold $\vartheta$ in $\varphi(X)$ to finalize the definition of $\varphi$ 


$$
\varphi\left(X_1, ..., X_n\right) = 
\left\{
\begin{matrix}
1 &  \qquad\text{if } \mathbb{P}\left(H_1\left(T(X)\right), \vartheta|X\right )\\
0 &  \qquad\text{else} \\
\end{matrix} \right.
$$

- now we can calculate the power function $\beta(\vartheta)=\mathbb{E}_\vartheta\left[\varphi(X)\right]$

$$
\begin{split}
\beta_\varphi(\mu) 
&= \mathbb{E}_\mu [\varphi] \\
&= 1 \cdot \mathbb{P}\left(H_1\left(T(X)\right), \vartheta|X\right ) + 0 \cdot \mathbb{P}(...)\\
\end{split}
$$

### [[confidence set]] for the mean of the [[normal distribution]]
- given a sample $X_1, ..., X_n \sim \mathcal{N}(\mu, \sigma^2)$ with a known $\sigma$ the [[confidence set]] $\mathcal{S}$ for $\mu$ is the following
- with the following [[statistical estimator]] of $\mu$

$$
\bar{X}_n = \frac{1}{n} \sum_{i=1}^n X_i 
$$

- $\Phi^{-1}$ is the [[quantile function]] of the [[standard normal distribution]]

$$
\begin{split}
\mathcal{S} 
&= \left[\bar{X}_n - \frac{\sigma \cdot z_{\frac{\alpha-1}{2}}}{\sqrt{n}}, \bar{X}_n + \frac{\sigma \cdot z_{\frac{\alpha-1}{2}}}{\sqrt{n}}\right] \\
z_{\frac{\alpha-1}{2}} &= \Phi^{-1}\left(\frac{\alpha-1}{2}\right)
\end{split}
$$

#### proof
- let $Y=\frac{1}{n} \sum_{i=1}^n X_i$ 
$$
\begin{split}
Y &=\frac{1}{n} \sum_{i=1}^n X_i \sim \mathcal{N}\left(\mu, \frac{\sigma^2}{2}\right) \\
\Rightarrow F_Y(y) &= \frac{\alpha-1}{2}
\end{split}
$$
- if $S=[l, u]$ we can calculate the boundarys of $S$ with the [[quantile function]] of $Y$
$$
\begin{split}
\mathbb{P}(Y \geq l) &= F_Y(l) = 1 - \frac{\alpha-1}{2} \\
\Rightarrow l &= F_Y^{-1}\left(1 - \frac{\alpha-1}{2}\right) \\
\mathbb{P}(Y \leq u)&=F_Y(u) = \frac{\alpha-1}{2} \\
\Rightarrow u &= F_Y^{-1}\left(\frac{\alpha-1}{2}\right) \\
\end{split}
$$

- since $Y$ has a [[normal distribution]] we can perform a standard normal transformation
- with $\Phi(x)$ and $\Phi^{-1}(q)$ being the [[cumulative distribution function (CDF)]] and [[quantile function]] of the [[standard normal distribution]]  

$$
\begin{split}
F^{-1}_Y(q) 
&= \Phi^{-1}\left(q\right) \sigma_y + \mu_Y\\
&= \Phi^{-1}\left(q\right) \sqrt{\frac{\sigma^2}{n}} + \mu\\
&= \Phi^{-1}\left(q\right) \frac{\sigma}{\sqrt{n}} + \mu\\
\end{split}
$$

$$
\begin{split}
u 
&= F_Y^{-1}\left(\frac{\alpha-1}{2}\right) \\
&=\Phi^{-1}\left(\frac{\alpha-1}{2}\right) \frac{\sigma}{\sqrt{n}} + \mu \\
&=z_\left(\frac{\alpha-1}{2}\right) \frac{\sigma}{\sqrt{n}} + \bar{X}_n \\
l &= \bar{X}_n - z_\left(\frac{\alpha-1}{2}\right) \frac{\sigma}{\sqrt{n}} \qquad \text{(follows from symmetry)}  \\
\end{split}
$$



Tags: mathematics statistics
<!--ID: 1720360441748-->
END