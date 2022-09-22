## Concept
- combine weak (simple model with high [[estimator bias|bias]]) [[statistical estimator|learners]] to a more powerful model
- increase [[model complexity]] → lower [[estimator bias]]
- can increase [[model variance]]
- each [[statistical estimator|estimator]] focuses on the weakness of the previous

## Definition
$$
f(x)=
\underbrace{
\sum\limits^{J_m}_{m=1} 
}_\text{sum over all basemodels}
\underbrace{
\beta_m
}_\text{wight base model}
 \cdot 
\underbrace{
h(x, \overbrace{
\gamma_m
}^\text{parameters of base model})
}_\text{base model}
$$

## Training
- fit next model to predict residuals of previous
- loss function $L(Y, f(X))=\frac{1}{N}\sum\limits_{i=1}^{N}L(y_i, x_i)$
0) init $f_0(x)=0$
1) for $m \in (1, ... , M)$:
$$
\beta_m, \gamma_m= argmin 
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
\beta
}_\text{weight}
 \cdot 
 \underbrace{
h(x_i, \gamma)
}_\text{new base model}
$$
$$
f_m(x)=
\underbrace{
f_{m-1}(x)
}_\text{previous model}
+
\underbrace{
\beta_m\cdot h_m(x, \gamma_m)
}_\text{addition in iteration m}
$$
### with [[mean square error]] loss
$$
L
(
y_i, 
f_{m-1}(x_i)
+
\beta
 \cdot 
h(x_i, \gamma)
)
=
[
y_i
-
f_{m-1}(x_i)
- \beta \cdot h(x_i, \gamma)
]^2
$$
START
Basic
boosting: model definition
Back: 
-combine weak (simple model with high [[estimator bias|bias]]) [[statistical estimator|learners]] to a more powerful model
$$
f(x)=
\underbrace{
\sum\limits^{J_m}_{m=1} 
}_\text{sum over all basemodels}
\underbrace{
\beta_m
}_\text{wight base mode}
 \cdot 
\underbrace{
h(x, \overbrace{
\gamma_m
}^\text{parameters of base model})
}_\text{base model}
$$
Tags: statistical learning
<!--ID: 1663839912719-->
END

START
Basic
boosting: 
- concept
- effect: (variance and bias)
- when to use
Back: 

concept:
- combine weak (simple model with high [[estimator bias|bias]]) [[statistical estimator|learners]] to a more powerful model
- each [[statistical estimator|estimator]] focuses on the weakness of the previous

effect:
- increase [[model complexity]] → lower [[estimator bias]]
→ use on high bias (weak) learners

Tags: statistical learning
<!--ID: 1663839912721-->
END

START
Basic
boosting: 
- definition
- training method 
- MSE example
Back: 
### Definition
$$
f(x)=
\underbrace{
\sum\limits^{J_m}_{m=1} 
}_\text{sum over all basemodels}
\underbrace{
\beta_m
}_\text{wight base model}
 \cdot 
\underbrace{
h(x, \overbrace{
\gamma_m
}^\text{parameters of base model})
}_\text{base model}
$$

## Training
- fit next model to predict residuals of previous
- loss function $L(Y, f(X))=\frac{1}{N}\sum\limits_{i=1}^{N}L(y_i, x_i)$
0) init $f_0(x)=0$
1) for $m \in (1, ... , M)$:
$$
\beta_m, \gamma_m= argmin 
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
\beta
}_\text{weight}
 \cdot 
 \underbrace{
h(x_i, \gamma)
}_\text{new base model}
$$
$$
f_m(x)=
\underbrace{
f_{m-1}(x)
}_\text{previous model}
+
\underbrace{
\beta_m\cdot h_m(x, \gamma_m)
}_\text{addition in iteration m}
$$
### MSE example:
$$
L
(
y_i, 
f_{m-1}(x_i)
+
\beta
 \cdot 
h(x_i, \gamma)
)
=
[
y_i
-
f_{m-1}(x_i)
- \beta \cdot h(x_i, \gamma)
]^2
$$
Tags: statistical learning

END