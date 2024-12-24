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
#### properties
1) $W_0 = 0$
2) $W_t$ has indenpendent increments thus $W_{t+h}-W_{t}$ is independent of $W_s: s < t$ 
3) the increments are [[normal distribution|normal distributed]] $W_{t+h}-W_t \sim \mathcal{N}(0, h)$
4) $W_t$ is a [[continuous function]] in $t$


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

# ---------

![[white noise#white noise]]
# Anki

START
Basic
[[wiener process]]
- definition
- base properties (4)
- [[expectation]], [[variance]], [[covariance]] and [[correlation]] (without proof)
Back: 

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
#### properties
1) $W_0 = 0$
2) $W_t$ has indenpendent increments thus $W_{t+h}-W_{t}$ is independent of $W_s: s < t$ 
3) the increments are [[normal distribution|normal distributed]] $W_{t+h}-W_t \sim \mathcal{N}(0, h)$
4) $W_t$ is a [[continuous function]] in $t$


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

___________

### white noise
[[time series]] $(e_t, t \in \mathbb{Z})$ with 
- i.i.d. values
- zero mean $\mathbb{E}[e_t] = 0$  
- constant and finite [[variance]] $\mathbb{VAR}[e_t] = \mathbb{E}[e_t^2]= \sigma^2 \in (0, \infty)$  
- [[correlation|uncorralated]] values $t \neq s \Rightarrow  \mathbb{COV}[e_t, e_s] = \mathbb{COR}[e_t, e_s] = 0$

#### gaussian white noise
- [[white noise]] with [[normal distribution|normal distributed]] values $e_t \sim \mathcal{N}(0, \sigma^2)$
### autocorrelation (ACF)
- [[correlation]] between two points of a [[time series]] / [[stochastic process]] is called [[autocorrelation (ACF)]]
- the [[autocorrelation (ACF)]] is a normalized [[autocovariance]]
- given a [[stochastic process]] $\{X_t\}$ the [[autocorrelation (ACF)]] $\rho_{XX}(t_1, t_2)$ for the time instances $t_1$ and $t_2$ is given as follows

$$
\begin{split}
\rho_{XX}(t_1, t_2) 
&= 
\frac{ K_{XX}(t_1, t_2)}{\sqrt{ \mathbb{VAR}\left[X_{t_1}\right]\mathbb{VAR}\left[X_{t_2}\right]}}\\ 
&= 
\frac{ \mathbb{COV}\left[X_{t_1}, X_{t_2}\right]}{\sqrt{ \mathbb{VAR}\left[X_{t_1}\right]\mathbb{VAR}\left[X_{t_2}\right]}}\\ 
&= 
\frac{ \mathbb{E}\left[X_{t_1}X_{t_2}\right] - \mathbb{E}\left[X_{t_1}\right]\mathbb{E}\left[X_{t_2}\right]}{\sqrt{ \mathbb{VAR}\left[X_{t_1}\right]\mathbb{VAR}\left[X_{t_2}\right]}}\\ 
\end{split}
$$


Tags: mathematics time_series WS2425

END


START
Basic
[[wiener process]]
- [[covariance]] (with proof)
- [[correlation]] (with proof)
Back: 

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
#### properties
1) $W_0 = 0$
2) $W_t$ has indenpendent increments thus $W_{t+h}-W_{t}$ is independent of $W_s: s < t$ 
3) the increments are [[normal distribution|normal distributed]] $W_{t+h}-W_t \sim \mathcal{N}(0, h)$
4) $W_t$ is a [[continuous function]] in $t$


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

______

### white noise
[[time series]] $(e_t, t \in \mathbb{Z})$ with 
- i.i.d. values
- zero mean $\mathbb{E}[e_t] = 0$  
- constant and finite [[variance]] $\mathbb{VAR}[e_t] = \mathbb{E}[e_t^2]= \sigma^2 \in (0, \infty)$  
- [[correlation|uncorralated]] values $t \neq s \Rightarrow  \mathbb{COV}[e_t, e_s] = \mathbb{COR}[e_t, e_s] = 0$

#### gaussian white noise
- [[white noise]] with [[normal distribution|normal distributed]] values $e_t \sim \mathcal{N}(0, \sigma^2)$
### autocorrelation (ACF)
- [[correlation]] between two points of a [[time series]] / [[stochastic process]] is called [[autocorrelation (ACF)]]
- the [[autocorrelation (ACF)]] is a normalized [[autocovariance]]
- given a [[stochastic process]] $\{X_t\}$ the [[autocorrelation (ACF)]] $\rho_{XX}(t_1, t_2)$ for the time instances $t_1$ and $t_2$ is given as follows

$$
\begin{split}
\rho_{XX}(t_1, t_2) 
&= 
\frac{ K_{XX}(t_1, t_2)}{\sqrt{ \mathbb{VAR}\left[X_{t_1}\right]\mathbb{VAR}\left[X_{t_2}\right]}}\\ 
&= 
\frac{ \mathbb{COV}\left[X_{t_1}, X_{t_2}\right]}{\sqrt{ \mathbb{VAR}\left[X_{t_1}\right]\mathbb{VAR}\left[X_{t_2}\right]}}\\ 
&= 
\frac{ \mathbb{E}\left[X_{t_1}X_{t_2}\right] - \mathbb{E}\left[X_{t_1}\right]\mathbb{E}\left[X_{t_2}\right]}{\sqrt{ \mathbb{VAR}\left[X_{t_1}\right]\mathbb{VAR}\left[X_{t_2}\right]}}\\ 
\end{split}
$$


Tags: mathematics time_series WS2425

END
