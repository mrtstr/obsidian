# Statistical predictor
- Goal: find connect between input/features $x$ and a [[stochastic independent|stochastic dependent]] $y$
- because the [[joint distribution]] $f_{XY}(x,y)$ is hard to find the goal is to approximate properties (e.g. mean, median, or [[quantile function|quantiles]]) of the [[conditional distribution]]  $f_{Y|X}(y|x)$
- every point in the feature space $x$ is a distribution of outputs $y$
- approximate predictor $f(x)$ by minimizing the [[loss functions]]

(in contrast, a [[statistical estimator_old]] is estimating a property of the true [[probability density function (PDF)|distribution]] based on [[statistical estimator_old|observed data]])


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
[[statistical predictor]]: goals and process
Back: 
- Goal: find connect between input/features $x$ and a [[stochastic independent|stochastic dependent]] $y$
- because the [[joint distribution]] $f_{XY}(x,y)$ is hard to find the goal is to approximate properties (e.g. mean, median, or quantiles) of the [[conditional distribution]]  $f_{Y|X}(y|x)$
- every point in the feature space $x$ is a distribution of outputs $y$
- approximate estimator $f(x)$ by minimizing the loss functions
Tags: mathematics statistical_learning
<!--ID: 1661678999092-->
END

START
Basic
Why put assumptions needed for [[statistical predictor]], and what are the effects?
Back: 
1) assumptions are needed for generalization
	- we need an approximation for every point in the feature space (even without any training samples in the area)
		→ assumptions needed to estimate in those regions of the feature space
2) assumptions needed for variance reduction
	- in sparse regions of the feature space the approximation will have a high variance because of the randomness of the training samples ($f_X(x)$ and $f_{Y|X=x}(y, x)$)
		→ assumptions can reduce the estimator's variance but induce a bias

Tags: mathematics statistical_learning
<!--ID: 1661678999122-->
END

START
Basic
Two kinds of assumptions for [[statistical predictor]], with examples
Back: 
1) can be model constraints like assuming a certain kind of relationship between feature $x$ and label $y$ (linear models)
2) can be local smoothing in the feature space (e.g. kernel methods, k nearest neighbours) assuming similar characteristics within an area in the feature space
Tags: mathematics statistical_learning
<!--ID: 1661678999127-->
END

START
Basic
[[statistical predictor]] that comes close to being bias less?
Back: 
- K nearest neighbour with k=1
- direct approximation of the mean around the sample's location: $\widehat{f}(x)=MEAN[y_i|x_i \in N_k(x)]$
→ problems in spare feature spaces
Tags: mathematics statistical_learning
<!--ID: 1661678999131-->
END



