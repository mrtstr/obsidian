# [[mean square error]]
[[loss functions]]

## Definition
For a [[statistical estimator|statistical estimaton]] $\widehat{x}$ of the [[random variable]] $X$ the [[mean square error]] is defined as the following
$$
L_{MSE}(X, \widehat{x})=\mathbb{E}\left[(X-\widehat{x})^2\right]
$$

For a [[statistical predictor|statistical prediction]] of the [[random variable]] $Y$ given a dependent [[random variable]] $X$ the [[mean square error]] is defined as the following
$$
L_{MSE}(X, f(x))=\mathbb{E}\left[(X-f(x))^2\right]
$$
$L(Y, f(x))=E[(Y-f(x))^2] \rightarrow f(x)=E[Y|X=x]$  

## minimum 

### [[statistical estimator|statistical estimaton]] $\widehat{x}$
The [[statistical estimator|statistical estimaton]] $\widehat{x}$ of the [[random variable]] $X$ that is minimizing the [[mean square error]] is the [[expectation]] $\widehat{x}_{MSE}=\mathbb{E}[X]$.
Proof
$$
\begin{split}
\mathbb{E}\left[(X-\widehat{x})^2\right] &= \mathbb{E}\left[X^2\right] + \widehat{x}^2 + 2\widehat{x}\mathbb{E}\left[X\right] \\
\frac{d\mathbb{E}\left[X^2\right] + \widehat{x}^2 + 2\widehat{x}\mathbb{E}\left[X\right]}{d\widehat{x}} &= 2\widehat{x}-2\mathbb{E}\left[X\right] = 0 \\
\rightarrow argmin \: \mathbb{E}\left[(X-\widehat{x})^2\right] &= \widehat{x}_{MSE}=\mathbb{E}[X]
\end{split}
$$


The [[mean square error]] of $\widehat{x}_{MSE}$ the [[variance]] $L_{MSE}(X, \widehat{x}_{MSE})=\mathbb{VAR}\left[X\right]$.
$$
L_{MSE}(X, \widehat{x}_{MSE})=\mathbb{E}\left[(X-\widehat{x}_{MSE})^2\right] = \mathbb{E}\left[(X-\mathbb{E}[X])^2\right] = \mathbb{VAR}\left[X\right]
$$
### [[statistical predictor]] $f(x)$
The [[statistical predictor]] $f(x)$ that is minimizing the [[mean square error]] is the [[conditional expectation]] $f_{MSE}(x)=\mathbb{E}[Y\:|\:X=x]$

#### proof
$$
\begin{split}
\mathbb{E}[(Y-f(X))^2] 
&=\int\limits_\infty^\infty \int\limits_\infty^\infty(y-f(x))^2f_{XY}(x,y)dxdy \\
&= \int\limits_\infty^\infty \underbrace{ \int\limits_\infty^\infty(y-f(x))^2f_{Y \mid X}(y) \: dy }_\text{$\mathbb{E}_{Y|X}[(Y-f(x))^2\:|\:X]$} \: f_{X}(x)dx \\
&=\mathbb{E}_{x_0 \sim f_{X}(x)} \left[ \mathbb{E}_{Y|X = x_0}[(Y-f(x_0))^2\:|\:X=x_0]\right] \\
\rightarrow f(x)&=argmin_c \:\mathbb{E}_{Y|X=x}[(Y-c)^2\:|\:X=x]=\mathbb{E}[Y\:|\:X=x]
\end{split}
$$


# Anki
START
Basic
[[mean square error]] definition
- [[statistical estimator]]
- [[statistical predictor]]
Back: 
For a [[statistical estimator|statistical estimaton]] $\widehat{x}$ of the [[random variable]] $X$ the [[mean square error]] is defined as the following
$$
L_{MSE}(X, \widehat{x})=\mathbb{E}\left[(X-\widehat{x})^2\right]
$$

For a [[statistical predictor|statistical prediction]] of the [[random variable]] $Y$ given a dependent [[random variable]] $X$ the [[mean square error]] is defined as the following
$$
L_{MSE}(X, f(x))=\mathbb{E}\left[(X-f(x))^2\right]
$$
$L(Y, f(x))=E[(Y-f(x))^2] \rightarrow f(x)=E[Y|X=x]$  

Tags: statistical estimator, statistical learning
<!--ID: 1661678999134-->
END


START
Basic
minumum of the [[mean square error]] with proof
- [[statistical estimator]]
- [[statistical predictor]]
Back: 
### [[statistical estimator|statistical estimaton]] $\widehat{x}$
The [[statistical estimator|statistical estimaton]] $\widehat{x}$ of the [[random variable]] $X$ that is minimizing the [[mean square error]] is the [[expectation]] $\widehat{x}_{MSE}=\mathbb{E}[X]$.
Proof
$$
\begin{split}
\mathbb{E}\left[(X-\widehat{x})^2\right] &= \mathbb{E}\left[X^2\right] + \widehat{x}^2 + 2\widehat{x}\mathbb{E}\left[X\right] \\
\frac{d\mathbb{E}\left[X^2\right] + \widehat{x}^2 + 2\widehat{x}\mathbb{E}\left[X\right]}{d\widehat{x}} &= 2\widehat{x}-2\mathbb{E}\left[X\right] = 0 \\
\rightarrow argmin \: \mathbb{E}\left[(X-\widehat{x})^2\right] &= \widehat{x}_{MSE}=\mathbb{E}[X]
\end{split}
$$


The [[mean square error]] of $\widehat{x}_{MSE}$ the [[variance]] $L_{MSE}(X, \widehat{x}_{MSE})=\mathbb{VAR}\left[X\right]$.
$$
L_{MSE}(X, \widehat{x}_{MSE})=\mathbb{E}\left[(X-\widehat{x}_{MSE})^2\right] = \mathbb{E}\left[(X-\mathbb{E}[X])^2\right] = \mathbb{VAR}\left[X\right]
$$
### [[statistical predictor]] $f(x)$
The [[statistical predictor]] $f(x)$ that is minimizing the [[mean square error]] is the [[conditional expectation]] $f_{MSE}(x)=\mathbb{E}[Y\:|\:X=x]$

#### proof
$$
\begin{split}
\mathbb{E}[(Y-f(X))^2] 
&=\int\limits_\infty^\infty \int\limits_\infty^\infty(y-f(x))^2f_{XY}(x,y)dxdy \\
&= \int\limits_\infty^\infty \underbrace{ \int\limits_\infty^\infty(y-f(x))^2f_{Y \mid X}(y) \: dy }_\text{$\mathbb{E}_{Y|X}[(Y-f(x))^2\:|\:X]$} \: f_{X}(x)dx \\
&=\mathbb{E}_{x_0 \sim f_{X}(x)} \left[ \mathbb{E}_{Y|X = x_0}[(Y-f(x_0))^2\:|\:X=x_0]\right] \\
\rightarrow f(x)&=argmin_c \:\mathbb{E}_{Y|X=x}[(Y-c)^2\:|\:X=x]=\mathbb{E}[Y\:|\:X=x]
\end{split}
$$


Tags: statistical estimator, statistical learning
<!--ID: 1674122984694-->
END