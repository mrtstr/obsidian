#### weighted mean smoothing
- [[smoothing]] method for [[time series]] where the value for each point in time is described as a weighted sum of the neighbor values
- the weights have to be normalized i.e. $\sum_{i=-\infty}^\infty w_i=1$ 
- can be done symmetric where the future as well as the past values are considered or just based on the past

$$
\hat m_t = \sum_{i=-k}^k \theta_i X_{t-i}
$$

$$
\hat m_t = \sum_{i=1}^k \theta_i X_{t-i}
$$

- for example [[mean smoothing for time series]] and [[kernel smoothing for time series]] use this approach
# ---------------

![[mean smoothing for time series#mean smoothing for time series]]

![[kernel smoothing for time series#kernel smoothing for time series]]



# Anki

START
Basic
[[weighted mean smoothing for time series]]
- summary with two examples

Back: 
#### weighted mean smoothing
- [[smoothing]] method for [[time series]] where the value for each point in time is described as a weighted sum of the neighbor values
- the weights have to be normalized i.e. $\sum_{i=-\infty}^\infty w_i=1$ 
- can be done symmetric where the future as well as the past values are considered or just based on the past

$$
\hat m_t = \sum_{i=-k}^k \theta_i X_{t-i}
$$

$$
\hat m_t = \sum_{i=1}^k \theta_i X_{t-i}
$$

- for example [[mean smoothing for time series]] and [[kernel smoothing for time series]] use this approach
### mean smoothing for time series
- given the [[time series]] $X_1, ..., X_n$ that are taken during one time interval
- we are looking for a continuous [[statistical estimator]] $\hat X(u)$ during the time interval where $u=0$ is the beginning of the interval and $u=1$ is the end

- $\hat X(u)$ can be estimated using the [[smoothing#rolling mean smoothing|rolling mean smoothing]] with a window size of $2q + 1$ where the [[floor function]] $\lfloor un \rfloor \in \{0,..., n\}$ is used to map $u \in [0,1]$ to a number between zero and $n$ 

$$
\begin{split}
\hat X(u)
&= \frac{1}{2q+1} \sum_{i=-q}^{q} X_{\lfloor un \rfloor-j}
\end{split}
$$

- when calculating the [[expectation]] we see that the maximum error depends on $\frac{q}{n}$ 
	- a higher observation frequency i.e. a higher $n$ means that we have more observations around the point of interest $u$ which reduces the [[bias]]
	- if we increase the window size $q$ we include more values that are further away from the point of interest $u$ which increases the [[bias]]

$$
\begin{split}
\mathbb{E}\left[\hat X(u)\right]
&= \frac{1}{2q+1} \sum_{i=-q}^{q} \mathbb{E}\left[X_\frac{\lfloor un \rfloor-j}{n}\right] \\
&= X_\frac{\lfloor un \rfloor}{n} + \mathcal{O}\left(\frac{q}{n}\right)
\end{split}
$$

- the [[variance]] does not depend on $n$ and is small when the $q$ is large
- this is an example for the [[variance bias trade-off]] for non-parametric statistics
- thus the asymptotically optimal sample size $q$ depends on $n$ and has to satisfy two conditions 
	- $q(n)$ has to go to infinity to minimize the [[variance]]
	- $\frac{q(n)}{n}$ has to go to zero to minimize the [[bias]]

$$
\begin{split}
q(n) &\xrightarrow{n \to \infty} \infty \\
\frac{q(n)}{n} &\xrightarrow{n \to \infty} 0 \\
\end{split}
$$

- this means we would have infinite close to the point of interest still infinite observations
### kernel smoothing for time series
- generalized [[weighted mean smoothing for time series]] with a shifted and scaled [[kernel function (statistics)]] $K: [-1,1] \to [0, \infty)$ for weighting the samples
- note that $\frac{t-t_i}{n}$ and $\frac{t_i}{n}-u$ is always inside $[-1, 1]$

$$
\begin{split}
\hat X_t
&= \frac{1}{\sum_{i=1}^n  K\left(\frac{t-t_i}{nh}\right)} \sum_{i=1}^n X_{t_i} K\left(\frac{t-t_i}{nh}\right) \\
&=\frac{1}{nh}  \sum_{i=1}^n X_{t_i} K\left(\frac{t-t_i}{nh}\right) + \mathcal{O}\left(\frac{1}{n}\right) \\
\end{split}
$$


- depending on $u \in [0,1]$ where 0 is the beginning of the observed time interval and $1$ is the end

$$
\begin{split}
\hat X(u)
&= \frac{1}{\sum_{i=1}^n  K\left(\frac{\frac{t_i}{n}-u}{h}\right)} \sum_{i=1}^n X_{t_i} K\left(\frac{\frac{t_i}{n}-u}{h}\right) \\
&=\frac{1}{nh}  \sum_{i=1}^n X_{t_i} K\left(\frac{\frac{t_i}{n}-u}{h}\right) + \mathcal{O}\left(\frac{1}{n}\right) \\
\end{split}
$$

- the normalization $\frac{1}{\sum_{i=1}^n  K\left(\frac{t-t_i}{nh}\right)}$ is necessary because $K$ is a continuous function and the [[time series]] is discrete but for sufficiently large $n$ the normalization term is a [[riemann sum]] that approximates the integral of the [[kernel]] which is one



$$
\begin{split}
&\frac{1}{\sum_{i=1}^n  K\left(\frac{\frac{t_i}{n}-u}{h}\right)} \sum_{i=1}^n X_{t_i} K\left(\frac{\frac{t_i}{n}-u}{h}\right) \\
=&\frac{1}{\frac{1}{nh}\sum_{i=1}^n  K\left(\frac{\frac{t_i}{n}-u}{h}\right)} \frac{1}{nh} \sum_{i=1}^n X_{t_i} K\left(\frac{\frac{t_i}{n}-u}{h}\right) \\
=&\frac{1}{\frac{1}{n}\sum_{i=1}^n  K_h\left(\frac{t_i}{n}-u\right)} \frac{1}{nh} \sum_{i=1}^n X_{t_i} K\left(\frac{\frac{t_i}{n}-u}{h}\right) \\
=&\frac{1}{\frac{1}{n}\sum_{i=1}^n  K_h\left(\frac{t_i}{n}-u\right)} \frac{1}{nh} \sum_{i=1}^n X_{t_i} K\left(\frac{\frac{t_i}{n}-u}{h}\right) \\
=&\frac{1}{\int K_h\left(t-u\right) dt} \frac{1}{nh} \sum_{i=1}^n X_{t_i} K\left(\frac{\frac{t_i}{n}-u}{h}\right) \\
=& \frac{1}{nh} \sum_{i=1}^n X_{t_i} K\left(\frac{\frac{t_i}{n}-u}{h}\right) + \mathcal{O}\left(\frac{1}{n}\right) \\
\end{split}
$$



____________________

### riemann sum
- $x_1, ..., x_{n+1}$ are points that are [[partition|partitioning]] $[a, b]$ in $n$ sub-intervals thus $a=x_1 < ...< x_n < x_{n+1} = b$
- $c_i \in [x_{i-1}, x_{i}]$ is an arbitrary point in each sub-interval 
- then the [[integral]] of $f$ can be approximated as follows

$$
\begin{split}
\int_a^b f(x) dx = \sum_{i=1}^n f(c_i) \left(x_{i+1} - x_i\right)+ \mathcal{O}\left(\frac{1}{n}\right)
\end{split}
$$

if the sub-intervals $x_i - x_{i-1}=\frac{a-b}{n}$ are equally sized then it simplifies as follows

$$
\begin{split}
\int_a^b f(x) dx = \frac{a-b}{n} \sum_{i=1}^n f(c_i) + \mathcal{O}\left(\frac{1}{n}\right)
\end{split}
$$

- the error is in $\mathcal{O}\left(\frac{1}{n}\right)$

### kernel function (statistics)
- [[probability density function (PDF)]] or [[probability mass function (PMF)]] $K$ that is often centered around zero and symmetric

$$
\begin{split}
\int_\infty^\infty K(u) du &= 1 \\
\sum_{u =\infty}^\infty K(u)  &= 1 \\
K(u)  &= K(-u) \\
\end{split}
$$

- the [[kernel function (statistics)]] is often used scaled with a bandwidth parameter $h$ but the resulting function $K_h(u)$ is still a [[kernel function (statistics)]]

$$
K_h(u) = \frac{1}{h}K\left(\frac{u}{h}\right)
$$

TODO add proof

Tags: mathematics time_series WS2425
END