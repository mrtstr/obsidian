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

#### log likelihood and MSE generalization gap
- the [[expectation|expected]] [[likelihood function|log likelihood]] under the true data generating [[distribution]] $P_{\theta^*}$ is the following

$$
\begin{split}
\mathbb{E}_{(X, Y)\sim P_{\theta^*}}\left[\log\left(p\left(Y|X, \theta\right)\right)\right] \\
\end{split}
$$

- for a [[empirical distribution of a dataset|test dataset]] $\mathcal{D}=\left\{(X_m, Y_m)\right\}^M_{m=1}$ drawn from $P_{\theta^*}$ the [[expectation|expected]] log likelihood is

$$
\begin{split}
\mathbb{E}_{\mathcal{D}\sim P_{\theta^*}}\left[{\mathcal{L}}(\theta)\right]
&=\mathbb{E}_{\mathcal{D}\sim P_\theta^*}\left[\log\left(p\left(\mathcal{D}_Y|\mathcal{D}_X, \theta\right)\right)\right] \\
&= \mathbb{E}_{\mathcal{D}\sim P_\theta^*}\left[\sum_{m=1}^M\log\left(p\left(Y_m|X_m, \theta\right)\right)\right] \\
&=M \mathbb{E}_{(X, Y)\sim P_{\theta^*}}\left[\log\left(p\left(Y|X, \theta\right)\right)\right] \\
\end{split}
$$

- but instead we maximize the empirical [[likelihood function|log likelihood]] on the a [[empirical distribution of a dataset|training dataset]] $\hat{\mathcal{D}}\left\{(X_n, Y_n)\right\}^N_{n=1}$

$$
\begin{split}
\theta_{MLE}
&=\mathrm{arg}\max_\theta \underbrace {\sum_{m=1}^N \log\left(p\left(Y_n|X_n, \theta\right)\right)}_{\tilde{\mathcal{L}}(\theta)}
\end{split}
$$

- By the **law of large numbers**, the empirical averages of both the training and test log-likelihoods converge to the true expectation

$$
\begin{split}
\frac{1}{N}{{\mathcal{L}}}(\theta) &= \frac{1}{N}\sum_{m=1}^N \log\left(p\left(Y_n|X_n, \theta\right)\right)
\xrightarrow{N\to\infty} \mathbb{E}_{(X, Y)\sim P_{\theta^*}}\left[\log\left(p\left(Y|X, \theta\right)\right)\right]\\
\frac{1}{M}\hat{\mathcal{L}}(\theta) &= \frac{1}{M}\sum_{m=1}^M \log\left(p\left(Y_m|X_m, \theta\right)\right)
\xrightarrow{M\to\infty} \mathbb{E}_{(X, Y)\sim P_{\theta^*}}\left[\log\left(p\left(Y|X, \theta\right)\right)\right]\\
\end{split}
$$

- so if we assume sufficiently large $N$ and $M$ we can approximate

$$
\begin{split}
\frac{1}{N}{\mathcal{L}}(\theta) \approx \frac{1}{M}\hat{\mathcal{L}}(\theta) 
\end{split}
$$

- but in reality there is an [[generalization gap]] $d$ so we have the following with the per sample [[generalization gap]] $d$

$$
\begin{split}
\mathbb{E}_{\mathcal{D}\sim P_{\theta^*}}\left[{\mathcal{L}}(\theta_{MLE})\right] &= \frac{N}{M}\mathbb{E}_{\mathcal{D}_{train}}\left[\hat{\mathcal{L}}(\theta_{MLE})\right] - d \\
\frac{1}{N}\mathbb{E}_{\mathcal{D}\sim P_{\theta^*}}\left[{\mathcal{L}}(\theta_{MLE})\right] &= \frac{1}{M}\mathbb{E}_{\mathcal{D}_{train}}\left[\hat{\mathcal{L}}(\theta_{MLE})\right] - \frac{d}{N}
\end{split}
$$

- now lets conciser the relationship between the [[mean square error]] and the [[maximum likelihood estimator]] if we assume Gaussian noise (see  [[mean square error#relationship to the maximum likelihood estimator]] )

$$
\begin{split}
\frac{1}{N}{\mathcal{L}}({\theta_{MLE}}) 
&=  -\frac{1}{2}\log{\left(2\pi \sigma^2\right)} - \frac{1}{2\sigma^2}  {\mathrm{MSE}}(f_{\theta^*}) \\
\frac{1}{M}\hat{\mathcal{L}}({\theta^*}) 
&=  -\frac{1}{2}\log{\left(2\pi \sigma^2\right)} - \frac{1}{2\sigma^2}  \hat{\mathrm{MSE}}_{train}(f_{\theta^*}) \\
\end{split}
$$

- if we plug this in we have the following [[mean square error]] [[generalization gap]]

$$
\begin{split}
- \frac{1}{2\sigma^2}  {\mathrm{MSE}}(f_{\theta^*}) &= - \frac{1}{2\sigma^2}  \hat{\mathrm{MSE}}_{train}(f_{\theta^*}) - \frac{d}{N} \\
 {\mathrm{MSE}}(f_{\theta^*}) &=  \hat{\mathrm{MSE}}_{train}(f_{\theta^*}) + \frac{2\sigma^2d}{N} \\

\end{split}
$$

# -------------


![[mean square error#mean square error]]


![[kl divergence#kl divergence and maximum likelihood]]



![[risk#risk]]


![[data distribution#data distribution]]


# anki

START
Basic
[[generalization gap]]
- regarding the [[mean square error]] and the log [[likelihood function|log likelihood]] with proof

Back: 
#### log likelihood and MSE generalization gap
- the [[expectation|expected]] [[likelihood function|log likelihood]] under the true data generating [[distribution]] $P_{\theta^*}$ is the following

$$
\begin{split}
\mathbb{E}_{(X, Y)\sim P_{\theta^*}}\left[\log\left(p\left(Y|X, \theta\right)\right)\right] \\
\end{split}
$$

- for a [[empirical distribution of a dataset|test dataset]] $\mathcal{D}=\left\{(X_m, Y_m)\right\}^M_{m=1}$ drawn from $P_{\theta^*}$ the [[expectation|expected]] log likelihood is

$$
\begin{split}
\mathbb{E}_{\mathcal{D}\sim P_{\theta^*}}\left[{\mathcal{L}}(\theta)\right]
&=\mathbb{E}_{\mathcal{D}\sim P_\theta^*}\left[\log\left(p\left(\mathcal{D}_Y|\mathcal{D}_X, \theta\right)\right)\right] \\
&= \mathbb{E}_{\mathcal{D}\sim P_\theta^*}\left[\sum_{m=1}^M\log\left(p\left(Y_m|X_m, \theta\right)\right)\right] \\
&=M \mathbb{E}_{(X, Y)\sim P_{\theta^*}}\left[\log\left(p\left(Y|X, \theta\right)\right)\right] \\
\end{split}
$$

- but instead we maximize the empirical [[likelihood function|log likelihood]] on the a [[empirical distribution of a dataset|training dataset]] $\hat{\mathcal{D}}\left\{(X_n, Y_n)\right\}^N_{n=1}$

$$
\begin{split}
\theta_{MLE}
&=\mathrm{arg}\max_\theta \underbrace {\sum_{m=1}^N \log\left(p\left(Y_n|X_n, \theta\right)\right)}_{\tilde{\mathcal{L}}(\theta)}
\end{split}
$$

- By the **law of large numbers**, the empirical averages of both the training and test log-likelihoods converge to the true expectation

$$
\begin{split}
\frac{1}{N}{{\mathcal{L}}}(\theta) &= \frac{1}{N}\sum_{m=1}^N \log\left(p\left(Y_n|X_n, \theta\right)\right)
\xrightarrow{N\to\infty} \mathbb{E}_{(X, Y)\sim P_{\theta^*}}\left[\log\left(p\left(Y|X, \theta\right)\right)\right]\\
\frac{1}{M}\hat{\mathcal{L}}(\theta) &= \frac{1}{M}\sum_{m=1}^M \log\left(p\left(Y_m|X_m, \theta\right)\right)
\xrightarrow{M\to\infty} \mathbb{E}_{(X, Y)\sim P_{\theta^*}}\left[\log\left(p\left(Y|X, \theta\right)\right)\right]\\
\end{split}
$$

- so if we assume sufficiently large $N$ and $M$ we can approximate

$$
\begin{split}
\frac{1}{N}{\mathcal{L}}(\theta) \approx \frac{1}{M}\hat{\mathcal{L}}(\theta) 
\end{split}
$$

- but in reality there is an [[generalization gap]] $d$ so we have the following with the per sample [[generalization gap]] $d$

$$
\begin{split}
\mathbb{E}_{\mathcal{D}\sim P_{\theta^*}}\left[{\mathcal{L}}(\theta_{MLE})\right] &= \frac{N}{M}\mathbb{E}_{\mathcal{D}_{train}}\left[\hat{\mathcal{L}}(\theta_{MLE})\right] - d \\
\frac{1}{N}\mathbb{E}_{\mathcal{D}\sim P_{\theta^*}}\left[{\mathcal{L}}(\theta_{MLE})\right] &= \frac{1}{M}\mathbb{E}_{\mathcal{D}_{train}}\left[\hat{\mathcal{L}}(\theta_{MLE})\right] - \frac{d}{N}
\end{split}
$$

- now lets conciser the relationship between the [[mean square error]] and the [[maximum likelihood estimator]] if we assume Gaussian noise (see  [[mean square error#relationship to the maximum likelihood estimator]] )

$$
\begin{split}
\frac{1}{N}{\mathcal{L}}({\theta_{MLE}}) 
&=  -\frac{1}{2}\log{\left(2\pi \sigma^2\right)} - \frac{1}{2\sigma^2}  {\mathrm{MSE}}(f_{\theta^*}) \\
\frac{1}{M}\hat{\mathcal{L}}({\theta^*}) 
&=  -\frac{1}{2}\log{\left(2\pi \sigma^2\right)} - \frac{1}{2\sigma^2}  \hat{\mathrm{MSE}}_{train}(f_{\theta^*}) \\
\end{split}
$$

- if we plug this in we have the following [[mean square error]] [[generalization gap]]

$$
\begin{split}
- \frac{1}{2\sigma^2}  {\mathrm{MSE}}(f_{\theta^*}) &= - \frac{1}{2\sigma^2}  \hat{\mathrm{MSE}}_{train}(f_{\theta^*}) - \frac{d}{N} \\
 {\mathrm{MSE}}(f_{\theta^*}) &=  \hat{\mathrm{MSE}}_{train}(f_{\theta^*}) + \frac{2\sigma^2d}{N} \\

\end{split}
$$

_______
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
<!--ID: 1752744686655-->
END


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