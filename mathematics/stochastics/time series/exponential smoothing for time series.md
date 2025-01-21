### exponential smoothing for time series
- [[smoothing]] method for [[time series]] that is only based on the past (asymmetric)
- can be described as a [[kernel smoothing for time series]]

$$
\begin{split}
\hat m_t 
&= \sum_{i=0}^\infty w_i X_{t-i} \quad \text{ with } w_i = \alpha^i (1-\alpha) \\
&= w_0 X_t + \sum_{i=1}^\infty w_i X_{t-i} \\
&= w_0 X_t + \alpha \sum_{i=0}^\infty w_i X_{t-i-1} \\
&= (1-\alpha) X_t +\alpha m_{t-1} \\
\end{split}
$$

$$
\begin{split}
\sum_{i=0}^\infty   \alpha^i (1-\alpha) 
&= (1-\alpha) \sum_{i=0}^\infty   \alpha^i \\
&=   \frac{1-\alpha }{1-\alpha } \\
&=   1 \\
\end{split}
$$

### exponential smoothing as kernel smoothing
- given a [[kernel]] $K(x)=e^x \cdot \mathbb{I}[x \leq 0]$ the following [[kernel smoothing for time series]] is equal to the [[exponential smoothing for time series]] with $u=\frac{t_0(n)}{n}$ and $t_0(n)\in \{1,...,n\}$ and $\alpha = \exp\left(-\frac{1}{nh}\right)$
- since $e^\lambda = \sum_{n=1}^\infty \frac{\lambda^n}{n!}\approx 1+\lambda$ we can approximate $\frac{1}{nh} = 1 - \exp\left(-\frac{1}{nh}\right) = 1-\alpha$

$$
\begin{split}
\hat X_t
&=\frac{1}{nh}  \sum_{t=1}^n X_{t} K\left(\frac{t-t_0(n)}{nh}\right)  \\
&=\frac{1}{nh}  \sum_{t=1}^n X_{t} \exp\left(\frac{t-t_0(n)}{nh}\right) \cdot \mathbb{I}[t-t_0(n) \leq 0]  \\
&=\frac{1}{nh}  \sum_{t=1}^{t_n(n)} X_{t} \exp\left(\frac{t-t_n(n)}{nh}\right)  \\
&=\frac{1}{nh}  \sum_{s=0}^{t_n(n)-1} X_{t_0(n)-s}  \exp\left(-\frac{1}{nh}\right)^{s} \quad \text{with } s = t_0(n) - t  \\
&=\frac{1}{nh}  \sum_{s=0}^{t_n(n)-1} X_{t_0(n)-s}  \alpha^{s}   \\
&=(1-\alpha)  \sum_{s=0}^{t_n(n)-1} X_{t_0(n)-s}  \alpha^{s}   \\
\end{split}
$$

# ---------

![[kernel smoothing for time series#kernel smoothing for time series]]

![[smoothing#smoothing]]

![[geometric series#geometric series]]


# anki

START
Basic
[[exponential smoothing for time series]]
prove the following equality
$$
\begin{split}

 \sum_{i=0}^\infty \alpha^i (1-\alpha) X_{t-i} =
 (1-\alpha) X_t +\alpha m_{t-1} \\
\end{split}
$$

Back: 
### exponential smoothing for time series
- [[smoothing]] method for [[time series]] that is only based on the past (asymmetric)
- can be described as a [[kernel smoothing for time series]]

$$
\begin{split}
\hat m_t 
&= \sum_{i=0}^\infty w_i X_{t-i} \quad \text{ with } w_i = \alpha^i (1-\alpha) \\
&= w_0 X_t + \sum_{i=1}^\infty w_i X_{t-i} \\
&= w_0 X_t + \alpha \sum_{i=0}^\infty w_i X_{t-i-1} \\
&= (1-\alpha) X_t +\alpha m_{t-1} \\
\end{split}
$$

$$
\begin{split}
\sum_{i=0}^\infty   \alpha^i (1-\alpha) 
&= (1-\alpha) \sum_{i=0}^\infty   \alpha^i \\
&=   \frac{1-\alpha }{1-\alpha } \\
&=   1 \\
\end{split}
$$

___________

### geometric series
geometric [[series]] 

$$
\sum_{k=1}^\infty q^k = \frac{1}{1-q}
$$

Tags: mathematics time_series WS2425
<!--ID: 1737448608375-->
END

START
Basic
[[exponential smoothing for time series]]
- closed form and recursive
- proof that its normalized
- relationship to [[kernel smoothing for time series]] (no proof)

Back: 
### exponential smoothing for time series
- [[smoothing]] method for [[time series]] that is only based on the past (asymmetric)
- can be described as a [[kernel smoothing for time series]]

$$
\begin{split}
\hat m_t 
&= \sum_{i=0}^\infty w_i X_{t-i} \quad \text{ with } w_i = \alpha^i (1-\alpha) \\
&= w_0 X_t + \sum_{i=1}^\infty w_i X_{t-i} \\
&= w_0 X_t + \alpha \sum_{i=0}^\infty w_i X_{t-i-1} \\
&= (1-\alpha) X_t +\alpha m_{t-1} \\
\end{split}
$$

$$
\begin{split}
\sum_{i=0}^\infty   \alpha^i (1-\alpha) 
&= (1-\alpha) \sum_{i=0}^\infty   \alpha^i \\
&=   \frac{1-\alpha }{1-\alpha } \\
&=   1 \\
\end{split}
$$
### exponential smoothing as kernel smoothing
- given a [[kernel]] $K(x)=e^x \cdot \mathbb{I}[x \leq 0]$ the following [[kernel smoothing for time series]] is equal to the [[exponential smoothing for time series]] with $u=\frac{t_0(n)}{n}$ and $t_0(n)\in \{1,...,n\}$ and $\alpha = \exp\left(-\frac{1}{nh}\right)$
- since $e^\lambda = \sum_{n=1}^\infty \frac{\lambda^n}{n!}\approx 1+\lambda$ we can approximate $\frac{1}{nh} = 1 - \exp\left(-\frac{1}{nh}\right) = 1-\alpha$

$$
\begin{split}
\hat X_t
&=\frac{1}{nh}  \sum_{t=1}^n X_{t} K\left(\frac{t-t_0(n)}{nh}\right)  \\
&=\frac{1}{nh}  \sum_{t=1}^n X_{t} \exp\left(\frac{t-t_0(n)}{nh}\right) \cdot \mathbb{I}[t-t_0(n) \leq 0]  \\
&=\frac{1}{nh}  \sum_{t=1}^{t_n(n)} X_{t} \exp\left(\frac{t-t_n(n)}{nh}\right)  \\
&=\frac{1}{nh}  \sum_{s=0}^{t_n(n)-1} X_{t_0(n)-s}  \exp\left(-\frac{1}{nh}\right)^{s} \quad \text{with } s = t_0(n) - t  \\
&=\frac{1}{nh}  \sum_{s=0}^{t_n(n)-1} X_{t_0(n)-s}  \alpha^{s}   \\
&=(1-\alpha)  \sum_{s=0}^{t_n(n)-1} X_{t_0(n)-s}  \alpha^{s}   \\
\end{split}
$$

___________

### geometric series
geometric [[series]] 

$$
\sum_{k=1}^\infty q^k = \frac{1}{1-q}
$$

Tags: mathematics time_series WS2425
<!--ID: 1737311250713-->
END



START
Basic
relationship between [[exponential smoothing for time series]] and [[kernel smoothing for time series]] wit proof


Back: 
### exponential smoothing for time series
- [[smoothing]] method for [[time series]] that is only based on the past (asymmetric)
- can be described as a [[kernel smoothing for time series]]

$$
\begin{split}
\hat m_t 
&= \sum_{i=0}^\infty w_i X_{t-i} \quad \text{ with } w_i = \alpha^i (1-\alpha) \\
&= w_0 X_t + \sum_{i=1}^\infty w_i X_{t-i} \\
&= w_0 X_t + \alpha \sum_{i=0}^\infty w_i X_{t-i-1} \\
&= (1-\alpha) X_t +\alpha m_{t-1} \\
\end{split}
$$

$$
\begin{split}
\sum_{i=0}^\infty   \alpha^i (1-\alpha) 
&= (1-\alpha) \sum_{i=0}^\infty   \alpha^i \\
&=   \frac{1-\alpha }{1-\alpha } \\
&=   1 \\
\end{split}
$$
### exponential smoothing as kernel smoothing
- given a [[kernel]] $K(x)=e^x \cdot \mathbb{I}[x \leq 0]$ the following [[kernel smoothing for time series]] is equal to the [[exponential smoothing for time series]] with $u=\frac{t_0(n)}{n}$ and $t_0(n)\in \{1,...,n\}$ and $\alpha = \exp\left(-\frac{1}{nh}\right)$
- since $e^\lambda = \sum_{n=1}^\infty \frac{\lambda^n}{n!}\approx 1+\lambda$ we can approximate $\frac{1}{nh} = 1 - \exp\left(-\frac{1}{nh}\right) = 1-\alpha$

$$
\begin{split}
\hat X_t
&=\frac{1}{nh}  \sum_{t=1}^n X_{t} K\left(\frac{t-t_0(n)}{nh}\right)  \\
&=\frac{1}{nh}  \sum_{t=1}^n X_{t} \exp\left(\frac{t-t_0(n)}{nh}\right) \cdot \mathbb{I}[t-t_0(n) \leq 0]  \\
&=\frac{1}{nh}  \sum_{t=1}^{t_n(n)} X_{t} \exp\left(\frac{t-t_n(n)}{nh}\right)  \\
&=\frac{1}{nh}  \sum_{s=0}^{t_n(n)-1} X_{t_0(n)-s}  \exp\left(-\frac{1}{nh}\right)^{s} \quad \text{with } s = t_0(n) - t  \\
&=\frac{1}{nh}  \sum_{s=0}^{t_n(n)-1} X_{t_0(n)-s}  \alpha^{s}   \\
&=(1-\alpha)  \sum_{s=0}^{t_n(n)-1} X_{t_0(n)-s}  \alpha^{s}   \\
\end{split}
$$

___________

### geometric series
geometric [[series]] 

$$
\sum_{k=1}^\infty q^k = \frac{1}{1-q}
$$

### kernel smoothing for time series
- generalized [[weighted mean smoothing for time series]] with a shifted and scaled [[kernel function (statistics)]] $K: [-1,1] \to [0, \infty)$ for weighting the samples
- note that $\frac{t-t_i}{n}$ and $\frac{t_i}{n}-u$ is always inside $[-1, 1]$

$$
\begin{split}
\hat X_t
&= \frac{1}{\sum_{i=1}^n  K\left(\frac{t-t_i}{nh}\right)} \sum_{i=1}^n X_{t_i} K\left(\frac{t-t_i}{nh}\right) \\
&=\frac{1}{nh}  \sum_{i=1}^n X_{t_i} K\left(\frac{t-t_i}{nh}\right) + \mathcal{O}\left(\frac{1}{nh}\right) \\
\end{split}
$$


- depending on $u \in [0,1]$ where 0 is the beginning of the observed time interval and $1$ is the end

$$
\begin{split}
\hat X(u)
&= \frac{1}{\sum_{i=1}^n  K\left(\frac{\frac{t_i}{n}-u}{h}\right)} \sum_{i=1}^n X_{t_i} K\left(\frac{\frac{t_i}{n}-u}{h}\right) \\
&=\frac{1}{nh}  \sum_{i=1}^n X_{t_i} K\left(\frac{\frac{t_i}{n}-u}{h}\right) + \mathcal{O}\left(\frac{1}{nh}\right) \\
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
=& \frac{1}{nh} \sum_{i=1}^n X_{t_i} K\left(\frac{\frac{t_i}{n}-u}{h}\right) + \mathcal{O}\left(\frac{1}{nh}\right) \\
\end{split}
$$


Tags: mathematics time_series WS2425
<!--ID: 1737394997643-->
END
