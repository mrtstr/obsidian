# General Ridge Regression

Ridge regression is a fundamental method in statistical learning and regularized linear modeling. It extends the classical ordinary least squares (OLS) estimator by incorporating a regularization term that penalizes large parameter magnitudes. This approach is particularly useful in high-dimensional settings or when the predictor variables exhibit multicollinearity.

## Model Definition

Ridge regression assumes a linear relationship between the input features and the target variable. Let $X \in \mathbb{R}^{n \times d}$ denote the design matrix with $n$ observations and $d$ features, and let $\theta \in \mathbb{R}^d$ be the parameter vector. The observed responses $Y \in \mathbb{R}^n$ are modeled as a linear combination of features with additive Gaussian white noise:

Y=Xθ+ϵ∼N(Xθ,Iσ2)\begin{split} Y &= X \theta + \epsilon \sim \mathcal{N}(X \theta, I\sigma^2) \\ \end{split}Y​=Xθ+ϵ∼N(Xθ,Iσ2)​

Here, $\epsilon \sim \mathcal{N}(0, I\sigma^2)$ represents independent and identically distributed Gaussian noise with variance $\sigma^2$.

## Objective Function

The ridge regression estimator is obtained by minimizing the penalized residual sum of squares. Specifically, the optimization objective augments the OLS loss with an $L^2$-norm penalty on the parameter vector $\theta$, controlled by a regularization parameter $\lambda > 0$:

θ^λ=argmin⁡θ1n∣∣Y−Xθ∣∣2+λ∣∣θ∣∣22\begin{split} \hat\theta_\lambda &= arg \min_\theta \frac{1}{n} ||Y - X\theta||^2 + \lambda ||\theta||^2_2 \\ \end{split}θ^λ​​=argθmin​n1​∣∣Y−Xθ∣∣2+λ∣∣θ∣∣22​​

This formulation balances data fit and model complexity. Larger values of $\lambda$ shrink the parameter estimates toward zero, thereby reducing variance at the cost of introducing bias.

## Analytical Solution

To derive the closed-form solution of the ridge estimator, we begin by defining the empirical covariance matrix $\hat\Sigma$ as:

Σ^=1nX⊤X\hat\Sigma = \frac{1}{n} X^\top XΣ^=n1​X⊤X

This matrix captures the non-centered second-order structure of the input features. We further define the inner product $\langle a, b\rangle_\hat\Sigma = a^\top \hat\Sigma b$ and the corresponding norm $||a||_{\hat\Sigma}^2 = a^\top \hat\Sigma a$.

To minimize the objective function, we compute its gradient with respect to $\theta$ and set it to zero:

∇(1n∣∣Y−Xθ∣∣2+λ∣∣θ∣∣22)=2nX⊤(Xθ−Y)+2λθ=00=1nX⊤Xθ−1nX⊤Y+λθ1nX⊤Y=(1nX⊤X+λI)θ⇒θ^λ=1n(1nX⊤X+λI)−1X⊤Y=(X⊤X+nλI)−1X⊤Y=1n(Σ^+λI)−1X⊤Y\begin{split} \nabla\left(\frac{1}{n}||Y - X\theta||^2 + \lambda ||\theta||^2_2 \right) &= \frac{2}{n} X^\top\left(X\theta -Y\right) + 2\lambda \theta = 0 \\ 0 &= \frac{1}{n} X^\top X\theta - \frac{1}{n} X^\top Y + \lambda \theta \\ \frac{1}{n}X^\top Y&=\left(\frac{1}{n}X^\top X + \lambda I \right)\theta \\ \Rightarrow\hat\theta_\lambda &=\frac{1}{n}\left(\frac{1}{n}X^\top X + \lambda I \right)^{-1}X^\top Y \\ &=\left(X^\top X + n \lambda I \right)^{-1}X^\top Y \\ &=\frac{1}{n}\left(\hat\Sigma + \lambda I \right)^{-1}X^\top Y \\ \end{split}∇(n1​∣∣Y−Xθ∣∣2+λ∣∣θ∣∣22​)0n1​X⊤Y⇒θ^λ​​=n2​X⊤(Xθ−Y)+2λθ=0=n1​X⊤Xθ−n1​X⊤Y+λθ=(n1​X⊤X+λI)θ=n1​(n1​X⊤X+λI)−1X⊤Y=(X⊤X+nλI)−1X⊤Y=n1​(Σ^+λI)−1X⊤Y​

This expression provides the unique minimizer of the ridge regression objective. The regularization term ensures the matrix inversion remains well-posed even when $X^\top X$ is ill-conditioned or not full rank.