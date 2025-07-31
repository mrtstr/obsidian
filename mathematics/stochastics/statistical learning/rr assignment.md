
## general ridge regression
Ridge regression is a fundamental method in statistical learning and regularized linear modeling. It extends the classical ordinary least squares (OLS) estimator by incorporating a regularization term that penalizes large parameter magnitudes. This approach is particularly useful in high-dimensional settings or when the predictor variables exhibit multicollinearity.
Throughout this section, we assume a fixed (non-random) design matrix $X$, meaning that all expectations and variances are taken with respect to the noise $\epsilon$, conditioned on the observed features.
##### Model Definition
Ridge regression assumes a linear relationship between the input features and the target variable. Let $X \in \mathbb{R}^{n \times d}$ denote the design matrix with $n$ observations and $d$ features, and let $\theta \in \mathbb{R}^d$ be the parameter vector. The observed responses $Y \in \mathbb{R}^n$ are modeled as a linear combination of features with additive Gaussian white noise:

$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, I\sigma^2) \\
\end{split}
$$

Here, $\epsilon \sim \mathcal{N}(0, I\sigma^2)$ represents independent and identically distributed Gaussian noise with variance $\sigma^2$.
##### Objective Function
The ridge regression estimator is obtained by minimizing the penalized residual sum of squares. Specifically, the optimization objective augments the OLS loss with an $L^2$-norm penalty on the parameter vector $\theta$, controlled by a regularization parameter $\lambda > 0$:

$$
\begin{split}
\hat\theta_\lambda 
&= arg \min_\theta \frac{1}{n} ||Y - X\theta||^2 + \lambda ||\theta||^2_2 \\
\end{split}
$$

This formulation balances data fit and model complexity. Larger values of $\lambda$ shrink the parameter estimates toward zero, thereby reducing variance at the cost of introducing bias.
##### Analytical Solution
To derive the closed-form solution of the ridge estimator, we begin by defining the empirical covariance matrix $\hat\Sigma$ as:

$$
\hat\Sigma = \frac{1}{n} X^\top X
$$
This matrix captures the non-centered second-order structure of the input features. We further define the inner product $\langle a, b\rangle_\hat\Sigma = a^\top \hat\Sigma b$ and the corresponding norm $||a||_{\hat\Sigma}^2 = a^\top \hat\Sigma a$.

To minimize the objective function, we compute its gradient with respect to $\theta$ and set it to zero:

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

##### Expectation

The expectation of the ridge estimator $\hat\theta_\lambda$ is derived as follows:

$$
\begin{split}
\mathbb{E}\left[\hat\theta_\lambda\right] 
&= \frac{1}{n}\left(\hat\Sigma + \lambda I \right)^{-1} X^\top \mathbb{E}[Y] \\
&= \frac{1}{n}\left(\hat\Sigma + \lambda I \right)^{-1}X^\top  X \theta\\
&= \left(\hat\Sigma + \lambda I \right)^{-1}\hat\Sigma \theta\\
&= \theta - \lambda \left(\hat\Sigma + \lambda I \right)^{-1}\theta\\
\end{split}
$$

This result shows that the ridge estimator is biased for any $\lambda > 0$. The amount of bias depends on both the magnitude of the regularization and the geometry of the data as encoded in $\hat\Sigma$. Notably, as $\lambda \to 0$, the expectation converges to the unbiased ordinary least squares solution.
##### Variance

The variance of $\hat\theta_\lambda$ quantifies the estimator’s sensitivity to the noise in the observations. It is computed as:
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

The variance is reduced compared to the OLS estimator due to the influence of the regularization term. As $\lambda$ increases, the matrix inverse becomes more dampened, leading to lower estimator variance at the expense of increased bias. This highlights the fundamental trade-off in ridge regression between bias and variance.
## Parameter Recovery Theory
In this section, we study the behavior of ridge regression in terms of parameter recovery, rather than in terms of output prediction. Specifically, our focus is on the mean squared error (MSE) of the estimator $\hat\theta_\lambda$ with respect to the true parameter vector $\theta^*$.

We assume the data is generated according to the following linear model:
$$
\begin{split}
Y 
&= X \theta^* + \epsilon \sim \mathcal{N}(X \theta^*, I\sigma^2) \\
\end{split}
$$

Here, $\theta^* \in \mathbb{R}^d$ denotes the true (but unknown) parameter vector that generates the data, and $\epsilon \sim \mathcal{N}(0, \sigma^2 I)$ is Gaussian white noise. The quantity of interest is the expected squared error between the estimated and true parameters:

$$
\begin{split}
\mathrm{MSE}(\theta_{\lambda}) 
&=  \mathbb{E}\left[ \left|\left| \theta_{\lambda} - \theta^*    \right|\right|^2_2 \right]   \\
\end{split}
$$
### Bias-Variance Decomposition
The parameter error is quantified by the following decomposition of the mean squared error:
$$
\begin{split}
\mathrm{MSE}(\theta_{\lambda}) 
&=  \mathbb{E}\left[ \left|\left| \theta_{\lambda} - \theta^*    \right|\right|^2_2 \right]   \\
&=  \mathbb{E}\left[ \left|\left| \mathbb{E}\left[\hat\theta_\lambda\right] - \theta^* + \mathbb{E}\left[\hat\theta_\lambda\right] -  \theta_{\lambda} \right|\right|^2_2 \right]   \\
&=   \left|\left|  \mathbb{E}\left[\hat\theta_\lambda\right] - \theta^* \right|\right|^2_2  + \mathbb{E}\left[ \left|\left|\mathbb{E}\left[\hat\theta_\lambda\right] -   \hat\theta_\lambda\right|\right|^2_2 \right]  \\
&=   \left|\left|  \mathbb{E}\left[\hat\theta_\lambda\right] - \theta^* \right|\right|^2_2  + \mathbb{E}\left[ \left|\left|\mathbb{E}\left[\hat\theta_\lambda\right] -   \hat\theta_\lambda\right|\right|^2_2 \right]  \\
&= \left|\left| \lambda \left(\hat\Sigma + \lambda I \right)^{-1}\theta^*  \right|\right|^2_2  + \frac{\sigma^2}{n} \mathrm{TR}\left(\hat\Sigma\left(\hat\Sigma + \lambda I \right)^{-2} \right) \\
\end{split}
$$

The first term represents the squared bias, and the second term corresponds to the variance of the estimator.

### Spectral Representation
To gain further insight into the structure of the bias and variance terms, we now analyze the MSE decomposition in the spectral domain. Specifically, we apply the eigendecomposition of the empirical covariance matrix $\hat\Sigma$ to express both bias and variance in terms of its eigenvalues and eigenvectors.

Let $\hat\Sigma = U\Lambda U^\top$ denote the spectral decomposition (i.e., eigendecomposition or singular value decomposition) of the empirical covariance matrix, where $\Lambda = \mathrm{diag}(\lambda_1, \dots, \lambda_d)$ contains the eigenvalues of $\hat\Sigma$, and $U$ is an orthonormal basis of eigenvectors.

Since $U$ forms an orthonormal basis, the true parameter vector can be expressed in the eigenbasis as $\theta^* = U\beta$, where $\beta = U^\top \theta^*$. This change of basis simplifies the computation of bias and variance components in terms of the eigenvalues.

#### Bias Term
We first consider the bias term in spectral form. Substituting the eigendecomposition into the expression for bias, we obtain:
$$
\begin{split}
\left|\left| \lambda \left(\hat\Sigma + \lambda I \right)^{-1}\theta^*  \right|\right|^2_2
&=  \left|\left| \lambda \left(U\Lambda U^\top + \lambda I \right)^{-1}U\beta  \right|\right|^2_2   \\
&=  \left|\left| \lambda \left(U\Lambda U^\top + \lambda UU^\top \right)^{-1}U\beta  \right|\right|^2_2   \\
&=  \left|\left| \lambda U\left(\Lambda + \lambda I \right)^{-1}U^\top U\beta  \right|\right|^2_2   \\
&= \lambda^2 \left|\left| \left(\Lambda + \lambda I \right)^{-1}\beta  \right|\right|^2_2   \\
&= \lambda^2 \sum_{i=1}^d \left( \frac{\beta_i}{\lambda_i+\lambda}\right)^2  \\
\end{split}
$$
#### Variance Term
Similarly, the variance term can be expressed in the spectral domain. Using the linearity and invariance properties of the trace operator, we derive the following expression:

$$
\begin{split}
\frac{\sigma^2}{n} \mathrm{TR}\left(\hat\Sigma\left(\hat\Sigma + \lambda I \right)^{-2} \right)
&=  \frac{\sigma^2}{n} \mathrm{TR}\left(U\Lambda U^\top\left(U\Lambda U^\top + \lambda I \right)^{-2} \right)   \\
&=  \frac{\sigma^2}{n} \mathrm{TR}\left(U\Lambda U^\top\left(U\Lambda U^\top + \lambda UU^\top \right)^{-2} \right)   \\
&=  \frac{\sigma^2}{n} \mathrm{TR}\left(U\Lambda U^\top U^2\left(\Lambda  + \lambda I \right)^{-2}U^{-2} \right)   \\
&=  \frac{\sigma^2}{n} \mathrm{TR}\left(\Lambda \left(\Lambda + \lambda I \right)^{-2} \right)   \\
&=  \frac{\sigma^2}{n} \sum_{i=1}^d  \frac{\lambda_i}{\left(\lambda_i+\lambda\right)^2}    \\
\end{split}
$$

### Optimal Regularization Parameter
In general, a closed-form solution for the regularization parameter $\lambda$ that minimizes the MSE does not exist due to the complexity of the eigenvalue-weighted sums. However, the optimal value can be computed numerically and under specific simplifying assumptions, a closed-form solution becomes tractable.

In general, there is no closed-form expression for the value of $\lambda$ that minimizes $\mathrm{MSE}(\theta_\lambda)$. It must typically be determined numerically:

$$
\begin{split}
\lambda^{*}_{\mathrm{num}}
&= arg \min_\lambda  \mathrm{MSE}(\theta_{\lambda})  \\
\end{split}
$$

However, under specific assumptions, we can derive a closed-form solution.

##### Closed-Form Under Simplifying Assumptions
To derive such a closed-form expression, we consider the special case where all eigenvalues are equal, and the signal is uniformly distributed across the eigenspace. Specifically, we assume:

1. $\hat\Sigma = I$, i.e., all eigenvalues $\lambda_i = 1$,
2. All components of $\beta$ are equal: $\theta^* = \beta \sum u_i$.

Since $U$ is an orthonormal basis formed by the eigenvectors of $\hat\Sigma$, we can express the true parameter vector $\theta^*$ in this basis as _$\theta^*=U\beta$, where $\beta=U^\top\theta^*$.
 $$
 ||\theta^*||^2= ||U\beta||^2= ||\beta||^2 = \sum \beta_i^2
 $$

With these assumptions, the total MSE simplifies:

$$
\begin{split}
\mathrm{MSE}(\theta_{\lambda}) 
&=  \lambda^2 \sum_{i=1}^d \left( \frac{\beta_i}{\lambda_i+\lambda}\right)^2 +  \frac{\sigma^2}{n} \sum_{i=1}^d  \frac{\lambda_i}{\left(\lambda_i+\lambda\right)^2}  \\
&=  \lambda^2  \frac{d\beta_1^2}{(1+\lambda)^2} +  \frac{\sigma^2d}{n}   \frac{1}{\left(1+\lambda\right)^2}  \\
&=  \lambda^2  \frac{||\theta^*||^2}{(1+\lambda)^2} +  \frac{\sigma^2d}{n}   \frac{1}{\left(1+\lambda\right)^2}  \\
\end{split}
$$

We then minimize the expression by solving for the optimal regularization parameter $\lambda^*_{\mathrm{param}}$:

$$
\begin{split}
\frac{d}{d\lambda} \mathrm{MSE}(\theta_{\lambda}) 
&= 0 \\
&= \frac{2\lambda||\theta^*||^2(1+\lambda)^2-2\left(1+\lambda\right)\left(\lambda^2 ||\theta^*||^2 - \frac{\sigma^2d}{n}  \right)}{(1+\lambda)^4} \\
&= \lambda||\theta^*||^2(1+\lambda)-\lambda^2 ||\theta^*||^2 - \frac{\sigma^2d}{n}   \\
&= \lambda||\theta^*||^2+\lambda^2||\theta^*||^2-\lambda^2 ||\theta^*||^2 - \frac{\sigma^2d}{n}   \\
&= \lambda||\theta^*||^2 - \frac{\sigma^2d}{n}   \\
\Rightarrow \lambda^{*}_{\mathrm{closed}} &= \frac{\sigma^2d}{n||\theta^*||^2}
\end{split}
$$

This expression provides an interpretable closed-form for the optimal regularization parameter under idealized conditions. It highlights the dependence of $\lambda^*_{\mathrm{closed}}$ on the noise variance $\sigma^2$, data dimensionality $d$, number of samples $n$, and the norm of the true parameter vector $||\theta^*||^2$.

- calculate delta MSE depending on lambda vs ols
$$
\begin{split}
\mathrm{MSE}(\theta_{\lambda}) 
&=  \lambda^2 \sum_{i=1}^d \left( \frac{\beta_i}{\lambda_i+\lambda}\right)^2 +  \frac{\sigma^2}{n} \sum_{i=1}^d  \frac{\lambda_i}{\left(\lambda_i+\lambda\right)^2}  \\
\end{split}
$$

$$
\begin{split}
\mathrm{MSE}(\theta_\mathrm{OLS}) 
&=    \frac{1}{n} \sum_{i=1}^d  \frac{\sigma^2}{\lambda_i}  \\
\end{split}
$$
- explain lambda_i = amount of data variance in direction U_i and beta_i is the amount is signal in direction U_i
- show that it depends on ratio beta^2 / sigma^2 because bias penaltiy is proportional to beta_i and the variance improvement is propotional to sigma^2 
- in both cases lambda_i is the same since the same random seed was used but sum of beta_i demands on ||theta*||^2 which is much larger for ones
​
![[Pasted image 20250615181031.png]]
## Simulation

##### single trail
- given one sample for the design X and one sample for the parameters theta
- 100 noise samples
- compare simulated results with theoretic results

- simulated optimizer lambda: take mean of 100 samples over the grid, fit splines to it and find the minimum numerically
- closed optimizer is calculated see theory part
- numerical optimizer for lambda is is numerical min (MSE bias and variance)

![/home/martin/repos/stock_prediction/ridge_mse_plot_single_rand_2025-06-15_18-48-36.svg](file:///home/martin/repos/stock_prediction/ridge_mse_plot_single_rand_2025-06-15_18-48-36.svg)


![/home/martin/repos/stock_prediction/ridge_mse_plot_single_rand_2025-06-15_18-49-18.svg](file:///home/martin/repos/stock_prediction/ridge_mse_plot_single_rand_2025-06-15_18-49-18.svg)

##### multiple trails

![/home/martin/repos/stock_prediction/ridge_mse_plot_multi_rand_2025-06-15_18-51-33.svg](file:///home/martin/repos/stock_prediction/ridge_mse_plot_multi_rand_2025-06-15_18-51-33.svg)


### Isotropic coefficient vector
##### single trail

![/home/martin/repos/stock_prediction/ridge_mse_plot_single_ones_2025-06-15_18-55-51.svg](file:///home/martin/repos/stock_prediction/ridge_mse_plot_single_ones_2025-06-15_18-55-51.svg)

![/home/martin/repos/stock_prediction/ridge_mse_plot_single_ones_2025-06-15_18-57-37.svg](file:///home/martin/repos/stock_prediction/ridge_mse_plot_single_ones_2025-06-15_18-57-37.svg)
##### multiple trails

![/home/martin/repos/stock_prediction/ridge_mse_plot_single_ones_2025-06-15_20-07-38.svg](file:///home/martin/repos/stock_prediction/ridge_mse_plot_single_ones_2025-06-15_20-07-38.svg)

- optimal of theoretic curve
- opt of simulated curve
- closed form of opt under assumptions

![/home/martin/repos/stock_prediction/ridge_mse_plot_single_ones_2025-06-15_20-20-05.svg](file:///home/martin/repos/stock_prediction/ridge_mse_plot_single_ones_2025-06-15_20-20-05.svg)


![/home/martin/repos/stock_prediction/ridge_mse_plot_single_ones_2025-06-15_20-26-22.svg](file:///home/martin/repos/stock_prediction/ridge_mse_plot_single_ones_2025-06-15_20-26-22.svg)


$$
\begin{split}
\mathbb{E}_{\epsilon, X}\left[\mathrm{MSE}(\theta_{\lambda}) \right] 
&= 
\end{split}
$$

![/home/martin/repos/stock_prediction/ridge_mse_plot_multi_ones_2025-06-15_20-04-06.svg](file:///home/martin/repos/stock_prediction/ridge_mse_plot_multi_ones_2025-06-15_20-04-06.svg)



- calculate analytically the minimum of the exception of the MSE taken over X and epsilon for a given theta
