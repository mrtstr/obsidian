### bayes optimal predictor
- the [[bayes optimal predictor]] $f^*$ is the best predictor possible
- the [[risk]] of the [[bayes optimal predictor]] is the [[white noise]] of the data

$$
\begin{split}
 f^* &= \arg\min_{f} \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f(x))\right]\\
 \mathcal{R}_\mathcal{D}(f^*) &=  \epsilon = \text{irreducable error} \\
 \end{split}
$$

# ------------

![[risk#risk]]
# anki

START
Basic
[[bayes optimal predictor]]
- defintion

Back: 
### bayes optimal predictor
- the [[bayes optimal predictor]] $f^*$ is the best predictor possible
- the [[risk]] of the [[bayes optimal predictor]] is the [[white noise]] of the data

$$
\begin{split}
 f^* &= \arg\min_{f} \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f(x))\right]\\
 \mathcal{R}_\mathcal{D}(f^*) &=  \epsilon = \text{irreducable error} \\
 \end{split}
$$

_________

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

Tags: mathematics basics WS2526
<!--ID: 1766918120799-->
END
