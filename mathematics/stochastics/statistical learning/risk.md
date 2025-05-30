### risk
- the [[risk]] is the [[expectation|expected]] [[loss function|loss]] over the entire [[data distribution]] $\mathcal{P}_{XY}$
- given a [[loss function]] $L(y, \hat{y})$ the [[risk]] is defined as following

$$
\begin{split}
\mathcal{R}(\theta) 
&= \mathbb{E}_{(x,y) \sim \mathcal{P}_{XY}}\left[L\left(f_\theta(x), y\right)\right] \\
\end{split}
$$

#### empirical risk
- the empirical [[risk]] is the approximation of the true [[risk]] and using the [[training dataset]] $\mathcal{D}_{train}=\{(x_i, y_i): i \in [n]\}$

$$
\begin{split}
\mathcal{\hat{R}}(\theta) 
&= \frac{1}{n} \sum_{i=1}^n L\left(f_\theta(x_i), y_i\right) \\
\end{split}
$$

#### bayes risk
- given a [[hypothesis space]] $\mathcal{H}$ and the optimal model $\theta^*=arg\min_{\theta \in \mathcal{H}} \mathcal{R}(\theta)$ 

$$
\mathcal{R}^*=\mathcal{R}(\theta^*)=\min_{\theta \in \mathcal{H}}\mathcal{R}(\theta)
$$
#### excess risk
- given a [[hypothesis space]] $\mathcal{H}$ and with the bayes [[risk]] $\mathcal{R}^*$
- the excess risk for a model $\theta \in \mathcal{H}$ is defined as follows

$$
\begin{split}
\mathcal{R}_{excess}(\theta) = \mathcal{{R}}(\theta) - \mathcal{R}^*
\end{split}
$$

# ------------

![[loss function#loss function]]

![[data distribution#data distribution]]


# anki

START
Basic
definitions for
- [[loss function]]
- [[risk]]
- empirical risk
- bayes risk
- excess risk

Back: 

### loss function
- the [[loss function]] is a non-negative [[function]] $L: \mathcal{Y} \times \mathcal{\hat{Y}} \to [0, \infty]$ that measures how much the model output $f(x_i)=\hat{y_i}$ differs from the label $y$

### risk
- the [[risk]] is the [[expectation|expected]] [[loss function|loss]] over the entire [[data distribution]] $\mathcal{P}_{XY}$
- given a [[loss function]] $L(y, \hat{y})$ the [[risk]] is defined as following

$$
\begin{split}
\mathcal{R}(\theta) 
&= \mathbb{E}_{(x,y) \sim \mathcal{P}_{XY}}\left[L\left(f_\theta(x), y\right)\right] \\
\end{split}
$$

### empirical risk
- the empirical [[risk]] is the approximation of the true [[risk]] and using the [[training dataset]] $\mathcal{D}_{train}=\{(x_i, y_i): i \in [n]\}$

$$
\begin{split}
\mathcal{\hat{R}}(\theta) 
&= \frac{1}{n} \sum_{i=1}^n L\left(f_\theta(x_i), y_i\right) \\
\end{split}
$$

### bayes risk
- given a [[hypothesis space]] $\mathcal{H}$ and the optimal model $\theta^*=arg\min_{\theta \in \mathcal{H}} \mathcal{R}(\theta)$ 

$$
\mathcal{R}^*=\mathcal{R}(\theta^*)=\min_{\theta \in \mathcal{H}}\mathcal{R}(\theta)
$$
### excess risk
- given a [[hypothesis space]] $\mathcal{H}$ and with the bayes [[risk]] $\mathcal{R}^*$
- the excess risk for a model $\theta \in \mathcal{H}$ is defined as follows

$$
\begin{split}
\mathcal{R}_{excess}(\theta) = \mathcal{{R}}(\theta) - \mathcal{R}^*
\end{split}
$$
______________
### data distribution
- the [[data distribution]] is the [[joint distribution]] of the [[input and output space]] of a model
- given the [[probability space]] 
	- input $(\mathcal{X}, \mathcal{A}_X, \mathcal{P}_X)$  
	- output $(\mathcal{Y}, \mathcal{A_Y}, \mathcal{P}_Y)$ 
- the [[data distribution]] $\mathcal{P}_{XY}$ is the joint [[probability measure]] over the [[product measure space|product measurable space]] $(\mathcal{X} \times \mathcal{Y}, \mathcal{A_X} \otimes \mathcal{A_Y})$
- given a dataset $\mathcal{D}_0 \subset \mathcal{X} \times \mathcal{Y}$ its [[empirical distribution of a dataset|empirical distribution]] $\mathcal{\hat{P}}_{XY}$ is defined as follows with the [[dirac measure]] $\delta$ 

$$
\mathcal{\hat P}_{XY}(A) = \frac{1}{n} \sum_{i=1}^n \delta_{(x_i, y_i)}(A)
$$

### input and output space
- the [[input and output space]] $(\mathcal{X}, \mathcal{A}_X, \mathcal{P}_X)$ and $(\mathcal{Y}, \mathcal{A_Y}, \mathcal{P}_Y)$ are [[probability space]] of the inputs and outputs of a model $f_\theta: \mathcal{X} \to \mathcal{Y}$ 
- given a dataset $\mathcal{D}_X \subset \mathcal{X}$ or $\mathcal{D}_Y \subset \mathcal{Y}$ its [[probability measure]] can be approximated using the [[empirical distribution of a dataset]]



Tags: mathematics statistics SS25
<!--ID: 1746870898945-->
END