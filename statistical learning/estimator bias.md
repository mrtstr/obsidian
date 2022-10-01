
## Definition
- Systematic error of an estimator that is left when the training set is infinite. 
- [[statistical estimator|estimator]] [[estimator bias|bias]] and [[estimator variance|variance]] are the two [[error]] sources of [[statistical estimator|statistical estimators]]: see [[variance bias tradeoff]]
- [[estimator variance]] error due to the randomness of an infinite training set / [[statistical sample|set of samples]]

### theory- Systematic error of an estimator that is left when the training set is infinite. 
- [[statistical estimator|estimator]] [[estimator bias|bias]] and [[estimator variance|variance]] are the two [[error]] sources of [[statistical estimator|statistical estimators]]: see [[variance bias tradeoff]]
- [[estimator variance]] error due to the randomness of an infinite training set / [[statistical sample|set of samples]]
- given the true [[PDF]] of our data $f_X(x, \theta)$ with parameters $\theta$
- and the estimated [[PDF]] $\widehat{f}_X(x, \widehat{\theta})$ with the estimated parameters $\widehat{\theta}$ trained [[statistical sample|samples]] $\{x_i \mid x_i \sim f_X(x, \theta) \}$
- then the bias is the difference between the [[expected value|expected]] parameter estimation and the true parameters 
 $$
 Bias(\widehat{\theta}) = \mathbb{E}_{x\sim f_X(x, \theta)}\left[\widehat{\theta}\right]-\theta=\mathbb{E}_{x\sim f_X(x, \theta)}\left[\widehat{\theta}-\theta\right]
$$
- let $\widehat{\theta}_n$ be an estimator trained on $n$ samples than the following is true: $\widehat{\theta}_n ~ is ~ unbiased \Leftrightarrow \lim\limits_{n\leftarrow \infty} \widehat{\theta}_n = \theta$  
### practical
- Given the approximated [[statistical estimator|estimator]] $\widehat{f}_{\mathcal{T}_{train}}(x)$ trained on a training set $\mathcal{T}_{train}=\{(x_i, y_i)\} \subset \mathcal{D}=\{(x, y) \; |\; (x, y) \sim f_{XY}(.,.)\}$ 
- optimal [[statistical estimator|estimator]] $f(x)=\mathbb{E}[Y \:|\:X=x]$
- then the bias is the expected difference between the estimator trained on a training set with infinite samples the true optimal estimator 
$$
Bias\left[\widehat{f}_{\mathcal{T}_{train}}(x)\right]

=\mathbb{E}_{
\mathcal{T}_{train} = \mathcal{D},x \sim \mathcal{D}
}\left[\widehat{f}_{\mathcal{T}_{train}}(x) - f(x)\right]

$$


## Bias free [[statistical estimator|estimators]]

START
Basic
estimator bias
- verbal definition and relationship to the estimator error
Back: 
- Systematic error of an estimator that is left when the training set is infinite. 
- [[statistical estimator|estimator]] [[estimator bias|bias]] and [[estimator variance|variance]] are the two [[error]] sources of [[statistical estimator|statistical estimators]]
- [[estimator variance]] error due to the randomness of an infinite training set / [[statistical sample|set of samples]]: see [[variance bias tradeoff]]
Tags: statistical estimator, statistical learning
<!--ID: 1664642588633-->
END


START
Basic
estimator bias
- theoretical definition
Back: 
- given the true [[PDF]] of our data $f_X(x, \theta)$ with parameters $\theta$
- and the estimated [[PDF]] $\widehat{f}_X(x, \widehat{\theta})$ with the estimated parameters $\widehat{\theta}$ trained [[statistical sample|samples]] $\{x_i \mid x_i \sim f_X(x, \theta) \}$
- then the bias is the difference between the [[expected value|expected]] parameter estimation and the true parameters 
 $$
 Bias(\widehat{\theta}) = \mathbb{E}_{x\sim f_X(x, \theta)}\left[\widehat{\theta}\right]-\theta=\mathbb{E}_{x\sim f_X(x, \theta)}\left[\widehat{\theta}-\theta\right]
$$
- let $\widehat{\theta}_n$ be an estimator trained on $n$ samples than the following is true: $\widehat{\theta}_n ~ is ~ unbiased \Leftrightarrow \lim\limits_{n\leftarrow \infty} \widehat{\theta}_n = \theta$  
Tags: statistical estimator, statistical learning
<!--ID: 1664642588638-->
END

START
Basic
estimator bias
- practical definition for a model $f(x)$
Back: 
- Given the approximated [[statistical estimator|estimator]] $\widehat{f}_{\mathcal{T}_{train}}(x)$ trained on a training set $\mathcal{T}_{train}=\{(x_i, y_i)\} \subset \mathcal{D}=\{(x, y) \; |\; (x, y) \sim f_{XY}(.,.)\}$ 
- optimal [[statistical estimator|estimator]] $f(x)=\mathbb{E}[Y \:|\:X=x]$
- then the bias is the expected difference between the estimator trained on a training set with infinite samples the true optimal estimator 
$$
Bias\left[\widehat{f}_{\mathcal{T}_{train}}(x)\right]

=\mathbb{E}_{
\mathcal{T}_{train} = \mathcal{D},x \sim \mathcal{D}
}\left[\widehat{f}_{\mathcal{T}_{train}}(x) - f(x)\right]

$$
Tags: statistical estimator, statistical learning
<!--ID: 1664642588641-->
END