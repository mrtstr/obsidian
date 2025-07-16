### generalization gap
- let $\mathcal{D}_\mathrm{train} \subset \mathcal{D}$ be a **finite training dataset** sampled i.i.d. from the [[data distribution]] $\mathcal{D}$
- let $\mathcal{L}$ be a [[loss function]] with the population [[risk]] $\mathcal{R}$ on the full dataset and the empirical [[risk]] $\mathcal{\hat{R}}$ estimated on the training dataset

$$
\begin{split}
\mathcal{R}(\theta) 
&= \mathbb{E}_{(x,y) \sim \mathcal{D}}\left[\mathcal{L}\left(f_\theta(x), y\right)\right] \\
\mathcal{\hat{R}}(\theta) 
&= \mathbb{E}_{(x,y) \sim \mathcal{D}_\mathrm{train}}\left[\mathcal{L}\left(f_\theta(x), y\right)\right] = \frac{1}{n} \sum_{i=1}^n \mathcal{L}\left(f_\theta(x_i), y_i\right) \\
\end{split}
$$

- let $\theta^*$ and $\theta_\mathrm{train}$ be the empirical and true [[risk]] minimizer 

$$
\begin{split}
\theta^* &= \mathrm{argmin}_{\theta \in \mathcal{H}} \: \mathbb{E}_\mathcal{D}\left[\mathcal{L}(X, Y, \theta)\right] &\quad\text{(true risk minimizer)} \\
\theta_\mathrm{train} &= \mathrm{argmin}_{\theta \in \mathcal{H}}  \: \mathbb{E}_{\mathcal{D}_\mathrm{train}}\left[\mathcal{L}(X, Y, \theta)\right] &\quad\text{(empirical risk minimizer)} \\
\end{split}
$$

- on the training set the **empirical risk minimizer** leads to a smaller risk than the **true risk minimizer**

$$
\begin{split}
\mathcal{\hat{R}}(\theta_\mathrm{train})  < \mathcal{\hat{R}}(\theta^*) 
\end{split}
$$

- but on the complete data distribution, the **empirical risk minimizer** performes better

$$
\begin{split}
\mathcal{R}(\theta_\mathrm{train})  > \mathcal{R}(\theta^*) 
\end{split}
$$

- the [[generalization gap]] is the difference between the true risk and the empirical risk and is caused by over fitting the limited number of training sames $n = |\mathcal{D}_\mathrm{train}|$

$$
\begin{split}
\mathcal{R}(\theta_\mathrm{train}) - \mathcal{\hat{R}}(\theta_\mathrm{train}) \geq 0
\end{split}
$$

#### maximum likelihood
- the log [[likelihood function]] based the [[empirical distribution of a dataset|test dataset]] which contains $M$ samples from a true [[distribution]] $P_{\theta^*}$ 
- note: here we assume that $M$ is large enough that we will find the true [[distribution]]

$$
\begin{split}
\mathbb{E}_{\mathcal{D}\sim P_{\theta^*}}\left[{\mathcal{L}}(\theta)\right]
&=\mathbb{E}_{\mathcal{D}\sim P_\theta^*}\left[\log\left(p\left(\mathcal{D}_Y|\mathcal{D}_X, \theta\right)\right)\right] \\
&=\sum_{m=1}^M \mathbb{E}_{(X_m, Y_m)\sim P_{\theta^*}}\left[\log\left(p\left(Y_m|X_m, \theta\right)\right)\right] \\
&=M \mathbb{E}_{(X, Y)\sim P_{\theta^*}}\left[\log\left(p\left(Y|X, \theta\right)\right)\right] \\
\end{split}
$$


- but instead we maximize the [[likelihood function]] on the a [[empirical distribution of a dataset|training dataset]] which contains $N$ samples from the same true [[distribution]] $P_{\theta^*}$ 

$$
\begin{split}
\theta_{MLE}
&=\mathrm{arg}\max_\theta\sum_{m=1}^N \log\left(p\left(Y_n|X_n, \theta\right)\right) \\

\end{split}
$$

![[kl divergence#kl divergence and maximum likelihood]]

# -------------

![[risk#risk]]


![[data distribution#data distribution]]


# anki

START
Basic
[[generalization gap]]
- definition and related concepts
- population [[risk]] vs empirical [[risk]]
- what causes the [[generalization gap]]?

Back: 
### generalization gap
- let $\mathcal{D}_\mathrm{train} \subset \mathcal{D}$ be a **finite training dataset** sampled i.i.d. from the [[data distribution]] $\mathcal{D}$
- let $\mathcal{L}$ be a [[loss function]] with the population [[risk]] $\mathcal{R}$ on the full dataset and the empirical [[risk]] $\mathcal{\hat{R}}$ estimated on the training dataset

$$
\begin{split}
\mathcal{R}(\theta) 
&= \mathbb{E}_{(x,y) \sim \mathcal{D}}\left[\mathcal{L}\left(f_\theta(x), y\right)\right] \\
\mathcal{\hat{R}}(\theta) 
&= \mathbb{E}_{(x,y) \sim \mathcal{D}_\mathrm{train}}\left[\mathcal{L}\left(f_\theta(x), y\right)\right] = \frac{1}{n} \sum_{i=1}^n \mathcal{L}\left(f_\theta(x_i), y_i\right) \\
\end{split}
$$

- let $\theta^*$ and $\theta_\mathrm{train}$ be the empirical and true [[risk]] minimizer 

$$
\begin{split}
\theta^* &= \mathrm{argmin}_{\theta \in \mathcal{H}} \: \mathbb{E}_\mathcal{D}\left[\mathcal{L}(X, Y, \theta)\right] &\quad\text{(true risk minimizer)} \\
\theta_\mathrm{train} &= \mathrm{argmin}_{\theta \in \mathcal{H}}  \: \mathbb{E}_{\mathcal{D}_\mathrm{train}}\left[\mathcal{L}(X, Y, \theta)\right] &\quad\text{(empirical risk minimizer)} \\
\end{split}
$$

- on the training set the **empirical risk minimizer** leads to a smaller risk than the **true risk minimizer**

$$
\begin{split}
\mathcal{\hat{R}}(\theta_\mathrm{train})  < \mathcal{\hat{R}}(\theta^*) 
\end{split}
$$

- but on the complete data distribution, the **empirical risk minimizer** performes better

$$
\begin{split}
\mathcal{R}(\theta_\mathrm{train})  > \mathcal{R}(\theta^*) 
\end{split}
$$

- the [[generalization gap]] is the difference between the true risk and the empirical risk and is caused by over fitting the limited number of training sames $n = |\mathcal{D}_\mathrm{train}|$

$$
\begin{split}
\mathcal{R}(\theta_\mathrm{train}) - \mathcal{\hat{R}}(\theta_\mathrm{train}) \geq 0
\end{split}
$$

_______

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

### data distribution
- the [[data distribution]] is the [[joint distribution]] of the [[input and output space]] of a model
- given the [[probability space]] 
	- input $(\mathcal{X}, \mathcal{A}_X, \mathcal{P}_X)$  
	- output  $(\mathcal{Y}, \mathcal{A_Y}, \mathcal{P}_Y)$ 
- the [[data distribution]] $\mathcal{P}_{XY}$ is the joint [[probability measure]] over the [[product measure space|product measurable space]] $(\mathcal{X} \times \mathcal{Y}, \mathcal{A_X} \otimes \mathcal{A_Y})$
- given a dataset $\mathcal{D}_0 \subset \mathcal{X} \times \mathcal{Y}$ its [[empirical distribution of a dataset|empirical distribution]] $\mathcal{\hat{P}}_{XY}$ is defined as follows with the [[dirac measure]] $\delta$ 

$$
\mathcal{\hat P}_{XY}(A) = \frac{1}{n} \sum_{i=1}^n \delta_{(x_i, y_i)}(A)
$$


Tags: mathematics statistics SS25
<!--ID: 1748624012851-->
END