### fisher information
- given a [[random variable]] $X$ with a [[statistical model]] $(\mathfrak{X}, \mathcal{A}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[probability density function (PDF)]] $f_\vartheta(x)$ 
- the [[fisher information]] $\mathcal{I}(\vartheta)$ measures the amount of information an observable [[random variable]] carries about a parameter $\vartheta$
- note: the fisher information is a general property of the [[statistical model]] and is independent of the values of the observations

$$
\begin{split}
\mathcal{I}(\vartheta) 
&= \mathbb{VAR}_\vartheta \left[\frac{d}{d\vartheta} \ln f_\vartheta(X)\right]  \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] 
&= \int \left(\frac{d}{d\vartheta} \ln f_\vartheta(x)\right)^2 f_\vartheta(x) dx \\
&= \mathbb{E}_\vartheta \left[\frac{d^2}{d\vartheta^2} \ln f_\vartheta(X)\right] \\
\end{split}
$$
#### interpretation
- if the [[probability density function (PDF)]] $f_\vartheta(x)$ has a sharp peak with respect to $\vartheta$ it is easy to estimate $\vartheta$ from observations of $X$
- since the [[score function]] measures the seasitivity of the model for data the [[fisher information]] gives the sequared sensitivity of the model for an average observation
$$
\begin{split}
\mathcal{I}(\vartheta) 
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right]  =\mathbb{E}_\vartheta \left[Q(\vartheta)^2\right]
\end{split}
$$

- can give an upper bound for the [[estimator variance]] of an [[bias|unbiased]] [[statistical estimator]] (see [[cramer rao bound]])


### fisher information and squared score function
- the [[fisher information]] is equal to [[expectation]] of the squared [[score function]]

$$
\begin{split}
\mathcal{I}(\vartheta) 
&= \mathbb{VAR}_\vartheta \left[\frac{d}{d\vartheta} \ln f_\vartheta(X)\right] \in (0, \infty) \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] - \mathbb{E}_\vartheta \left[\frac{d}{d\vartheta} \ln f_\vartheta(X)\right]^2 \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] - \mathbb{E}_\vartheta \left[\frac{\frac{d}{d\vartheta} f_\vartheta(X)}{f_\vartheta(X)}\right]^2 \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] -  \left[ \int \frac{\frac{d}{d\vartheta} f_\vartheta(x)}{f_\vartheta(x)} f_\vartheta(x) dx\right]^2 \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] -  \left[ \int \frac{d}{d\vartheta} f_\vartheta(x) dx\right]^2 \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] -  \left[ \frac{d}{d\vartheta} \int  f_\vartheta(x) dx\right]^2 \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] 
\end{split}
$$

### fisher information and derivate of the score function
- the [[fisher information]] is equal to the expected [[derivative]] of the [[score function]]
$$
\begin{split}
\mathcal{I}(\vartheta) 
&= - \mathbb{E}_\vartheta \left[\frac{d^2}{d\vartheta^2} \ln f_\vartheta(X)\right]
\end{split}
$$

 proof
$$
\begin{split}
\frac{d^2}{d\vartheta^2} \ln f_\vartheta(X)  
&= \frac{\frac{d^2}{d\vartheta^2} f_\vartheta(X)}{f_\vartheta(X)} - \left(\frac{\frac{d}{d\vartheta} f_\vartheta(X)}{f_\vartheta(X)}\right)^2 \\
&= \frac{\frac{d^2}{d\vartheta^2} f_\vartheta(X)}{f_\vartheta(X)} - \left(\frac{d}{d\vartheta} \ln f_\vartheta(X) \right)^2 \\
\mathbb{E}_\vartheta \left[\frac{d^2}{d\vartheta^2} \ln f_\vartheta(X)\right] 
&= \mathbb{E}_\vartheta \left[\frac{\frac{d^2}{d\vartheta^2} f_\vartheta(X)}{f_\vartheta(X)}\right] - \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X) \right)^2\right] \\
&=  - \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X) \right)^2\right] \\
\end{split}
$$





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

# ----------------------

![[score function#score function]]


# anki

START
Basic
[[fisher information]]
- definition (3 versions without proof)
- interpretation
- where can it be used for?
Back: 
### fisher information
- given a [[random variable]] $X$ with a [[statistical model]] $(\mathfrak{X}, \mathcal{A}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[probability density function (PDF)]] $f_\vartheta(x)$ 
- the [[fisher information]] $\mathcal{I}(\vartheta)$ measures the amount of information an observable [[random variable]] carries about a parameter $\vartheta$
- note: the fisher information is a general property of the [[statistical model]] and is independent of the values of the observations

$$
\begin{split}
\mathcal{I}(\vartheta) 
&= \mathbb{VAR}_\vartheta \left[\frac{d}{d\vartheta} \ln f_\vartheta(X)\right]  \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] 
&= \int \left(\frac{d}{d\vartheta} \ln f_\vartheta(x)\right)^2 f_\vartheta(x) dx \\
&= \mathbb{E}_\vartheta \left[\frac{d^2}{d\vartheta^2} \ln f_\vartheta(X)\right] \\
\end{split}
$$
#### interpretation
- if the [[probability density function (PDF)]] $f_\vartheta(x)$ has a sharp peak with respect to $\vartheta$ it is easy to estimate $\vartheta$ from observations of $X$
- since the [[score function]] measures the seasitivity of the model for data the [[fisher information]] gives the sequared sensitivity of the model for an average observation
$$
\begin{split}
\mathcal{I}(\vartheta) 
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right]  =\mathbb{E}_\vartheta \left[Q(\vartheta)^2\right]
\end{split}
$$

- can give an upper bound for the [[estimator variance]] of an [[bias|unbiased]] [[statistical estimator]] (see [[cramer rao bound]])


### fisher information and squared score function
- the [[fisher information]] is equal to [[expectation]] of the squared [[score function]]

$$
\begin{split}
\mathcal{I}(\vartheta) 
&= \mathbb{VAR}_\vartheta \left[\frac{d}{d\vartheta} \ln f_\vartheta(X)\right] \in (0, \infty) \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] - \mathbb{E}_\vartheta \left[\frac{d}{d\vartheta} \ln f_\vartheta(X)\right]^2 \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] - \mathbb{E}_\vartheta \left[\frac{\frac{d}{d\vartheta} f_\vartheta(X)}{f_\vartheta(X)}\right]^2 \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] -  \left[ \int \frac{\frac{d}{d\vartheta} f_\vartheta(x)}{f_\vartheta(x)} f_\vartheta(x) dx\right]^2 \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] -  \left[ \int \frac{d}{d\vartheta} f_\vartheta(x) dx\right]^2 \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] -  \left[ \frac{d}{d\vartheta} \int  f_\vartheta(x) dx\right]^2 \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] 
\end{split}
$$

### fisher information and derivate of the score function
- the [[fisher information]] is equal to the expected [[derivative]] of the [[score function]]
$$
\begin{split}
\mathcal{I}(\vartheta) 
&= - \mathbb{E}_\vartheta \left[\frac{d^2}{d\vartheta^2} \ln f_\vartheta(X)\right]
\end{split}
$$

 proof
$$
\begin{split}
\frac{d^2}{d\vartheta^2} \ln f_\vartheta(X)  
&= \frac{\frac{d^2}{d\vartheta^2} f_\vartheta(X)}{f_\vartheta(X)} - \left(\frac{\frac{d}{d\vartheta} f_\vartheta(X)}{f_\vartheta(X)}\right)^2 \\
&= \frac{\frac{d^2}{d\vartheta^2} f_\vartheta(X)}{f_\vartheta(X)} - \left(\frac{d}{d\vartheta} \ln f_\vartheta(X) \right)^2 \\
\mathbb{E}_\vartheta \left[\frac{d^2}{d\vartheta^2} \ln f_\vartheta(X)\right] 
&= \mathbb{E}_\vartheta \left[\frac{\frac{d^2}{d\vartheta^2} f_\vartheta(X)}{f_\vartheta(X)}\right] - \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X) \right)^2\right] \\
&=  - \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X) \right)^2\right] \\
\end{split}
$$



Tags: mathematics statistics WS2425
<!--ID: 1729346313373-->
END


START
Basic
[[fisher information]]
- relationship between [[fisher information]] of one oberservation to $n$ i.i.d oberservations
- with proof

Back: 

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

### fisher information
- given a [[random variable]] $X$ with a [[statistical model]] $(\mathfrak{X}, \mathcal{A}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[probability density function (PDF)]] $f_\vartheta(x)$ 
- the [[fisher information]] $\mathcal{I}(\vartheta)$ measures the amount of information an observable [[random variable]] carries about a parameter $\vartheta$
- note: the fisher information is a general property of the [[statistical model]] and is independent of the values of the observations

$$
\begin{split}
\mathcal{I}(\vartheta) 
&= \mathbb{VAR}_\vartheta \left[\frac{d}{d\vartheta} \ln f_\vartheta(X)\right]  \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] 
&= \int \left(\frac{d}{d\vartheta} \ln f_\vartheta(x)\right)^2 f_\vartheta(x) dx \\
&= \mathbb{E}_\vartheta \left[\frac{d^2}{d\vartheta^2} \ln f_\vartheta(X)\right] \\
\end{split}
$$
#### interpretation
- if the [[probability density function (PDF)]] $f_\vartheta(x)$ has a sharp peak with respect to $\vartheta$ it is easy to estimate $\vartheta$ from observations of $X$
- since the [[score function]] measures the seasitivity of the model for data the [[fisher information]] gives the sequared sensitivity of the model for an average observation
$$
\begin{split}
\mathcal{I}(\vartheta) 
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right]  =\mathbb{E}_\vartheta \left[Q(\vartheta)^2\right]
\end{split}
$$

- can give an upper bound for the [[estimator variance]] of an [[bias|unbiased]] [[statistical estimator]] (see [[cramer rao bound]])


### fisher information and squared score function
- the [[fisher information]] is equal to [[expectation]] of the squared [[score function]]

$$
\begin{split}
\mathcal{I}(\vartheta) 
&= \mathbb{VAR}_\vartheta \left[\frac{d}{d\vartheta} \ln f_\vartheta(X)\right] \in (0, \infty) \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] - \mathbb{E}_\vartheta \left[\frac{d}{d\vartheta} \ln f_\vartheta(X)\right]^2 \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] - \mathbb{E}_\vartheta \left[\frac{\frac{d}{d\vartheta} f_\vartheta(X)}{f_\vartheta(X)}\right]^2 \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] -  \left[ \int \frac{\frac{d}{d\vartheta} f_\vartheta(x)}{f_\vartheta(x)} f_\vartheta(x) dx\right]^2 \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] -  \left[ \int \frac{d}{d\vartheta} f_\vartheta(x) dx\right]^2 \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] -  \left[ \frac{d}{d\vartheta} \int  f_\vartheta(x) dx\right]^2 \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] 
\end{split}
$$

### fisher information and derivate of the score function
- the [[fisher information]] is equal to the expected [[derivative]] of the [[score function]]
$$
\begin{split}
\mathcal{I}(\vartheta) 
&= - \mathbb{E}_\vartheta \left[\frac{d^2}{d\vartheta^2} \ln f_\vartheta(X)\right]
\end{split}
$$

 proof
$$
\begin{split}
\frac{d^2}{d\vartheta^2} \ln f_\vartheta(X)  
&= \frac{\frac{d^2}{d\vartheta^2} f_\vartheta(X)}{f_\vartheta(X)} - \left(\frac{\frac{d}{d\vartheta} f_\vartheta(X)}{f_\vartheta(X)}\right)^2 \\
&= \frac{\frac{d^2}{d\vartheta^2} f_\vartheta(X)}{f_\vartheta(X)} - \left(\frac{d}{d\vartheta} \ln f_\vartheta(X) \right)^2 \\
\mathbb{E}_\vartheta \left[\frac{d^2}{d\vartheta^2} \ln f_\vartheta(X)\right] 
&= \mathbb{E}_\vartheta \left[\frac{\frac{d^2}{d\vartheta^2} f_\vartheta(X)}{f_\vartheta(X)}\right] - \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X) \right)^2\right] \\
&=  - \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X) \right)^2\right] \\
\end{split}
$$


Tags: mathematics statistics WS2425
<!--ID: 1729757165041-->
END


START
Basic
[[fisher information]]
- proof for the following:

$$
\begin{split}
\mathcal{I}(\vartheta) 
&= - \mathbb{E}_\vartheta \left[\frac{d^2}{d\vartheta^2} \ln f_\vartheta(X)\right]
\end{split}
$$

Back: 
### fisher information
- given a [[random variable]] $X$ with a [[statistical model]] $(\mathfrak{X}, \mathcal{A}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[probability density function (PDF)]] $f_\vartheta(x)$ 
- the [[fisher information]] $\mathcal{I}(\vartheta)$ measures the amount of information an observable [[random variable]] carries about a parameter $\vartheta$
- note: the fisher information is a general property of the [[statistical model]] and is independent of the values of the observations

$$
\begin{split}
\mathcal{I}(\vartheta) 
&= \mathbb{VAR}_\vartheta \left[\frac{d}{d\vartheta} \ln f_\vartheta(X)\right]  \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] 
&= \int \left(\frac{d}{d\vartheta} \ln f_\vartheta(x)\right)^2 f_\vartheta(x) dx \\
&= \mathbb{E}_\vartheta \left[\frac{d^2}{d\vartheta^2} \ln f_\vartheta(X)\right] \\
\end{split}
$$
#### interpretation
- if the [[probability density function (PDF)]] $f_\vartheta(x)$ has a sharp peak with respect to $\vartheta$ it is easy to estimate $\vartheta$ from observations of $X$
- since the [[score function]] measures the seasitivity of the model for data the [[fisher information]] gives the sequared sensitivity of the model for an average observation
$$
\begin{split}
\mathcal{I}(\vartheta) 
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right]  =\mathbb{E}_\vartheta \left[Q(\vartheta)^2\right]
\end{split}
$$

- can give an upper bound for the [[estimator variance]] of an [[bias|unbiased]] [[statistical estimator]] (see [[cramer rao bound]])


### fisher information and squared score function
- the [[fisher information]] is equal to [[expectation]] of the squared [[score function]]

$$
\begin{split}
\mathcal{I}(\vartheta) 
&= \mathbb{VAR}_\vartheta \left[\frac{d}{d\vartheta} \ln f_\vartheta(X)\right] \in (0, \infty) \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] - \mathbb{E}_\vartheta \left[\frac{d}{d\vartheta} \ln f_\vartheta(X)\right]^2 \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] - \mathbb{E}_\vartheta \left[\frac{\frac{d}{d\vartheta} f_\vartheta(X)}{f_\vartheta(X)}\right]^2 \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] -  \left[ \int \frac{\frac{d}{d\vartheta} f_\vartheta(x)}{f_\vartheta(x)} f_\vartheta(x) dx\right]^2 \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] -  \left[ \int \frac{d}{d\vartheta} f_\vartheta(x) dx\right]^2 \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] -  \left[ \frac{d}{d\vartheta} \int  f_\vartheta(x) dx\right]^2 \\
&= \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X)\right)^2\right] 
\end{split}
$$

### fisher information and derivate of the score function
- the [[fisher information]] is equal to the expected [[derivative]] of the [[score function]]
$$
\begin{split}
\mathcal{I}(\vartheta) 
&= - \mathbb{E}_\vartheta \left[\frac{d^2}{d\vartheta^2} \ln f_\vartheta(X)\right]
\end{split}
$$

 proof
$$
\begin{split}
\frac{d^2}{d\vartheta^2} \ln f_\vartheta(X)  
&= \frac{\frac{d^2}{d\vartheta^2} f_\vartheta(X)}{f_\vartheta(X)} - \left(\frac{\frac{d}{d\vartheta} f_\vartheta(X)}{f_\vartheta(X)}\right)^2 \\
&= \frac{\frac{d^2}{d\vartheta^2} f_\vartheta(X)}{f_\vartheta(X)} - \left(\frac{d}{d\vartheta} \ln f_\vartheta(X) \right)^2 \\
\mathbb{E}_\vartheta \left[\frac{d^2}{d\vartheta^2} \ln f_\vartheta(X)\right] 
&= \mathbb{E}_\vartheta \left[\frac{\frac{d^2}{d\vartheta^2} f_\vartheta(X)}{f_\vartheta(X)}\right] - \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X) \right)^2\right] \\
&=  - \mathbb{E}_\vartheta \left[\left(\frac{d}{d\vartheta} \ln f_\vartheta(X) \right)^2\right] \\
\end{split}
$$



Tags: mathematics statistics WS2425
<!--ID: 1730182230101-->
END