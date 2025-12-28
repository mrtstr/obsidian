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

### relationship to the vanilla optimizer
- in the following, we ignore the bias term and pretend the [[risk]] just depends on the weights $\mathcal{w}$ and compare the following optimizers

$$
\begin{split}
\mathcal{w}_\gamma &= \arg\min \mathcal{R}(\mathcal{w}) + \gamma \Omega(\mathcal{w}) \\
\widehat{\mathcal{w}} &= \arg\min \mathcal{R}(\mathcal{w}) \\
\end{split}
$$


- we have the following [[taylor series|taylor approximation]] of the [[risk]] function in the neighborhood of $\widehat{\mathcal{w}}$ 


$$
\begin{split}
\widehat{\mathcal{R}}(\mathcal{w}) 
&= \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) + \overbrace{\nabla_\mathcal{w} \widehat{\mathcal{R}}(\mathcal{w} - \widehat{\mathcal{w}})}^\text{vanishes near the minimum} + \frac{1}{2} (\mathcal{w} - \widehat{\mathcal{w}})^\top H (\mathcal{w} - \widehat{\mathcal{w}}) \\
H &= \nabla^2_\mathcal{w} \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) \\
\end{split}
$$

- we have the following approximation of the regularized [[risk]] 

$$
\begin{split}
\widehat{\mathcal{R}}_\gamma(\mathcal{w}) &= \widehat{\mathcal{R}}(\mathcal{w}) + \frac{\gamma}{2} ||\mathcal{w}||^2_2\\
\end{split}
$$

- when $\mathcal{w}_\gamma$ and $\widehat{\mathcal{w}}$ are sufficiently close, we can calculate the minimizer of the regularized [[risk]] as a function of the non-regularized [[risk]]

$$
\begin{split}
\nabla_\mathcal{w} \widehat{\mathcal{R}}_\gamma(\mathcal{w}) 
&= \nabla_\mathcal{w} \widehat{\mathcal{R}}(\mathcal{w}_\gamma) + \gamma\mathcal{w}_\gamma \\
&= H (\mathcal{w}_\gamma - \widehat{\mathcal{w}}) +  \gamma\mathcal{w}_\gamma\\
&= (H+I\gamma)\mathcal{w}_\gamma - H\widehat{\mathcal{w}}\\
&= 0 \\
\Rightarrow \mathcal{w}_\gamma &= (H+I\gamma)^{-1}H\widehat{\mathcal{w}}
\end{split}
$$

- let $H=Q\Lambda Q^\top$ be the [[eigendecomposition]] of $H$ with the [[orthogonal]] [[eigenvector|eigenbasis]] $Q$ and the [[diagonal matrix]] $\Lambda$ containing the [[eigenvalue]]  
- we have the following expression for the optimizer $\mathcal{w}_\gamma$

$$
\begin{split}
\mathcal{w}_\gamma 
&= (H+I\gamma)^{-1}H\widehat{\mathcal{w}} \\
&= (Q\Lambda Q^\top+I\gamma)^{-1}Q\Lambda Q^\top\widehat{\mathcal{w}} \\
&= Q(\Lambda +I\gamma)^{-1}Q^\top Q\Lambda Q^\top\widehat{\mathcal{w}} \\
&= Q(\Lambda +I\gamma)^{-1}\Lambda Q^\top\widehat{\mathcal{w}} \\
&= \sum_{i=1}^p \frac{\lambda_i}{\lambda_i + \gamma} \underbrace{\left(Q_{(*, i)}^\top \widehat{\mathcal{w}}\right)}_{\text{eigenspace projection}} Q_{(*, i)} \\
\end{split}
$$

- since $Q$ is a [[orthogonal matrix]] we can express the optimizer of unregularized [[risk]] as follows (see [[projection]])
- this shows that the [[nn l2 regularization]] is damping the weights with the factor of $\frac{\lambda_i}{\lambda_i + \gamma}$ in the direction of the [[eigenvector]] → unstable directions with small [[eigenvalue]] are suppressed while directions with large [[eigenvalue]] are not much impacted

$$
\begin{split}
\widehat{\mathcal{w}} 
&= QQ^\top \widehat{\mathcal{w}} \\
&= \sum_{i=1}^p  Q_{(*, i)}\underbrace{\left(Q_{(*, i)}^\top \widehat{\mathcal{w}} \right)}_{\text{eigenspace projection}} 
\end{split}
$$


# ----------------

![[frobenius norm#frobenius norm]]

![[regularization#regularization]]

# anki

START
Basic
[[nn l2 regularization]] summary
- objective function
- gradient
- update rule
Back: 
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

_________________

### relationship to the vanilla optimizer
- in the following, we ignore the bias term and pretend the [[risk]] just depends on the weights $\mathcal{w}$ and compare the following optimizers

$$
\begin{split}
\mathcal{w}_\gamma &= \arg\min \mathcal{R}(\mathcal{w}) + \gamma \Omega(\mathcal{w}) \\
\widehat{\mathcal{w}} &= \arg\min \mathcal{R}(\mathcal{w}) \\
\end{split}
$$


- we have the following [[taylor series|taylor approximation]] of the [[risk]] function in the neighborhood of $\widehat{\mathcal{w}}$ 


$$
\begin{split}
\widehat{\mathcal{R}}(\mathcal{w}) 
&= \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) + \overbrace{\nabla_\mathcal{w} \widehat{\mathcal{R}}(\mathcal{w} - \widehat{\mathcal{w}})}^\text{vanishes near the minimum} + \frac{1}{2} (\mathcal{w} - \widehat{\mathcal{w}})^\top H (\mathcal{w} - \widehat{\mathcal{w}}) \\
H &= \nabla^2_\mathcal{w} \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) \\
\end{split}
$$

- we have the following approximation of the regularized [[risk]] 

$$
\begin{split}
\widehat{\mathcal{R}}_\gamma(\mathcal{w}) &= \widehat{\mathcal{R}}(\mathcal{w}) + \frac{\gamma}{2} ||\mathcal{w}||^2_2\\
\end{split}
$$

- when $\mathcal{w}_\gamma$ and $\widehat{\mathcal{w}}$ are sufficiently close, we can calculate the minimizer of the regularized [[risk]] as a function of the non-regularized [[risk]]

$$
\begin{split}
\nabla_\mathcal{w} \widehat{\mathcal{R}}_\gamma(\mathcal{w}) 
&= \nabla_\mathcal{w} \widehat{\mathcal{R}}(\mathcal{w}_\gamma) + \gamma\mathcal{w}_\gamma \\
&= H (\mathcal{w}_\gamma - \widehat{\mathcal{w}}) +  \gamma\mathcal{w}_\gamma\\
&= (H+I\gamma)\mathcal{w}_\gamma - H\widehat{\mathcal{w}}\\
&= 0 \\
\Rightarrow \mathcal{w}_\gamma &= (H+I\gamma)^{-1}H\widehat{\mathcal{w}}
\end{split}
$$

- let $H=Q\Lambda Q^\top$ be the [[eigendecomposition]] of $H$ with the [[orthogonal]] [[eigenvector|eigenbasis]] $Q$ and the [[diagonal matrix]] $\Lambda$ containing the [[eigenvalue]]  
- we have the following expression for the optimizer $\mathcal{w}_\gamma$

$$
\begin{split}
\mathcal{w}_\gamma 
&= (H+I\gamma)^{-1}H\widehat{\mathcal{w}} \\
&= (Q\Lambda Q^\top+I\gamma)^{-1}Q\Lambda Q^\top\widehat{\mathcal{w}} \\
&= Q(\Lambda +I\gamma)^{-1}Q^\top Q\Lambda Q^\top\widehat{\mathcal{w}} \\
&= Q(\Lambda +I\gamma)^{-1}\Lambda Q^\top\widehat{\mathcal{w}} \\
&= \sum_{i=1}^p \frac{\lambda_i}{\lambda_i + \gamma} \underbrace{\left(Q_{(*, i)}^\top \widehat{\mathcal{w}}\right)}_{\text{eigenspace projection}} Q_{(*, i)} \\
\end{split}
$$

- since $Q$ is a [[orthogonal matrix]] we can express the optimizer of unregularized [[risk]] as follows (see [[projection]])
- this shows that the [[nn l2 regularization]] is damping the weights with the factor of $\frac{\lambda_i}{\lambda_i + \gamma}$ in the direction of the [[eigenvector]] → unstable directions with small [[eigenvalue]] are suppressed while directions with large [[eigenvalue]] are not much impacted

$$
\begin{split}
\widehat{\mathcal{w}} 
&= QQ^\top \widehat{\mathcal{w}} \\
&= \sum_{i=1}^p  Q_{(*, i)}\underbrace{\left(Q_{(*, i)}^\top \widehat{\mathcal{w}} \right)}_{\text{eigenspace projection}} 
\end{split}
$$

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


## bias complexity tradeoff
- the [[nn bias complexity tradeoff]] describes the relationship between the **error caused by the limited model [[function space]] $\mathcal{H}$** and the **error caused by the training process**

- let $\mathcal{S}=\{(x_1, y_1), ..., (x_m, y_m)\}$ be the [[training dataset]] and true [[data distribution]] $\mathcal{D}$ (often approximated using a large validation set)

$$
\begin{split}
 f_\mathcal{D} &= \arg\min_{f \in \mathcal{H}} \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f(x))\right] \\
 f_\mathcal{S} &= \arg\min_{f \in \mathcal{H}} \mathbb{E}_{(x, y) \sim \mathcal{S}}\left[\ell(y, f(x))\right] \\
 \end{split}
$$

- we can decompose the error in the **approximation error** or [[bias]] $\epsilon_\mathrm{app}$ and the **estimation error** $\epsilon_\mathrm{est}$
 
$$
\begin{split}
\mathcal{R}_\mathcal{D}(f_\mathcal{S}) 
&= \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f_\mathcal{S}(x))\right] \\
&= \underbrace{\mathcal{R}_\mathcal{D}(f_\mathcal{D})}_{\epsilon_\mathrm{app}} + \underbrace{ \mathcal{R}_\mathcal{D}(f_\mathcal{S}) -  \mathcal{R}_\mathcal{D}(f_\mathcal{D})}_{\epsilon_\mathrm{est}}   \\
\end{split}
$$

### tradeoff relationship
- if we increase the size of $\mathcal{H}$ the approximation error will decrease → decreases overall error
- but a more complex model can over fit the training dataset better → increases overall error

### approximation error
- error caused by the limited model [[function space]] $\mathcal{H}$
- $\epsilon_\mathrm{app}$ does not depend on the training data and thus is entirely dependent on the model architecture choice ([[function space]] of the model and [[parameter space]]) 
- error because the model is too small plus the noise or the data

$$
\epsilon_\mathrm{app} = \mathcal{R}_\mathcal{D}(f_\mathcal{D})
$$

- note: there exists a different definition of the approximation error where the noise is removed → difference between the best model in my [[hypothesis space]] minus the performance of the ideal model $f^*$ (which is equal to the noise of the data $\epsilon$)
- in this formulation approximation error is a generalized form of the [[bias]] for a general [[loss function]] (instead of the [[mean square error]])

$$
\begin{split}
\epsilon_\mathrm{app} &= \mathcal{R}_\mathcal{D}(f_\mathcal{D}) - \mathcal{R}_\mathcal{D}(f^*)\\
 f^* &= \arg\min_{f} \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f(x))\right]\\
 \mathcal{R}_\mathcal{D}(f^*) &=  \epsilon = \text{irreducable error} \\
 \end{split}
$$

### estimation error
- error caused in training procedure
- the estimation error $\epsilon_\mathrm{est}$ is the difference [[risk|true risk]] of the trained model and the [[risk|true risk]] of the optimal model in the [[function space]] $\mathcal{H}$

$$
\begin{split}
\epsilon_\mathrm{est}= \mathcal{R}_\mathcal{D}(f_\mathcal{S}) -  \mathcal{R}_\mathcal{D}(f_\mathcal{D})  \\
\end{split}
$$

- it is dependent on the **training data set**, the **model architecture** and the **leaning algorithm**
- for example can be caused by over fitting or limited data
- can be reduced by [[regularization]] and more training data



Tags: mathematics basics WS2526
<!--ID: 1766944220768-->
END


START
Basic
[[nn l2 regularization]]
- proof that the [[nn l2 regularization]] is damping the weights in the direction of low [[eigenvalue]]
Back: 

### relationship to the vanilla optimizer
- in the following, we ignore the bias term and pretend the [[risk]] just depends on the weights $\mathcal{w}$ and compare the following optimizers

$$
\begin{split}
\mathcal{w}_\gamma &= \arg\min \mathcal{R}(\mathcal{w}) + \gamma \Omega(\mathcal{w}) \\
\widehat{\mathcal{w}} &= \arg\min \mathcal{R}(\mathcal{w}) \\
\end{split}
$$


- we have the following [[taylor series|taylor approximation]] of the [[risk]] function in the neighborhood of $\widehat{\mathcal{w}}$ 


$$
\begin{split}
\widehat{\mathcal{R}}(\mathcal{w}) 
&= \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) + \overbrace{\nabla_\mathcal{w} \widehat{\mathcal{R}}(\mathcal{w} - \widehat{\mathcal{w}})}^\text{vanishes near the minimum} + \frac{1}{2} (\mathcal{w} - \widehat{\mathcal{w}})^\top H (\mathcal{w} - \widehat{\mathcal{w}}) \\
H &= \nabla^2_\mathcal{w} \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) \\
\end{split}
$$

- we have the following approximation of the regularized [[risk]] 

$$
\begin{split}
\widehat{\mathcal{R}}_\gamma(\mathcal{w}) &= \widehat{\mathcal{R}}(\mathcal{w}) + \frac{\gamma}{2} ||\mathcal{w}||^2_2\\
\end{split}
$$

- when $\mathcal{w}_\gamma$ and $\widehat{\mathcal{w}}$ are sufficiently close, we can calculate the minimizer of the regularized [[risk]] as a function of the non-regularized [[risk]]

$$
\begin{split}
\nabla_\mathcal{w} \widehat{\mathcal{R}}_\gamma(\mathcal{w}) 
&= \nabla_\mathcal{w} \widehat{\mathcal{R}}(\mathcal{w}_\gamma) + \gamma\mathcal{w}_\gamma \\
&= H (\mathcal{w}_\gamma - \widehat{\mathcal{w}}) +  \gamma\mathcal{w}_\gamma\\
&= (H+I\gamma)\mathcal{w}_\gamma - H\widehat{\mathcal{w}}\\
&= 0 \\
\Rightarrow \mathcal{w}_\gamma &= (H+I\gamma)^{-1}H\widehat{\mathcal{w}}
\end{split}
$$

- let $H=Q\Lambda Q^\top$ be the [[eigendecomposition]] of $H$ with the [[orthogonal]] [[eigenvector|eigenbasis]] $Q$ and the [[diagonal matrix]] $\Lambda$ containing the [[eigenvalue]]  
- we have the following expression for the optimizer $\mathcal{w}_\gamma$

$$
\begin{split}
\mathcal{w}_\gamma 
&= (H+I\gamma)^{-1}H\widehat{\mathcal{w}} \\
&= (Q\Lambda Q^\top+I\gamma)^{-1}Q\Lambda Q^\top\widehat{\mathcal{w}} \\
&= Q(\Lambda +I\gamma)^{-1}Q^\top Q\Lambda Q^\top\widehat{\mathcal{w}} \\
&= Q(\Lambda +I\gamma)^{-1}\Lambda Q^\top\widehat{\mathcal{w}} \\
&= \sum_{i=1}^p \frac{\lambda_i}{\lambda_i + \gamma} \underbrace{\left(Q_{(*, i)}^\top \widehat{\mathcal{w}}\right)}_{\text{eigenspace projection}} Q_{(*, i)} \\
\end{split}
$$

- since $Q$ is a [[orthogonal matrix]] we can express the optimizer of unregularized [[risk]] as follows (see [[projection]])
- this shows that the [[nn l2 regularization]] is damping the weights with the factor of $\frac{\lambda_i}{\lambda_i + \gamma}$ in the direction of the [[eigenvector]] → unstable directions with small [[eigenvalue]] are suppressed while directions with large [[eigenvalue]] are not much impacted

$$
\begin{split}
\widehat{\mathcal{w}} 
&= QQ^\top \widehat{\mathcal{w}} \\
&= \sum_{i=1}^p  Q_{(*, i)}\underbrace{\left(Q_{(*, i)}^\top \widehat{\mathcal{w}} \right)}_{\text{eigenspace projection}} 
\end{split}
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

_________________


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


## bias complexity tradeoff
- the [[nn bias complexity tradeoff]] describes the relationship between the **error caused by the limited model [[function space]] $\mathcal{H}$** and the **error caused by the training process**

- let $\mathcal{S}=\{(x_1, y_1), ..., (x_m, y_m)\}$ be the [[training dataset]] and true [[data distribution]] $\mathcal{D}$ (often approximated using a large validation set)

$$
\begin{split}
 f_\mathcal{D} &= \arg\min_{f \in \mathcal{H}} \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f(x))\right] \\
 f_\mathcal{S} &= \arg\min_{f \in \mathcal{H}} \mathbb{E}_{(x, y) \sim \mathcal{S}}\left[\ell(y, f(x))\right] \\
 \end{split}
$$

- we can decompose the error in the **approximation error** or [[bias]] $\epsilon_\mathrm{app}$ and the **estimation error** $\epsilon_\mathrm{est}$
 
$$
\begin{split}
\mathcal{R}_\mathcal{D}(f_\mathcal{S}) 
&= \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f_\mathcal{S}(x))\right] \\
&= \underbrace{\mathcal{R}_\mathcal{D}(f_\mathcal{D})}_{\epsilon_\mathrm{app}} + \underbrace{ \mathcal{R}_\mathcal{D}(f_\mathcal{S}) -  \mathcal{R}_\mathcal{D}(f_\mathcal{D})}_{\epsilon_\mathrm{est}}   \\
\end{split}
$$

### tradeoff relationship
- if we increase the size of $\mathcal{H}$ the approximation error will decrease → decreases overall error
- but a more complex model can over fit the training dataset better → increases overall error

### approximation error
- error caused by the limited model [[function space]] $\mathcal{H}$
- $\epsilon_\mathrm{app}$ does not depend on the training data and thus is entirely dependent on the model architecture choice ([[function space]] of the model and [[parameter space]]) 
- error because the model is too small plus the noise or the data

$$
\epsilon_\mathrm{app} = \mathcal{R}_\mathcal{D}(f_\mathcal{D})
$$

- note: there exists a different definition of the approximation error where the noise is removed → difference between the best model in my [[hypothesis space]] minus the performance of the ideal model $f^*$ (which is equal to the noise of the data $\epsilon$)
- in this formulation approximation error is a generalized form of the [[bias]] for a general [[loss function]] (instead of the [[mean square error]])

$$
\begin{split}
\epsilon_\mathrm{app} &= \mathcal{R}_\mathcal{D}(f_\mathcal{D}) - \mathcal{R}_\mathcal{D}(f^*)\\
 f^* &= \arg\min_{f} \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f(x))\right]\\
 \mathcal{R}_\mathcal{D}(f^*) &=  \epsilon = \text{irreducable error} \\
 \end{split}
$$

### estimation error
- error caused in training procedure
- the estimation error $\epsilon_\mathrm{est}$ is the difference [[risk|true risk]] of the trained model and the [[risk|true risk]] of the optimal model in the [[function space]] $\mathcal{H}$

$$
\begin{split}
\epsilon_\mathrm{est}= \mathcal{R}_\mathcal{D}(f_\mathcal{S}) -  \mathcal{R}_\mathcal{D}(f_\mathcal{D})  \\
\end{split}
$$

- it is dependent on the **training data set**, the **model architecture** and the **leaning algorithm**
- for example can be caused by over fitting or limited data
- can be reduced by [[regularization]] and more training data



Tags: mathematics basics WS2526
<!--ID: 1766944220771-->
END
