### ordinary least square estimator
- when training a [[linear model]] with the [[linear least squares]] method

$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^2 I)  \\
\end{split}
$$

- with the non-centered empirical [[empirical covariance]] $\hat\Sigma$ the solution of the ordinary least square estimator we have the following
- the solution exists if $\mathrm{rank}(X) = d$ with $\theta \in \mathbb{R}^d$

$$
\begin{split}
\theta_\mathrm{OLS}
&= arg \min_\theta ||Y - X\theta||^2 \\
&= \left(X^\top X\right)^{-1}X^\top Y \\
&= \frac{1}{n}  \hat\Sigma^{-1}X^\top Y \\
\end{split}
$$

- non centered empirical [[empirical covariance]] $\hat\Sigma$
$$
\hat\Sigma = \frac{1}{n} X^\top X
$$


$$
\begin{split}
\nabla_\theta||Y - X\theta||^2
&= A^\top\left(X\theta -Y\right) = 0 \\
\Rightarrow\theta_\mathrm{OLS}&= \left(X^\top X\right)^{-1}X^\top Y \\
&= \left(n \hat\Sigma\right)^{-1}X^\top Y \\
&= \frac{1}{n}  \hat\Sigma^{-1}X^\top Y \\
\end{split}
$$
#### expectation

$$
\begin{split}
\mathbb{E}[\theta_\mathrm{OLS}] 
&= \left(X^\top X\right)^{-1}X^\top \mathbb{E}[Y] \\
&= \left(X^\top X\right)^{-1}X^\top X\theta \\
&= \theta \\
\end{split}
$$

#### variance

$$
\begin{split}
\mathbb{VAR}[Y] 

&= \mathbb{VAR}[X\theta + \epsilon]  \\
&= \mathbb{VAR}[\epsilon]  \\
&= \sigma^2I\\

\end{split}
$$

$$
\begin{split}
\mathbb{VAR}[\theta_\mathrm{OLS}] 
&= \mathbb{E}\left[\left(\theta_\mathrm{OLS} - \mathbb{E}\left[\theta_\mathrm{OLS}\right]\right)\left(\theta_\mathrm{OLS} - \mathbb{E}\left[\theta_\mathrm{OLS}\right]\right)^\top\right]  \\
&= \mathbb{E}\left[\left(\left(X^\top X\right)^{-1}X^\top Y - \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top Y\right]\right)\left(\left(X^\top X\right)^{-1}X^\top Y - \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top Y\right]\right)^\top\right]  \\
&= \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top\left( Y - \mathbb{E}\left[ Y\right]\right)\left(\left(X^\top X\right)^{-1}X^\top \left(Y - \mathbb{E}\left[ Y\right]\right)\right)^\top\right]  \\
&= \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top\left( Y - \mathbb{E}\left[ Y\right]\right) \left(Y - \mathbb{E}\left[ Y\right]\right)^\top \left(\left(X^\top X\right)^{-1}X^\top \right)^\top\right]  \\
&= \left(X^\top X\right)^{-1}X^\top \mathbb{E}\left[\left( Y - \mathbb{E}\left[ Y\right]\right) \left(Y - \mathbb{E}\left[ Y\right]\right)^\top \right] \left(\left(X^\top X\right)^{-1}X^\top \right)^\top \\
&= \left(X^\top X\right)^{-1}X^\top \mathbb{VAR}\left[Y\right] \left(\left(X^\top X\right)^{-1}X^\top \right)^\top \\
&= \left(X^\top X\right)^{-1}X^\top \sigma^2I X \left(X^\top X\right)^{-\top}  \\
&= \sigma^2 \left(X^\top X\right)^{-1}X^\top X \left(X^\top X\right)^{-1}  \\
&= \sigma^2 \left(X^\top X\right)^{-1} \\
&= \frac{\sigma^2}{n} \hat\Sigma^{-1} \\
\end{split}
$$

#### risk
- with the [[mean square error]] [[loss function]] the unavoidable [[risk]] $\mathcal{R^*}$ is as follows
- note this assumes the relationship $Y= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^2 I)$ and does not work in general

$$
\begin{split}
R^* = \mathcal{R}(\theta^*) 
&= \min_\theta \mathbb{E}\left[ \frac{1}{n} || Y -  X \theta||^2_2 \right] \\
&= \min_\theta \mathbb{E}\left[ \frac{1}{n} || X\theta + \epsilon -  X \theta||^2_2 \right] \\
&= \frac{1}{n} \mathbb{E}\left[  ||  \epsilon ||^2_2 \right] \\
&= \frac{1}{n} \mathbb{E}\left[    \mathrm{TR}(\epsilon\epsilon^\top) \right] \\
&= \frac{1}{n} \mathbb{E}\left[  \sigma^2  \mathrm{TR}(I) \right] \\
&= \sigma^2 \\
\end{split}
$$

- the excess [[risk]] for the [[ordinary least square estimator]] is defined as follows
- with the [[scalar product]] $\langle a, b\rangle_\hat\Sigma=a^\top\hat\Sigma b$ and the [[norm]]$|| a||_\hat\Sigma^2 =a^\top\hat\Sigma b$ 
- note: we can split the [[expectation]] because $\theta_\mathrm{OLS}$ and the [[white noise]] $\epsilon$ are [[stochastic independent]]

$$
\begin{split}
\mathbb{E}\left[ \mathcal{R\left(\theta_\mathrm{OLS}\right)} \right] - \mathcal{R^*} 
&=\mathbb{E}\left[ \frac{1}{n} || Y -  X \theta_\mathrm{OLS}||^2_2 \right] - \sigma^2 \\
&=\mathbb{E}\left[ \frac{1}{n} || X \theta^* -  X \theta_\mathrm{OLS} + \epsilon||^2_2  \right] - \sigma^2 \\
&=\frac{1}{n}\mathbb{E}\left[  || X \left(\theta^* -   \theta_\mathrm{OLS}\right) + \epsilon||^2_2  \right] - \sigma^2 \\
&= \mathbb{E}\left[ \frac{1}{n} || X \left(\theta^* -   \theta_\mathrm{OLS}\right)||^2_2  \right] + \frac{1}{n} \mathbb{E}\left[||\epsilon||^2_2  \right] - \sigma^2 + \frac{2}{n} \mathbb{E}\left[\langle\epsilon, X \left(\theta^* -   \theta_\mathrm{OLS}\right) \rangle  \right] \\
&=  \frac{1}{n} \mathbb{E}\left[|| X \left(\theta^* -   \theta_\mathrm{OLS}\right)||^2_2 \right]    \\
&= \frac{1}{n} \mathbb{E}\left[  \left(X \left(\theta^* -   \theta_\mathrm{OLS}\right)\right)^\top X \left(\theta^* -   \theta_\mathrm{OLS}\right) \right] \\
&= \frac{1}{n} \mathbb{E}\left[ \left( \theta^* -   \theta_\mathrm{OLS}\right)^\top X^\top X \left(\theta^* -   \theta_\mathrm{OLS}\right)  \right]\\
&= \frac{n}{n} \mathbb{E}\left[ \left( \theta^* -   \theta_\mathrm{OLS}\right)^\top \hat\Sigma \left(\theta^* -   \theta_\mathrm{OLS}\right)  \right]\\
&=  \mathbb{E}\left[ || \theta^* -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right]   \\
\end{split}
$$

- in a fixed design setting with an [[bias|unbiased]] [[ordinary least square estimator]] we can express the excess [[risk]] as follows

$$
\begin{split}
\mathbb{E}\left[ \mathcal{R\left(\theta_\mathrm{OLS}\right)} \right] - \mathcal{R^*} 
&=   \mathrm{TR}\left( \hat\Sigma \mathbb{VAR}\left[\theta_\mathrm{OLS}\right] \right)   \\
&=   \mathrm{TR}\left( \hat\Sigma \frac{\sigma^2}{n} \hat\Sigma^{-1} \right)   \\
&= \frac{\sigma^2}{n}  \mathbb{E}\left[ \mathrm{TR}\left( \hat\Sigma  \hat\Sigma^{-1} \right) \right]   \\
&=  \frac{\sigma^2d}{n}   \\
\end{split}
$$

#### bias variance decomposition
- the excess [[risk]] can be decomposed as the sum of the [[variance]] and the squared [[bias]]
- with the [[scalar product]] $\langle a, b\rangle_\hat\Sigma=a^\top\hat\Sigma b$ and the [[norm]]$|| a||_\hat\Sigma^2 =a^\top\hat\Sigma b$ 

$$
\begin{split}
\mathbb{E}\left[ \mathcal{R\left(\theta_\mathrm{OLS}\right)} \right] - \mathcal{R^*} 
&=  \mathbb{E}\left[ || \theta^* -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right]   \\
&=  \mathbb{E}\left[ || \left(\theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right]\right) + \left(\mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}\right)  ||^2_\hat\Sigma \right]   \\
&=   || \theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right] ||^2_\hat\Sigma  + \mathbb{E}\left[ ||\mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right] -2 \mathbb{E}\left[ \langle\theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right], \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}\rangle_\hat\Sigma \right]  \\
&=   || \theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right] ||^2_\hat\Sigma  + \mathbb{E}\left[|| \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right] -2  \langle\theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right], \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \mathbb{E}\left[\theta_\mathrm{OLS}\right]\rangle_\hat\Sigma   \\
&=   || \theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right] ||^2_\hat\Sigma  + \mathbb{E}\left[ ||\mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right]  \\
\end{split}
$$

- when assuming constant $\hat\Sigma$ we have the following expression for the error contribution of the  [[variance]]

$$
\begin{split}
\mathbb{E}\left[ ||\mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right]
&= \mathbb{E}\left[ \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right)^\top\hat\Sigma \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right) \right] \\
&= \mathbb{E}\left[ \mathrm{TR}\left( \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right)^\top\hat\Sigma \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right)\right) \right] \\
&= \mathbb{E}\left[ \mathrm{TR}\left( \hat\Sigma \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right) \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right)^\top \right) \right] \\
&=  \mathrm{TR}\left( \hat\Sigma \mathbb{VAR}\left[\theta_\mathrm{OLS}\right] \right)  \\
\end{split}
$$

- note: since the variance is a [[matrix]] we cant decompose it in the bias and variance directly but in the contribution of bias and variance
#### condition of the problem
- the [[condition]] of the problem depends on $\kappa\left(X^\top X\right)$

$$
\begin{split}
X^\top X \theta_\mathrm{OLS}= X^\top Y \\
\end{split}
$$

- when $\kappa\left(X^\top X\right)$ is large small noise can lead to a significant error of the parameters $\theta_\mathrm{OLS}$
- $\kappa\left(X^\top X\right)$ is large when the columns are almost [[linear independent|linear dependent]]
- in this case use [[ridge regression]]

# ----------

![[linear least squares#linear least squares]]
![[linear least squares#normal equation]]

![[linear least squares#existence of a solution]]

![[linear model#linear model]]

![[condition of a matrix#condition of a square matrix]]



# anki


START
Basic
[[ordinary least square estimator]]
- model definition
- existence of a solution and solution
- [[expectation]]
- [[variance]]
- excess [[risk]]
- bias variance decomposition
Back: 


### ordinary least square estimator
- when training a [[linear model]] with the [[linear least squares]] method

$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^2 I)  \\
\end{split}
$$

- with the non-centered empirical [[empirical covariance]] $\hat\Sigma$ the solution of the ordinary least square estimator we have the following
- the solution exists if $\mathrm{rank}(X) = d$ with $\theta \in \mathbb{R}^d$

$$
\begin{split}
\theta_\mathrm{OLS}
&= arg \min_\theta ||Y - X\theta||^2 \\
&= \left(X^\top X\right)^{-1}X^\top Y \\
&= \frac{1}{n}  \hat\Sigma^{-1}X^\top Y \\
\end{split}
$$

- non centered empirical [[empirical covariance]] $\hat\Sigma$
$$
\hat\Sigma = \frac{1}{n} X^\top X
$$


$$
\begin{split}
\nabla_\theta||Y - X\theta||^2
&= A^\top\left(X\theta -Y\right) = 0 \\
\Rightarrow\theta_\mathrm{OLS}&= \left(X^\top X\right)^{-1}X^\top Y \\
&= \left(n \hat\Sigma\right)^{-1}X^\top Y \\
&= \frac{1}{n}  \hat\Sigma^{-1}X^\top Y \\
\end{split}
$$


#### expectation

$$
\begin{split}
\mathbb{E}[\theta_\mathrm{OLS}] 
&= \left(X^\top X\right)^{-1}X^\top \mathbb{E}[Y] \\
&= \left(X^\top X\right)^{-1}X^\top X\theta \\
&= \theta \\
\end{split}
$$

#### variance

$$
\begin{split}
\mathbb{VAR}[Y] 

&= \mathbb{VAR}[X\theta + \epsilon]  \\
&= \mathbb{VAR}[\epsilon]  \\
&= \sigma^2I\\

\end{split}
$$

$$
\begin{split}
\mathbb{VAR}[\theta_\mathrm{OLS}] 
&= \mathbb{E}\left[\left(\theta_\mathrm{OLS} - \mathbb{E}\left[\theta_\mathrm{OLS}\right]\right)\left(\theta_\mathrm{OLS} - \mathbb{E}\left[\theta_\mathrm{OLS}\right]\right)^\top\right]  \\
&= \mathbb{E}\left[\left(\left(X^\top X\right)^{-1}X^\top Y - \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top Y\right]\right)\left(\left(X^\top X\right)^{-1}X^\top Y - \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top Y\right]\right)^\top\right]  \\
&= \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top\left( Y - \mathbb{E}\left[ Y\right]\right)\left(\left(X^\top X\right)^{-1}X^\top \left(Y - \mathbb{E}\left[ Y\right]\right)\right)^\top\right]  \\
&= \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top\left( Y - \mathbb{E}\left[ Y\right]\right) \left(Y - \mathbb{E}\left[ Y\right]\right)^\top \left(\left(X^\top X\right)^{-1}X^\top \right)^\top\right]  \\
&= \left(X^\top X\right)^{-1}X^\top \mathbb{E}\left[\left( Y - \mathbb{E}\left[ Y\right]\right) \left(Y - \mathbb{E}\left[ Y\right]\right)^\top \right] \left(\left(X^\top X\right)^{-1}X^\top \right)^\top \\
&= \left(X^\top X\right)^{-1}X^\top \mathbb{VAR}\left[Y\right] \left(\left(X^\top X\right)^{-1}X^\top \right)^\top \\
&= \left(X^\top X\right)^{-1}X^\top \sigma^2I X \left(X^\top X\right)^{-\top}  \\
&= \sigma^2 \left(X^\top X\right)^{-1}X^\top X \left(X^\top X\right)^{-1}  \\
&= \sigma^2 \left(X^\top X\right)^{-1} \\
&= \frac{\sigma^2}{n} \hat\Sigma^{-1} \\
\end{split}
$$

#### risk
- with the [[mean square error]] [[loss function]] the unavoidable [[risk]] $\mathcal{R^*}$ is as follows
- note this assumes the relationship $Y= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^2 I)$ and does not work in general

$$
\begin{split}
R^* = \mathcal{R}(\theta^*) 
&= \min_\theta \mathbb{E}\left[ \frac{1}{n} || Y -  X \theta||^2_2 \right] \\
&= \min_\theta \mathbb{E}\left[ \frac{1}{n} || X\theta + \epsilon -  X \theta||^2_2 \right] \\
&= \frac{1}{n} \mathbb{E}\left[  ||  \epsilon ||^2_2 \right] \\
&= \frac{1}{n} \mathbb{E}\left[    \mathrm{TR}(\epsilon\epsilon^\top) \right] \\
&= \frac{1}{n} \mathbb{E}\left[  \sigma^2  \mathrm{TR}(I) \right] \\
&= \sigma^2 \\
\end{split}
$$

- the excess [[risk]] for the [[ordinary least square estimator]] is defined as follows
- with the [[scalar product]] $\langle a, b\rangle_\hat\Sigma=a^\top\hat\Sigma b$ and the [[norm]]$|| a||_\hat\Sigma^2 =a^\top\hat\Sigma b$ 
- note: we can split the [[expectation]] because $\theta_\mathrm{OLS}$ and the [[white noise]] $\epsilon$ are [[stochastic independent]]

$$
\begin{split}
\mathbb{E}\left[ \mathcal{R\left(\theta_\mathrm{OLS}\right)} \right] - \mathcal{R^*} 
&=\mathbb{E}\left[ \frac{1}{n} || Y -  X \theta_\mathrm{OLS}||^2_2 \right] - \sigma^2 \\
&=\mathbb{E}\left[ \frac{1}{n} || X \theta^* -  X \theta_\mathrm{OLS} + \epsilon||^2_2  \right] - \sigma^2 \\
&=\frac{1}{n}\mathbb{E}\left[  || X \left(\theta^* -   \theta_\mathrm{OLS}\right) + \epsilon||^2_2  \right] - \sigma^2 \\
&= \mathbb{E}\left[ \frac{1}{n} || X \left(\theta^* -   \theta_\mathrm{OLS}\right)||^2_2  \right] + \frac{1}{n} \mathbb{E}\left[||\epsilon||^2_2  \right] - \sigma^2 + \frac{2}{n} \mathbb{E}\left[\langle\epsilon, X \left(\theta^* -   \theta_\mathrm{OLS}\right) \rangle  \right] \\
&=  \frac{1}{n} \mathbb{E}\left[|| X \left(\theta^* -   \theta_\mathrm{OLS}\right)||^2_2 \right]    \\
&= \frac{1}{n} \mathbb{E}\left[  \left(X \left(\theta^* -   \theta_\mathrm{OLS}\right)\right)^\top X \left(\theta^* -   \theta_\mathrm{OLS}\right) \right] \\
&= \frac{1}{n} \mathbb{E}\left[ \left( \theta^* -   \theta_\mathrm{OLS}\right)^\top X^\top X \left(\theta^* -   \theta_\mathrm{OLS}\right)  \right]\\
&= \frac{n}{n} \mathbb{E}\left[ \left( \theta^* -   \theta_\mathrm{OLS}\right)^\top \hat\Sigma \left(\theta^* -   \theta_\mathrm{OLS}\right)  \right]\\
&=  \mathbb{E}\left[ || \theta^* -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right]   \\
\end{split}
$$

- in a fixed design setting with an [[bias|unbiased]] [[ordinary least square estimator]] we can express the excess [[risk]] as follows

$$
\begin{split}
\mathbb{E}\left[ \mathcal{R\left(\theta_\mathrm{OLS}\right)} \right] - \mathcal{R^*} 
&=   \mathrm{TR}\left( \hat\Sigma \mathbb{VAR}\left[\theta_\mathrm{OLS}\right] \right)   \\
&=   \mathrm{TR}\left( \hat\Sigma \frac{\sigma^2}{n} \hat\Sigma^{-1} \right)   \\
&= \frac{\sigma^2}{n}  \mathbb{E}\left[ \mathrm{TR}\left( \hat\Sigma  \hat\Sigma^{-1} \right) \right]   \\
&=  \frac{\sigma^2d}{n}   \\
\end{split}
$$
#### bias variance decomposition
- the excess [[risk]] can be decomposed as the sum of the [[variance]] and the squared [[bias]]
- with the [[scalar product]] $\langle a, b\rangle_\hat\Sigma=a^\top\hat\Sigma b$ and the [[norm]]$|| a||_\hat\Sigma^2 =a^\top\hat\Sigma b$ 

$$
\begin{split}
\mathbb{E}\left[ \mathcal{R\left(\theta_\mathrm{OLS}\right)} \right] - \mathcal{R^*} 
&=  \mathbb{E}\left[ || \theta^* -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right]   \\
&=  \mathbb{E}\left[ || \left(\theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right]\right) + \left(\mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}\right)  ||^2_\hat\Sigma \right]   \\
&=   || \theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right] ||^2_\hat\Sigma  + \mathbb{E}\left[ ||\mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right] -2 \mathbb{E}\left[ \langle\theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right], \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}\rangle_\hat\Sigma \right]  \\
&=   || \theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right] ||^2_\hat\Sigma  + \mathbb{E}\left[|| \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right] -2  \langle\theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right], \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \mathbb{E}\left[\theta_\mathrm{OLS}\right]\rangle_\hat\Sigma   \\
&=   || \theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right] ||^2_\hat\Sigma  + \mathbb{E}\left[ ||\mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right]  \\
\end{split}
$$

- when assuming constant $\hat\Sigma$ we have the following expression for the error contribution of the  [[variance]]

$$
\begin{split}
\mathbb{E}\left[ ||\mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right]
&= \mathbb{E}\left[ \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right)^\top\hat\Sigma \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right) \right] \\
&= \mathbb{E}\left[ \mathrm{TR}\left( \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right)^\top\hat\Sigma \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right)\right) \right] \\
&= \mathbb{E}\left[ \mathrm{TR}\left( \hat\Sigma \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right) \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right)^\top \right) \right] \\
&=  \mathrm{TR}\left( \hat\Sigma \mathbb{VAR}\left[\theta_\mathrm{OLS}\right] \right)  \\
\end{split}
$$

- note: since the variance is a [[matrix]] we cant decompose it in the bias and variance directly but in the contribution of bias and variance

____________



### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\theta, \sigma^2}: \theta \in \mathbb{R}^{s}\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(X)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\epsilon=(\epsilon_1, ..., \epsilon_n)^\top$ with $\mathbb{E}[\epsilon_i]=0$ and $\mathbb{VAR}[\epsilon]=I\sigma^2$

$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^ I) \\
&= \sum_{j \in [S]} X_{(*, j)} \theta_j + \epsilon \\
Y_i
&= \sum_{j \in [S]} X_{(i, j)} \theta_j + \epsilon_i \\
\end{split}
$$

### linear least squares
- given an over determined [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- since there is no exact solution the approach is to find the best fitting solution that minimizes the squared deviation

$$
x = \mathrm{argmin} ||Ax - b||_2
$$

### normal equation
- by setting the [[derivative]] of the objective function to zero we get the **normal equation**$A^\top Ax = A^\top b$
- every solution that minimizes the squared residuals will satisfy $A^\top Ax = A^\top b$

$$
\begin{split}
f(x) &= \frac{1}{2}||Ax - b||_2^2 \\
Df(x)[h] &= A^\top\left(Ax -b\right) = 0 \\
\Rightarrow & A^\top Ax = A^\top b \\
\end{split}
$$

### existence of a solution
- given an over determined [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- $\mathrm{argmin} ||Ax - b||_2$ always has a solution if $\mathrm{rank}(A)=m$

##### proof

$$
\begin{split}
A^\top Ax = A^\top b \\
\Rightarrow x = \left(A^\top A\right)^{-1} A^\top b \\
\end{split}
$$
- and if $\mathrm{rank}(A)=n$ then $A^\top A$ is positive definite and thus has a inverse


Tags: mathematics statistics SS25
<!--ID: 1748614636990-->
END

START
Basic
[[ordinary least square estimator]]
- model definition
- solution with proof
- existence of a solution
- relationship to the non centered empirical [[empirical covariance]] $\hat\Sigma$

Back: 
### ordinary least square estimator
- when training a [[linear model]] with the [[linear least squares]] method

$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^2 I)  \\
\end{split}
$$

- with the non-centered empirical [[empirical covariance]] $\hat\Sigma$ the solution of the ordinary least square estimator we have the following
- the solution exists if $\mathrm{rank}(X) = d$ with $\theta \in \mathbb{R}^d$

$$
\begin{split}
\theta_\mathrm{OLS}
&= arg \min_\theta ||Y - X\theta||^2 \\
&= \left(X^\top X\right)^{-1}X^\top Y \\
&= \frac{1}{n}  \hat\Sigma^{-1}X^\top Y \\
\end{split}
$$

- non centered empirical [[empirical covariance]] $\hat\Sigma$
$$
\hat\Sigma = \frac{1}{n} X^\top X
$$


$$
\begin{split}
\nabla_\theta||Y - X\theta||^2
&= A^\top\left(X\theta -Y\right) = 0 \\
\Rightarrow\theta_\mathrm{OLS}&= \left(X^\top X\right)^{-1}X^\top Y \\
&= \left(n \hat\Sigma\right)^{-1}X^\top Y \\
&= \frac{1}{n}  \hat\Sigma^{-1}X^\top Y \\
\end{split}
$$

_____________

### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\theta, \sigma^2}: \theta \in \mathbb{R}^{s}\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(X)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\epsilon=(\epsilon_1, ..., \epsilon_n)^\top$ with $\mathbb{E}[\epsilon_i]=0$ and $\mathbb{VAR}[\epsilon]=I\sigma^2$

$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^ I) \\
&= \sum_{j \in [S]} X_{(*, j)} \theta_j + \epsilon \\
Y_i
&= \sum_{j \in [S]} X_{(i, j)} \theta_j + \epsilon_i \\
\end{split}
$$

### linear least squares
- given an over determined [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- since there is no exact solution the approach is to find the best fitting solution that minimizes the squared deviation

$$
x = \mathrm{argmin} ||Ax - b||_2
$$

### normal equation
- by setting the [[derivative]] of the objective function to zero we get the **normal equation**$A^\top Ax = A^\top b$
- every solution that minimizes the squared residuals will satisfy $A^\top Ax = A^\top b$

$$
\begin{split}
f(x) &= \frac{1}{2}||Ax - b||_2^2 \\
Df(x)[h] &= A^\top\left(Ax -b\right) = 0 \\
\Rightarrow & A^\top Ax = A^\top b \\
\end{split}
$$

### existence of a solution
- given an over determined [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- $\mathrm{argmin} ||Ax - b||_2$ always has a solution if $\mathrm{rank}(A)=m$

##### proof

$$
\begin{split}
A^\top Ax = A^\top b \\
\Rightarrow x = \left(A^\top A\right)^{-1} A^\top b \\
\end{split}
$$
- and if $\mathrm{rank}(A)=n$ then $A^\top A$ is positive definite and thus has a inverse


Tags: mathematics statistics SS25
<!--ID: 1748614636994-->
END


START
Basic
given the [[ordinary least square estimator]] of the following [[linear model]]

$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^2 I)  \\
\end{split}
$$
calculate:
- the [[expectation]] $\mathbb{E}[\theta_\mathrm{OLS}]$
- the [[variance]] $\mathbb{VAR}[\theta_\mathrm{OLS}]$
Back: 

#### expectation

$$
\begin{split}
\mathbb{E}[\theta_\mathrm{OLS}] 
&= \left(X^\top X\right)^{-1}X^\top \mathbb{E}[Y] \\
&= \left(X^\top X\right)^{-1}X^\top X\theta \\
&= \theta \\
\end{split}
$$

#### variance

$$
\begin{split}
\mathbb{VAR}[Y] 

&= \mathbb{VAR}[X\theta + \epsilon]  \\
&= \mathbb{VAR}[\epsilon]  \\
&= \sigma^2I\\

\end{split}
$$

$$
\begin{split}
\mathbb{VAR}[\theta_\mathrm{OLS}] 
&= \mathbb{E}\left[\left(\theta_\mathrm{OLS} - \mathbb{E}\left[\theta_\mathrm{OLS}\right]\right)\left(\theta_\mathrm{OLS} - \mathbb{E}\left[\theta_\mathrm{OLS}\right]\right)^\top\right]  \\
&= \mathbb{E}\left[\left(\left(X^\top X\right)^{-1}X^\top Y - \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top Y\right]\right)\left(\left(X^\top X\right)^{-1}X^\top Y - \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top Y\right]\right)^\top\right]  \\
&= \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top\left( Y - \mathbb{E}\left[ Y\right]\right)\left(\left(X^\top X\right)^{-1}X^\top \left(Y - \mathbb{E}\left[ Y\right]\right)\right)^\top\right]  \\
&= \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top\left( Y - \mathbb{E}\left[ Y\right]\right) \left(Y - \mathbb{E}\left[ Y\right]\right)^\top \left(\left(X^\top X\right)^{-1}X^\top \right)^\top\right]  \\
&= \left(X^\top X\right)^{-1}X^\top \mathbb{E}\left[\left( Y - \mathbb{E}\left[ Y\right]\right) \left(Y - \mathbb{E}\left[ Y\right]\right)^\top \right] \left(\left(X^\top X\right)^{-1}X^\top \right)^\top \\
&= \left(X^\top X\right)^{-1}X^\top \mathbb{VAR}\left[Y\right] \left(\left(X^\top X\right)^{-1}X^\top \right)^\top \\
&= \left(X^\top X\right)^{-1}X^\top \sigma^2I X \left(X^\top X\right)^{-\top}  \\
&= \sigma^2 \left(X^\top X\right)^{-1}X^\top X \left(X^\top X\right)^{-1}  \\
&= \sigma^2 \left(X^\top X\right)^{-1} \\
&= \frac{\sigma^2}{n} \hat\Sigma^{-1} \\
\end{split}
$$


_____________

### ordinary least square estimator
- when training a [[linear model]] with the [[linear least squares]] method

$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^2 I)  \\
\end{split}
$$

- with the non-centered empirical [[empirical covariance]] $\hat\Sigma$ the solution of the ordinary least square estimator we have the following
- the solution exists if $\mathrm{rank}(X) = d$ with $\theta \in \mathbb{R}^d$

$$
\begin{split}
\theta_\mathrm{OLS}
&= arg \min_\theta ||Y - X\theta||^2 \\
&= \left(X^\top X\right)^{-1}X^\top Y \\
&= \frac{1}{n}  \hat\Sigma^{-1}X^\top Y \\
\end{split}
$$

- non centered empirical [[empirical covariance]] $\hat\Sigma$
$$
\hat\Sigma = \frac{1}{n} X^\top X
$$


$$
\begin{split}
\nabla_\theta||Y - X\theta||^2
&= A^\top\left(X\theta -Y\right) = 0 \\
\Rightarrow\theta_\mathrm{OLS}&= \left(X^\top X\right)^{-1}X^\top Y \\
&= \left(n \hat\Sigma\right)^{-1}X^\top Y \\
&= \frac{1}{n}  \hat\Sigma^{-1}X^\top Y \\
\end{split}
$$


### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\theta, \sigma^2}: \theta \in \mathbb{R}^{s}\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(X)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\epsilon=(\epsilon_1, ..., \epsilon_n)^\top$ with $\mathbb{E}[\epsilon_i]=0$ and $\mathbb{VAR}[\epsilon]=I\sigma^2$

$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^ I) \\
&= \sum_{j \in [S]} X_{(*, j)} \theta_j + \epsilon \\
Y_i
&= \sum_{j \in [S]} X_{(i, j)} \theta_j + \epsilon_i \\
\end{split}
$$

### linear least squares
- given an over determined [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- since there is no exact solution the approach is to find the best fitting solution that minimizes the squared deviation

$$
x = \mathrm{argmin} ||Ax - b||_2
$$

### normal equation
- by setting the [[derivative]] of the objective function to zero we get the **normal equation**$A^\top Ax = A^\top b$
- every solution that minimizes the squared residuals will satisfy $A^\top Ax = A^\top b$

$$
\begin{split}
f(x) &= \frac{1}{2}||Ax - b||_2^2 \\
Df(x)[h] &= A^\top\left(Ax -b\right) = 0 \\
\Rightarrow & A^\top Ax = A^\top b \\
\end{split}
$$

### existence of a solution
- given an over determined [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- $\mathrm{argmin} ||Ax - b||_2$ always has a solution if $\mathrm{rank}(A)=m$

##### proof

$$
\begin{split}
A^\top Ax = A^\top b \\
\Rightarrow x = \left(A^\top A\right)^{-1} A^\top b \\
\end{split}
$$
- and if $\mathrm{rank}(A)=n$ then $A^\top A$ is positive definite and thus has a inverse


Tags: mathematics statistics SS25
<!--ID: 1748614636997-->
END


START
Basic
given the [[ordinary least square estimator]] of the following [[linear model]]

$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^2 I)  \\
\end{split}
$$
- definition of the unavoidable [[risk]]
- definition and equation of the excess [[risk]]

Back: 
#### risk
- with the [[mean square error]] [[loss function]] the unavoidable [[risk]] $\mathcal{R^*}$ is as follows
- note this assumes the relationship $Y= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^2 I)$ and does not work in general

$$
\begin{split}
R^* = \mathcal{R}(\theta^*) 
&= \min_\theta \mathbb{E}\left[ \frac{1}{n} || Y -  X \theta||^2_2 \right] \\
&= \min_\theta \mathbb{E}\left[ \frac{1}{n} || X\theta + \epsilon -  X \theta||^2_2 \right] \\
&= \frac{1}{n} \mathbb{E}\left[  ||  \epsilon ||^2_2 \right] \\
&= \frac{1}{n} \mathbb{E}\left[    \mathrm{TR}(\epsilon\epsilon^\top) \right] \\
&= \frac{1}{n} \mathbb{E}\left[  \sigma^2  \mathrm{TR}(I) \right] \\
&= \sigma^2 \\
\end{split}
$$

- the excess [[risk]] for the [[ordinary least square estimator]] is defined as follows
- with the [[scalar product]] $\langle a, b\rangle_\hat\Sigma=a^\top\hat\Sigma b$ and the [[norm]]$|| a||_\hat\Sigma^2 =a^\top\hat\Sigma b$ 
- note: we can split the [[expectation]] because $\theta_\mathrm{OLS}$ and the [[white noise]] $\epsilon$ are [[stochastic independent]]

$$
\begin{split}
\mathbb{E}\left[ \mathcal{R\left(\theta_\mathrm{OLS}\right)} \right] - \mathcal{R^*} 
&=\mathbb{E}\left[ \frac{1}{n} || Y -  X \theta_\mathrm{OLS}||^2_2 \right] - \sigma^2 \\
&=\mathbb{E}\left[ \frac{1}{n} || X \theta^* -  X \theta_\mathrm{OLS} + \epsilon||^2_2  \right] - \sigma^2 \\
&=\frac{1}{n}\mathbb{E}\left[  || X \left(\theta^* -   \theta_\mathrm{OLS}\right) + \epsilon||^2_2  \right] - \sigma^2 \\
&= \mathbb{E}\left[ \frac{1}{n} || X \left(\theta^* -   \theta_\mathrm{OLS}\right)||^2_2  \right] + \frac{1}{n} \mathbb{E}\left[||\epsilon||^2_2  \right] - \sigma^2 + \frac{2}{n} \mathbb{E}\left[\langle\epsilon, X \left(\theta^* -   \theta_\mathrm{OLS}\right) \rangle  \right] \\
&=  \frac{1}{n} \mathbb{E}\left[|| X \left(\theta^* -   \theta_\mathrm{OLS}\right)||^2_2 \right]    \\
&= \frac{1}{n} \mathbb{E}\left[  \left(X \left(\theta^* -   \theta_\mathrm{OLS}\right)\right)^\top X \left(\theta^* -   \theta_\mathrm{OLS}\right) \right] \\
&= \frac{1}{n} \mathbb{E}\left[ \left( \theta^* -   \theta_\mathrm{OLS}\right)^\top X^\top X \left(\theta^* -   \theta_\mathrm{OLS}\right)  \right]\\
&= \frac{n}{n} \mathbb{E}\left[ \left( \theta^* -   \theta_\mathrm{OLS}\right)^\top \hat\Sigma \left(\theta^* -   \theta_\mathrm{OLS}\right)  \right]\\
&=  \mathbb{E}\left[ || \theta^* -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right]   \\
\end{split}
$$

_____________



### ordinary least square estimator
- when training a [[linear model]] with the [[linear least squares]] method

$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^2 I)  \\
\end{split}
$$

- with the non-centered empirical [[empirical covariance]] $\hat\Sigma$ the solution of the ordinary least square estimator we have the following
- the solution exists if $\mathrm{rank}(X) = d$ with $\theta \in \mathbb{R}^d$

$$
\begin{split}
\theta_\mathrm{OLS}
&= arg \min_\theta ||Y - X\theta||^2 \\
&= \left(X^\top X\right)^{-1}X^\top Y \\
&= \frac{1}{n}  \hat\Sigma^{-1}X^\top Y \\
\end{split}
$$

- non centered empirical [[empirical covariance]] $\hat\Sigma$
$$
\hat\Sigma = \frac{1}{n} X^\top X
$$


$$
\begin{split}
\nabla_\theta||Y - X\theta||^2
&= A^\top\left(X\theta -Y\right) = 0 \\
\Rightarrow\theta_\mathrm{OLS}&= \left(X^\top X\right)^{-1}X^\top Y \\
&= \left(n \hat\Sigma\right)^{-1}X^\top Y \\
&= \frac{1}{n}  \hat\Sigma^{-1}X^\top Y \\
\end{split}
$$


#### expectation

$$
\begin{split}
\mathbb{E}[\theta_\mathrm{OLS}] 
&= \left(X^\top X\right)^{-1}X^\top \mathbb{E}[Y] \\
&= \left(X^\top X\right)^{-1}X^\top X\theta \\
&= \theta \\
\end{split}
$$

#### variance

$$
\begin{split}
\mathbb{VAR}[Y] 

&= \mathbb{VAR}[X\theta + \epsilon]  \\
&= \mathbb{VAR}[\epsilon]  \\
&= \sigma^2I\\

\end{split}
$$

$$
\begin{split}
\mathbb{VAR}[\theta_\mathrm{OLS}] 
&= \mathbb{E}\left[\left(\theta_\mathrm{OLS} - \mathbb{E}\left[\theta_\mathrm{OLS}\right]\right)\left(\theta_\mathrm{OLS} - \mathbb{E}\left[\theta_\mathrm{OLS}\right]\right)^\top\right]  \\
&= \mathbb{E}\left[\left(\left(X^\top X\right)^{-1}X^\top Y - \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top Y\right]\right)\left(\left(X^\top X\right)^{-1}X^\top Y - \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top Y\right]\right)^\top\right]  \\
&= \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top\left( Y - \mathbb{E}\left[ Y\right]\right)\left(\left(X^\top X\right)^{-1}X^\top \left(Y - \mathbb{E}\left[ Y\right]\right)\right)^\top\right]  \\
&= \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top\left( Y - \mathbb{E}\left[ Y\right]\right) \left(Y - \mathbb{E}\left[ Y\right]\right)^\top \left(\left(X^\top X\right)^{-1}X^\top \right)^\top\right]  \\
&= \left(X^\top X\right)^{-1}X^\top \mathbb{E}\left[\left( Y - \mathbb{E}\left[ Y\right]\right) \left(Y - \mathbb{E}\left[ Y\right]\right)^\top \right] \left(\left(X^\top X\right)^{-1}X^\top \right)^\top \\
&= \left(X^\top X\right)^{-1}X^\top \mathbb{VAR}\left[Y\right] \left(\left(X^\top X\right)^{-1}X^\top \right)^\top \\
&= \left(X^\top X\right)^{-1}X^\top \sigma^2I X \left(X^\top X\right)^{-\top}  \\
&= \sigma^2 \left(X^\top X\right)^{-1}X^\top X \left(X^\top X\right)^{-1}  \\
&= \sigma^2 \left(X^\top X\right)^{-1} \\
&= \frac{\sigma^2}{n} \hat\Sigma^{-1} \\
\end{split}
$$


### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\theta, \sigma^2}: \theta \in \mathbb{R}^{s}\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(X)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\epsilon=(\epsilon_1, ..., \epsilon_n)^\top$ with $\mathbb{E}[\epsilon_i]=0$ and $\mathbb{VAR}[\epsilon]=I\sigma^2$

$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^ I) \\
&= \sum_{j \in [S]} X_{(*, j)} \theta_j + \epsilon \\
Y_i
&= \sum_{j \in [S]} X_{(i, j)} \theta_j + \epsilon_i \\
\end{split}
$$

### linear least squares
- given an over determined [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- since there is no exact solution the approach is to find the best fitting solution that minimizes the squared deviation

$$
x = \mathrm{argmin} ||Ax - b||_2
$$

### normal equation
- by setting the [[derivative]] of the objective function to zero we get the **normal equation**$A^\top Ax = A^\top b$
- every solution that minimizes the squared residuals will satisfy $A^\top Ax = A^\top b$

$$
\begin{split}
f(x) &= \frac{1}{2}||Ax - b||_2^2 \\
Df(x)[h] &= A^\top\left(Ax -b\right) = 0 \\
\Rightarrow & A^\top Ax = A^\top b \\
\end{split}
$$

### existence of a solution
- given an over determined [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- $\mathrm{argmin} ||Ax - b||_2$ always has a solution if $\mathrm{rank}(A)=m$

##### proof

$$
\begin{split}
A^\top Ax = A^\top b \\
\Rightarrow x = \left(A^\top A\right)^{-1} A^\top b \\
\end{split}
$$
- and if $\mathrm{rank}(A)=n$ then $A^\top A$ is positive definite and thus has a inverse


Tags: mathematics statistics SS25
<!--ID: 1748614637000-->
END


START
Basic
- given the [[ordinary least square estimator]] of the following [[linear model]]

$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^2 I)  \\
\end{split}
$$

- given the non centered empirical [[empirical covariance]] $\hat\Sigma$ with the [[scalar product]] $\langle a, b\rangle_\hat\Sigma=a^\top\hat\Sigma b$ and the [[norm]]$|| a||_\hat\Sigma^2 =a^\top\hat\Sigma b$ 

$$
\hat\Sigma = \frac{1}{n} X^\top X
$$

- given the excess [[risk]] of the [[ordinary least square estimator]]

$$
\begin{split}
\mathbb{E}\left[ \mathcal{R\left(\theta_\mathrm{OLS}\right)} \right] - \mathcal{R^*} 
&= \frac{n}{n} \mathbb{E}\left[ \left( \theta^* -   \theta_\mathrm{OLS}\right)^\top \hat\Sigma \left(\theta^* -   \theta_\mathrm{OLS}\right)  \right]\\
&=  \mathbb{E}\left[ || \theta^* -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right]   \\
\end{split}
$$

- calculate the bias variance decomposition of the [[ordinary least square estimator]] + as a function of the estimator [[variance]]
- how is it different to the single variant bias variance decomposition

Back: 

#### bias variance decomposition
- the excess [[risk]] can be decomposed as the sum of the [[variance]] and the squared [[bias]]
- with the [[scalar product]] $\langle a, b\rangle_\hat\Sigma=a^\top\hat\Sigma b$ and the [[norm]]$|| a||_\hat\Sigma^2 =a^\top\hat\Sigma b$ 

$$
\begin{split}
\mathbb{E}\left[ \mathcal{R\left(\theta_\mathrm{OLS}\right)} \right] - \mathcal{R^*} 
&=  \mathbb{E}\left[ || \theta^* -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right]   \\
&=  \mathbb{E}\left[ || \left(\theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right]\right) + \left(\mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}\right)  ||^2_\hat\Sigma \right]   \\
&=   || \theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right] ||^2_\hat\Sigma  + \mathbb{E}\left[ ||\mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right] -2 \mathbb{E}\left[ \langle\theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right], \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}\rangle_\hat\Sigma \right]  \\
&=   || \theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right] ||^2_\hat\Sigma  + \mathbb{E}\left[|| \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right] -2  \langle\theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right], \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \mathbb{E}\left[\theta_\mathrm{OLS}\right]\rangle_\hat\Sigma   \\
&=   || \theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right] ||^2_\hat\Sigma  + \mathbb{E}\left[ ||\mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right]  \\
\end{split}
$$

- when assuming constant $\hat\Sigma$ we have the following expression for the error contribution of the  [[variance]]

$$
\begin{split}
\mathbb{E}\left[ ||\mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right]
&= \mathbb{E}\left[ \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right)^\top\hat\Sigma \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right) \right] \\
&= \mathbb{E}\left[ \mathrm{TR}\left( \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right)^\top\hat\Sigma \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right)\right) \right] \\
&= \mathbb{E}\left[ \mathrm{TR}\left( \hat\Sigma \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right) \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right)^\top \right) \right] \\
&=  \mathrm{TR}\left( \hat\Sigma \mathbb{VAR}\left[\theta_\mathrm{OLS}\right] \right)  \\
\end{split}
$$

- note: since the variance is a [[matrix]] we cant decompose it in the bias and variance directly but in the contribution of bias and variance

_____________


### ordinary least square estimator
- when training a [[linear model]] with the [[linear least squares]] method

$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^2 I)  \\
\end{split}
$$

- with the non-centered empirical [[empirical covariance]] $\hat\Sigma$ the solution of the ordinary least square estimator we have the following
- the solution exists if $\mathrm{rank}(X) = d$ with $\theta \in \mathbb{R}^d$

$$
\begin{split}
\theta_\mathrm{OLS}
&= arg \min_\theta ||Y - X\theta||^2 \\
&= \left(X^\top X\right)^{-1}X^\top Y \\
&= \frac{1}{n}  \hat\Sigma^{-1}X^\top Y \\
\end{split}
$$

- non centered empirical [[empirical covariance]] $\hat\Sigma$
$$
\hat\Sigma = \frac{1}{n} X^\top X
$$


$$
\begin{split}
\nabla_\theta||Y - X\theta||^2
&= A^\top\left(X\theta -Y\right) = 0 \\
\Rightarrow\theta_\mathrm{OLS}&= \left(X^\top X\right)^{-1}X^\top Y \\
&= \left(n \hat\Sigma\right)^{-1}X^\top Y \\
&= \frac{1}{n}  \hat\Sigma^{-1}X^\top Y \\
\end{split}
$$


#### expectation

$$
\begin{split}
\mathbb{E}[\theta_\mathrm{OLS}] 
&= \left(X^\top X\right)^{-1}X^\top \mathbb{E}[Y] \\
&= \left(X^\top X\right)^{-1}X^\top X\theta \\
&= \theta \\
\end{split}
$$

#### variance

$$
\begin{split}
\mathbb{VAR}[Y] 

&= \mathbb{VAR}[X\theta + \epsilon]  \\
&= \mathbb{VAR}[\epsilon]  \\
&= \sigma^2I\\

\end{split}
$$

$$
\begin{split}
\mathbb{VAR}[\theta_\mathrm{OLS}] 
&= \mathbb{E}\left[\left(\theta_\mathrm{OLS} - \mathbb{E}\left[\theta_\mathrm{OLS}\right]\right)\left(\theta_\mathrm{OLS} - \mathbb{E}\left[\theta_\mathrm{OLS}\right]\right)^\top\right]  \\
&= \mathbb{E}\left[\left(\left(X^\top X\right)^{-1}X^\top Y - \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top Y\right]\right)\left(\left(X^\top X\right)^{-1}X^\top Y - \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top Y\right]\right)^\top\right]  \\
&= \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top\left( Y - \mathbb{E}\left[ Y\right]\right)\left(\left(X^\top X\right)^{-1}X^\top \left(Y - \mathbb{E}\left[ Y\right]\right)\right)^\top\right]  \\
&= \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top\left( Y - \mathbb{E}\left[ Y\right]\right) \left(Y - \mathbb{E}\left[ Y\right]\right)^\top \left(\left(X^\top X\right)^{-1}X^\top \right)^\top\right]  \\
&= \left(X^\top X\right)^{-1}X^\top \mathbb{E}\left[\left( Y - \mathbb{E}\left[ Y\right]\right) \left(Y - \mathbb{E}\left[ Y\right]\right)^\top \right] \left(\left(X^\top X\right)^{-1}X^\top \right)^\top \\
&= \left(X^\top X\right)^{-1}X^\top \mathbb{VAR}\left[Y\right] \left(\left(X^\top X\right)^{-1}X^\top \right)^\top \\
&= \left(X^\top X\right)^{-1}X^\top \sigma^2I X \left(X^\top X\right)^{-\top}  \\
&= \sigma^2 \left(X^\top X\right)^{-1}X^\top X \left(X^\top X\right)^{-1}  \\
&= \sigma^2 \left(X^\top X\right)^{-1} \\
&= \frac{\sigma^2}{n} \hat\Sigma^{-1} \\
\end{split}
$$

#### risk
- with the [[mean square error]] [[loss function]] the unavoidable [[risk]] $\mathcal{R^*}$ is as follows
- note this assumes the relationship $Y= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^2 I)$ and does not work in general

$$
\begin{split}
R^* = \mathcal{R}(\theta^*) 
&= \min_\theta \mathbb{E}\left[ \frac{1}{n} || Y -  X \theta||^2_2 \right] \\
&= \min_\theta \mathbb{E}\left[ \frac{1}{n} || X\theta + \epsilon -  X \theta||^2_2 \right] \\
&= \frac{1}{n} \mathbb{E}\left[  ||  \epsilon ||^2_2 \right] \\
&= \frac{1}{n} \mathbb{E}\left[    \mathrm{TR}(\epsilon\epsilon^\top) \right] \\
&= \frac{1}{n} \mathbb{E}\left[  \sigma^2  \mathrm{TR}(I) \right] \\
&= \sigma^2 \\
\end{split}
$$

- the excess [[risk]] for the [[ordinary least square estimator]] is defined as follows
- with the [[scalar product]] $\langle a, b\rangle_\hat\Sigma=a^\top\hat\Sigma b$ and the [[norm]]$|| a||_\hat\Sigma^2 =a^\top\hat\Sigma b$ 
- note: we can split the [[expectation]] because $\theta_\mathrm{OLS}$ and the [[white noise]] $\epsilon$ are [[stochastic independent]]

$$
\begin{split}
\mathbb{E}\left[ \mathcal{R\left(\theta_\mathrm{OLS}\right)} \right] - \mathcal{R^*} 
&=\mathbb{E}\left[ \frac{1}{n} || Y -  X \theta_\mathrm{OLS}||^2_2 \right] - \sigma^2 \\
&=\mathbb{E}\left[ \frac{1}{n} || X \theta^* -  X \theta_\mathrm{OLS} + \epsilon||^2_2  \right] - \sigma^2 \\
&=\frac{1}{n}\mathbb{E}\left[  || X \left(\theta^* -   \theta_\mathrm{OLS}\right) + \epsilon||^2_2  \right] - \sigma^2 \\
&= \mathbb{E}\left[ \frac{1}{n} || X \left(\theta^* -   \theta_\mathrm{OLS}\right)||^2_2  \right] + \frac{1}{n} \mathbb{E}\left[||\epsilon||^2_2  \right] - \sigma^2 + \frac{2}{n} \mathbb{E}\left[\langle\epsilon, X \left(\theta^* -   \theta_\mathrm{OLS}\right) \rangle  \right] \\
&=  \frac{1}{n} \mathbb{E}\left[|| X \left(\theta^* -   \theta_\mathrm{OLS}\right)||^2_2 \right]    \\
&= \frac{1}{n} \mathbb{E}\left[  \left(X \left(\theta^* -   \theta_\mathrm{OLS}\right)\right)^\top X \left(\theta^* -   \theta_\mathrm{OLS}\right) \right] \\
&= \frac{1}{n} \mathbb{E}\left[ \left( \theta^* -   \theta_\mathrm{OLS}\right)^\top X^\top X \left(\theta^* -   \theta_\mathrm{OLS}\right)  \right]\\
&= \frac{n}{n} \mathbb{E}\left[ \left( \theta^* -   \theta_\mathrm{OLS}\right)^\top \hat\Sigma \left(\theta^* -   \theta_\mathrm{OLS}\right)  \right]\\
&=  \mathbb{E}\left[ || \theta^* -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right]   \\
\end{split}
$$

- in a fixed design setting with an [[bias|unbiased]] [[ordinary least square estimator]] we can express the excess [[risk]] as follows

$$
\begin{split}
\mathbb{E}\left[ \mathcal{R\left(\theta_\mathrm{OLS}\right)} \right] - \mathcal{R^*} 
&=   \mathrm{TR}\left( \hat\Sigma \mathbb{VAR}\left[\theta_\mathrm{OLS}\right] \right)   \\
&=   \mathrm{TR}\left( \hat\Sigma \frac{\sigma^2}{n} \hat\Sigma^{-1} \right)   \\
&= \frac{\sigma^2}{n}  \mathbb{E}\left[ \mathrm{TR}\left( \hat\Sigma  \hat\Sigma^{-1} \right) \right]   \\
&=  \frac{\sigma^2d}{n}   \\
\end{split}
$$

### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\theta, \sigma^2}: \theta \in \mathbb{R}^{s}\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(X)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\epsilon=(\epsilon_1, ..., \epsilon_n)^\top$ with $\mathbb{E}[\epsilon_i]=0$ and $\mathbb{VAR}[\epsilon]=I\sigma^2$

$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^ I) \\
&= \sum_{j \in [S]} X_{(*, j)} \theta_j + \epsilon \\
Y_i
&= \sum_{j \in [S]} X_{(i, j)} \theta_j + \epsilon_i \\
\end{split}
$$

### linear least squares
- given an over determined [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- since there is no exact solution the approach is to find the best fitting solution that minimizes the squared deviation

$$
x = \mathrm{argmin} ||Ax - b||_2
$$

### normal equation
- by setting the [[derivative]] of the objective function to zero we get the **normal equation**$A^\top Ax = A^\top b$
- every solution that minimizes the squared residuals will satisfy $A^\top Ax = A^\top b$

$$
\begin{split}
f(x) &= \frac{1}{2}||Ax - b||_2^2 \\
Df(x)[h] &= A^\top\left(Ax -b\right) = 0 \\
\Rightarrow & A^\top Ax = A^\top b \\
\end{split}
$$

### existence of a solution
- given an over determined [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- $\mathrm{argmin} ||Ax - b||_2$ always has a solution if $\mathrm{rank}(A)=m$

##### proof

$$
\begin{split}
A^\top Ax = A^\top b \\
\Rightarrow x = \left(A^\top A\right)^{-1} A^\top b \\
\end{split}
$$
- and if $\mathrm{rank}(A)=n$ then $A^\top A$ is positive definite and thus has a inverse


Tags: mathematics statistics SS25
<!--ID: 1748614637002-->
END




START
Basic
- given the [[ordinary least square estimator]] of the following [[linear model]]
- definition of the [[condition]]
- when does the problem have a good condition
- what can be done if the problem has a bad condition?



Back: 
### ordinary least square estimator
- when training a [[linear model]] with the [[linear least squares]] method

$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^2 I)  \\
\end{split}
$$

- with the non-centered empirical [[empirical covariance]] $\hat\Sigma$ the solution of the ordinary least square estimator we have the following
- the solution exists if $\mathrm{rank}(X) = d$ with $\theta \in \mathbb{R}^d$

$$
\begin{split}
\theta_\mathrm{OLS}
&= arg \min_\theta ||Y - X\theta||^2 \\
&= \left(X^\top X\right)^{-1}X^\top Y \\
&= \frac{1}{n}  \hat\Sigma^{-1}X^\top Y \\
\end{split}
$$

- non centered empirical [[empirical covariance]] $\hat\Sigma$
$$
\hat\Sigma = \frac{1}{n} X^\top X
$$


$$
\begin{split}
\nabla_\theta||Y - X\theta||^2
&= A^\top\left(X\theta -Y\right) = 0 \\
\Rightarrow\theta_\mathrm{OLS}&= \left(X^\top X\right)^{-1}X^\top Y \\
&= \left(n \hat\Sigma\right)^{-1}X^\top Y \\
&= \frac{1}{n}  \hat\Sigma^{-1}X^\top Y \\
\end{split}
$$

#### condition of the problem
- the [[condition]] of the problem depends on $\kappa\left(X^\top X\right)$

$$
\begin{split}
X^\top X \theta_\mathrm{OLS}= X^\top Y \\
\end{split}
$$

- when $\kappa\left(X^\top X\right)$ is large small noise can lead to a significant error of the parameters $\theta_\mathrm{OLS}$
- $\kappa\left(X^\top X\right)$ is large when the columns are almost [[linear independent|linear dependent]]
- in this case use [[ridge regression]]


### condition of a square matrix
- given a [[regular matrix|regular]] [[square matrix]] $A \in \mathbb{R}^{m \times m}$ 
- the [[condition]] of the $A$ for a arbitrary [[operator norm]] is defined as follows
$$
\kappa(A) = \left|\left|A^{-1}\right|\right| \cdot \left|\left|A\right|\right|
$$
- the [[condition of a matrix]] answers the question of how big the relative error of $x$ would be when $b$ is perturbed by an error vector $e$ (or $A$ is perturbed)
$$
Ax=b + e
$$
- the result for x would be $x=A^{-1}b$ with an error $A^{-1}e$ thus the relative error would be as follows

$$
\begin{split}
\frac{||A^{-1}b||}{||A^{-1}e||} / \frac{||b||}{||e||} 
&= \frac{||A^{-1}b||}{||b||}  \frac{||e||}{||A^{-1}e||} \\
&\leq ||A^{-1}||  \frac{||e||}{||A^{-1}e||} \frac{||A||}{||A||}  \\
&\leq ||A^{-1}||  \frac{||e||}{||AA^{-1}e||} ||A||  \\
&\leq ||A^{-1}|| \cdot ||A||  \\
\end{split}
$$


_____________




### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\theta, \sigma^2}: \theta \in \mathbb{R}^{s}\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(X)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\epsilon=(\epsilon_1, ..., \epsilon_n)^\top$ with $\mathbb{E}[\epsilon_i]=0$ and $\mathbb{VAR}[\epsilon]=I\sigma^2$

$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^ I) \\
&= \sum_{j \in [S]} X_{(*, j)} \theta_j + \epsilon \\
Y_i
&= \sum_{j \in [S]} X_{(i, j)} \theta_j + \epsilon_i \\
\end{split}
$$

### linear least squares
- given an over determined [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- since there is no exact solution the approach is to find the best fitting solution that minimizes the squared deviation

$$
x = \mathrm{argmin} ||Ax - b||_2
$$

### normal equation
- by setting the [[derivative]] of the objective function to zero we get the **normal equation**$A^\top Ax = A^\top b$
- every solution that minimizes the squared residuals will satisfy $A^\top Ax = A^\top b$

$$
\begin{split}
f(x) &= \frac{1}{2}||Ax - b||_2^2 \\
Df(x)[h] &= A^\top\left(Ax -b\right) = 0 \\
\Rightarrow & A^\top Ax = A^\top b \\
\end{split}
$$

### existence of a solution
- given an over determined [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- $\mathrm{argmin} ||Ax - b||_2$ always has a solution if $\mathrm{rank}(A)=m$

##### proof

$$
\begin{split}
A^\top Ax = A^\top b \\
\Rightarrow x = \left(A^\top A\right)^{-1} A^\top b \\
\end{split}
$$
- and if $\mathrm{rank}(A)=n$ then $A^\top A$ is positive definite and thus has a inverse


Tags: mathematics statistics SS25
<!--ID: 1748614637004-->
END


START
Basic
given the [[ordinary least square estimator]] of the following [[linear model]]

$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^2 I)  \\
\end{split}
$$

- given the non centered empirical [[empirical covariance]] $\hat\Sigma$ with the [[scalar product]] $\langle a, b\rangle_\hat\Sigma=a^\top\hat\Sigma b$ and the [[norm]]$|| a||_\hat\Sigma^2 =a^\top\hat\Sigma b$ 

$$
\hat\Sigma = \frac{1}{n} X^\top X
$$

- given the excess [[risk]] of the [[ordinary least square estimator]]

$$
\begin{split}
\mathbb{E}\left[ \mathcal{R\left(\theta_\mathrm{OLS}\right)} \right] - \mathcal{R^*} 
&= \frac{n}{n} \mathbb{E}\left[ \left( \theta^* -   \theta_\mathrm{OLS}\right)^\top \hat\Sigma \left(\theta^* -   \theta_\mathrm{OLS}\right)  \right]\\
&=  \mathbb{E}\left[ || \theta^* -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right]   \\
\end{split}
$$


- proof that the excess [[risk]] is equal to $\frac{\sigma^2d}{n}$ for a fixed design setting and an unbiased estimator

Back: 
#### risk
- with the [[mean square error]] [[loss function]] the unavoidable [[risk]] $\mathcal{R^*}$ is as follows
- note this assumes the relationship $Y= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^2 I)$ and does not work in general

$$
\begin{split}
R^* = \mathcal{R}(\theta^*) 
&= \min_\theta \mathbb{E}\left[ \frac{1}{n} || Y -  X \theta||^2_2 \right] \\
&= \min_\theta \mathbb{E}\left[ \frac{1}{n} || X\theta + \epsilon -  X \theta||^2_2 \right] \\
&= \frac{1}{n} \mathbb{E}\left[  ||  \epsilon ||^2_2 \right] \\
&= \frac{1}{n} \mathbb{E}\left[    \mathrm{TR}(\epsilon\epsilon^\top) \right] \\
&= \frac{1}{n} \mathbb{E}\left[  \sigma^2  \mathrm{TR}(I) \right] \\
&= \sigma^2 \\
\end{split}
$$

- the excess [[risk]] for the [[ordinary least square estimator]] is defined as follows
- with the [[scalar product]] $\langle a, b\rangle_\hat\Sigma=a^\top\hat\Sigma b$ and the [[norm]]$|| a||_\hat\Sigma^2 =a^\top\hat\Sigma b$ 
- note: we can split the [[expectation]] because $\theta_\mathrm{OLS}$ and the [[white noise]] $\epsilon$ are [[stochastic independent]]

$$
\begin{split}
\mathbb{E}\left[ \mathcal{R\left(\theta_\mathrm{OLS}\right)} \right] - \mathcal{R^*} 
&=\mathbb{E}\left[ \frac{1}{n} || Y -  X \theta_\mathrm{OLS}||^2_2 \right] - \sigma^2 \\
&=\mathbb{E}\left[ \frac{1}{n} || X \theta^* -  X \theta_\mathrm{OLS} + \epsilon||^2_2  \right] - \sigma^2 \\
&=\frac{1}{n}\mathbb{E}\left[  || X \left(\theta^* -   \theta_\mathrm{OLS}\right) + \epsilon||^2_2  \right] - \sigma^2 \\
&= \mathbb{E}\left[ \frac{1}{n} || X \left(\theta^* -   \theta_\mathrm{OLS}\right)||^2_2  \right] + \frac{1}{n} \mathbb{E}\left[||\epsilon||^2_2  \right] - \sigma^2 + \frac{2}{n} \mathbb{E}\left[\langle\epsilon, X \left(\theta^* -   \theta_\mathrm{OLS}\right) \rangle  \right] \\
&=  \frac{1}{n} \mathbb{E}\left[|| X \left(\theta^* -   \theta_\mathrm{OLS}\right)||^2_2 \right]    \\
&= \frac{1}{n} \mathbb{E}\left[  \left(X \left(\theta^* -   \theta_\mathrm{OLS}\right)\right)^\top X \left(\theta^* -   \theta_\mathrm{OLS}\right) \right] \\
&= \frac{1}{n} \mathbb{E}\left[ \left( \theta^* -   \theta_\mathrm{OLS}\right)^\top X^\top X \left(\theta^* -   \theta_\mathrm{OLS}\right)  \right]\\
&= \frac{n}{n} \mathbb{E}\left[ \left( \theta^* -   \theta_\mathrm{OLS}\right)^\top \hat\Sigma \left(\theta^* -   \theta_\mathrm{OLS}\right)  \right]\\
&=  \mathbb{E}\left[ || \theta^* -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right]   \\
\end{split}
$$

- in a fixed design setting with an [[bias|unbiased]] [[ordinary least square estimator]] we can express the excess [[risk]] as follows

$$
\begin{split}
\mathbb{E}\left[ \mathcal{R\left(\theta_\mathrm{OLS}\right)} \right] - \mathcal{R^*} 
&=   \mathrm{TR}\left( \hat\Sigma \mathbb{VAR}\left[\theta_\mathrm{OLS}\right] \right)   \\
&=   \mathrm{TR}\left( \hat\Sigma \frac{\sigma^2}{n} \hat\Sigma^{-1} \right)   \\
&= \frac{\sigma^2}{n}  \mathbb{E}\left[ \mathrm{TR}\left( \hat\Sigma  \hat\Sigma^{-1} \right) \right]   \\
&=  \frac{\sigma^2d}{n}   \\
\end{split}
$$

#### bias variance decomposition
- the excess [[risk]] can be decomposed as the sum of the [[variance]] and the squared [[bias]]
- with the [[scalar product]] $\langle a, b\rangle_\hat\Sigma=a^\top\hat\Sigma b$ and the [[norm]]$|| a||_\hat\Sigma^2 =a^\top\hat\Sigma b$ 

$$
\begin{split}
\mathbb{E}\left[ \mathcal{R\left(\theta_\mathrm{OLS}\right)} \right] - \mathcal{R^*} 
&=  \mathbb{E}\left[ || \theta^* -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right]   \\
&=  \mathbb{E}\left[ || \left(\theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right]\right) + \left(\mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}\right)  ||^2_\hat\Sigma \right]   \\
&=   || \theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right] ||^2_\hat\Sigma  + \mathbb{E}\left[ ||\mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right] -2 \mathbb{E}\left[ \langle\theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right], \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}\rangle_\hat\Sigma \right]  \\
&=   || \theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right] ||^2_\hat\Sigma  + \mathbb{E}\left[|| \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right] -2  \langle\theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right], \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \mathbb{E}\left[\theta_\mathrm{OLS}\right]\rangle_\hat\Sigma   \\
&=   || \theta^* - \mathbb{E}\left[\theta_\mathrm{OLS}\right] ||^2_\hat\Sigma  + \mathbb{E}\left[ ||\mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right]  \\
\end{split}
$$

- when assuming constant $\hat\Sigma$ we have the following expression for the error contribution of the  [[variance]]

$$
\begin{split}
\mathbb{E}\left[ ||\mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS}||^2_\hat\Sigma \right]
&= \mathbb{E}\left[ \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right)^\top\hat\Sigma \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right) \right] \\
&= \mathbb{E}\left[ \mathrm{TR}\left( \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right)^\top\hat\Sigma \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right)\right) \right] \\
&= \mathbb{E}\left[ \mathrm{TR}\left( \hat\Sigma \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right) \left( \mathbb{E}\left[\theta_\mathrm{OLS}\right] -   \theta_\mathrm{OLS} \right)^\top \right) \right] \\
&=  \mathrm{TR}\left( \hat\Sigma \mathbb{VAR}\left[\theta_\mathrm{OLS}\right] \right)  \\
\end{split}
$$

- note: since the variance is a [[matrix]] we cant decompose it in the bias and variance directly but in the contribution of bias and variance

_____________



### ordinary least square estimator
- when training a [[linear model]] with the [[linear least squares]] method

$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^2 I)  \\
\end{split}
$$

- with the non-centered empirical [[empirical covariance]] $\hat\Sigma$ the solution of the ordinary least square estimator we have the following
- the solution exists if $\mathrm{rank}(X) = d$ with $\theta \in \mathbb{R}^d$

$$
\begin{split}
\theta_\mathrm{OLS}
&= arg \min_\theta ||Y - X\theta||^2 \\
&= \left(X^\top X\right)^{-1}X^\top Y \\
&= \frac{1}{n}  \hat\Sigma^{-1}X^\top Y \\
\end{split}
$$

- non centered empirical [[empirical covariance]] $\hat\Sigma$
$$
\hat\Sigma = \frac{1}{n} X^\top X
$$


$$
\begin{split}
\nabla_\theta||Y - X\theta||^2
&= A^\top\left(X\theta -Y\right) = 0 \\
\Rightarrow\theta_\mathrm{OLS}&= \left(X^\top X\right)^{-1}X^\top Y \\
&= \left(n \hat\Sigma\right)^{-1}X^\top Y \\
&= \frac{1}{n}  \hat\Sigma^{-1}X^\top Y \\
\end{split}
$$


#### expectation

$$
\begin{split}
\mathbb{E}[\theta_\mathrm{OLS}] 
&= \left(X^\top X\right)^{-1}X^\top \mathbb{E}[Y] \\
&= \left(X^\top X\right)^{-1}X^\top X\theta \\
&= \theta \\
\end{split}
$$

#### variance

$$
\begin{split}
\mathbb{VAR}[Y] 

&= \mathbb{VAR}[X\theta + \epsilon]  \\
&= \mathbb{VAR}[\epsilon]  \\
&= \sigma^2I\\

\end{split}
$$

$$
\begin{split}
\mathbb{VAR}[\theta_\mathrm{OLS}] 
&= \mathbb{E}\left[\left(\theta_\mathrm{OLS} - \mathbb{E}\left[\theta_\mathrm{OLS}\right]\right)\left(\theta_\mathrm{OLS} - \mathbb{E}\left[\theta_\mathrm{OLS}\right]\right)^\top\right]  \\
&= \mathbb{E}\left[\left(\left(X^\top X\right)^{-1}X^\top Y - \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top Y\right]\right)\left(\left(X^\top X\right)^{-1}X^\top Y - \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top Y\right]\right)^\top\right]  \\
&= \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top\left( Y - \mathbb{E}\left[ Y\right]\right)\left(\left(X^\top X\right)^{-1}X^\top \left(Y - \mathbb{E}\left[ Y\right]\right)\right)^\top\right]  \\
&= \mathbb{E}\left[\left(X^\top X\right)^{-1}X^\top\left( Y - \mathbb{E}\left[ Y\right]\right) \left(Y - \mathbb{E}\left[ Y\right]\right)^\top \left(\left(X^\top X\right)^{-1}X^\top \right)^\top\right]  \\
&= \left(X^\top X\right)^{-1}X^\top \mathbb{E}\left[\left( Y - \mathbb{E}\left[ Y\right]\right) \left(Y - \mathbb{E}\left[ Y\right]\right)^\top \right] \left(\left(X^\top X\right)^{-1}X^\top \right)^\top \\
&= \left(X^\top X\right)^{-1}X^\top \mathbb{VAR}\left[Y\right] \left(\left(X^\top X\right)^{-1}X^\top \right)^\top \\
&= \left(X^\top X\right)^{-1}X^\top \sigma^2I X \left(X^\top X\right)^{-\top}  \\
&= \sigma^2 \left(X^\top X\right)^{-1}X^\top X \left(X^\top X\right)^{-1}  \\
&= \sigma^2 \left(X^\top X\right)^{-1} \\
&= \frac{\sigma^2}{n} \hat\Sigma^{-1} \\
\end{split}
$$


### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\theta, \sigma^2}: \theta \in \mathbb{R}^{s}\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(X)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\epsilon=(\epsilon_1, ..., \epsilon_n)^\top$ with $\mathbb{E}[\epsilon_i]=0$ and $\mathbb{VAR}[\epsilon]=I\sigma^2$

$$
\begin{split}
Y 
&= X \theta + \epsilon \sim \mathcal{N}(X \theta, \sigma^ I) \\
&= \sum_{j \in [S]} X_{(*, j)} \theta_j + \epsilon \\
Y_i
&= \sum_{j \in [S]} X_{(i, j)} \theta_j + \epsilon_i \\
\end{split}
$$

### linear least squares
- given an over determined [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- since there is no exact solution the approach is to find the best fitting solution that minimizes the squared deviation

$$
x = \mathrm{argmin} ||Ax - b||_2
$$

### normal equation
- by setting the [[derivative]] of the objective function to zero we get the **normal equation**$A^\top Ax = A^\top b$
- every solution that minimizes the squared residuals will satisfy $A^\top Ax = A^\top b$

$$
\begin{split}
f(x) &= \frac{1}{2}||Ax - b||_2^2 \\
Df(x)[h] &= A^\top\left(Ax -b\right) = 0 \\
\Rightarrow & A^\top Ax = A^\top b \\
\end{split}
$$

### existence of a solution
- given an over determined [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- $\mathrm{argmin} ||Ax - b||_2$ always has a solution if $\mathrm{rank}(A)=m$

##### proof

$$
\begin{split}
A^\top Ax = A^\top b \\
\Rightarrow x = \left(A^\top A\right)^{-1} A^\top b \\
\end{split}
$$
- and if $\mathrm{rank}(A)=n$ then $A^\top A$ is positive definite and thus has a inverse


Tags: mathematics statistics SS25
<!--ID: 1748673949591-->
END
