### akaike information criterion
- [[statistical estimator]] for relative prediction error 
- relative quality of a statistical model given a collection of statistical models
- estimates the amount if information lost with the model
- trade off between model over fitting and under fitting

$$
ACI = 2k -2\ln\left(\max L(\theta)\right)
$$
- $k$ is the number of estimated parameters
- $L$ is the [[likelihood function]]

### AIC with gaussian noise and the MSE
- criterion for choosing the model with the best assumed test error
- here the [[mean square error]] based formula derived with the assumption of gaussian noise
- training [[mean square error]] plus the approximated [[generalization gap]]

$$
\mathrm{AIC}(\mathcal{M})=\mathrm{MSE}_{train}(f_{\theta_{MLE}}) + \frac{2\sigma^2d}{N}
$$


# -----------


![[generalization gap#log likelihood and MSE generalization gap]]

# anki

START
Basic
[[akaike information criterion]] with gaussian noise and the MSE
- definition
- where does the equation come from?

Back: 
### AIC with gaussian noise and the MSE
- criterion for choosing the model with the best assumed test error
- here the [[mean square error]] based formula derived with the assumption of gaussian noise
- training [[mean square error]] plus the approximated [[generalization gap]]

$$
\mathrm{AIC}(\mathcal{M})=\mathrm{MSE}_{train}(f_{\theta_{MLE}}) + \frac{2\sigma^2d}{N}
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
\mathbb{E}_{\mathcal{D}\sim P_{\theta^*}}\left[{\mathcal{L}}(\theta_{MLE})\right] &= \frac{N}{M}\mathbb{E}_{\mathcal{D}_{train}}\left[\hat{\mathcal{L}}(\theta_{MLE})\right] + d \\
\frac{1}{N}\mathbb{E}_{\mathcal{D}\sim P_{\theta^*}}\left[{\mathcal{L}}(\theta_{MLE})\right] &= \frac{1}{M}\mathbb{E}_{\mathcal{D}_{train}}\left[\hat{\mathcal{L}}(\theta_{MLE})\right] + \frac{d}{N}
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
- \frac{1}{2\sigma^2}  {\mathrm{MSE}}(f_{\theta^*}) &= - \frac{1}{2\sigma^2}  \hat{\mathrm{MSE}}_{train}(f_{\theta^*}) + \frac{d}{N} \\
 {\mathrm{MSE}}(f_{\theta^*}) &=  \hat{\mathrm{MSE}}_{train}(f_{\theta^*}) - \frac{2\sigma^2d}{N} \\

\end{split}
$$


Tags: mathematics statistics SS25
<!--ID: 1752750759594-->
END
