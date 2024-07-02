### one sided gauss test
- given a sample $X_1, ..., X_n \sim \mathcal{N}(\mu, \sigma^2)$ with a known $\sigma$ and $\Theta = \{\mu \in \mathbb{R}\}$ 

#### upper bound
$$
\begin{split}
H_0: \mu \leq \mu_0 \\
H_1: \mu > \mu_0 \\
\end{split}
$$

- reject $H_0$ if $\bar X_n > \mu_o + \frac{z_{1-\alpha} \sigma}{\sqrt{n}}$ 
$$
\varphi(X_1, ..., X_n) = 
\left\{\begin{matrix}
1 &\qquad \text{if } \bar X_n > \mu_o + \frac{z_{1-\alpha} \sigma}{\sqrt{n}} \\
0 &
\end{matrix}
\right.
$$

$$
\begin{split}
\beta_\varphi(\mu) 
&= \mathbb{E}_\mu [\varphi] \\
&= 1 \cdot \mathbb{P}\left(\bar X_n > \mu_o + \frac{z_{1-\alpha} \sigma}{\sqrt{n}}\right) + 0 \cdot \mathbb{P}(...)\\
&= \mathbb{P}\left(\bar X_n > \mu_o + \frac{z_{1-\alpha} \sigma}{\sqrt{n}}\right) \\
&= \mathbb{P}\left( \sqrt{n} \frac{\bar X_n - \mu}{\sigma} > \sqrt{n} \frac{\mu_o - \mu}{\sigma}  + z_{1-\alpha}\right) \\
&=1 - \Phi\left(  \sqrt{n} \frac{\mu_o - \mu}{\sigma}  + z_{1-\alpha}\right) \\
\end{split}
$$


#### lower bound
$$
\begin{split}
H_0: \mu \geq \mu_0 \\
H_1: \mu < \mu_0 \\
\end{split}
$$

- reject $H_0$ if $\bar X_n < \mu_o - \frac{z_{1-\alpha} \sigma}{\sqrt{n}}$ 
$$
\varphi(X_1, ..., X_n) = 
\left\{\begin{matrix}
1 &\qquad \text{if } \bar X_n < \mu_o - \frac{z_{1-\alpha} \sigma}{\sqrt{n}} \\
0 &
\end{matrix}
\right.
$$

$$
\begin{split}
\beta_\varphi(\mu) 
&= \mathbb{E}_\mu [\varphi] \\
&= 1 \cdot \mathbb{P}\left(\bar X_n < \mu_o - \frac{z_{1-\alpha} \sigma}{\sqrt{n}}\right) + 0 \cdot \mathbb{P}(...)\\
&= \mathbb{P}\left(\bar X_n < \mu_o - \frac{z_{1-\alpha} \sigma}{\sqrt{n}}\right) \\
&= \mathbb{P}\left( \sqrt{n} \frac{\bar X_n - \mu}{\sigma} < \sqrt{n} \frac{\mu_o - \mu}{\sigma}  - z_{1-\alpha}\right) \\
&=\Phi\left(  \sqrt{n} \frac{\mu_o - \mu}{\sigma}  - z_{1-\alpha}\right) \\
\end{split}
$$

# -----------------------



![[confidence set#confidence set for the mean of the normal distribution]]


![[statistical test#statistical test]]



# anki


START
Basic
[[one sided gauss test]] with an upper bound
- [[statistical test]] $\varphi$
- power function $\beta_\varphi$
Back: 
### one sided gauss test
- given a sample $X_1, ..., X_n \sim \mathcal{N}(\mu, \sigma^2)$ with a known $\sigma$ and $\Theta = \{\mu \in \mathbb{R}\}$ 

#### upper bound
$$
\begin{split}
H_0: \mu \leq \mu_0 \\
H_1: \mu > \mu_0 \\
\end{split}
$$

- reject $H_0$ if $\bar X_n > \mu_o + \frac{z_{1-\alpha} \sigma}{\sqrt{n}}$ 
$$
\varphi(X_1, ..., X_n) = 
\left\{\begin{matrix}
1 &\qquad \text{if } \bar X_n > \mu_o + \frac{z_{1-\alpha} \sigma}{\sqrt{n}} \\
0 &
\end{matrix}
\right.
$$

$$
\begin{split}
\beta_\varphi(\mu) 
&= \mathbb{E}_\mu [\varphi] \\
&= 1 \cdot \mathbb{P}\left(\bar X_n > \mu_o + \frac{z_{1-\alpha} \sigma}{\sqrt{n}}\right) + 0 \cdot \mathbb{P}(...)\\
&= \mathbb{P}\left(\bar X_n > \mu_o + \frac{z_{1-\alpha} \sigma}{\sqrt{n}}\right) \\
&= \mathbb{P}\left( \sqrt{n} \frac{\bar X_n - \mu}{\sigma} > \sqrt{n} \frac{\mu_o - \mu}{\sigma}  + z_{1-\alpha}\right) \\
&=1 - \Phi\left(  \sqrt{n} \frac{\mu_o - \mu}{\sigma}  + z_{1-\alpha}\right) \\
\end{split}
$$



_________________________________

### statistical test
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ 
- with a [[disjoint]] seperated [[parameter space]] $\Theta_0$ and $\Theta_1 = \Theta \setminus \Theta_0$ 
- every [[statistics]] $\varphi: \mathfrak{X} \to [0,1]$ is called a [[statistical test]] of the **nullhypothesis** $\Theta_0$ against $\Theta_1$
- given an observation $x \in \mathfrak{X}$ the [[statistics]] $\varphi(x) \in [0,1]$ is the properbility of deciding for the alternative $\Theta_1$ thus the **rejection rate**

$$
\begin{split}
\varphi(X) = \mathbb{P}\left(H_1 | X\right)
\end{split}
$$

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
\beta_\varphi (\vartheta) = \mathbb{E}_{\vartheta} [\varphi] = \mathbb{E}_{x \sim \mathbb{P}_\vartheta} [\varphi(x)]
$$

- the power function $\beta_\varphi$ can be interpreted as the **expected rejection rate** for a given parameter [[set]] $\vartheta$ if the obervations are sampled $x \sim \mathbb{P}_\vartheta$ from the [[distribution]] $\mathbb{P}_\vartheta$
- ideally $\beta_\varphi (\vartheta)$ should be close to $0$ for $\vartheta \in \Theta_0$ and close to $1$ for $\vartheta \in \Theta_1$


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
<!--ID: 1719861660028-->
END



START
Basic
[[one sided gauss test]] with an lower bound
- [[statistical test]] $\varphi$
- power function $\beta_\varphi$
Back: 
### one sided gauss test
- given a sample $X_1, ..., X_n \sim \mathcal{N}(\mu, \sigma^2)$ with a known $\sigma$ and $\Theta = \{\mu \in \mathbb{R}\}$ 


#### lower bound
$$
\begin{split}
H_0: \mu \geq \mu_0 \\
H_1: \mu < \mu_0 \\
\end{split}
$$

- reject $H_0$ if $\bar X_n < \mu_o - \frac{z_{1-\alpha} \sigma}{\sqrt{n}}$ 
$$
\varphi(X_1, ..., X_n) = 
\left\{\begin{matrix}
1 &\qquad \text{if } \bar X_n < \mu_o - \frac{z_{1-\alpha} \sigma}{\sqrt{n}} \\
0 &
\end{matrix}
\right.
$$

$$
\begin{split}
\beta_\varphi(\mu) 
&= \mathbb{E}_\mu [\varphi] \\
&= 1 \cdot \mathbb{P}\left(\bar X_n < \mu_o - \frac{z_{1-\alpha} \sigma}{\sqrt{n}}\right) + 0 \cdot \mathbb{P}(...)\\
&= \mathbb{P}\left(\bar X_n < \mu_o - \frac{z_{1-\alpha} \sigma}{\sqrt{n}}\right) \\
&= \mathbb{P}\left( \sqrt{n} \frac{\bar X_n - \mu}{\sigma} < \sqrt{n} \frac{\mu_o - \mu}{\sigma}  - z_{1-\alpha}\right) \\
&=\Phi\left(  \sqrt{n} \frac{\mu_o - \mu}{\sigma}  - z_{1-\alpha}\right) \\
\end{split}
$$

_________________________________

### statistical test
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ 
- with a [[disjoint]] seperated [[parameter space]] $\Theta_0$ and $\Theta_1 = \Theta \setminus \Theta_0$ 
- every [[statistics]] $\varphi: \mathfrak{X} \to [0,1]$ is called a [[statistical test]] of the **nullhypothesis** $\Theta_0$ against $\Theta_1$
- given an observation $x \in \mathfrak{X}$ the [[statistics]] $\varphi(x) \in [0,1]$ is the properbility of deciding for the alternative $\Theta_1$ thus the **rejection rate**

$$
\begin{split}
\varphi(X) = \mathbb{P}\left(H_1 | X\right)
\end{split}
$$

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
\beta_\varphi (\vartheta) = \mathbb{E}_{\vartheta} [\varphi] = \mathbb{E}_{x \sim \mathbb{P}_\vartheta} [\varphi(x)]
$$

- the power function $\beta_\varphi$ can be interpreted as the **expected rejection rate** for a given parameter [[set]] $\vartheta$ if the obervations are sampled $x \sim \mathbb{P}_\vartheta$ from the [[distribution]] $\mathbb{P}_\vartheta$
- ideally $\beta_\varphi (\vartheta)$ should be close to $0$ for $\vartheta \in \Theta_0$ and close to $1$ for $\vartheta \in \Theta_1$

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


#### randomized vs non-random tests
- non-random tests if $\forall x \in \mathfrak{X}: \varphi(x) \in \{0,1\}$ and random otherwise ($\varphi(x) \in [0,1]$)


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
<!--ID: 1719861660033-->
END