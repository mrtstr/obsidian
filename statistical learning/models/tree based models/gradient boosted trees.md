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
Approximate the optimal output change with a [[tree models|tree model]] using [[mean square error|MSE]].

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

- calculate the gradient $\frac{\partial L(y_i,f_{m-1}(x_i))}{\partial f_{m-1}(x_i)}$
	→ how has prediction $f_{m-1}(x_i)$ to change to achieve the best improvement of loss $L(y_i,f_{m-1}(x_i))$ 
- approximate the optimal change in model output with a [[tree models|tree model]] using [[mean square error|MSE]]
- for [[mean square error|MSE]] $\frac{\partial L(y_i,f_{m-1}(x_i))}{\partial f_{m-1}(x_i)} = y_i - f_{m-1}(x_i)$ the derivative is equal to the residuals 

## Algorithm
