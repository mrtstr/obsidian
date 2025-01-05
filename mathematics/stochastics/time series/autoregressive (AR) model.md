### autoregressive (AR) model
- The [[autoregressive (AR) model]] of order $p$ $AP(p)$ assumes the captures the linear relationship of the current value to the past p $p$ values
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
- first estimate the [[autocovariance]] $\hat\gamma(h)$ using a [[estimators for stationary time series#autocorrelation estimators for stationary time series|autocorrelation estimators for stationary time series]]

$$
\begin{split}
\hat X_n &= \sum_{i \in [n]} X_i \\
\hat\gamma_n(h) &= \frac{1}{n} \sum_{t=1}^{n-|h|} \left(X_t- X_n\right)\left(X_{t+h}- X_n\right) \\
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
r &= (\gamma(r))_{r \in [n]} = \left(\begin{matrix}
\gamma(1) & ... & \rho(p)
\end{matrix}\right) \\
R &= (\gamma(r-s))_{r, s \in [n]} \left(\begin{matrix}
1 & \gamma(1) & ... & \gamma(p-1) \\
\gamma(1) & 1 & ... & \gamma(p-2) \\
 &  & ... & \ \\
 \gamma(p-1) & \gamma(p-2) & ... & 1 \\
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
\gamma_{X}(h) &= a_1 \gamma_{X}(h-1)  \\
\gamma_{X}(1) &= a_1 \gamma_{X}(0)   \\
\gamma_{X}(2) &= a_1 \gamma_{X}(1) = a_1^2 \gamma_{X}(0) \\
\gamma_{X}(h) &= a_1 \gamma_{X}(h-1) = a_1^h \gamma_{X}(0) \\
\rho_{X}(h) &=  \frac{\gamma_{X}(h)}{\gamma_{X}(0)} =  a_1^h  \\
\end{split}
$$

#### parameter boundary's

$$
\begin{split}
a_1 
&=  \frac{\gamma_{X}(1)}{\gamma_{X}(0)}   \\
&=  \rho_{X}(1) \in [-1,1]  \\
\end{split}
$$

### the AR(1) model has no stationary solution
- given the following $AR(1)$ model with $a_1>0$ and $e_t \sim \mathcal{N}(0, \sigma^2)$
- there is not [[stationary process|stationary]] solution for $X_t$

$$
X_t = a_1 X_{t-1}  + e_t
$$

#### proof
- by recursively insertion the equation into itself we get the following
- by assuming [[stationary process|stationarity]] and calculating the [[variance]] we see that the variance is time-dependent and thus $X_t$ is not stationary

$$
\begin{split}
X_t 
&= a_1 X_{t-1}  + e_t \\
&= a_1^t X_{0}  + \sum_{i=0}^{t-1} a_1^i e_{t-i} \\
\mathbb{VAR}\left[X_t\right] 
&= \mathbb{E}\left[\left(a_1^t X_{0}  + \sum_{i=0}^{t-1} a_1^i e_{t-i}\right)^2\right] \\
&= a_1^{2t} \mathbb{E}\left[ X_{0}^2  \right] + \sum_{i=0}^{t-1}\sum_{j=0}^{t-1} a_1^i a_1^j\mathbb{E}\left[   e_{t-i}e_{t-j}\right]\\
&= a_1^{2t} \mathbb{E}\left[ X_{0}^2  \right] + \sigma^2 \sum_{i=0}^{t-1} a_1^{2i}  \\
\end{split}
$$

# ----------------------------
![[yule walker equation#yule walker equation]]

![[stationary process#weakly stationary process]]

![[white noise#white noise]]


# Anki

START
Basic
#### [[autoregressive (AR) model]]
- proof that the $AR(1)$ model does not have a stationary solution

Back: 

### the AR(1) model has no stationary solution
- given the following $AR(1)$ model with $a_1>0$ and $e_t \sim \mathcal{N}(0, \sigma^2)$
- there is not [[stationary process|stationary]] solution for $X_t$

$$
X_t = a_1 X_{t-1}  + e_t
$$

#### proof
- by recursively insertion the equation into itself we get the following
- by assuming [[stationary process|stationarity]] and calculating the [[variance]] we see that the variance is time-dependent and thus $X_t$ is not stationary

$$
\begin{split}
X_t 
&= a_1 X_{t-1}  + e_t \\
&= a_1^t X_{0}  + \sum_{i=0}^{t-1} a_1^i e_{t-i} \\
\mathbb{VAR}\left[X_t\right] 
&= \mathbb{E}\left[\left(a_1^t X_{0}  + \sum_{i=0}^{t-1} a_1^i e_{t-i}\right)^2\right] \\
&= a_1^{2t} \mathbb{E}\left[ X_{0}^2  \right] + \sum_{i=0}^{t-1}\sum_{j=0}^{t-1} a_1^i a_1^j\mathbb{E}\left[   e_{t-i}e_{t-j}\right]\\
&= a_1^{2t} \mathbb{E}\left[ X_{0}^2  \right] + \sigma^2 \sum_{i=0}^{t-1} a_1^{2i}  \\
\end{split}
$$



_______
### autoregressive (AR) model
- The [[autoregressive (AR) model]] of order $p$ $AP(p)$ assumes the captures the linear releationship of the current value to the past p $p$ values
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
<!--ID: 1736090396274-->
END


START
Basic
#### [[autoregressive (AR) model]]
- definition
- [[expectation]] and [[variance]] of $AR(1)$

Back: 
### autoregressive (AR) model
- The [[autoregressive (AR) model]] of order $p$ $AP(p)$ assumes the captures the linear releationship of the current value to the past p $p$ values
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
- zero mean $\mathbb{E}[e_t] = 0$  
- [[correlation|uncorralated]] values $t \neq s \Rightarrow  \mathbb{COV}[e_t, e_s] = \mathbb{COR}[e_t, e_s] = 0$

#### gaussian white noise
- [[white noise]] with [[normal distribution|normal distributed]] values $e_t \sim \mathcal{N}(0, \sigma^2)$



Tags: mathematics time_series WS2425
<!--ID: 1705250198064-->
END







START
Basic
#### [[autoregressive (AR) model]]
- definition
- [[autocorrelation (ACF)]] and [[autocovariance]]  of $AR(1)$ (np proof)

Back: 
### autoregressive (AR) model
- The [[autoregressive (AR) model]] of order $p$ $AP(p)$ assumes the captures the linear releationship of the current value to the past p $p$ values
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
- zero mean $\mathbb{E}[e_t] = 0$  
- [[correlation|uncorralated]] values $t \neq s \Rightarrow  \mathbb{COV}[e_t, e_s] = \mathbb{COR}[e_t, e_s] = 0$

#### gaussian white noise
- [[white noise]] with [[normal distribution|normal distributed]] values $e_t \sim \mathcal{N}(0, \sigma^2)$


Tags: mathematics time_series WS2425
<!--ID: 1705250198077-->
END



START
Basic
#### [[autoregressive (AR) model]]
- [[autocorrelation (ACF)]] of $AR(1)$ model with proof using the [[yule walker equation]]

Back: 
### autoregressive (AR) model
- The [[autoregressive (AR) model]] of order $p$ $AP(p)$ assumes the captures the linear releationship of the current value to the past p $p$ values
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
\gamma_{X}(h) &= a_1 \gamma_{X}(h-1)  \\
\gamma_{X}(1) &= a_1 \gamma_{X}(0)   \\
\gamma_{X}(2) &= a_1 \gamma_{X}(1) = a_1^2 \gamma_{X}(0) \\
\gamma_{X}(h) &= a_1 \gamma_{X}(h-1) = a_1^h \gamma_{X}(0) \\
\rho_{X}(h) &=  \frac{\gamma_{X}(h)}{\gamma_{X}(0)} = a_1^h  \\
\end{split}
$$


_____________________

### yule walker equation
- for [[statistical estimator|estimating]] the parameters $a_1, ..., a_p$ of an [[autoregressive (AR) model]]

- for $h > 0$
$$
\begin{split}
\gamma(h) 
&= a_1 \gamma(h-1) + a_2 \gamma{X}(h-2) + ... + a_p \gamma(h-p) \\
&= \sum_{i=1}^p a_i \gamma(h-i)  \\
\end{split}
$$

- for $h = 0$
$$
\begin{split}
\gamma(0) - \sigma^2_e
&= \sum_{i=1}^p a_i \gamma(0-i)  \\
\end{split}
$$



_______


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
<!--ID: 1734865948126-->
END

START
Basic
#### [[autoregressive (AR) model]] of order 1 $AR(1)$
- definition
- [[expectation]] without proof
- [[variance]] without proof
- [[autocovariance]] without proof
- [[autocorrelation (ACF)]] without proof

Back: 
### autoregressive (AR) model
- The [[autoregressive (AR) model]] of order $p$ $AP(p)$ assumes the captures the linear relationship of the current value to the past p $p$ values
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
- zero mean $\mathbb{E}[e_t] = 0$  
- [[correlation|uncorralated]] values $t \neq s \Rightarrow  \mathbb{COV}[e_t, e_s] = \mathbb{COR}[e_t, e_s] = 0$
#### gaussian white noise
- [[white noise]] with [[normal distribution|normal distributed]] values $e_t \sim \mathcal{N}(0, \sigma^2)$

Tags: mathematics time_series WS2425
<!--ID: 1705250198080-->
END


START
Basic
given an [[autoregressive (AR) model]] of order 1 $AR(1)$
- which values can the parameter $a_1$ take (with proof)

Back: 

## autoregresive model of order 1 $AR(1)$

$$
X_t = a_1 X_{t-1} + \beta + e_t
$$



#### parameter boundarys

$$
\begin{split}
a_1 
&=  \frac{\gamma_{X}(1)}{\gamma_{X}(0)}   \\
&=  \rho_{X}(1) \in [-1,1]  \\
\end{split}
$$

_____________________

### yule walker equation
- for [[statistical estimator|estimating]] the parameters $a_1, ..., a_p$ of an [[autoregressive (AR) model]]

- for $h > 0$
$$
\begin{split}
\gamma(h) 
&= a_1 \gamma(h-1) + a_2 \gamma{X}(h-2) + ... + a_p \gamma(h-p) \\
&= \sum_{i=1}^p a_i \gamma(h-i)  \\
\end{split}
$$

- for $h = 0$
$$
\begin{split}
\gamma(0) - \sigma^2_e
&= \sum_{i=1}^p a_i \gamma(0-i)  \\
\end{split}
$$


### autoregressive (AR) model
- The [[autoregressive (AR) model]] of order $p$ $AP(p)$ assumes the captures the linear releationship of the current value to the past p $p$ values
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
how to estimate the parameters of a [[autoregressive (AR) model]]?

Back: 
### parameter estimation
- first estimate the [[autocovariance]] $\hat\gamma(h)$ using a [[estimators for stationary time series#autocorrelation estimators for stationary time series|autocorrelation estimators for stationary time series]]

$$
\begin{split}
\hat X_n &= \sum_{i \in [n]} X_i \\
\hat\gamma_n(h) &= \frac{1}{n} \sum_{t=1}^{n-|h|} \left(X_t- X_n\right)\left(X_{t+h}- X_n\right) \\
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
r &= (\gamma(r))_{r \in [n]} = \left(\begin{matrix}
\gamma(1) & ... & \rho(p)
\end{matrix}\right) \\
R &= (\gamma(r-s))_{r, s \in [n]} \left(\begin{matrix}
1 & \gamma(1) & ... & \gamma(p-1) \\
\gamma(1) & 1 & ... & \gamma(p-2) \\
 &  & ... & \ \\
 \gamma(p-1) & \gamma(p-2) & ... & 1 \\
\end{matrix}\right)
\end{split}
$$


- use the [[yule walker equation]] to calculate the parameter vector


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



### yule walker equation
- for [[statistical estimator|estimating]] the parameters $a_1, ..., a_p$ of an [[autoregressive (AR) model]]

- for $h > 0$
$$
\begin{split}
\gamma(h) 
&= a_1 \gamma(h-1) + a_2 \gamma{X}(h-2) + ... + a_p \gamma(h-p) \\
&= \sum_{i=1}^p a_i \gamma(h-i)  \\
\end{split}
$$

- for $h = 0$
$$
\begin{split}
\gamma(0) - \sigma^2_e
&= \sum_{i=1}^p a_i \gamma(0-i)  \\
\end{split}
$$

- this can be written as the following [[linear map|linear]] [[matrix]] equation which can be solved for the parameter vector $A$

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
r &= (\gamma(r))_{r \in [n]} = \left(\begin{matrix}
\gamma(1) & ... & \rho(p)
\end{matrix}\right) \\
R &= (\gamma(r-s))_{r, s \in [n]} \left(\begin{matrix}
1 & \gamma(1) & ... & \gamma(p-1) \\
\gamma(1) & 1 & ... & \gamma(p-2) \\
 &  & ... & \ \\
 \gamma(p-1) & \gamma(p-2) & ... & 1 \\
\end{matrix}\right)
\end{split}
$$


### autoregressive (AR) model
- The [[autoregressive (AR) model]] of order $p$ $AP(p)$ assumes the captures the linear releationship of the current value to the past p $p$ values
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


### correlation
- The [[correlation]] is a measure for the linear dependency of [[random variable|random variables]] 
- in contrast to the [[covariance]] the [[correlation]] is not depending on the absolut size of the [[random variable|random variables]]
$$
\rho[X,Y] =\frac{\mathbb{COVAR}[X,Y]}{\sqrt{\mathbb{VAR}[X]\mathbb{VAR}[Y]}}
$$


Tags: mathematics time_series WS2425
<!--ID: 1734893934057-->
END