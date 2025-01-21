### GARCH model
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

### the GARCH model is white noise
- the [[GARCH model]] is [[white noise]] but not [[stochastic independent]] [[white noise]] and thus also not identical distributed because then all moments like $X_t^2$ had to be independent which they are not

$$
\begin{split}
\mathbb{E}\left[ X_t\right] 
&= \mathbb{E}\left[ \sigma_t \cdot e_t\right] \\
&= \mathbb{E}\left[ \mathbb{E}\left[ \sigma_t \cdot e_t | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t \mathbb{E}\left[ e_t | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t \cdot 0\right] = 0\\
\end{split}
$$

$$
\begin{split}
\mathbb{VAR}\left[ X_t\right] 
&= \mathbb{E}\left[ X_t^2\right] \\
&= \mathbb{E}\left[ \sigma_t^2 \cdot e_t^2\right] \\
&= \mathbb{E}\left[ \mathbb{E}\left[ \sigma_t^2 \cdot e_t^2 | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \mathbb{E}\left[ e_t^2 | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \mathbb{E}\left[ e_t^2 \right]\right] \\
&= \mathbb{E}\left[\sigma_t \right] \\
\end{split}
$$


$$
\begin{split}
\mathbb{COV}\left[ X_t, X_{t+h}\right] 
&= \mathbb{E}\left[ X_t X_{t+h}\right] \\
&= \mathbb{E}\left[ \sigma_t e_t \sigma_{t+h}  e_{t+h}\right] \\
&= \mathbb{E}\left[ \mathbb{E}\left[ \sigma_t e_t \sigma_{t+h}  e_{t+h} | \mathcal{F}_{t+h-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t e_t \sigma_{t+h} \mathbb{E}\left[   e_{t+h} | \mathcal{F}_{t+h-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t e_t \sigma_{t+h} \mathbb{E}\left[   e_{t+h} \right]\right] = 0 \\
\end{split}
$$

### squared GARCH model is an ARMA model
- the squared [[GARCH model]] $X^2_t$ is similar to a [[autoregressive moving average (ARMA) model]] with $a_i'= a_i + b_i$ and $b_j'=b_j$ (assuming $a_i=0$ for $i>p$ and $b_j=0$ for $j>q$)
- this makes sense because we care using an [[autoregressive moving average (ARMA) model]] to model the [[variance]] which is closely related to $X^2_t$ 

$$
\begin{split}
\eta_t 
&= \sigma^2_t \left(e^2_t-1\right) \\
&= e^2_t \sigma^2_t - \sigma^2_t\\
&= X^2_t - \sigma^2_t\\
\Rightarrow \sigma^2_t  &= X^2_t - \eta_t 
\end{split}
$$

$$
\begin{split}
X^2_t 
&= \sigma^2_t e^2_t \\
&= \sigma^2_t e^2_t + \sigma^2_t - \sigma^2_t \\
&= \sigma^2_t + \underbrace{ \sigma^2_t \left(e^2_t-1\right)}_{\eta_t}  \\
&= a_0 + \sum_{i=1}^{p} a_i X^2_{t-i} + \sum_{j=1}^{q} b_i \sigma^2_{t-j} e^2_t + \eta_t\\
&= a_0 + \sum_{i=1}^{p} a_i X^2_{t-i} + \sum_{j=1}^{q} b_i \left( X^2_{t-j} - \eta_{t-j}\right) e^2_t + \eta_t\\
&= a_0 + \sum_{i=1}^{\max(p,q)} (a_i+b_i) X^2_{t-i} - \sum_{j=1}^{q} b_i \eta_{t-j}  e^2_t + \eta_t\\
\end{split}
$$

- $\eta_t = \sigma^2_t \left(e^2_t-1\right)$ is [[white noise]]

$$
\begin{split}
\mathbb{E}\left[\eta_t\right] 
&= \mathbb{E}\left[\mathbb{E}\left[\eta_t | \mathcal{F_{t-1}}\right]\right]  \\
&= \mathbb{E}\left[\mathbb{E}\left[\sigma^2_t \left(e^2_t-1\right) | \mathcal{F_{t-1}}\right]\right]  \\
&= \mathbb{E}\left[ \sigma^2_t \mathbb{E}\left[ \left(e^2_t-1\right) | \mathcal{F_{t-1}}\right]\right]  \\
&= \mathbb{E}\left[ \sigma^2_t \mathbb{E}\left[ e^2_t-1 \right]\right]  \\
&= \mathbb{E}\left[ \sigma^2_t \cdot 0\right] = 0 \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[\eta_t\eta_s\right] 
&= \mathbb{E}\left[\mathbb{E}\left[\eta_t \eta_s | \mathcal{F_{s-1}}\right]\right]  \\
&= \mathbb{E}\left[ \eta_t \mathbb{E}\left[ \eta_t | \mathcal{F_{t-1}}\right]\right]  \\
&= \mathbb{E}\left[ \eta_t \cdot 0\right] = 0 \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[\eta_t^2\right] 
&= \mathbb{E}\left[\sigma^4_t \left(e^2_t-1\right)^2 \right] \\
&= \mathbb{E}\left[\sigma^4_t \right]  \mathbb{E}\left[ e^4_t-1 \right] \\
\end{split}
$$
### existence and stationary of GARCH solutions
- for every [[white noise]] there always exists a [[stationary process#weakly stationary process|weakly stationary]] solution that describes it if and only if the following is true

$$
\sum_{i=1}^{p} a_i  + \sum_{j=1}^{q} b_j < 1
$$

- the solution is not unique

### GARCH(1,1) model
- $e_t \sim (0,1)$ i.i.d
- $a_i, b_j \geq 0$ and $a_p, b_q \neq 0$
$$
\begin{split}
 X_t&= \sigma_t \cdot e_t \\
\sigma^2_t &= a_0 +  a X_{t-1}^2 +  b \sigma^2_{t-1}
\end{split}
$$
- has a unique and strictly stationary solutions if and only if $\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0$

$$
\sigma_t^2 = a_0\left(1 + \sum_{j=1}^\infty \prod_{i=1}^\infty \left(a\cdot e^2_{t-1} + b\right)\right)
$$

# ---------------
![[non-parametric volatility model#the base model]]

![[non-parametric volatility model#time dependent volatility model]]

# anki

START
Basic
[[GARCH model]]
- when does a [[stationary process|stationary]] solution exist
- does there always exists a solution and is it unique?

Back: 
### GARCH model
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

### existence and stationary of GARCH solutions
- for every [[white noise]] there always exists a [[stationary process#weakly stationary process|weakly stationary]] solution that describes it if and only if the following is true

$$
\sum_{i=1}^{p} a_i  + \sum_{j=1}^{q} b_j < 1
$$

- the solution is not unique

Tags: mathematics time_series WS2425
<!--ID: 1737474478123-->
END

START
Basic
[[GARCH model]]
- proof that the  [[GARCH model]] $X_t$ is [[white noise]]
- is it [[stochastic independent]]
- is it i.i.d

Back: 
### GARCH model
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

### the GARCH model is white noise
- the [[GARCH model]] is [[white noise]] but not [[stochastic independent]] [[white noise]] and thus also not identical distributed because then all moments like $X_t^2$ had to be independent which they are not

$$
\begin{split}
\mathbb{E}\left[ X_t\right] 
&= \mathbb{E}\left[ \sigma_t \cdot e_t\right] \\
&= \mathbb{E}\left[ \mathbb{E}\left[ \sigma_t \cdot e_t | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t \mathbb{E}\left[ e_t | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t \cdot 0\right] = 0\\
\end{split}
$$

$$
\begin{split}
\mathbb{VAR}\left[ X_t\right] 
&= \mathbb{E}\left[ X_t^2\right] \\
&= \mathbb{E}\left[ \sigma_t^2 \cdot e_t^2\right] \\
&= \mathbb{E}\left[ \mathbb{E}\left[ \sigma_t^2 \cdot e_t^2 | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \mathbb{E}\left[ e_t^2 | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \mathbb{E}\left[ e_t^2 \right]\right] \\
&= \mathbb{E}\left[\sigma_t \right] \\
\end{split}
$$


$$
\begin{split}
\mathbb{COV}\left[ X_t, X_{t+h}\right] 
&= \mathbb{E}\left[ X_t X_{t+h}\right] \\
&= \mathbb{E}\left[ \sigma_t e_t \sigma_{t+h}  e_{t+h}\right] \\
&= \mathbb{E}\left[ \mathbb{E}\left[ \sigma_t e_t \sigma_{t+h}  e_{t+h} | \mathcal{F}_{t+h-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t e_t \sigma_{t+h} \mathbb{E}\left[   e_{t+h} | \mathcal{F}_{t+h-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t e_t \sigma_{t+h} \mathbb{E}\left[   e_{t+h} \right]\right] = 0 \\
\end{split}
$$


Tags: mathematics time_series WS2425
<!--ID: 1737474478126-->
END

START
Basic
[[GARCH model]]
- proof that the squared [[GARCH model]] $X^2_t$ is similar to a [[autoregressive moving average (ARMA) model]] 

Back: 
### GARCH model
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


### squared GARCH model is an ARMA model
- the squared [[GARCH model]] $X^2_t$ is similar to a [[autoregressive moving average (ARMA) model]] with $a_i'= a_i + b_i$ and $b_j'=b_j$ (assuming $a_i=0$ for $i>p$ and $b_j=0$ for $j>q$)
- this makes sense because we care using an [[autoregressive moving average (ARMA) model]] to model the [[variance]] which is closely related to $X^2_t$ 

$$
\begin{split}
\eta_t 
&= \sigma^2_t \left(e^2_t-1\right) \\
&= e^2_t \sigma^2_t - \sigma^2_t\\
&= X^2_t - \sigma^2_t\\
\Rightarrow \sigma^2_t  &= X^2_t - \eta_t 
\end{split}
$$

$$
\begin{split}
X^2_t 
&= \sigma^2_t e^2_t \\
&= \sigma^2_t e^2_t + \sigma^2_t - \sigma^2_t \\
&= \sigma^2_t + \underbrace{ \sigma^2_t \left(e^2_t-1\right)}_{\eta_t}  \\
&= a_0 + \sum_{i=1}^{p} a_i X^2_{t-i} + \sum_{j=1}^{q} b_i \sigma^2_{t-j} e^2_t + \eta_t\\
&= a_0 + \sum_{i=1}^{p} a_i X^2_{t-i} + \sum_{j=1}^{q} b_i \left( X^2_{t-j} - \eta_{t-j}\right) e^2_t + \eta_t\\
&= a_0 + \sum_{i=1}^{\max(p,q)} (a_i+b_i) X^2_{t-i} - \sum_{j=1}^{q} b_i \eta_{t-j}  e^2_t + \eta_t\\
\end{split}
$$

- $\eta_t = \sigma^2_t \left(e^2_t-1\right)$ is [[white noise]]

$$
\begin{split}
\mathbb{E}\left[\eta_t\right] 
&= \mathbb{E}\left[\mathbb{E}\left[\eta_t | \mathcal{F_{t-1}}\right]\right]  \\
&= \mathbb{E}\left[\mathbb{E}\left[\sigma^2_t \left(e^2_t-1\right) | \mathcal{F_{t-1}}\right]\right]  \\
&= \mathbb{E}\left[ \sigma^2_t \mathbb{E}\left[ \left(e^2_t-1\right) | \mathcal{F_{t-1}}\right]\right]  \\
&= \mathbb{E}\left[ \sigma^2_t \mathbb{E}\left[ e^2_t-1 \right]\right]  \\
&= \mathbb{E}\left[ \sigma^2_t \cdot 0\right] = 0 \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[\eta_t\eta_s\right] 
&= \mathbb{E}\left[\mathbb{E}\left[\eta_t \eta_s | \mathcal{F_{s-1}}\right]\right]  \\
&= \mathbb{E}\left[ \eta_t \mathbb{E}\left[ \eta_t | \mathcal{F_{t-1}}\right]\right]  \\
&= \mathbb{E}\left[ \eta_t \cdot 0\right] = 0 \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[\eta_t^2\right] 
&= \mathbb{E}\left[\sigma^4_t \left(e^2_t-1\right)^2 \right] \\
&= \mathbb{E}\left[\sigma^4_t \right]  \mathbb{E}\left[ e^4_t-1 \right] \\
\end{split}
$$

Tags: mathematics time_series WS2425
<!--ID: 1737474478129-->
END

START
Basic
[[GARCH model]] summary
- concept
- definition + assumptions
- properties of $X_t$ and $X_t^2$ without proof 
Back: 
### GARCH model
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

### the GARCH model is white noise
- the [[GARCH model]] is [[white noise]] but not [[stochastic independent]] [[white noise]] and thus also not identical distributed

$$
\begin{split}
\mathbb{E}\left[ X_t\right] 
&= \mathbb{E}\left[ \sigma_t \cdot e_t\right] \\
&= \mathbb{E}\left[ \mathbb{E}\left[ \sigma_t \cdot e_t | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t \mathbb{E}\left[ e_t | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t \cdot 0\right] = 0\\
\end{split}
$$

$$
\begin{split}
\mathbb{VAR}\left[ X_t\right] 
&= \mathbb{E}\left[ X_t^2\right] \\
&= \mathbb{E}\left[ \sigma_t^2 \cdot e_t^2\right] \\
&= \mathbb{E}\left[ \mathbb{E}\left[ \sigma_t^2 \cdot e_t^2 | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \mathbb{E}\left[ e_t^2 | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \mathbb{E}\left[ e_t^2 \right]\right] \\
&= \mathbb{E}\left[\sigma_t \right] \\
\end{split}
$$


$$
\begin{split}
\mathbb{COV}\left[ X_t, X_{t+h}\right] 
&= \mathbb{E}\left[ X_t X_{t+h}\right] \\
&= \mathbb{E}\left[ \sigma_t e_t \sigma_{t+h}  e_{t+h}\right] \\
&= \mathbb{E}\left[ \mathbb{E}\left[ \sigma_t e_t \sigma_{t+h}  e_{t+h} | \mathcal{F}_{t+h-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t e_t \sigma_{t+h} \mathbb{E}\left[   e_{t+h} | \mathcal{F}_{t+h-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t e_t \sigma_{t+h} \mathbb{E}\left[   e_{t+h} \right]\right] = 0 \\
\end{split}
$$

### squared GARCH model is an ARMA model
- the squared [[GARCH model]] $X^2_t$ is similar to a [[autoregressive moving average (ARMA) model]] with $a_i'= a_i + b_i$ and $b_j'=b_j$ (assuming $a_i=0$ for $i>p$ and $b_j=0$ for $j>q$)
- this makes sense because we care using an [[autoregressive moving average (ARMA) model]] to model the [[variance]] which is closely related to $X^2_t$ 

$$
\begin{split}
\eta_t 
&= \sigma^2_t \left(e^2_t-1\right) \\
&= e^2_t \sigma^2_t - \sigma^2_t\\
&= X^2_t - \sigma^2_t\\
\Rightarrow \sigma^2_t  &= X^2_t - \eta_t 
\end{split}
$$

$$
\begin{split}
X^2_t 
&= \sigma^2_t e^2_t \\
&= \sigma^2_t e^2_t + \sigma^2_t - \sigma^2_t \\
&= \sigma^2_t + \underbrace{ \sigma^2_t \left(e^2_t-1\right)}_{\eta_t}  \\
&= a_0 + \sum_{i=1}^{p} a_i X^2_{t-i} + \sum_{j=1}^{q} b_i \sigma^2_{t-j} e^2_t + \eta_t\\
&= a_0 + \sum_{i=1}^{p} a_i X^2_{t-i} + \sum_{j=1}^{q} b_i \left( X^2_{t-j} - \eta_{t-j}\right) e^2_t + \eta_t\\
&= a_0 + \sum_{i=1}^{\max(p,q)} (a_i+b_i) X^2_{t-i} - \sum_{j=1}^{q} b_i \eta_{t-j}  e^2_t + \eta_t\\
\end{split}
$$

- $\eta_t = \sigma^2_t \left(e^2_t-1\right)$ is [[white noise]]

$$
\begin{split}
\mathbb{E}\left[\eta_t\right] 
&= \mathbb{E}\left[\mathbb{E}\left[\eta_t | \mathcal{F_{t-1}}\right]\right]  \\
&= \mathbb{E}\left[\mathbb{E}\left[\sigma^2_t \left(e^2_t-1\right) | \mathcal{F_{t-1}}\right]\right]  \\
&= \mathbb{E}\left[ \sigma^2_t \mathbb{E}\left[ \left(e^2_t-1\right) | \mathcal{F_{t-1}}\right]\right]  \\
&= \mathbb{E}\left[ \sigma^2_t \mathbb{E}\left[ e^2_t-1 \right]\right]  \\
&= \mathbb{E}\left[ \sigma^2_t \cdot 0\right] = 0 \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[\eta_t\eta_s\right] 
&= \mathbb{E}\left[\mathbb{E}\left[\eta_t \eta_s | \mathcal{F_{s-1}}\right]\right]  \\
&= \mathbb{E}\left[ \eta_t \mathbb{E}\left[ \eta_t | \mathcal{F_{t-1}}\right]\right]  \\
&= \mathbb{E}\left[ \eta_t \cdot 0\right] = 0 \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[\eta_t^2\right] 
&= \mathbb{E}\left[\sigma^4_t \left(e^2_t-1\right)^2 \right] \\
&= \mathbb{E}\left[\sigma^4_t \right]  \mathbb{E}\left[ e^4_t-1 \right] \\
\end{split}
$$


_____________


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
## time dependent volatility  model

- assume $\alpha=0$ and is a function $\sigma:[0,1] \to [0, \infty)$ and $t=1,2,...,n$
- note: we don't assume that $e_t$ is [[normal distribution|normal distributed]]

$$
\begin{split}
X_{n,t} = \frac{\sigma\left(\frac{t}{n}\right)}{\sqrt{n}} \cdot e_t
\end{split}
$$

- instead of taking the [[mean]] of $X_{t,n}^2$ we try to estimate the function $\sigma$ by applying [[smoothing]] to the [[time series]] $X_{t,n}^2$ around the 


Tags: mathematics time_series WS2425
<!--ID: 1737448608369-->
END