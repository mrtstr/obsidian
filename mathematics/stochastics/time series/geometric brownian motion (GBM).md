### geometric brownian motion
- [[geometric brownian motion (GBM)]] is a [[stochastic process]] that can be used to describe the evolution of financial asset prices in a random but predictable manner
- $P_t$ is a [[geometric brownian motion (GBM)]] with the [[wiener process]] $W_t$ the [[drift]]  $\mu$ (return rate) and the [[volatility]] (of the return) $\sigma$
- the return is [[log normal distribution|log normal distributed]]

$$
P_t = P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right)
$$

- is the solution of the following stochastic differential equation with the increment of the [[wiener process]] $dW_t$ 

$$
dP_t = \mu P_t dt + \sigma P_t dW_t
$$


- plays a pivotal role in the Black-Scholes model for options pricing
# ----------

![[wiener process#wiener process]]