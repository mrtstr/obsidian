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


# -----------------

![[riemann sum#riemann sum]]

![[weighted mean smoothing for time series#weighted mean smoothing]]


![[kernel function (statistics)#kernel function (statistics)]]


![[kernel density estimator#kernel density estimators]]


# Anki

START
Basic
prove the equivalence of the following two definitions for [[kernel smoothing for time series]]
$$
\begin{split}
\hat X(u)
&= \frac{1}{\sum_{i=1}^n  K\left(\frac{\frac{t_i}{n}-u}{h}\right)} \sum_{i=1}^n X_{t_i} K\left(\frac{\frac{t_i}{n}-u}{h}\right) \\
&=\frac{1}{nh}  \sum_{i=1}^n X_{t_i} K\left(\frac{\frac{t_i}{n}-u}{h}\right) + \mathcal{O}\left(\frac{1}{n}\right) \\
\end{split}
$$
Back: 
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
=& \frac{1}{nh} \sum_{i=1}^n X_{t_i} K\left(\frac{\frac{t_i}{n}-u}{h}\right) + \mathcal{O}\left(\frac{1}{nh}\right) \\
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
<!--ID: 1737394997651-->
END

START
Basic
[[kernel smoothing for time series]]
- based on the original scale $[t_0, t_n]$
- based and the scale $u \in [0,1]$
- approximation of the normalization term
Back: 
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
=& \frac{1}{nh} \sum_{i=1}^n X_{t_i} K\left(\frac{\frac{t_i}{n}-u}{h}\right) + \mathcal{O}\left(\frac{1}{nh}\right) \\
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
<!--ID: 1736001837822-->
END