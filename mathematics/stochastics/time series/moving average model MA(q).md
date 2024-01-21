## definition [[moving average model MA(q)]]
- discribes the current value as a linear combination of the past $p$  error / [[white noise]] terms
- caputes the direct effect (shok response) of the past error terms on the curent value
- assumes [[stationary process|weakly stationary]]

![[stationary process#Definition (weakly) stationary process]]

- [[stochastic process]] $\{X_t\}$  
- [[white noise]] $\epsilon$ with $\mathbb{E}[\epsilon_t] =0$ and $\mathbb{VAR}[\epsilon_t] =const$ and [[stochastic independent]] of $X_t$
- mean of the timeseries $\mu$ (sometimes assumed to be 0)
$$
X_t = \mu +  \epsilon_t  + \sum_{i=1}^q \theta_i \epsilon_{t-i} 
$$
## relationship to the [[autoregresive model AR(q)]]
### $AR(q)$ to $MA(\infty)$
- any $AR(q)$ model can be transfered to an eqivalent $MA(\infty)$ model  by repeated substitution
- in the following example it is shown with an $AR(1)$ model, but it's also possible with any $AR(q)$ model - the calculcation will be much more complicated but $X_t$ will also only depend on the past error terms $\epsilon_{t-h}$ and $\theta_i$ will depend on $\{\phi_1, ..., \phi_q \}$ 
- an $MA(q_1)$ model can also be approximated by any $AR(q)$ but the difference will be bigger the sameller $q_1$ is

#### example $AR(1)$ to $MA(\infty)$
![[autoregresive model AR(q)#Definition autoregresive model AR(q) AR(1) model]]

$$
\begin{split}
X_t 
&= \phi_1 X_{t-1} + \epsilon_t \\
&= \phi_1 \left(\phi_1 X_{t-2} + \epsilon_{t-1} \right) + \epsilon_t \\
&= \phi_1^2 X_{t-2} + \phi_1 \epsilon_{t-1}  + \epsilon_t \\
&= \phi_1^2 \left(\phi_1 X_{t-2} + \epsilon_{t-1} \right) + \phi_1 \epsilon_{t-1}  + \epsilon_t \\
&= \phi_1^3 X_{t-2}  + \phi_1^2  \epsilon_{t-2}  + \phi_1 \epsilon_{t-1}  + \epsilon_t \\
& ... \\
&=  \epsilon_t  + \phi_1^\infty X_{t-\infty} + \sum_{i=1}^q \phi_1^i \epsilon_{t-i} \\
&=  \epsilon_t  + \sum_{i=1}^q \phi_1^i \epsilon_{t-i} \\
\end{split}
$$

- since $\phi_1 \in (-1, 1)$ the term $\phi_1^\infty X_{t-\infty}$ is converging against zero and $X_t$ is only depending on the past error terms $\epsilon_{t-h}$
- the result will be similar to the $MA(\infty)$ model with the parameters $\theta_i = \phi_1^i$  

### $MA(q)$ to $AR(\infty)$  

#### example $MA(1)$ to $AR(\infty)$ 


# Anki

START
Basic
[[moving average model MA(q)]]
- definition
- transformation [[autoregresive model AR(q)]] to [[moving average model MA(q)]] with example
Back: 
#### definition [[moving average model MA(q)]]
- discribes the current value as a linear combination of the past $p$  error / [[white noise]] terms
- caputes the direct effect (shok response) of the past error terms on the curent value
- assumes [[stationary process|weakly stationary]]


- [[stochastic process]] $\{X_t\}$  
- [[white noise]] $\epsilon$ with $\mathbb{E}[\epsilon_t] =0$ and $\mathbb{VAR}[\epsilon_t] =const$ and [[stochastic independent]] of $X_t$
- mean of the timeseries $\mu$ (sometimes assumed to be 0)
$$
X_t = \mu +  \epsilon_t  + \sum_{i=1}^q \theta_i \epsilon_{t-i} 
$$

#### $AR(q)$ to $MA(\infty)$
- the $MA(\infty)$ model can be derrived from any the $AR(q)$ model by repeated substitution
- in the following example it is shown with an $AR(1)$ model, but it's also possible with any $AR(q)$ model - the calculcation will be much more complicated but $X_t$ will also only depend on the past error terms $\epsilon_{t-h}$ and $\theta_i$ will depend on $\{\phi_1, ..., \phi_q \}$ 
- an $MA(q_1)$ model can also be approximated by any $AR(q)$ but the difference will be bigger the sameller $q_1$ is
#### example $AR(1)$ to $MA(\infty)$

$$
\begin{split}
X_t 
&= \phi_1 X_{t-1} + \epsilon_t \\
&= \phi_1 \left(\phi_1 X_{t-2} + \epsilon_{t-1} \right) + \epsilon_t \\
&= \phi_1^2 X_{t-2} + \phi_1 \epsilon_{t-1}  + \epsilon_t \\
&= \phi_1^2 \left(\phi_1 X_{t-2} + \epsilon_{t-1} \right) + \phi_1 \epsilon_{t-1}  + \epsilon_t \\
&= \phi_1^3 X_{t-2}  + \phi_1^2  \epsilon_{t-2}  + \phi_1 \epsilon_{t-1}  + \epsilon_t \\
& ... \\
&=  \epsilon_t  + \phi_1^\infty X_{t-\infty} + \sum_{i=1}^q \phi_1^i \epsilon_{t-i} \\
&=  \epsilon_t  + \sum_{i=1}^q \phi_1^i \epsilon_{t-i} \\
\end{split}
$$

- since $\phi_1 \in (-1, 1)$ the term $\phi_1^\infty X_{t-\infty}$ is converging against zero and $X_t$ is only depending on the past error terms $\epsilon_{t-h}$
- the result will be similar to the $MA(\infty)$ model with the parameters $\theta_i = \phi_1^i$  

#### definition [[autoregresive model AR(q)]]
- The [[autoregresive model AR(q)]] of order $p$ $AP(p)$ assumes the captures the linear releationship of the current value to the past p $p$ values
- assumes an at least [[stationary process]]


- [[stochastic process]] $\{X_t\}$  
- white noise $\epsilon$ with $\mathbb{E}[\epsilon] =0$ and $\mathbb{VAR}[\epsilon] =const$ and [[stochastic independent]] of $X_t$
- constant $\beta$ ( assumed to be zero here)
$$
X_t = \sum_{i=1}^p \phi_i X_{t-i} + \epsilon
$$

#### Definition (weakly) [[stationary process]]
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- every starongly statanary process is also a (weakly) [[stationary process]]

Tags: mathematics time_series
<!--ID: 1705832321108-->
END



START
Basic


Back: 
### definition


#### Definition (weakly) [[stationary process]]
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- every starongly statanary process is also a (weakly) [[stationary process]]

Tags: mathematics time_series

END