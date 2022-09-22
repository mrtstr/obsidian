# [[boosting]] with [[tree models]] as base models
## model
- sum of $M$ [[tree models]] (submodels/weak learners)
- in contrast to [[random forrest]] the [[tree models]] are not independent but focus on the weaknesses of the previous models
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
###  tree definition
- tree parameters $\Theta_m=\{R_{j, m}, \gamma_{j,m}\}^{J_M}_{i=1}$ 
- submodel $m$ and leaf $j$
- leafs $R_{j, m}$ 
- mean values  $\gamma_{j, m}=mean[y_i \:|\: x_i \in R_{j, m}]$ 

## training
$$
\widehat{\Theta}_m= argmin 
\underbrace{
\sum\limits_{x_i, y_i \in R_{j,m}}^N 
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
- find a tree that approximates the residuals of the previous model
- in general It's hard for find the regions $R_m$ (for difficult than building a normal tree)
- for some lesses it simplifies but for a general [[loss functions]] it can be approximated with [[gradient boosted trees]]
## training with [[mean square error|MSE loss]]
- for MSE the problems simplifies
	→ find tree model to predict residuals
$$
\widehat{\Theta}_m= argmin 
\underbrace{
\sum\limits_{x_i, y_i \in R_{j,m}}^N 
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


START
Basic
gradient boosted trees: model definition
Back: 
model
- sum of $M$ [[tree models]] (submodels/weak learners)
- in contrast to [[random forrest]] the [[tree models]] are not independent but focus on the weaknesses of the previous models
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
 tree definition
- tree parameters $\Theta_m=\{R_{j, m}, \gamma_{j,m}\}^{J_M}_{i=1}$ 
- submodel $m$ and leaf $j$
- leafs $R_{j, m}$ 
- mean values  $\gamma_{j, m}=mean[y_i \:|\: x_i \in R_{j, m}]$ 
Tags: statistical learning, models
<!--ID: 1663854449556-->
END


START
Basic
gradient boosted trees: training
Back: 
## in general
$$
\widehat{\Theta}_m= argmin 
\underbrace{
\sum\limits_{x_i, y_i \in R_{j,m}}^N 
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
- find a tree that approximates the residuals of the previous model
- in general It's hard for find the regions $R_m$ (for difficult than building a normal tree)
- for some lesses it simplifies but for a general [[loss functions]] it can be approximated with [[gradient boosted trees]]
## with MSE 
- for MSE the problems simplifies
	→ find tree model to predict residuals
$$
\widehat{\Theta}_m= argmin 
\underbrace{
\sum\limits_{x_i, y_i \in R_{j,m}}^N 
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


Tags: statistical learning, models
<!--ID: 1663854449559-->
END


