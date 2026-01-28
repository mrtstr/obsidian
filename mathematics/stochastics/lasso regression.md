### lasso regression
- [[linear model]] trained with a $L1$ regularization term
-  similar to [[ridge regression]] but with $L1$ [[norm]] instead of $L2$  
- there is no closed form solution
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
\hat\theta_\mathrm{lasso} 
&= arg \min_\theta \frac{1}{n} ||Y - X\theta||^2 + \lambda ||\theta||_1 \\
\end{split}
$$

#### lasso as MAP optimizer
- [[linear model]] trained with a [[maximum aposteriori]] and parameters $\theta$ from a [[laplace distribution]]

$$
\theta \sim p(x)= \frac{\lambda}{2} e^{-\lambda |x|}
$$

$$
\begin{split}
\theta_{\mathrm{MAP}} 
&= \mathrm{arg} \max_\theta \log p\left(\theta|\mathcal{D}\right) \\
&= \mathrm{arg} \max_\theta \log p\left(\mathcal{D}|\theta\right)+\log p(\theta) \\
&= \mathrm{arg} \max_\theta \sum_{i=1}^n \log p\left(y_i|x_i, \theta\right)+\sum_{j=1}^d\log \frac{\lambda}{2} e^{-\lambda |\theta_j|} \\
&= \mathrm{arg} \max_\theta - \frac{1}{2\sigma^2}  \sum_{i=1}^n  \left(y_i-x_i^\top \theta\right)^2-\lambda \sum_{j=1}^d|\theta_j| \\
&= \mathrm{arg} \min_\theta \frac{1}{2}  \sum_{i=1}^n  \left(y_i-x_i^\top \theta\right)^2+\sigma^2\lambda ||\theta_j||_1 \\
&= \mathrm{arg} \min_\theta  \frac{n}{2} \mathrm{MSE}(Y,X\theta) ^2+\sigma^2\lambda ||\theta_j||_1 \\
&= \mathrm{arg} \min_\theta  \mathrm{MSE}(Y,X\theta) ^2+ \frac{2\sigma^2\lambda }{n} ||\theta_j||_1 \\
\end{split}
$$

# ------------

![[laplace distribution#laplace distribution]]

![[maximum aposteriori#maximum aposteriori]]


# --------------

START
Basic
[[lasso regression]]
- definition
- objective function
- analytical solution
- relationship to [[maximum aposteriori]] with proof
Back: 
### lasso regression
- [[linear model]] trained with a $L1$ regularization term
-  similar to [[ridge regression]] but with $L1$ [[norm]] instead of $L2$  
- there is no closed form solution
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
\hat\theta_\mathrm{lasso} 
&= arg \min_\theta \frac{1}{n} ||Y - X\theta||^2 + \lambda ||\theta||_1 \\
\end{split}
$$

#### lasso as MAP optimizer
- [[linear model]] trained with a [[maximum aposteriori]] and parameters $\theta$ from a [[laplace distribution]]

$$
\theta \sim p(x)= \frac{\lambda}{2} e^{-\lambda |x|}
$$

$$
\begin{split}
\theta_{\mathrm{MAP}} 
&= \mathrm{arg} \max_\theta \log p\left(\theta|\mathcal{D}\right) \\
&= \mathrm{arg} \max_\theta \log p\left(\mathcal{D}|\theta\right)+\log p(\theta) \\
&= \mathrm{arg} \max_\theta \sum_{i=1}^n \log p\left(y_i|x_i, \theta\right)+\sum_{j=1}^d\log \frac{\lambda}{2} e^{-\lambda |\theta_j|} \\
&= \mathrm{arg} \max_\theta - \frac{1}{2\sigma^2}  \sum_{i=1}^n  \left(y_i-x_i^\top \theta\right)^2-\lambda \sum_{j=1}^d|\theta_j| \\
&= \mathrm{arg} \min_\theta \frac{1}{2}  \sum_{i=1}^n  \left(y_i-x_i^\top \theta\right)^2+\sigma^2\lambda ||\theta_j||_1 \\
&= \mathrm{arg} \min_\theta  \frac{n}{2} \mathrm{MSE}(Y,X\theta) ^2+\sigma^2\lambda ||\theta_j||_1 \\
&= \mathrm{arg} \min_\theta  \mathrm{MSE}(Y,X\theta) ^2+ \frac{2\sigma^2\lambda }{n} ||\theta_j||_1 \\
\end{split}
$$

_______________

### maximum aposteriori
- [[bayesian inference]] given a [[empirical distribution of a dataset|dataset]] $\mathcal{D}$ with a [[probability density function (PDF)]] $f(\theta)$ and a model $\theta$ with a prior assumed distribution $f(\theta)$
- with a full [[bayesian inference]] approach we would model $f\left(\theta \mid \mathcal{D}\right)$ which would require to calculate $P(\mathcal{D})$ which is often not possible
- with the [[maximum aposteriori]] approach we train the model by maximizing the posterior $f\left(\theta \mid \mathcal{D}\right)$

$$
\overbrace{f\left(\theta \mid \mathcal{D}\right)}^\text{posterior}
= \frac{
\overbrace{f\left(\mathcal{D} \mid \theta\right)}^\text{likelihood}
\overbrace{f\left(\theta\right)}^\text{prior}
}
{
P(\mathcal{D})
}
$$

- for the [[maximum aposteriori]] estimation we have the following
- this works because 
	- we can assume the features $X$ to be constant and thus treat them as given
	- the [[logarithm]] is a [[monotonic function]] and thus does not change the argmax
	- the distribution of the data does not depend on the parameters

$$
\begin{split}
\theta_{MAP} 
&= arg\max_\theta f\left(\theta \mid \mathcal{D}\right) \\
&= arg\max_\theta \frac{f\left(\mathcal{D} \mid \theta\right)f\left(\theta\right)}{P(\mathcal{D})} \\
&= arg\max_\theta f\left(\mathcal{D} \mid \theta\right)f\left(\theta\right) \\
&= arg\max_\theta \log{ f\left(\mathcal{D} \mid \theta\right)f\left(\theta\right)} \\
&= arg\max_\theta \log{ f\left(\mathcal{D} \mid \theta\right)}+\log{f\left(\theta\right)} \\
&= arg\max_\theta \log{ f\left(Y \mid \theta, X\right)}+\log{f\left(\theta\right)} \\
\end{split}
$$
### laplace distribution

$$
f_X(x|\lambda) = \frac{\lambda}{2} e^{-\lambda |x|}
$$

Tags: mathematics basics SS25
<!--ID: 1752933658940-->
END