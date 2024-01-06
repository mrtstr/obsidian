## definition [[autocovariance]]
- [[covariance]] between two points of a [[time series]] / [[stochastic process]]
- given a [[stochastic process]] $\{X_t\}$ the [[autocovariance]] $K_{XX}(t_1, t_2)$ for the time instances $t_1$ and $t_2$ is given as follows

$$
\begin{split}
K_{XX}(t_1, t_2) 
&= \mathbb{COV}\left[X_{t_1}, X_{t_2}\right] \\ 
&= \mathbb{E}\left[X_{t_1}X_{t_2}\right] - \mathbb{E}\left[X_{t_1}\right]\mathbb{E}\left[X_{t_2}\right] \\ 
\end{split}
$$

![[covariance#definition covariance]]

## [[autocovariance]] for [[stationary process]]
$$
\begin{split}
K_{XX}(t_1, t_2) = K_{XX}(\tau , t_2 - t_1 + \tau)  \quad 
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

![[stationary process#Definition (strongly) stationary process]]




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
K_{XX}(t_1, t_2) = K_{XX}(\tau , t_2 - t_1 + \tau)  \quad 
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

#### Definition (strongly) [[stationary process]]
- a [[stochastic process]] whose [[joint distribution]] is not time-dependent
- given a [[stationary process]] $\{X_t\}$ and an arbitray [[set]] of time instances ${t_1, ..., t_n}$ the [[joint distribution|joint distributions]] of the [[random variable|random variables]] $X(t_1), ..., X(t_n)$ is the same as the [[joint distribution|joint distributions]] of the [[random variable|random variables]] $X(t_1+\tau), ..., X(t_n+\tau)$ 

$$
\begin{split}
F_X(x_1, ..., x_n) = F_X(x_1 + \tau, ..., x_n + \tau) \quad 
\forall \tau, t_1, ... , t_n \in \mathbb{R} \\
f_X(x_1, ..., x_n) = f_X(x_1 + \tau, ..., x_n + \tau) \quad 
\forall \tau, t_1, ... , t_n \in \mathbb{R} 
\end{split}
$$

Tags: mathematics time_series
<!--ID: 1704533194482-->
END