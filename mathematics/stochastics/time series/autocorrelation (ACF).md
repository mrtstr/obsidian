
### autocorrelation (ACF)
- [[correlation]] between two points of a [[time series]] / [[stochastic process]] is called [[autocorrelation (ACF)]]
- the [[autocorrelation (ACF)]] is a normalized [[autocovariance]]
- given a [[stochastic process]] $\{X_t\}$ the [[autocorrelation (ACF)]] $\rho_{XX}(t_1, t_2)$ for the time instances $t_1$ and $t_2$ is given as follows

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

### autocorrelation (ACF) for stationary processes

$$
\begin{split}
\rho_{XX}(t_1, t_2) 
&= \rho_{XX}(t, t + h) \qquad \text{with } h = t_2-t_1\\
&= \rho_{XX}(h) \\
&= \frac{ \mathbb{COV}\left[X_{t}, X_{t - h}\right]}{\mathbb{VAR}\left[X_{t}\right]} 
\qquad \text{with arbitray } \tau, h
\end{split}
$$

### the autocorrelation (ACF) for stationary time series is positive definite
- the [[autocorrelation (ACF)]] of a [[stationary process|stationary|]] [[time series]] is a [[positive definite]] [[matrix]]

$$
\begin{split}
c^\top \rho(r-s)_{r,s \in [n]}c 
&= \sum_{r \in [n]} \sum_{s \in [n]} c_r c_s \rho(r - s) \\
&= \sum_{r \in [n]} \sum_{s \in [n]} c_r c_s \frac{\mathbb{COV}\left[X_{t}, X_{t+r-s}\right]}{\mathbb{VAR}\left[X_{t}\right]} \\
&= \mathbb{VAR}\left[X_{t}\right] \sum_{r \in [n]} \sum_{s \in [n]} c_r c_s \mathbb{E}\left[X_{t}X_{t+r-s}\right]  \\
&= \mathbb{VAR}\left[X_{t}\right] \sum_{r \in [n]} \sum_{s \in [n]} c_r c_s \mathbb{E}\left[X_{t+s}X_{t+r}\right]  \\
&= \mathbb{VAR}\left[X_{t}\right]  \mathbb{E}\left[\left(\sum_{r \in [n]}  c_r X_r \right)^2\right] \geq 0  \\
\end{split}
$$


# -----------------------
![[correlation#correlation]]

![[autocovariance#definition autocovariance]]


![[stationary process#weakly stationary process]]

![[autocovariance#autocovariance for stationary process]]


# Anki

START
Basic
[[autocorrelation (ACF)]]
- defintion

[[autocorrelation (ACF)]] of a [[stationary process]]
- defintion

Back: 
### autocorrelation (ACF)
- [[correlation]] between two points of a [[time series]] / [[stochastic process]] is called [[autocorrelation (ACF)]]
- the [[autocorrelation (ACF)]] is a normalized [[autocovariance]]
- given a [[stochastic process]] $\{X_t\}$ the [[autocorrelation (ACF)]] $\rho_{XX}(t_1, t_2)$ for the time instances $t_1$ and $t_2$ is given as follows

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

### autocorrelation (ACF) for stationary processes

$$
\begin{split}
\rho_{XX}(t_1, t_2) 
&= \rho_{XX}(t, t + h) \qquad \text{with } h = t_2-t_1\\
&= \rho_{XX}(h) \\
&= \frac{ \mathbb{COV}\left[X_{t}, X_{t - h}\right]}{\mathbb{VAR}\left[X_{t}\right]} 
\qquad \text{with arbitray } \tau, h
\end{split}
$$

Tags: mathematics time_series WS2425
<!--ID: 1704533194469-->
END


START
Basic
proof the [[autocorrelation (ACF)]] of a [[stationary process|stationary|]] [[time series]] is a [[positive definite]] [[matrix]]

Back: 
### the autocorrelation (ACF) for stationary time series is positive definite
- the [[autocorrelation (ACF)]] of a [[stationary process|stationary|]] [[time series]] is a [[positive definite]] [[matrix]]

$$
\begin{split}
c^\top \rho(r-s)_{r,s \in [n]}c 
&= \sum_{r \in [n]} \sum_{s \in [n]} c_r c_s \rho(r - s) \\
&= \sum_{r \in [n]} \sum_{s \in [n]} c_r c_s \frac{\mathbb{COV}\left[X_{t}, X_{t+r-s}\right]}{\mathbb{VAR}\left[X_{t}\right]} \\
&= \mathbb{VAR}\left[X_{t}\right] \sum_{r \in [n]} \sum_{s \in [n]} c_r c_s \mathbb{E}\left[X_{t}X_{t+r-s}\right]  \\
&= \mathbb{VAR}\left[X_{t}\right] \sum_{r \in [n]} \sum_{s \in [n]} c_r c_s \mathbb{E}\left[X_{t+s}X_{t+r}\right]  \\
&= \mathbb{VAR}\left[X_{t}\right]  \mathbb{E}\left[\left(\sum_{r \in [n]}  c_r X_r \right)^2\right] \geq 0  \\
\end{split}
$$

________________

#### positive semi definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[definiteness of matrices|positive semi definite]] if the following is true
$$
\forall x \in \mathbb{R}^n : x^\top A x \geq0
$$
- in other words $f(x) = x^\top A x$ is a [[positive definite|positive semi definite]] [[function]]


### weakly stationary process
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- every starongly statanary process is also a (weakly) [[stationary process]]


### autocorrelation (ACF)
- [[correlation]] between two points of a [[time series]] / [[stochastic process]] is called [[autocorrelation (ACF)]]
- the [[autocorrelation (ACF)]] is a normalized [[autocovariance]]
- given a [[stochastic process]] $\{X_t\}$ the [[autocorrelation (ACF)]] $\rho_{XX}(t_1, t_2)$ for the time instances $t_1$ and $t_2$ is given as follows

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

### autocorrelation (ACF) for stationary processes

$$
\begin{split}
\rho_{XX}(t_1, t_2) 
&= \rho_{XX}(t, t + h) \qquad \text{with } h = t_2-t_1\\
&= \rho_{XX}(h) \\
&= \frac{ \mathbb{COV}\left[X_{t}, X_{t - h}\right]}{\mathbb{VAR}\left[X_{t}\right]} 
\qquad \text{with arbitray } \tau, h
\end{split}
$$

Tags: mathematics time_series WS2425
<!--ID: 1734890698113-->
END