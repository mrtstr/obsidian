### kernel smoothing for time series
- generalized [[weighted mean smoothing]] with a shifted and scaled [[kernel function (statistics)]] $K: [-1,1] \to [0, \infty)$ for weighting the samples
- note the normalization $\frac{1}{\sum_{i=1}^n  K\left(\frac{t-t_i}{nh}\right)}$ is necessary because $K$ is a continuous function and the [[time series]] is discrete
- note that $\frac{t-t_i}{n}$ and $\frac{t_i}{n}-u$ is always inside $[-1, 1]$

$$
\hat X_t=\frac{1}{h} \frac{1}{\sum_{i=1}^n  K\left(\frac{t-t_i}{nh}\right)} \sum_{i=1}^n X_{t_i} K\left(\frac{t-t_i}{nh}\right)
$$


- depending on $u \in [0,1]$ where 0 is the beginning of the observed time interval and $1$ is the end

$$
\hat X(u)=\frac{1}{h} \frac{1}{\sum_{i=1}^n  K\left(\frac{\frac{t_i}{n}-u}{h}\right)} \sum_{i=1}^n X_{t_i} K\left(\frac{\frac{t_i}{n}-u}{h}\right)
$$

# -----------------

![[weighted mean smoothing#weighted mean smoothing]]


![[kernel function (statistics)#kernel function (statistics)]]


![[kernel density estimator#kernel density estimators]]


# Anki

START
Basic
[[kernel smoothing for time series]]
- based on the original scale $[t_0, t_n]$
- based and the scale $u \in [0,1]$
Back: 
### kernel smoothing for time series
- generalized [[weighted mean smoothing]] with a shifted and scaled [[kernel function (statistics)]] $K: [-1,1] \to [0, \infty)$ for weighting the samples
- note the normalization $\frac{1}{\sum_{i=1}^n  K\left(\frac{t-t_i}{nh}\right)}$ is necessary because $K$ is a continuous function and the [[time series]] is discrete
- note that $\frac{t-t_i}{n}$ and $\frac{t_i}{n}-u$ is always inside $[-1, 1]$

$$
\hat X_t=\frac{1}{h} \frac{1}{\sum_{i=1}^n  K\left(\frac{t-t_i}{nh}\right)} \sum_{i=1}^n X_{t_i} K\left(\frac{t-t_i}{nh}\right)
$$


- depending on $u \in [0,1]$ where 0 is the beginning of the observed time interval and $1$ is the end

$$
\hat X(u)=\frac{1}{h} \frac{1}{\sum_{i=1}^n  K\left(\frac{\frac{t_i}{n}-u}{h}\right)} \sum_{i=1}^n X_{t_i} K\left(\frac{\frac{t_i}{n}-u}{h}\right)
$$


____________________

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