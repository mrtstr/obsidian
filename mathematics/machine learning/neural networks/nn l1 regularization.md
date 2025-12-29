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

$$
\begin{split}
\nabla_\mathcal{w} \mathcal{R}_\gamma(\theta) = \nabla_\mathcal{w} \mathcal{R}(\theta) + \gamma\mathrm{sign}(\mathcal{w})
\end{split}
$$


