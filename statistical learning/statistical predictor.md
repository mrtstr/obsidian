# Statistical predictor
- Goal: find connect between input/features $x$ and output/labels $y$
- because the [[joint distribution]] $f_{XY}(x,y)$ is hard to find the goal is to approximate properties (e.g. mean, median, or [[quantile function|quantiles]]) of the [[conditional distribution]]  $f_{Y|X}(y|x)$
- every point in the feature space $x$ is a distribution of outputs $y$
- approximate predictor $f(x)$ by minimizing the [[loss functions]]

(in contrast, a [[statistical estimator]] is estimating a property of the true [[PDF|distribution]] based on [[statistical estimator|observed data]])

### connection to [[loss functions]] 
#### [[mean square error]] 
- $L(Y, f(x))=\mathbb{E}[(Y-f(X))^2]$
- $=\int\limits_\infty^\infty \int\limits_\infty^\infty(y-f(x))^2f_{XY}(x,y)dxdy$
$$=\int\limits_\infty^\infty \underbrace{ \int\limits_\infty^\infty(y-f(x))^2f_{Y \mid X}(y) \: dy }_\text{$\mathbb{E}_{Y|X}[(Y-f(x))^2\:|\:X]$} \: f_{X}(x)dx$$
- $=\mathbb{E}_{x_0 \sim f_{X}(x)} \left[ \mathbb{E}_{Y|X = x_0}[(Y-f(x_0))^2\:|\:X=x_0]\right]$ ([[factoring of joint densities]])
- $\rightarrow f(x)=argmin_c \:\mathbb{E}_{Y|X=x}[(Y-c)^2\:|\:X=x]=\mathbb{E}[Y\:|\:X=x]$ ([[conditional expectation]])
#### [[mean absolute error]] 
- $L(Y, f(x))=\mathbb{E}[|Y-f(X)|] \rightarrow f(x)=median[Y|X=x]$ 
#### [[maximum likelihood]] 
- $L(\Theta)=\sum_{(x_i,y_i) \in \mathcal{T}_{train}} log [f_{Y|X, \Theta}(y_i,x_i)] \rightarrow f_\Theta(x)$
- equal to [[mean square error]] when $f_{Y|X}(y|x) \sim \mathcal{N}$ 

### Approximation
having an approximation for every point in the feature space often not possible because there might not be enough/any samples in every area of the feature space.
→ assumptions needed
### Assumptions 
1) assumptions are needed for generalization
	- we need an approximation for every point in the feature space (even without any training samples in the area)
		→ assumptions needed to estimate in those regions of the feature space
2) assumptions needed for variance reduction
	- in sparse regions of the feature space the approximation will have a high variance because of the randomness of the training samples ($f_X(x)$ and $f_{Y|X=x}(y, x)$)
		→ assumptions can reduce the estimator's variance but induce a bias
#### two kinds of Assumptions
1) can be model constraints like assuming a certain kind of relationship between feature $x$ and label $y$ 
2) can be local smoothing in the feature space (e.g. [[kernel methods]], [[k nearest neighbours]]) assuming similar characteristics within an area in the feature space

##### Constraint estimator
→ assuming a certain relationship between $x$ and $y$ 
- [[linear models]]

##### unconstrained estimator
→ assuming no relationship between $x$ and $y$ 
- [[k nearest neighbours]] $\widehat{f}(x)=MEAN[y_i|x_i \in N_k(x)]$

### [[variance bias trade-off]]
- Constrains induce a bias but can reduce the estimator's variance

START
Basic
statistical estimators: goals and process
Back: 
- Goal: find connect between input/features $x$ and output/labels $y$
- because the [[joint distribution]] $f_{XY}(x,y)$ is hard to find the goal is to approximate properties (e.g. mean, median, or quantiles) of the [[conditional distribution]]  $f_{Y|X}(y|x)$
- every point in the feature space $x$ is a distribution of outputs $y$
- approximate estimator $f(x)$ by minimizing the loss functions
Tags: statistical estimator, statistical learning
<!--ID: 1661678999092-->
END

START
Basic
Why put assumptions needed for statistical estimators, and what are the effects?
Back: 
1) assumptions are needed for generalization
	- we need an approximation for every point in the feature space (even without any training samples in the area)
		→ assumptions needed to estimate in those regions of the feature space
2) assumptions needed for variance reduction
	- in sparse regions of the feature space the approximation will have a high variance because of the randomness of the training samples ($f_X(x)$ and $f_{Y|X=x}(y, x)$)
		→ assumptions can reduce the estimator's variance but induce a bias

Tags: statistical estimator, statistical learning
<!--ID: 1661678999122-->
END

START
Basic
Two kinds of assumptions for statistical estimators, with examples
Back: 
1) can be model constraints like assuming a certain kind of relationship between feature $x$ and label $y$ (linear models)
2) can be local smoothing in the feature space (e.g. kernel methods, k nearest neighbours) assuming similar characteristics within an area in the feature space
Tags: statistical estimator, statistical learning
<!--ID: 1661678999127-->
END

START
Basic
Statistical estimator that comes close to being bias less?
Back: 
- K nearest neighbour with k=1
- direct approximation of the mean around the sample's location: $\widehat{f}(x)=MEAN[y_i|x_i \in N_k(x)]$
→ problems in spare feature spaces
Tags: statistical estimator, statistical learning
<!--ID: 1661678999131-->
END

START
Basic
Effect of using MSE (with proof) and MAE criterion for a statistical estimator?
Back: 
- mean square error estimates the conditional mean: 
- $L(Y, f(x))=\mathbb{E}[(Y-f(X))^2]$
- $=\int\limits_\infty^\infty \int\limits_\infty^\infty(y-f(x))^2f_{XY}(x,y)dxdy$
- $=\int\limits_\infty^\infty \underbrace{ \int\limits_\infty^\infty(y-f(x))^2f_{Y \mid X}(y) \: dy }_\text{conditional expectation} \: f_{X}(x)dx$
- $=\mathbb{E}_{x_0 \sim f_{X}(x)} \left[ \mathbb{E}_{Y|X = x_0}[(Y-f(x_0))^2\:|\:X=x_0]\right]$ ([[factoring of joint densities]])
- $\rightarrow f(x)=argmin_c \:\mathbb{E}_{Y|X=x}[(Y-c)^2\:|\:X=x]=\mathbb{E}[Y\:|\:X=x]$ ([[conditional expectation]])
- mean absolute error estimated the conditional median:  
	→ $L(Y, f(x))=\mathbb{E}[|Y-f(X)|]$ ⟶ $f(x)=median[Y|X=x]$ 
Tags: statistical estimator, statistical learning
<!--ID: 1661678999134-->
END

