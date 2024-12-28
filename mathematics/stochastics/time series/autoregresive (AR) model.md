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
### parameter estimation
- first estimate the [[autocorrelation (ACF)]]

### parameter estimation
- first estimate the [[autocorrelation (ACF)]] $\hat\rho(h)$ using a [[estimators for stationary time series#autocorrelation estimators for stationary time series|autocorrelation estimators for stationary time series]]

$$
\begin{split}
\hat X_n &= \sum_{i \in [n]} X_i \\
\hat\gamma_n(h) &= \frac{1}{n} \sum_{t=1}^{n-|h|} \left(X_t- X_n\right)\left(X_{t+h}- X_n\right) \\
\hat\rho_n(h) &= \frac{\hat\gamma_n(h)}{\hat\gamma_n(0)}  \\
\end{split}
$$


- use the [[yule walker equation]] to calculate the parameter vector

$$
\begin{split}
RA = r \Leftrightarrow A = R^{-1}r
\end{split}
$$

$$
\begin{split}
A &= \left(\begin{matrix}
a_1 & ... & a_p
\end{matrix}\right) \\
r &= (\rho(r))_{r \in [n]} = \left(\begin{matrix}
\rho(1) & ... & \rho(p)
\end{matrix}\right) \\
R &= (\rho(r-s))_{r, s \in [n]} \left(\begin{matrix}
1 & \rho(1) & ... & \rho(p-1) \\
\rho(1) & 1 & ... & \rho(p-2) \\
 &  & ... & \ \\
 \rho(p-1) & \rho(p-2) & ... & 1 \\
\end{matrix}\right)
\end{split}
$$


- use the [[yule walker equation]] to calculate the parameter vector

### autoregresive model of order 1 $AR(1)$

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
##### proof with yule walker equation

$$
\begin{split}
\rho_{X}(h) &= a_1 \rho_{X}(h-1)  \\
\rho_{X}(1) &= a_1 \rho_{X}(0) = a_1  \\
\rho_{X}(2) &= a_1 \rho_{X}(1) = a_1^2  \\
\rho_{X}(h) &= a_1 \rho_{X}(h-1) = a_1^h  \\
\end{split}
$$

#### parameter boundarys

$$
\begin{split}
a_1 
&=  \frac{\rho_{X}(1)}{\rho_{X}(0)}   \\
&=  \rho_{X}(1) \in [-1,1]  \\
\end{split}
$$



# ----------------------------
![[yule walker equation#yule walker equation]]

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
#### [[autoregresive (AR) model]]
- [[autocorrelation (ACF)]] with proof using the [[yule walker equation]]

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



#### autocorrelation (ACF)


$$
\begin{split}
\rho(h) 
&= a_1^h
\end{split}
$$


##### proof with yule walker equation

$$
\begin{split}
\rho_{X}(h) &= a_1 \rho_{X}(h-1)  \\
\rho_{X}(1) &= a_1 \rho_{X}(0) = a_1  \\
\rho_{X}(2) &= a_1 \rho_{X}(1) = a_1^2  \\
\rho_{X}(h) &= a_1 \rho_{X}(h-1) = a_1^h  \\
\end{split}
$$

_____________________

### yule walker equation
- for [[statistical estimator|estimating]] the parameters $a_1, ..., a_p$ of an [[autoregresive (AR) model]]

- fo $h > 0$
$$
\begin{split}
\rho_{X}(h) 
&= a_1 \rho_{X}(h-1) + a_2 \rho_{X}(h-2) + ... + a_p \rho_{X}(h-p) \\
&= \sum_{i=1}^p a_i \rho_{X}(h-i)  \\
\end{split}
$$

- fo $h = 0$
$$
\begin{split}
\rho_{X}(0) - \sigma^2_e
&= \sum_{i=1}^p a_i \rho_{X}(0-i)  \\
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
<!--ID: 1734865948126-->
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


START
Basic
given an [[autoregresive (AR) model]] of order 1 $AR(1)$
- which values can the parameter $a_1$ take (with proof)

Back: 

## autoregresive model of order 1 $AR(1)$

$$
X_t = a_1 X_{t-1} + \beta + e_t
$$



#### parameter boundarys
- since the [[correlation]] can only take values between $-1$ and $1$

$$
\begin{split}
a_1 
&=  \frac{\rho_{X}(1)}{\rho_{X}(0)}   \\
&=  \rho_{X}(1) \in [-1,1]  \\
\end{split}
$$


_____________________



### yule walker equation
- for [[statistical estimator|estimating]] the parameters $a_1, ..., a_p$ of an [[autoregresive (AR) model]]

- fo $h > 0$
$$
\begin{split}
\rho_{X}(h) 
&= a_1 \rho_{X}(h-1) + a_2 \rho_{X}(h-2) + ... + a_p \rho_{X}(h-p) \\
&= \sum_{i=1}^p a_i \rho_{X}(h-i)  \\
\end{split}
$$

- fo $h = 0$
$$
\begin{split}
\rho_{X}(0) - \sigma^2_e
&= \sum_{i=1}^p a_i \rho_{X}(0-i)  \\
\end{split}
$$


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
- i.i.d. values
- zero mean $\mathbb{E}[e_t] = 0$  
- constant and finite [[variance]] $\mathbb{VAR}[e_t] = \mathbb{E}[e_t^2]= \sigma^2 \in (0, \infty)$  
- [[correlation|uncorralated]] values $t \neq s \Rightarrow  \mathbb{COV}[e_t, e_s] = \mathbb{COR}[e_t, e_s] = 0$

#### gaussian white noise
- [[white noise]] with [[normal distribution|normal distributed]] values $e_t \sim \mathcal{N}(0, \sigma^2)$


### correlation
- The [[correlation]] is a measure for the linear dependency of [[random variable|random variables]] 
- in contrast to the [[covariance]] the [[correlation]] is not depending on the absolut size of the [[random variable|random variables]]
$$
\rho[X,Y] =\frac{\mathbb{COVAR}[X,Y]}{\sqrt{\mathbb{VAR}[X]\mathbb{VAR}[Y]}}
$$



#### boundarys
$$
-1 \leq \rho[X,Y] \leq 1
$$
##### cauchy schwarz inequality for probabilities

$$
\mathbb{COV}[X, Y]^2 \leq \mathbb{VAR}[X]  \mathbb{VAR}[Y]
$$


$$
\begin{split}
0 
&\leq \mathbb{E}\left[(X-\lambda Y)^2\right] \\
&\leq \mathbb{E}\left[X^2\right] + \lambda^2 \mathbb{E}\left[Y^2\right] - 2\lambda\mathbb{E}\left[XY\right] \quad \text{with } \lambda = \frac{\mathbb{E}\left[XY\right]}{\mathbb{E}\left[Y^2\right]} \\

&\leq \mathbb{E}\left[X^2\right] + \left(\frac{\mathbb{E}\left[XY\right]}{\mathbb{E}\left[Y^2\right]}\right)^2 \mathbb{E}\left[Y^2\right] -2 \frac{\mathbb{E}\left[XY\right]}{\mathbb{E}\left[Y^2\right]} \mathbb{E}\left[XY\right] \\
&\leq \mathbb{E}\left[X^2\right] + \frac{\mathbb{E}\left[XY\right]^2}{\mathbb{E}\left[Y^2\right]}  - 2\frac{\mathbb{E}\left[XY\right]^2}{\mathbb{E}\left[Y^2\right]}  \\
&\leq \mathbb{E}\left[X^2\right]  - \frac{\mathbb{E}\left[XY\right]^2}{\mathbb{E}\left[Y^2\right]}  \\
&\leq \mathbb{E}\left[X^2\right]\mathbb{E}\left[Y^2\right]  - \mathbb{E}\left[XY\right]^2  \\
\Rightarrow \mathbb{E}\left[XY\right]^2 &\leq \mathbb{E}\left[X^2\right]\mathbb{E}\left[Y^2\right]
\end{split}
$$

- let $X' = X - \mathbb{E}[X]$ and $Y' = Y - \mathbb{E}[Y]$

$$
\begin{split}
&\mathbb{E}\left[X'Y'\right]^2 \leq \mathbb{E}\left[^2\right]\mathbb{E}\left[Y'^2\right] \\
\Rightarrow &\mathbb{E}\left[\left( X - \mathbb{E}[X]\right)\left( Y - \mathbb{E}[Y]\right)\right]^2 \leq \mathbb{E}\left[\left( X - \mathbb{E}[X]\right)^2\right]\mathbb{E}\left[\left( Y - \mathbb{E}[Y]\right)^2\right] \\
\Rightarrow &\mathbb{COV}[X, Y]^2 \leq \mathbb{VAR}[X]  \mathbb{VAR}[Y]\\
\end{split}
$$


Tags: mathematics time_series WS2425
<!--ID: 1734890698110-->
END


START
Basic
how to estimate the parameters of a [[autoregresive (AR) model]]?

Back: 
### parameter estimation
- first estimate the [[autocorrelation (ACF)]] $\hat\rho(h)$ 

$$
\begin{split}
\hat X_n &= \sum_{i \in [n]} X_i \\
\hat\gamma_n(h) &= \frac{1}{n} \sum_{t=1}^{n-|h|} \left(X_t- X_n\right)\left(X_{t+h}- X_n\right) \\
\hat\rho_n(h) &= \frac{\hat\gamma_n(h)}{\hat\gamma_n(0)}  \\
\end{split}
$$


- use the [[yule walker equation]] to calculate the parameter vector

$$
\begin{split}
RA = r \Leftrightarrow A = R^{-1}r
\end{split}
$$

$$
\begin{split}
A &= \left(\begin{matrix}
a_1 & ... & a_p
\end{matrix}\right) \\
r &= (\rho(r))_{r \in [n]} = \left(\begin{matrix}
\rho(1) & ... & \rho(p)
\end{matrix}\right) \\
R &= (\rho(r-s))_{r, s \in [n]} \left(\begin{matrix}
1 & \rho(1) & ... & \rho(p-1) \\
\rho(1) & 1 & ... & \rho(p-2) \\
 &  & ... & \ \\
 \rho(p-1) & \rho(p-2) & ... & 1 \\
\end{matrix}\right)
\end{split}
$$



_____________________

### mean estimators for stationary time series
- given an observation $X_1, ..., X_n$ from a [[stationary process|stationary]] [[time series]]
- the mean $\mu = \mathbb{E}[X_i]$ can be estimated with the following [[statistical estimator]]

$$
\hat X_n = \sum_{i \in [n]} X_i
$$
- $X_n$ is an [[estimator consitency#$ sqrt{n}$ consitency|root n consistent]] [[statistical estimator]] for 
- the [[statistical estimator]] converges in distribution to a [[normal distribution]]

$$
\sqrt{n} (X_n - \mu) \xrightarrow{\mathcal{D}} \mathcal{N}\left(0, \sum_{h = 1}^\infty \rho(h) \right)
$$

### autocorrelation estimators for stationary time series
- given an observation $X_1, ..., X_n$ from a [[stationary process|stationary]] [[time series]]
- the [[autocorrelation (ACF)]] $\rho(h)$ can be estimated with the following [[statistical estimator]] (for $h \leq n$)

$$
\hat\rho_n(h) = \frac{1}{n} \sum_{t=1}^{n-|h|} \left(X_t- X_n\right)\left(X_{t+h}- X_n\right)
$$

- under suitable assumptions $\hat\rho_n(h)$ is [[estimator consitency#$ sqrt{n}$ consitency|root n consistent]] and [[normal distribution]]


### yule walker equation
- for [[statistical estimator|estimating]] the parameters $a_1, ..., a_p$ of an [[autoregresive (AR) model]]

- fo $h > 0$
$$
\begin{split}
\rho_{X}(h) 
&= a_1 \rho_{X}(h-1) + a_2 \rho_{X}(h-2) + ... + a_p \rho_{X}(h-p) \\
&= \sum_{i=1}^p a_i \rho_{X}(h-i)  \\
\end{split}
$$

- fo $h = 0$
$$
\begin{split}
\rho_{X}(0) - \sigma^2_e
&= \sum_{i=1}^p a_i \rho_{X}(0-i)  \\
\end{split}
$$
- this can be writting as the following [[linear map|linear]] [[matrix]] equation which can be solved for the parameter vector $A$

$$
\begin{split}
RA = r \Leftrightarrow A = R^{-1}r
\end{split}
$$

$$
\begin{split}
A &= \left(\begin{matrix}
a_1 & ... & a_p
\end{matrix}\right) \\
r &= (\rho(r))_{r \in [n]} = \left(\begin{matrix}
\rho(1) & ... & \rho(p)
\end{matrix}\right) \\
R &= (\rho(r-s))_{r, s \in [n]} \left(\begin{matrix}
1 & \rho(1) & ... & \rho(p-1) \\
\rho(1) & 1 & ... & \rho(p-2) \\
 &  & ... & \ \\
 \rho(p-1) & \rho(p-2) & ... & 1 \\
\end{matrix}\right)
\end{split}
$$


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
- i.i.d. values
- zero mean $\mathbb{E}[e_t] = 0$  
- constant and finite [[variance]] $\mathbb{VAR}[e_t] = \mathbb{E}[e_t^2]= \sigma^2 \in (0, \infty)$  
- [[correlation|uncorralated]] values $t \neq s \Rightarrow  \mathbb{COV}[e_t, e_s] = \mathbb{COR}[e_t, e_s] = 0$

#### gaussian white noise
- [[white noise]] with [[normal distribution|normal distributed]] values $e_t \sim \mathcal{N}(0, \sigma^2)$


### correlation
- The [[correlation]] is a measure for the linear dependency of [[random variable|random variables]] 
- in contrast to the [[covariance]] the [[correlation]] is not depending on the absolut size of the [[random variable|random variables]]
$$
\rho[X,Y] =\frac{\mathbb{COVAR}[X,Y]}{\sqrt{\mathbb{VAR}[X]\mathbb{VAR}[Y]}}
$$


Tags: mathematics time_series WS2425
<!--ID: 1734893934057-->
END