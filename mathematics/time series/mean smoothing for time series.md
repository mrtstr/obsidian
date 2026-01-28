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

# ----------------


![[weighted mean smoothing for time series#weighted mean smoothing]]


# Anki

START
Basic
[[mean smoothing for time series]]
- given the [[time series]] $X_1, ..., X_n$ that are taken during one time interval
- we are looking for a continuous [[statistical estimator]] $\hat X(u)$ during the time interval where $u=0$ is the beginning of the interval and $u=1$ is the end
- with [[expectation]]

asymptotically optimal window size $q$
- explanation but no formal proof

Back: 
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

_____________

#### weighted mean smoothing
- with $\sum_{i=-k}^k \theta_i=1$ e.g. $\theta_i=\frac{1}{2k+1}$

$$
\hat m_t = \sum_{i=-k}^k \theta_i X_{t+i}
$$


Tags: mathematics time_series WS2425
<!--ID: 1736005667355-->
END