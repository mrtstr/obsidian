### ARCH model
- the concept behind the [[GARCH model]] is to use a [[autoregressive moving average (ARMA) model]] to model the [[volatility]] 
- $e_t \sim (0,1)$ i.i.d
- $a_i, b_j \geq 0$ and $a_p, b_q \neq 0$
$$
\begin{split}
 X_t&= \sigma_t \cdot e_t \\
\sigma^2_t &= a_0 + \sum_{i=1}^{p} a_i X_{t-i}^2 + \sum_{j=1}^{q} b_j \sigma^2_{t-j}
\end{split}
$$

- that means that $\sigma^2_t=\mathbb{VAR}[X_t|X_{t-1}, X_{t-2},...]$ is equal to the [[conditional variance]] of $X_t$ given the past values
	→ $\sigma^2_t$ is measurable given the past values
- the [[GARCH model]] $X_t$ is [[white noise]] but not independent white noise and the squared [[GARCH model]] $X^2_t$ is a [[autoregressive moving average (ARMA) model]] [[time series]]