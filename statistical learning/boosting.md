## concept
- combine weak (simple model with high [[estimator bias|bias]]) [[statistical estimator|learners]] to a more powerful model
- increase [[model complexity]] → lower [[estimator bias]]
- can increase [[model variance]]
- each [[statistical estimator|estimator]] focuses on the weakness of the previous

## definition
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