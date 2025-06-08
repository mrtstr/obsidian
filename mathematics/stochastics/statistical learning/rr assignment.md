##### model
$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, I\sigma^2) \\
\end{split}
$$

##### objective function

$$
\begin{split}
\hat\theta_\lambda 
&= arg \min_\theta \frac{1}{n} ||Y - X\theta||^2 + \lambda ||\theta||^2_2 \\
\end{split}
$$
##### solution

- non centered empirical [[empirical covariance]] $\hat\Sigma$ with the [[scalar product]] $\langle a, b\rangle_\hat\Sigma=a^\top\hat\Sigma b$ and the [[norm]]$|| a||_\hat\Sigma^2 =a^\top\hat\Sigma b$ 

$$
\hat\Sigma = \frac{1}{n} X^\top X
$$

$$
\begin{split}
\nabla\left(\frac{1}{n}||Y - X\theta||^2 + \lambda ||\theta||^2_2 \right) 
&= \frac{2}{n} X^\top\left(X\theta -Y\right) + 2\lambda \theta  = 0 \\
0 &= \frac{1}{n} X^\top X\theta - \frac{1}{n} X^\top Y + \lambda \theta \\
\frac{1}{n}X^\top Y&=\left(\frac{1}{n}X^\top X + \lambda I \right)\theta  \\
\Rightarrow\hat\theta_\lambda 
&=\frac{1}{n}\left(\frac{1}{n}X^\top X + \lambda I \right)^{-1}X^\top Y \\
&=\left(X^\top X + n \lambda I \right)^{-1}X^\top Y \\
&=\frac{1}{n}\left(\hat\Sigma + \lambda I \right)^{-1}X^\top Y \\
\end{split}
$$

##### expectation

$$
\begin{split}
\mathbb{E}\left[\hat\theta_\lambda\right] 
&= \frac{1}{n}\left(\hat\Sigma + \lambda I \right)^{-1} X^\top \mathbb{E}[Y] \\
&= \frac{1}{n}\left(\hat\Sigma + \lambda I \right)^{-1}X^\top  X \theta\\
&= \left(\hat\Sigma + \lambda I \right)^{-1}\hat\Sigma \theta\\
&= \theta - \lambda \left(\hat\Sigma + \lambda I \right)^{-1}\theta\\
\end{split}
$$

##### variance
$$
\begin{split}
\mathbb{VAR}\left[ \hat\theta_\lambda\right] 
&=\mathbb{E}\left[\left(\hat\theta_\lambda-\mathbb{E}\left[\hat\theta_\lambda\right]\right)\left(\hat\theta_\lambda-\mathbb{E}\left[\hat\theta_\lambda\right]\right)^\top\right] \\
&=\mathbb{E}\left[\frac{1}{n^2}\left(\hat\Sigma + \lambda I \right)^{-1} X^\top \left(Y-\mathbb{E}\left[Y\right]\right)\left(Y-\mathbb{E}\left[Y\right]\right)^\top X\left(\hat\Sigma + \lambda I \right)^{-1} \right] \\
&=\mathbb{E}\left[\frac{1}{n^2}\left(\hat\Sigma + \lambda I \right)^{-1} X^\top \mathbb{VAR}[Y] X\left(\hat\Sigma + \lambda I \right)^{-1} \right] \\
&=\frac{1}{n^2}\left(\hat\Sigma + \lambda I \right)^{-1} X^\top I \sigma^2 X\left(\hat\Sigma + \lambda I \right)^{-1}  \\
&=\frac{\sigma^2}{n^2}\left(\hat\Sigma + \lambda I \right)^{-1} X^\top  X\left(\hat\Sigma + \lambda I \right)^{-1}  \\
&=\frac{\sigma^2}{n}\left(\hat\Sigma + \lambda I \right)^{-1} \hat\Sigma\left(\hat\Sigma + \lambda I \right)^{-1}  \\
\end{split}
$$

##### parameter error

$$
\begin{split}
\mathrm{MSE}(\theta_{\lambda}) 
&=  \mathbb{E}\left[ \left|\left| \theta_{\lambda} - \theta^*    \right|\right|^2_2 \right]   \\
&=  \mathbb{E}\left[ \left|\left| \mathbb{E}\left[\hat\theta_\lambda\right] - \theta^* + \mathbb{E}\left[\hat\theta_\lambda\right] -  \theta_{\lambda} \right|\right|^2_2 \right]   \\
&=   \left|\left|  \mathbb{E}\left[\hat\theta_\lambda\right] - \theta^* \right|\right|^2_2  + \mathbb{E}\left[ \left|\left|\mathbb{E}\left[\hat\theta_\lambda\right] -   \hat\theta_\lambda\right|\right|^2_2 \right]  \\
&=   \left|\left|  \mathbb{E}\left[\hat\theta_\lambda\right] - \theta^* \right|\right|^2_2  + \mathbb{E}\left[ \left|\left|\mathbb{E}\left[\hat\theta_\lambda\right] -   \hat\theta_\lambda\right|\right|^2_2 \right]  \\
&=  \lambda^2   \theta^{*\top}\left(\hat\Sigma + \lambda I \right)^{-2}  \hat\Sigma \theta^*   + \frac{\sigma^2}{n} \mathrm{TR}\left(\hat\Sigma^2\left(\hat\Sigma + \lambda I \right)^{-2} \right)  \\
\end{split}
$$



![[Pasted image 20250608172948.png]]