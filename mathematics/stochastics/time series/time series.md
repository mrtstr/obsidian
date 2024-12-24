
### time series
- family of [[random variable]] $(x_t, t \in Z)$ on a [[probability space]] $(\Omega, \mathcal{X}, P)$ 
- often obervations are taken at descrete points in time $t$ over a fixed time period of length $T$: $X_1, ..., X_n$  
- in most cases the obervations at different points in time (e.g. $X_{t_1}$ and $X_{t_2}$) are not independent

## classical models

![[white noise#white noise]]

### autoregressive time series
- a [[time series]] $(X_t)$ is an autoregressive [[time series]] of order $p$ if there exists an $AR(q)$ model with parameters $a_1,..., a_p$ and [[white noise]] $e_t$ to describe the law of $(X_t)$ 

![[autoregresive (AR) model#autoregresive (AR) model]]


### moving average time series
- a [[time series]] $(X_t)$ is an moving average [[time series]] of order $q$ if there exists an $MA(q)$ model with parameters $b_1,..., b_q$ and [[white noise]] $e_t$ to describe the law of $(X_t)$ 

![[moving average (MA) model#moving average model MA(q)]]

### autoregressive moving average time series
- a [[time series]] $(X_t)$ is an autoregressive moving average [[time series]] of order $p$ if there exists an $ARMA(p, q)$ model with parameters $a_1, ..., a_p$ and $b_1,..., b_q$ and [[white noise]] $e_t$ to describe the law of $(X_t)$ 

![[autoregressive moving average (ARMA) model#autoregressive moving average (ARMA) model]]

# -------------------

![[volatility#volatility]]

![[drift#drift]]

![[trend#trend]]

# Anki

START
Basic
[[time series]]
- definition
- classical models (4)

Back: 
### time series
- family of [[random variable]] $(x_t, t \in Z)$ on a [[probability space]] $(\Omega, \mathcal{X}, P)$ 
- often obervations are taken at descrete points in time $t$ over a fixed time period of length $T$: $X_1, ..., X_n$  
- in most cases the obervations at different points in time (e.g. $X_{t_1}$ and $X_{t_2}$) are not independent

## classical models

### white noise
[[time series]] $(e_t, t \in \mathbb{Z})$ with 
- i.i.d. values
- zero mean $\mathbb{E}[e_t] = 0$  
- constant and finite [[variance]] $\mathbb{VAR}[e_t] = \mathbb{E}[e_t^2]= \sigma^2 \in (0, \infty)$  
- [[correlation|uncorralated]] values $t \neq s \Rightarrow  \mathbb{COV}[e_t, e_s] = \mathbb{COR}[e_t, e_s] = 0$

#### gaussian white noise
- [[white noise]] with [[normal distribution|normal distributed]] values $e_t \sim \mathcal{N}(0, \sigma^2)$

### autoregressive time series
- a [[time series]] $(X_t)$ is an autoregressive [[time series]] of order $p$ if there exists an $AR(q)$ model with parameters $a_1,..., a_p$ and [[white noise]] $e_t$ to describe the law of $(X_t)$ 

#### autoregresive (AR) model
- The [[autoregresive (AR) model]] of order $p$ $AP(p)$ assumes the captures the linear releationship of the current value to the past p $p$ values
- assumes an at least [[stationary process]]

models the [[time series]]
- with parameters $a_1, ..., a_p$
- [[white noise]] $e$ (i.i.d. with $\mathbb{E}[e] =0$ and $\mathbb{VAR}[e_t] \in (0, \infty)$)
- constant $\beta$ (sometimes assumed to be zero)
$$
X_t = \sum_{i=1}^p a_i X_{t-i} + \beta + e_t
$$

### moving average time series
- a [[time series]] $(X_t)$ is an moving average [[time series]] of order $q$ if there exists an $MA(q)$ model with parameters $b_1,..., b_q$ and [[white noise]] $e_t$ to describe the law of $(X_t)$ 
#### moving average model MA(q)
- discribes the current value as a linear combination of the past $p$  error / [[white noise]] terms
models the [[time series]]
- with parameters $b_1, ..., b_p$
- [[white noise]] $e$ (i.i.d. with $\mathbb{E}[e] =0$ and $\mathbb{VAR}[e_t] \in (0, \infty)$)
- mean of the timeseries $\mu$ (sometimes assumed to be 0)

$$
X_t = \mu +  e_t  + \sum_{i=1}^q b_i e_{t-i} 
$$

##### interpretation
- caputes the direct effect (shok response) of the past error terms on the curent value
- assumes [[stationary process|weakly stationary]]

### autoregressive moving average time series
- a [[time series]] $(X_t)$ is an autoregressive moving average [[time series]] of order $p$ if there exists an $ARMA(p, q)$ model with parameters $a_1, ..., a_p$ and $b_1,..., b_q$ and [[white noise]] $e_t$ to describe the law of $(X_t)$ 

#### autoregressive moving average (ARMA) model
- The [[autoregressive moving average (ARMA) model]] of order $p$ $ARMA(p)$ is a combination of a [[autoregresive (AR) model]] and an [[moving average (MA) model]]
- captures the linear releationship of the current value to the past $p$ values and to the past $q$ error terms

models the [[time series]]
- with parameters $a_1, ..., a_p$ and $b_1, ..., b_p$
- [[white noise]] $e$ (i.i.d. with $\mathbb{E}[e] =0$ and $\mathbb{VAR}[e_t] \in (0, \infty)$)

$$
X_t = e_t + \sum_{i=1}^p a_i X_{t-i} + \sum_{i=1}^q b_i e_{t-i}  
$$

_______


### weakly stationary process
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- every starongly statanary process is also a (weakly) [[stationary process]]


Tags: mathematics time_series WS2425
<!--ID: 1734801203344-->
END



START
Basic
definitions for the following [[time series]] concepts with example:
- [[volatility]]
- [[drift]]
- [[trend]]

Back: 
### volatility
- subjective term and n clear defintion
- defree of variation of a [[stochastic process]]
- connected to the concept of squared [[variance]] 

### drift
- static component in a [[time series]]
- in the following example the parameter $c$ would quantify the [[drift]]

### trend
- the [[trend]] is a time variant component in a [[time series]]
- in the following example the parameter $\delta$ would be the trend


$$
\begin{split}
X_t &= c + \delta t \\
\tilde X_t &= \tilde X_t + c + \delta t \\
\end{split}
$$


Tags: mathematics time_series WS2425
<!--ID: 1735056916124-->
END
