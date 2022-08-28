## statistical estimator
- Goal: find connect between input/features $x$ and output/labels $y$
- because the [[joint distribution]] $f_{XY}(x,y)$ is hard to find the goal is to approximate [[conditional distribution]]  $f_{X|Y}(x|y)$
- every point in the feature space $x$ is a distribution of outputs $y$
- approximate estimator $f(x)$  by minimizing the [[loss functions]]

### connection to [[loss functions]] 
#### [[mean square error]] 
- $L(Y, f(x))=E[(Y-f(x))^2] \rightarrow f(x)=E[Y|X=x]$  
#### [[mean absolute error]] 
- $L(Y, f(x))=E[|Y-f(x)|] \rightarrow f(x)=median[Y|X=x]$ 
#### [[maximum likelihood]] 
- $L(\Theta)=\sum_{(x_i,y_i) \in \mathcal{T}_{train}} log [f_{Y|X, \Theta}(y_i,x_i)] \rightarrow f_\Theta(x)$
- equal to [[mean square error]] when $f_{Y|X}(y|x) \sim \mathcal{N}$ 

### Approximation
having an approximation for every point in the feature space often not possible because there might not be enough/any samples in every area in the feature space.
→ assumptions needed
#### Assumptions 
- can be model constraints like assuming a certain kind of relationship between feature $x$ and label $y$ 
- can be local smoothing in the feature space (e.g. [[kernel methods]], [[k nearest neighbors]]) assuming similar characteristics within an area in the feature space

##### Constraint estimator
→ assuming a certain relationship between $x$ and $y$ 
- [[linear models]]

##### unconstrained estimator
→ assuming no relationship between $x$ and $y$ 
- [[k nearest neighbors]] $\widehat{f}(x)=MEAN[y_i|x_i \in N_k(x)]$

### [[variance bias tradeoff]]
- Constrains induce a bias but can reduce the estimator's variance

START
Basic
statistical estimators: goals and process
Back: 
- Goal: find connect between input/features $x$ and output/labels $y$
- because the joint distribution $f_{XY}(x,y)$ is hard to find the goal is to approximate conditional distribution  $f_{X|Y}(x|y)$
- every point in the feature space $x$ is a distribution of outputs $y$
- approximate estimator $f(x)$  by minimizing the loss functions
Tags: statistical estimator, statistical learning
END

START
Basic
Why put assumptions needed for statistical estimators, and what are the effects?
Back: 
having an approximation for every point in the feature space not possible because there might not be enough/any samples in every point in the feature space.
→ assumptions needed to estimate in those regions of the feature space
Effect: assumptions induce a bias but can reduce the estimator's variance
Tags: statistical estimator, statistical learning
END

START
Basic
Two kinds of assumptions for statistical estimators, with examples
Back: 
1) can be model constraints like assuming a certain kind of relationship between feature $x$ and label $y$ (linear models)
2) can be local smoothing in the feature space (e.g. kernel methods, k nearest neighbors) assuming similar characteristics within an area in the feature space
Tags: statistical estimator, statistical learning
END

START
Basic
Statistical estimator that comes close to being unconstrained?
Back: 
- K nearest neighbor with k=1
- direct approximation of the mean around the sample's location: $\widehat{f}(x)=MEAN[y_i|x_i \in N_k(x)]$
→ problems in spare feature spaces
Tags: statistical estimator, statistical learning
END

START
Basic
Effect of using MSE and MAE criterion for a statistical estimator?
Back: 
- mean square error estimates the conditional mean: 
	-> $L(Y, f(x))=E[(Y-f(x))^2]$  ⟶ $f(x)=E[Y|X=x]$  
- mean absolute error estimated the conditional median:  
	-> $L(Y, f(x))=E[|Y-f(x)|]$  ⟶ $f(x)=median[Y|X=x]$ 
Tags: statistical estimator, statistical learning
END

