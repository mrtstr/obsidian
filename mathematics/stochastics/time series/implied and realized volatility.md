### implied and realized volatility

#### implied volatility
- implied [[volatility]] is derived from option prices with the black scholes model (formula for options pricing based on [[geometric brownian motion (GBM)]]) based on current option prices 
- is forward-looking and is about market expectation of the [[volatility]] in the future

#### realized volatility
- realized [[volatility]] is the actual observed volatility in the past in a given period of time

##### assumed to be constant
- realized volatility for $n$ observations that represent e.g. $n$ days with where the [[volatility]] is assumed to be constant based on [[geometric brownian motion (GBM)]]

$$
\begin{split}
P_t 
&= P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right) \\
X_t 
&= \ln\left(P_t \right) - \ln\left(P_{t-1} \right) \\
&= \left(\mu - \frac{\sigma^2}{2}\right) + \sigma e_t  \\
&\sim \mathcal{N}\left(\mu - \frac{\sigma^2}{2} , \sigma^2  \right)
\end{split}
$$

$$
\begin{split}
\hat\sigma_{ML}^2 &= \frac{1}{n}  \sum_{i=1}^n \left(X_i - \bar X_n\right)^2 \\ 
\end{split}
$$
##### time dependent
- can be estimated with the following [[non-parametric volatility model]]

$$
\begin{split}
X_{t,n} = \frac{\alpha\left(\frac{t}{n}\right)}{n} + \frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} e_t
\end{split}
$$


- continues as a function $\hat\sigma^2: [0,1] \to [0, \infty)$ of $u$ (with drift zero or $n \to \infty$)

$$
\begin{split}
\hat\sigma^2(u)
&= \frac{1}{h}  \sum_{i=1}^{n} X_{t,n}^2 \cdot K\left(\frac{\frac{t}{n} - u}{h}\right) 
\end{split}
$$

- or for fixed time period with observations at time $0, t\frac{1}{n}, t\frac{2}{n}, t\frac{n}{n}$ (with drift zero or $n \to \infty$)

$$
\begin{split}
\hat\sigma^2
&= \sum_{t=1}^n X_{t,n}^2 \xrightarrow{n \to \infty} \int_0^1\sigma^2(u) du \\
\end{split}
$$

- or with drift $\neq 0$

$$
\begin{split}
\sigma^2 
&=  \sum_{t=1}^n X_{t,n}^2 - \frac{1}{n} \left(\frac{1}{T} \sum_{t=1}^{nT} X_{t,n} \right)^2 \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[X_{t,n}\right] 
&= \mathbb{E}\left[\frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t \right] \\
&= \frac{\alpha}{n}   \\
\Rightarrow \alpha &=  n \mathbb{E}\left[X_{t,n}\right] \\
\Rightarrow\hat\alpha 
&= \frac{n}{nT} \sum_{t=1}^{nT} X_{t,n} \\
&= \frac{1}{T} \sum_{t=1}^{nT} X_{t,n} \\
\end{split}
$$
$$
\begin{split}
\mathbb{E}\left[X_{t,n}^2\right] 
&= \mathbb{E}\left[ \left( \frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t \right)^2 \right] \\
&=   \frac{\alpha^2}{n^2} +  \frac{\sigma^2}{n}   \\
\sigma^2 
&=  n\mathbb{E}\left[X_{t,n}^2\right] -\frac{\alpha^2}{n} \\
&=  \sum_{t=1}^n X_{t,n}^2 - \frac{1}{n} \left(\frac{1}{T} \sum_{t=1}^{nT} X_{t,n} \right)^2 \\
\end{split}
$$

# ---------------

![[non-parametric volatility model#volatility estimator]]

![[non-parametric volatility model#time dependent volatility model]]

![[geometric brownian motion (GBM)#geometric brownian motion]]


![[GARCH model#GARCH model]]


![[volatility#volatility]]


START
Basic
definitions for
- implied volatility
- realized volatility
Back: 
### implied and realized volatility

#### implied volatility
- implied [[volatility]] is derived from option prices with the black scholes model (formula for options pricing based on [[geometric brownian motion (GBM)]]) based on current option prices 
- is forward-looking and is about market expectation of the [[volatility]] in the future

#### realized volatility
- realized [[volatility]] is the actual observed volatility in the past in a given period of time

##### assumed to be constant
- realized volatility for $n$ observations that represent e.g. $n$ days with where the [[volatility]] is assumed to be constant based on [[geometric brownian motion (GBM)]]

$$
\begin{split}
P_t 
&= P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right) \\
X_t 
&= \ln\left(P_t \right) - \ln\left(P_{t-1} \right) \\
&= \left(\mu - \frac{\sigma^2}{2}\right) + \sigma e_t  \\
&\sim \mathcal{N}\left(\mu - \frac{\sigma^2}{2} , \sigma^2  \right)
\end{split}
$$

$$
\begin{split}
\hat\sigma_{ML}^2 &= \frac{1}{n}  \sum_{i=1}^n \left(X_i - \bar X_n\right)^2 \\ 
\end{split}
$$
##### time dependent
- can be estimated with the following [[non-parametric volatility model]]

$$
\begin{split}
X_{t,n} = \frac{\alpha\left(\frac{t}{n}\right)}{n} + \frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} e_t
\end{split}
$$


- continues as a function $\hat\sigma^2: [0,1] \to [0, \infty)$ of $u$ (with drift zero or $n \to \infty$)

$$
\begin{split}
\hat\sigma^2(u)
&= \frac{1}{h}  \sum_{i=1}^{n} X_{t,n}^2 \cdot K\left(\frac{\frac{t}{n} - u}{h}\right) 
\end{split}
$$

- or for fixed time period with observations at time $0, t\frac{1}{n}, t\frac{2}{n}, t\frac{n}{n}$ (with drift zero or $n \to \infty$)

$$
\begin{split}
\hat\sigma^2
&= \sum_{t=1}^n X_{t,n}^2 \xrightarrow{n \to \infty} \int_0^1\sigma^2(u) du \\
\end{split}
$$

- or with drift $\neq 0$

$$
\begin{split}
\sigma^2 
&=  \sum_{t=1}^n X_{t,n}^2 - \frac{1}{n} \left(\frac{1}{T} \sum_{t=1}^{nT} X_{t,n} \right)^2 \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[X_{t,n}\right] 
&= \mathbb{E}\left[\frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t \right] \\
&= \frac{\alpha}{n}   \\
\Rightarrow \alpha &=  n \mathbb{E}\left[X_{t,n}\right] \\
\Rightarrow\hat\alpha 
&= \frac{n}{nT} \sum_{t=1}^{nT} X_{t,n} \\
&= \frac{1}{T} \sum_{t=1}^{nT} X_{t,n} \\
\end{split}
$$
$$
\begin{split}
\mathbb{E}\left[X_{t,n}^2\right] 
&= \mathbb{E}\left[ \left( \frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t \right)^2 \right] \\
&=   \frac{\alpha^2}{n^2} +  \frac{\sigma^2}{n}   \\
\sigma^2 
&=  n\mathbb{E}\left[X_{t,n}^2\right] -\frac{\alpha^2}{n} \\
&=  \sum_{t=1}^n X_{t,n}^2 - \frac{1}{n} \left(\frac{1}{T} \sum_{t=1}^{nT} X_{t,n} \right)^2 \\
\end{split}
$$

________________
### geometric brownian motion
- [[geometric brownian motion (GBM)]] is a [[stochastic process]] that can be used to describe the evolution of financial asset prices in a random but predictable manner
- $P_t$ is a [[geometric brownian motion (GBM)]] with the [[wiener process]] $W_t$ the [[drift]]  $\mu$ (return rate) and the [[volatility]] (of the return) $\sigma$

$$
P_t = P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right)
$$

### geometric brownian motion is log normal distributed
- [[geometric brownian motion (GBM)]] is [[log normal distribution| log normal distributed]]
- given $P_t$ with $P_0=1$ and the [[wiener process]] $W_t \sim \mathcal{N}(0, t)$
- first part is deterministic, and the second part is [[normal distribution|normal distributed]] $\sigma W_t \sim \mathcal{N}(0, \sigma^2 t)$
- thus the [[natural logarithm]] of $P_t$ is also [[normal distribution|normal distributed]]  and thus $P_t$ has a [[log normal distribution]]

$$
\begin{split}
\ln(P_t) = \left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t \sim \mathcal{N}\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t, \sigma^2 t \right)
\end{split}
$$

### log returns
- the log returns $X_t$ are defined as follows

$$
\begin{split}
X_t 
&= \ln\left(\frac{P_t}{P_{t-1}} \right) \\
&= \ln\left(P_t \right) - \ln\left(P_{t-1} \right) \\
\end{split}
$$
#### distribution of the log returns
- the log returns $X_t$ are i.i.d. [[normal distribution|normal distributed]]

$$
\begin{split}
X_t 
&= \ln\left(P_t \right) - \ln\left(P_{t-1} \right) \\
&= \left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t - \left(\mu - \frac{\sigma^2}{2}\right)\cdot (t-1) - \sigma W_{t-1} \\
&= \left(\mu - \frac{\sigma^2}{2}\right) + \sigma \left( W_{t-1} - W_{t-1} \right) \\
&= \left(\mu - \frac{\sigma^2}{2}\right) + \sigma e_t  \\
&\sim \mathcal{N}\left(\mu - \frac{\sigma^2}{2} , \sigma^2  \right)
\end{split}
$$



#### maximum likelihood estimator for the parameters
- since the log returns are [[normal distribution|normal distributed]] the [[maximum likelihood estimator]] can be calculated as follows
- from $\mathbb{E}[X] = \mu - \frac{\sigma^2}{2} \rightarrow \mu = \mathbb{E}[X]  - \frac{\sigma^2}{2}$

$$
\begin{split}
\bar X_n &= \frac{1}{n}  \sum_{i=1}^n X_i \\
\hat\sigma_{ML}^2 &= \frac{1}{n}  \sum_{i=1}^n \left(X_i - \bar X_n\right)^2 \\
\hat\mu_{ML}^2 &= \bar X_n +   \frac{\hat\sigma_{ML}^2}{2} \\
\end{split}
$$


## the base model
- given the [[geometric brownian motion (GBM)]] $P_t$ with $\alpha = \mu - \frac{\sigma^2}{2}$

$$
P_t = \exp\left( t \alpha + \sigma W_t\right)
$$

- assume we have $T$ time intervals (e.g. days) and we observe the continuous values $n$ times for each $t \in T$ 
- we would get the $nT+1$ observations $P_0, P_{\frac{1}{n}}, P_{\frac{2}{n}}, ..., P_{T\frac{n}{n}}$ 
- the equations would change as follows

$$
\begin{split}
P_{t, n} &= \exp\left( \frac{t}{n} \alpha + \sigma W_{t, n}\right) \\
W_{t, n}  &=  \sum_{i=1}^{t-1} \frac{1}{\sqrt{n}}  e_i \sim \mathcal{N}\left(0 , \frac{t}{n}  \right) \\
W_{t, n} - W_{t-1, n} &=  \frac{1}{\sqrt{n}} e_t \sim \mathcal{N}\left(0 , \frac{1}{n}\right) \\
X_{t,n} 
&= \ln\left(P_{\frac{t}{n}}\right) - \ln\left(P_{\frac{t-1}{n}}\right) \\
&= \frac{\alpha}{n} + \sigma \left(W_{t, n} - W_{t-1, n}\right) \\
&= \frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t \\
&\sim \mathcal{N}\left(\frac{\alpha}{n} , \frac{\sigma^2}{n}\right)
\end{split}
$$

### drift estimator

- when calculation the [[expectation]] and approximating it with the [[mean]] we get the following [[statistical estimator]] for $\alpha$
- the parameter $\alpha$ is still based on the revenue for the periods $t$ and not based on observations

$$
\begin{split}
\mathbb{E}\left[X_{t,n}\right] 
&= \mathbb{E}\left[\frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t \right] \\
&= \frac{\alpha}{n}   \\
\Rightarrow \alpha &=  n \mathbb{E}\left[X_{t,n}\right] \\
\Rightarrow\hat\alpha 
&= \frac{n}{nT} \sum_{t=1}^{nT} X_{t,n} \\
&= \frac{1}{T} \sum_{t=1}^{nT} X_{t,n} \\
\end{split}
$$

- $\hat\alpha$ only depends on the first price $P_0$ and the last price $P_T$

$$
\begin{split}
\hat\alpha 
&= \frac{1}{T} \sum_{t=1}^{nT} X_{t,n} \\
&= \frac{1}{T} \sum_{t=1}^{nT} \ln\left(P_{\frac{t}{n}}\right) - \ln\left(P_{\frac{t-1}{n}}\right) \\
&= \frac{1}{T} \left( \ln\left(P_T\right) - \ln\left(P_0\right) \right)\\
\end{split}
$$

- $\hat\alpha$ is a [[estimator consitency|consistent]] [[statistical estimator]] a fixed $n<\infty$ and $T \to \infty$, but cant be estimated consistently for a single day $T=1$ because the noise would dominate

$$
\begin{split}
\hat\alpha 
&= \frac{1}{T} \sum_{t=1}^{nT} X_{t,n} \\
&= \frac{1}{T} \sum_{t=1}^{nT} \frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t\\
&=  \frac{nT}{nT}  \alpha  + n \frac{\sigma}{\sqrt{n}} \frac{1}{T} \sum_{t=1}^{T}  e_t\\
&= \alpha  + \sigma\sqrt{n} \frac{1}{T} \sum_{t=1}^{T}  e_t\\
&= \alpha  \quad \text{for } T \to \infty\\
\end{split}
$$


### volatility estimator
- estimator for $\sigma_t^2$ for a single day $t$ can be calculated based on the [[expectation]] for $X_{t,n}^2$ which can be approximated by the mean

$$
\begin{split}
\mathbb{E}\left[X_{t,n}^2\right] 
&= \mathbb{E}\left[ \left( \frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t \right)^2 \right] \\
&= \mathbb{E}\left[  \frac{\alpha^2}{n^2} +  \frac{\sigma^2}{n} e_t^2 + 2 \frac{\alpha}{n} \frac{\sigma}{\sqrt{n}} e_t \right] \\
&=   \frac{\alpha^2}{n^2} +  \frac{\sigma^2}{n} \mathbb{E}\left[e_t^2 \right] + 2 \frac{\alpha}{n} \frac{\sigma}{\sqrt{n}} \mathbb{E}\left[e_t \right] \\
&=   \frac{\alpha^2}{n^2} +  \frac{\sigma^2}{n}   \\
\end{split}
$$
- the estimator is consistent for a sufficiently large number of observations $n$
$$
\begin{split}
n\mathbb{E}\left[X_{t,n}^2\right]
&= n \frac{\alpha^2}{n^2} + n \frac{\sigma^2}{n}  \\
&= \frac{\alpha^2}{n} + \sigma^2  \xrightarrow{n \to \infty}  \sigma^2 \\
\end{split}
$$

- the estimator $\hat\sigma^2$ is called the **realized [[volatility]]** 

$$
\begin{split}
\hat\sigma^2_t
&= \sum_{t=1}^n X_{t,n}^2 \\
\hat\sigma^2_T
&= \frac{1}{T} \sum_{t=1}^{nT} X_{t,n}^2
\end{split}
$$


## time dependent volatility model

- assume $\alpha=0$ and is a function $\sigma:[0,1] \to [0, \infty)$ and $t=1,2,...,n$
- note: we don't assume that $e_t$ is [[normal distribution|normal distributed]]

$$
\begin{split}
X_{n,t} = \frac{\alpha\left(\frac{t}{n}\right)}{n} + \frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} e_t = \frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} \cdot e_t
\end{split}
$$

- instead of taking the [[mean]] of $X_{t,n}^2$ we try to estimate the function $\sigma$ by applying [[smoothing]] to the [[time series]] $X_{t,n}^2$ around the 


#### kernel smoothing
- using [[kernel smoothing for time series]] to estimate a time depended on implied [[volatility]]
- note this approximation can be done because for sufficiently large $n$ the normalization term is a [[riemann sum]] which approximates the [[integral]] of the [[kernel]] which is normalized

$$
\begin{split}
\hat\sigma^2(u)
&= \frac{n}{nh}  \sum_{i=1}^{n} X_{t,n}^2 \cdot K\left(\frac{\frac{t}{n} - u}{h}\right) \\
&= \frac{1}{h}  \sum_{i=1}^{n} X_{t,n}^2 \cdot K\left(\frac{\frac{t}{n} - u}{h}\right)
\end{split}
$$
### convergence of the RV estimator

$$
\begin{split}
\hat\sigma^2
&= \sum_{t=1}^n X_{t,n}^2 \xrightarrow{n \to \infty} \int_0^1\sigma^2(u) du \\
\end{split}
$$

##### proof
- to show that the estimator converges in probability (see [[estimator convergence]]) we have to prove that its [[expectation]] converges and that its [[variance]] converges to zero
- the proof is completed with the [[riemann sum]]

$$
\begin{split}
\hat\sigma^2
&= \sum_{t=1}^n X_{t,n}^2  \\
&= \sum_{t=1}^n \left(\frac{\alpha\left(\frac{t}{n}\right)}{n} + \frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} e_t\right)^2  \\
&= \sum_{t=1}^n \frac{\alpha^2\left(\frac{t}{n}\right)}{n^2} + \frac{\sigma^2\left(\frac{t}{n}\right)}{n} e_t^2 + 2\frac{\alpha\left(\frac{t}{n}\right)}{n}  \frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} e_t  \\
&= \frac{1}{n} \sum_{t=1}^n \frac{\alpha^2\left(\frac{t}{n}\right)}{n} + \sigma^2\left(\frac{t}{n}\right) e_t^2 + 2  \frac{\alpha\left(\frac{t}{n}\right)\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} e_t  \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[\hat\sigma^2\right]
&\xrightarrow{n \to \infty} \sum_{t=1}^n \mathbb{E}\left[X_{t,n}^2\right]   \\
&\xrightarrow{n \to \infty} \frac{1}{n} \sum_{t=1}^n \frac{\alpha^2\left(\frac{t}{n}\right)}{n} + \sigma^2\left(\frac{t}{n}\right) \mathbb{E}\left[e_t^2\right] + 2  \frac{\alpha\left(\frac{t}{n}\right)\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} \mathbb{E}\left[e_t\right]   \\
&\xrightarrow{n \to \infty} \frac{1}{n} \sum_{t=1}^n \frac{\alpha^2\left(\frac{t}{n}\right)}{n} + \frac{1}{n} \sum_{t=1}^n \sigma^2\left(\frac{t}{n}\right)   \\
&\xrightarrow{n \to \infty}  \frac{1}{n} \sum_{t=1}^n \sigma^2\left(\frac{t}{n}\right)   \\
&\xrightarrow{n \to \infty}  \int_0^1 \sigma^2\left(u\right) du + \mathcal{O}\left(\frac{1}{n}\right)  \\
&\xrightarrow{n \to \infty}  \int_0^1 \sigma^2\left(u\right) du  \\
\end{split}
$$

- [[variance]] goes to zero (TODO add proof)


Tags: mathematics time_series WS2425
<!--ID: 1737718507733-->
END



START
Basic
realized volatility
- definition
- 3 ways how it can be estimated with assumptions
Back: 
#### realized volatility
- realized [[volatility]] is the actual observed volatility in the past in a given period of time

##### assumed to be constant
- realized volatility for $n$ observations that represent e.g. $n$ days with where the [[volatility]] is assumed to be constant based on [[geometric brownian motion (GBM)]]

$$
\begin{split}
P_t 
&= P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right) \\
X_t 
&= \ln\left(P_t \right) - \ln\left(P_{t-1} \right) \\
&= \left(\mu - \frac{\sigma^2}{2}\right) + \sigma e_t  \\
&\sim \mathcal{N}\left(\mu - \frac{\sigma^2}{2} , \sigma^2  \right)
\end{split}
$$

$$
\begin{split}
\hat\sigma_{ML}^2 &= \frac{1}{n}  \sum_{i=1}^n \left(X_i - \bar X_n\right)^2 \\ 
\end{split}
$$
##### time dependent
- can be estimated with the following [[non-parametric volatility model]]

$$
\begin{split}
X_{t,n} = \frac{\alpha\left(\frac{t}{n}\right)}{n} + \frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} e_t
\end{split}
$$


- continues as a function $\hat\sigma^2: [0,1] \to [0, \infty)$ of $u$ (with drift zero or $n \to \infty$)

$$
\begin{split}
\hat\sigma^2(u)
&= \frac{1}{h}  \sum_{i=1}^{n} X_{t,n}^2 \cdot K\left(\frac{\frac{t}{n} - u}{h}\right) 
\end{split}
$$

- or for fixed time period with observations at time $0, t\frac{1}{n}, t\frac{2}{n}, t\frac{n}{n}$ (with drift zero or $n \to \infty$)

$$
\begin{split}
\hat\sigma^2
&= \sum_{t=1}^n X_{t,n}^2 \xrightarrow{n \to \infty} \int_0^1\sigma^2(u) du \\
\end{split}
$$

- or with drift $\neq 0$

$$
\begin{split}
\sigma^2 
&=  \sum_{t=1}^n X_{t,n}^2 - \frac{1}{n} \left(\frac{1}{T} \sum_{t=1}^{nT} X_{t,n} \right)^2 \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[X_{t,n}\right] 
&= \mathbb{E}\left[\frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t \right] \\
&= \frac{\alpha}{n}   \\
\Rightarrow \alpha &=  n \mathbb{E}\left[X_{t,n}\right] \\
\Rightarrow\hat\alpha 
&= \frac{n}{nT} \sum_{t=1}^{nT} X_{t,n} \\
&= \frac{1}{T} \sum_{t=1}^{nT} X_{t,n} \\
\end{split}
$$
$$
\begin{split}
\mathbb{E}\left[X_{t,n}^2\right] 
&= \mathbb{E}\left[ \left( \frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t \right)^2 \right] \\
&=   \frac{\alpha^2}{n^2} +  \frac{\sigma^2}{n}   \\
\sigma^2 
&=  n\mathbb{E}\left[X_{t,n}^2\right] -\frac{\alpha^2}{n} \\
&=  \sum_{t=1}^n X_{t,n}^2 - \frac{1}{n} \left(\frac{1}{T} \sum_{t=1}^{nT} X_{t,n} \right)^2 \\
\end{split}
$$

________________
### geometric brownian motion
- [[geometric brownian motion (GBM)]] is a [[stochastic process]] that can be used to describe the evolution of financial asset prices in a random but predictable manner
- $P_t$ is a [[geometric brownian motion (GBM)]] with the [[wiener process]] $W_t$ the [[drift]]  $\mu$ (return rate) and the [[volatility]] (of the return) $\sigma$

$$
P_t = P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right)
$$

### geometric brownian motion is log normal distributed
- [[geometric brownian motion (GBM)]] is [[log normal distribution| log normal distributed]]
- given $P_t$ with $P_0=1$ and the [[wiener process]] $W_t \sim \mathcal{N}(0, t)$
- first part is deterministic, and the second part is [[normal distribution|normal distributed]] $\sigma W_t \sim \mathcal{N}(0, \sigma^2 t)$
- thus the [[natural logarithm]] of $P_t$ is also [[normal distribution|normal distributed]]  and thus $P_t$ has a [[log normal distribution]]

$$
\begin{split}
\ln(P_t) = \left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t \sim \mathcal{N}\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t, \sigma^2 t \right)
\end{split}
$$

### log returns
- the log returns $X_t$ are defined as follows

$$
\begin{split}
X_t 
&= \ln\left(\frac{P_t}{P_{t-1}} \right) \\
&= \ln\left(P_t \right) - \ln\left(P_{t-1} \right) \\
\end{split}
$$
#### distribution of the log returns
- the log returns $X_t$ are i.i.d. [[normal distribution|normal distributed]]

$$
\begin{split}
X_t 
&= \ln\left(P_t \right) - \ln\left(P_{t-1} \right) \\
&= \left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t - \left(\mu - \frac{\sigma^2}{2}\right)\cdot (t-1) - \sigma W_{t-1} \\
&= \left(\mu - \frac{\sigma^2}{2}\right) + \sigma \left( W_{t-1} - W_{t-1} \right) \\
&= \left(\mu - \frac{\sigma^2}{2}\right) + \sigma e_t  \\
&\sim \mathcal{N}\left(\mu - \frac{\sigma^2}{2} , \sigma^2  \right)
\end{split}
$$



#### maximum likelihood estimator for the parameters
- since the log returns are [[normal distribution|normal distributed]] the [[maximum likelihood estimator]] can be calculated as follows
- from $\mathbb{E}[X] = \mu - \frac{\sigma^2}{2} \rightarrow \mu = \mathbb{E}[X]  - \frac{\sigma^2}{2}$

$$
\begin{split}
\bar X_n &= \frac{1}{n}  \sum_{i=1}^n X_i \\
\hat\sigma_{ML}^2 &= \frac{1}{n}  \sum_{i=1}^n \left(X_i - \bar X_n\right)^2 \\
\hat\mu_{ML}^2 &= \bar X_n +   \frac{\hat\sigma_{ML}^2}{2} \\
\end{split}
$$


## the base model
- given the [[geometric brownian motion (GBM)]] $P_t$ with $\alpha = \mu - \frac{\sigma^2}{2}$

$$
P_t = \exp\left( t \alpha + \sigma W_t\right)
$$

- assume we have $T$ time intervals (e.g. days) and we observe the continuous values $n$ times for each $t \in T$ 
- we would get the $nT+1$ observations $P_0, P_{\frac{1}{n}}, P_{\frac{2}{n}}, ..., P_{T\frac{n}{n}}$ 
- the equations would change as follows

$$
\begin{split}
P_{t, n} &= \exp\left( \frac{t}{n} \alpha + \sigma W_{t, n}\right) \\
W_{t, n}  &=  \sum_{i=1}^{t-1} \frac{1}{\sqrt{n}}  e_i \sim \mathcal{N}\left(0 , \frac{t}{n}  \right) \\
W_{t, n} - W_{t-1, n} &=  \frac{1}{\sqrt{n}} e_t \sim \mathcal{N}\left(0 , \frac{1}{n}\right) \\
X_{t,n} 
&= \ln\left(P_{\frac{t}{n}}\right) - \ln\left(P_{\frac{t-1}{n}}\right) \\
&= \frac{\alpha}{n} + \sigma \left(W_{t, n} - W_{t-1, n}\right) \\
&= \frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t \\
&\sim \mathcal{N}\left(\frac{\alpha}{n} , \frac{\sigma^2}{n}\right)
\end{split}
$$

### drift estimator

- when calculation the [[expectation]] and approximating it with the [[mean]] we get the following [[statistical estimator]] for $\alpha$
- the parameter $\alpha$ is still based on the revenue for the periods $t$ and not based on observations

$$
\begin{split}
\mathbb{E}\left[X_{t,n}\right] 
&= \mathbb{E}\left[\frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t \right] \\
&= \frac{\alpha}{n}   \\
\Rightarrow \alpha &=  n \mathbb{E}\left[X_{t,n}\right] \\
\Rightarrow\hat\alpha 
&= \frac{n}{nT} \sum_{t=1}^{nT} X_{t,n} \\
&= \frac{1}{T} \sum_{t=1}^{nT} X_{t,n} \\
\end{split}
$$

- $\hat\alpha$ only depends on the first price $P_0$ and the last price $P_T$

$$
\begin{split}
\hat\alpha 
&= \frac{1}{T} \sum_{t=1}^{nT} X_{t,n} \\
&= \frac{1}{T} \sum_{t=1}^{nT} \ln\left(P_{\frac{t}{n}}\right) - \ln\left(P_{\frac{t-1}{n}}\right) \\
&= \frac{1}{T} \left( \ln\left(P_T\right) - \ln\left(P_0\right) \right)\\
\end{split}
$$

- $\hat\alpha$ is a [[estimator consitency|consistent]] [[statistical estimator]] a fixed $n<\infty$ and $T \to \infty$, but cant be estimated consistently for a single day $T=1$ because the noise would dominate

$$
\begin{split}
\hat\alpha 
&= \frac{1}{T} \sum_{t=1}^{nT} X_{t,n} \\
&= \frac{1}{T} \sum_{t=1}^{nT} \frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t\\
&=  \frac{nT}{nT}  \alpha  + n \frac{\sigma}{\sqrt{n}} \frac{1}{T} \sum_{t=1}^{T}  e_t\\
&= \alpha  + \sigma\sqrt{n} \frac{1}{T} \sum_{t=1}^{T}  e_t\\
&= \alpha  \quad \text{for } T \to \infty\\
\end{split}
$$


### volatility estimator
- estimator for $\sigma_t^2$ for a single day $t$ can be calculated based on the [[expectation]] for $X_{t,n}^2$ which can be approximated by the mean

$$
\begin{split}
\mathbb{E}\left[X_{t,n}^2\right] 
&= \mathbb{E}\left[ \left( \frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t \right)^2 \right] \\
&= \mathbb{E}\left[  \frac{\alpha^2}{n^2} +  \frac{\sigma^2}{n} e_t^2 + 2 \frac{\alpha}{n} \frac{\sigma}{\sqrt{n}} e_t \right] \\
&=   \frac{\alpha^2}{n^2} +  \frac{\sigma^2}{n} \mathbb{E}\left[e_t^2 \right] + 2 \frac{\alpha}{n} \frac{\sigma}{\sqrt{n}} \mathbb{E}\left[e_t \right] \\
&=   \frac{\alpha^2}{n^2} +  \frac{\sigma^2}{n}   \\
\end{split}
$$
- the estimator is consistent for a sufficiently large number of observations $n$
$$
\begin{split}
n\mathbb{E}\left[X_{t,n}^2\right]
&= n \frac{\alpha^2}{n^2} + n \frac{\sigma^2}{n}  \\
&= \frac{\alpha^2}{n} + \sigma^2  \xrightarrow{n \to \infty}  \sigma^2 \\
\end{split}
$$

- the estimator $\hat\sigma^2$ is called the **realized [[volatility]]** 

$$
\begin{split}
\hat\sigma^2_t
&= \sum_{t=1}^n X_{t,n}^2 \\
\hat\sigma^2_T
&= \frac{1}{T} \sum_{t=1}^{nT} X_{t,n}^2
\end{split}
$$


## time dependent volatility model

- assume $\alpha=0$ and is a function $\sigma:[0,1] \to [0, \infty)$ and $t=1,2,...,n$
- note: we don't assume that $e_t$ is [[normal distribution|normal distributed]]

$$
\begin{split}
X_{n,t} = \frac{\alpha\left(\frac{t}{n}\right)}{n} + \frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} e_t = \frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} \cdot e_t
\end{split}
$$

- instead of taking the [[mean]] of $X_{t,n}^2$ we try to estimate the function $\sigma$ by applying [[smoothing]] to the [[time series]] $X_{t,n}^2$ around the 


#### kernel smoothing
- using [[kernel smoothing for time series]] to estimate a time depended on implied [[volatility]]
- note this approximation can be done because for sufficiently large $n$ the normalization term is a [[riemann sum]] which approximates the [[integral]] of the [[kernel]] which is normalized

$$
\begin{split}
\hat\sigma^2(u)
&= \frac{n}{nh}  \sum_{i=1}^{n} X_{t,n}^2 \cdot K\left(\frac{\frac{t}{n} - u}{h}\right) \\
&= \frac{1}{h}  \sum_{i=1}^{n} X_{t,n}^2 \cdot K\left(\frac{\frac{t}{n} - u}{h}\right)
\end{split}
$$
### convergence of the RV estimator

$$
\begin{split}
\hat\sigma^2
&= \sum_{t=1}^n X_{t,n}^2 \xrightarrow{n \to \infty} \int_0^1\sigma^2(u) du \\
\end{split}
$$

##### proof
- to show that the estimator converges in probability (see [[estimator convergence]]) we have to prove that its [[expectation]] converges and that its [[variance]] converges to zero
- the proof is completed with the [[riemann sum]]

$$
\begin{split}
\hat\sigma^2
&= \sum_{t=1}^n X_{t,n}^2  \\
&= \sum_{t=1}^n \left(\frac{\alpha\left(\frac{t}{n}\right)}{n} + \frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} e_t\right)^2  \\
&= \sum_{t=1}^n \frac{\alpha^2\left(\frac{t}{n}\right)}{n^2} + \frac{\sigma^2\left(\frac{t}{n}\right)}{n} e_t^2 + 2\frac{\alpha\left(\frac{t}{n}\right)}{n}  \frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} e_t  \\
&= \frac{1}{n} \sum_{t=1}^n \frac{\alpha^2\left(\frac{t}{n}\right)}{n} + \sigma^2\left(\frac{t}{n}\right) e_t^2 + 2  \frac{\alpha\left(\frac{t}{n}\right)\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} e_t  \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[\hat\sigma^2\right]
&\xrightarrow{n \to \infty} \sum_{t=1}^n \mathbb{E}\left[X_{t,n}^2\right]   \\
&\xrightarrow{n \to \infty} \frac{1}{n} \sum_{t=1}^n \frac{\alpha^2\left(\frac{t}{n}\right)}{n} + \sigma^2\left(\frac{t}{n}\right) \mathbb{E}\left[e_t^2\right] + 2  \frac{\alpha\left(\frac{t}{n}\right)\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} \mathbb{E}\left[e_t\right]   \\
&\xrightarrow{n \to \infty} \frac{1}{n} \sum_{t=1}^n \frac{\alpha^2\left(\frac{t}{n}\right)}{n} + \frac{1}{n} \sum_{t=1}^n \sigma^2\left(\frac{t}{n}\right)   \\
&\xrightarrow{n \to \infty}  \frac{1}{n} \sum_{t=1}^n \sigma^2\left(\frac{t}{n}\right)   \\
&\xrightarrow{n \to \infty}  \int_0^1 \sigma^2\left(u\right) du + \mathcal{O}\left(\frac{1}{n}\right)  \\
&\xrightarrow{n \to \infty}  \int_0^1 \sigma^2\left(u\right) du  \\
\end{split}
$$

- [[variance]] goes to zero (TODO add proof)


Tags: mathematics time_series WS2425
<!--ID: 1737748473550-->
END



START
Basic
relationship
- [[GARCH model]]
- implied volatility
- realized volatility
Back: 
- the [[GARCH model]] is a parameterized [[time series]] model for the [[volatility]] that can be used for forecasting the [[volatility]] or describing the past [[volatility]] as a [[stochastic process]]
- implied volatility is the market expectation of the future volatility based on option prices and the black scholes model
- realized volatility can be estimated for the past often using [[geometric brownian motion (GBM)]] or a [[non-parametric volatility model]] based on GBR
### implied and realized volatility

#### implied volatility
- implied [[volatility]] is derived from option prices with the black scholes model (formula for options pricing based on [[geometric brownian motion (GBM)]]) based on current option prices 
- is forward-looking and is about market expectation of the [[volatility]] in the future

#### realized volatility
- realized [[volatility]] is the actual observed volatility in the past in a given period of time

##### assumed to be constant
- realized volatility for $n$ observations that represent e.g. $n$ days with where the [[volatility]] is assumed to be constant based on [[geometric brownian motion (GBM)]]

$$
\begin{split}
P_t 
&= P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right) \\
X_t 
&= \ln\left(P_t \right) - \ln\left(P_{t-1} \right) \\
&= \left(\mu - \frac{\sigma^2}{2}\right) + \sigma e_t  \\
&\sim \mathcal{N}\left(\mu - \frac{\sigma^2}{2} , \sigma^2  \right)
\end{split}
$$

$$
\begin{split}
\hat\sigma_{ML}^2 &= \frac{1}{n}  \sum_{i=1}^n \left(X_i - \bar X_n\right)^2 \\ 
\end{split}
$$
##### time dependent
- can be estimated with the following [[non-parametric volatility model]]

$$
\begin{split}
X_{t,n} = \frac{\alpha\left(\frac{t}{n}\right)}{n} + \frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} e_t
\end{split}
$$


- continues as a function $\hat\sigma^2: [0,1] \to [0, \infty)$ of $u$ (with drift zero or $n \to \infty$)

$$
\begin{split}
\hat\sigma^2(u)
&= \frac{1}{h}  \sum_{i=1}^{n} X_{t,n}^2 \cdot K\left(\frac{\frac{t}{n} - u}{h}\right) 
\end{split}
$$

- or for fixed time period with observations at time $0, t\frac{1}{n}, t\frac{2}{n}, t\frac{n}{n}$ (with drift zero or $n \to \infty$)

$$
\begin{split}
\hat\sigma^2
&= \sum_{t=1}^n X_{t,n}^2 \xrightarrow{n \to \infty} \int_0^1\sigma^2(u) du \\
\end{split}
$$

### GARCH model
- for modeling the conditional volatility as [[white noise]] based on historical returns, capturing the time-varying nature of volatility
- produces forecasts of future volatility conditioned on past data
- the concept behind the [[GARCH model]] is to use a [[autoregressive moving average (ARMA) model]] to model the [[volatility]] 
- $e_t \sim (0,1)$ i.i.d
- $a_i, b_j \geq 0$ and $a_p, b_q \neq 0$
$$
\begin{split}
 X_t&= \sigma_t \cdot e_t \\
\sigma^2_t &= a_0 + \sum_{i=1}^{p} a_i X_{t-i}^2 + \sum_{j=1}^{q} b_j \sigma^2_{t-j}
\end{split}
$$

- that means that $\sigma^2_t=\mathbb{VAR}[X_t|X_{t-1}, X_{t-2},...]$ is equal to the [[conditional variance]] of $X_t$ given the past values
	→ $\sigma^2_t$ is measurable given the past values
- the [[GARCH model]] $X_t$ is [[white noise]] but not independent white noise and the squared [[GARCH model]] $X^2_t$ is a [[autoregressive moving average (ARMA) model]] [[time series]]

________________
### geometric brownian motion
- [[geometric brownian motion (GBM)]] is a [[stochastic process]] that can be used to describe the evolution of financial asset prices in a random but predictable manner
- $P_t$ is a [[geometric brownian motion (GBM)]] with the [[wiener process]] $W_t$ the [[drift]]  $\mu$ (return rate) and the [[volatility]] (of the return) $\sigma$

$$
P_t = P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right)
$$

### geometric brownian motion is log normal distributed
- [[geometric brownian motion (GBM)]] is [[log normal distribution| log normal distributed]]
- given $P_t$ with $P_0=1$ and the [[wiener process]] $W_t \sim \mathcal{N}(0, t)$
- first part is deterministic, and the second part is [[normal distribution|normal distributed]] $\sigma W_t \sim \mathcal{N}(0, \sigma^2 t)$
- thus the [[natural logarithm]] of $P_t$ is also [[normal distribution|normal distributed]]  and thus $P_t$ has a [[log normal distribution]]

$$
\begin{split}
\ln(P_t) = \left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t \sim \mathcal{N}\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t, \sigma^2 t \right)
\end{split}
$$

### log returns
- the log returns $X_t$ are defined as follows

$$
\begin{split}
X_t 
&= \ln\left(\frac{P_t}{P_{t-1}} \right) \\
&= \ln\left(P_t \right) - \ln\left(P_{t-1} \right) \\
\end{split}
$$
#### distribution of the log returns
- the log returns $X_t$ are i.i.d. [[normal distribution|normal distributed]]

$$
\begin{split}
X_t 
&= \ln\left(P_t \right) - \ln\left(P_{t-1} \right) \\
&= \left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t - \left(\mu - \frac{\sigma^2}{2}\right)\cdot (t-1) - \sigma W_{t-1} \\
&= \left(\mu - \frac{\sigma^2}{2}\right) + \sigma \left( W_{t-1} - W_{t-1} \right) \\
&= \left(\mu - \frac{\sigma^2}{2}\right) + \sigma e_t  \\
&\sim \mathcal{N}\left(\mu - \frac{\sigma^2}{2} , \sigma^2  \right)
\end{split}
$$



#### maximum likelihood estimator for the parameters
- since the log returns are [[normal distribution|normal distributed]] the [[maximum likelihood estimator]] can be calculated as follows
- from $\mathbb{E}[X] = \mu - \frac{\sigma^2}{2} \rightarrow \mu = \mathbb{E}[X]  - \frac{\sigma^2}{2}$

$$
\begin{split}
\bar X_n &= \frac{1}{n}  \sum_{i=1}^n X_i \\
\hat\sigma_{ML}^2 &= \frac{1}{n}  \sum_{i=1}^n \left(X_i - \bar X_n\right)^2 \\
\hat\mu_{ML}^2 &= \bar X_n +   \frac{\hat\sigma_{ML}^2}{2} \\
\end{split}
$$


## the base model
- given the [[geometric brownian motion (GBM)]] $P_t$ with $\alpha = \mu - \frac{\sigma^2}{2}$

$$
P_t = \exp\left( t \alpha + \sigma W_t\right)
$$

- assume we have $T$ time intervals (e.g. days) and we observe the continuous values $n$ times for each $t \in T$ 
- we would get the $nT+1$ observations $P_0, P_{\frac{1}{n}}, P_{\frac{2}{n}}, ..., P_{T\frac{n}{n}}$ 
- the equations would change as follows

$$
\begin{split}
P_{t, n} &= \exp\left( \frac{t}{n} \alpha + \sigma W_{t, n}\right) \\
W_{t, n}  &=  \sum_{i=1}^{t-1} \frac{1}{\sqrt{n}}  e_i \sim \mathcal{N}\left(0 , \frac{t}{n}  \right) \\
W_{t, n} - W_{t-1, n} &=  \frac{1}{\sqrt{n}} e_t \sim \mathcal{N}\left(0 , \frac{1}{n}\right) \\
X_{t,n} 
&= \ln\left(P_{\frac{t}{n}}\right) - \ln\left(P_{\frac{t-1}{n}}\right) \\
&= \frac{\alpha}{n} + \sigma \left(W_{t, n} - W_{t-1, n}\right) \\
&= \frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t \\
&\sim \mathcal{N}\left(\frac{\alpha}{n} , \frac{\sigma^2}{n}\right)
\end{split}
$$

### drift estimator

- when calculation the [[expectation]] and approximating it with the [[mean]] we get the following [[statistical estimator]] for $\alpha$
- the parameter $\alpha$ is still based on the revenue for the periods $t$ and not based on observations

$$
\begin{split}
\mathbb{E}\left[X_{t,n}\right] 
&= \mathbb{E}\left[\frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t \right] \\
&= \frac{\alpha}{n}   \\
\Rightarrow \alpha &=  n \mathbb{E}\left[X_{t,n}\right] \\
\Rightarrow\hat\alpha 
&= \frac{n}{nT} \sum_{t=1}^{nT} X_{t,n} \\
&= \frac{1}{T} \sum_{t=1}^{nT} X_{t,n} \\
\end{split}
$$

- $\hat\alpha$ only depends on the first price $P_0$ and the last price $P_T$

$$
\begin{split}
\hat\alpha 
&= \frac{1}{T} \sum_{t=1}^{nT} X_{t,n} \\
&= \frac{1}{T} \sum_{t=1}^{nT} \ln\left(P_{\frac{t}{n}}\right) - \ln\left(P_{\frac{t-1}{n}}\right) \\
&= \frac{1}{T} \left( \ln\left(P_T\right) - \ln\left(P_0\right) \right)\\
\end{split}
$$

- $\hat\alpha$ is a [[estimator consitency|consistent]] [[statistical estimator]] a fixed $n<\infty$ and $T \to \infty$, but cant be estimated consistently for a single day $T=1$ because the noise would dominate

$$
\begin{split}
\hat\alpha 
&= \frac{1}{T} \sum_{t=1}^{nT} X_{t,n} \\
&= \frac{1}{T} \sum_{t=1}^{nT} \frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t\\
&=  \frac{nT}{nT}  \alpha  + n \frac{\sigma}{\sqrt{n}} \frac{1}{T} \sum_{t=1}^{T}  e_t\\
&= \alpha  + \sigma\sqrt{n} \frac{1}{T} \sum_{t=1}^{T}  e_t\\
&= \alpha  \quad \text{for } T \to \infty\\
\end{split}
$$


### volatility estimator
- estimator for $\sigma_t^2$ for a single day $t$ can be calculated based on the [[expectation]] for $X_{t,n}^2$ which can be approximated by the mean

$$
\begin{split}
\mathbb{E}\left[X_{t,n}^2\right] 
&= \mathbb{E}\left[ \left( \frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t \right)^2 \right] \\
&= \mathbb{E}\left[  \frac{\alpha^2}{n^2} +  \frac{\sigma^2}{n} e_t^2 + 2 \frac{\alpha}{n} \frac{\sigma}{\sqrt{n}} e_t \right] \\
&=   \frac{\alpha^2}{n^2} +  \frac{\sigma^2}{n} \mathbb{E}\left[e_t^2 \right] + 2 \frac{\alpha}{n} \frac{\sigma}{\sqrt{n}} \mathbb{E}\left[e_t \right] \\
&=   \frac{\alpha^2}{n^2} +  \frac{\sigma^2}{n}   \\
\end{split}
$$
- the estimator is consistent for a sufficiently large number of observations $n$
$$
\begin{split}
n\mathbb{E}\left[X_{t,n}^2\right]
&= n \frac{\alpha^2}{n^2} + n \frac{\sigma^2}{n}  \\
&= \frac{\alpha^2}{n} + \sigma^2  \xrightarrow{n \to \infty}  \sigma^2 \\
\end{split}
$$

- the estimator $\hat\sigma^2$ is called the **realized [[volatility]]** 

$$
\begin{split}
\hat\sigma^2_t
&= \sum_{t=1}^n X_{t,n}^2 \\
\hat\sigma^2_T
&= \frac{1}{T} \sum_{t=1}^{nT} X_{t,n}^2
\end{split}
$$


## time dependent volatility model

- assume $\alpha=0$ and is a function $\sigma:[0,1] \to [0, \infty)$ and $t=1,2,...,n$
- note: we don't assume that $e_t$ is [[normal distribution|normal distributed]]

$$
\begin{split}
X_{n,t} = \frac{\alpha\left(\frac{t}{n}\right)}{n} + \frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} e_t = \frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} \cdot e_t
\end{split}
$$

- instead of taking the [[mean]] of $X_{t,n}^2$ we try to estimate the function $\sigma$ by applying [[smoothing]] to the [[time series]] $X_{t,n}^2$ around the 


#### kernel smoothing
- using [[kernel smoothing for time series]] to estimate a time depended on implied [[volatility]]
- note this approximation can be done because for sufficiently large $n$ the normalization term is a [[riemann sum]] which approximates the [[integral]] of the [[kernel]] which is normalized

$$
\begin{split}
\hat\sigma^2(u)
&= \frac{n}{nh}  \sum_{i=1}^{n} X_{t,n}^2 \cdot K\left(\frac{\frac{t}{n} - u}{h}\right) \\
&= \frac{1}{h}  \sum_{i=1}^{n} X_{t,n}^2 \cdot K\left(\frac{\frac{t}{n} - u}{h}\right)
\end{split}
$$
### convergence of the RV estimator

$$
\begin{split}
\hat\sigma^2
&= \sum_{t=1}^n X_{t,n}^2 \xrightarrow{n \to \infty} \int_0^1\sigma^2(u) du \\
\end{split}
$$

##### proof
- to show that the estimator converges in probability (see [[estimator convergence]]) we have to prove that its [[expectation]] converges and that its [[variance]] converges to zero
- the proof is completed with the [[riemann sum]]

$$
\begin{split}
\hat\sigma^2
&= \sum_{t=1}^n X_{t,n}^2  \\
&= \sum_{t=1}^n \left(\frac{\alpha\left(\frac{t}{n}\right)}{n} + \frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} e_t\right)^2  \\
&= \sum_{t=1}^n \frac{\alpha^2\left(\frac{t}{n}\right)}{n^2} + \frac{\sigma^2\left(\frac{t}{n}\right)}{n} e_t^2 + 2\frac{\alpha\left(\frac{t}{n}\right)}{n}  \frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} e_t  \\
&= \frac{1}{n} \sum_{t=1}^n \frac{\alpha^2\left(\frac{t}{n}\right)}{n} + \sigma^2\left(\frac{t}{n}\right) e_t^2 + 2  \frac{\alpha\left(\frac{t}{n}\right)\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} e_t  \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[\hat\sigma^2\right]
&\xrightarrow{n \to \infty} \sum_{t=1}^n \mathbb{E}\left[X_{t,n}^2\right]   \\
&\xrightarrow{n \to \infty} \frac{1}{n} \sum_{t=1}^n \frac{\alpha^2\left(\frac{t}{n}\right)}{n} + \sigma^2\left(\frac{t}{n}\right) \mathbb{E}\left[e_t^2\right] + 2  \frac{\alpha\left(\frac{t}{n}\right)\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} \mathbb{E}\left[e_t\right]   \\
&\xrightarrow{n \to \infty} \frac{1}{n} \sum_{t=1}^n \frac{\alpha^2\left(\frac{t}{n}\right)}{n} + \frac{1}{n} \sum_{t=1}^n \sigma^2\left(\frac{t}{n}\right)   \\
&\xrightarrow{n \to \infty}  \frac{1}{n} \sum_{t=1}^n \sigma^2\left(\frac{t}{n}\right)   \\
&\xrightarrow{n \to \infty}  \int_0^1 \sigma^2\left(u\right) du + \mathcal{O}\left(\frac{1}{n}\right)  \\
&\xrightarrow{n \to \infty}  \int_0^1 \sigma^2\left(u\right) du  \\
\end{split}
$$

- [[variance]] goes to zero (TODO add proof)


Tags: mathematics time_series WS2425
<!--ID: 1737748473553-->
END