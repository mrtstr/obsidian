### probabilistic model
- a [[probabilistic model]] models the [[distribution]] of output [[random variable]] $Y$

##### input $X$ and the output $Y$ is random
- assumes that both input $X$ and the output $Y$ and [[random variable]] with a [[joint distribution]] $P(Y, X)$ which is approximated
- for example joint gaussian models there the full model models $P(X, Y)$ but $P(Y \mid X)$ is derived, naive bayes, or some generative models
##### only $Y$ is random
- $X$ is assumed to be fixed/observed then 
- usually the [[conditional probability]] $P(Y|X)$ is modeled
- examples: [[mathematics/stochastics/statistical learning/models/neural networks/neural networks]] with [[softmax function]], [[logistic regession]] 

##### bayesian: $Y$ and the parameters are random
- [[bayesian inference]]: used in the [[maximum aposteriori]] estimator where $f\left(\theta \mid \mathcal{D}\right)=f\left(\theta \mid X, Y\right)$ and $f\left(Y \mid X, \theta\right)$ are modeled



# ----------------
![[data distribution#data distribution]]

![[maximum aposteriori#maximum aposteriori]]

# anki


START
Basic
[[probabilistic model]]
- definition
- 3 approaches with examples

Back: 

### probabilistic model
- a [[probabilistic model]] models the [[distribution]] of output [[random variable]] $Y$

##### input $X$ and the output $Y$ is random
- assumes that both input $X$ and the output $Y$ and [[random variable]] with a [[joint distribution]] $P(Y, X)$ which is approximated
- for example joint gaussian models there the full model models $P(X, Y)$ but $P(Y \mid X)$ is derived, naive bayes, or some generative models
##### only $Y$ is random
- $X$ is assumed to be fixed/observed then 
- usually the [[conditional probability]] $P(Y|X)$ is modeled
- examples: [[mathematics/stochastics/statistical learning/models/neural networks/neural networks]] with [[softmax function]], [[logistic regession]] 

##### bayesian: $Y$ and the parameters are random
- [[bayesian inference]]: used in the [[maximum aposteriori]] estimator where $f\left(\theta \mid \mathcal{D}\right)=f\left(\theta \mid X, Y\right)$ and $f\left(Y \mid X, \theta\right)$ are modeled


Tags: mathematics statistics SS25
<!--ID: 1752603832842-->
END
