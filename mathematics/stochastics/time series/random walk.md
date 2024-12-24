### random walk
- [[time series]] model where each value is equal to the previous values plus a [[white noise]] term $e_t$
- the [[random walk]] is equal to a [[autoregresive (AR) model]] of order $p=1$ with the parameter $a_1=1$

$$
X_t = X_{t-1} + e_t
$$
# ----

![[white noise#white noise]]

![[autoregresive (AR) model#autoregresive (AR) model]]


# anki

START
Basic
[[random walk]]
- definition
- relationship to [[autoregresive (AR) model]]

Back: 
### random walk
- [[time series]] model where each value is equal to the previous values plus a [[white noise]] term $e_t$
- the [[random walk]] is equal to a [[autoregresive (AR) model]] of order $p=1$ with the parameter $a_1=1$

$$
X_t = X_{t-1} + e_t
$$


### white noise
[[time series]] $(e_t, t \in \mathbb{Z})$ with 
- i.i.d. values
- zero mean $\mathbb{E}[e_t] = 0$  
- constant and finite [[variance]] $\mathbb{VAR}[e_t] = \mathbb{E}[e_t^2]= \sigma^2 \in (0, \infty)$  
- [[correlation|uncorralated]] values $t \neq s \Rightarrow  \mathbb{COV}[e_t, e_s] = \mathbb{COR}[e_t, e_s] = 0$

#### gaussian white noise
- [[white noise]] with [[normal distribution|normal distributed]] values $e_t \sim \mathcal{N}(0, \sigma^2)$

### autoregresive (AR) model
- The [[autoregresive (AR) model]] of order $p$ $AP(p)$ assumes the captures the linear releationship of the current value to the past p $p$ values
- assumes an at least [[stationary process]]

models the [[time series]]
- with parameters $a_1, ..., a_p$
- [[white noise]] $e$ (i.i.d. with $\mathbb{E}[e] =0$ and $\mathbb{VAR}[e_t] \in (0, \infty)$)

$$
X_t = \sum_{i=1}^p a_i X_{t-i}  + e_t
$$

Tags: mathematics time_series WS2425
<!--ID: 1735056916132-->
END
