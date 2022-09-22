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
- tree parameters $\Theta_m=(R_{j, m}, \gamma_{j,m})$ 
- submodel $m$ and leaf $j$
- leafs $R_{j, m}$ 
- mean values  $\gamma_{j, m}=mean[y_i \:|\: x_i \in R_{j, m}]$ 

## training
- easy with [[mean square error|MSE loss]]: find tree model to predict residuals
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
- can be generalised for different losses: [[gradient boosted trees]]

START
Basic
gradient boosted trees: model definition
Back: 
model
- sum of $M$ [[tree models]] (submodels/weak learners)
-  in contrast to [[random forrest]] the [[tree models]] are not independent but focus on the weaknesses of the previous models
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
- tree parameters $\Theta_m=(R_{j, m}, \gamma_{j,m})$ 
- submodel $m$ and leaf $j$
- leafs $R_{j, m}$ 
- mean values  $\gamma_{j, m}=mean[y_i \:|\: x_i \in R_{j, m}]$ 
Tags: statistical learning, models
END


START
Basic
gradient boosted trees: training
Back: 
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
- easy with [[mean square error|MSE loss]]: find tree model to predict residuals
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
- can be generalised for different losses: [[gradient boosted trees]]
Tags: statistical learning, models
END