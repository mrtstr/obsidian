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

### stationarity of the MA model
- [[stationary process|stationarity]] of the [[moving average (MA) model]]

$$
\begin{split}
\mathbb{E}\left[X_t\right] &= \mathbb{E}\left[e_t\right]    + \sum_{i=1}^q b_i \mathbb{E}\left[e_{t-i}\right] = 0  \\
\mathbb{COV}\left[X_t, X_{t+h}\right] 
&= \mathbb{E}\left[X_t X_{t+h}\right] \\
&= \mathbb{E}\left[\left(\sum_{i=0}^q b_i e_{t-i} \right)\left(\sum_{i=0}^q b_i e_{t+h-i} \right)\right] \\
&= \sum_{i=0}^q \sum_{j=0}^q b_i b_j \mathbb{E}\left[e_{t-i}e_{t+h-j}\right] \\
&= \sigma^2 \sum_{i=0}^q \sum_{j=0}^q b_i b_j \mathbb{I}[t-i = t+h-j] \\
&= \sigma^2 \sum_{i=0}^{q-|h|}  b_i b_{i-|h|}  \\
\end{split}
$$

### relationship to autoregresive models 
- any [[autoregresive (AR) model]] $AR(q)$ model can be transfered to an eqivalent $MA(\infty)$ model  by repeated substitution
- in the following example it is shown with an $AR(1)$ model, but it's also possible with any $AR(q)$ model - the calculcation will be much more complicated but $X_t$ will also only depend on the past error terms $e_{t-h}$ and $b_i$ will depend on $\{\phi_1, ..., \phi_q \}$ 
- an $MA(q_1)$ model can also be approximated by any $AR(q)$ but the difference will be bigger the sameller $q_1$ is

#### example $AR(1)$ to $MA(\infty)$


$$
\begin{split}
X_t 
&= \phi_1 X_{t-1} + e_t \\
&= \phi_1 \left(\phi_1 X_{t-2} + e_{t-1} \right) + e_t \\
&= \phi_1^2 X_{t-2} + \phi_1 e_{t-1}  + e_t \\
&= \phi_1^2 \left(\phi_1 X_{t-2} + e_{t-1} \right) + \phi_1 e_{t-1}  + e_t \\
&= \phi_1^3 X_{t-2}  + \phi_1^2  e_{t-2}  + \phi_1 e_{t-1}  + e_t \\
& ... \\
&=  e_t  + \phi_1^\infty X_{t-\infty} + \sum_{i=1}^q \phi_1^i e_{t-i} \\
&=  e_t  + \sum_{i=1}^q \phi_1^i e_{t-i} \\
\end{split}
$$

- since $\phi_1 \in (-1, 1)$ the term $\phi_1^\infty X_{t-\infty}$ is converging against zero and $X_t$ is only depending on the past error terms $e_{t-h}$
- the result will be similar to the $MA(\infty)$ model with the parameters $b_i = \phi_1^i$  

# -----------------
![[autoregresive (AR) model#autoregresive model of order 1 $AR(1)$]]

![[stationary process#weakly stationary process]]

# Anki

START
Basic
[[moving average (MA) model]]
- definition
- inerpretation
Back: 
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

Tags: mathematics time_series WS2425
<!--ID: 1705832321108-->
END



START
Basic
relationship
[[moving average (MA) model]] and [[autoregresive (AR) model]]

Back: 

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

### relationship to autoregresive models 
- any [[autoregresive (AR) model]] $AR(q)$ model can be transfered to an eqivalent $MA(\infty)$ model  by repeated substitution
- in the following example it is shown with an $AR(1)$ model, but it's also possible with any $AR(q)$ model - the calculcation will be much more complicated but $X_t$ will also only depend on the past error terms $e_{t-h}$ and $b_i$ will depend on $\{\phi_1, ..., \phi_q \}$ 
- an $MA(q_1)$ model can also be approximated by any $AR(q)$ but the difference will be bigger the sameller $q_1$ is

#### example $AR(1)$ to $MA(\infty)$


$$
\begin{split}
X_t 
&= \phi_1 X_{t-1} + e_t \\
&= \phi_1 \left(\phi_1 X_{t-2} + e_{t-1} \right) + e_t \\
&= \phi_1^2 X_{t-2} + \phi_1 e_{t-1}  + e_t \\
&= \phi_1^2 \left(\phi_1 X_{t-2} + e_{t-1} \right) + \phi_1 e_{t-1}  + e_t \\
&= \phi_1^3 X_{t-2}  + \phi_1^2  e_{t-2}  + \phi_1 e_{t-1}  + e_t \\
& ... \\
&=  e_t  + \phi_1^\infty X_{t-\infty} + \sum_{i=1}^q \phi_1^i e_{t-i} \\
&=  e_t  + \sum_{i=1}^q \phi_1^i e_{t-i} \\
\end{split}
$$

- since $\phi_1 \in (-1, 1)$ the term $\phi_1^\infty X_{t-\infty}$ is converging against zero and $X_t$ is only depending on the past error terms $e_{t-h}$
- the result will be similar to the $MA(\infty)$ model with the parameters $b_i = \phi_1^i$  

Tags: mathematics time_series WS2425
<!--ID: 1734777204036-->
END


START
Basic
[[stationary process|weak stationarity]] of the [[moving average (MA) model]]
- proof

Back: 

### stationarity of the MA model
- [[stationary process|stationarity]] of the [[moving average (MA) model]]

$$
\begin{split}
\mathbb{E}\left[X_t\right] &= \mathbb{E}\left[e_t\right]    + \sum_{i=1}^q b_i \mathbb{E}\left[e_{t-i}\right] = 0  \\
\mathbb{COV}\left[X_t, X_{t+h}\right] 
&= \mathbb{E}\left[X_t X_{t+h}\right] \\
&= \mathbb{E}\left[\left(\sum_{i=0}^q b_i e_{t-i} \right)\left(\sum_{i=0}^q b_i e_{t+h-i} \right)\right] \\
&= \sum_{i=0}^q \sum_{j=0}^q b_i b_j \mathbb{E}\left[e_{t-i}e_{t+h-j}\right] \\
&= \sigma^2 \sum_{i=0}^q \sum_{j=0}^q b_i b_j \mathbb{I}[t-i = t+h-j] \\
&= \sigma^2 \sum_{i=0}^{q-|h|}  b_i b_{i-|h|}  \\
\end{split}
$$


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

Tags: mathematics time_series WS2425
<!--ID: 1734801203341-->
END
