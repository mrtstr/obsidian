## l1 regularization
- given a [[neural network]] with the parameters $\theta$
- we introduce a penalty term $\Omega(\theta)$ with a weight factor $\gamma$ that penalized the size of the parameters of the weight metrics $W^{1}, ..., W^{L}$
- we ignore the bias term here because they are not prone to over fitting

$$
\begin{split}
\Omega(\theta) 
= ||\mathcal{w}||_1 = \sum_{i=1}^p |\mathcal{w}_i|
\end{split}
$$

- we minimize the following objective function consisting of the [[risk]] and the penalty term 

$$
\begin{split}
\theta_\gamma = \underbrace{\arg\min \mathcal{R}(\theta) + \gamma \Omega(\theta)}_{\mathcal{R}_\gamma(\theta)}
\end{split}
$$

- resulting in the following [[gradient]] of the [[risk]] with respect to the weights
- however, we can't solve this analytically

$$
\begin{split}
\nabla_\mathcal{w} \mathcal{R}_\gamma(\theta) = \nabla_\mathcal{w} \mathcal{R}(\theta) + \gamma\mathrm{sign}(\mathcal{w})
\end{split}
$$

- using the [[nn quadratic loss model]] we have the following problem that we want to solve
- we assume that the [[hessian matrix]] $H$ is a [[diagonal matrix]] to simplify the expression as follows

$$
\begin{split}
\mathcal{w}_\gamma &=\arg\min_\mathcal{w}\widehat{\mathcal{R}}_\gamma(\mathcal{w}) \\
&=\arg\min_\mathcal{w} \mathcal{R}(\widehat{\mathcal{w}}) + \frac{1}{2}  (\mathcal{w} - \widehat{\mathcal{w}})H (\mathcal{w} - \widehat{\mathcal{w}})  + \gamma||\mathcal{w}||_1 \\
&=\arg\min_\mathcal{w}   \sum_i \frac{1}{2} H_{ii} (\mathcal{w}_i - \widehat{\mathcal{w}}_i)^2 + \gamma|\mathcal{w}_i| \\
&=\arg\min_\mathcal{w}   \sum_i \frac{1}{2}  (\mathcal{w}_i - \widehat{\mathcal{w}}_i)^2 + \frac{\gamma}{H_{ii}}|\mathcal{w}_i| \\
\end{split}
$$

$$
\begin{split}
\frac{\partial}{\partial {\mathcal{w}}_i} \sum_i \frac{1}{2}  (\mathcal{w}_i - \widehat{\mathcal{w}}_i)^2 + \frac{\gamma}{H_{ii}}|\mathcal{w}_i|
&= \mathcal{w}_i - \widehat{\mathcal{w}}_i + \frac{\gamma}{H_ii} \mathrm{sign}(\mathcal{w}_i) = 0\\
\Rightarrow  \mathcal{w}_i =  \widehat{\mathcal{w}}_i - \frac{\gamma}{H_ii} \mathrm{sign}(\mathcal{w}_i)
\end{split}
$$

- case $w_i > 0$

$$
\begin{split}
\mathcal{w}_i - \widehat{\mathcal{w}}_i + \frac{\gamma}{H_ii}  = 0\\
\Rightarrow {(\mathcal{w}_\gamma)}_i = \widehat{\mathcal{w}}_i - \frac{\gamma}{H_ii} \\
w_i > 0\Rightarrow  \widehat{\mathcal{w}}_i > \frac{\gamma}{H_ii} \\
\end{split}
$$

- case $w_i < 0$

$$
\begin{split}
\mathcal{w}_i - \widehat{\mathcal{w}}_i - \frac{\gamma}{H_ii}  = 0\\
\Rightarrow {(\mathcal{w}_\gamma)}_i = \widehat{\mathcal{w}}_i + \frac{\gamma}{H_ii} \\
w_i < 0\Rightarrow  \widehat{\mathcal{w}}_i < - \frac{\gamma}{H_ii} \\
\end{split}
$$

- case $w_i = 0$

$$
\begin{split}
{(\mathcal{w}_\gamma)}_i
&=\begin{cases}
\widehat{\mathcal{w}}_i - \frac{\gamma}{H_{ii}} &if \  \widehat{\mathcal{w}}_i > \frac{\gamma}{H_{ii}}\\
0 &if \  \widehat{\mathcal{w}}_i \leq \left|\frac{\gamma}{H_{ii}}\right|\\
\widehat{\mathcal{w}}_i + \frac{\gamma}{H_{ii}}&if \  \widehat{\mathcal{w}}_i < - \frac{\gamma}{H_{ii}}\\
\end{cases}  \\
&= \mathrm{sign}(\widehat{\mathcal{w}}_i) \max\left(|\widehat{\mathcal{w}}_i|- \frac{\gamma}{H_{ii}}, 0\right)
\end{split}
$$


![[nn quadratic loss model#quadratic loss model]]


# anki

START
Basic
[[nn l1 regularization]]
- loss function
- solution with assumptions
Back: 
## l1 regularization
- given a [[neural network]] with the parameters $\theta$
- we introduce a penalty term $\Omega(\theta)$ with a weight factor $\gamma$ that penalized the size of the parameters of the weight metrics $W^{1}, ..., W^{L}$
- we ignore the bias term here because they are not prone to over fitting

$$
\begin{split}
\Omega(\theta) 
= ||\mathcal{w}||_1 = \sum_{i=1}^p |\mathcal{w}_i|
\end{split}
$$

- we minimize the following objective function consisting of the [[risk]] and the penalty term 

$$
\begin{split}
\theta_\gamma = \underbrace{\arg\min \mathcal{R}(\theta) + \gamma \Omega(\theta)}_{\mathcal{R}_\gamma(\theta)}
\end{split}
$$

- resulting in the following [[gradient]] of the [[risk]] with respect to the weights
- however, we can't solve this analytically

$$
\begin{split}
\nabla_\mathcal{w} \mathcal{R}_\gamma(\theta) = \nabla_\mathcal{w} \mathcal{R}(\theta) + \gamma\mathrm{sign}(\mathcal{w})
\end{split}
$$

- using the [[nn quadratic loss model]] we have the following problem that we want to solve
- we assume that the [[hessian matrix]] $H$ is a [[diagonal matrix]] to simplify the expression as follows

$$
\begin{split}
\mathcal{w}_\gamma &=\arg\min_\mathcal{w}\widehat{\mathcal{R}}_\gamma(\mathcal{w}) \\
&=\arg\min_\mathcal{w} \mathcal{R}(\widehat{\mathcal{w}}) + \frac{1}{2}  (\mathcal{w} - \widehat{\mathcal{w}})H (\mathcal{w} - \widehat{\mathcal{w}})  + \gamma||\mathcal{w}||_1 \\
&=\arg\min_\mathcal{w}   \sum_i \frac{1}{2} H_{ii} (\mathcal{w}_i - \widehat{\mathcal{w}}_i)^2 + \gamma|\mathcal{w}_i| \\
&=\arg\min_\mathcal{w}   \sum_i \frac{1}{2}  (\mathcal{w}_i - \widehat{\mathcal{w}}_i)^2 + \frac{\gamma}{H_{ii}}|\mathcal{w}_i| \\
\end{split}
$$

$$
\begin{split}
\frac{\partial}{\partial {\mathcal{w}}_i} \sum_i \frac{1}{2}  (\mathcal{w}_i - \widehat{\mathcal{w}}_i)^2 + \frac{\gamma}{H_{ii}}|\mathcal{w}_i|
&= \mathcal{w}_i - \widehat{\mathcal{w}}_i + \frac{\gamma}{H_ii} \mathrm{sign}(\mathcal{w}_i) = 0\\
\Rightarrow  \mathcal{w}_i =  \widehat{\mathcal{w}}_i - \frac{\gamma}{H_ii} \mathrm{sign}(\mathcal{w}_i)
\end{split}
$$

- case $w_i > 0$

$$
\begin{split}
\mathcal{w}_i - \widehat{\mathcal{w}}_i + \frac{\gamma}{H_ii}  = 0\\
\Rightarrow {(\mathcal{w}_\gamma)}_i = \widehat{\mathcal{w}}_i - \frac{\gamma}{H_ii} \\
w_i > 0\Rightarrow  \widehat{\mathcal{w}}_i > \frac{\gamma}{H_ii} \\
\end{split}
$$

- case $w_i < 0$

$$
\begin{split}
\mathcal{w}_i - \widehat{\mathcal{w}}_i - \frac{\gamma}{H_ii}  = 0\\
\Rightarrow {(\mathcal{w}_\gamma)}_i = \widehat{\mathcal{w}}_i + \frac{\gamma}{H_ii} \\
w_i < 0\Rightarrow  \widehat{\mathcal{w}}_i < - \frac{\gamma}{H_ii} \\
\end{split}
$$

- case $w_i = 0$

$$
\begin{split}
{(\mathcal{w}_\gamma)}_i
&=\begin{cases}
\widehat{\mathcal{w}}_i - \frac{\gamma}{H_{ii}} &if \  \widehat{\mathcal{w}}_i > \frac{\gamma}{H_{ii}}\\
0 &if \  \widehat{\mathcal{w}}_i \leq \left|\frac{\gamma}{H_{ii}}\right|\\
\widehat{\mathcal{w}}_i + \frac{\gamma}{H_{ii}}&if \  \widehat{\mathcal{w}}_i < - \frac{\gamma}{H_{ii}}\\
\end{cases}  \\
&= \mathrm{sign}(\widehat{\mathcal{w}}_i) \max\left(|\widehat{\mathcal{w}}_i|- \frac{\gamma}{H_{ii}}, 0\right)
\end{split}
$$

_________________

### quadratic loss model
- using the [[taylor series|taylor approximation]] of the [[risk]] function in the neighborhood of $\widehat{\mathcal{w}}$ we have the following quadratic model that is valid near $\widehat{\mathcal{w}}$

$$
\begin{split}
\widehat{\mathcal{R}}(\mathcal{w}) 
&= \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) + \overbrace{\nabla_\mathcal{w} \widehat{\mathcal{R}}^\top(\mathcal{w} - \widehat{\mathcal{w}})}^\text{vanishes near the minimum} + \frac{1}{2} (\mathcal{w} - \widehat{\mathcal{w}})^\top H (\mathcal{w} - \widehat{\mathcal{w}}) \\
H &= \nabla^2_\mathcal{w} \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) \\
\end{split}
$$

- the [[nn quadratic loss model]] has the following [[gradient]] with the [[eigendecomposition]] of the [[hessian]] $H=Q\Lambda Q^\top$

$$
\begin{split}
\nabla\widehat{\mathcal{R}}(\mathcal{w}) 
&=  H (\mathcal{w} - \widehat{\mathcal{w}}) \\
&=  Q\Lambda Q^\top (\mathcal{w} - \widehat{\mathcal{w}}) \\

\end{split}
$$

### update rule of the quadratic loss model
- update rule of the [[nn quadratic loss model]]

$$
\begin{split}
\mathcal{w}^{(t)} 
&= \mathcal{w}^{(t-1)}  - \alpha \nabla\mathcal{R}\left(\mathcal{w}^{(t-1)} \right) \\
&= \mathcal{w}^{(t-1)}  - \alpha H\left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right) \\
&= QQ^\top\mathcal{w}^{(t-1)}  - \alpha Q\Lambda Q^\top  \left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right) \\
Q^\top\mathcal{w}^{(t)}  
&= Q^\top\mathcal{w}^{(t-1)}  - \alpha \Lambda Q^\top  \left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right) \\
&= Q^\top\mathcal{w}^{(t-1)}  - \alpha \Lambda Q^\top  \mathcal{w}^{(t-1)} +\alpha \Lambda Q^\top\widehat{\mathcal{w}} \\
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(t-1)} +\alpha \Lambda Q^\top\widehat{\mathcal{w}} \\
Q^\top\left(\mathcal{w}^{(t)} -\widehat{\mathcal{w}}\right) 
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(t-1)} +\alpha \Lambda Q^\top\widehat{\mathcal{w}} - Q^\top\widehat{\mathcal{w}}  \\
&=  \left(I -\alpha \Lambda\right) Q^\top  \left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right)   \\
\end{split}
$$
- when projected in the eigenspace the difference to the optimum is decreasing by a factor of $\left(1 -\alpha \lambda_i\right)$ in every step in the direction of the [[eigenvector]] of the [[eigenvalue]] $\lambda_i$

$$
\begin{split}
Q_{(:,i)}^\top\left(\mathcal{w}^{(t)} -\widehat{\mathcal{w}}\right) 
&=  \left(1 -\alpha \lambda_i\right) Q_{(:,i)}^\top  \left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right)   \\
\end{split}
$$

- assuming $\mathcal{w}^{(0)}=0$ we can derive the following closed form of the update rule for the [[nn quadratic loss model]]

$$
\begin{split}
Q^\top \mathcal{w}^{(t)} 
&=  \left(I -\alpha \Lambda\right) Q^\top  \left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right) + Q^\top  \widehat{\mathcal{w}}\\ 
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(t-1)} -\left(I -\alpha \Lambda\right) Q^\top\widehat{\mathcal{w}} + Q^\top  \widehat{\mathcal{w}}\\ 
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(t-1)} +\left(I-\left(I -\alpha \Lambda\right)\right) Q^\top\widehat{\mathcal{w}} \\ 
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(t-1)} +\alpha \Lambda Q^\top\widehat{\mathcal{w}} \\ 
Q^\top\mathcal{w}^{(1)}  
&=  \alpha \Lambda Q^\top\widehat{\mathcal{w}}  \\
Q^\top \mathcal{w}^{(2)} 
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(1)} +\alpha \Lambda Q^\top\widehat{\mathcal{w}}  \\ 
&=  \left(I -\alpha \Lambda\right) \alpha \Lambda Q^\top\widehat{\mathcal{w}} +\alpha \Lambda Q^\top\widehat{\mathcal{w}}  \\ 
&=  \left(I+\left(I -\alpha \Lambda\right)\right) \alpha \Lambda Q^\top\widehat{\mathcal{w}}   \\ 
Q^\top \mathcal{w}^{(3)} 
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(2)} +\alpha \Lambda Q^\top\widehat{\mathcal{w}}  \\ 
&=  \left(I -\alpha \Lambda\right) \left(\left(I -\alpha \Lambda\right) \alpha \Lambda Q^\top\widehat{\mathcal{w}} +\alpha \Lambda Q^\top\widehat{\mathcal{w}}\right) +\alpha \Lambda Q^\top\widehat{\mathcal{w}}  \\ 
&=   \left(I -\alpha \Lambda\right)^2 \alpha \Lambda Q^\top\widehat{\mathcal{w}} +\left(I -\alpha \Lambda\right)\alpha \Lambda Q^\top\widehat{\mathcal{w}} +\alpha \Lambda Q^\top\widehat{\mathcal{w}}  \\ 
&=   \left(I -\alpha \Lambda\right)^2 \alpha \Lambda Q^\top\widehat{\mathcal{w}} +\left(I -\alpha \Lambda\right)\alpha \Lambda Q^\top\widehat{\mathcal{w}} +\left(I -\alpha \Lambda\right)^0\alpha \Lambda Q^\top\widehat{\mathcal{w}}  \\ 
&= \sum_{i=0}^2  \left(I -\alpha \Lambda\right)^i \alpha \Lambda Q^\top\widehat{\mathcal{w}}   \\ 
Q^\top \mathcal{w}^{(t)} 
&= \sum_{i=0}^{t-1}  \left(I -\alpha \Lambda\right)^i \alpha \Lambda Q^\top\widehat{\mathcal{w}}   \\ 
&= \left( I - \left(I -\alpha \Lambda\right)\right)^{-1}\left( I - \left(I -\alpha \Lambda\right)^t \right) \alpha \Lambda Q^\top\widehat{\mathcal{w}}   \\ 
&= \left(\alpha \Lambda\right)^{-1}\left( I - \left(I -\alpha \Lambda\right)^t \right) \alpha \Lambda Q^\top\widehat{\mathcal{w}}   \\ 
&= \left( I - \left(I -\alpha \Lambda\right)^t \right)  Q^\top\widehat{\mathcal{w}}   \\ 
\end{split}
$$

- in the dimension $i$ of the eigenspace, we reach the optimum $\widehat{\mathcal{w}}$ as $\left(1 -\alpha \lambda_i\right)^t \to_{t \to \infty} 0$ for $\lambda_i > 0$ and a small enough learning rate $\alpha$

$$
\begin{split}
Q_{(:,i)}^\top \mathcal{w}^{(t)} 
&= \left( 1 - \left(1 -\alpha \lambda_i\right)^t \right)  Q_{(:,i)}^\top\widehat{\mathcal{w}}   \\ 
\end{split}
$$

- to ensure convergence the following condition must hold for all eigenvalues $\lambda_i$

$$
|1 -\alpha \lambda_i| < 1 \Rightarrow 0 < \alpha < \frac{1}{\lambda_i}
$$

## l2 regularization
- given a [[neural network]] with the parameters $\theta$
- we introduce a penalty term $\Omega(\theta)$ with a weight factor $\gamma$ that penalized the size of the parameters of the weight metrics $W^{1}, ..., W^{L}$
- we ignore the bias term here because they are not prone to over fitting

$$
\begin{split}
\Omega(\theta) 
= \sum_{l=1}^L \frac{1}{2} ||W^{{l}}||^2_F 
= \sum_{l=1}^L \frac{1}{2} \sum_{i=1}^{n_l} \sum_{j=1}^{n_{l-1}} \left(W_{ij}^{(l)}\right)^2 = \frac{1}{2}||\mathcal{w}||^2_2
\end{split}
$$

- we minimize the following objective function consisting of the [[risk]] and the penalty term 

$$
\begin{split}
\theta_\gamma = \underbrace{\arg\min \mathcal{R}(\theta) + \gamma \Omega(\theta)}_{\mathcal{R}_\gamma(\theta)}
\end{split}
$$

- resulting in the following [[gradient]] of the [[risk]] with respect to the weights

$$
\begin{split}
\nabla_\mathcal{w} \mathcal{R}_\gamma(\theta) = \nabla_\mathcal{w} \mathcal{R}(\theta) + \gamma\mathcal{w}
\end{split}
$$

- plugging in the gradient in the [[gradient descent]] update rule yields the following weight update

$$
\begin{split}
\mathcal{w}^{(t+1)} 
&= \mathcal{w}^{(t)} - \alpha \nabla_\mathcal{w} \mathcal{R}_\gamma(\theta) \\
&= \mathcal{w}^{(t)} - \alpha \left(\nabla_\mathcal{w} \mathcal{R}(\theta) + \gamma\mathcal{w}^{(t)}\right) \\
&= \mathcal{w}^{(t)} \left(1-\alpha \gamma\right) - \alpha \nabla_\mathcal{w} \mathcal{R}(\theta) \\
\end{split}
$$

- in every step the size of the weights are damped by the factor $\left(1-\alpha \gamma\right)$
## regularization
- during training of a [[neural network]] we are minimizing the training [[risk]] but at the same time we also want the training error ([[risk]] on the training set) to be not too much different from the true [[risk]] (based on the true [[data distribution]])
- [[regularization]] methods reduce the discrepancy between the error on the training dataset and the true error 

- classic approach: start with a simple model and increase complexity until the performance doesn't improve
- modern approach: distinguish between the **representational capacity** and the **effective capacity** → focus on the effective capacity by adapting the learning algorithm ([[regularization]])

- when the **representational capacity** is much larger than the amount of training data available regularization can force the training algorithm to find models with lower **effective capacity** within the [[hypothesis space]]
	→ for example for a good estimation we need about one sample per parameter but if we have a large [[neural network]] with not much training data we can penalize the parameters size with a penalty term $\Omega(\theta)$ such that the number of effective (non-zero) parameters is smaller

$$
\begin{split}
\theta_\gamma \in \underbrace{\arg\min \mathcal{R}(\theta) + \gamma \Omega(\theta)}_{\mathcal{R}_\gamma(\theta)}
\end{split}
$$
#### representational capacity
- overall size of the [[hypothesis space]] $\mathcal{H}$ → variety of functions the model architecture is mathematically capable of approximating
- theoretical upper limit or the models power
- depends only on $\mathcal{H}$
#### effective capacity
- range of functions that the learning algorithm actually can find
- is a subset of the representational capacity
- depends on $\mathcal{H}$, the learning algorithm and the data




Tags: mathematics WS2526
<!--ID: 1767114100266-->
END
