## Background
$$
f_M(x) =
\underbrace{
\sum\limits_{m=1}^{M}
}_\text{sum over all trees = number iterations}
\underbrace{
T(x, 

\overbrace{
\Theta_m
}^\text{parameters of tree m}
)
}_\text{tree model}
$$
[[boosting]] [[tree models]] ([[boosted trees]]) for general [[loss functions]] is hard because the following problem is hard to solve.
$$
\widehat{\Theta}_m= argmin 
\underbrace{
\sum\limits_{i=1}^N 
}_\text{sum over samples}
\underbrace{
L
}_\text{loss}
(y_i, 
\underbrace{
f_{m-1}(x_i)
}_\text{model previous of iteration}
+
\underbrace{
T(x_i, \Theta_m)
}_\text{new base model}
)
$$

For the [[mean square error|MSE loss]] the problem simplifies to the following, wich is not harder to solve than building a regular [[tree models]].
$$
\widehat{\Theta}_m= argmin 
\underbrace{
\sum\limits_{i=1}^N 
}_\text{sum over samples}
\underbrace{
L
}_\text{MSE loss}
(
\underbrace{
y_i - f_{m-1}(x_i)
}_\text{residuals for previous model}, 


\underbrace{
T(x_i, \Theta_m)
}_\text{new base model}
)
$$
## Approach
For each iteration $m$ we build a new [[tree models|tree]] as base model by performing the following two steps:
details: [[boosting]], [[boosted trees]]
1) approximate the optimal output change with a [[tree models|tree model]] using [[mean square error|MSE]].
	
	$$
	\widehat{\Theta}_m= argmin 
	\underbrace{
	\sum\limits_{i=1}^N 
	}_\text{sum over samples}
	
	\left(
	\frac{\partial L(y_i,f_{m-1}(x_i))}{\partial f_{m-1}(x_i)} 
	-
	\underbrace{
	T(x_i, \Theta_m)
	}_\text{new base model}
	\right)^2
	$$
	
	- $\widehat{\Theta}_m=(\{R_{m,j}, c_{m, j}\}_{1\leq j \leq J_m})$ containing the parameters of the [[tree models|tree model]] of iteration $m$
	- calculate the gradient $\frac{\partial L(y_i,f_{m-1}(x_i))}{\partial f_{m-1}(x_i)}$
		→ how has prediction $f_{m-1}(x_i)$ to change to achieve the best improvement of loss $L(y_i,f_{m-1}(x_i))$ 
	- approximate the optimal change in model output with a [[tree models|tree model]] using [[mean square error|MSE]]
	- for [[mean square error|MSE]] $\frac{\partial L(y_i,f_{m-1}(x_i))}{\partial f_{m-1}(x_i)} = y_i - f_{m-1}(x_i)$ the derivative is equal to the residuals 
2) recalculate the mean for each leaf $R_{m,j}$ $\{ c_{m, j}\}_{1\leq j \leq J_m}$ 
$$
c_{m,j} = argmin \sum\limits_{x_i \in R_{m, j}} L(y_i, f_{m-1}(x_i)+c)
$$
## Shrinkage
Use a shrinkage parameter $v$ 
$$
f_m(x) = f_{m-1}(x)+v \cdot \sum\limits_{j=1}^{J_m} c_{m,j} \mathbb{I}[x_i \in R_{m,j}]
$$

START
Basic
gradient boosted trees: process
Back: 
For each iteration $m$ we build a new [[tree models|tree]] as base model by performing the following two steps:
details: [[boosting]], [[boosted trees]]
1) approximate the optimal output change with a [[tree models|tree model]] using [[mean square error|MSE]].
$$
\widehat{\Theta}_m= argmin 
\underbrace{
\sum\limits_{i=1}^N 
}_\text{sum over samples}
\left(
\frac{\partial L(y_i,f_{m-1}(x_i))}{\partial f_{m-1}(x_i)} 
-
\underbrace{
T(x_i, \Theta_m)
}_\text{new base model}
\right)^2
$$
	
- $\widehat{\Theta}_m=(\{R_{m,j}, c_{m, j}\}_{1\leq j \leq J_m})$ containing the parameters of the [[tree models|tree model]] of iteration $m$
- calculate the gradient $\frac{\partial L(y_i,f_{m-1}(x_i))}{\partial f_{m-1}(x_i)}$
	→ how has prediction $f_{m-1}(x_i)$ to change to achieve the best improvement of loss $L(y_i,f_{m-1}(x_i))$ 
- approximate the optimal change in model output with a [[tree models|tree model]] using [[mean square error|MSE]]
- for [[mean square error|MSE]] $\frac{\partial L(y_i,f_{m-1}(x_i))}{\partial f_{m-1}(x_i)} = y_i - f_{m-1}(x_i)$ the derivative is equal to the residuals 
2) recalculate the mean for each leaf $R_{m,j}$ $\{ c_{m, j}\}_{1\leq j \leq J_m}$ 
	$$
	c_{m,j} = argmin \sum\limits_{x_i \in R_{m, j}} L(y_i, f_{m-1}(x_i)+c)
	$$
Tags: statistical_learning model
<!--ID: 1663933113777-->
END

START
Basic
why use gradient boosted trees and not boosted trees?
Back: 
## Background
$$
f_M(x) =
\underbrace{
\sum\limits_{m=1}^{M}
}_\text{sum over all trees = number iterations}
\underbrace{
T(x, 

\overbrace{
\Theta_m
}^\text{parameters of tree m}
)
}_\text{tree model}
$$
[[boosting]] [[tree models]] ([[boosted trees]]) for general [[loss functions]] is hard because the following problem is hard to solve.
$$
\widehat{\Theta}_m= argmin 
\underbrace{
\sum\limits_{i=1}^N 
}_\text{sum over samples}
\underbrace{
L
}_\text{loss}
(y_i, 
\underbrace{
f_{m-1}(x_i)
}_\text{model previous of iteration}
+
\underbrace{
T(x_i, \Theta_m)
}_\text{new base model}
)
$$

For the [[mean square error|MSE loss]] the problem simplifies to the following, which is not harder to solve than building a regular [[tree models]].
$$
\widehat{\Theta}_m= argmin 
\underbrace{
\sum\limits_{i=1}^N 
}_\text{sum over samples}
\underbrace{
L
}_\text{MSE loss}
(
\underbrace{
y_i - f_{m-1}(x_i)
}_\text{residuals for previous model}, 


\underbrace{
T(x_i, \Theta_m)
}_\text{new base model}
)
$$
Tags: statistical_learning model
<!--ID: 1663933113781-->
END