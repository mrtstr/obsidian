### autoregressive moving average (ARMA) model
- The [[autoregressive moving average (ARMA) model]] of order $p$ $ARMA(p)$ is a combination of a [[autoregresive (AR) model]] and an [[moving average (MA) model]]
- captures the linear releationship of the current value to the past $p$ values and to the past $q$ error terms

models the [[time series]]
- with parameters $a_1, ..., a_p$ and $b_1, ..., b_p$
- [[white noise]] $e$ (i.i.d. with $\mathbb{E}[e] =0$ and $\mathbb{VAR}[e_t] \in (0, \infty)$)

$$
X_t = e_t + \sum_{i=1}^p a_i X_{t-i} + \sum_{i=1}^q b_i e_{t-i}  
$$

# -----------------

![[autoregresive (AR) model#autoregresive (AR) model]]

![[moving average (MA) model#moving average model MA(q)]]


# Anki

START
Basic
[[autoregressive moving average (ARMA) model]]
- definition
- interpretation

Back: 
### autoregressive moving average (ARMA) model
- The [[autoregressive moving average (ARMA) model]] of order $p$ $ARMA(p)$ is a combination of a [[autoregresive (AR) model]] and an [[moving average (MA) model]]
- captures the linear releationship of the current value to the past $p$ values and to the past $q$ error terms

models the [[time series]]
- with parameters $a_1, ..., a_p$ and $b_1, ..., b_p$
- [[white noise]] $e$ (i.i.d. with $\mathbb{E}[e] =0$ and $\mathbb{VAR}[e_t] \in (0, \infty)$)

$$
X_t = e_t + \sum_{i=1}^p a_i X_{t-i} + \sum_{i=1}^q b_i e_{t-i}  
$$


_______
### moving average model MA(q)
- discribes the current value as a linear combination of the past $p$  error / [[white noise]] terms
models the [[time series]]
- with parameters $b_1, ..., b_p$
- [[white noise]] $e$ (i.i.d. with $\mathbb{E}[e] =0$ and $\mathbb{VAR}[e_t] \in (0, \infty)$)
- mean of the timeseries $\mu$ (sometimes assumed to be 0)

$$
X_t = \mu +  e_t  + \sum_{i=1}^q b_i e_{t-i} 
$$

#### interpretation
- caputes the direct effect (shok response) of the past error terms on the curent value
- assumes [[stationary process|weakly stationary]]



### autoregresive (AR) model
- The [[autoregresive (AR) model]] of order $p$ $AP(p)$ assumes the captures the linear releationship of the current value to the past p $p$ values
- assumes an at least [[stationary process]]

models the [[time series]]
- with parameters $a_1, ..., a_p$
- [[white noise]] $e$ (i.i.d. with $\mathbb{E}[e] =0$ and $\mathbb{VAR}[e_t] \in (0, \infty)$)
- constant $\beta$ (sometimes assumed to be zero)
$$
X_t = \sum_{i=1}^p a_i X_{t-i} + \beta + e_t
$$



### weakly stationary process
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- every starongly statanary process is also a (weakly) [[stationary process]]


### white noise
[[time series]] $(e_t, t \in \mathbb{Z})$ with 
- zero mean $\mathbb{E}[e_t] = 0$  
- [[correlation|uncorralated]] values $t \neq s \Rightarrow  \mathbb{COV}[e_t, e_s] = \mathbb{COR}[e_t, e_s] = 0$
#### gaussian white noise
- [[white noise]] with [[normal distribution|normal distributed]] values $e_t \sim \mathcal{N}(0, \sigma^2)$



Tags: mathematics time_series WS2425
<!--ID: 1734801203337-->
END
