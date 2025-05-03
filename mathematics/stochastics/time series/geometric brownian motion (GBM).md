### geometric brownian motion
- [[geometric brownian motion (GBM)]] is a [[stochastic process]] that can be used to describe the evolution of financial asset prices in a random but predictable manner
- $P_t$ is a [[geometric brownian motion (GBM)]] with the [[wiener process]] $W_t$ the [[drift]]  $\mu$ (return rate) and the [[volatility]] (of the return) $\sigma$

$$
P_t = P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right)
$$

### geometric brownian motion as a SDG
- given a deterministic case where the price of a good is growing by the constant interest rate $\mu$ each period the price in period $t$ can be modeled as follows

$$
\begin{split}
P_t 
&= X_0 \left(1+\mu\right)^t \\
&= \lim_{h \to 0} P_0 \left(1+\frac{\mu}{h}\right)^{ht} \\
&= P_0 \left(e^{\mu}\right)^t \\
\end{split}
$$
- by calculating the [[derivative]] we get the following equation for the change in price in period $dP_t = \mu  P_t dt$ which is the current price multiplied by the [[drift]] $\mu$ and the length of the time interval $dt$

$$
\begin{split}
\frac{dP_t}{dt}
&= \lim_{h\to 0} \frac{P_{t+h}-P_t}{h} \\
&= P_0 \lim_{h\to 0} \frac{e^{\mu(t+h)}-e^{\mu t}}{h} \\
&= P_0 e^{\mu t} \lim_{h\to 0} \frac{e^{\mu h}-1}{h} \\
&= P_0 e^{\mu t} \ln\left(e^{\mu}\right) \\
&= P_0 e^{\mu t} \mu  \\
&= P_t\mu  \\
\Rightarrow dP_t &= \mu  P_t dt
\end{split}
$$

- in the stochastic case we add the [[standard normal distribution|standard normal distributed]] change of the  [[wiener process]] $dW_t = W_{t+1} - W_t \sim \mathcal{N}(0, 1)$ and we get the following equation for the [[geometric brownian motion (GBM)]]


$$
\begin{split}
dP_t 
&= P_t ( \mu   dt + \sigma \: dW_t) \\
&= P_t \mu   dt + P_t \sigma \: dW_t \\
&= P_{t+1} - P_{t} \\
\end{split}
$$

- by solving the [[stochastic differential equation]] we get the following 

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

### components
- exponential growth $\left(e^{\mu}\right)^t$ of the asset price assuming a constant interest rate $\mu$ (using the fact that $e^\alpha \approx 1+ \alpha$)
- random part modeled with a [[wiener process]] in the exponent $e^{\sigma W_t}$ with the impact modeled by the [[volatility]] $\sigma$




### returns
- in period $t$ the returns $R_t$ are given by the following

$$
\begin{split}
R_t = \frac{P_t - P_{t-1}}{P_{t-1}} 
=  \frac{P_t}{P_{t-1}} - 1
\end{split}
$$
#### relationship returns to log returns
- the returns $R_t$ and the log returns $X_t$ are related as follows

$$
\begin{split}
X_t 
&= \ln\left(\frac{P_t}{P_{t-1}} \right) \\
&= \ln\left(R_t + 1 \right) \\
\Leftrightarrow\\
R_t 
&= \exp\left(X_t \right) - 1 \\
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

### expectation
- since the [[geometric brownian motion (GBM)]] has a [[log normal distribution]] the [[expectation]] can be calculated as follows

$$
\begin{split}
\mathbb{E}\left[P_t \right]
&= P_0 e^{\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \frac{\sigma^2 t}{2}} \\
&= P_0 e^{\mu t}  \\
\end{split}
$$

### variance
- since the [[geometric brownian motion (GBM)]] has a [[log normal distribution]] the [[variance]] can be calculated as follows

$$
\begin{split}
\mathbb{VAR}\left[P_t \right]
&= e^{2\left(\mu - \frac{\sigma^2}{2}\right)\cdot t+ \sigma^2 t} (e^{\sigma^2t} - 1 ) \\
&= e^{2\mu t} (e^{\sigma^2t} - 1 ) \\
\end{split}
$$

#### martingale
- [[martingal]]
$$
\begin{split}
\mathbb{E}\left[P_{t}| \left\{P_s: s \leq t-1\right\}\right] = \mu P_{t-1}
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

### short comings

- lets assume $X_t' = X_t - \left(\mu - \frac{\sigma^2}{2} \right)$ or that the mean of the log returns is zero thus $\mu = \frac{\sigma^2}{2}$ like for currency exchange rates without general trends
- with the [[geometric brownian motion (GBM)]] model the log returns $X_t$ are [[white noise#gaussian white noise|gaussian white noise]] and thus [[stochastic independent]]
- when checking empirically one can see that $X_t$ is [[white noise]] because its [[autocorrelation (ACF)]] is zero but when checking other [[moments]] like $X_t^2$ one can see that the log returns are not [[stochastic independent]]

observations for $h>0$:

$$
\begin{split}
\mathbb{COV}[X_{t}, X_{t+h}] = \mathbb{E}[X_{t}X_{t+h}]-\mathbb{E}[X_{t}]\mathbb{E}[X_{t+h}] = 0\\
\mathbb{COV}[X_{t}^2, X_{t+h}^2] = \mathbb{E}[X_{t}^2X_{t+h}^2]-\mathbb{E}[X_{t}^2]\mathbb{E}[X_{t+h}^2] \neq 0\\
\end{split}
$$

# ---------- 

![[white noise#white noise]]

![[natural logarithm#limit identity of the natural logarithm]]

![[eulers number#limit identity of eulers number]]


![[log normal distribution#moments of the log normal distribution]]

![[log normal distribution#log normal distribution]]

![[wiener process#wiener process]]

# anki

START
Basic
[[geometric brownian motion (GBM)]] 
- short commings when modeling real asset prices

Back: 
- lets assume $X_t' = X_t - \left(\mu - \frac{\sigma^2}{2} \right)$ or that the mean of the log returns is zero thus $\mu = \frac{\sigma^2}{2}$ like for currency excange rates without general trends
- with the [[geometric brownian motion (GBM)]] model the log returns $X_t$ are [[white noise#gaussian white noise|gaussian white noise]] and thus [[stochastic independent]]
- when checking empirically one can see that $X_t$ is [[white noise]] because its [[autocorrelation (ACF)]] is zero but when checking other [[moments]] like $X_t^2$ one can see that the log returns are not [[stochastic independent]]

observations for $h>0$:

$$
\begin{split}
\mathbb{COV}[X_{t}, X_{t+h}] = \mathbb{E}[X_{t}X_{t+h}]-\mathbb{E}[X_{t}]\mathbb{E}[X_{t+h}] = 0\\
\mathbb{COV}[X_{t}^2, X_{t+h}^2] = \mathbb{E}[X_{t}^2X_{t+h}^2]-\mathbb{E}[X_{t}^2]\mathbb{E}[X_{t+h}^2] \neq 0\\
\end{split}
$$

____________
### geometric brownian motion
- [[geometric brownian motion (GBM)]] is a [[stochastic process]] that can be used to describe the evolution of financial asset prices in a random but predictable manner
- $P_t$ is a [[geometric brownian motion (GBM)]] with the [[wiener process]] $W_t$ the [[drift]]  $\mu$ (return rate) and the [[volatility]] (of the return) $\sigma$


$$
P_t = P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right)
$$

### geometric brownian motion is log normal distributed
- [[geometric brownian motion (GBM)]] is [[log normal distribution| log normal distributed]]
- given $P_t$ with $P_0=1$ and the [[wiener process]] $W_t \sim \mathcal{N}(0, t)$
- first part is deterministic and the second part is [[normal distribution|normal distributed]] $\sigma W_t \sim \mathcal{N}(0, \sigma^2 t)$
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

Tags: mathematics time_series WS2425
<!--ID: 1735316706789-->
END

START
Basic
[[geometric brownian motion (GBM)]] 
- [[maximum likelihood estimator]] for the parameters

Back: 
#### maximum likelihood estimator for the parameters
- since the log returns are [[normal distribution|normal distributed]] the [[maximum likelihood estimator]] can be calculated as follows
- from $\mathbb{E}[X] = \mu - \frac{\sigma^2}{2} \rightarrow \mu = \mathbb{E}[X]  - \frac{\sigma^2}{2}$

$$
\begin{split}
\bar X_n &= \frac{1}{n}  \sum_{i=1}^n X_i \\
\hat\sigma_{ML}^2 &= \frac{1}{n-1}  \sum_{i=1}^n \left(X_i - \bar X_n\right)^2 \\
\hat\mu_{ML}^2 &= \bar X_n +   \frac{\hat\sigma_{ML}^2}{2} \\
\end{split}
$$

#### log returns
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


____________

### geometric brownian motion
- [[geometric brownian motion (GBM)]] is a [[stochastic process]] that can be used to describe the evolution of financial asset prices in a random but predictable manner
- $P_t$ is a [[geometric brownian motion (GBM)]] with the [[wiener process]] $W_t$ the [[drift]]  $\mu$ (return rate) and the [[volatility]] (of the return) $\sigma$


$$
P_t = P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right)
$$

### geometric brownian motion is log normal distributed
- [[geometric brownian motion (GBM)]] is [[log normal distribution| log normal distributed]]
- given $P_t$ with $P_0=1$ and the [[wiener process]] $W_t \sim \mathcal{N}(0, t)$
- first part is deterministic and the second part is [[normal distribution|normal distributed]] $\sigma W_t \sim \mathcal{N}(0, \sigma^2 t)$
- thus the [[natural logarithm]] of $P_t$ is also [[normal distribution|normal distributed]]  and thus $P_t$ has a [[log normal distribution]]

$$
\begin{split}
\ln(P_t) = \left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t \sim \mathcal{N}\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t, \sigma^2 t \right)
\end{split}
$$



Tags: mathematics time_series WS2425
<!--ID: 1735314209304-->
END

START
Basic
[[geometric brownian motion (GBM)]] (without  proof)
- definition returns $R_t$
- definition log returns $X_t$
- distribution of the log returns
- aproximation of the log returns
- relationship returns to log returns
Back: 
#### returns
- in perod $t$ the returns $R_t$ are given by the following

$$
\begin{split}
R_t = \frac{P_t - P_{t-1}}{P_{t-1}} 
=  \frac{P_t}{P_{t-1}} - 1
\end{split}
$$
#### log returns
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

#### aproximation of the log returns
- for small retuns the log returns can be approximated as follows

$$
\begin{split}
X_t 
&= \ln\left(\frac{P_t}{P_{t-1}} \right) \\
&= \ln\left(\left(\frac{P_t}{P_{t-1}}  -1 \right) +1 \right)  \\
&\approx \ln\left(\exp\left(\frac{P_t}{P_{t-1}}  -1 \right) \right) \quad \text{since }e^\alpha \approx 1+ \alpha  \\
&= \frac{P_t}{P_{t-1}} - 1 \\
\end{split}
$$
#### relationship returns to log returns
- the returns $R_t$ and the log returns $X_t$ are related as follows

$$
\begin{split}
X_t 
&= \ln\left(\frac{P_t}{P_{t-1}} \right) \\
&= \ln\left(R_t + 1 \right) \\
\Leftrightarrow\\
R_t 
&= \exp\left(X_t \right) - 1 \\
\end{split}
$$

____________

### geometric brownian motion
- [[geometric brownian motion (GBM)]] is a [[stochastic process]] that can be used to describe the evolution of financial asset prices in a random but predictable manner
- $P_t$ is a [[geometric brownian motion (GBM)]] with the [[wiener process]] $W_t$ the [[drift]]  $\mu$ (return rate) and the [[volatility]] (of the return) $\sigma$
- $P_t$ has a [[log normal distribution]] and is a [[martingal]] and a [[markov process]]

$$
P_t = P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right)
$$

### geometric brownian motion is log normal distributed
- [[geometric brownian motion]] is [[log normal distribution| log normal distributed]]
- given $P_t$ with $P_0=1$ and the [[wiener process]] $W_t \sim \mathcal{N}(0, t)$
- first part is deterministic and the second part is [[normal distribution|normal distributed]] $\sigma W_t \sim \mathcal{N}(0, \sigma^2 t)$
- thus the [[natural logarithm]] of $P_t$ is also [[normal distribution|normal distributed]]  and thus $P_t$ has a [[log normal distribution]]

$$
\begin{split}
\ln(P_t) = \left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t \sim \mathcal{N}\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t, \sigma^2 t \right)
\end{split}
$$



Tags: mathematics time_series WS2425
<!--ID: 1735301089856-->
END

START
Basic
[[geometric brownian motion (GBM)]] 
- show that the log returns can be approximated as follows for small retuns

$$
X_t \approx \frac{P_t}{P_{t-1}} - 1 
$$

Back: 
#### log returns
- the log returns $X_t$ are defined as follows

$$
\begin{split}
X_t 
&= \ln\left(\frac{P_t}{P_{t-1}} \right) \\
&= \ln\left(P_t \right) - \ln\left(P_{t-1} \right) \\
\end{split}
$$

#### aproximation of the log returns
- for small retuns the log returns can be approximated as follows

$$
\begin{split}
X_t 
&= \ln\left(\frac{P_t}{P_{t-1}} \right) \\
&= \ln\left(\left(\frac{P_t}{P_{t-1}}  -1 \right) +1 \right)  \\
&\approx \ln\left(\exp\left(\frac{P_t}{P_{t-1}}  -1 \right) \right) \quad \text{since }e^\alpha \approx 1+ \alpha  \\
&= \frac{P_t}{P_{t-1}} - 1 \\
\end{split}
$$

____________

### [[series]] identity of exponential [[function]]

$$
e^\lambda = \sum\limits_{k=0}^\infty \frac{\lambda^k}{k!}
$$

### geometric brownian motion
- [[geometric brownian motion (GBM)]] is a [[stochastic process]] that can be used to describe the evolution of financial asset prices in a random but predictable manner
- $P_t$ is a [[geometric brownian motion (GBM)]] with the [[wiener process]] $W_t$ the [[drift]]  $\mu$ (return rate) and the [[volatility]] (of the return) $\sigma$
- $P_t$ has a [[log normal distribution]] and is a [[martingal]] and a [[markov process]]

$$
P_t = P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right)
$$

### geometric brownian motion is log normal distributed
- [[geometric brownian motion]] is [[log normal distribution| log normal distributed]]
- given $P_t$ with $P_0=1$ and the [[wiener process]] $W_t \sim \mathcal{N}(0, t)$
- first part is deterministic and the second part is [[normal distribution|normal distributed]] $\sigma W_t \sim \mathcal{N}(0, \sigma^2 t)$
- thus the [[natural logarithm]] of $P_t$ is also [[normal distribution|normal distributed]]  and thus $P_t$ has a [[log normal distribution]]

$$
\begin{split}
\ln(P_t) = \left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t \sim \mathcal{N}\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t, \sigma^2 t \right)
\end{split}
$$



Tags: mathematics time_series WS2425
<!--ID: 1735301089864-->
END

START
Basic
[[geometric brownian motion (GBM)]]
- distribution of the log returns with proof
Back: 
#### log returns
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



____________

### geometric brownian motion
- [[geometric brownian motion (GBM)]] is a [[stochastic process]] that can be used to describe the evolution of financial asset prices in a random but predictable manner
- $P_t$ is a [[geometric brownian motion (GBM)]] with the [[wiener process]] $W_t$ the [[drift]]  $\mu$ (return rate) and the [[volatility]] (of the return) $\sigma$
- $P_t$ has a [[log normal distribution]] and is a [[martingal]] and a [[markov process]]

$$
P_t = P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right)
$$

### geometric brownian motion is log normal distributed
- [[geometric brownian motion]] is [[log normal distribution| log normal distributed]]
- given $P_t$ with $P_0=1$ and the [[wiener process]] $W_t \sim \mathcal{N}(0, t)$
- first part is deterministic and the second part is [[normal distribution|normal distributed]] $\sigma W_t \sim \mathcal{N}(0, \sigma^2 t)$
- thus the [[natural logarithm]] of $P_t$ is also [[normal distribution|normal distributed]]  and thus $P_t$ has a [[log normal distribution]]

$$
\begin{split}
\ln(P_t) = \left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t \sim \mathcal{N}\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t, \sigma^2 t \right)
\end{split}
$$



Tags: mathematics time_series WS2425
<!--ID: 1735301089876-->
END




START
Basic
[[geometric brownian motion (GBM)]]
- [[expectation]]
- [[variance]]
Back: 
### geometric brownian motion
- [[geometric brownian motion (GBM)]] is a [[stochastic process]] that can be used to describe the evolution of financial asset prices in a random but predictable manner
- $P_t$ is a [[geometric brownian motion (GBM)]] with the [[wiener process]] $W_t$ the [[drift]]  $\mu$ (return rate) and the [[volatility]] (of the return) $\sigma$
- $P_t$ has a [[log normal distribution]] and is a [[martingal]] and a [[markov process]]

$$
P_t = P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right)
$$

### geometric brownian motion is log normal distributed
- [[geometric brownian motion]] is [[log normal distribution| log normal distributed]]
- given $P_t$ with $P_0=1$ and the [[wiener process]] $W_t \sim \mathcal{N}(0, t)$
- first part is deterministic and the second part is [[normal distribution|normal distributed]] $\sigma W_t \sim \mathcal{N}(0, \sigma^2 t)$
- thus the [[natural logarithm]] of $P_t$ is also [[normal distribution|normal distributed]]  and thus $P_t$ has a [[log normal distribution]]

$$
\begin{split}
\ln(P_t) = \left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t \sim \mathcal{N}\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t, \sigma^2 t \right)
\end{split}
$$

### properties

##### expectation
- since the [[geometric brownian motion (GBM)]] has a [[log normal distribution]] the [[expectation]] can be calculated as follows

$$
\begin{split}
\mathbb{E}\left[P_t \right]
&= P_0 e^{\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \frac{\sigma^2 t}{2}} \\
&= P_0 e^{\mu t}  \\
\end{split}
$$

##### variance
- since the [[geometric brownian motion (GBM)]] has a [[log normal distribution]] the [[variance]] can be calculated as follows

$$
\begin{split}
\mathbb{VAR}\left[P_t \right]
&= e^{2\left(\mu - \frac{\sigma^2}{2}\right)\cdot t+ \sigma^2 t} (e^{\sigma^2t} - 1 ) \\
&= e^{2\mu t} (e^{\sigma^2t} - 1 ) \\
\end{split}
$$

### log normal distribution
- A [[random variable]] $X$ is [[log normal distribution|log normal distributed]] if the [[logarithm]] of $X$ $Y=log(X) \sim f_Y\left(y|\mu, \sigma^2\right)$ is [[normal distribution|normal distributed]]

#### CDF
$$
F_X\left(x \: | \: \mu, \sigma^2\right) = 
F_Y\left(log(x) \: | \: \mu, \sigma^2\right)
$$

#### PDF
$$
f_X\left(x \: | \: \mu, \sigma^2\right) = 
\frac{1}{x} f_Y\left(log(x) \: | \: \mu, \sigma^2\right)
$$

#### moments of the log normal distribution

$$
\mathbb{E}\left[X^n\right] = e^{n\mu + \frac{n^2}{2} \sigma^2 }
$$

$$
\mathbb{E}\left[X\right] = e^{\mu + \frac{\sigma^2}{2}}
$$

$$
\begin{split}
\mathbb{VAR}\left[X\right] 
&= \mathbb{E}\left[X^2\right] - \mathbb{E}\left[X\right]^2 \\
&= e^{2\mu + 2 \sigma^2 } - e^{2 \cdot 1\mu + \frac{1^2}{2} 2 \sigma^2 } \\
&= e^{2\mu + 2 \sigma^2 } - e^{2 \mu +  \sigma^2 } \\
&= e^{2\mu+ \sigma^2} (e^{\sigma^2} - 1 ) \\
\end{split}
$$




Tags: mathematics time_series WS2425
<!--ID: 1735301089885-->
END

START
Basic
approximation of $1+ \alpha$ and why does it work?

Back: 
- works for small $\alpha$
$$e^\alpha \approx 1+ \alpha$$

works because its a approximation with the following formula until $k = 1$
### [[series]] identity of exponential [[function]]

$$
e^\lambda = \sum\limits_{k=0}^\infty \frac{\lambda^k}{k!}
$$

Tags: mathematics time_series WS2425
<!--ID: 1735149315358-->
END

START
Basic
[[geometric brownian motion (GBM)]]
- concept: what is it used for
- defintion
- distribution
- [[stochastic differential equation]]
Back: 
### geometric brownian motion
- [[geometric brownian motion (GBM)]] is a [[stochastic process]] that can be used to describe the evolution of financial asset prices in a random but predictable manner
- $P_t$ is a [[geometric brownian motion (GBM)]] with the [[wiener process]] $W_t$ the [[drift]]  $\mu$ (return rate) and the [[volatility]] (of the return) $\sigma$
- $P_t$ has a [[log normal distribution]] and is a [[martingal]] and a [[markov process]]

$$
P_t = P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right)
$$

### geometric brownian motion as a  SDG
- given a deterministic case where the price of a good is growing by the constant interest rate $\mu$ each period the price in period $t$ can be modled as follows

$$
\begin{split}
P_t 
&= X_0 \left(1+\mu\right)^t \\
&= \lim_{h \to 0} P_0 \left(1+\frac{\mu}{h}\right)^{ht} \\
&= P_0 \left(e^{\mu}\right)^t \\
\end{split}
$$
- by calculating the [[derivative]] we get the following equation for the change in price in period $dP_t = \mu  P_t dt$ which is the current price multiplied by the [[drift]] $\mu$ and the length of the time interval $dt$

$$
\begin{split}
\frac{dP_t}{dt}
&= \lim_{h\to 0} \frac{P_{t+h}-P_t}{h} \\
&= P_0 \lim_{h\to 0} \frac{e^{\mu(t+h)}-e^{\mu t}}{h} \\
&= P_0 e^{\mu t} \lim_{h\to 0} \frac{e^{\mu h}-1}{h} \\
&= P_0 e^{\mu t} \ln\left(e^{\mu}\right) \\
&= P_0 e^{\mu t} \mu  \\
&= P_t\mu  \\
\Rightarrow dP_t &= \mu  P_t dt
\end{split}
$$

- in the stochastic case we add the [[standard normal distribution|standard normal distributed]] change of the  [[wiener process]] $dW_t = W_{t+1} - W_t \sim \mathcal{N}(0, 1)$ and we get the following equation for the [[geometric brownian motion (GBM)]]


$$
\begin{split}
dP_t 
&= P_t ( \mu   dt + \sigma \: dW_t) \\
&= P_t \mu   dt + P_t \sigma \: dW_t \\
&= P_{t+1} - P_{t} \\
\end{split}
$$

- by solving the [[stochastic differential equation]] we get the following 

$$
P_t = P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right)
$$



### geometric brownian motion is log normal distributed
- [[geometric brownian motion]] is [[log normal distribution| log normal distributed]]
- given $P_t$ with $P_0=1$ and the [[wiener process]] $W_t \sim \mathcal{N}(0, t)$
- first part is deterministic and the second part is [[normal distribution|normal distributed]] $\sigma W_t \sim \mathcal{N}(0, \sigma^2 t)$
- thus the [[natural logarithm]] of $P_t$ is also [[normal distribution|normal distributed]]  and thus $P_t$ has a [[log normal distribution]]

$$
\begin{split}
\ln(P_t) = \left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t \sim \mathcal{N}\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t, \sigma^2 t \right)
\end{split}
$$

___________

### wiener process
- [[time series]] $W_t: t \geq 0$ which is the result of [[integral]]/sum [[white noise#gaussian white noise|gaussian white noise]] $e_t$

$$
\begin{split}
W_t 
&=W_{t-1} + e_t \\
&= \left\{
\begin{matrix}
\sum_{i=1}^t e_i & \text{for } t>0 \\ 
0 & \text{for } t=0 \\
\end{matrix} \right.
\end{split}
$$
#### axioms

1) $W_0 = 0$
2) $W_t$ has indenpendent increments thus $W_{t+h}-W_{t}$ is independent of $W_s: s < t$ 
3) the increments are [[normal distribution|normal distributed]] $W_{t+h}-W_t \sim \mathcal{N}(0, h)$
4) $W_t$ is a [[continuous function]] in $t$

#### properties
$$
\mathbb{E}[W_t] = \sum_{i=1}^t \mathbb{E}\left[e_i\right]    = 0
$$

$$
\mathbb{VAR}[W_t] = \sum_{i=1}^t \mathbb{VAR}\left[e_i\right]    = t
$$

$$
\begin{split}
\mathbb{COV}[W_t, W_{t+h}] 
&= \mathbb{E}\left[W_t W_{t+h}\right]  \\
&= \mathbb{E}\left[\left(\sum_{i=1}^t e_i\right) \left(\sum_{j=1}^{t+h} e_j\right)\right]  \\
&= \mathbb{E}\left[\sum_{i=1}^t \sum_{j=1}^{t+h} e_i  e_j\right]  \\
&= \sum_{i=1}^t \mathbb{VAR}\left[e_i\right] + h \cdot 0 \\
&= t \\
\end{split}
$$

$$
\begin{split}
\mathbb{COR}\left[W_t, W_{s}\right]
&= \frac{\mathbb{COR}\left[W_t, W_{s}\right] } {\sqrt{\mathbb{VAR}\left[ W_{s}\right]\mathbb{VAR}\left[ W_{t}\right] }} \quad \text{with } t > s \\
&= \frac{t}{\sqrt{t s} }  \\
&= \frac{\sqrt{t }}{\sqrt{s} }  \\
\end{split}
$$

### log normal distribution
- A [[random variable]] $X$ is [[log normal distribution|log normal distributed]] if the [[logarithm]] of $X$ $Y=log(X) \sim f_Y\left(y|\mu, \sigma^2\right)$ is [[normal distribution|normal distributed]]


```functionplot
---
title: 
xLabel: 
yLabel: 
bounds: [-2, 4, 0, 0.7]
disableZoom: true
grid: true
---
f(x) = 1/x 1/sqrt(2*PI) exp(-log(x)^2 / 2)
g(x) = 1/sqrt(2*PI) exp(-x^2 / 2)
```

#### CDF
$$
F_X\left(x \: | \: \mu, \sigma^2\right) = 
F_Y\left(log(x) \: | \: \mu, \sigma^2\right)
$$
proof
$$
\begin{split}
F_X\left(x\: | \: \mu, \sigma^2\right) 
&= P\left(X \leq x\right)  \\
&= P\left(log(X) \leq log(x)\right) \qquad \text{(since log is monotone increasing)}\\
&= F_Y\left(log(X)\right) \\
&= F_Y\left(log(x) \: | \: \mu, \sigma^2\right)
\end{split}
$$

#### PDF
$$
f_X\left(x \: | \: \mu, \sigma^2\right) = 
\frac{1}{x} f_Y\left(log(x) \: | \: \mu, \sigma^2\right)
$$



proof

$$
\begin{split}
f_X\left(x \: | \: \mu, \sigma^2\right) 
&= \frac{dF_X\left(x \: | \: \mu, \sigma^2\right)}{dy} \\ 
&= \frac{dF_Y\left(log(x) \: | \: \mu, \sigma^2\right)}{dy} \\ 
&= \frac{dlog(x)}{dy} f_Y\left(log(x) \: | \: \mu, \sigma^2\right)  \\ 
&= \frac{1}{x} f_Y\left(log(x) \: | \: \mu, \sigma^2\right)  \\ 


\end{split}
$$

### limit identity of the natural logarithm

$$
\begin{split}
\ln(a) &= \lim_{h \rightarrow 0} \frac{a^h - 1}{h}
\end{split}
$$

### limit identity of eulers number

$$
\begin{split}

e &= \lim_{n \rightarrow \infty} \left(1 + \frac{1}{n}\right)^n \\
&\Leftrightarrow_{h=\frac{1}{n}}
\\
e &= \lim_{h \rightarrow 0} \left(1 + h\right)^{\frac{1}{h}}

\end{split}
\tag{limit identity of e}
$$


Tags: mathematics time_series WS2425
<!--ID: 1735149315373-->
END



START
Basic
distribution of the [[geometric brownian motion (GBM)]] with proof

Back: 
### geometric brownian motion
- [[geometric brownian motion (GBM)]] is a [[stochastic process]] that can be used to describe the evolution of financial asset prices in a random but predictable manner
- $P_t$ is a [[geometric brownian motion (GBM)]] with the [[wiener process]] $W_t$ the [[drift]]  $\mu$ (return rate) and the [[volatility]] (of the return) $\sigma$
- $P_t$ has a [[log normal distribution]] and is a [[martingal]] and a [[markov process]]

$$
P_t = P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right)
$$

### geometric brownian motion is log normal distributed
- [[geometric brownian motion]] is [[log normal distribution| log normal distributed]]
- given $P_t$ with $P_0=1$ and the [[wiener process]] $W_t \sim \mathcal{N}(0, t)$
- first part is deterministic and the second part is [[normal distribution|normal distributed]] $\sigma W_t \sim \mathcal{N}(0, \sigma^2 t)$
- thus the [[natural logarithm]] of $P_t$ is also [[normal distribution|normal distributed]]  and thus $P_t$ has a [[log normal distribution]]

$$
\begin{split}
\ln(P_t) = \left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t \sim \mathcal{N}\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t, \sigma^2 t \right)
\end{split}
$$

___________

### wiener process
- [[time series]] $W_t: t \geq 0$ which is the result of [[integral]]/sum [[white noise#gaussian white noise|gaussian white noise]] $e_t$

$$
\begin{split}
W_t 
&=W_{t-1} + e_t \\
&= \left\{
\begin{matrix}
\sum_{i=1}^t e_i & \text{for } t>0 \\ 
0 & \text{for } t=0 \\
\end{matrix} \right.
\end{split}
$$
#### axioms

1) $W_0 = 0$
2) $W_t$ has indenpendent increments thus $W_{t+h}-W_{t}$ is independent of $W_s: s < t$ 
3) the increments are [[normal distribution|normal distributed]] $W_{t+h}-W_t \sim \mathcal{N}(0, h)$
4) $W_t$ is a [[continuous function]] in $t$

#### properties
$$
\mathbb{E}[W_t] = \sum_{i=1}^t \mathbb{E}\left[e_i\right]    = 0
$$

$$
\mathbb{VAR}[W_t] = \sum_{i=1}^t \mathbb{VAR}\left[e_i\right]    = t
$$

$$
\begin{split}
\mathbb{COV}[W_t, W_{t+h}] 
&= \mathbb{E}\left[W_t W_{t+h}\right]  \\
&= \mathbb{E}\left[\left(\sum_{i=1}^t e_i\right) \left(\sum_{j=1}^{t+h} e_j\right)\right]  \\
&= \mathbb{E}\left[\sum_{i=1}^t \sum_{j=1}^{t+h} e_i  e_j\right]  \\
&= \sum_{i=1}^t \mathbb{VAR}\left[e_i\right] + h \cdot 0 \\
&= t \\
\end{split}
$$

$$
\begin{split}
\mathbb{COR}\left[W_t, W_{s}\right]
&= \frac{\mathbb{COR}\left[W_t, W_{s}\right] } {\sqrt{\mathbb{VAR}\left[ W_{s}\right]\mathbb{VAR}\left[ W_{t}\right] }} \quad \text{with } t > s \\
&= \frac{t}{\sqrt{t s} }  \\
&= \frac{\sqrt{t }}{\sqrt{s} }  \\
\end{split}
$$

### log normal distribution
- A [[random variable]] $X$ is [[log normal distribution|log normal distributed]] if the [[logarithm]] of $X$ $Y=log(X) \sim f_Y\left(y|\mu, \sigma^2\right)$ is [[normal distribution|normal distributed]]


```functionplot
---
title: 
xLabel: 
yLabel: 
bounds: [-2, 4, 0, 0.7]
disableZoom: true
grid: true
---
f(x) = 1/x 1/sqrt(2*PI) exp(-log(x)^2 / 2)
g(x) = 1/sqrt(2*PI) exp(-x^2 / 2)
```

#### CDF
$$
F_X\left(x \: | \: \mu, \sigma^2\right) = 
F_Y\left(log(x) \: | \: \mu, \sigma^2\right)
$$
proof
$$
\begin{split}
F_X\left(x\: | \: \mu, \sigma^2\right) 
&= P\left(X \leq x\right)  \\
&= P\left(log(X) \leq log(x)\right) \qquad \text{(since log is monotone increasing)}\\
&= F_Y\left(log(X)\right) \\
&= F_Y\left(log(x) \: | \: \mu, \sigma^2\right)
\end{split}
$$

#### PDF
$$
f_X\left(x \: | \: \mu, \sigma^2\right) = 
\frac{1}{x} f_Y\left(log(x) \: | \: \mu, \sigma^2\right)
$$



proof

$$
\begin{split}
f_X\left(x \: | \: \mu, \sigma^2\right) 
&= \frac{dF_X\left(x \: | \: \mu, \sigma^2\right)}{dy} \\ 
&= \frac{dF_Y\left(log(x) \: | \: \mu, \sigma^2\right)}{dy} \\ 
&= \frac{dlog(x)}{dy} f_Y\left(log(x) \: | \: \mu, \sigma^2\right)  \\ 
&= \frac{1}{x} f_Y\left(log(x) \: | \: \mu, \sigma^2\right)  \\ 


\end{split}
$$


Tags: mathematics time_series WS2425
<!--ID: 1735149315379-->
END


START
Basic
[[geometric brownian motion (GBM)]]: how can the equation be derived?

Back: 
### geometric brownian motion
- [[geometric brownian motion (GBM)]] is a [[stochastic process]] that can be used to describe the evolution of financial asset prices in a random but predictable manner
- $P_t$ is a [[geometric brownian motion (GBM)]] with the [[wiener process]] $W_t$ the [[drift]]  $\mu$ (return rate) and the [[volatility]] (of the return) $\sigma$
- $P_t$ has a [[log normal distribution]] and is a [[martingal]] and a [[markov process]]

$$
P_t = P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right)
$$

### geometric brownian motion as a  SDG
- given a deterministic case where the price of a good is growing by the constant interest rate $\mu$ each period the price in period $t$ can be modled as follows

$$
\begin{split}
P_t 
&= X_0 \left(1+\mu\right)^t \\
&= \lim_{h \to 0} P_0 \left(1+\frac{\mu}{h}\right)^{ht} \\
&= P_0 \left(e^{\mu}\right)^t \\
\end{split}
$$
- by calculating the [[derivative]] we get the following equation for the change in price in period $dP_t = \mu  P_t dt$ which is the current price multiplied by the [[drift]] $\mu$ and the length of the time interval $dt$

$$
\begin{split}
\frac{dP_t}{dt}
&= \lim_{h\to 0} \frac{P_{t+h}-P_t}{h} \\
&= P_0 \lim_{h\to 0} \frac{e^{\mu(t+h)}-e^{\mu t}}{h} \\
&= P_0 e^{\mu t} \lim_{h\to 0} \frac{e^{\mu h}-1}{h} \\
&= P_0 e^{\mu t} \ln\left(e^{\mu}\right) \\
&= P_0 e^{\mu t} \mu  \\
&= P_t\mu  \\
\Rightarrow dP_t &= \mu  P_t dt
\end{split}
$$

- in the stochastic case we add the [[standard normal distribution|standard normal distributed]] change of the  [[wiener process]] $dW_t = W_{t+1} - W_t \sim \mathcal{N}(0, 1)$ and we get the following equation for the [[geometric brownian motion (GBM)]]


$$
\begin{split}
dP_t 
&= P_t ( \mu   dt + \sigma \: dW_t) \\
&= P_t \mu   dt + P_t \sigma \: dW_t \\
&= P_{t+1} - P_{t} \\
\end{split}
$$

- by solving the [[stochastic differential equation]] we get the following 

$$
P_t = P_0 \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t\right)
$$



### geometric brownian motion is log normal distributed
- [[geometric brownian motion]] is [[log normal distribution| log normal distributed]]
- given $P_t$ with $P_0=1$ and the [[wiener process]] $W_t \sim \mathcal{N}(0, t)$
- first part is deterministic and the second part is [[normal distribution|normal distributed]] $\sigma W_t \sim \mathcal{N}(0, \sigma^2 t)$
- thus the [[natural logarithm]] of $P_t$ is also [[normal distribution|normal distributed]]  and thus $P_t$ has a [[log normal distribution]]

$$
\begin{split}
\ln(P_t) = \left(\mu - \frac{\sigma^2}{2}\right)\cdot t + \sigma W_t \sim \mathcal{N}\left(\left(\mu - \frac{\sigma^2}{2}\right)\cdot t, \sigma^2 t \right)
\end{split}
$$

___________

### limit identity of the natural logarithm

$$
\begin{split}
\ln(a) &= \lim_{h \rightarrow 0} \frac{a^h - 1}{h}
\end{split}
$$

### limit identity of eulers number

$$
\begin{split}

e &= \lim_{n \rightarrow \infty} \left(1 + \frac{1}{n}\right)^n \\
&\Leftrightarrow_{h=\frac{1}{n}}
\\
e &= \lim_{h \rightarrow 0} \left(1 + h\right)^{\frac{1}{h}}

\end{split}
\tag{limit identity of e}
$$

### wiener process
- [[time series]] $W_t: t \geq 0$ which is the result of [[integral]]/sum [[white noise#gaussian white noise|gaussian white noise]] $e_t$

$$
\begin{split}
W_t 
&=W_{t-1} + e_t \\
&= \left\{
\begin{matrix}
\sum_{i=1}^t e_i & \text{for } t>0 \\ 
0 & \text{for } t=0 \\
\end{matrix} \right.
\end{split}
$$
#### axioms

1) $W_0 = 0$
2) $W_t$ has indenpendent increments thus $W_{t+h}-W_{t}$ is independent of $W_s: s < t$ 
3) the increments are [[normal distribution|normal distributed]] $W_{t+h}-W_t \sim \mathcal{N}(0, h)$
4) $W_t$ is a [[continuous function]] in $t$

#### properties
$$
\mathbb{E}[W_t] = \sum_{i=1}^t \mathbb{E}\left[e_i\right]    = 0
$$

$$
\mathbb{VAR}[W_t] = \sum_{i=1}^t \mathbb{VAR}\left[e_i\right]    = t
$$

$$
\begin{split}
\mathbb{COV}[W_t, W_{t+h}] 
&= \mathbb{E}\left[W_t W_{t+h}\right]  \\
&= \mathbb{E}\left[\left(\sum_{i=1}^t e_i\right) \left(\sum_{j=1}^{t+h} e_j\right)\right]  \\
&= \mathbb{E}\left[\sum_{i=1}^t \sum_{j=1}^{t+h} e_i  e_j\right]  \\
&= \sum_{i=1}^t \mathbb{VAR}\left[e_i\right] + h \cdot 0 \\
&= t \\
\end{split}
$$

$$
\begin{split}
\mathbb{COR}\left[W_t, W_{s}\right]
&= \frac{\mathbb{COR}\left[W_t, W_{s}\right] } {\sqrt{\mathbb{VAR}\left[ W_{s}\right]\mathbb{VAR}\left[ W_{t}\right] }} \quad \text{with } t > s \\
&= \frac{t}{\sqrt{t s} }  \\
&= \frac{\sqrt{t }}{\sqrt{s} }  \\
\end{split}
$$

### log normal distribution
- A [[random variable]] $X$ is [[log normal distribution|log normal distributed]] if the [[logarithm]] of $X$ $Y=log(X) \sim f_Y\left(y|\mu, \sigma^2\right)$ is [[normal distribution|normal distributed]]


```functionplot
---
title: 
xLabel: 
yLabel: 
bounds: [-2, 4, 0, 0.7]
disableZoom: true
grid: true
---
f(x) = 1/x 1/sqrt(2*PI) exp(-log(x)^2 / 2)
g(x) = 1/sqrt(2*PI) exp(-x^2 / 2)
```

#### CDF
$$
F_X\left(x \: | \: \mu, \sigma^2\right) = 
F_Y\left(log(x) \: | \: \mu, \sigma^2\right)
$$
proof
$$
\begin{split}
F_X\left(x\: | \: \mu, \sigma^2\right) 
&= P\left(X \leq x\right)  \\
&= P\left(log(X) \leq log(x)\right) \qquad \text{(since log is monotone increasing)}\\
&= F_Y\left(log(X)\right) \\
&= F_Y\left(log(x) \: | \: \mu, \sigma^2\right)
\end{split}
$$

#### PDF
$$
f_X\left(x \: | \: \mu, \sigma^2\right) = 
\frac{1}{x} f_Y\left(log(x) \: | \: \mu, \sigma^2\right)
$$



proof

$$
\begin{split}
f_X\left(x \: | \: \mu, \sigma^2\right) 
&= \frac{dF_X\left(x \: | \: \mu, \sigma^2\right)}{dy} \\ 
&= \frac{dF_Y\left(log(x) \: | \: \mu, \sigma^2\right)}{dy} \\ 
&= \frac{dlog(x)}{dy} f_Y\left(log(x) \: | \: \mu, \sigma^2\right)  \\ 
&= \frac{1}{x} f_Y\left(log(x) \: | \: \mu, \sigma^2\right)  \\ 


\end{split}
$$



Tags: mathematics time_series WS2425
<!--ID: 1735149315384-->
END