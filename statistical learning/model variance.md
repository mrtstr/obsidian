# Model Variance
- [[variance]] of a model ([[statistical estimator]] or [[statistical predictor]]) due to the randomness of an infinite training set / [[statistical sample|set of samples]]
- model [[model bias|bias]] and [[model variance|variance]] are two [[error]] sources of [[statistical predictor|statistical estimators]]: see [[variance bias tradeoff]]
- for [[statistical predictor]] there is also a part of the [[error]] that is based on the randomness of $f_{Y|X}(y|x)$ and thus is unavoidable 

## [[statistical estimator]]
- given a [[statistical sample|sample]] $\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)$ from the true but unknown [[PDF|distribution]] and the parameter estimation $\widehat{\theta}_\mathcal{T}$ based on $\mathcal{T}$
- the variance of the [[statistical estimator]] is defined as follows
$$
\mathbb{VAR}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[\widehat{\theta}_\mathcal{T}\right]=
\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[\left(\widehat{\theta}_\mathcal{T}-\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[\widehat{\theta}_\mathcal{T}\right]\right)^2\right]=\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[\widehat{\theta}_\mathcal{T}^2\right]-\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[\widehat{\theta}_\mathcal{T}\right]^2
$$
- the randomness is induced by the random [[statistical sample|sample]]

## [[statistical predictor]]
- Given the approximated [[statistical predictor]] $\widehat{f}_{\mathcal{T}_{train}}(x)$ trained on a training set $\mathcal{T}_{train}=\{(x_i, y_i)\} \subset \mathcal{D}=\{(x, y) \; |\; (x, y) \sim f_{XY}(.,.)\}$ 
- optimal [[statistical predictor|estimator]] $f(x)=\mathbb{E}[Y \:|\:X=x]$
- for a given point in the feature space $x_0$
$$
\mathbb{VAR}_{\mathcal{T} \sim \mathcal{D}}\left[\widehat{f}_{\mathcal{T}}(x_0)\right]=
\mathbb{E}_{\mathcal{T} \sim \mathcal{D}}\left[\left(\widehat{f}_{\mathcal{T}}(x_0)-\mathbb{E}_{\mathcal{T} \sim \mathcal{D}}\left[\widehat{f}_{\mathcal{T}}(x_0)\right]\right)^2\right]=\mathbb{E}_{\mathcal{T} \sim \mathcal{D}}\left[\widehat{f}_{\mathcal{T}}(x_0)^2\right]-\mathbb{E}_{\mathcal{T} \sim \mathcal{D}}\left[\widehat{f}_{\mathcal{T}}(x_0)\right]^2
$$
- the randomness is induced by the random training set 
domness is induced by the random training set 
START
Basic
model variance
- verbal definition and relationship to the estimator error
Back: 
- [[variance]] of a model ([[statistical estimator]] or [[statistical predictor]]) due to the randomness of an infinite training set / [[statistical sample|set of samples]]
- model [[model bias|bias]] and [[model variance|variance]] are two [[error]] sources of [[statistical predictor|statistical estimators]]: see [[variance bias tradeoff]]
- for [[statistical predictor]] there is also a part of the [[error]] that is based on the randomness of $f_{Y|X}(y|x)$ and thus is unavoidable 
Tags: statistical learning
<!--ID: 1664642588627-->
END


START
Basic
model variance of a [[statistical estimator]]
Back: 
- given a [[statistical sample|sample]] $\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)$ from the true but unknown [[PDF|distribution]] and the parameter estimation $\widehat{\theta}_\mathcal{T}$ based on $\mathcal{T}$
- the variance of the [[statistical estimator]] is defined as follows
$$
\mathbb{VAR}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[\widehat{\theta}_\mathcal{T}\right]=
\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[\left(\widehat{\theta}_\mathcal{T}-\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[\widehat{\theta}_\mathcal{T}\right]\right)^2\right]=\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[\widehat{\theta}_\mathcal{T}^2\right]-\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[\widehat{\theta}_\mathcal{T}\right]^2
$$
- the randomness is induced by the random [[statistical sample|sample]]
Tags: statistical learning
<!--ID: 1664723232171-->
END

START
Basic
model variance of a [[statistical predictor]]
Back: 
- Given the approximated [[statistical predictor]] $\widehat{f}_{\mathcal{T}_{train}}(x)$ trained on a training set $\mathcal{T}_{train}=\{(x_i, y_i)\} \subset \mathcal{D}=\{(x, y) \; |\; (x, y) \sim f_{XY}(.,.)\}$ 
- optimal [[statistical predictor|estimator]] $f(x)=\mathbb{E}[Y \:|\:X=x]$
- for a given point in the feature space $x_0$
$$
\mathbb{VAR}_{\mathcal{T} \sim \mathcal{D}}\left[\widehat{f}_{\mathcal{T}}(x_0)\right]=
\mathbb{E}_{\mathcal{T} \sim \mathcal{D}}\left[\left(\widehat{f}_{\mathcal{T}}(x_0)-\mathbb{E}_{\mathcal{T} \sim \mathcal{D}}\left[\widehat{f}_{\mathcal{T}}(x_0)\right]\right)^2\right]=\mathbb{E}_{\mathcal{T} \sim \mathcal{D}}\left[\widehat{f}_{\mathcal{T}}(x_0)^2\right]-\mathbb{E}_{\mathcal{T} \sim \mathcal{D}}\left[\widehat{f}_{\mathcal{T}}(x_0)\right]^2
$$

Tags: statistical learning
<!--ID: 1664723232175-->
END