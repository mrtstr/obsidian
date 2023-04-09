[[boosting]]
[[generalized linear models]]

$g(\mathbb{E}\left[Y \mid X\right]) = \alpha + \sum\limits_{i=1}f_i(X_i)$ 

$$

\underbrace{
g(\mathbb{E}\left[Y \mid X\right]) 
}_\text{linking function}
=
\underbrace{
\alpha
}_\text{indipendent coefficient}
+ 
\sum\limits^{M}_{i=1}
\underbrace{
f_i(
\overbrace{
X_i
}^\text{one input feature})
)
}_\text{base model}
$$

- link function $g$ often logit or identity

# training with backfitting algorithm

START
Basic
generalized additive models
- definition
- and name of training algorithm
Back: 
$$

\underbrace{
g(\mathbb{E}\left[Y \mid X\right]) 
}_\text{linking function}
=
\underbrace{
\alpha
}_\text{indipendent coefficient}
+ 
\sum\limits^{M}_{i=1}
\underbrace{
f_i(
\overbrace{
X_i
}^\text{one input feature})
)
}_\text{base model}
$$
- link function $g$ often logit or identity
training: with backfitting algorithm
Tags: statistical_learning model
<!--ID: 1663839912717-->
END
