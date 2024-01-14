## Definition (strongly) [[stationary process]]
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

## Definition (weakly) [[stationary process]]
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- every starongly statanary process is also a (weakly) [[stationary process]]


# Anki

START
Basic
Definition (strongly) stationary [[stochastic process]]
Back: 
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
<!--ID: 1704533194477-->
END


START
Basic
Definition (weakly) stationary [[stochastic process]]
Back: 
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- every starongly statanary process is also a (weakly) [[stationary process]]

Tags: mathematics time_series
<!--ID: 1705250198085-->
END