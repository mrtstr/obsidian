### non-parametric volatility model
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
W_{t, n}  &= \sum_{i=1}^t \frac{1}{\sqrt{n}} e_t \sim \mathcal{N}\left(0 , \frac{t}{n} \sigma^2 \right) \\
W_{t, n} - W_{t-1, n} &=  \frac{1}{\sqrt{n}} e_t \sim \mathcal{N}\left(0 , \frac{1}{n}\right) \\
X_{t,n} 
&= \ln\left(P_{\frac{t}{n}}\right) - \ln\left(P_{\frac{t-1}{n}}\right) \\
&= \frac{\alpha}{n} + \sigma \left(W_{t, n} - W_{t-1, n}\right) \\
&= \frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t \\
&\sim \mathcal{N}\left(\frac{\alpha}{n} , \frac{\sigma^2}{n}\right)
\end{split}
$$

### drift estimator

- the parameter $\alpha$ can be estimated as follows
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
&=  \frac{nT}{nT}  \alpha  + n \frac{\sigma}{\sqrt{n}} \sum_{t=1}^{T}  e_t\\
&= \alpha  + \sigma\sqrt{n} \sum_{t=1}^{T}  e_t\\
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

# ---------------------

![[wiener process#wiener process]]

![[geometric brownian motion (GBM)#geometric brownian motion]]

![[geometric brownian motion (GBM)#log returns]]


# Anki

START
Basic
[[non-parametric volatility model]] summary
- price $P_{t, n}$
- log returns $X_{t, n}$
- drift estimator
- realized [[volatility]] estimator

Back: 
### non-parametric volatility model
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
W_{t, n}  &= \sum_{i=1}^t \frac{1}{\sqrt{n}} e_t \sim \mathcal{N}\left(0 , \frac{t}{n} \sigma^2 \right) \\
W_{t, n} - W_{t-1, n} &=  \frac{1}{\sqrt{n}} e_t \sim \mathcal{N}\left(0 , \frac{1}{n}\right) \\
X_{t,n} 
&= \ln\left(P_{\frac{t}{n}}\right) - \ln\left(P_{\frac{t-1}{n}}\right) \\
&= \frac{\alpha}{n} + \sigma \left(W_{t, n} - W_{t-1, n}\right) \\
&= \frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t \\
&\sim \mathcal{N}\left(\frac{\alpha}{n} , \frac{\sigma^2}{n}\right)
\end{split}
$$

### drift estimator

- the parameter $\alpha$ can be estimated as follows
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
&=  \frac{nT}{nT}  \alpha  + n \frac{\sigma}{\sqrt{n}} \sum_{t=1}^{T}  e_t\\
&= \alpha  + \sigma\sqrt{n} \sum_{t=1}^{T}  e_t\\
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

___________
### geometric brownian motion
- [[geometric brownian motion (GBM)]] is a [[stochastic process]] that can be used to describe the evolution of financial asset prices in a random but predictable manner
- $P_t$ is a [[geometric brownian motion (GBM)]] with the [[wiener process]] $W_t$ the [[drift]]  $\mu$ (return rate) and the [[volatility]] (of the return) $\sigma$

$$
P_t = P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right)
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

#### approximation of the log returns
- for small returns the log returns can be approximated as follows

$$
\begin{split}
X_t 
&= \ln\left(\frac{P_t}{P_{t-1}} \right) \\
&= \ln\left(\left(\frac{P_t}{P_{t-1}}  -1 \right) +1 \right)  \\
&\approx \ln\left(\exp\left(\frac{P_t}{P_{t-1}}  -1 \right) \right) \quad \text{since }e^\alpha \approx 1+ \alpha  \\
&= \frac{P_t}{P_{t-1}} - 1 \\
\end{split}
$$


Tags: mathematics time_series WS2425
<!--ID: 1735633487121-->
END

START
Basic
[[non-parametric volatility model]]
- model for [[geometric brownian motion (GBM)]] with $n$ observations per time interval: price and log returns
Back: 
### non-parametric volatility model
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
W_{t, n}  &= \sum_{i=1}^t \frac{1}{\sqrt{n}} e_t \sim \mathcal{N}\left(0 , \frac{t}{n} \sigma^2 \right) \\
W_{t, n} - W_{t-1, n} &=  \frac{1}{\sqrt{n}} e_t \sim \mathcal{N}\left(0 , \frac{1}{n}\right) \\
X_{t,n} 
&= \ln\left(P_{\frac{t}{n}}\right) - \ln\left(P_{\frac{t-1}{n}}\right) \\
&= \frac{\alpha}{n} + \sigma \left(W_{t, n} - W_{t-1, n}\right) \\
&= \frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t \\
&\sim \mathcal{N}\left(\frac{\alpha}{n} , \frac{\sigma^2}{n}\right)
\end{split}
$$

___________
### geometric brownian motion
- [[geometric brownian motion (GBM)]] is a [[stochastic process]] that can be used to describe the evolution of financial asset prices in a random but predictable manner
- $P_t$ is a [[geometric brownian motion (GBM)]] with the [[wiener process]] $W_t$ the [[drift]]  $\mu$ (return rate) and the [[volatility]] (of the return) $\sigma$

$$
P_t = P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right)
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

#### approximation of the log returns
- for small returns the log returns can be approximated as follows

$$
\begin{split}
X_t 
&= \ln\left(\frac{P_t}{P_{t-1}} \right) \\
&= \ln\left(\left(\frac{P_t}{P_{t-1}}  -1 \right) +1 \right)  \\
&\approx \ln\left(\exp\left(\frac{P_t}{P_{t-1}}  -1 \right) \right) \quad \text{since }e^\alpha \approx 1+ \alpha  \\
&= \frac{P_t}{P_{t-1}} - 1 \\
\end{split}
$$


Tags: mathematics time_series WS2425
<!--ID: 1735633487125-->
END


START
Basic
[[drift]] estimator for [[non-parametric volatility model]]
- [[bias]]
- [[estimator consitency]]
- when can it be estimated?
Back: 
### non-parametric volatility model
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
W_{t, n}  &= \sum_{i=1}^t \frac{1}{\sqrt{n}} e_t \sim \mathcal{N}\left(0 , \frac{t}{n} \sigma^2 \right) \\
W_{t, n} - W_{t-1, n} &=  \frac{1}{\sqrt{n}} e_t \sim \mathcal{N}\left(0 , \frac{1}{n}\right) \\
X_{t,n} 
&= \ln\left(P_{\frac{t}{n}}\right) - \ln\left(P_{\frac{t-1}{n}}\right) \\
&= \frac{\alpha}{n} + \sigma \left(W_{t, n} - W_{t-1, n}\right) \\
&= \frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t \\
&\sim \mathcal{N}\left(\frac{\alpha}{n} , \frac{\sigma^2}{n}\right)
\end{split}
$$

### drift estimator

- the parameter $\alpha$ can be estimated as follows
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
&=  \frac{nT}{nT}  \alpha  + n \frac{\sigma}{\sqrt{n}} \sum_{t=1}^{T}  e_t\\
&= \alpha  + \sigma\sqrt{n} \sum_{t=1}^{T}  e_t\\
&= \alpha  \quad \text{for } T \to \infty\\
\end{split}
$$



___________
### geometric brownian motion
- [[geometric brownian motion (GBM)]] is a [[stochastic process]] that can be used to describe the evolution of financial asset prices in a random but predictable manner
- $P_t$ is a [[geometric brownian motion (GBM)]] with the [[wiener process]] $W_t$ the [[drift]]  $\mu$ (return rate) and the [[volatility]] (of the return) $\sigma$

$$
P_t = P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right)
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

#### approximation of the log returns
- for small returns the log returns can be approximated as follows

$$
\begin{split}
X_t 
&= \ln\left(\frac{P_t}{P_{t-1}} \right) \\
&= \ln\left(\left(\frac{P_t}{P_{t-1}}  -1 \right) +1 \right)  \\
&\approx \ln\left(\exp\left(\frac{P_t}{P_{t-1}}  -1 \right) \right) \quad \text{since }e^\alpha \approx 1+ \alpha  \\
&= \frac{P_t}{P_{t-1}} - 1 \\
\end{split}
$$


Tags: mathematics time_series WS2425
<!--ID: 1735633487127-->
END


START
Basic
realized [[volatility]] estimator for [[non-parametric volatility model]]
- [[bias]]
- [[estimator consitency]]
- when can it be estimated?

Back: 
### non-parametric volatility model
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
W_{t, n}  &= \sum_{i=1}^t \frac{1}{\sqrt{n}} e_t \sim \mathcal{N}\left(0 , \frac{t}{n} \sigma^2 \right) \\
W_{t, n} - W_{t-1, n} &=  \frac{1}{\sqrt{n}} e_t \sim \mathcal{N}\left(0 , \frac{1}{n}\right) \\
X_{t,n} 
&= \ln\left(P_{\frac{t}{n}}\right) - \ln\left(P_{\frac{t-1}{n}}\right) \\
&= \frac{\alpha}{n} + \sigma \left(W_{t, n} - W_{t-1, n}\right) \\
&= \frac{\alpha}{n} +  \frac{\sigma}{\sqrt{n}} e_t \\
&\sim \mathcal{N}\left(\frac{\alpha}{n} , \frac{\sigma^2}{n}\right)
\end{split}
$$

### drift estimator

- the parameter $\alpha$ can be estimated as follows
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
&=  \frac{nT}{nT}  \alpha  + n \frac{\sigma}{\sqrt{n}} \sum_{t=1}^{T}  e_t\\
&= \alpha  + \sigma\sqrt{n} \sum_{t=1}^{T}  e_t\\
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

___________
### geometric brownian motion
- [[geometric brownian motion (GBM)]] is a [[stochastic process]] that can be used to describe the evolution of financial asset prices in a random but predictable manner
- $P_t$ is a [[geometric brownian motion (GBM)]] with the [[wiener process]] $W_t$ the [[drift]]  $\mu$ (return rate) and the [[volatility]] (of the return) $\sigma$

$$
P_t = P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right)
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

#### approximation of the log returns
- for small returns the log returns can be approximated as follows

$$
\begin{split}
X_t 
&= \ln\left(\frac{P_t}{P_{t-1}} \right) \\
&= \ln\left(\left(\frac{P_t}{P_{t-1}}  -1 \right) +1 \right)  \\
&\approx \ln\left(\exp\left(\frac{P_t}{P_{t-1}}  -1 \right) \right) \quad \text{since }e^\alpha \approx 1+ \alpha  \\
&= \frac{P_t}{P_{t-1}} - 1 \\
\end{split}
$$


Tags: mathematics time_series WS2425
<!--ID: 1735633487130-->
END