## Concept
- Local regression inside a sample's neighbourhood.
- Size of neighbourhood $N_k(x)$ is defined by a number of samples $k$ 
- Sample distance is defined by a [[metric]]

$\widehat{f}(x)=MEAN[y_i|x_i \in N_k(x)]$

## Properties
- unconstrained approach 
	→ no assumption about the relationship between features $x$ and labels $y$ 
	→ direct approximation of local [[expected value]] 
- assumptions: similar characteristics in areas in the feature space 
	→ high $k$ → bigger area  $N_k(x)$ → more smoothing → more [[estimator bias]], less [[estimator variance]]

## Problem
- bad performance in sparse feature spaces
- high dimensional spaces are sparse ([[curse of dimensionality]]) → not good for high dimensional problems

START
Basic
k nearest neighbours: concept
Back: 
Concept
- Local regression inside a sample's neighbourhood.
- Size of neighbourhood $N_k(x)$ is defined by a number of samples $k$ 
- Sample distance is defined by a metric

$\widehat{f}(x)=MEAN[y_i|x_i \in N_k(x)]$
<!--ID: 1661678999137-->
END

START
Basic
k nearest neighbours: assumptions
Back: 
$\widehat{f}(x)=MEAN[y_i|x_i \in N_k(x)]$

- unconstrained approach 
	→ no assumption about the relationship between features $x$ and labels $y$ 
	→ direct approximation of local expectation 
- assumption: similar characteristics in areas in the feature space 
	→ high $k$ → bigger area  $N_k(x)$ → more smoothing → more model bias, less model variance
Tags: model, statistical learning
<!--ID: 1661928261911-->
END

START
Basic
k nearest neighbours: problems
Back: 
$\widehat{f}(x)=MEAN[y_i|x_i \in N_k(x)]$

- bad performance in sparse feature spaces
- high dimensional spaces are sparse (curse of dimensionality) → not good for high dimensional problems
Tags: model, statistical learning
<!--ID: 1661928261914-->
END