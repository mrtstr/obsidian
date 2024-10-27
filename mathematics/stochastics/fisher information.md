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

### fisher information for n fold models
- given [[statistical model]] $(\mathfrak{X}, \mathcal{A}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[probability density function (PDF)]] $f_\vartheta(x)$ 
- and [[random variable]] $X_1, ..., X_n \sim \mathcal{D}$ i.i.d with a known fisher information for one observation
$$
\begin{split}
\mathcal{I}_1(\vartheta) 
&= \mathbb{VAR}_\vartheta \left[\frac{d}{d\vartheta} \ln f_\vartheta(X_1)\right] \\
\end{split}
$$
- the following can be said about the [[fisher information]] for $n$ observations

$$
\begin{split}
\mathcal{I}_n(\vartheta) 
&= \mathbb{VAR}_\vartheta \left[\frac{d}{d\vartheta} \ln \prod_{i \in [n]} f_\vartheta(X_i)\right] \\
&= \sum_{i \in [n]} \mathbb{VAR}_\vartheta \left[\frac{d}{d\vartheta} \ln  f_\vartheta(X_i)\right] \\
&= n \mathbb{VAR}_\vartheta \left[\frac{d}{d\vartheta} \ln  f_\vartheta(X_1)\right] \\
&= n \cdot\mathcal{I}_1(\vartheta)  \\
\end{split}
$$

# anki

START
Basic
[[fisher information]]
- definition
- interpretation
- where can it be used for?
Back: 

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
<!--ID: 1729346313373-->
END


START
Basic
[[fisher information]]
- relationship between [[fisher information]] of one oberservation to $n$ i.i.d oberservations
- with proof

Back: 
### fisher information
- given a [[random variable]] $X$ with a [[statistical model]] $(\mathfrak{X}, \mathcal{A}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[probability density function (PDF)]] $f_\vartheta(x)$ 


$$
\begin{split}
\mathcal{I}_n(\vartheta) 
&= \mathbb{VAR}_\vartheta \left[\frac{d}{d\vartheta} \ln \prod_{i \in [n]} f_\vartheta(X_i)\right] \\
&= \sum_{i \in [n]} \mathbb{VAR}_\vartheta \left[\frac{d}{d\vartheta} \ln  f_\vartheta(X_i)\right] \\
&= n \mathbb{VAR}_\vartheta \left[\frac{d}{d\vartheta} \ln  f_\vartheta(X_1)\right] \\
&= n \cdot\mathcal{I}_1(\vartheta)  \\
\end{split}
$$

#### interpretation
- if the [[probability density function (PDF)]] $f_\vartheta(x)$ has a sharp peak with respect to $\vartheta$ it is easy to estimate $\vartheta$ from observations of $X$
- thus $\mathcal{I}(\vartheta)$ measures the amount of information an observable [[random variable]] carries about a parameter $\vartheta$
- can give an upper bound for the [[estimator variance]] of an [[bias|unbiased]] [[statistical estimator]] (see [[cramer rao bound]])

### fisher information for n fold models
- given [[statistical model]] $(\mathfrak{X}, \mathcal{A}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[probability density function (PDF)]] $f_\vartheta(x)$ 
- and [[random variable]] $X_1, ..., X_n \sim \mathcal{D}$ i.i.d with a known fisher information for one observation
$$
\begin{split}
\mathcal{I}_1(\vartheta) 
&= \mathbb{VAR}_\vartheta \left[\frac{d}{d\vartheta} \ln f_\vartheta(X_1)\right] \\
\end{split}
$$
- the following can be said about the [[fisher information]] for $n$ observations

$$
\begin{split}
\mathcal{I}_n(\vartheta) 
&= \mathbb{VAR}_\vartheta \left[\frac{d}{d\vartheta} \ln \prod_{i \in [n]} f_\vartheta(X)\right] = n \cdot\mathcal{I}_1(\vartheta)  \\
\end{split}
$$
Tags: mathematics statistics WS2425
<!--ID: 1729757165041-->
END