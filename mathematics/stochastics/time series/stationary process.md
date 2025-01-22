### stationary process
- not every strong stationary process is weak stationary because the [[variance]] might not exist
- every strong stationary process with existing [[moments]] is also weak stationary

- weak stationary does not imply strong stationary because just because the first moments are time invariant does not guarantee that the [[distribution]] is time invariant 
#### strongly stationary process
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

#### weakly stationary process
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- the [[variance]] $\mathbb{VAR}\left[X_t\right]< \infty$ has to be finite



# Anki

START
Basic
[[stationary process]]
- strong vs weak stationary
- does one imply the other?
Back: 
### stationary process
- not every strong stationary process is weak stationary because the [[variance]] might not exist
- every strong stationary process with existing [[moments]] is also weak stationary

- weak stationary does not imply strong stationary because just because the first moments are time invariant does not guarantee that the [[distribution]] is time invariant 
#### strongly stationary process
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

#### weakly stationary process
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- the [[variance]] $\mathbb{VAR}\left[X_t\right]< \infty$ has to be finite
Tags: mathematics time_series WS2425
<!--ID: 1737556427961-->
END

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

Tags: mathematics time_series WS2425
<!--ID: 1704533194477-->
END


START
Basic
Definition (weakly) stationary [[stochastic process]]
Back: 
### weakly stationary process
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- the [[variance]] $\mathbb{VAR}\left[X_t\right]< \infty$ has to be finite
- every strongly stationary process is also a (weakly) [[stationary process]]

Tags: mathematics time_series WS2425
<!--ID: 1705250198085-->
END