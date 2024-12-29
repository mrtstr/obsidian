### financial time series
- log returns over time [[autocorrelation (ACF)|uncorelated]] but dont seem to be from the same [[distribution]] because the mean and [[variance]] might change over time ([[structural break]])
	- there appear to be periods with high and variability of log returns
	- the mean of the log returns might also not be constant over time
- log return also might not be [[stochastic independent]] because eventhough the [[autocorrelation (ACF)]] is zero for $h>0$ the [[autocorrelation (ACF)]] for higher moments like $X_t^2$ are not
# anki

START
Basic
properties of [[financial time series]] (3)

Back: 
### financial time series
- log returns over time [[autocorrelation (ACF)|uncorelated]] but dont seem to be from the same [[distribution]] because the mean and [[variance]] might change over time ([[structural break]])
	- there appear to be periods with high and variability of log returns
	- the mean of the log returns might also not be constant over time
- log return also might not be [[stochastic independent]] because eventhough the [[autocorrelation (ACF)]] is zero for $h>0$ the [[autocorrelation (ACF)]] for higher moments like $X_t^2$ are not


____________
### structural break
- when the underlying law of a [[time series]] suddenly changes e.g. the parameters of the model are changing

#### mean changes
- given and a log returns [[geometric brownian motion (GBM)#log returns|log returns]] $X_t = e_t + \mu$ that changes to $X_t = e_t - \mu$ with [[white noise#gaussian white noise|gaussian white noise]] $e_t$ 
- the [[autocorrelation (ACF)]] of $X_t$ $\hat\rho(h)$ would not reflect the [[structural break]]
- the [[structural break]] becomes visible in $\mathbb{E}[X_t]$
#### variances changes
- given and a log returns [[geometric brownian motion (GBM)#log returns|log returns]] $X_t = \sigma_1 e_t$ that changes to $X_t = \sigma_2 e_t$ with [[white noise#gaussian white noise|gaussian white noise]] $e_t$ 
- the [[autocorrelation (ACF)]] of $X_t$ or even of $X_t^2$  $\hat\rho(h)$ would not reflect the [[structural break]]
- the [[structural break]] becomes visible in $\mathbb{VAR}[X_t]=\mathbb{E}[X_t^2]$


### autocovariance estimators for stationary time series
- given an observation $X_1, ..., X_n$ from a [[stationary process|stationary]] [[time series]]
- the [[autocovariance]] $\gamma(h)$ can be estimated with the following [[statistical estimator]] (for $h \leq n$)

$$
\hat\gamma_n(h) = \frac{1}{n} \sum_{t=1}^{n-|h|} \left(X_t- X_n\right)\left(X_{t+h}- X_n\right)
$$

- under suitable assumptions $\hat\gamma_n(h)$ is [[estimator consitency#$ sqrt{n}$ consitency|root n consistent]] and [[normal distribution]]

### correlation estimators for stationary time series
- given an observation $X_1, ..., X_n$ from a [[stationary process|stationary]] [[time series]]
- the [[autocovariance]] $\rho(h)$ can be estimated with the following [[statistical estimator]] (for $h \leq n$)

$$
\hat\rho_n(h) = \frac{\hat\gamma_n(h)}{\hat\gamma_n(0)} 
$$

### geometric brownian motion
- [[geometric brownian motion (GBM)]] is a [[stochastic process]] that can be used to describe the evolution of financial asset prices in a random but predictable manner
- $P_t$ is a [[geometric brownian motion (GBM)]] with the [[wiener process]] $W_t$ the [[drift]]  $\mu$ (return rate) and the [[volatility]] (of the return) $\sigma$

$$
P_t = P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right)
$$

#### log returns
- the log returns $X_t$ are defined as follows

$$
\begin{split}
X_t 
&= \ln\left(\frac{P_t}{P_{t-1}} \right) \\
&= \ln\left(P_t \right) - \ln\left(P_{t-1} \right) \\
\end{split}
$$
#### distribution of the log returns
- the log returns $X_t$ are i.i.d. [[normal distribution|normal distributed]]

$$
\begin{split}
X_t 
&= \ln\left(P_t \right) - \ln\left(P_{t-1} \right) \\
&= \left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t - \left(\mu - \frac{\sigma^2}{2}\right)\cdot (t-1) - \sigma W_{t-1} \\
&= \left(\mu - \frac{\sigma^2}{2}\right) + \sigma \left( W_{t-1} - W_{t-1} \right) \\
&= \left(\mu - \frac{\sigma^2}{2}\right) + \sigma e_t  \\
&\sim \mathcal{N}\left(\mu - \frac{\sigma^2}{2} , \sigma^2  \right)
\end{split}
$$

Tags: mathematics time_series WS2425
<!--ID: 1735412621665-->
END