## definition [[autoregresive model]]

the [[autoregresive model]] of order $p$ $AP(p)$ assumes the output valiable depends linearly on its preivious $p$ values
makes only sense for at least [[stationary process|weakly stationary]]

![[stationary process#Definition (weakly) stationary process]]

- [[stochastic process]] $\{X_t\}$  
- white noise $\epsilon$ with $\mathbb{E}[\epsilon] =0$ and [[stochastic independent]] of $X_t$
- constant $\beta$
$$
X_t = \sum_{i=1}^p \phi_i X_{t-i} + \beta + \epsilon
$$

## [[autoregresive model]] of order 1 $AR(1)$
$$
X_t = \phi_1 X_{t-1} + \beta + \epsilon
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
![[variance#Definition]]

### $\mathbb{E}\left[X_t X_{t-h}\right]$
$$
\begin{split}
\mathbb{E}\left[X_t X_{t-h}\right] 
&= \phi_1^h \mathbb{E}\left[X_t^2\right] 
\end{split}
$$
#### proof
$$
\begin{split}
\mathbb{E}\left[X_t X_{t-1}\right] 
&= \mathbb{E}\left[X_t X_{t+1}\right] \\
&= \mathbb{E}\left[\left(\phi_1 X_{t} + \epsilon\right) X_{t}\right]  \\
&= \phi_1 \mathbb{E}\left[X_{t}^2\right] + \mathbb{E}\left[\epsilon\right]\mathbb{E}\left[X_{t}\right]  \\
&= \phi_1 \mathbb{E}\left[X_{t}^2\right]  \\
\Rightarrow \mathbb{E}\left[X_t X_{t-h}\right]
&= \phi_1^h \mathbb{E}\left[X_{t}^2\right] 
\end{split}
$$

### [[autocorrelation (ACF)]]
- assuming $\mathbb{E}[X_t]=0$

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
&= \frac{ \mathbb{E}\left[X_t X_{t-h}\right] - \mathbb{E}\left[X_t\right]^2  }{\mathbb{E}\left[X_t^2\right]  -\mathbb{E}\left[X_t\right]^2  } \\
&= \frac{ \mathbb{E}\left[X_t X_{t-h}\right] }{\mathbb{E}\left[X_t^2\right]  } \\
&= \frac{  \phi_1^h \mathbb{E}\left[X_{t}^2\right]  }{\mathbb{E}\left[X_t^2\right]  } \\
&=  \phi_1^h \\
\end{split}
$$

![[autocorrelation (ACF)#definition autocorrelation (ACF) for stationary process]]

![[covariance#definition covariance]]


# Anki

START
Basic
#### [[autoregresive model]] of order 1 $AR(1)$
- definition
- [[expectation]] with proof

Back: 
### definition
- [[stationary process|weakly stationary]] [[stochastic process]] $\{X_t\}$  
- white noise $\epsilon$ with $\mathbb{E}[\epsilon] =0$ and [[stochastic independent]] of $X_t$
- constant $\beta$
$$
X_t = \phi_1 X_{t-1} + \beta + \epsilon
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
#### [[autoregresive model]] of order 1 $AR(1)$
- definition
- [[variance]] with proof

Back: 
### definition
- [[stationary process|weakly stationary]] [[stochastic process]] $\{X_t\}$  
- white noise $\epsilon$ with $\mathbb{E}[\epsilon] =0$ and [[stochastic independent]] of $X_t$
- constant $\beta$
$$
X_t = \phi_1 X_{t-1} + \beta + \epsilon
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
#### [[autoregresive model]] of order 1 $AR(1)$
- definition
- [[autocorrelation (ACF)]] with proof

Back: 
### definition
- [[stationary process|weakly stationary]] [[stochastic process]] $\{X_t\}$  
- white noise $\epsilon$ with $\mathbb{E}[\epsilon] =0$ and [[stochastic independent]] of $X_t$
- constant $\beta$
$$
X_t = \phi_1 X_{t-1} + \beta + \epsilon
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
#### [[autoregresive model]] of order 1 $AR(1)$
- definition
- [[autocorrelation (ACF)]] (assuming $\mathbb{E}[X_t]=0$) with proof

Back: 
### definition
- [[stationary process|weakly stationary]] [[stochastic process]] $\{X_t\}$  
- white noise $\epsilon$ with $\mathbb{E}[\epsilon] =0$ and [[stochastic independent]] of $X_t$
- constant $\beta$
$$
X_t = \phi_1 X_{t-1} + \beta + \epsilon
$$

### $\mathbb{E}\left[X_t X_{t-h}\right]$
$$
\begin{split}
\mathbb{E}\left[X_t X_{t-h}\right] 
&= \phi_1^h \mathbb{E}\left[X_t^2\right] 
\end{split}
$$
#### proof
$$
\begin{split}
\mathbb{E}\left[X_t X_{t-1}\right] 
&= \mathbb{E}\left[X_t X_{t+1}\right] \\
&= \mathbb{E}\left[\left(\phi_1 X_{t} + \epsilon\right) X_{t}\right]  \\
&= \phi_1 \mathbb{E}\left[X_{t}^2\right] + \mathbb{E}\left[\epsilon\right]\mathbb{E}\left[X_{t}\right]  \\
&= \phi_1 \mathbb{E}\left[X_{t}^2\right]  \\
\Rightarrow \mathbb{E}\left[X_t X_{t-h}\right]
&= \phi_1^h \mathbb{E}\left[X_{t}^2\right] 
\end{split}
$$

### [[autocorrelation (ACF)]]
- assuming $\mathbb{E}[X_t]=0$

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
&= \frac{ \mathbb{E}\left[X_t X_{t-h}\right] - \mathbb{E}\left[X_t\right]^2  }{\mathbb{E}\left[X_t^2\right]  -\mathbb{E}\left[X_t\right]^2  } \\
&= \frac{ \mathbb{E}\left[X_t X_{t-h}\right] }{\mathbb{E}\left[X_t^2\right]  } \\
&= \frac{  \phi_1^h \mathbb{E}\left[X_{t}^2\right]  }{\mathbb{E}\left[X_t^2\right]  } \\
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
#### [[autoregresive model]] of order 1 $AR(1)$
- definition
- [[expectation]] without proof
- [[variance]] without proof
- [[autocorrelation (ACF)]] without proof

Back: 
### definition
- [[stationary process|weakly stationary]] [[stochastic process]] $\{X_t\}$  
- white noise $\epsilon$ with $\mathbb{E}[\epsilon] =0$ and [[stochastic independent]] of $X_t$
- constant $\beta$
$$
X_t = \phi_1 X_{t-1} + \beta + \epsilon
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

### $\mathbb{E}\left[X_t X_{t-h}\right]$
$$
\begin{split}
\mathbb{E}\left[X_t X_{t-h}\right] 
&= \phi_1^h \mathbb{E}\left[X_t^2\right] 
\end{split}
$$
#### proof
$$
\begin{split}
\mathbb{E}\left[X_t X_{t-1}\right] 
&= \mathbb{E}\left[X_t X_{t+1}\right] \\
&= \mathbb{E}\left[\left(\phi_1 X_{t} + \epsilon\right) X_{t}\right]  \\
&= \phi_1 \mathbb{E}\left[X_{t}^2\right] + \mathbb{E}\left[\epsilon\right]\mathbb{E}\left[X_{t}\right]  \\
&= \phi_1 \mathbb{E}\left[X_{t}^2\right]  \\
\Rightarrow \mathbb{E}\left[X_t X_{t-h}\right]
&= \phi_1^h \mathbb{E}\left[X_{t}^2\right] 
\end{split}
$$

### [[autocorrelation (ACF)]]
- assuming $\mathbb{E}[X_t]=0$

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
&= \frac{ \mathbb{E}\left[X_t X_{t-h}\right] - \mathbb{E}\left[X_t\right]^2  }{\mathbb{E}\left[X_t^2\right]  -\mathbb{E}\left[X_t\right]^2  } \\
&= \frac{ \mathbb{E}\left[X_t X_{t-h}\right] }{\mathbb{E}\left[X_t^2\right]  } \\
&= \frac{  \phi_1^h \mathbb{E}\left[X_{t}^2\right]  }{\mathbb{E}\left[X_t^2\right]  } \\
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