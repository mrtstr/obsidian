### quantile regression

#### loss function
- the pinball [[loss function]] is a generalized form of the [[mean absolute error]] that penalizes over and underestimation asymmetrically based on the parameter $\alpha \in [0,1]$

$$
\begin{split}
\ell(y, \hat y) 
&= \begin{cases}
\alpha (y-\hat y) & \text{if } y \geq \hat y \\
(1-\alpha) (\hat y - y) & \text{if } y < \hat y \\
\end{cases} \\
&= \max\left(\alpha (y-\hat y), (1-\alpha) (\hat y -  y)\right)
\end{split}
$$

#### relationship to the CDF \ quantile function
- minimizing the pinball loss yields the $\alpha$ [[quantile function|quantile]] of the [[distribution]] of the estimated [[random variable]] $Y$

$$
\begin{split}
\frac{d}{d \hat y}\mathbb{E}\left[\ell(y, \hat y) \right]
&= \frac{d}{d \hat y}\int_\mathbb{R} f(y) \max\left(\alpha (y-\hat y), (1-\alpha) (\hat y -  y)\right) dy \\
&=\frac{d}{d \hat y}(1-\alpha)  \int_{-\infty}^{\hat y} f(y) (\hat y- y) dy + \frac{d}{d \hat y}\alpha \int_{\hat y}^{\infty} f(y) (y-\hat y) dy \\
&=...\\
&=F(\hat y) - \alpha = 0\\
\Rightarrow F(\hat y)  &= \alpha \\
\Rightarrow \hat y  &= F^{-1}(\alpha) \\

\end{split}
$$




# anki

START
Basic
[[quantile regression]]
- [[loss function]]
- relationship to the [[cumulative distribution function (CDF)]] and [[quantile function]]

Back: 
### quantile regression

#### loss function
- the pinball [[loss function]] is a generalized form of the [[mean absolute error]] that penalizes over and underestimation asymmetrically based on the parameter $\alpha \in [0,1]$

$$
\begin{split}
\ell(y, \hat y) 
&= \begin{cases}
\alpha (y-\hat y) & \text{if } y \geq \hat y \\
(1-\alpha) (\hat y - y) & \text{if } y < \hat y \\
\end{cases} \\
&= \max\left(\alpha (y-\hat y), (1-\alpha) (\hat y -  y)\right)
\end{split}
$$

#### relationship to the CDF \ quantile function
- minimizing the pinball loss yields the $\alpha$ [[quantile function|quantile]] of the [[distribution]] of the estimated [[random variable]] $Y$

$$
\begin{split}
\frac{d}{d \hat y}\mathbb{E}\left[\ell(y, \hat y) \right]
&= \frac{d}{d \hat y}\int_\mathbb{R} f(y) \max\left(\alpha (y-\hat y), (1-\alpha) (\hat y -  y)\right) dy \\
&=\frac{d}{d \hat y}(1-\alpha)  \int_{-\infty}^{\hat y} f(y) (\hat y- y) dy + \frac{d}{d \hat y}\alpha \int_{\hat y}^{\infty} f(y) (y-\hat y) dy \\
&=...\\
&=F(\hat y) - \alpha = 0\\
\Rightarrow F(\hat y)  &= \alpha \\
\Rightarrow \hat y  &= F^{-1}(\alpha) \\

\end{split}
$$



Tags: mathematics WS2526
<!--ID: 1768725519977-->
END