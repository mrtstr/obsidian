### autocovariance
- [[covariance]] between two points of a [[time series]] / [[stochastic process]]
- given a [[stochastic process]] $\{X_t\}$ the [[autocovariance]] $K_{XX}(t_1, t_2)$ for the time instances $t_1$ and $t_2$ is given as follows

$$
\begin{split}
K_{XX}(t_1, t_2) 
&= \mathbb{COV}\left[X_{t_1}, X_{t_2}\right] \\ 
&= \mathbb{E}\left[X_{t_1}X_{t_2}\right] - \mathbb{E}\left[X_{t_1}\right]\mathbb{E}\left[X_{t_2}\right] \\ 
\end{split}
$$



## autocovariance for stationary process

$$
\begin{split}
\mathbb{COV}(t_1, t_2) = K_{XX}(h) = K_{XX}(t_2 - t_1)  \quad 
\forall \tau, t_1, ... , t_n \in \mathbb{R} 
\end{split}
$$
#### proof
$$
\begin{split}
K_{XX}(t_1, t_2) 
 =&\mathbb{E}\left[X_{t_1}X_{t_2}\right] - \mathbb{E}\left[X_{t_1}\right]\mathbb{E}\left[X_{t_2}\right] \\
= &\int\int x_{t_1}x_{t_2} f_{X_{t_1}X_{t_2}}(x_{t_1}x_{t_2})dx_{t_1}dx_{t_2} 
- \int x_{t_1} f_{X_{t_1}}(x_{t_1})dx_{t_1} \int x_{t_2} f_{X_{t_2}}(x_{t_2})dx_{t_2} \\
= &\int\int x_{t_1}x_{t_2} f_{X_{\tau}X_{\tau + t_2 - t_1}}(x_{t_1}x_{t_2})dx_{t_1}dx_{t_2} 
- \int x_{t_1} f_{X_{\tau}}(x_{t_1})dx_{t_1} \int x_{t_2} f_{X_{\tau + t_2 - t_1}}(x_{t_2})dx_{t_2} \\
=  &\mathbb{E}\left[X_{\tau}X_{\tau + t_2 - t_1}\right] - \mathbb{E}\left[X_{\tau}\right]\mathbb{E}\left[X_{\tau + t_2 - t_1}\right] \\
=  &K_{XX}(\tau , t_2 - t_1 + \tau)
\end{split}
$$


## linked
![[covariance#covariance]]

![[stationary process#weakly stationary process]]




# Anki

START
Basic
[[autocovariance]]
- defition
[[autocovariance]] of a [[stationary process]]
- propertie with proof

Back: 
## definition [[autocovariance]]
- [[covariance]] between two points of a [[time series]] / [[stochastic process]]
- given a [[stochastic process]] $\{X_t\}$ the [[autocovariance]] $K_{XX}(t_1, t_2)$ for the time instances $t_1$ and $t_2$ is given as follows

$$
\begin{split}
K_{XX}(t_1, t_2) 
&= \mathbb{COV}\left[X_{t_1, X_2}\right] \\ 
&= \mathbb{E}\left[X_{t_1}X_{t_2}\right] - \mathbb{E}\left[X_{t_1}\right]\mathbb{E}\left[X_{t_2}\right] \\ 
\end{split}
$$

#### definition [[covariance]]
The [[covariance]] is the [[variance]] of a [[joint distribution]]

$$
\mathbb{COV}\left[X,Y\right] = \mathbb{E}\left[(X-\mathbb{E}\left[X\right])(Y-\mathbb{E}\left[Y\right])\right]
= 
\mathbb{E}\left[XY\right]-\mathbb{E}\left[X\right]\mathbb{E}\left[Y\right]
$$

## [[autocovariance]] for [[stationary process]]
$$
\begin{split}
\mathbb{COV}(t_1, t_2) = K_{XX}(h) = K_{XX}(t_2 - t_1)  \quad 
\forall \tau, t_1, ... , t_n \in \mathbb{R} 
\end{split}
$$
#### proof
$$
\begin{split}
K_{XX}(t_1, t_2) 
 =&\mathbb{E}\left[X_{t_1}X_{t_2}\right] - \mathbb{E}\left[X_{t_1}\right]\mathbb{E}\left[X_{t_2}\right] \\
= &\int\int x_{t_1}x_{t_2} f_{X_{t_1}X_{t_2}}(x_{t_1}x_{t_2})dx_{t_1}dx_{t_2} 
- \int x_{t_1} f_{X_{t_1}}(x_{t_1})dx_{t_1} \int x_{t_2} f_{X_{t_2}}(x_{t_2})dx_{t_2} \\
= &\int\int x_{t_1}x_{t_2} f_{X_{\tau}X_{\tau + t_2 - t_1}}(x_{t_1}x_{t_2})dx_{t_1}dx_{t_2} 
- \int x_{t_1} f_{X_{\tau}}(x_{t_1})dx_{t_1} \int x_{t_2} f_{X_{\tau + t_2 - t_1}}(x_{t_2})dx_{t_2} \\
=  &\mathbb{E}\left[X_{\tau}X_{\tau + t_2 - t_1}\right] - \mathbb{E}\left[X_{\tau}\right]\mathbb{E}\left[X_{\tau + t_2 - t_1}\right] \\
=  &K_{XX}(\tau , t_2 - t_1 + \tau)
\end{split}
$$

#### Definition (weakly) [[stationary process]]
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- every starongly statanary process is also a (weakly) [[stationary process]]

Tags: mathematics time_series
<!--ID: 1704533194482-->
END