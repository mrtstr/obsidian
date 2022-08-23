## statistical estimator
- Goal: find connect between input/features $x$ and output/labels $y$
- because the [[joint distribution]] $f_{XY}(x,y)$ is hard to find the goal is to approximate [[conditional distribution]]  $f_{X|Y}(x|y)$
- every point in the feature space $x$ is a distribution of outputs $y$
- approximate estimator $f(x)$  by minimizing the [[loss functions]]

### connection to [[loss functions]] 
#### [[mean square error]] 
- $L(Y, f(x))=E[(Y-f(x))^2]$  ⟶ $f(x)=E[Y|X=x]$  
#### [[mean absolut error]] 
- $L(Y, f(x))=E[|Y-f(x)|]$  ⟶ $f(x)=median[Y|X=x]$ 
#### [[maximum likelihood]] 
- $L(\Theta)=\sum_{(x_i,y_i) \in \mathcal{T}_{train}} log [f_{Y|X, \Theta}(y_i,x_i)]$    ⟶ $f_\Theta(x)$
- equal to [[mean square error]] when $f_{Y|X}(y|x) \sim \mathcal{N}$ 

### approximation
having an approximation for every point in the feature space often not possible 
-> assumptions needed

### contraint estimator
assuming a certain relationship between relationship between $x$ and $y$  e. g. linear ([[linear models]])

### unconstraint estimator
- assuming no rationship between  $x$ and $y$ 
- e. g. [[k nearest neighbours]] $\widehat{f}(x)=MEAN[y_i|x_i \in N_k(x)]$
- assumtions through local smoothing 

### [[variance bias tradeoff]]
