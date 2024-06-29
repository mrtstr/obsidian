### confidence set
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ and [[set]] $\mathcal{S}$ with a characteristics $\tau: \Theta \to \mathcal{S}$ 
- a [[function]] $C: \mathfrak{X} \to \mathcal{P}(S)$ that is mapping the obervation space to the [[power set]] of $\mathcal{S}$ is called the [[confidence set]] of $\tau$ to the level of $1 - \alpha$ if the following is true

$$
\mathbb{P}_\vartheta \left\{C \ni \tau(\vartheta)\right\} \geq 1-\alpha
$$
 - for a given observation we want to be at least $1 - \alpha$ sure that the true value is in $C$
 - we want $C$ to be as small as possible because $C = \mathcal{S}$ would statisfy the condition but would not contain any information

### [[confidence set]] for the mean of the [[normal distribution]]
- given a sample $X_1, ..., X_n \sim \mathcal{N}(\mu, \sigma^2)$ with a known $\sigma$ the [[confidence set]] $\mathcal{S}$ for $\mu$ is the following
- with the following [[statistical estimator]] of $\mu$

$$
\bar{X}_n = \frac{1}{n} \sum_{i=1}^n X_i 
$$

- $\Phi^{-1}$ is the [[quantile function]] of the [[standard normal distribution]]

$$
\begin{split}
$\mathcal{S}$ 
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


### [[confidence set]] for the [[normal distribution]] (mean and [[variance]] unknown)
- given a sample $X_1, ..., X_n \sim \mathcal{N}(\mu, \sigma^2)$  
- with the following [[statistical estimator]] of $\mu$ and $\sigma^2$
$$
\begin{split}
\bar{X}_n &= \frac{1}{n} \sum_{i=1}^n X_i \\
S^2_n &= \frac{1}{n-1} \sum_{i=1}^n \left(X_i - \bar{X}_n\right)^2 \\
\end{split}
$$
- the [[confidence set]] $\mathcal{S}$ for $\mu$ is the following
- with $t_{\frac{n-1;\alpha-1}{2}}$ being the [[quantile function]] of the [[students t distribution]] with a degree of freedom $n-1$

$$
\begin{split}
\mathcal{S}
&= \left[\bar{X}_n - \frac{S_n \cdot t_{\frac{n-1;\alpha-1}{2}}}{\sqrt{n}}, \bar{X}_n + \frac{\sigma \cdot t_{\frac{n-1;\alpha-1}{2}}}{\sqrt{n}}\right] \\
\end{split}
$$


### [[confidence set]] for a sample from a general [[random variable]]
- given a sample $X_1, ..., X_n$ i.i.d. from the same [[distribution]] with the [[cumulative distribution function (CDF)]] $F_X(x)$
- with the following unbiased [[statistical estimator]] for the [[expectation]] and the [[variance]] for $X$: $\mu$ and $\sigma^2$
$$
\begin{split}
\bar{X}_n &= \frac{1}{n} \sum_{i=1}^n X_i \\
S^2_n &= \frac{1}{n-1} \sum_{i=1}^n \left(X_i - \bar{X}_n\right)^2 \\
\end{split}
$$


- the [[confidence set]] $\mathcal{S}_n$ for $\mu$ is converging to the following
$$
\begin{split}
\lim_{n \to \infty}\mathcal{S}_n
&= \left[\bar{X}_n - \frac{S_n \cdot z_{\frac{\alpha-1}{2}}}{\sqrt{n}}, \bar{X}_n + \frac{\sigma \cdot z_{\frac{\alpha-1}{2}}}{\sqrt{n}}\right] \\
\end{split}
$$

- with $z_\frac{1-\alpha}{2} = F^{-1}_X\left(\frac{1-\alpha}{2}\right)$ being the [[quantile function]] of $X$
#### proof

$$
\begin{split}
Y 
=&\bar{X}_n= \frac{1}{n} \sum_{i=1}^n X_i \\
F_Y(y) 
=& \mathbb{P}(Y \leq y) \\
=& \mathbb{P}\left(\frac{1}{n} \sum_{i=1}^n X_i \leq y\right) \\
=& \mathbb{P}\left( \sum_{i=1}^n X_i \leq n \cdot y\right) \\

\end{split}
$$


$$
\begin{split}
\mathbb{P}(Y \geq l) &= F_Y(l) = 1 - \frac{\alpha-1}{2} \\
\Rightarrow l &= F_Y^{-1}\left(1 - \frac{\alpha-1}{2}\right) \\
\mathbb{P}(Y \leq u)&=F_Y(u) = \frac{\alpha-1}{2} \\
\Rightarrow u &= F_Y^{-1}\left(\frac{\alpha-1}{2}\right) \\
\end{split}
$$

# -----------------------

![[normal distribution#probability density function (PDF)]]


![[normal distribution#random sample from a normal distribution]]

![[normal distribution#standard normal transformation]]

![[normal distribution#linear map Linear Functions of normal distribution normal distributed random variable random variables]]

![[power set#power set]]



# anki


START
Basic
[[confidence set]]
- definition
- interpretation

Back: 
### confidence set
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ and [[set]] $\mathcal{S}$ with a characteristics $\tau: \Theta \to \mathcal{S}$ 
- a [[function]] $C: \mathfrak{X} \to \mathcal{P}(S)$ that is mapping the obervation space to the [[power set]] of $\mathcal{S}$ is called the [[confidence set]] of $\tau$ to the level of $1 - \alpha$ if the following is true

$$
\mathbb{P}_\vartheta \left\{C \ni \tau(\vartheta)\right\} \geq 1-\alpha
$$
- for a given observation we want to be at least $1 - \alpha$ sure that the true value is in $C$
- we want $C$ to be as small as possible because $C = \mathcal{S}$ would statisfy the condition but would not contain any information

_________________________________


### power set
- given a set $A$ the [[power set]] $\mathcal{P}(S)$ is a set that contains all subsets of $S$

$$
\mathcal{P}(S) = \{A \mid A \subseteq S \}
$$
- [[cardinality]] of a [[power set]]:
$$
\left|\mathcal{P}(S) \right| = 2^{\left|S\right|} 
$$

Tags: mathematics statistics
<!--ID: 1719674487788-->
END



START
Basic
- given a sample $X_1, ..., X_n \sim \mathcal{N}(\mu, \sigma^2)$ with a known $\sigma$ the [[confidence set]] $S$ for $\mu$ is the following
- [[confidence set]] of $\mu$ as  a function of the [[quantile function]] of the [[standard normal distribution]] $\Phi^{-1}$ (with proof)

$$
\bar{X}_n = \frac{1}{n} \sum_{i=1}^n X_i 
$$

Back: 
### [[confidence set]] for the mean of the [[normal distribution]]
- given a sample $X_1, ..., X_n \sim \mathcal{N}(\mu, \sigma^2)$ with a known $\sigma$ the [[confidence set]] $S$ for $\mu$ is the following
- 

$$
\begin{split}
S 
&= \left[\bar{X}_n - \frac{\sigma \cdot z_{\frac{\alpha-1}{2}}}{\sqrt{n}}, \bar{X}_n + \frac{\sigma \cdot z_{\frac{\alpha-1}{2}}}{\sqrt{n}}\right] \\
\bar{X}_n &= \frac{1}{n} \sum_{i=1}^n X_i \\
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


_________________________________
### confidence set
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ and [[set]] $\mathcal{S}$ with a characteristics $\tau: \Theta \to \mathcal{S}$ 
- a [[function]] $C: \mathfrak{X} \to \mathcal{P}(S)$ that is mapping the obervation space to the [[power set]] of $\mathcal{S}$ is called the [[confidence set]] of $\tau$ to the level of $1 - \alpha$ if the following is true

$$
\mathbb{P}_\vartheta \left\{C \ni \tau(\vartheta)\right\} \geq 1-\alpha
$$
- for a given observation we want to be at least $1 - \alpha$ sure that the true value is in $C$
- we want $C$ to be as small as possible because $C = \mathcal{S}$ would statisfy the condition but would not contain any information


### [[random sample]] from a [[normal distribution]]

The mean from a [[random sample]] of the sixe $n$ from a [[normal distribution]] is again [[normal distribution|normal distributed]] with a mean $\mu$ and a [[variance]] $\frac{\sigma^2}{n}$. 
$$
\begin{split}
X_i &\sim f_{X}\left(x | \mu, \sigma^2\right) \: i.i.d \\
\Rightarrow \bar{X_n}&=\frac{1}{n}\sum_{i=1}^nX_i \sim f_{\bar{X_n}}\left(\bar{x} \mid  \mu, \frac{\sigma^2}{n} \right) 
\end{split}
$$
proof
Since the folowing is true
$$
\begin{split}
X_i &\sim f_{X_i}\left(x_i | \mu_i, \sigma_i^2\right) \\
\Rightarrow Y&=\sum_{i=1}^n a_i +b \sim f_{Y}\left(y \mid \sum_{i=1}^n a_i \mu_i + b, \sum_{i=1}^n a_i^2 \sigma_i^2\right) 
\end{split}
$$
$$
\begin{split}
\bar{X_n}&=\frac{1}{n}\sum_{i=1}^nX_i  \\
&=\sum_{i=1}^n \frac{1}{n} X_i  \\
&\sim f_{\bar{X_n}}\left(\bar{x} \mid \sum_{i=1}^n \frac{\mu_i}{n} , \sum_{i=1}^n  \frac{\sigma_i^2}{n^2}\right) \\
&\sim f_{\bar{X_n}}\left(\bar{x} \mid  \mu, \frac{\sigma^2}{n} \right) \\ \\
\end{split}
$$

### standard normal transformation

$$
\begin{split}
&X \sim \mathcal{N}(0,1) \\
\Rightarrow& Y = \mu + \sigma X \sim \mathcal{N}(\mu,\sigma^2)
\end{split}
$$

$$
\begin{split}
F_Y(y) 
&= F_X\left(\frac{y- \mu}{\sigma}\right) \\ 
f_y(y) 
&= \frac{d}{dy} F_Y(y) \\
F^{-1}_Y(q) 
&= F^{-1}_X\left(q\right) \cdot \sigma + \mu \\ 
\end{split}
$$

$$
\begin{split}
F_Y(y) 
&= \mathbb{P}\left(Y \leq y\right) \\
&= \mathbb{P}\left(\mu + \sigma X \leq y\right) \\
&= \mathbb{P}\left(X \leq \frac{y- \mu}{\sigma}\right) \\
&= F_X\left(\frac{y- \mu}{\sigma}\right) \\ 
f_y(y) 
&= \frac{d}{dy} F_Y(y) \\
&= \frac{d}{dy} F_X\left(\frac{y- \mu}{\sigma}\right) \\
&= \frac{1}{\sigma} f_X\left(\frac{y- \mu}{\sigma}\right) \\
\end{split}
$$

- let $F_Y(y)=q \Leftrightarrow F^{-1}_Y(q)=y$
$$
\begin{split}
F_Y(y) &= F_X\left(\frac{y- \mu}{\sigma}\right) \\
F^{-1}_X\left(F_Y(y)\right) &= F^{-1}_X\left(F_X\left(\frac{y- \mu}{\sigma}\right)\right) \\
F^{-1}_X\left(q\right) &= \frac{y- \mu}{\sigma}\\
y &= F^{-1}_X\left(q\right) \sigma + \mu\\
F^{-1}_Y(q) &= F^{-1}_X\left(q\right) \sigma + \mu\\
\end{split}
$$



Tags: mathematics statistics
<!--ID: 1719674487794-->
END



START
Basic
- given a sample $X_1, ..., X_n \sim \mathcal{N}(\mu, \sigma^2)$  
- with the following [[statistical estimator]] of $\mu$ and $\sigma^2$
$$
\begin{split}
\bar{X}_n &= \frac{1}{n} \sum_{i=1}^n X_i \\
S^2_n &= \frac{1}{n-1} \sum_{i=1}^n \left(X_i - \bar{X}_n\right)^2 \\
\end{split}
$$
- what is the [[confidence set]] $\mathcal{S}$ for $\mu$? (no proof)

Back: 
### [[confidence set]] for the [[normal distribution]] (mean and [[variance]] unknown)
- given a sample $X_1, ..., X_n \sim \mathcal{N}(\mu, \sigma^2)$  
- with the following [[statistical estimator]] of $\mu$ and $\sigma^2$
$$
\begin{split}
\bar{X}_n &= \frac{1}{n} \sum_{i=1}^n X_i \\
S^2_n &= \frac{1}{n-1} \sum_{i=1}^n \left(X_i - \bar{X}_n\right)^2 \\
\end{split}
$$
- the [[confidence set]] $\mathcal{S}$ for $\mu$ is the following
- with $t_{\frac{n-1;\alpha-1}{2}}$ being the [[quantile function]] of the [[students t distribution]] with a degree of freedom $n-1$

$$
\begin{split}
\mathcal{S} 
&= \left[\bar{X}_n - \frac{S_n \cdot t_{\frac{n-1;\alpha-1}{2}}}{\sqrt{n}}, \bar{X}_n + \frac{\sigma \cdot t_{\frac{n-1;\alpha-1}{2}}}{\sqrt{n}}\right] \\
\end{split}
$$


_________________________________
### confidence set
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ and [[set]] $\mathcal{S}$ with a characteristics $\tau: \Theta \to \mathcal{S}$ 
- a [[function]] $C: \mathfrak{X} \to \mathcal{P}(S)$ that is mapping the obervation space to the [[power set]] of $\mathcal{S}$ is called the [[confidence set]] of $\tau$ to the level of $1 - \alpha$ if the following is true

$$
\mathbb{P}_\vartheta \left\{C \ni \tau(\vartheta)\right\} \geq 1-\alpha
$$
- for a given observation we want to be at least $1 - \alpha$ sure that the true value is in $C$
- we want $C$ to be as small as possible because $C = \mathcal{S}$ would statisfy the condition but would not contain any information

Tags: mathematics statistics
<!--ID: 1719677907240-->
END




START
Basic
- given a sample $X_1, ..., X_n \sim \mathcal{N}(\mu, \sigma^2)$ 
$$
\bar{X}_n = \frac{1}{n} \sum_{i=1}^n X_i 
$$
- how to transform $\bar{X}_n$ that it has a [[standard normal distribution]]

Back: 

$$
Y=\sqrt{n} \frac{\bar{X}_n - \mu}{\sigma}
$$

$$
\bar{X}_n \sim \mathcal{N}\left(\mu, \frac{\sigma^2}{n}\right)
$$

$$
\begin{split}
Y
&=\sqrt{n} \frac{\bar{X}_n - \mu}{\sigma} \\
\bar{X}_n&= Y \frac{\sigma}{\sqrt{n}} + \mu \\ 
&\sim \mathcal{N}\left(\mu_Y \frac{\sigma}{\sqrt{n}} + \mu, \frac{\sigma^2}{n} \sigma_Y^2\right)\\
&\sim \mathcal{N}\left(\mu, \frac{\sigma^2}{n} \right)\\
\end{split}
$$

_________________________________



### [[random sample]] from a [[normal distribution]]

The mean from a [[random sample]] of the sixe $n$ from a [[normal distribution]] is again [[normal distribution|normal distributed]] with a mean $\mu$ and a [[variance]] $\frac{\sigma^2}{n}$. 
$$
\begin{split}
X_i &\sim f_{X}\left(x | \mu, \sigma^2\right) \: i.i.d \\
\Rightarrow \bar{X_n}&=\frac{1}{n}\sum_{i=1}^nX_i \sim f_{\bar{X_n}}\left(\bar{x} \mid  \mu, \frac{\sigma^2}{n} \right) 
\end{split}
$$
proof
Since the folowing is true
$$
\begin{split}
X_i &\sim f_{X_i}\left(x_i | \mu_i, \sigma_i^2\right) \\
\Rightarrow Y&=\sum_{i=1}^n a_i +b \sim f_{Y}\left(y \mid \sum_{i=1}^n a_i \mu_i + b, \sum_{i=1}^n a_i^2 \sigma_i^2\right) 
\end{split}
$$
$$
\begin{split}
\bar{X_n}&=\frac{1}{n}\sum_{i=1}^nX_i  \\
&=\sum_{i=1}^n \frac{1}{n} X_i  \\
&\sim f_{\bar{X_n}}\left(\bar{x} \mid \sum_{i=1}^n \frac{\mu_i}{n} , \sum_{i=1}^n  \frac{\sigma_i^2}{n^2}\right) \\
&\sim f_{\bar{X_n}}\left(\bar{x} \mid  \mu, \frac{\sigma^2}{n} \right) \\ \\
\end{split}
$$

### standard normal transformation

$$
\begin{split}
&X \sim \mathcal{N}(0,1) \\
\Rightarrow& Y = \mu + \sigma X \sim \mathcal{N}(\mu,\sigma^2)
\end{split}
$$

$$
\begin{split}
F_Y(y) 
&= F_X\left(\frac{y- \mu}{\sigma}\right) \\ 
f_y(y) 
&= \frac{d}{dy} F_Y(y) \\
F^{-1}_Y(q) 
&= F^{-1}_X\left(q\right) \cdot \sigma + \mu \\ 
\end{split}
$$

$$
\begin{split}
F_Y(y) 
&= \mathbb{P}\left(Y \leq y\right) \\
&= \mathbb{P}\left(\mu + \sigma X \leq y\right) \\
&= \mathbb{P}\left(X \leq \frac{y- \mu}{\sigma}\right) \\
&= F_X\left(\frac{y- \mu}{\sigma}\right) \\ 
f_y(y) 
&= \frac{d}{dy} F_Y(y) \\
&= \frac{d}{dy} F_X\left(\frac{y- \mu}{\sigma}\right) \\
&= \frac{1}{\sigma} f_X\left(\frac{y- \mu}{\sigma}\right) \\
\end{split}
$$

- let $F_Y(y)=q \Leftrightarrow F^{-1}_Y(q)=y$
$$
\begin{split}
F_Y(y) &= F_X\left(\frac{y- \mu}{\sigma}\right) \\
F^{-1}_X\left(F_Y(y)\right) &= F^{-1}_X\left(F_X\left(\frac{y- \mu}{\sigma}\right)\right) \\
F^{-1}_X\left(q\right) &= \frac{y- \mu}{\sigma}\\
y &= F^{-1}_X\left(q\right) \sigma + \mu\\
F^{-1}_Y(q) &= F^{-1}_X\left(q\right) \sigma + \mu\\
\end{split}
$$



Tags: mathematics statistics
<!--ID: 1719677907246-->
END




START
Basic
- given a sample $X_1, ..., X_n$ i.i.d. from the same [[distribution]] with the [[cumulative distribution function (CDF)]] $F_X(x)$
- with the following unbiased [[statistical estimator]] for the [[expectation]] and the [[variance]] for $X$: $\mu$ and $\sigma^2$
$$
\begin{split}
\bar{X}_n &= \frac{1}{n} \sum_{i=1}^n X_i \\
S^2_n &= \frac{1}{n-1} \sum_{i=1}^n \left(X_i - \bar{X}_n\right)^2 \\
\end{split}
$$


- what can be said about the is the [[confidence set]] $\mathcal{S}$ for $\mu$? (no proof)

Back: 
### [[confidence set]] for a sample from a general [[random variable]]
- given a sample $X_1, ..., X_n$ i.i.d. from the same [[distribution]] with the [[cumulative distribution function (CDF)]] $F_X(x)$
- with the following unbiased [[statistical estimator]] for the [[expectation]] and the [[variance]] for $X$: $\mu$ and $\sigma^2$
$$
\begin{split}
\bar{X}_n &= \frac{1}{n} \sum_{i=1}^n X_i \\
S^2_n &= \frac{1}{n-1} \sum_{i=1}^n \left(X_i - \bar{X}_n\right)^2 \\
\end{split}
$$


- the [[confidence set]] $\mathcal{S}_n$ for $\mu$ is converging to the following
$$
\begin{split}
\lim_{n \to \infty}\mathcal{S}_n
&= \left[\bar{X}_n - \frac{S_n \cdot z_{\frac{\alpha-1}{2}}}{\sqrt{n}}, \bar{X}_n + \frac{\sigma \cdot z_{\frac{\alpha-1}{2}}}{\sqrt{n}}\right] \\
\end{split}
$$

- with $z_\frac{1-\alpha}{2} = F^{-1}_X\left(\frac{1-\alpha}{2}\right)$ being the [[quantile function]] of $X$
_________________________________
### confidence set
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ and [[set]] $\mathcal{S}$ with a characteristics $\tau: \Theta \to \mathcal{S}$ 
- a [[function]] $C: \mathfrak{X} \to \mathcal{P}(S)$ that is mapping the obervation space to the [[power set]] of $\mathcal{S}$ is called the [[confidence set]] of $\tau$ to the level of $1 - \alpha$ if the following is true

$$
\mathbb{P}_\vartheta \left\{C \ni \tau(\vartheta)\right\} \geq 1-\alpha
$$
- for a given observation we want to be at least $1 - \alpha$ sure that the true value is in $C$
- we want $C$ to be as small as possible because $C = \mathcal{S}$ would statisfy the condition but would not contain any information

Tags: mathematics statistics
<!--ID: 1719680983086-->
END