
## definition [[autocorrelation (pearson)]]
- [[correlation]] between two points of a [[time series]] / [[stochastic process]] is called [[autocorrelation (pearson)]]
- the [[autocorrelation (pearson)]] is a normalized [[autocovariance]]
- given a [[stochastic process]] $\{X_t\}$ the [[autocorrelation (pearson)]] $\rho_{XX}(t_1, t_2)$ for the time instances $t_1$ and $t_2$ is given as follows

$$
\begin{split}
\rho_{XX}(t_1, t_2) 
&= 
\frac{ K_{XX}(t_1, t_2)}{\sqrt{ \mathbb{VAR}\left[X_{t_1}\right]\mathbb{VAR}\left[X_{t_2}\right]}}\\ 
&= 
\frac{ \mathbb{COV}\left[X_{t_1}, X_{t_2}\right]}{\sqrt{ \mathbb{VAR}\left[X_{t_1}\right]\mathbb{VAR}\left[X_{t_2}\right]}}\\ 
&= 
\frac{ \mathbb{E}\left[X_{t_1}X_{t_2}\right] - \mathbb{E}\left[X_{t_1}\right]\mathbb{E}\left[X_{t_2}\right]}{\sqrt{ \mathbb{VAR}\left[X_{t_1}\right]\mathbb{VAR}\left[X_{t_2}\right]}}\\ 
\end{split}
$$

![[correlation#definition correlation]]

![[autocovariance#definition autocovariance]]

## definition [[autocorrelation (pearson)]] for [[stationary process]]

$$
\begin{split}
\rho_{XX}(t_1, t_2) = \rho_{XX}(\tau, \tau + t_2 - t_1)
\end{split}
$$
#### proof
$$
\begin{split}
\rho_{XX}(t_1, t_2) 
&= 
\frac{ K_{XX}(t_1, t_2)}{\sqrt{ \mathbb{VAR}\left[X_{t_1}\right]\mathbb{VAR}\left[X_{t_2}\right]}}\\ 
&= 
\frac{ K_{XX}(\tau , t_2 - t_1 + \tau)}{\mathbb{VAR}\left[X_{\tau_2}\right]}\\ 
\end{split}
$$

![[stationary process#Definition (strongly) stationary process]]

![[autocovariance#autocovariance for stationary process]]


# Anki

START
Basic
[[autocorrelation (pearson)]]
- defintion
- relationship to the [[autocovariance]]
[[autocorrelation (pearson)]] of a [[stationary process]]
- propertie with proof

Back: 

## definition [[autocorrelation (pearson)]]
- [[correlation]] between two points of a [[time series]] / [[stochastic process]] is called [[autocorrelation (pearson)]]
- the [[autocorrelation (pearson)]] is a normalized [[autocovariance]]
- given a [[stochastic process]] $\{X_t\}$ the [[autocorrelation (pearson)]] $\rho_{XX}(t_1, t_2)$ for the time instances $t_1$ and $t_2$ is given as follows

$$
\begin{split}
\rho_{XX}(t_1, t_2) 
&= 
\frac{ K_{XX}(t_1, t_2)}{\sqrt{ \mathbb{VAR}\left[X_{t_1}\right]\mathbb{VAR}\left[X_{t_2}\right]}}\\ 
&= 
\frac{ \mathbb{COV}\left[X_{t_1}, X_{t_2}\right]}{\sqrt{ \mathbb{VAR}\left[X_{t_1}\right]\mathbb{VAR}\left[X_{t_2}\right]}}\\ 
&= 
\frac{ \mathbb{E}\left[X_{t_1}X_{t_2}\right] - \mathbb{E}\left[X_{t_1}\right]\mathbb{E}\left[X_{t_2}\right]}{\sqrt{ \mathbb{VAR}\left[X_{t_1}\right]\mathbb{VAR}\left[X_{t_2}\right]}}\\ 
\end{split}
$$

#### definition [[correlation]]
- The [[correlation]] is a measure for the linear dependency of [[random variable|random variables]] 
- in contrast to the [[covariance]] the [[correlation]] is not depending on the absolut size of the [[random variable|random variables]]
$$
\rho[X,Y] = \frac{\mathbb{COVAR}[X,Y]}{\sigma_X\sigma_Y}=\frac{\mathbb{COVAR}[X,Y]}{\sqrt{\mathbb{VAR}[X]\mathbb{VAR}[Y]}}
$$

#### definition [[autocovariance]]
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



## definition [[autocorrelation (pearson)]] for [[stationary process]]

$$
\begin{split}
\rho_{XX}(t_1, t_2) = \rho_{XX}(\tau, \tau + t_2 - t_1)
\end{split}
$$
#### proof
$$
\begin{split}
\rho_{XX}(t_1, t_2) 
&= 
\frac{ K_{XX}(t_1, t_2)}{\sqrt{ \mathbb{VAR}\left[X_{t_1}\right]\mathbb{VAR}\left[X_{t_2}\right]}}\\ 
&= 
\frac{ K_{XX}(\tau , t_2 - t_1 + \tau)}{\mathbb{VAR}\left[X_{\tau_2}\right]}\\ 
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


#### [[autocovariance]] for [[stationary process]]
$$
\begin{split}
K_{XX}(t_1, t_2) = K_{XX}(\tau , t_2 - t_1 + \tau)  \quad 
\forall \tau, t_1, ... , t_n \in \mathbb{R} 
\end{split}
$$
proof
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

Tags: mathematics time_series
<!--ID: 1704533194469-->
END