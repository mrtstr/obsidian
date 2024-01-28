## definition [[autoregresive model AR(q)]]
- The [[autoregresive model AR(q)]] of order $p$ $AP(p)$ assumes the captures the linear releationship of the current value to the past p $p$ values
- assumes an at least [[stationary process]]

![[stationary process#Definition (weakly) stationary process]]

- [[stochastic process]] $\{X_t\}$  
- white noise $\epsilon$ with $\mathbb{E}[\epsilon] =0$ and $\mathbb{VAR}[\epsilon] =const$ and [[stochastic independent]] of $X_t$
- constant $\beta$ (sometimes assumed to be zero)
$$
X_t = \sum_{i=1}^p \phi_i X_{t-i} + \beta + \epsilon
$$

# [[autoregresive model AR(q)]] of order 1 $AR(1)$
## Definition [[autoregresive model AR(q)|AR(1) model]]
$$
X_t = \phi_1 X_{t-1} + \beta + \epsilon_t
$$
## examples
For an AR(1) model:

-   when ϕ1=0

, yt-   is equivalent to white noise;
-   when ϕ1=1
and c=0, yt-   is equivalent to a random walk;
-   when ϕ1=1
and c≠0, yt-   is equivalent to a random walk with drift;
-   when ϕ1<0
, yt

-   tends to oscillate around the mean.

We normally restrict autoregressive models to stationary data, in which case some constraints on the values of the parameters are required.

-   For an AR(1) model: −1<ϕ1<1

-   .
-   For an AR(2) model: −1<ϕ2<1
, ϕ1+ϕ2<1, ϕ2−ϕ1<1

-   .

When p≥3

, the restrictions are much more complicated. R takes care of these restrictions when estimating a model.

As with autoregressive models, the variance of the error term εt will only change the scale of the series, not the patterns.

## properties


### [[expectation]]
$$
\begin{split}
\mathbb{E}\left[X_t\right] = \frac{\beta}{1-\phi_1}
\end{split}
$$
#### proof
$$
\begin{split}
\mathbb{E}\left[X_t\right] 
&= \mathbb{E}\left[\phi_1 X_{t-1} + \beta + \epsilon\right] \\
&= \phi_1 \mathbb{E}\left[ X_{t-1} \right] +  \mathbb{E}\left[\epsilon\right] + \beta \\
&= \phi_1 \mathbb{E}\left[ X_{t} \right] + \beta \\
&= \frac{\beta}{1-\phi_1} \\
\end{split}
$$

### [[variance]]
$$
\begin{split}
\mathbb{VAR}\left[X_t\right] = \frac{\mathbb{VAR}\left[\epsilon\right]}{1-\phi_1^2}
\end{split}
$$
#### proof
$$
\begin{split}
\mathbb{VAR}\left[X_t\right] 
&= \mathbb{VAR}\left[\phi_1 X_{t-1} + \beta + \epsilon\right] \\
&= \phi_1^2 \mathbb{VAR}\left[ X_{t-1}\right] + \mathbb{VAR}\left[\epsilon\right]\\
&= \phi_1^2 \mathbb{VAR}\left[ X_{t}\right] + \mathbb{VAR}\left[\epsilon\right]\\
&= \frac{\mathbb{VAR}\left[\epsilon\right]}{1-\phi_1^2}
\end{split}
$$
![[variance#Definition]]

### [[autocovariance]]
$$
\begin{split}
\mathbb{COV}\left[X_t X_{t-h}\right] 
&= \phi_1^h \mathbb{COV}\left[X_t X_{t-0}\right] \\ 
&= \phi_1^h \mathbb{VAR}\left[X_t\right] \\ 
\end{split}
$$
#### proof
$$
\begin{split}
\mathbb{COV}\left[X_t X_{t-1}\right] 
&= \mathbb{COV}\left[X_t X_{t+1}\right] \\
&= \mathbb{E}\left[X_t X_{t+1}\right] - \mathbb{E}\left[X_t X_{t+1}\right] \\
&= \mathbb{E}\left[X_t \left(\phi_1 X_{t} + \beta + \epsilon_t \right)\right] - \mathbb{E}\left[X_t \left(\phi_1 X_{t} + \beta + \epsilon_t \right)\right] \\
&= \phi_1 \mathbb{E}\left[X_t^2\right] + \mathbb{E}\left[X_t\right] \beta 
- \phi_1 \mathbb{E}\left[X_t\right]^2  -\mathbb{E}\left[X_t\right] \beta  \\

&= \phi_1 \mathbb{E}\left[X_t^2\right] + 
- \phi_1 \mathbb{E}\left[X_t\right]^2   \\

&= \phi_1 \mathbb{COV}\left[X_t X_{t-0}\right]    \\


\mathbb{COV}\left[X_t X_{t-2}\right] 
&= \mathbb{COV}\left[X_t X_{t+2}\right] \\
&= \mathbb{E}\left[X_t X_{t+2}\right] - \mathbb{E}\left[X_t X_{t+2}\right] \\
&= \mathbb{E}\left[X_t \left(\phi_1 X_{t+1} + \beta + \epsilon_{t+1} \right)\right] - \mathbb{E}\left[X_t \left(\phi_1 X_{t+1} + \beta + \epsilon_{t+1} \right)\right] \\
&= \phi_1 \mathbb{E}\left[X_t X_{t+1}\right] + \mathbb{E}\left[X_t\right] \beta 
- \phi_1 \mathbb{E}\left[X_t\right] \mathbb{E}\left[X_{t+1}\right] -\mathbb{E}\left[X_t\right] \beta  \\



&= \phi_1 \mathbb{COV}\left[X_t X_{t-1}\right]    \\
&= \phi_1^2 \mathbb{COV}\left[X_t X_{t-0}\right]    \\
&= \phi_1^2 \mathbb{VAR}\left[X_t\right]      \\
\Rightarrow \mathbb{E}\left[X_t X_{t-h}\right]
&= \phi_1^h \mathbb{COV}\left[X_t X_{t-0}\right]  \\
&= \phi_1^h \mathbb{VAR}\left[X_t\right]  
\end{split}
$$

### [[autocorrelation (ACF)]]


$$
\begin{split}
\rho(h) 
&= \phi_1^h
\end{split}
$$
#### proof
$$
\begin{split}
\rho(h) 
&= \frac{ \mathbb{COV}\left[X_{t}, X_{t - h}\right]}{\mathbb{VAR}\left[X_{t}\right]} \\
&= \frac{\phi_1^h \mathbb{VAR}\left[X_t\right]}{\mathbb{VAR}\left[X_{t}\right]} \\
&=  \phi_1^h \\
\end{split}
$$

![[autocorrelation (ACF)#definition autocorrelation (ACF) for stationary process]]

![[covariance#definition covariance]]


# Anki

START
Basic
#### [[autoregresive model AR(q)]] of order 1 $AR(1)$
- definition
- [[expectation]] with proof

Back: 
### definition
- The [[autoregresive model AR(q)]] of order $p$ $AP(p)$ assumes the captures the linear releationship of the current value to the past p $p$ values
- assumes an at least [[stationary process]]

- [[stochastic process]] $\{X_t\}$  
- white noise $\epsilon$ with $\mathbb{E}[\epsilon] =0$ and $\mathbb{VAR}[\epsilon] =const$ and [[stochastic independent]] of $X_t$
- constant $\beta$ (sometimes assumed to be zero)
$$
X_t = \sum_{i=1}^p \phi_i X_{t-i} + \beta + \epsilon
$$

### [[expectation]]
$$
\begin{split}
\mathbb{E}\left[X_t\right] = \frac{\beta}{1-\phi_1}
\end{split}
$$
#### proof
$$
\begin{split}
\mathbb{E}\left[X_t\right] 
&= \mathbb{E}\left[\phi_1 X_{t-1} + \beta + \epsilon\right] \\
&= \phi_1 \mathbb{E}\left[ X_{t-1} \right] +  \mathbb{E}\left[\epsilon\right] + \beta \\
&= \phi_1 \mathbb{E}\left[ X_{t} \right] + \beta \\
&= \frac{\beta}{1-\phi_1} \\
\end{split}
$$


#### Definition (weakly) [[stationary process]]
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- every starongly statanary process is also a (weakly) [[stationary process]]

Tags: mathematics time_series
<!--ID: 1705250198064-->
END


START
Basic
#### [[autoregresive model AR(q)]] of order 1 $AR(1)$
- definition
- [[variance]] with proof

Back: 
### definition
- The [[autoregresive model AR(q)]] of order $p$ $AP(p)$ assumes the captures the linear releationship of the current value to the past p $p$ values
- assumes an at least [[stationary process]]

- [[stochastic process]] $\{X_t\}$  
- white noise $\epsilon$ with $\mathbb{E}[\epsilon] =0$ and $\mathbb{VAR}[\epsilon] =const$ and [[stochastic independent]] of $X_t$
- constant $\beta$ (sometimes assumed to be zero)
$$
X_t = \sum_{i=1}^p \phi_i X_{t-i} + \beta + \epsilon
$$

### [[variance]]
$$
\begin{split}
\mathbb{VAR}\left[X_t\right] = \frac{\mathbb{VAR}\left[\epsilon\right]}{1-\phi_1^2}
\end{split}
$$
#### proof
$$
\begin{split}
\mathbb{VAR}\left[X_t\right] 
&= \mathbb{VAR}\left[\phi_1 X_{t-1} + \beta + \epsilon\right] \\
&= \phi_1^2 \mathbb{VAR}\left[ X_{t-1}\right] + \mathbb{VAR}\left[\epsilon\right]\\
&= \phi_1^2 \mathbb{VAR}\left[ X_{t}\right] + \mathbb{VAR}\left[\epsilon\right]\\
&= \frac{\mathbb{VAR}\left[\epsilon\right]}{1-\phi_1^2}
\end{split}
$$

#### Definition (weakly) [[stationary process]]
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- every starongly statanary process is also a (weakly) [[stationary process]]

Tags: mathematics time_series
<!--ID: 1705250198069-->
END

START
Basic
#### [[autoregresive model AR(q)]] of order 1 $AR(1)$
- definition
- [[autocovariance]] with proof

Back: 
### definition
- The [[autoregresive model AR(q)]] of order $p$ $AP(p)$ assumes the captures the linear releationship of the current value to the past p $p$ values
- assumes an at least [[stationary process]]

- [[stochastic process]] $\{X_t\}$  
- white noise $\epsilon$ with $\mathbb{E}[\epsilon] =0$ and $\mathbb{VAR}[\epsilon] =const$ and [[stochastic independent]] of $X_t$
- constant $\beta$ (sometimes assumed to be zero)
$$
X_t = \sum_{i=1}^p \phi_i X_{t-i} + \beta + \epsilon
$$

### [[autocovariance]]
$$
\begin{split}
\mathbb{COV}\left[X_t X_{t-h}\right] 
&= \phi_1^h \mathbb{COV}\left[X_t X_{t-0}\right] \\ 
&= \phi_1^h \mathbb{VAR}\left[X_t\right] \\ 
\end{split}
$$
#### proof
$$
\begin{split}
\mathbb{COV}\left[X_t X_{t-1}\right] 
&= \mathbb{COV}\left[X_t X_{t+1}\right] \\
&= \mathbb{E}\left[X_t X_{t+1}\right] - \mathbb{E}\left[X_t X_{t+1}\right] \\
&= \mathbb{E}\left[X_t \left(\phi_1 X_{t} + \beta + \epsilon_t \right)\right] - \mathbb{E}\left[X_t \left(\phi_1 X_{t} + \beta + \epsilon_t \right)\right] \\
&= \phi_1 \mathbb{E}\left[X_t^2\right] + \mathbb{E}\left[X_t\right] \beta 
- \phi_1 \mathbb{E}\left[X_t\right]^2  -\mathbb{E}\left[X_t\right] \beta  \\

&= \phi_1 \mathbb{E}\left[X_t^2\right] + 
- \phi_1 \mathbb{E}\left[X_t\right]^2   \\

&= \phi_1 \mathbb{COV}\left[X_t X_{t-0}\right]    \\


\mathbb{COV}\left[X_t X_{t-2}\right] 
&= \mathbb{COV}\left[X_t X_{t+2}\right] \\
&= \mathbb{E}\left[X_t X_{t+2}\right] - \mathbb{E}\left[X_t X_{t+2}\right] \\
&= \mathbb{E}\left[X_t \left(\phi_1 X_{t+1} + \beta + \epsilon_{t+1} \right)\right] - \mathbb{E}\left[X_t \left(\phi_1 X_{t+1} + \beta + \epsilon_{t+1} \right)\right] \\
&= \phi_1 \mathbb{E}\left[X_t X_{t+1}\right] + \mathbb{E}\left[X_t\right] \beta 
- \phi_1 \mathbb{E}\left[X_t\right] \mathbb{E}\left[X_{t+1}\right] -\mathbb{E}\left[X_t\right] \beta  \\



&= \phi_1 \mathbb{COV}\left[X_t X_{t-1}\right]    \\
&= \phi_1^2 \mathbb{COV}\left[X_t X_{t-0}\right]    \\
&= \phi_1^2 \mathbb{VAR}\left[X_t\right]      \\
\Rightarrow \mathbb{E}\left[X_t X_{t-h}\right]
&= \phi_1^h \mathbb{COV}\left[X_t X_{t-0}\right]  \\
&= \phi_1^h \mathbb{VAR}\left[X_t\right]  
\end{split}
$$



#### Definition (weakly) [[stationary process]]
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- every starongly statanary process is also a (weakly) [[stationary process]]

Tags: mathematics time_series
<!--ID: 1705250198074-->
END


START
Basic
#### [[autoregresive model AR(q)]] of order 1 $AR(1)$
- definition
- [[autocorrelation (ACF)]]  with proof

Back: 
### definition
- The [[autoregresive model AR(q)]] of order $p$ $AP(p)$ assumes the captures the linear releationship of the current value to the past p $p$ values
- assumes an at least [[stationary process]]

- [[stochastic process]] $\{X_t\}$  
- white noise $\epsilon$ with $\mathbb{E}[\epsilon] =0$ and $\mathbb{VAR}[\epsilon] =const$ and [[stochastic independent]] of $X_t$
- constant $\beta$ (sometimes assumed to be zero)
$$
X_t = \sum_{i=1}^p \phi_i X_{t-i} + \beta + \epsilon
$$

### [[autocovariance]]
$$
\begin{split}
\mathbb{COV}\left[X_t X_{t-h}\right] 
&= \phi_1^h \mathbb{COV}\left[X_t X_{t-0}\right] \\ 
&= \phi_1^h \mathbb{VAR}\left[X_t\right] \\ 
\end{split}
$$
#### proof
$$
\begin{split}
\mathbb{COV}\left[X_t X_{t-1}\right] 
&= \mathbb{COV}\left[X_t X_{t+1}\right] \\
&= \mathbb{E}\left[X_t X_{t+1}\right] - \mathbb{E}\left[X_t X_{t+1}\right] \\
&= \mathbb{E}\left[X_t \left(\phi_1 X_{t} + \beta + \epsilon_t \right)\right] - \mathbb{E}\left[X_t \left(\phi_1 X_{t} + \beta + \epsilon_t \right)\right] \\
&= \phi_1 \mathbb{E}\left[X_t^2\right] + \mathbb{E}\left[X_t\right] \beta 
- \phi_1 \mathbb{E}\left[X_t\right]^2  -\mathbb{E}\left[X_t\right] \beta  \\

&= \phi_1 \mathbb{E}\left[X_t^2\right] + 
- \phi_1 \mathbb{E}\left[X_t\right]^2   \\

&= \phi_1 \mathbb{COV}\left[X_t X_{t-0}\right]    \\


\mathbb{COV}\left[X_t X_{t-2}\right] 
&= \mathbb{COV}\left[X_t X_{t+2}\right] \\
&= \mathbb{E}\left[X_t X_{t+2}\right] - \mathbb{E}\left[X_t X_{t+2}\right] \\
&= \mathbb{E}\left[X_t \left(\phi_1 X_{t+1} + \beta + \epsilon_{t+1} \right)\right] - \mathbb{E}\left[X_t \left(\phi_1 X_{t+1} + \beta + \epsilon_{t+1} \right)\right] \\
&= \phi_1 \mathbb{E}\left[X_t X_{t+1}\right] + \mathbb{E}\left[X_t\right] \beta 
- \phi_1 \mathbb{E}\left[X_t\right] \mathbb{E}\left[X_{t+1}\right] -\mathbb{E}\left[X_t\right] \beta  \\



&= \phi_1 \mathbb{COV}\left[X_t X_{t-1}\right]    \\
&= \phi_1^2 \mathbb{COV}\left[X_t X_{t-0}\right]    \\
&= \phi_1^2 \mathbb{VAR}\left[X_t\right]      \\
\Rightarrow \mathbb{E}\left[X_t X_{t-h}\right]
&= \phi_1^h \mathbb{COV}\left[X_t X_{t-0}\right]  \\
&= \phi_1^h \mathbb{VAR}\left[X_t\right]  
\end{split}
$$

### [[autocorrelation (ACF)]]

$$
\begin{split}
\rho(h) 
&= \phi_1^h
\end{split}
$$
#### proof
$$
\begin{split}
\rho(h) 
&= \frac{ \mathbb{COV}\left[X_{t}, X_{t - h}\right]}{\mathbb{VAR}\left[X_{t}\right]} \\
&= \frac{\phi_1^h \mathbb{VAR}\left[X_t\right]}{\mathbb{VAR}\left[X_{t}\right]} \\
&=  \phi_1^h \\
\end{split}
$$



#### Definition (weakly) [[stationary process]]
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- every starongly statanary process is also a (weakly) [[stationary process]]

#### definition [[autocorrelation (ACF)]] for [[stationary process]]

$$
\begin{split}
\rho_{XX}(t_1, t_2) 
&= \rho_{XX}(t, t + h) \qquad \text{with } h = t_2-t_1\\
&= \rho_{XX}(h) \\
&= \frac{ \mathbb{COV}\left[X_{t}, X_{t - h}\right]}{\mathbb{VAR}\left[X_{t}\right]} 
\qquad \text{with arbitray } \tau, h
\end{split}
$$
#### definition [[covariance]]
The [[covariance]] is the [[variance]] of a [[joint distribution]]

$$
\mathbb{COV}\left[X,Y\right] = \mathbb{E}\left[(X-\mathbb{E}\left[X\right])(Y-\mathbb{E}\left[Y\right])\right]
= 
\mathbb{E}\left[XY\right]-\mathbb{E}\left[X\right]\mathbb{E}\left[Y\right]
$$

Tags: mathematics time_series
<!--ID: 1705250198077-->
END



START
Basic
#### [[autoregresive model AR(q)]] of order 1 $AR(1)$
- definition
- [[expectation]] without proof
- [[variance]] without proof
- [[autocovariance]] without proof
- [[autocorrelation (ACF)]] without proof

Back: 
### definition
- The [[autoregresive model AR(q)]] of order $p$ $AP(p)$ assumes the captures the linear releationship of the current value to the past p $p$ values
- assumes an at least [[stationary process]]

- [[stochastic process]] $\{X_t\}$  
- white noise $\epsilon$ with $\mathbb{E}[\epsilon] =0$ and $\mathbb{VAR}[\epsilon] =const$ and [[stochastic independent]] of $X_t$
- constant $\beta$ (sometimes assumed to be zero)
$$
X_t = \sum_{i=1}^p \phi_i X_{t-i} + \beta + \epsilon
$$

### [[expectation]]
$$
\begin{split}
\mathbb{E}\left[X_t\right] = \frac{\beta}{1-\phi_1}
\end{split}
$$
#### proof
$$
\begin{split}
\mathbb{E}\left[X_t\right] 
&= \mathbb{E}\left[\phi_1 X_{t-1} + \beta + \epsilon\right] \\
&= \phi_1 \mathbb{E}\left[ X_{t-1} \right] +  \mathbb{E}\left[\epsilon\right] + \beta \\
&= \phi_1 \mathbb{E}\left[ X_{t} \right] + \beta \\
&= \frac{\beta}{1-\phi_1} \\
\end{split}
$$

### [[variance]]
$$
\begin{split}
\mathbb{VAR}\left[X_t\right] = \frac{\mathbb{VAR}\left[\epsilon\right]}{1-\phi_1^2}
\end{split}
$$
#### proof
$$
\begin{split}
\mathbb{VAR}\left[X_t\right] 
&= \mathbb{VAR}\left[\phi_1 X_{t-1} + \beta + \epsilon\right] \\
&= \phi_1^2 \mathbb{VAR}\left[ X_{t-1}\right] + \mathbb{VAR}\left[\epsilon\right]\\
&= \phi_1^2 \mathbb{VAR}\left[ X_{t}\right] + \mathbb{VAR}\left[\epsilon\right]\\
&= \frac{\mathbb{VAR}\left[\epsilon\right]}{1-\phi_1^2}
\end{split}
$$

### [[autocovariance]]
$$
\begin{split}
\mathbb{COV}\left[X_t X_{t-h}\right] 
&= \phi_1^h \mathbb{COV}\left[X_t X_{t-0}\right] \\ 
&= \phi_1^h \mathbb{VAR}\left[X_t\right] \\ 
\end{split}
$$
#### proof
$$
\begin{split}
\mathbb{COV}\left[X_t X_{t-1}\right] 
&= \mathbb{COV}\left[X_t X_{t+1}\right] \\
&= \mathbb{E}\left[X_t X_{t+1}\right] - \mathbb{E}\left[X_t X_{t+1}\right] \\
&= \mathbb{E}\left[X_t \left(\phi_1 X_{t} + \beta + \epsilon_t \right)\right] - \mathbb{E}\left[X_t \left(\phi_1 X_{t} + \beta + \epsilon_t \right)\right] \\
&= \phi_1 \mathbb{E}\left[X_t^2\right] + \mathbb{E}\left[X_t\right] \beta 
- \phi_1 \mathbb{E}\left[X_t\right]^2  -\mathbb{E}\left[X_t\right] \beta  \\

&= \phi_1 \mathbb{E}\left[X_t^2\right] + 
- \phi_1 \mathbb{E}\left[X_t\right]^2   \\

&= \phi_1 \mathbb{COV}\left[X_t X_{t-0}\right]    \\


\mathbb{COV}\left[X_t X_{t-2}\right] 
&= \mathbb{COV}\left[X_t X_{t+2}\right] \\
&= \mathbb{E}\left[X_t X_{t+2}\right] - \mathbb{E}\left[X_t X_{t+2}\right] \\
&= \mathbb{E}\left[X_t \left(\phi_1 X_{t+1} + \beta + \epsilon_{t+1} \right)\right] - \mathbb{E}\left[X_t \left(\phi_1 X_{t+1} + \beta + \epsilon_{t+1} \right)\right] \\
&= \phi_1 \mathbb{E}\left[X_t X_{t+1}\right] + \mathbb{E}\left[X_t\right] \beta 
- \phi_1 \mathbb{E}\left[X_t\right] \mathbb{E}\left[X_{t+1}\right] -\mathbb{E}\left[X_t\right] \beta  \\



&= \phi_1 \mathbb{COV}\left[X_t X_{t-1}\right]    \\
&= \phi_1^2 \mathbb{COV}\left[X_t X_{t-0}\right]    \\
&= \phi_1^2 \mathbb{VAR}\left[X_t\right]      \\
\Rightarrow \mathbb{E}\left[X_t X_{t-h}\right]
&= \phi_1^h \mathbb{COV}\left[X_t X_{t-0}\right]  \\
&= \phi_1^h \mathbb{VAR}\left[X_t\right]  
\end{split}
$$

### [[autocorrelation (ACF)]]

$$
\begin{split}
\rho(h) 
&= \phi_1^h
\end{split}
$$
#### proof
$$
\begin{split}
\rho(h) 
&= \frac{ \mathbb{COV}\left[X_{t}, X_{t - h}\right]}{\mathbb{VAR}\left[X_{t}\right]} \\
&= \frac{\phi_1^h \mathbb{VAR}\left[X_t\right]}{\mathbb{VAR}\left[X_{t}\right]} \\
&=  \phi_1^h \\
\end{split}
$$

#### Definition (weakly) [[stationary process]]
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- every starongly statanary process is also a (weakly) [[stationary process]]

#### definition [[autocorrelation (ACF)]] for [[stationary process]]

$$
\begin{split}
\rho_{XX}(t_1, t_2) 
&= \rho_{XX}(t, t + h) \qquad \text{with } h = t_2-t_1\\
&= \rho_{XX}(h) \\
&= \frac{ \mathbb{COV}\left[X_{t}, X_{t - h}\right]}{\mathbb{VAR}\left[X_{t}\right]} 
\qquad \text{with arbitray } \tau, h
\end{split}
$$
#### definition [[covariance]]
The [[covariance]] is the [[variance]] of a [[joint distribution]]

$$
\mathbb{COV}\left[X,Y\right] = \mathbb{E}\left[(X-\mathbb{E}\left[X\right])(Y-\mathbb{E}\left[Y\right])\right]
= 
\mathbb{E}\left[XY\right]-\mathbb{E}\left[X\right]\mathbb{E}\left[Y\right]
$$

Tags: mathematics time_series
<!--ID: 1705250198080-->
END