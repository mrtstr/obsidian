### implied and realized volatility

#### implied volatility
- implied [[volatility]] is derived from option prices with the black scholes model (formula for options pricing based on [[geometric brownian motion (GBM)]]) based on current option prices 
- is forward-looking and is about market expectation of the [[volatility]] in the future

#### realized volatility
- realized [[volatility]] is the actual observed volatility in the past in a given period of time
- can be estimated with the following  [[non-parametric volatility model]]
$$
\begin{split}
X_{t,n} = \frac{\alpha\left(\frac{t}{n}\right)}{n} + \frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} e_t
\end{split}
$$

- continues as a function $\hat\sigma^2: [0,1] \to [0, \infty)$ of for a fixes time period with observations at time $0, t\frac{1}{n}, t\frac{2}{n}, t\frac{n}{n}$

$$
\begin{split}
\hat\sigma^2
&= \sum_{t=1}^n X_{t,n}^2 \xrightarrow{n \to \infty} \int_0^1\sigma^2(u) du \\
\hat\sigma^2(u)
&= \frac{1}{h}  \sum_{i=1}^{n} X_{t,n}^2 \cdot K\left(\frac{\frac{t}{n} - u}{h}\right)
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
- how can the RV be estimated (continuous vs for discrete intervals)
Back: 
### implied and realized volatility

#### implied volatility
- implied [[volatility]] is derived from option prices with the black scholes model (formula for options pricing based on [[geometric brownian motion (GBM)]]) based on current option prices 
- is forward-looking and is about market expectation of the [[volatility]] in the future

#### realized volatility
- realized [[volatility]] is the actual observed volatility in the past in a given period of time
- can be estimated with the following model
$$
\begin{split}
X_{t,n} = \frac{\alpha\left(\frac{t}{n}\right)}{n} + \frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} e_t
\end{split}
$$

- continues as a function $\hat\sigma^2: [0,1] \to [0, \infty)$ of for a fixes time period with observations at time $0, t\frac{1}{n}, t\frac{2}{n}, t\frac{n}{n}$

$$
\begin{split}
\hat\sigma^2
&= \sum_{t=1}^n X_{t,n}^2 \xrightarrow{n \to \infty} \int_0^1\sigma^2(u) du \\
\hat\sigma^2(u)
&= \frac{1}{h}  \sum_{i=1}^{n} X_{t,n}^2 \cdot K\left(\frac{\frac{t}{n} - u}{h}\right)
\end{split}
$$

________________

## time dependent volatility  model

- assume $\alpha=0$ and is a function $\sigma:[0,1] \to [0, \infty)$ and $t=1,2,...,n$
- note: we don't assume that $e_t$ is [[normal distribution|normal distributed]]

$$
\begin{split}
X_{n,t} = \frac{\alpha\left(\frac{t}{n}\right)}{n} + \frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} e_t = \frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} \cdot e_t
\end{split}
$$

- instead of taking the [[mean]] of $X_{t,n}^2$ we try to estimate the function $\sigma$ by applying [[smoothing]] to the [[time series]] $X_{t,n}^2$ around the 


#### weighted mean smoothing
- for example [[smoothing#rolling mean smoothing|rolling mean smoothing]] where the [[floor function]] $\lfloor un \rfloor \in \{0,..., n\}$ is used to map $u \in [0,1]$ to a number between zero and $n$ 

$$
\begin{split}
\hat\sigma^2(u)
&= \frac{1}{2q+1} \sum_{i=-q}^{q} X_{\lfloor un \rfloor-j,n}^2
\end{split}
$$

- if $\frac{q}{n}$ is sufficiently small $\frac{\lfloor un \rfloor}{n} \approx n$ and $\mathbb{E}[\hat\sigma^2(u)] \approx \sigma^2(u)$

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
### error for the kernel estimator
- given log returns $X_{t,n}$ with a [[differentiabe]] and bounded parameters that are functions $\sigma:[0,1] \to [0,\infty)$ and $\alpha:[0,1] \to \mathbb{R}$ and [[white noise]] $e_t \sim (0,1)$ with $\mathbb{E}[e_t^4]=\kappa < \infty$

$$
\begin{split}
X_{t,n} 
&= \frac{\alpha\left(\frac{t}{n}\right)}{n} +  \frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} e_t \\
\end{split}
$$
- the [[kernel smoothing for time series]] produces a estimator for the spot [[volatility]] with the following errors

$$
\begin{split}
\hat\sigma^2(u)
&= \sigma^2(u) + \mathcal{O}_P\left(\frac{1}{\sqrt{nh}}\right) + \mathcal{O}\left(h^2\right) \\
\end{split}
$$

#### bias
$$
\begin{split}
\mathbb{E}\left[\hat\sigma^2(u)\right] 
&= \sigma^2(u) + \mathcal{O}\left(h^2\right) + \mathcal{O}\left(\frac{1}{nh}\right)   \\
&= \frac{1}{h} \mathbb{E}\left[\sum_{t=1}^{n} X_{t,n}^2 \cdot K\left(\frac{\frac{t}{n} - u}{h}\right)\right] \\
&= \frac{1}{h} \mathbb{E}\left[\sum_{i=t}^{n} \left(\frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} \cdot e_t\right)^2 \cdot K\left(\frac{\frac{t}{n} - u}{h}\right)\right] \\
&= \frac{1}{hn} \sum_{t=1}^{n} \sigma\left(\frac{t}{n}\right)^2 \mathbb{E}\left[  \cdot e_t^2  \right] K\left(\frac{\frac{t}{n} - u}{h}\right) \\
&= \frac{1}{hn} \sum_{t=1}^{n} \sigma\left(\frac{t}{n}\right)^2  K\left(\frac{\frac{t}{n} - u}{h}\right) \\
&= \frac{1}{h} \int_0^1 \sigma\left(x\right)^2  K\left(\frac{x - u}{h}\right) dx + \mathcal{O}\left(\frac{1}{nh}\right)   \\
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