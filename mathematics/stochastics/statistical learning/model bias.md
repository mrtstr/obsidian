# Model Bias
## Definition
- Systematic [[error]] of a model that is left when the training set is infinite. 
- model [[model bias|bias]] and [[model variance|variance]] are [[error]] sources of [[statistical estimator]] and [[statistical predictor]]: see [[variance bias trade-off]]
- for [[statistical predictor]] there is also a part of the [[error]] that is based on the randomness of $f_{Y|X}(y|x)$ and thus is unavoidable and has nothing to do with the model

### [[statistical estimator]]
- given a [[statistical sample|sample]] $\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)$ from the true but unknown [[probability density function|distribution]] and the parameter estimation $\widehat{\theta}_\mathcal{T}$ based on $\mathcal{T}$
- then the bias is the difference between the [[expectation|expected]] parameter estimation and the true parameters 
- the randomness of $\widehat{\theta}_\mathcal{T}$ does not matter because the bias is based on the [[expectation]] over all possible samples $\widehat{\theta}_\mathcal{T}$ and $\theta$ is a constant property and thus is non-stochastic 
 $$
 Bias(\widehat{\theta}_\mathcal{T}) = \mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[\widehat{\theta}_\mathcal{T}\right]-\theta
 =\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[\widehat{\theta}_\mathcal{T}-\theta\right]
$$
- let $\widehat{\theta}_n$ be an estimator trained on $n$ samples than the following is true: $\widehat{\theta}_n ~ is ~ unbiased \Leftrightarrow \lim\limits_{n\leftarrow \infty} \widehat{\theta}_n = \theta$  
### [[statistical predictor]]
- Given the approximated [[statistical predictor]] $\widehat{f}_{\mathcal{T}_{train}}(x)$ trained on a training set $\mathcal{T}_{train}=\{(x_i, y_i)\} \subset \mathcal{D}=\{(x, y) \; |\; (x, y) \sim f_{XY}(.,.)\}$ 
- optimal [[statistical predictor|estimator]] $f(x)=\mathbb{E}[Y \:|\:X=x]$
- for a given point in the feature space $x_0$
- then the bias is the expected difference between the estimator trained on a training set with infinite samples the true optimal estimator 
$$
Bias\left[\widehat{f}_{\mathcal{T}_{train}}(x_0)\right]
=\mathbb{E}_{
\mathcal{T}_{train} \sim \mathcal{D}
}\left[\widehat{f}_{\mathcal{T}_{train}}(x_0) - f(x_0)\right]
=
\mathbb{E}_{
\mathcal{T}_{train} \sim \mathcal{D}
}\left[\widehat{f}_{\mathcal{T}_{train}}(x)\right]
- f(x_0)
$$

START
Basic
estimator bias
- verbal definition and relationship to the total error
Back: 
- Systematic [[error]] of a model that is left when the training set is infinite. 
- model [[model bias|bias]] and [[model variance|variance]] are [[error]] sources of [[statistical estimator]] and [[statistical predictor]]: see [[variance bias trade-off]]
- for [[statistical predictor]] there is also a part of the [[error]] that is based on the randomness of $f_{Y|X}(y|x)$ and thus is unavoidable and has nothing to do with the model
Tags: statistical estimator, statistical learning
<!--ID: 1664642588633-->
END


START
Basic
[[statistical estimator]] bias
- definition
- property of an unbiased estimator
Back: 
- given a [[statistical sample|sample]] $\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)$ from the true but unknown [[probability density function|distribution]] and the parameter estimation $\widehat{\theta}_\mathcal{T}$ based on $\mathcal{T}$
- then the bias is the difference between the [[expectation|expected]] parameter estimation and the true parameters 
- the randomness of $\widehat{\theta}_\mathcal{T}$ does not matter because the bias is based on the [[expectation]] over all possible samples $\widehat{\theta}_\mathcal{T}$ and $\theta$ is a constant property and thus is non-stochastic 
 $$
 Bias(\widehat{\theta}_\mathcal{T}) = \mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[\widehat{\theta}_\mathcal{T}\right]-\theta=\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[\widehat{\theta}_\mathcal{T}-\theta\right]
$$
- let $\widehat{\theta}_n$ be an estimator trained on $n$ samples than the following is true: $\widehat{\theta}_n ~ is ~ unbiased \Leftrightarrow \lim\limits_{n\leftarrow \infty} \widehat{\theta}_n = \theta$  
Tags: statistical estimator, statistical learning
<!--ID: 1664642588638-->
END

START
Basic
[[statistical predictor]] bias
- definition
Back: 
- Given the approximated [[statistical predictor]] $\widehat{f}_{\mathcal{T}_{train}}(x)$ trained on a training set $\mathcal{T}_{train}=\{(x_i, y_i)\} \subset \mathcal{D}=\{(x, y) \; |\; (x, y) \sim f_{XY}(.,.)\}$ 
- optimal [[statistical predictor|estimator]] $f(x)=\mathbb{E}[Y \:|\:X=x]$
- for a given point in the feature space $x_0$
- then the bias is the expected difference between the estimator trained on a training set with infinite samples the true optimal estimator 
$$
Bias\left[\widehat{f}_{\mathcal{T}_{train}}(x_0)\right]
=\mathbb{E}_{
\mathcal{T}_{train} \sim \mathcal{D}
}\left[\widehat{f}_{\mathcal{T}_{train}}(x_0) - f(x_0)\right]
=
\mathbb{E}_{
\mathcal{T}_{train} \sim \mathcal{D}
}\left[\widehat{f}_{\mathcal{T}_{train}}(x)\right]
- f(x_0)
$$

Tags: statistical estimator, statistical learning
<!--ID: 1664642588641-->
END