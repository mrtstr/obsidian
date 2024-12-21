
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

# -----------------------
![[correlation#correlation]]

![[autocovariance#definition autocovariance]]


![[stationary process#strongly stationary process]]

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