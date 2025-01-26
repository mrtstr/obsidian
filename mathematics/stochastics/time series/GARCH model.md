## GARCH model
- for modeling the conditional volatility based on historical returns, capturing the time-varying nature of volatility
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
&= \mathbb{E}\left[\sigma_t^2 \right] \\
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
- for every [[white noise]] there always exists a [[stationary process#weakly stationary process|weakly stationary]] solution that describes it if and only if the following is true and the solution is unique for a given $p$ and $q$

$$
\sum_{i=1}^{p} a_i  + \sum_{j=1}^{q} b_j < 1
$$
- in this case the [[variance]] is as follows

$$
\mathbb{VAR}[X_t] = \mathbb{E}[X_t^2] = \mathbb{E}[\sigma_t^2] = \frac{a_0}{1-\sum_{i=1}^{p} a_i  - \sum_{j=1}^{q} b_j }
$$
- the given condition is not necessary for the existence of a strict stationary solution but in this case the [[variance]] does not exist and we have the following

$$
\mathbb{VAR}[X_t] = \mathbb{E}[X_t^2] = \mathbb{E}[\sigma_t^2] = \infty
$$

### uniqueness of GARCH solutions
- given a weak stationary solution of a GARCH(p, q) model with $a_0>0$
- the solution is unique for the given $p$ and $q$ but there can be another GARCH $\tilde p$ $\tilde q$ model with the same solution
- for example the two GARCH models describe the same [[time series]]

$$
\begin{split}
\sigma_{t}^2 
&=\frac{3}{4} + \frac{1}{3}X_{t-1}^2 + \frac{1}{2} \sigma_{t-1}^2 \\
&=\frac{3}{4} + \frac{1}{3}X_{t-1}^2 + \frac{1}{6} \sigma_{t-1}^2 + \frac{2}{6} \sigma_{t-1}^2 \\
&=\frac{3}{4} + \frac{1}{3}X_{t-1}^2 + \frac{1}{6} \sigma_{t-1}^2 + \frac{1}{3} \left(\frac{3}{4} + \frac{1}{3}X_{t-2}^2 + \frac{1}{2} \sigma_{t-2}^2\right) \\
&=\frac{3}{4} + \frac{1}{3}X_{t-1}^2 + \frac{1}{6} \sigma_{t-1}^2 + \frac{1}{4} + \frac{1}{9}X_{t-2}^2 + \frac{1}{6} \sigma_{t-2}^2 \\
&=1 + \frac{1}{3}X_{t-1}^2 + \frac{1}{9}X_{t-2}^2 + \frac{1}{6} \sigma_{t-1}^2 + \frac{1}{6} \sigma_{t-2}^2 \\
\sigma_{t}^2 
&=1 + \frac{1}{3}X_{t-1}^2 + \frac{1}{9}X_{t-2}^2 + \frac{1}{6} \sigma_{t-1}^2 + \frac{1}{6} \sigma_{t-2}^2 \\
\end{split}
$$

- if a GARCH model that satisfies the following conditions its [[time series]] is identifiable which means there is no other GARCH model that describes the same [[time series]] that satisfies both conditions
1) $\mathcal{L}\left(e_1^2\right)$  does not have a one point distribution
2) $A(z)=\sum_{i=1}^p a_i z^i$ and $B(z)=\sum_{i=1}^q b_i z^i$ don't have the same roots (nullstellen)

- in the example the first example does satisfy the conditions but the second does not so they don't violate the theorem
## GARCH(1,1) model
- $e_t \sim (0,1)$ i.i.d
- $a_i, b_j \geq 0$ and $a_p, b_q \neq 0$
$$
\begin{split}
 X_t&= \sigma_t \cdot e_t \\
\sigma^2_t &= a_0 +  a X_{t-1}^2 +  b \sigma^2_{t-1}
\end{split}
$$


### stationary solution
if the GARCH(1,1) model has a solution ($\neq \infty, -\infty$) it looks like the following and is unique

$$
\sigma_t^2 = a_0 \left(1 + \sum_{j=1}^k \prod_{i=1}^j \left(a\cdot e_{t-i}^2 +  b \right)\right)
$$
- with certain conditions the rest term $\sigma_{t-k-1}^2 \prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)$ converges to zero

$$
\begin{split}
\sigma^2_t 
&= a_0 + a X_{t-1}^2 +  b \sigma^2_{t-1} \\
&= a_0 + \sigma_{t-1}^2 \left(a\cdot e_{t-1}^2 +  b \right)  \\
&= a_0 + \left(a_0 + \sigma_{t-2}^2 \left(a\cdot e_{t-2}^2 +  b \right)\right) \left(a\cdot e_{t-1}^2 +  b \right)  \\
&= a_0 + a_0 \left(a\cdot e_{t-1}^2 +  b \right) + \sigma_{t-2}^2 \left(a\cdot e_{t-2}^2 +  b \right)\left(a\cdot e_{t-1}^2 +  b \right)  \\
&= a_0 \left(1 + \sum_{j=1}^k \prod_{i=1}^j \left(a\cdot e_{t-i}^2 +  b \right)\right) + \sigma_{t-k-1}^2 \prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)
\end{split}
$$
#### strict stationary solution
- the [[GARCH model]] has a unique and strictly stationary solutions if and only if $\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0$
- the factor of the rest term $\sigma_{t-k-1}^2 \prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)$ goes to zero if and only if $\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0$ because otherwise $\prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)$ would go to infinity 
$$
\begin{split}
\ln\left(\prod_{i=1}^n\left(a \cdot e_{t-i}^2 + b \right)\right) 
&= \sum_{i=1}^n \ln\left(a \cdot e_{t-i}^2 + b \right) \\
&= n \ln\left(a \cdot e_{1}^2 + b \right) \\
\end{split}
$$
- to show the [[estimator convergence]] it is enough to show that its [[expectation]] and [[variance]] are [[convergence in probability|converging in probability]] against zero (as a consequence of the [[chebyshev markov inequality]])
$$
\begin{split}
\mathbb{E}\left[\prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right) \right] 
&= \mathbb{E}\left[\exp\ln\prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right) \right]  \\
&= \mathbb{E}\left[\exp\left(n \ln\left(a \cdot e_{1}^2 + b \right)\right) \right] \xrightarrow{\text{condition}} 0 \\
\end{split}
$$

- with $\mathbb{E}[\ln(a \cdot e_1^2 + b)] = 0$ the rest term does not converge too (no proof)

#### weak stationary solution
- if $a_0>0$ and $a,b\geq0$ and $a+b < 1$ then the GARCH(1,1) model has a weak stationary solution 
- the is because $a + b < 1$ implies the condition for strong stationary 

$$
 a + b < 1 \Rightarrow \mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0
$$

$$
\begin{split}
&\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0 \\
\Leftrightarrow &\mathbb{E}[\exp\ln(a \cdot e_1^2 + b)] < 1 \\
\Leftrightarrow &\mathbb{E}[a \cdot e_1^2 + b] =a+b < 1 \\
\end{split}
$$

- $a + b < 1$ also implies that the [[variance]] $\mathbb{VAR}\left[X_t\right]=\frac{a_0}{1-(a+b)}$ does exist 
- from strong stationary plus the existence of the [[variance]] follows weak stationary

##### variance
- for a weak stationary solution of the GARCH model the [[variance]] is as follows
- it is easy to see that the [[variance]] does not exist if $a + b \geq 1$

$$
\begin{split}
\mathbb{VAR}\left[X_t\right]
&= \mathbb{E}\left[\sigma_t^2\right] \\
&= \mathbb{E}\left[X_t^2\right]\\
&= \mathbb{E}\left[a_0 +  a X_{t-1}^2 +  b \sigma^2_{t-1}  \right] \\
&= \mathbb{E}\left[a_0 +  a \sigma_{t-1}^2 e_{t-1}^2 +  b \sigma^2_{t-1}  \right] \\
&= a_0 +  a \mathbb{E}\left[ \sigma_{t-1}^2\right] \mathbb{E}\left[e_{t-1}^2 \right]+  b \mathbb{E}\left[ \sigma^2_{t-1}  \right] \\
&= a_0 +  a \mathbb{E}\left[ \sigma_{t-1}^2\right] +  b \mathbb{E}\left[ \sigma^2_{t-1}  \right] \\
&= a_0 +  (a+b) \mathbb{E}\left[ \sigma_{t-1}^2\right]  \\
&= a_0 +  (a+b) \mathbb{E}\left[ \sigma_{t}^2\right]  \\
&= \frac{a_0}{1-(a+b)}    \\
\end{split}
$$

##### strong but not weak stationary solution
- if $\sigma^2_t$ is measurable with respect to $\mathcal{F_{t-1}}$ that the conditions for weak and strong stationary imply each other and 

$$
\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0 \Leftrightarrow a + b < 1
$$

$$
\begin{split}
\mathbb{E}\left[ X_t^2\right] 
&= \mathbb{E}\left[ \sigma_t^2 \cdot e_t^2\right] \\
&= \mathbb{E}\left[ \mathbb{E}\left[ \sigma_t^2 \cdot e_t^2 | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \mathbb{E}\left[ e_t^2 | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \mathbb{E}\left[ e_t^2 \right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \right] \\
&= \mathbb{E}\left[a_0 + a X_{t-1}^2 +  b \sigma^2_{t-1}\right] \\
&= a_0 +a \mathbb{E}\left[  X_{t-1}^2 \right] + b \mathbb{E}\left[\sigma^2_{t-1}\right] \\
&= a_0 +(a+b) \mathbb{E}\left[  X_{t-1}^2 \right]  \\
\Rightarrow \mathbb{E}\left[ X_t^2\right]& \left(1 - (a+b)\right) = a_0 > 0 \\
\Rightarrow a + b > &0
\end{split}
$$

- this means a strong but not weak stationary solution can only exist if $\sigma^2_t$ is not measurable with respect to $\mathcal{F_{t-1}}$ 
- then only the condition for a strong but not weak stationary solution is true

$$
\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0 \land a + b \geq 1
$$

- then the [[variance]] $\mathbb{E}\left[X_t^2\right]=\infty$ does exist because if it would exist strong stationary would imply weak stationary
- for example for ARCH(1) $\mathbb{E}[\ln ae_1^2]<0 \rightarrow a<3.56$ which is much weaker than $a < 1$

### GARCH(0, q)
- GARCH(0, q) does not make sense because it would lead to a constant $\sigma^2_t$ which would make the process a [[white noise#i.i.d white noise|i.i.d white noise]]

$$
\begin{split}
 X_t&= \sigma_t \cdot e_t \\
\sigma^2_t 
&= a_0 +  \sum_{j=1}^{q} b_j \sigma^2_{t-j} \\
&= \frac{a_0}{1 - \sum_{j=1}^{q} b_j } \\
\end{split}
$$

## GARCH parameter estimation
- the parameters of the GARCH model can be estimated with the quasi [[maximum likelihood estimator|maximum likelihood]] method
- assume there is a [[probability density function (PDF)]] $f\left(X_n, ..., X_1\right)$ and split it up in a product of conditional PDFs

$$
\begin{split}
f\left(X_n, ..., X_1\right)
&=\prod_{t=1}^n f\left(X_t | X_{t-1}, ..., X_{t-p},\sigma_{t}, ..., \sigma_{t-q} \right) \\
\end{split}
$$
- since $\sigma_t$ is measurable given $X_{t-1}$ and $\sigma_t$ it only depends on the [[white noise]] $e_t \sim (0,1)$ that is NOT [[normal distribution|normal distributed]]
$$
\begin{split}
F_X(x) 
&= P(X_t < x) \\
&= P(\sigma_t e_t < x) \\
&= P\left( e_t < \frac{x}{\sigma_t}\right) \\
&= F_e\left( \frac{X_t}{\sigma_t}\right) \\
\\
f\left(X_t | X_{t-1}, ..., X_{t-p},\sigma_{t}, ..., \sigma_{t-q} \right)
&= f_X(X_t) \\
&= \frac{d}{dx} F_e\left( \frac{X_t}{\sigma_t}\right) \\
&= \frac{1}{\sigma_t} f_e\left( \frac{X_t}{\sigma_t}\right) \\
\end{split}
$$

- as a result we have the following for the [[probability density function (PDF)]]
$$
\begin{split}
f\left(X_n, ..., X_1\right)
&=\prod_{t=1}^n\frac{1}{\sigma_t} f_e\left( \frac{X_t}{\sigma_t}\right) \\
\end{split}
$$
- for the next step we assume that $e_t \sim \mathcal{N}(0,1)$ 
# ---------------
![[estimator convergence#estimator convergence]]

![[stationary process#stationary process]]

![[non-parametric volatility model#the base model]]

![[non-parametric volatility model#time dependent volatility model]]

# anki

START
Basic
GARCH(1,1) model summary
- definition
- solution
- when does it have a strict stationary solution
- when does it have a weak stationary solution
- do they imply each other?
- are the solutions unique?

Back: 
## GARCH(1,1) model
- $e_t \sim (0,1)$ i.i.d
- $a_i, b_j \geq 0$ and $a_p, b_q \neq 0$
$$
\begin{split}
 X_t&= \sigma_t \cdot e_t \\
\sigma^2_t &= a_0 +  a X_{t-1}^2 +  b \sigma^2_{t-1}
\end{split}
$$

### stationary solution
if the GARCH(1,1) model has a solution ($\neq \infty, -\infty$) it looks like the following and is unique

$$
\sigma_t^2 = a_0 \left(1 + \sum_{j=1}^k \prod_{i=1}^j \left(a\cdot e_{t-i}^2 +  b \right)\right)
$$
- with certain conditions the rest term $\sigma_{t-k-1}^2 \prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)$ converges to zero

$$
\begin{split}
\sigma^2_t 
&= a_0 + a X_{t-1}^2 +  b \sigma^2_{t-1} \\
&= a_0 + \sigma_{t-1}^2 \left(a\cdot e_{t-1}^2 +  b \right)  \\
&= a_0 + \left(a_0 + \sigma_{t-2}^2 \left(a\cdot e_{t-2}^2 +  b \right)\right) \left(a\cdot e_{t-1}^2 +  b \right)  \\
&= a_0 + a_0 \left(a\cdot e_{t-1}^2 +  b \right) + \sigma_{t-2}^2 \left(a\cdot e_{t-2}^2 +  b \right)\left(a\cdot e_{t-1}^2 +  b \right)  \\
&= a_0 \left(1 + \sum_{j=1}^k \prod_{i=1}^j \left(a\cdot e_{t-i}^2 +  b \right)\right) + \sigma_{t-k-1}^2 \prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)
\end{split}
$$
#### strict stationary solution
- the [[GARCH model]] has a unique and strictly stationary solutions if and only if $\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0$
- the factor of the rest term $\sigma_{t-k-1}^2 \prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)$ goes to zero if and only if $\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0$ because otherwise $\prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)$ would go to infinity 
$$
\begin{split}
\ln\left(\prod_{i=1}^n\left(a \cdot e_{t-i}^2 + b \right)\right) 
&= \sum_{i=1}^n \ln\left(a \cdot e_{t-i}^2 + b \right) \\
&= n \ln\left(a \cdot e_{1}^2 + b \right) \\
\end{split}
$$

- to show the [[estimator convergence]] it is enough to show that its [[expectation]] and [[variance]] are [[convergence in probability|converging in probability]] against zero (as a consequence of the [[chebyshev markov inequality]])

$$
\begin{split}
\mathbb{E}\left[\prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right) \right] 
&= \mathbb{E}\left[\exp\ln\prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right) \right]  \\
&= \mathbb{E}\left[\exp\left(n \ln\left(a \cdot e_{1}^2 + b \right)\right) \right] \xrightarrow{\text{condition}} 0 \\
\end{split}
$$

- with $\mathbb{E}[\ln(a \cdot e_1^2 + b)] = 0$ the rest term does not converge too (no proof)

#### weak stationary solution
- if $a_0>0$ and $a,b\geq0$ and $a+b < 1$ then the GARCH(1,1) model has a weak stationary solution 
- the is because $a + b < 1$ implies the condition for strong stationary 

$$
 a + b < 1 \Rightarrow \mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0
$$

$$
\begin{split}
&\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0 \\
\Leftrightarrow &\mathbb{E}[\exp\ln(a \cdot e_1^2 + b)] < 1 \\
\Leftrightarrow &\mathbb{E}[a \cdot e_1^2 + b] =a+b < 1 \\
\end{split}
$$

- $a + b < 1$ also implies that the [[variance]] $\mathbb{VAR}\left[X_t\right]=\frac{a_0}{1-(a+b)}$ does exist 
- from strong stationary plus the existence of the [[variance]] follows weak stationary

##### variance
- for a weak stationary solution of the GARCH model the [[variance]] is as follows
- it is easy to see that the [[variance]] does not exist if $a + b \geq 1$

$$
\begin{split}
\mathbb{VAR}\left[X_t\right]
&= \mathbb{E}\left[\sigma_t^2\right] \\
&= \mathbb{E}\left[X_t^2\right]\\
&= \mathbb{E}\left[a_0 +  a X_{t-1}^2 +  b \sigma^2_{t-1}  \right] \\
&= \mathbb{E}\left[a_0 +  a \sigma_{t-1}^2 e_{t-1}^2 +  b \sigma^2_{t-1}  \right] \\
&= a_0 +  a \mathbb{E}\left[ \sigma_{t-1}^2\right] \mathbb{E}\left[e_{t-1}^2 \right]+  b \mathbb{E}\left[ \sigma^2_{t-1}  \right] \\
&= a_0 +  a \mathbb{E}\left[ \sigma_{t-1}^2\right] +  b \mathbb{E}\left[ \sigma^2_{t-1}  \right] \\
&= a_0 +  (a+b) \mathbb{E}\left[ \sigma_{t-1}^2\right]  \\
&= a_0 +  (a+b) \mathbb{E}\left[ \sigma_{t}^2\right]  \\
&= \frac{a_0}{1-(a+b)}    \\
\end{split}
$$

##### strong but not weak stationary solution
- if $\sigma^2_t$ is measurable with respect to $\mathcal{F_{t-1}}$ that the conditions for weak and strong stationary imply each other and 

$$
\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0 \Leftrightarrow a + b < 1
$$

$$
\begin{split}
\mathbb{E}\left[ X_t^2\right] 
&= \mathbb{E}\left[ \sigma_t^2 \cdot e_t^2\right] \\
&= \mathbb{E}\left[ \mathbb{E}\left[ \sigma_t^2 \cdot e_t^2 | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \mathbb{E}\left[ e_t^2 | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \mathbb{E}\left[ e_t^2 \right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \right] \\
&= \mathbb{E}\left[a_0 + a X_{t-1}^2 +  b \sigma^2_{t-1}\right] \\
&= a_0 +a \mathbb{E}\left[  X_{t-1}^2 \right] + b \mathbb{E}\left[\sigma^2_{t-1}\right] \\
&= a_0 +(a+b) \mathbb{E}\left[  X_{t-1}^2 \right]  \\
\Rightarrow \mathbb{E}\left[ X_t^2\right]& \left(1 - (a+b)\right) = a_0 > 0 \\
\Rightarrow a + b > &0
\end{split}
$$

- this means a strong but not weak stationary solution can only exist if $\sigma^2_t$ is not measurable with respect to $\mathcal{F_{t-1}}$ 
- then only the condition for a strong but not weak stationary solution is true

$$
\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0 \land a + b \geq 1
$$

- then the [[variance]] $\mathbb{E}\left[X_t^2\right]=\infty$ does exist because if it would exist strong stationary would imply weak stationary
- for example for ARCH(1) $\mathbb{E}[\ln ae_1^2]<0 \rightarrow a<3.56$ which is much weaker than $a < 1$

### uniqueness of GARCH solutions
- given a weak stationary solution of a GARCH(p, q) model with $a_0>0$
- the solution is unique for the given $p$ and $q$ but there can be another GARCH $\tilde p$ $\tilde q$ model with the same solution
- for example the two GARCH models describe the same [[time series]]

$$
\begin{split}
\sigma_{t}^2 
&=\frac{3}{4} + \frac{1}{3}X_{t-1}^2 + \frac{1}{2} \sigma_{t-1}^2 \\
&=\frac{3}{4} + \frac{1}{3}X_{t-1}^2 + \frac{1}{6} \sigma_{t-1}^2 + \frac{2}{6} \sigma_{t-1}^2 \\
&=\frac{3}{4} + \frac{1}{3}X_{t-1}^2 + \frac{1}{6} \sigma_{t-1}^2 + \frac{1}{3} \left(\frac{3}{4} + \frac{1}{3}X_{t-2}^2 + \frac{1}{2} \sigma_{t-2}^2\right) \\
&=\frac{3}{4} + \frac{1}{3}X_{t-1}^2 + \frac{1}{6} \sigma_{t-1}^2 + \frac{1}{4} + \frac{1}{9}X_{t-2}^2 + \frac{1}{6} \sigma_{t-2}^2 \\
&=1 + \frac{1}{3}X_{t-1}^2 + \frac{1}{9}X_{t-2}^2 + \frac{1}{6} \sigma_{t-1}^2 + \frac{1}{6} \sigma_{t-2}^2 \\
\sigma_{t}^2 
&=1 + \frac{1}{3}X_{t-1}^2 + \frac{1}{9}X_{t-2}^2 + \frac{1}{6} \sigma_{t-1}^2 + \frac{1}{6} \sigma_{t-2}^2 \\
\end{split}
$$

- if a GARCH model that satisfies the following conditions its [[time series]] is identifiable which means there is no other GARCH model that describes the same [[time series]] that satisfies both conditions
1) $\mathcal{L}\left(e_1^2\right)$  does not have a one point distribution
2) $A(z)=\sum_{i=1}^p a_i z^i$ and $B(z)=\sum_{i=1}^q b_i z^i$ don't have the same roots (nullstellen)

- in the example the first example does satisfy the conditions but the second does not so they don't violate the theorem

________________

### stationary process
- not every strong stationary process is weak stationary because the [[variance]] might not exist
- every strong stationary process with existing [[moments]] is also weak stationary

- weak stationary does not imply strong stationary because just because the first moments are time invariant does not guarantee that the [[distribution]] is time invariant 
#### strongly stationary process
- a [[stochastic process]] whose [[joint distribution]] is not time-dependent
- given a [[stationary process]] $\{X_t\}$ and an arbitray [[set]] of time instances ${t_1, ..., t_n}$ the [[joint distribution|joint distributions]] of the [[random variable|random variables]] $X(t_1), ..., X(t_n)$ is the same as the [[joint distribution|joint distributions]] of the [[random variable|random variables]] $X(t_1+\tau), ..., X(t_n+\tau)$ 

$$
\begin{split}
F_X(x_1, ..., x_n) = F_X(x_1 + \tau, ..., x_n + \tau) \quad 
\forall \tau, t_1, ... , t_n \in \mathbb{R} \\
f_X(x_1, ..., x_n) = f_X(x_1 + \tau, ..., x_n + \tau) \quad 
\forall \tau, t_1, ... , t_n \in \mathbb{R} 
\end{split}
$$

#### weakly stationary process
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- the [[variance]] $\mathbb{VAR}\left[X_t\right]< \infty$ has to be finite

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
- for every [[white noise]] there always exists a [[stationary process#weakly stationary process|weakly stationary]] solution that describes it if and only if the following is true and the solution is unique for a given $p$ and $q$

$$
\sum_{i=1}^{p} a_i  + \sum_{j=1}^{q} b_j < 1
$$
- in this case the [[variance]] is as follows

$$
\mathbb{VAR}[X_t] = \mathbb{E}[X_t^2] = \mathbb{E}[\sigma_t^2] = \frac{a_0}{1-\sum_{i=1}^{p} a_i  - \sum_{j=1}^{q} b_j }
$$
- the given condition is not necessary for the existence of a strict stationary solution but in this case the [[variance]] does not exist and we have the following

$$
\mathbb{VAR}[X_t] = \mathbb{E}[X_t^2] = \mathbb{E}[\sigma_t^2] = \infty
$$


Tags: mathematics time_series WS2425
<!--ID: 1737556427966-->
END

START
Basic
GARCH(1,1) model
- solution with proof but no convergence proof
- is the solution unique?
Back: 

## GARCH(1,1) model
- $e_t \sim (0,1)$ i.i.d
- $a_i, b_j \geq 0$ and $a_p, b_q \neq 0$
$$
\begin{split}
 X_t&= \sigma_t \cdot e_t \\
\sigma^2_t &= a_0 +  a X_{t-1}^2 +  b \sigma^2_{t-1}
\end{split}
$$

### stationary solution
if the GARCH(1,1) model has a solution ($\neq \infty, -\infty$) it looks like the following and is unique

$$
\sigma_t^2 = a_0 \left(1 + \sum_{j=1}^k \prod_{i=1}^j \left(a\cdot e_{t-i}^2 +  b \right)\right)
$$
- with certain conditions the rest term $\sigma_{t-k-1}^2 \prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)$ converges to zero

$$
\begin{split}
\sigma^2_t 
&= a_0 + a X_{t-1}^2 +  b \sigma^2_{t-1} \\
&= a_0 + \sigma_{t-1}^2 \left(a\cdot e_{t-1}^2 +  b \right)  \\
&= a_0 + \left(a_0 + \sigma_{t-2}^2 \left(a\cdot e_{t-2}^2 +  b \right)\right) \left(a\cdot e_{t-1}^2 +  b \right)  \\
&= a_0 + a_0 \left(a\cdot e_{t-1}^2 +  b \right) + \sigma_{t-2}^2 \left(a\cdot e_{t-2}^2 +  b \right)\left(a\cdot e_{t-1}^2 +  b \right)  \\
&= a_0 \left(1 + \sum_{j=1}^k \prod_{i=1}^j \left(a\cdot e_{t-i}^2 +  b \right)\right) + \sigma_{t-k-1}^2 \prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)
\end{split}
$$
#### strict stationary solution
- the [[GARCH model]] has a unique and strictly stationary solutions if and only if $\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0$
- the factor of the rest term $\sigma_{t-k-1}^2 \prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)$ goes to zero if and only if $\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0$ because otherwise $\prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)$ would go to infinity 
$$
\begin{split}
\ln\left(\prod_{i=1}^n\left(a \cdot e_{t-i}^2 + b \right)\right) 
&= \sum_{i=1}^n \ln\left(a \cdot e_{t-i}^2 + b \right) \\
&= n \ln\left(a \cdot e_{1}^2 + b \right) \\
\end{split}
$$

- to show the [[estimator convergence]] it is enough to show that its [[expectation]] and [[variance]] are [[convergence in probability|converging in probability]] against zero (as a consequence of the [[chebyshev markov inequality]])

$$
\begin{split}
\mathbb{E}\left[\prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right) \right] 
&= \mathbb{E}\left[\exp\ln\prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right) \right]  \\
&= \mathbb{E}\left[\exp\left(n \ln\left(a \cdot e_{1}^2 + b \right)\right) \right] \xrightarrow{\text{condition}} 0 \\
\end{split}
$$

- with $\mathbb{E}[\ln(a \cdot e_1^2 + b)] = 0$ the rest term does not converge too (no proof)

#### weak stationary solution
- if $a_0>0$ and $a,b\geq0$ and $a+b < 1$ then the GARCH(1,1) model has a weak stationary solution 
- the is because $a + b < 1$ implies the condition for strong stationary 

$$
 a + b < 1 \Rightarrow \mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0
$$

$$
\begin{split}
&\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0 \\
\Leftrightarrow &\mathbb{E}[\exp\ln(a \cdot e_1^2 + b)] < 1 \\
\Leftrightarrow &\mathbb{E}[a \cdot e_1^2 + b] =a+b < 1 \\
\end{split}
$$

- $a + b < 1$ also implies that the [[variance]] $\mathbb{VAR}\left[X_t\right]=\frac{a_0}{1-(a+b)}$ does exist 
- from strong stationary plus the existence of the [[variance]] follows weak stationary


##### variance
- for a weak stationary solution of the GARCH model the [[variance]] is as follows
- it is easy to see that the [[variance]] does not exist if $a + b \geq 1$

$$
\begin{split}
\mathbb{VAR}\left[X_t\right]
&= \mathbb{E}\left[\sigma_t^2\right] \\
&= \mathbb{E}\left[X_t^2\right]\\
&= \mathbb{E}\left[a_0 +  a X_{t-1}^2 +  b \sigma^2_{t-1}  \right] \\
&= \mathbb{E}\left[a_0 +  a \sigma_{t-1}^2 e_{t-1}^2 +  b \sigma^2_{t-1}  \right] \\
&= a_0 +  a \mathbb{E}\left[ \sigma_{t-1}^2\right] \mathbb{E}\left[e_{t-1}^2 \right]+  b \mathbb{E}\left[ \sigma^2_{t-1}  \right] \\
&= a_0 +  a \mathbb{E}\left[ \sigma_{t-1}^2\right] +  b \mathbb{E}\left[ \sigma^2_{t-1}  \right] \\
&= a_0 +  (a+b) \mathbb{E}\left[ \sigma_{t-1}^2\right]  \\
&= a_0 +  (a+b) \mathbb{E}\left[ \sigma_{t}^2\right]  \\
&= \frac{a_0}{1-(a+b)}    \\
\end{split}
$$

##### strong but not weak stationary solution
- if $\sigma^2_t$ is measurable with respect to $\mathcal{F_{t-1}}$ that the conditions for weak and strong stationary imply each other and 

$$
\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0 \Leftrightarrow a + b < 1
$$

$$
\begin{split}
\mathbb{E}\left[ X_t^2\right] 
&= \mathbb{E}\left[ \sigma_t^2 \cdot e_t^2\right] \\
&= \mathbb{E}\left[ \mathbb{E}\left[ \sigma_t^2 \cdot e_t^2 | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \mathbb{E}\left[ e_t^2 | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \mathbb{E}\left[ e_t^2 \right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \right] \\
&= \mathbb{E}\left[a_0 + a X_{t-1}^2 +  b \sigma^2_{t-1}\right] \\
&= a_0 +a \mathbb{E}\left[  X_{t-1}^2 \right] + b \mathbb{E}\left[\sigma^2_{t-1}\right] \\
&= a_0 +(a+b) \mathbb{E}\left[  X_{t-1}^2 \right]  \\
\Rightarrow \mathbb{E}\left[ X_t^2\right]& \left(1 - (a+b)\right) = a_0 > 0 \\
\Rightarrow a + b > &0
\end{split}
$$

- this means a strong but not weak stationary solution can only exist if $\sigma^2_t$ is not measurable with respect to $\mathcal{F_{t-1}}$ 
- then only the condition for a strong but not weak stationary solution is true

$$
\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0 \land a + b \geq 1
$$

- then the [[variance]] $\mathbb{E}\left[X_t^2\right]=\infty$ does exist because if it would exist strong stationary would imply weak stationary
- for example for ARCH(1) $\mathbb{E}[\ln ae_1^2]<0 \rightarrow a<3.56$ which is much weaker than $a < 1$

________________
### stationary process
- not every strong stationary process is weak stationary because the [[variance]] might not exist
- every strong stationary process with existing [[moments]] is also weak stationary

- weak stationary does not imply strong stationary because just because the first moments are time invariant does not guarantee that the [[distribution]] is time invariant 
#### strongly stationary process
- a [[stochastic process]] whose [[joint distribution]] is not time-dependent
- given a [[stationary process]] $\{X_t\}$ and an arbitray [[set]] of time instances ${t_1, ..., t_n}$ the [[joint distribution|joint distributions]] of the [[random variable|random variables]] $X(t_1), ..., X(t_n)$ is the same as the [[joint distribution|joint distributions]] of the [[random variable|random variables]] $X(t_1+\tau), ..., X(t_n+\tau)$ 

$$
\begin{split}
F_X(x_1, ..., x_n) = F_X(x_1 + \tau, ..., x_n + \tau) \quad 
\forall \tau, t_1, ... , t_n \in \mathbb{R} \\
f_X(x_1, ..., x_n) = f_X(x_1 + \tau, ..., x_n + \tau) \quad 
\forall \tau, t_1, ... , t_n \in \mathbb{R} 
\end{split}
$$

#### weakly stationary process
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- the [[variance]] $\mathbb{VAR}\left[X_t\right]< \infty$ has to be finite

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
- for every [[white noise]] there always exists a [[stationary process#weakly stationary process|weakly stationary]] solution that describes it if and only if the following is true and the solution is unique for a given $p$ and $q$

$$
\sum_{i=1}^{p} a_i  + \sum_{j=1}^{q} b_j < 1
$$
- in this case the [[variance]] is as follows

$$
\mathbb{VAR}[X_t] = \mathbb{E}[X_t^2] = \mathbb{E}[\sigma_t^2] = \frac{a_0}{1-\sum_{i=1}^{p} a_i  - \sum_{j=1}^{q} b_j }
$$
- the given condition is not necessary for the existence of a strict stationary solution but in this case the [[variance]] does not exist and we have the following

$$
\mathbb{VAR}[X_t] = \mathbb{E}[X_t^2] = \mathbb{E}[\sigma_t^2] = \infty
$$


Tags: mathematics time_series WS2425
<!--ID: 1737556427969-->
END


START
Basic
GARCH(1,1) model
- solution without proof
- minimal condition for convergence with proof
- is the solution unique

Back: 
## GARCH(1,1) model
- $e_t \sim (0,1)$ i.i.d
- $a_i, b_j \geq 0$ and $a_p, b_q \neq 0$
$$
\begin{split}
 X_t&= \sigma_t \cdot e_t \\
\sigma^2_t &= a_0 +  a X_{t-1}^2 +  b \sigma^2_{t-1}
\end{split}
$$

### stationary solution
if the GARCH(1,1) model has a solution ($\neq \infty, -\infty$) it looks like the following and is unique

$$
\sigma_t^2 = a_0 \left(1 + \sum_{j=1}^k \prod_{i=1}^j \left(a\cdot e_{t-i}^2 +  b \right)\right)
$$
- with certain conditions the rest term $\sigma_{t-k-1}^2 \prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)$ converges to zero

$$
\begin{split}
\sigma^2_t 
&= a_0 + a X_{t-1}^2 +  b \sigma^2_{t-1} \\
&= a_0 + \sigma_{t-1}^2 \left(a\cdot e_{t-1}^2 +  b \right)  \\
&= a_0 + \left(a_0 + \sigma_{t-2}^2 \left(a\cdot e_{t-2}^2 +  b \right)\right) \left(a\cdot e_{t-1}^2 +  b \right)  \\
&= a_0 + a_0 \left(a\cdot e_{t-1}^2 +  b \right) + \sigma_{t-2}^2 \left(a\cdot e_{t-2}^2 +  b \right)\left(a\cdot e_{t-1}^2 +  b \right)  \\
&= a_0 \left(1 + \sum_{j=1}^k \prod_{i=1}^j \left(a\cdot e_{t-i}^2 +  b \right)\right) + \sigma_{t-k-1}^2 \prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)
\end{split}
$$
#### strict stationary solution
- the [[GARCH model]] has a unique and strictly stationary solutions if and only if $\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0$
- the factor of the rest term $\sigma_{t-k-1}^2 \prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)$ goes to zero if and only if $\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0$ because otherwise $\prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)$ would go to infinity 
$$
\begin{split}
\ln\left(\prod_{i=1}^n\left(a \cdot e_{t-i}^2 + b \right)\right) 
&= \sum_{i=1}^n \ln\left(a \cdot e_{t-i}^2 + b \right) \\
&= n \ln\left(a \cdot e_{1}^2 + b \right) \\
\end{split}
$$

- to show the [[estimator convergence]] it is enough to show that its [[expectation]] and [[variance]] are [[convergence in probability|converging in probability]] against zero (as a consequence of the [[chebyshev markov inequality]])

$$
\begin{split}
\mathbb{E}\left[\prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right) \right] 
&= \mathbb{E}\left[\exp\ln\prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right) \right]  \\
&= \mathbb{E}\left[\exp\left(n \ln\left(a \cdot e_{1}^2 + b \right)\right) \right] \xrightarrow{\text{condition}} 0 \\
\end{split}
$$

- with $\mathbb{E}[\ln(a \cdot e_1^2 + b)] = 0$ the rest term does not converge too (no proof)

#### weak stationary solution
- if $a_0>0$ and $a,b\geq0$ and $a+b < 1$ then the GARCH(1,1) model has a weak stationary solution 
- the is because $a + b < 1$ implies the condition for strong stationary 

$$
 a + b < 1 \Rightarrow \mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0
$$

$$
\begin{split}
&\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0 \\
\Leftrightarrow &\mathbb{E}[\exp\ln(a \cdot e_1^2 + b)] < 1 \\
\Leftrightarrow &\mathbb{E}[a \cdot e_1^2 + b] =a+b < 1 \\
\end{split}
$$

- $a + b < 1$ also implies that the [[variance]] $\mathbb{VAR}\left[X_t\right]=\frac{a_0}{1-(a+b)}$ does exist 
- from strong stationary plus the existence of the [[variance]] follows weak stationary


##### variance
- for a weak stationary solution of the GARCH model the [[variance]] is as follows
- it is easy to see that the [[variance]] does not exist if $a + b \geq 1$

$$
\begin{split}
\mathbb{VAR}\left[X_t\right]
&= \mathbb{E}\left[\sigma_t^2\right] \\
&= \mathbb{E}\left[X_t^2\right]\\
&= \mathbb{E}\left[a_0 +  a X_{t-1}^2 +  b \sigma^2_{t-1}  \right] \\
&= \mathbb{E}\left[a_0 +  a \sigma_{t-1}^2 e_{t-1}^2 +  b \sigma^2_{t-1}  \right] \\
&= a_0 +  a \mathbb{E}\left[ \sigma_{t-1}^2\right] \mathbb{E}\left[e_{t-1}^2 \right]+  b \mathbb{E}\left[ \sigma^2_{t-1}  \right] \\
&= a_0 +  a \mathbb{E}\left[ \sigma_{t-1}^2\right] +  b \mathbb{E}\left[ \sigma^2_{t-1}  \right] \\
&= a_0 +  (a+b) \mathbb{E}\left[ \sigma_{t-1}^2\right]  \\
&= a_0 +  (a+b) \mathbb{E}\left[ \sigma_{t}^2\right]  \\
&= \frac{a_0}{1-(a+b)}    \\
\end{split}
$$

##### strong but not weak stationary solution
- if $\sigma^2_t$ is measurable with respect to $\mathcal{F_{t-1}}$ that the conditions for weak and strong stationary imply each other and 

$$
\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0 \Leftrightarrow a + b < 1
$$

$$
\begin{split}
\mathbb{E}\left[ X_t^2\right] 
&= \mathbb{E}\left[ \sigma_t^2 \cdot e_t^2\right] \\
&= \mathbb{E}\left[ \mathbb{E}\left[ \sigma_t^2 \cdot e_t^2 | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \mathbb{E}\left[ e_t^2 | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \mathbb{E}\left[ e_t^2 \right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \right] \\
&= \mathbb{E}\left[a_0 + a X_{t-1}^2 +  b \sigma^2_{t-1}\right] \\
&= a_0 +a \mathbb{E}\left[  X_{t-1}^2 \right] + b \mathbb{E}\left[\sigma^2_{t-1}\right] \\
&= a_0 +(a+b) \mathbb{E}\left[  X_{t-1}^2 \right]  \\
\Rightarrow \mathbb{E}\left[ X_t^2\right]& \left(1 - (a+b)\right) = a_0 > 0 \\
\Rightarrow a + b > &0
\end{split}
$$

- this means a strong but not weak stationary solution can only exist if $\sigma^2_t$ is not measurable with respect to $\mathcal{F_{t-1}}$ 
- then only the condition for a strong but not weak stationary solution is true

$$
\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0 \land a + b \geq 1
$$

- then the [[variance]] $\mathbb{E}\left[X_t^2\right]=\infty$ does exist because if it would exist strong stationary would imply weak stationary
- for example for ARCH(1) $\mathbb{E}[\ln ae_1^2]<0 \rightarrow a<3.56$ which is much weaker than $a < 1$

________________

### estimator convergence
- give a [[statistical estimator]] $X_n$ and with en [[expectation]] that [[convergence in probability|converges in probability]] against $\mu$ and a [[variance]] that converges against zero i.e. $\mathbb{E}[X_n] \xrightarrow{\mathbb{P}} \mu$ and $\mathbb{VAR}[X_n] \xrightarrow{\mathbb{P}} 0$ 
- then $X_n \xrightarrow{\mathbb{P}} \mu$ also converges against $\mu$

#### proof
$$
\begin{split}
\mathbb{P}\left(|X_n-\mu| > \epsilon\right) 
&\leq \frac{\mathbb{E}\left[(X_n-\mu)^2\right]}{\epsilon^2}  \\
&\leq \frac{\mathbb{VAR}[X_n]}{\epsilon^2} \xrightarrow{n \to \infty} 0 \\
\end{split}
$$

### stationary process
- not every strong stationary process is weak stationary because the [[variance]] might not exist
- every strong stationary process with existing [[moments]] is also weak stationary

- weak stationary does not imply strong stationary because just because the first moments are time invariant does not guarantee that the [[distribution]] is time invariant 
#### strongly stationary process
- a [[stochastic process]] whose [[joint distribution]] is not time-dependent
- given a [[stationary process]] $\{X_t\}$ and an arbitray [[set]] of time instances ${t_1, ..., t_n}$ the [[joint distribution|joint distributions]] of the [[random variable|random variables]] $X(t_1), ..., X(t_n)$ is the same as the [[joint distribution|joint distributions]] of the [[random variable|random variables]] $X(t_1+\tau), ..., X(t_n+\tau)$ 

$$
\begin{split}
F_X(x_1, ..., x_n) = F_X(x_1 + \tau, ..., x_n + \tau) \quad 
\forall \tau, t_1, ... , t_n \in \mathbb{R} \\
f_X(x_1, ..., x_n) = f_X(x_1 + \tau, ..., x_n + \tau) \quad 
\forall \tau, t_1, ... , t_n \in \mathbb{R} 
\end{split}
$$

#### weakly stationary process
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- the [[variance]] $\mathbb{VAR}\left[X_t\right]< \infty$ has to be finite

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
- for every [[white noise]] there always exists a [[stationary process#weakly stationary process|weakly stationary]] solution that describes it if and only if the following is true and the solution is unique for a given $p$ and $q$

$$
\sum_{i=1}^{p} a_i  + \sum_{j=1}^{q} b_j < 1
$$
- in this case the [[variance]] is as follows

$$
\mathbb{VAR}[X_t] = \mathbb{E}[X_t^2] = \mathbb{E}[\sigma_t^2] = \frac{a_0}{1-\sum_{i=1}^{p} a_i  - \sum_{j=1}^{q} b_j }
$$
- the given condition is not necessary for the existence of a strict stationary solution but in this case the [[variance]] does not exist and we have the following

$$
\mathbb{VAR}[X_t] = \mathbb{E}[X_t^2] = \mathbb{E}[\sigma_t^2] = \infty
$$


Tags: mathematics time_series WS2425
<!--ID: 1737556427972-->
END


START
Basic
GARCH(1,1) model
- solution without proof
- condition for weak stationary with proof

Back: 


## GARCH(1,1) model
- $e_t \sim (0,1)$ i.i.d
- $a_i, b_j \geq 0$ and $a_p, b_q \neq 0$
$$
\begin{split}
 X_t&= \sigma_t \cdot e_t \\
\sigma^2_t &= a_0 +  a X_{t-1}^2 +  b \sigma^2_{t-1}
\end{split}
$$

### stationary solution
if the GARCH(1,1) model has a solution ($\neq \infty, -\infty$) it looks like the following and is unique

$$
\sigma_t^2 = a_0 \left(1 + \sum_{j=1}^k \prod_{i=1}^j \left(a\cdot e_{t-i}^2 +  b \right)\right)
$$
- with certain conditions the rest term $\sigma_{t-k-1}^2 \prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)$ converges to zero

$$
\begin{split}
\sigma^2_t 
&= a_0 + a X_{t-1}^2 +  b \sigma^2_{t-1} \\
&= a_0 + \sigma_{t-1}^2 \left(a\cdot e_{t-1}^2 +  b \right)  \\
&= a_0 + \left(a_0 + \sigma_{t-2}^2 \left(a\cdot e_{t-2}^2 +  b \right)\right) \left(a\cdot e_{t-1}^2 +  b \right)  \\
&= a_0 + a_0 \left(a\cdot e_{t-1}^2 +  b \right) + \sigma_{t-2}^2 \left(a\cdot e_{t-2}^2 +  b \right)\left(a\cdot e_{t-1}^2 +  b \right)  \\
&= a_0 \left(1 + \sum_{j=1}^k \prod_{i=1}^j \left(a\cdot e_{t-i}^2 +  b \right)\right) + \sigma_{t-k-1}^2 \prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)
\end{split}
$$
#### strict stationary solution
- the [[GARCH model]] has a unique and strictly stationary solutions if and only if $\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0$
- the factor of the rest term $\sigma_{t-k-1}^2 \prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)$ goes to zero if and only if $\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0$ because otherwise $\prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)$ would go to infinity 
$$
\begin{split}
\ln\left(\prod_{i=1}^n\left(a \cdot e_{t-i}^2 + b \right)\right) 
&= \sum_{i=1}^n \ln\left(a \cdot e_{t-i}^2 + b \right) \\
&= n \ln\left(a \cdot e_{1}^2 + b \right) \\
\end{split}
$$

- to show the [[estimator convergence]] it is enough to show that its [[expectation]] and [[variance]] are [[convergence in probability|converging in probability]] against zero (as a consequence of the [[chebyshev markov inequality]])

$$
\begin{split}
\mathbb{E}\left[\prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right) \right] 
&= \mathbb{E}\left[\exp\ln\prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right) \right]  \\
&= \mathbb{E}\left[\exp\left(n \ln\left(a \cdot e_{1}^2 + b \right)\right) \right] \xrightarrow{\text{condition}} 0 \\
\end{split}
$$

- with $\mathbb{E}[\ln(a \cdot e_1^2 + b)] = 0$ the rest term does not converge too (no proof)

#### weak stationary solution
- if $a_0>0$ and $a,b\geq0$ and $a+b < 1$ then the GARCH(1,1) model has a weak stationary solution 
- the is because $a + b < 1$ implies the condition for strong stationary 

$$
 a + b < 1 \Rightarrow \mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0
$$

$$
\begin{split}
&\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0 \\
\Leftrightarrow &\mathbb{E}[\exp\ln(a \cdot e_1^2 + b)] < 1 \\
\Leftrightarrow &\mathbb{E}[a \cdot e_1^2 + b] =a+b < 1 \\
\end{split}
$$

- $a + b < 1$ also implies that the [[variance]] $\mathbb{VAR}\left[X_t\right]=\frac{a_0}{1-(a+b)}$ does exist 
- from strong stationary plus the existence of the [[variance]] follows weak stationary


##### variance
- for a weak stationary solution of the GARCH model the [[variance]] is as follows
- it is easy to see that the [[variance]] does not exist if $a + b \geq 1$

$$
\begin{split}
\mathbb{VAR}\left[X_t\right]
&= \mathbb{E}\left[\sigma_t^2\right] \\
&= \mathbb{E}\left[X_t^2\right]\\
&= \mathbb{E}\left[a_0 +  a X_{t-1}^2 +  b \sigma^2_{t-1}  \right] \\
&= \mathbb{E}\left[a_0 +  a \sigma_{t-1}^2 e_{t-1}^2 +  b \sigma^2_{t-1}  \right] \\
&= a_0 +  a \mathbb{E}\left[ \sigma_{t-1}^2\right] \mathbb{E}\left[e_{t-1}^2 \right]+  b \mathbb{E}\left[ \sigma^2_{t-1}  \right] \\
&= a_0 +  a \mathbb{E}\left[ \sigma_{t-1}^2\right] +  b \mathbb{E}\left[ \sigma^2_{t-1}  \right] \\
&= a_0 +  (a+b) \mathbb{E}\left[ \sigma_{t-1}^2\right]  \\
&= a_0 +  (a+b) \mathbb{E}\left[ \sigma_{t}^2\right]  \\
&= \frac{a_0}{1-(a+b)}    \\
\end{split}
$$

##### strong but not weak stationary solution
- if $\sigma^2_t$ is measurable with respect to $\mathcal{F_{t-1}}$ that the conditions for weak and strong stationary imply each other and 

$$
\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0 \Leftrightarrow a + b < 1
$$

$$
\begin{split}
\mathbb{E}\left[ X_t^2\right] 
&= \mathbb{E}\left[ \sigma_t^2 \cdot e_t^2\right] \\
&= \mathbb{E}\left[ \mathbb{E}\left[ \sigma_t^2 \cdot e_t^2 | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \mathbb{E}\left[ e_t^2 | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \mathbb{E}\left[ e_t^2 \right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \right] \\
&= \mathbb{E}\left[a_0 + a X_{t-1}^2 +  b \sigma^2_{t-1}\right] \\
&= a_0 +a \mathbb{E}\left[  X_{t-1}^2 \right] + b \mathbb{E}\left[\sigma^2_{t-1}\right] \\
&= a_0 +(a+b) \mathbb{E}\left[  X_{t-1}^2 \right]  \\
\Rightarrow \mathbb{E}\left[ X_t^2\right]& \left(1 - (a+b)\right) = a_0 > 0 \\
\Rightarrow a + b > &0
\end{split}
$$

- this means a strong but not weak stationary solution can only exist if $\sigma^2_t$ is not measurable with respect to $\mathcal{F_{t-1}}$ 
- then only the condition for a strong but not weak stationary solution is true

$$
\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0 \land a + b \geq 1
$$

- then the [[variance]] $\mathbb{E}\left[X_t^2\right]=\infty$ does exist because if it would exist strong stationary would imply weak stationary
- for example for ARCH(1) $\mathbb{E}[\ln ae_1^2]<0 \rightarrow a<3.56$ which is much weaker than $a < 1$
________________

### stationary process
- not every strong stationary process is weak stationary because the [[variance]] might not exist
- every strong stationary process with existing [[moments]] is also weak stationary

- weak stationary does not imply strong stationary because just because the first moments are time invariant does not guarantee that the [[distribution]] is time invariant 
#### strongly stationary process
- a [[stochastic process]] whose [[joint distribution]] is not time-dependent
- given a [[stationary process]] $\{X_t\}$ and an arbitray [[set]] of time instances ${t_1, ..., t_n}$ the [[joint distribution|joint distributions]] of the [[random variable|random variables]] $X(t_1), ..., X(t_n)$ is the same as the [[joint distribution|joint distributions]] of the [[random variable|random variables]] $X(t_1+\tau), ..., X(t_n+\tau)$ 

$$
\begin{split}
F_X(x_1, ..., x_n) = F_X(x_1 + \tau, ..., x_n + \tau) \quad 
\forall \tau, t_1, ... , t_n \in \mathbb{R} \\
f_X(x_1, ..., x_n) = f_X(x_1 + \tau, ..., x_n + \tau) \quad 
\forall \tau, t_1, ... , t_n \in \mathbb{R} 
\end{split}
$$

#### weakly stationary process
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- the [[variance]] $\mathbb{VAR}\left[X_t\right]< \infty$ has to be finite

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
- for every [[white noise]] there always exists a [[stationary process#weakly stationary process|weakly stationary]] solution that describes it if and only if the following is true and the solution is unique for a given $p$ and $q$

$$
\sum_{i=1}^{p} a_i  + \sum_{j=1}^{q} b_j < 1
$$
- in this case the [[variance]] is as follows

$$
\mathbb{VAR}[X_t] = \mathbb{E}[X_t^2] = \mathbb{E}[\sigma_t^2] = \frac{a_0}{1-\sum_{i=1}^{p} a_i  - \sum_{j=1}^{q} b_j }
$$
- the given condition is not necessary for the existence of a strict stationary solution but in this case the [[variance]] does not exist and we have the following

$$
\mathbb{VAR}[X_t] = \mathbb{E}[X_t^2] = \mathbb{E}[\sigma_t^2] = \infty
$$


Tags: mathematics time_series WS2425
<!--ID: 1737556427974-->
END

START
Basic
GARCH(1,1) model
- can a solution be weak stationery but not strong stationary or the other way around?
Back: 
## GARCH(1,1) model
- $e_t \sim (0,1)$ i.i.d
- $a_i, b_j \geq 0$ and $a_p, b_q \neq 0$
$$
\begin{split}
 X_t&= \sigma_t \cdot e_t \\
\sigma^2_t &= a_0 +  a X_{t-1}^2 +  b \sigma^2_{t-1}
\end{split}
$$

### stationary solution
if the GARCH(1,1) model has a solution ($\neq \infty, -\infty$) it looks like the following and is unique

$$
\sigma_t^2 = a_0 \left(1 + \sum_{j=1}^k \prod_{i=1}^j \left(a\cdot e_{t-i}^2 +  b \right)\right)
$$
- with certain conditions the rest term $\sigma_{t-k-1}^2 \prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)$ converges to zero

$$
\begin{split}
\sigma^2_t 
&= a_0 + a X_{t-1}^2 +  b \sigma^2_{t-1} \\
&= a_0 + \sigma_{t-1}^2 \left(a\cdot e_{t-1}^2 +  b \right)  \\
&= a_0 + \left(a_0 + \sigma_{t-2}^2 \left(a\cdot e_{t-2}^2 +  b \right)\right) \left(a\cdot e_{t-1}^2 +  b \right)  \\
&= a_0 + a_0 \left(a\cdot e_{t-1}^2 +  b \right) + \sigma_{t-2}^2 \left(a\cdot e_{t-2}^2 +  b \right)\left(a\cdot e_{t-1}^2 +  b \right)  \\
&= a_0 \left(1 + \sum_{j=1}^k \prod_{i=1}^j \left(a\cdot e_{t-i}^2 +  b \right)\right) + \sigma_{t-k-1}^2 \prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)
\end{split}
$$
#### strict stationary solution
- the [[GARCH model]] has a unique and strictly stationary solutions if and only if $\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0$
- the factor of the rest term $\sigma_{t-k-1}^2 \prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)$ goes to zero if and only if $\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0$ because otherwise $\prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right)$ would go to infinity 
$$
\begin{split}
\ln\left(\prod_{i=1}^n\left(a \cdot e_{t-i}^2 + b \right)\right) 
&= \sum_{i=1}^n \ln\left(a \cdot e_{t-i}^2 + b \right) \\
&= n \ln\left(a \cdot e_{1}^2 + b \right) \\
\end{split}
$$

- to show the [[estimator convergence]] it is enough to show that its [[expectation]] and [[variance]] are [[convergence in probability|converging in probability]] against zero (as a consequence of the [[chebyshev markov inequality]])

$$
\begin{split}
\mathbb{E}\left[\prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right) \right] 
&= \mathbb{E}\left[\exp\ln\prod_{i=1}^{k+1}  \left(a\cdot e_{t-i}^2 +  b \right) \right]  \\
&= \mathbb{E}\left[\exp\left(n \ln\left(a \cdot e_{1}^2 + b \right)\right) \right] \xrightarrow{\text{condition}} 0 \\
\end{split}
$$

- with $\mathbb{E}[\ln(a \cdot e_1^2 + b)] = 0$ the rest term does not converge too (no proof)

#### weak stationary solution
- if $a_0>0$ and $a,b\geq0$ and $a+b < 1$ then the GARCH(1,1) model has a weak stationary solution 
- the is because $a + b < 1$ implies the condition for strong stationary 

$$
 a + b < 1 \Rightarrow \mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0
$$

$$
\begin{split}
&\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0 \\
\Leftrightarrow &\mathbb{E}[\exp\ln(a \cdot e_1^2 + b)] < 1 \\
\Leftrightarrow &\mathbb{E}[a \cdot e_1^2 + b] =a+b < 1 \\
\end{split}
$$

- $a + b < 1$ also implies that the [[variance]] $\mathbb{VAR}\left[X_t\right]=\frac{a_0}{1-(a+b)}$ does exist 
- from strong stationary plus the existence of the [[variance]] follows weak stationary


##### variance
- for a weak stationary solution of the GARCH model the [[variance]] is as follows
- it is easy to see that the [[variance]] does not exist if $a + b \geq 1$

$$
\begin{split}
\mathbb{VAR}\left[X_t\right]
&= \mathbb{E}\left[\sigma_t^2\right] \\
&= \mathbb{E}\left[X_t^2\right]\\
&= \mathbb{E}\left[a_0 +  a X_{t-1}^2 +  b \sigma^2_{t-1}  \right] \\
&= \mathbb{E}\left[a_0 +  a \sigma_{t-1}^2 e_{t-1}^2 +  b \sigma^2_{t-1}  \right] \\
&= a_0 +  a \mathbb{E}\left[ \sigma_{t-1}^2\right] \mathbb{E}\left[e_{t-1}^2 \right]+  b \mathbb{E}\left[ \sigma^2_{t-1}  \right] \\
&= a_0 +  a \mathbb{E}\left[ \sigma_{t-1}^2\right] +  b \mathbb{E}\left[ \sigma^2_{t-1}  \right] \\
&= a_0 +  (a+b) \mathbb{E}\left[ \sigma_{t-1}^2\right]  \\
&= a_0 +  (a+b) \mathbb{E}\left[ \sigma_{t}^2\right]  \\
&= \frac{a_0}{1-(a+b)}    \\
\end{split}
$$

##### strong but not weak stationary solution
- if $\sigma^2_t$ is measurable with respect to $\mathcal{F_{t-1}}$ that the conditions for weak and strong stationary imply each other and 

$$
\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0 \Leftrightarrow a + b < 1
$$

$$
\begin{split}
\mathbb{E}\left[ X_t^2\right] 
&= \mathbb{E}\left[ \sigma_t^2 \cdot e_t^2\right] \\
&= \mathbb{E}\left[ \mathbb{E}\left[ \sigma_t^2 \cdot e_t^2 | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \mathbb{E}\left[ e_t^2 | \mathcal{F}_{t-1}\right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \mathbb{E}\left[ e_t^2 \right]\right] \\
&= \mathbb{E}\left[\sigma_t^2 \right] \\
&= \mathbb{E}\left[a_0 + a X_{t-1}^2 +  b \sigma^2_{t-1}\right] \\
&= a_0 +a \mathbb{E}\left[  X_{t-1}^2 \right] + b \mathbb{E}\left[\sigma^2_{t-1}\right] \\
&= a_0 +(a+b) \mathbb{E}\left[  X_{t-1}^2 \right]  \\
\Rightarrow \mathbb{E}\left[ X_t^2\right]& \left(1 - (a+b)\right) = a_0 > 0 \\
\Rightarrow a + b > &0
\end{split}
$$

- this means a strong but not weak stationary solution can only exist if $\sigma^2_t$ is not measurable with respect to $\mathcal{F_{t-1}}$ 
- then only the condition for a strong but not weak stationary solution is true

$$
\mathbb{E}[\ln(a \cdot e_1^2 + b)] < 0 \land a + b \geq 1
$$

- then the [[variance]] $\mathbb{E}\left[X_t^2\right]=\infty$ does exist because if it would exist strong stationary would imply weak stationary
- for example for ARCH(1) $\mathbb{E}[\ln ae_1^2]<0 \rightarrow a<3.56$ which is much weaker than $a < 1$
### stationary process
- not every strong stationary process is weak stationary because the [[variance]] might not exist
- every strong stationary process with existing [[moments]] is also weak stationary

- weak stationary does not imply strong stationary because just because the first moments are time invariant does not guarantee that the [[distribution]] is time invariant 
#### strongly stationary process
- a [[stochastic process]] whose [[joint distribution]] is not time-dependent
- given a [[stationary process]] $\{X_t\}$ and an arbitray [[set]] of time instances ${t_1, ..., t_n}$ the [[joint distribution|joint distributions]] of the [[random variable|random variables]] $X(t_1), ..., X(t_n)$ is the same as the [[joint distribution|joint distributions]] of the [[random variable|random variables]] $X(t_1+\tau), ..., X(t_n+\tau)$ 

$$
\begin{split}
F_X(x_1, ..., x_n) = F_X(x_1 + \tau, ..., x_n + \tau) \quad 
\forall \tau, t_1, ... , t_n \in \mathbb{R} \\
f_X(x_1, ..., x_n) = f_X(x_1 + \tau, ..., x_n + \tau) \quad 
\forall \tau, t_1, ... , t_n \in \mathbb{R} 
\end{split}
$$

#### weakly stationary process
- a [[stochastic process]] whose [[expectation]], [[variance]] and [[covariance]] are not time-dependent
- a [[stochastic process]] $\{X_t\}$ is weakly [[stationary process|stationary]] when $\mathbb{E}\left[X_t\right], \mathbb{VAR}\left[X_t\right], \mathbb{COVAR}\left[X_t, X_{t+h}\right]$ are time independent (the same for all $t$)
- the [[variance]] $\mathbb{VAR}\left[X_t\right]< \infty$ has to be finite


________________
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
- for every [[white noise]] there always exists a [[stationary process#weakly stationary process|weakly stationary]] solution that describes it if and only if the following is true and the solution is unique for a given $p$ and $q$

$$
\sum_{i=1}^{p} a_i  + \sum_{j=1}^{q} b_j < 1
$$
- in this case the [[variance]] is as follows

$$
\mathbb{VAR}[X_t] = \mathbb{E}[X_t^2] = \mathbb{E}[\sigma_t^2] = \frac{a_0}{1-\sum_{i=1}^{p} a_i  - \sum_{j=1}^{q} b_j }
$$
- the given condition is not necessary for the existence of a strict stationary solution but in this case the [[variance]] does not exist and we have the following

$$
\mathbb{VAR}[X_t] = \mathbb{E}[X_t^2] = \mathbb{E}[\sigma_t^2] = \infty
$$


Tags: mathematics time_series WS2425
<!--ID: 1737556427977-->
END


START
Basic
[[GARCH model]]
- when does a [[stationary process|stationary]] solution exist
- does there always exists a solution and is it unique?
- relationship weak vs strong stationary solutions
- what does it mean for the [[variance]]

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
- for every [[white noise]] there always exists a [[stationary process#weakly stationary process|weakly stationary]] solution that describes it if and only if the following is true and the solution is unique for a given $p$ and $q$

$$
\sum_{i=1}^{p} a_i  + \sum_{j=1}^{q} b_j < 1
$$
- in this case the [[variance]] is as follows

$$
\mathbb{VAR}[X_t] = \mathbb{E}[X_t^2] = \mathbb{E}[\sigma_t^2] = \frac{a_0}{1-\sum_{i=1}^{p} a_i  - \sum_{j=1}^{q} b_j }
$$
- the given condition is not necessary for the existence of a strict stationary solution but in this case the [[variance]] does not exist and we have the following

$$
\mathbb{VAR}[X_t] = \mathbb{E}[X_t^2] = \mathbb{E}[\sigma_t^2] = \infty
$$


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


START
Basic
[[GARCH model]] interpretation
- what does it?
- what can it be used for?

Back: 
## GARCH model
- for modeling the conditional volatility based on historical returns, capturing the time-varying nature of volatility
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

_____________

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
<!--ID: 1737734993473-->
END


START
Basic
[[GARCH model]]
- why does GARCH(0, q) don't make sense?

Back: 

### GARCH(0, q)
- GARCH(0, q) does not make sense because it would lead to a constant $\sigma^2_t$ which would make the process a [[white noise#i.i.d white noise|i.i.d white noise]]

$$
\begin{split}
 X_t&= \sigma_t \cdot e_t \\
\sigma^2_t 
&= a_0 +  \sum_{j=1}^{q} b_j \sigma^2_{t-j} \\
&= \frac{a_0}{1 - \sum_{j=1}^{q} b_j } \\
\end{split}
$$

## GARCH model
- for modeling the conditional volatility based on historical returns, capturing the time-varying nature of volatility
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


Tags: mathematics time_series WS2425
<!--ID: 1737832825893-->
END


START
Basic
[[GARCH model]]
- what can be said about the uniqueness of GARCH solutions

Back: 
### uniqueness of GARCH solutions
- given a weak stationary solution of a GARCH(p, q) model with $a_0>0$
- the solution is unique for the given $p$ and $q$ but there can be another GARCH $\tilde p$ $\tilde q$ model with the same solution
- for example the two GARCH models describe the same [[time series]]

$$
\begin{split}
\sigma_{t}^2 
&=\frac{3}{4} + \frac{1}{3}X_{t-1}^2 + \frac{1}{2} \sigma_{t-1}^2 \\
&=\frac{3}{4} + \frac{1}{3}X_{t-1}^2 + \frac{1}{6} \sigma_{t-1}^2 + \frac{2}{6} \sigma_{t-1}^2 \\
&=\frac{3}{4} + \frac{1}{3}X_{t-1}^2 + \frac{1}{6} \sigma_{t-1}^2 + \frac{1}{3} \left(\frac{3}{4} + \frac{1}{3}X_{t-2}^2 + \frac{1}{2} \sigma_{t-2}^2\right) \\
&=\frac{3}{4} + \frac{1}{3}X_{t-1}^2 + \frac{1}{6} \sigma_{t-1}^2 + \frac{1}{4} + \frac{1}{9}X_{t-2}^2 + \frac{1}{6} \sigma_{t-2}^2 \\
&=1 + \frac{1}{3}X_{t-1}^2 + \frac{1}{9}X_{t-2}^2 + \frac{1}{6} \sigma_{t-1}^2 + \frac{1}{6} \sigma_{t-2}^2 \\
\sigma_{t}^2 
&=1 + \frac{1}{3}X_{t-1}^2 + \frac{1}{9}X_{t-2}^2 + \frac{1}{6} \sigma_{t-1}^2 + \frac{1}{6} \sigma_{t-2}^2 \\
\end{split}
$$

- if a GARCH model that satisfies the following conditions its [[time series]] is identifiable which means there is no other GARCH model that describes the same [[time series]] that satisfies both conditions
1) $\mathcal{L}\left(e_1^2\right)$  does not have a one point distribution
2) $A(z)=\sum_{i=1}^p a_i z^i$ and $B(z)=\sum_{i=1}^q b_i z^i$ don't have the same roots (nullstellen)

- in the example the first example does satisfy the conditions but the second does not so they don't violate the theorem

## GARCH model
- for modeling the conditional volatility based on historical returns, capturing the time-varying nature of volatility
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


Tags: mathematics time_series WS2425
<!--ID: 1737832825898-->
END