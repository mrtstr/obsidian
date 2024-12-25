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

##### returns
- in perod $t$ the returns are given by the following

$$
\begin{split}
\frac{P_t - P_{t-1}}{P_{t-1}} 
=  \frac{P_t}{P_{t-1}} - 1
\end{split}
$$

- the [[natural logarithm|log]] returns $X_t$ are given by the following

$$
\begin{split}
X_t 
&= \ln\left(\frac{P_t}{P_{t-1}} \right) \\
&= \ln\left(P_t \right) - \ln\left(P_{t-1} \right) \\
&= \ln\left(\frac{P_t}{P_{t-1} +1 -1} \right) \approx \frac{P_t}{P_{t-1}} - 1 \\
\end{split}
$$
### properties
##### expecation

$$
\begin{split}
\mathbb{E}\left[P_t \right]
&= \mathbb{E}\left[P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right) \right] \\
&= P_0  \exp\left(\mu t\right) \cdot \frac{ \mathbb{E}\left[\exp\left(\sigma  W_t  \right) \right] }{\exp\left(\frac{\sigma^2}{2}t\right) }    \\
&= P_0 e^{\mu t}  \\
\end{split}
$$
# ----------

![[log normal distribution#log normal distribution]]

![[wiener process#wiener process]]