[[functions of random variables]] 
$$
\begin{split}
&Y_1 = g_1(X_1,...,X_n) \\
&\qquad ... \\
&Y_m = g_m(X_1,...,X_n) \\
&\boldsymbol{g}: \mathbb{R}^n  \mapsto \mathbb{R}^m: \boldsymbol{g}(\boldsymbol{X}) = \boldsymbol{Y}
\end{split}
$$
## [[discrete random variable|discrete]] case
- $\boldsymbol{X} = (X_1, ..., X_n)$ is a [[discrete random variable|discrete]] [[vector notation|multidimensional]] [[random variable]] with a [[joint probability function]]  $f_{\boldsymbol{X}}(\boldsymbol{x})$
- $\boldsymbol{Y} = (Y_1, ..., Y_n) = \boldsymbol{g}(\boldsymbol{X})$
The [[joint probability function]] $f_{\boldsymbol{Y}}(\boldsymbol{y})$ is defined as follows
$$
f_{\boldsymbol{Y}}(\boldsymbol{y}) = \sum\limits_{\{\boldsymbol{x} \mid \boldsymbol{g}(\boldsymbol{x}) = \boldsymbol{y}\}} f_{\boldsymbol{X}}(\boldsymbol{x})
$$

## brute force method for the [[continuous random variable|continuous]] case
- $\boldsymbol{X} = (X_1, ..., X_n)$ is a [[continuous random variable|continuous]] [[vector notation|multidimensional]] [[random variable]] with a [[joint distribution]]  $f_{\boldsymbol{X}}(\boldsymbol{x})$
- $Y = g(\boldsymbol{X})$ is a (one dimensional) [[continuous random variable]]

$$
f_{Y}(y) = \int...\int\limits_{\{\boldsymbol{x} \mid g(\boldsymbol{x}) = y\}} f_{\boldsymbol{X}}(\boldsymbol{x}) dx
$$


###  [[continuous random variable|continuous]] [[vector notation|multidimensional]] [[random variable]] with a [[linear function]]
- $\boldsymbol{X} = (X_1, ..., X_n)$ is a [[continuous random variable|continuous]] [[vector notation|multidimensional]] [[random variable]] with a [[joint distribution]]  $f_{\boldsymbol{X}}(\boldsymbol{x})$
- $\boldsymbol{Y} = (Y_1, ..., Y_n)= \boldsymbol{g(X)} = A \boldsymbol{X}$ with an [[linear function]] with a [[regular matrix]] $A \in \mathbb{R}^{n}$
$$
f_\boldsymbol{Y}(\boldsymbol{y})=\underbrace{\frac{1}{|det(A)|}}_\text{normalization} f_{\boldsymbol{X}}
\underbrace{
\left(A^{-1} \boldsymbol{y}\right)
}_{g^{-1}(y)}
$$


# Anki

START
Basic
[[functions of random variables]]: 
- $\boldsymbol{X} = (X_1, ..., X_n)$ is a [[continuous random variable|continuous]] [[vector notation|multidimensional]] [[random variable]] with a [[joint distribution]]  $f_{\boldsymbol{X}}(\boldsymbol{x})$
- $\boldsymbol{Y} = (Y_1, ..., Y_n)= \boldsymbol{g(X)} = A \boldsymbol{X}$ with an [[linear function]] with a [[regular matrix]] $A \in \mathbb{R}^{n}$
- [[probability density function]] of the transformed [[random variable]] $f_Y(y)$
Back: 

$$
f_\boldsymbol{Y}(\boldsymbol{y})=\underbrace{\frac{1}{|det(A)|}}_\text{normalization} f_{\boldsymbol{X}}
\underbrace{
\left(A^{-1} \boldsymbol{y}\right)
}_{g^{-1}(y)}
$$
Tags: mathematics, statistics
<!--ID: 1671642994794-->
END
