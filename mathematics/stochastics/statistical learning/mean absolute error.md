TODO 
add proofs
add error of optimal estimation
# [[mean absolute error]]
[[loss functions]]

## Definition
For a [[statistical estimator|statistical estimaton]] $\widehat{x}$ of the [[random variable]] $X$ the [[mean absolute error]] is defined as the following
$$
L_{MAE}(X, \widehat{x})=\mathbb{E}\left[|X-\widehat{x}|\right]
$$

For a [[statistical predictor|statistical prediction]] of the [[random variable]] $Y$ given a dependent [[random variable]] $X$ the [[mean absolute error]] is defined as the following
$$
L_{MAE}(X, f(x))=\mathbb{E}\left[|X-f(x)|\right]
$$
## minimum
### [[statistical estimator|statistical estimaton]] $\widehat{x}$
The [[statistical estimator|statistical estimaton]] $\widehat{x}$ of the [[random variable]] $X$ that is minimizing the [[mean absolute error]] is the [[median]] of $X$ $\widehat{x}_{MAE}=median[X]$.

### [[statistical predictor]] $f(x)$
The [[statistical predictor]] $f(x)$ that is minimizing the [[mean absolute error]] is the [[conditional distribution|conditional]] [[median]] of the [[conditional distribution]] $f_{Y\mid X = x}(y)$ $f_{MAE}(x)=median[Y\:|\:X=x]$


# Anki
START
Basic
[[mean absolute error]] definition and minumum
- [[statistical estimator]]
- [[statistical predictor]]
Back: 
## Definition
For a [[statistical estimator|statistical estimaton]] $\widehat{x}$ of the [[random variable]] $X$ the [[mean absolute error]] is defined as the following
$$
L_{MAE}(X, \widehat{x})=\mathbb{E}\left[|X-\widehat{x}|\right]
$$

For a [[statistical predictor|statistical prediction]] of the [[random variable]] $Y$ given a dependent [[random variable]] $X$ the [[mean absolute error]] is defined as the following
$$
L_{MAE}(X, f(x))=\mathbb{E}\left[|X-f(x)|\right]
$$
## minimum
### [[statistical estimator|statistical estimaton]] $\widehat{x}$
The [[statistical estimator|statistical estimaton]] $\widehat{x}$ of the [[random variable]] $X$ that is minimizing the [[mean absolute error]] is the [[median]] of $X$ $\widehat{x}_{MAE}=median[X]$.

### [[statistical predictor]] $f(x)$
The [[statistical predictor]] $f(x)$ that is minimizing the [[mean absolute error]] is the [[conditional distribution|conditional]] [[median]] of the [[conditional distribution]] $f_{Y\mid X = x}(y)$ $f_{MAE}(x)=median[Y\:|\:X=x]$

Tags: statistical_learning
<!--ID: 1674124469387-->
END