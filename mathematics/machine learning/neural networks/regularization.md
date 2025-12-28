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


# ------------------

![[nn bias complexity tradeoff#bias complexity tradeoff]]


# anki

START
Basic
two approaches of for preventing over fitting
- plus one example: when it is needed and how to do it
Back: 
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
_________________

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
<!--ID: 1766390400611-->
END

START
Basic
**representational capacity** and the **effective capacity** of a model
- definition 
- what are they depending on
Back: 
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
_________________

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
<!--ID: 1766390400616-->
END