### cramer rao bound
- defines the theotetical optimum for a [[bias|unbiased]] [[statistical estimator]]

##### the statistical model
- given a [[random variable]] $X$ with a [[statistical model]] $(\mathfrak{X}, \mathcal{A}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[probability density function (PDF)]] $f_\vartheta(x)$ 
- the true [[distribution]] of the [[random variable]] $\mathcal{L}(X)$ is in $\left\{\mathbb{P}_\vartheta: \vartheta \in \Theta\right\}$
- $f_\vartheta(x)$ is [[differentiabe]] with respect to $\vartheta$ and satisfies the following condition

$$
\begin{split}
\int_\mathfrak{X} \frac{d}{d\vartheta} f_\vartheta(x) dx = 0 \\
\end{split}
$$
- note: this is given if the order [[integral]] and the [[derivative]] can be swiched ([[regularity of density function]])

$$
\int_\mathfrak{X} \frac{d}{d\vartheta} f_\vartheta(x) dx 
= \frac{d}{d\vartheta} \int_\mathfrak{X}  f_\vartheta(x) dx 
= \frac{d}{d\vartheta} 1 
= 0
$$

##### the statistical estimator
- for every [[bias|unbiased]] [[statistical estimator]] that satisfies the following condition


$$
\begin{split}
\int_\mathfrak{X} T(x) \frac{d}{d\vartheta} f_\vartheta(x) dx = 1 \\
\end{split}
$$
- note: this is given if the order [[integral]] and the [[derivative]] can be swiched ([[regularity of density function]])

$$
\int_\mathfrak{X} T(x) \frac{d}{d\vartheta} f_\vartheta(x) dx  
= \frac{d}{d\vartheta} \int_\mathfrak{X} T(x)  f_\vartheta(x) dx
= \frac{d}{d\vartheta} \mathbb{E}_\vartheta[T] 
= \frac{d}{d\vartheta} \vartheta 
= 1
$$

##### the bound
- the [[estimator variance]] of $T$ is bound by the reciprocal of the [[fisher information]]

$$
\forall \vartheta \in \Theta: \mathbb{VAR}_\vartheta[T] \leq \frac{1}{\mathcal{I}(\vartheta)}
$$

##### note
a [[bias|unbiased]] [[statistical estimator]] that matches this bound is 
- the [[best estimator]]
- the estimator with the lowest [[estimator variance]]
- the estimator with the lowest [[mean square error]]

### proof

$$
\begin{split}
\mathcal{I}(\vartheta) 
&= \mathbb{E}_\vartheta \left[\frac{d}{d\vartheta} \ln f_\vartheta(x)\right] \\
&= \mathbb{E}_\vartheta \left[ \frac{\frac{d}{d\vartheta} f_\vartheta(x)}{f_\vartheta(x)} \right]  \\
&= \int \frac{\frac{d}{d\vartheta} f_\vartheta(x)}{f_\vartheta(x)} f_\vartheta(x) dx  \\
&= \int \frac{d}{d\vartheta} f_\vartheta(x)  dx  \\
&= \int \frac{d}{d\vartheta} f_\vartheta(x)  dx  \\
&= 0
\end{split}
$$

TODO continue


### example: [[normal distribution]]
- given $X_1, ..., X_n \sim \mathcal{N}(\mu = \vartheta, \sigma^2)$ i.i.d with a known $\sigma^2$

$$
f_\vartheta\left(X| \sigma^2\right) = \prod_{i \in [n]} \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(X_i-\vartheta)^2}{\sigma^2}\right]}
$$

- the [[fisher information]] of the model is as follows

$$
\begin{split}
\frac{d}{d \vartheta} \ln \left(f_\vartheta\left(X| \sigma^2\right)\right)  
&= \frac{d}{d \vartheta} \ln \left(\prod_{i \in [n]} \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(X_i-\vartheta)^2}{\sigma^2}\right]}\right)   \\
&= \sum_{i \in [n]} \frac{d}{d \vartheta} \frac{-1}{2}\frac{(X_i-\vartheta)^2}{\sigma^2}  \\
&= \sum_{i \in [n]} \frac{-1}{2} \cdot (-1) \cdot 2 \cdot \frac{X_i-\vartheta}{\sigma^2}  \\
&= \sum_{i \in [n]} \frac{X_i-\vartheta}{\sigma^2}  \\
&= \frac{1}{\sigma^2} \left(\sum_{i \in [n]} X_i \right)-  \frac{n\vartheta}{\sigma^2} \\
\end{split}
$$

$$
\begin{split}
\mathcal{I}(\vartheta) 
&= \mathbb{VAR}_\vartheta \left[ \frac{d}{d \vartheta} \ln \left(f_\vartheta\left(X| \sigma^2\right)\right) \right] \\
&= \mathbb{VAR}_\vartheta \left[ \frac{1}{\sigma^2} \left(\sum_{i \in [n]} X_i \right)-\frac{n\vartheta}{\sigma^2}  \right] \\
&= \frac{1}{\sigma^4} \mathbb{VAR}_\vartheta \left[  \sum_{i \in [n]} X_i   \right] \\
&= \frac{1}{\sigma^4} \sum_{i \in [n]} \mathbb{VAR}_\vartheta \left[   X_i   \right] \\
&= n \frac{1}{\sigma^4} \mathbb{VAR}_\vartheta  \left[   X_1   \right] \\
&= n \frac{1}{\sigma^4}   \sigma^2 \\
&=  \frac{n}{\sigma^2}    \\
\end{split}
$$
- thus the following is true for every [[bias|unbiased]] [[statistical estimator]]

$$
 \mathbb{VAR}_\vartheta[T] 
 \leq \frac{1}{\mathcal{I}(\vartheta)} = \frac{\sigma^2}{n}
$$

- for the basic mean estimator $T_n = \frac{1}{n} \sum_{i \in [n]} X_i$ we can prove that it's optimal for a [[normal distribution]]

$$
\mathbb{VAR}_\vartheta[T_n] = \frac{\sigma^2}{n}
$$

![[basic estimator for n fold statistical model#basic mean estimator]]
# ---------
![[fisher information#fisher information]]

![[estimator variance#estimator variance]]



# anki





START
Basic
[[bias|unbiased]] [[statistical estimator]]
- theorem that defines the optimum
- with conditions
- interpretation and relationship to the [[mean square error]]

Back: 
### cramer rao bound
- defines the theotetical optimum for a [[bias|unbiased]] [[statistical estimator]]

##### the statistical model
- given a [[random variable]] $X$ with a [[statistical model]] $(\mathfrak{X}, \mathcal{A}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[probability density function (PDF)]] $f_\vartheta(x)$ 
- the true [[distribution]] of the [[random variable]] $\mathcal{L}(X)$ is in $\left\{\mathbb{P}_\vartheta: \vartheta \in \Theta\right\}$
- $f_\vartheta(x)$ is [[differentiabe]] with respect to $\vartheta$ and satisfies the following condition

$$
\begin{split}
\int_\mathfrak{X} \frac{d}{d\vartheta} f_\vartheta(x) dx = 0 \\
\end{split}
$$
- note: this is given if the order [[integral]] and the [[derivative]] can be swiched ([[regularity of density function]])

$$
\int_\mathfrak{X} \frac{d}{d\vartheta} f_\vartheta(x) dx 
= \frac{d}{d\vartheta} \int_\mathfrak{X}  f_\vartheta(x) dx 
= \frac{d}{d\vartheta} 1 
= 0
$$

##### the statistical estimator
- for every [[bias|unbiased]] [[statistical estimator]] that satisfies the following condition


$$
\begin{split}
\int_\mathfrak{X} T(x) \frac{d}{d\vartheta} f_\vartheta(x) dx = 1 \\
\end{split}
$$
- note: this is given if the order [[integral]] and the [[derivative]] can be swiched ([[regularity of density function]])

$$
\int_\mathfrak{X} T(x) \frac{d}{d\vartheta} f_\vartheta(x) dx  
= \frac{d}{d\vartheta} \int_\mathfrak{X} T(x)  f_\vartheta(x) dx
= \frac{d}{d\vartheta} \mathbb{E}_\vartheta[T] 
= \frac{d}{d\vartheta} \vartheta 
= 1
$$

##### the bound
- the [[estimator variance]] of $T$ is bound by the reciprocal of the [[fisher information]]

$$
\forall \vartheta \in \Theta: \mathbb{VAR}_\vartheta[T] \leq \frac{1}{\mathcal{I}(\vartheta)}
$$

##### note
a [[bias|unbiased]] [[statistical estimator]] that matches this bound is 
- the [[best estimator]]
- the estimator with the lowest [[estimator variance]]
- the estimator with the lowest [[mean square error]]

_________________


### fisher information
- given a [[random variable]] $X$ with a [[statistical model]] $(\mathfrak{X}, \mathcal{A}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[probability density function (PDF)]] $f_\vartheta(x)$ 


$$
\begin{split}
\mathcal{I}(\vartheta) 
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] \\
&= \mathbb{VAR}_\vartheta \left[\frac{d}{d\vartheta} \ln f_\vartheta(X)\right] \\
&= \mathbb{VAR}_\vartheta \left[ \frac{\frac{d}{d\vartheta} f_\vartheta(X)}{f_\vartheta(X)} \right] 
\in (0, \infty)
\end{split}
$$

#### interpretation
- if the [[probability density function (PDF)]] $f_\vartheta(x)$ has a sharp peak with respect to $\vartheta$ it is easy to estimate $\vartheta$ from observations of $X$
- thus $\mathcal{I}(\vartheta)$ measures the amount of information an observable [[random variable]] carries about a parameter $\vartheta$
- can give an upper bound for the [[estimator variance]] of an [[bias|unbiased]] [[statistical estimator]] (see [[cramer rao bound]])


Tags: mathematics statistics WS2425
<!--ID: 1729751853185-->
END


START
Basic
given $X_1, ..., X_n \sim \mathcal{N}(\mu = \vartheta, \sigma^2)$ i.i.d with a known $\sigma^2$
- what is the upper bound for estimators for $\vartheta$ 

Back: 
- using the [[cramer rao bound]] we just have to calculate the [[fisher information]] for the model to define an upper bound
### example: [[normal distribution]]
- given $X_1, ..., X_n \sim \mathcal{N}(\mu = \vartheta, \sigma^2)$ i.i.d with a known $\sigma^2$

$$
f_\vartheta\left(X| \sigma^2\right) = \prod_{i \in [n]} \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(X_i-\vartheta)^2}{\sigma^2}\right]}
$$

- the [[fisher information]] of the model is as follows

$$
\begin{split}
\frac{d}{d \vartheta} \ln \left(f_\vartheta\left(X| \sigma^2\right)\right)  
&= \frac{d}{d \vartheta} \ln \left(\prod_{i \in [n]} \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(X_i-\vartheta)^2}{\sigma^2}\right]}\right)   \\
&= \sum_{i \in [n]} \frac{d}{d \vartheta} \frac{-1}{2}\frac{(X_i-\vartheta)^2}{\sigma^2}  \\
&= \sum_{i \in [n]} \frac{-1}{2} \cdot (-1) \cdot 2 \cdot \frac{X_i-\vartheta}{\sigma^2}  \\
&= \sum_{i \in [n]} \frac{X_i-\vartheta}{\sigma^2}  \\
&= \frac{1}{\sigma^2} \left(\sum_{i \in [n]} X_i \right)-  \frac{n\vartheta}{\sigma^2} \\
\end{split}
$$

$$
\begin{split}
\mathcal{I}(\vartheta) 
&= \mathbb{VAR}_\vartheta \left[ \frac{d}{d \vartheta} \ln \left(f_\vartheta\left(X| \sigma^2\right)\right) \right] \\
&= \mathbb{VAR}_\vartheta \left[ \frac{1}{\sigma^2} \left(\sum_{i \in [n]} X_i \right)-\frac{n\vartheta}{\sigma^2}  \right] \\
&= \frac{1}{\sigma^4} \mathbb{VAR}_\vartheta \left[  \sum_{i \in [n]} X_i   \right] \\
&= \frac{1}{\sigma^4} \sum_{i \in [n]} \mathbb{VAR}_\vartheta \left[   X_i   \right] \\
&= n \frac{1}{\sigma^4} \mathbb{VAR}_\vartheta  \left[   X_1   \right] \\
&= n \frac{1}{\sigma^4}   \sigma^2 \\
&=  \frac{n}{\sigma^2}    \\
\end{split}
$$

________________________


### cramer rao bound
- defines the theotetical optimum for a [[bias|unbiased]] [[statistical estimator]]

##### the statistical model
- given a [[random variable]] $X$ with a [[statistical model]] $(\mathfrak{X}, \mathcal{A}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[probability density function (PDF)]] $f_\vartheta(x)$ 
- the true [[distribution]] of the [[random variable]] $\mathcal{L}(X)$ is in $\left\{\mathbb{P}_\vartheta: \vartheta \in \Theta\right\}$
- $f_\vartheta(x)$ is [[differentiabe]] with respect to $\vartheta$ and satisfies the following condition

$$
\begin{split}
\int_\mathfrak{X} \frac{d}{d\vartheta} f_\vartheta(x) dx = 0 \\
\end{split}
$$
- note: this is given if the order [[integral]] and the [[derivative]] can be swiched ([[regularity of density function]])

$$
\int_\mathfrak{X} \frac{d}{d\vartheta} f_\vartheta(x) dx 
= \frac{d}{d\vartheta} \int_\mathfrak{X}  f_\vartheta(x) dx 
= \frac{d}{d\vartheta} 1 
= 0
$$

##### the statistical estimator
- for every [[bias|unbiased]] [[statistical estimator]] that satisfies the following condition


$$
\begin{split}
\int_\mathfrak{X} T(x) \frac{d}{d\vartheta} f_\vartheta(x) dx = 1 \\
\end{split}
$$
- note: this is given if the order [[integral]] and the [[derivative]] can be swiched ([[regularity of density function]])

$$
\int_\mathfrak{X} T(x) \frac{d}{d\vartheta} f_\vartheta(x) dx  
= \frac{d}{d\vartheta} \int_\mathfrak{X} T(x)  f_\vartheta(x) dx
= \frac{d}{d\vartheta} \mathbb{E}_\vartheta[T] 
= \frac{d}{d\vartheta} \vartheta 
= 1
$$

##### the bound
- the [[estimator variance]] of $T$ is bound by the reciprocal of the [[fisher information]]

$$
\forall \vartheta \in \Theta: \mathbb{VAR}_\vartheta[T] \leq \frac{1}{\mathcal{I}(\vartheta)}
$$

##### note
a [[bias|unbiased]] [[statistical estimator]] that matches this bound is 
- the [[best estimator]]
- the estimator with the lowest [[estimator variance]]
- the estimator with the lowest [[mean square error]]


### fisher information
- given a [[random variable]] $X$ with a [[statistical model]] $(\mathfrak{X}, \mathcal{A}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[probability density function (PDF)]] $f_\vartheta(x)$ 


$$
\begin{split}
\mathcal{I}(\vartheta) 
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] \\
&= \mathbb{VAR}_\vartheta \left[\frac{d}{d\vartheta} \ln f_\vartheta(X)\right] \\
&= \mathbb{VAR}_\vartheta \left[ \frac{\frac{d}{d\vartheta} f_\vartheta(X)}{f_\vartheta(X)} \right] 
\in (0, \infty)
\end{split}
$$

#### interpretation
- if the [[probability density function (PDF)]] $f_\vartheta(x)$ has a sharp peak with respect to $\vartheta$ it is easy to estimate $\vartheta$ from observations of $X$
- thus $\mathcal{I}(\vartheta)$ measures the amount of information an observable [[random variable]] carries about a parameter $\vartheta$
- can give an upper bound for the [[estimator variance]] of an [[bias|unbiased]] [[statistical estimator]] (see [[cramer rao bound]])


Tags: mathematics statistics WS2425
<!--ID: 1729751853191-->
END




START
Basic
given $X_1, ..., X_n \sim \mathcal{N}(\mu = \vartheta, \sigma^2)$ i.i.d with a known $\sigma^2$ and the estimator $T_n$ for $\vartheta$
- proof that $T_n$ is optimal

$$
\begin{split}
T_n &= \frac{1}{n} \sum_{i=1}^n X_i \\
\end{split}
$$

Back: 
- using the [[cramer rao bound]] we just have to calculate the [[fisher information]] for the model to define an upper bound
- by calculating the [[estimator variance]] of the basic mean estimator we can proof that is reaching the bound

### basic mean estimator
- given an [[n fold statistical model]] $\left(\mathbb{R}^n, \mathcal{B}(\mathbb{R}^n), \mathbb{P}^{\otimes n}_{\vartheta \in \Theta}\right)$ with the following characteristics

$$
\begin{split}
m(\vartheta) &= \mathbb{E}_\vartheta[X_1] \\
\end{split}
$$

- the following are [[statistical estimator|statistical estimators]] for $m$ 

$$
\begin{split}
M &= \frac{1}{n} \sum_{i=1}^n X_i \\
\end{split}
$$


$$
\begin{split}
\mathbb{E}_\vartheta[M]  
&= \mathbb{E}_\vartheta\left[\frac{1}{n} \sum_{i=1}^n X_i\right]  \\
&= \frac{n}{n}  \mathbb{E}_\vartheta\left[  X_1\right]  \\
&= \mathbb{E}_\vartheta\left[  X_1\right]  \\
\end{split}
$$

$$
\begin{split}
\mathbb{B}[M] 
&= \mathbb{E}_\vartheta[M] - m(\vartheta) \\
&= \mathbb{E}_\vartheta\left[\frac{1}{n} \sum_{i=1}^n X_i\right] -  \mathbb{E}_\vartheta[X_1] \\
&= \frac{n}{n}  \mathbb{E}_\vartheta\left[  X_1\right] -  \mathbb{E}_\vartheta[X_1] = 0 \\
\end{split}
$$

$$
\begin{split}
\mathbb{VAR}_\vartheta[M] 
&= \mathbb{E}_\vartheta\left[M^2\right] -\mathbb{E}_\vartheta\left[M\right]^2   \\
&= \mathbb{E}_\vartheta\left[ X_1\right]^2 + \frac{1}{n} \mathbb{VAR}_\vartheta\left[ X\right] -\mathbb{E}_\vartheta\left[X_1\right]^2   \\
&= \frac{1}{n} \mathbb{VAR}_\vartheta\left[ X\right]  \\
\end{split}
$$


________________________
### example: [[normal distribution]]
- given $X_1, ..., X_n \sim \mathcal{N}(\mu = \vartheta, \sigma^2)$ i.i.d with a known $\sigma^2$

$$
f_\vartheta\left(X| \sigma^2\right) = \prod_{i \in [n]} \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(X_i-\vartheta)^2}{\sigma^2}\right]}
$$

- the [[fisher information]] of the model is as follows

$$
\begin{split}
\frac{d}{d \vartheta} \ln \left(f_\vartheta\left(X| \sigma^2\right)\right)  
&= \frac{d}{d \vartheta} \ln \left(\prod_{i \in [n]} \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(X_i-\vartheta)^2}{\sigma^2}\right]}\right)   \\
&= \sum_{i \in [n]} \frac{d}{d \vartheta} \frac{-1}{2}\frac{(X_i-\vartheta)^2}{\sigma^2}  \\
&= \sum_{i \in [n]} \frac{-1}{2} \cdot (-1) \cdot 2 \cdot \frac{X_i-\vartheta}{\sigma^2}  \\
&= \sum_{i \in [n]} \frac{X_i-\vartheta}{\sigma^2}  \\
&= \frac{1}{\sigma^2} \left(\sum_{i \in [n]} X_i \right)-  \frac{n\vartheta}{\sigma^2} \\
\end{split}
$$

$$
\begin{split}
\mathcal{I}(\vartheta) 
&= \mathbb{VAR}_\vartheta \left[ \frac{d}{d \vartheta} \ln \left(f_\vartheta\left(X| \sigma^2\right)\right) \right] \\
&= \mathbb{VAR}_\vartheta \left[ \frac{1}{\sigma^2} \left(\sum_{i \in [n]} X_i \right)-\frac{n\vartheta}{\sigma^2}  \right] \\
&= \frac{1}{\sigma^4} \mathbb{VAR}_\vartheta \left[  \sum_{i \in [n]} X_i   \right] \\
&= \frac{1}{\sigma^4} \sum_{i \in [n]} \mathbb{VAR}_\vartheta \left[   X_i   \right] \\
&= n \frac{1}{\sigma^4} \mathbb{VAR}_\vartheta  \left[   X_1   \right] \\
&= n \frac{1}{\sigma^4}   \sigma^2 \\
&=  \frac{n}{\sigma^2}    \\
\end{split}
$$

- thus the following is true for every [[bias|unbiased]] [[statistical estimator]]

$$
 \mathbb{VAR}_\vartheta[T] 
 \leq \frac{1}{\mathcal{I}(\vartheta)} = \frac{\sigma^2}{n}
$$



### cramer rao bound
- defines the theotetical optimum for a [[bias|unbiased]] [[statistical estimator]]

##### the statistical model
- given a [[random variable]] $X$ with a [[statistical model]] $(\mathfrak{X}, \mathcal{A}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[probability density function (PDF)]] $f_\vartheta(x)$ 
- the true [[distribution]] of the [[random variable]] $\mathcal{L}(X)$ is in $\left\{\mathbb{P}_\vartheta: \vartheta \in \Theta\right\}$
- $f_\vartheta(x)$ is [[differentiabe]] with respect to $\vartheta$ and satisfies the following condition

$$
\begin{split}
\int_\mathfrak{X} \frac{d}{d\vartheta} f_\vartheta(x) dx = 0 \\
\end{split}
$$
- note: this is given if the order [[integral]] and the [[derivative]] can be swiched ([[regularity of density function]])

$$
\int_\mathfrak{X} \frac{d}{d\vartheta} f_\vartheta(x) dx 
= \frac{d}{d\vartheta} \int_\mathfrak{X}  f_\vartheta(x) dx 
= \frac{d}{d\vartheta} 1 
= 0
$$

##### the statistical estimator
- for every [[bias|unbiased]] [[statistical estimator]] that satisfies the following condition


$$
\begin{split}
\int_\mathfrak{X} T(x) \frac{d}{d\vartheta} f_\vartheta(x) dx = 1 \\
\end{split}
$$
- note: this is given if the order [[integral]] and the [[derivative]] can be swiched ([[regularity of density function]])

$$
\int_\mathfrak{X} T(x) \frac{d}{d\vartheta} f_\vartheta(x) dx  
= \frac{d}{d\vartheta} \int_\mathfrak{X} T(x)  f_\vartheta(x) dx
= \frac{d}{d\vartheta} \mathbb{E}_\vartheta[T] 
= \frac{d}{d\vartheta} \vartheta 
= 1
$$

##### the bound
- the [[estimator variance]] of $T$ is bound by the reciprocal of the [[fisher information]]

$$
\forall \vartheta \in \Theta: \mathbb{VAR}_\vartheta[T] \leq \frac{1}{\mathcal{I}(\vartheta)}
$$

##### note
a [[bias|unbiased]] [[statistical estimator]] that matches this bound is 
- the [[best estimator]]
- the estimator with the lowest [[estimator variance]]
- the estimator with the lowest [[mean square error]]


### fisher information
- given a [[random variable]] $X$ with a [[statistical model]] $(\mathfrak{X}, \mathcal{A}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[probability density function (PDF)]] $f_\vartheta(x)$ 


$$
\begin{split}
\mathcal{I}(\vartheta) 
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] \\
&= \mathbb{VAR}_\vartheta \left[\frac{d}{d\vartheta} \ln f_\vartheta(X)\right] \\
&= \mathbb{VAR}_\vartheta \left[ \frac{\frac{d}{d\vartheta} f_\vartheta(X)}{f_\vartheta(X)} \right] 
\in (0, \infty)
\end{split}
$$

#### interpretation
- if the [[probability density function (PDF)]] $f_\vartheta(x)$ has a sharp peak with respect to $\vartheta$ it is easy to estimate $\vartheta$ from observations of $X$
- thus $\mathcal{I}(\vartheta)$ measures the amount of information an observable [[random variable]] carries about a parameter $\vartheta$
- can give an upper bound for the [[estimator variance]] of an [[bias|unbiased]] [[statistical estimator]] (see [[cramer rao bound]])


Tags: mathematics statistics WS2425
<!--ID: 1729751853194-->
END