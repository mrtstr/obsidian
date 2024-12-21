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


## autoregresive model of order 1 $AR(1)$

$$
X_t = a_1 X_{t-1} + \beta + e_t
$$


#### expectation
$$
\begin{split}
\mathbb{E}\left[X_t\right] = \frac{\beta}{1-a_1}
\end{split}
$$
$$
\begin{split}
\mathbb{E}\left[X_t\right] 
&= \mathbb{E}\left[a_1 X_{t-1} + \beta + e\right] \\
&= a_1 \mathbb{E}\left[ X_{t-1} \right] +  \mathbb{E}\left[e\right] + \beta \\
&= a_1 \mathbb{E}\left[ X_{t} \right] + \beta \\
&= \frac{\beta}{1-a_1} \\
\end{split}
$$

#### variance
$$
\begin{split}
\mathbb{VAR}\left[X_t\right] = \frac{\mathbb{VAR}\left[e\right]}{1-a_1^2}
\end{split}
$$

$$
\begin{split}
\mathbb{VAR}\left[X_t\right] 
&= \mathbb{VAR}\left[a_1 X_{t-1} + \beta + e\right] \\
&= a_1^2 \mathbb{VAR}\left[ X_{t-1}\right] + \mathbb{VAR}\left[e\right]\\
&= a_1^2 \mathbb{VAR}\left[ X_{t}\right] + \mathbb{VAR}\left[e\right]\\
&= \frac{\mathbb{VAR}\left[e\right]}{1-a_1^2}
\end{split}
$$


### autocovariance
$$
\begin{split}
\mathbb{COV}\left[X_t X_{t-h}\right] 
&= a_1^h \mathbb{COV}\left[X_t X_{t-0}\right] \\ 
&= a_1^h \mathbb{VAR}\left[X_t\right] \\ 
\end{split}
$$

$$
\begin{split}
\mathbb{COV}\left[X_t X_{t-1}\right] 
&= \mathbb{COV}\left[X_t X_{t+1}\right] \\
&= \mathbb{E}\left[X_t X_{t+1}\right] - \mathbb{E}\left[X_t X_{t+1}\right] \\
&= \mathbb{E}\left[X_t \left(a_1 X_{t} + \beta + e_t \right)\right] - \mathbb{E}\left[X_t \left(a_1 X_{t} + \beta + e_t \right)\right] \\
&= a_1 \mathbb{E}\left[X_t^2\right] + \mathbb{E}\left[X_t\right] \beta 
- a_1 \mathbb{E}\left[X_t\right]^2  -\mathbb{E}\left[X_t\right] \beta  \\

&= a_1 \mathbb{E}\left[X_t^2\right] + 
- a_1 \mathbb{E}\left[X_t\right]^2   \\

&= a_1 \mathbb{COV}\left[X_t X_{t-0}\right]    \\


\mathbb{COV}\left[X_t X_{t-2}\right] 
&= \mathbb{COV}\left[X_t X_{t+2}\right] \\
&= \mathbb{E}\left[X_t X_{t+2}\right] - \mathbb{E}\left[X_t X_{t+2}\right] \\
&= \mathbb{E}\left[X_t \left(a_1 X_{t+1} + \beta + e_{t+1} \right)\right] - \mathbb{E}\left[X_t \left(a_1 X_{t+1} + \beta + e_{t+1} \right)\right] \\
&= a_1 \mathbb{E}\left[X_t X_{t+1}\right] + \mathbb{E}\left[X_t\right] \beta 
- a_1 \mathbb{E}\left[X_t\right] \mathbb{E}\left[X_{t+1}\right] -\mathbb{E}\left[X_t\right] \beta  \\



&= a_1 \mathbb{COV}\left[X_t X_{t-1}\right]    \\
&= a_1^2 \mathbb{COV}\left[X_t X_{t-0}\right]    \\
&= a_1^2 \mathbb{VAR}\left[X_t\right]      \\
\Rightarrow \mathbb{E}\left[X_t X_{t-h}\right]
&= a_1^h \mathbb{COV}\left[X_t X_{t-0}\right]  \\
&= a_1^h \mathbb{VAR}\left[X_t\right]  
\end{split}
$$

#### autocorrelation (ACF)


$$
\begin{split}
\rho(h) 
&= a_1^h
\end{split}
$$

$$
\begin{split}
\rho(h) 
&= \frac{ \mathbb{COV}\left[X_{t}, X_{t - h}\right]}{\mathbb{VAR}\left[X_{t}\right]} \\
&= \frac{a_1^h \mathbb{VAR}\left[X_t\right]}{\mathbb{VAR}\left[X_{t}\right]} \\
&=  a_1^h \\
\end{split}
$$

# ----------------------------

![[stationary process#weakly stationary process]]

![[white noise#white noise]]


# Anki

START
Basic
#### [[autoregresive (AR) model]]
- definition
- [[expectation]] and [[variance]] of $AR(1)$

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


## autoregresive model of order 1 $AR(1)$

$$
X_t = a_1 X_{t-1} + \beta + e_t
$$


#### expectation
$$
\begin{split}
\mathbb{E}\left[X_t\right] = \frac{\beta}{1-a_1}
\end{split}
$$
$$
\begin{split}
\mathbb{E}\left[X_t\right] 
&= \mathbb{E}\left[a_1 X_{t-1} + \beta + e\right] \\
&= a_1 \mathbb{E}\left[ X_{t-1} \right] +  \mathbb{E}\left[e\right] + \beta \\
&= a_1 \mathbb{E}\left[ X_{t} \right] + \beta \\
&= \frac{\beta}{1-a_1} \\
\end{split}
$$

#### variance
$$
\begin{split}
\mathbb{VAR}\left[X_t\right] = \frac{\mathbb{VAR}\left[e\right]}{1-a_1^2}
\end{split}
$$

$$
\begin{split}
\mathbb{VAR}\left[X_t\right] 
&= \mathbb{VAR}\left[a_1 X_{t-1} + \beta + e\right] \\
&= a_1^2 \mathbb{VAR}\left[ X_{t-1}\right] + \mathbb{VAR}\left[e\right]\\
&= a_1^2 \mathbb{VAR}\left[ X_{t}\right] + \mathbb{VAR}\left[e\right]\\
&= \frac{\mathbb{VAR}\left[e\right]}{1-a_1^2}
\end{split}
$$


_______


### weakly stationary process
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- every starongly statanary process is also a (weakly) [[stationary process]]


### white noise
[[time series]] $(e_t, t \in \mathbb{Z})$ with 
- i.i.d. values
- zero mean $\mathbb{E}[e_t] = 0$  
- constant and finite [[variance]] $\mathbb{VAR}[e_t] = \mathbb{E}[e_t^2]= \sigma^2 \in (0, \infty)$  
- [[correlation|uncorralated]] values $t \neq s \Rightarrow  \mathbb{COV}[e_t, e_s] = \mathbb{COR}[e_t, e_s] = 0$

#### gaussian white noise
- [[white noise]] with [[normal distribution|normal distributed]] values $e_t \sim \mathcal{N}(0, \sigma^2)$



Tags: mathematics time_series WS2425
<!--ID: 1705250198064-->
END







START
Basic
#### [[autoregresive (AR) model]]
- definition
- [[autocorrelation (ACF)]] and [[autocovariance]]  of $AR(1)$ (np proof)

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


## autoregresive model of order 1 $AR(1)$

$$
X_t = a_1 X_{t-1} + \beta + e_t
$$


#### expectation
$$
\begin{split}
\mathbb{E}\left[X_t\right] = \frac{\beta}{1-a_1}
\end{split}
$$
$$
\begin{split}
\mathbb{E}\left[X_t\right] 
&= \mathbb{E}\left[a_1 X_{t-1} + \beta + e\right] \\
&= a_1 \mathbb{E}\left[ X_{t-1} \right] +  \mathbb{E}\left[e\right] + \beta \\
&= a_1 \mathbb{E}\left[ X_{t} \right] + \beta \\
&= \frac{\beta}{1-a_1} \\
\end{split}
$$

#### variance
$$
\begin{split}
\mathbb{VAR}\left[X_t\right] = \frac{\mathbb{VAR}\left[e\right]}{1-a_1^2}
\end{split}
$$

$$
\begin{split}
\mathbb{VAR}\left[X_t\right] 
&= \mathbb{VAR}\left[a_1 X_{t-1} + \beta + e\right] \\
&= a_1^2 \mathbb{VAR}\left[ X_{t-1}\right] + \mathbb{VAR}\left[e\right]\\
&= a_1^2 \mathbb{VAR}\left[ X_{t}\right] + \mathbb{VAR}\left[e\right]\\
&= \frac{\mathbb{VAR}\left[e\right]}{1-a_1^2}
\end{split}
$$


### autocovariance
$$
\begin{split}
\mathbb{COV}\left[X_t X_{t-h}\right] 
&= a_1^h \mathbb{COV}\left[X_t X_{t-0}\right] \\ 
&= a_1^h \mathbb{VAR}\left[X_t\right] \\ 
\end{split}
$$

$$
\begin{split}
\mathbb{COV}\left[X_t X_{t-1}\right] 
&= \mathbb{COV}\left[X_t X_{t+1}\right] \\
&= \mathbb{E}\left[X_t X_{t+1}\right] - \mathbb{E}\left[X_t X_{t+1}\right] \\
&= \mathbb{E}\left[X_t \left(a_1 X_{t} + \beta + e_t \right)\right] - \mathbb{E}\left[X_t \left(a_1 X_{t} + \beta + e_t \right)\right] \\
&= a_1 \mathbb{E}\left[X_t^2\right] + \mathbb{E}\left[X_t\right] \beta 
- a_1 \mathbb{E}\left[X_t\right]^2  -\mathbb{E}\left[X_t\right] \beta  \\

&= a_1 \mathbb{E}\left[X_t^2\right] + 
- a_1 \mathbb{E}\left[X_t\right]^2   \\

&= a_1 \mathbb{COV}\left[X_t X_{t-0}\right]    \\


\mathbb{COV}\left[X_t X_{t-2}\right] 
&= \mathbb{COV}\left[X_t X_{t+2}\right] \\
&= \mathbb{E}\left[X_t X_{t+2}\right] - \mathbb{E}\left[X_t X_{t+2}\right] \\
&= \mathbb{E}\left[X_t \left(a_1 X_{t+1} + \beta + e_{t+1} \right)\right] - \mathbb{E}\left[X_t \left(a_1 X_{t+1} + \beta + e_{t+1} \right)\right] \\
&= a_1 \mathbb{E}\left[X_t X_{t+1}\right] + \mathbb{E}\left[X_t\right] \beta 
- a_1 \mathbb{E}\left[X_t\right] \mathbb{E}\left[X_{t+1}\right] -\mathbb{E}\left[X_t\right] \beta  \\



&= a_1 \mathbb{COV}\left[X_t X_{t-1}\right]    \\
&= a_1^2 \mathbb{COV}\left[X_t X_{t-0}\right]    \\
&= a_1^2 \mathbb{VAR}\left[X_t\right]      \\
\Rightarrow \mathbb{E}\left[X_t X_{t-h}\right]
&= a_1^h \mathbb{COV}\left[X_t X_{t-0}\right]  \\
&= a_1^h \mathbb{VAR}\left[X_t\right]  
\end{split}
$$

#### autocorrelation (ACF)


$$
\begin{split}
\rho(h) 
&= a_1^h
\end{split}
$$

$$
\begin{split}
\rho(h) 
&= \frac{ \mathbb{COV}\left[X_{t}, X_{t - h}\right]}{\mathbb{VAR}\left[X_{t}\right]} \\
&= \frac{a_1^h \mathbb{VAR}\left[X_t\right]}{\mathbb{VAR}\left[X_{t}\right]} \\
&=  a_1^h \\
\end{split}
$$


_______


### weakly stationary process
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- every starongly statanary process is also a (weakly) [[stationary process]]


### white noise
[[time series]] $(e_t, t \in \mathbb{Z})$ with 
- i.i.d. values
- zero mean $\mathbb{E}[e_t] = 0$  
- constant and finite [[variance]] $\mathbb{VAR}[e_t] = \mathbb{E}[e_t^2]= \sigma^2 \in (0, \infty)$  
- [[correlation|uncorralated]] values $t \neq s \Rightarrow  \mathbb{COV}[e_t, e_s] = \mathbb{COR}[e_t, e_s] = 0$

#### gaussian white noise
- [[white noise]] with [[normal distribution|normal distributed]] values $e_t \sim \mathcal{N}(0, \sigma^2)$


Tags: mathematics time_series WS2425
<!--ID: 1705250198077-->
END



START
Basic
#### [[autoregresive (AR) model]] of order 1 $AR(1)$
- definition
- [[expectation]] without proof
- [[variance]] without proof
- [[autocovariance]] without proof
- [[autocorrelation (ACF)]] without proof

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


## autoregresive model of order 1 $AR(1)$

$$
X_t = a_1 X_{t-1} + \beta + e_t
$$


#### expectation
$$
\begin{split}
\mathbb{E}\left[X_t\right] = \frac{\beta}{1-a_1}
\end{split}
$$
$$
\begin{split}
\mathbb{E}\left[X_t\right] 
&= \mathbb{E}\left[a_1 X_{t-1} + \beta + e\right] \\
&= a_1 \mathbb{E}\left[ X_{t-1} \right] +  \mathbb{E}\left[e\right] + \beta \\
&= a_1 \mathbb{E}\left[ X_{t} \right] + \beta \\
&= \frac{\beta}{1-a_1} \\
\end{split}
$$

#### variance
$$
\begin{split}
\mathbb{VAR}\left[X_t\right] = \frac{\mathbb{VAR}\left[e\right]}{1-a_1^2}
\end{split}
$$

$$
\begin{split}
\mathbb{VAR}\left[X_t\right] 
&= \mathbb{VAR}\left[a_1 X_{t-1} + \beta + e\right] \\
&= a_1^2 \mathbb{VAR}\left[ X_{t-1}\right] + \mathbb{VAR}\left[e\right]\\
&= a_1^2 \mathbb{VAR}\left[ X_{t}\right] + \mathbb{VAR}\left[e\right]\\
&= \frac{\mathbb{VAR}\left[e\right]}{1-a_1^2}
\end{split}
$$


### autocovariance
$$
\begin{split}
\mathbb{COV}\left[X_t X_{t-h}\right] 
&= a_1^h \mathbb{COV}\left[X_t X_{t-0}\right] \\ 
&= a_1^h \mathbb{VAR}\left[X_t\right] \\ 
\end{split}
$$

$$
\begin{split}
\mathbb{COV}\left[X_t X_{t-1}\right] 
&= \mathbb{COV}\left[X_t X_{t+1}\right] \\
&= \mathbb{E}\left[X_t X_{t+1}\right] - \mathbb{E}\left[X_t X_{t+1}\right] \\
&= \mathbb{E}\left[X_t \left(a_1 X_{t} + \beta + e_t \right)\right] - \mathbb{E}\left[X_t \left(a_1 X_{t} + \beta + e_t \right)\right] \\
&= a_1 \mathbb{E}\left[X_t^2\right] + \mathbb{E}\left[X_t\right] \beta 
- a_1 \mathbb{E}\left[X_t\right]^2  -\mathbb{E}\left[X_t\right] \beta  \\

&= a_1 \mathbb{E}\left[X_t^2\right] + 
- a_1 \mathbb{E}\left[X_t\right]^2   \\

&= a_1 \mathbb{COV}\left[X_t X_{t-0}\right]    \\


\mathbb{COV}\left[X_t X_{t-2}\right] 
&= \mathbb{COV}\left[X_t X_{t+2}\right] \\
&= \mathbb{E}\left[X_t X_{t+2}\right] - \mathbb{E}\left[X_t X_{t+2}\right] \\
&= \mathbb{E}\left[X_t \left(a_1 X_{t+1} + \beta + e_{t+1} \right)\right] - \mathbb{E}\left[X_t \left(a_1 X_{t+1} + \beta + e_{t+1} \right)\right] \\
&= a_1 \mathbb{E}\left[X_t X_{t+1}\right] + \mathbb{E}\left[X_t\right] \beta 
- a_1 \mathbb{E}\left[X_t\right] \mathbb{E}\left[X_{t+1}\right] -\mathbb{E}\left[X_t\right] \beta  \\



&= a_1 \mathbb{COV}\left[X_t X_{t-1}\right]    \\
&= a_1^2 \mathbb{COV}\left[X_t X_{t-0}\right]    \\
&= a_1^2 \mathbb{VAR}\left[X_t\right]      \\
\Rightarrow \mathbb{E}\left[X_t X_{t-h}\right]
&= a_1^h \mathbb{COV}\left[X_t X_{t-0}\right]  \\
&= a_1^h \mathbb{VAR}\left[X_t\right]  
\end{split}
$$

#### autocorrelation (ACF)


$$
\begin{split}
\rho(h) 
&= a_1^h
\end{split}
$$

$$
\begin{split}
\rho(h) 
&= \frac{ \mathbb{COV}\left[X_{t}, X_{t - h}\right]}{\mathbb{VAR}\left[X_{t}\right]} \\
&= \frac{a_1^h \mathbb{VAR}\left[X_t\right]}{\mathbb{VAR}\left[X_{t}\right]} \\
&=  a_1^h \\
\end{split}
$$


_______


### weakly stationary process
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- every starongly statanary process is also a (weakly) [[stationary process]]


### white noise
[[time series]] $(e_t, t \in \mathbb{Z})$ with 
- i.i.d. values
- zero mean $\mathbb{E}[e_t] = 0$  
- constant and finite [[variance]] $\mathbb{VAR}[e_t] = \mathbb{E}[e_t^2]= \sigma^2 \in (0, \infty)$  
- [[correlation|uncorralated]] values $t \neq s \Rightarrow  \mathbb{COV}[e_t, e_s] = \mathbb{COR}[e_t, e_s] = 0$

#### gaussian white noise
- [[white noise]] with [[normal distribution|normal distributed]] values $e_t \sim \mathcal{N}(0, \sigma^2)$

Tags: mathematics time_series WS2425
<!--ID: 1705250198080-->
END