# [[mean square error]]
[[loss function]]

# Definition
For a [[statistical estimator_old|statistical estimaton]] $\widehat{x}$ of the [[random variable]] $X$ the [[mean square error]] is defined as the following
$$
L_{MSE}(X, \widehat{x})=\mathbb{E}\left[(X-\widehat{x})^2\right]
$$

For a [[statistical predictor|statistical prediction]] of the [[random variable]] $Y$ given a dependent [[random variable]] $X$ the [[mean square error]] is defined as the following
$$
L_{MSE}(X, f(x))=\mathbb{E}\left[(X-f(x))^2\right]
$$
$L(Y, f(x))=E[(Y-f(x))^2] \rightarrow f(x)=E[Y|X=x]$  


# [[mean square error|mse]] optimizing [[statistical estimator_old|statistical estimaton]] $\widehat{x}$

The [[statistical estimator_old|statistical estimaton]] $\widehat{x}$ of the [[random variable]] $X$ that is minimizing the [[mean square error]] is the [[expectation]] $\widehat{x}_{MSE}=\mathbb{E}[X]$.
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
# [[mean square error|mse]] optimizing [[statistical predictor]] $f(x)$
## optimal [[statistical predictor]] $f(x)$
The [[statistical predictor]] $f(x)$ that is minimizing the [[mean square error]] is the [[conditional expectation]] $f_{MSE}(x)=\mathbb{E}[Y\:|\:X=x]$

### proof
- from the [[law of total probability]] we know that $\mathbb{E}[(Y-f(X))^2] =\mathbb{E}\left[\mathbb{E}\left[(Y-f(X))^2 | X \right] \right]$
![[conditional expectation#law of total probability for expectation expectations general case]]

- for an observed $x_0$ $\mathbb{E}\left[\mathbb{E}\left[(Y-f(x_0))^2 | X=x_0 \right] \right] = \mathbb{E}\left[(Y-f(x_0))^2 | X=x_0 \right]$ since its a constant
- if we can prove for every $x$ that $f(x)=argmin_c \:\mathbb{E}_{Y|X=x}[(Y-c)^2\:|\:X=x]=\mathbb{E}[Y\:|\:X=x]$ its clear that $f(X)=\mathbb{E}[Y\:|\:X]$ is also true
$$
\begin{split}
\frac{d \mathbb{E}_{Y|X=x}[(Y-c)^2\:|\:X=x]}{dc} &= 0 \\
&=\frac{d \mathbb{E}_{Y|X=x}[Y^2\:|\:X=x]+c^2-2\mathbb{E}_{Y|X=x}[Y\:|\:X=x]c}{dc}  \\
&= 2x-2\mathbb{E}_{Y|X=x}[Y\:|\:X=x] \\
\rightarrow c&=\mathbb{E}_{Y|X=x}[Y\:|\:X=x] = f(x) 
\end{split}
$$
# error of optimal [[statistical predictor]] $f(x) = \mathbb{E}_{Y|X=x}[Y\:|\:X=x]$

- for every constant $X=x_0$ the [[mean square error]] for an optimal [[statistical predictor]] $f(x) = \mathbb{E}_{Y|X=x}[Y\:|\:X=x]$ is equal to the [[conditional variance]] of $Y$ given $X=x$
$$
\mathbb{E}\left[(Y-\mathbb{E}_{Y|X=x_0}[Y\:|\:X])^2 | X=x_0 \right] = \mathbb{VAR}_{Y|X=x_0}\left[Y\:|\:X=x_0 \right]
$$
- the expected [[mean square error]] for an optimal [[statistical predictor]] $f(x) = \mathbb{E}_{Y|X}[Y\:|\:X]$ is equal to the [[expectation]] of the  [[conditional variance]] of $Y$ over all possiple $X$ values 
- (remember $\mathbb{E}\left[(Y-\mathbb{E}_{Y|X}[Y\:|\:X])^2 | X \right]$ is a [[function]] of the [[random variable]] $X$)
$$
\mathbb{E}\left[\mathbb{E}\left[(Y-\mathbb{E}_{Y|X}[Y\:|\:X])^2 | X \right]\right] = \mathbb{E}\left[\mathbb{VAR}_{Y|X}\left[Y\:|\:X \right]\right]
$$
- for an optimal [[statistical predictor]] without any observation for $X$ the [[mean square error]] would be $\mathbb{VAR}\left[Y\right]$
- thus the [[mean square error]] improvemnt because of the observation $X=x_0$ would be
$$
\mathbb{VAR}\left[Y\right] -\mathbb{VAR}_{Y|X=x_0}\left[Y\:|\:X=x_0 \right] 
$$
- the [[mean square error]] improvemnt because of a general observation of the [[random variable]] $X$ would be the following
$$
\mathbb{VAR}\left[Y\right] - \mathbb{E}\left[\mathbb{VAR}_{Y|X}\left[Y\:|\:X \right]\right]
= \mathbb{VAR}\left[\mathbb{E}_{Y|X}\left[Y\:|\:X \right]\right]
= \mathbb{VAR}\left[f(X)\right]
$$
- according to the [[law of total probability]] for the [[variance]] the improvement of the [[mean square error]] due to an observation of the [[random variable]] $X$ is equal to the [[variance]] of the optimal [[statistical predictor]] $\mathbb{VAR}\left[\mathbb{E}_{Y|X}\left[Y\:|\:X \right]\right]$ (see [[variance bias trade-off]])
$$

\underbrace{
\mathbb{VAR}\left[Y\right]
}_\text{$=0$}

= \underbrace{
\mathbb{VAR}\left[\mathbb{E}_{Y|X}\left[Y\:|\:X \right]\right]
}_\text{$=0$}

+ \underbrace{
\mathbb{E}\left[\mathbb{VAR}_{Y|X}\left[Y\:|\:X \right]\right]
}_\text{$=0$}
$$
# Anki
START
Basic
[[mean square error]] definition
- [[statistical estimator_old]]
- [[statistical predictor]]
Back: 
For a [[statistical estimator_old|statistical estimaton]] $\widehat{x}$ of the [[random variable]] $X$ the [[mean square error]] is defined as the following
$$
L_{MSE}(X, \widehat{x})=\mathbb{E}\left[(X-\widehat{x})^2\right]
$$

For a [[statistical predictor|statistical prediction]] of the [[random variable]] $Y$ given a dependent [[random variable]] $X$ the [[mean square error]] is defined as the following
$$
L_{MSE}(X, f(x))=\mathbb{E}\left[(X-f(x))^2\right]
$$
$L(Y, f(x))=E[(Y-f(x))^2] \rightarrow f(x)=E[Y|X=x]$  

Tags: mathematics statistical_learning
<!--ID: 1661678999134-->
END


START
Basic
[[mean square error|mse]] optimizing [[statistical estimator_old|statistical estimaton]] $\widehat{x}$ and its error (with proof)
Back: 
### [[statistical estimator_old|statistical estimaton]] $\widehat{x}$
The [[statistical estimator_old|statistical estimaton]] $\widehat{x}$ of the [[random variable]] $X$ that is minimizing the [[mean square error]] is the [[expectation]] $\widehat{x}_{MSE}=\mathbb{E}[X]$.
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

Tags: mathematics statistical_learning
<!--ID: 1674122984694-->
END



START
Basic
- [[statistical predictor]] that minimizes the [[mean square error]] 
- [[mean square error]] of optimal [[statistical predictor]]
- [[mean square error]] improvment due to an observation of $X$

Back: 

### [[statistical predictor]] $f(x)$
The [[statistical predictor]] $f(x)$ that is minimizing the [[mean square error]] is the [[conditional expectation]] $f_{MSE}(x)=\mathbb{E}[Y\:|\:X=x]$

- from the [[law of total probability]] we know that $\mathbb{E}[(Y-f(X))^2] =\mathbb{E}\left[\mathbb{E}\left[(Y-f(X))^2 | X \right] \right]$

$$
\begin{split}
\mathbb{E}\left[\mathbb{E}\left[g(X,Y)|X\right]\right] 
& = \int\limits_{-\infty}^\infty f_{X}(x)  \int\limits_{-\infty}^\infty 
 g(X,Y) \cdot f_{YX|X}(y,x \mid x)dy \:dx \\
& = \int\limits_{-\infty}^\infty f_{X}(x) \int\limits_{-\infty}^\infty 
g(X,Y) \cdot f_{Y|X}(y \mid x)dy \:dx \\
& = \int\limits_{-\infty}^\infty \int\limits_{-\infty}^\infty \frac{f_{X}(x)}{f_{X}(x)}  
g(X,Y) \cdot f_{YX}(y, x)dy \:dx \\
&=  \mathbb{E}\left[g(X,Y)\right]
\end{split}
$$


- for an observed $x_0$ $\mathbb{E}\left[\mathbb{E}\left[(Y-f(x_0))^2 | X=x_0 \right] \right] = \mathbb{E}\left[(Y-f(x_0))^2 | X=x_0 \right]$ since its a constant
- if we can prove for every $x$ that $f(x)=argmin_c \:\mathbb{E}_{Y|X=x}[(Y-c)^2\:|\:X=x]=\mathbb{E}[Y\:|\:X=x]$ its clear that $f(X)=\mathbb{E}[Y\:|\:X]$ is also true

$$
\begin{split}
\frac{d \mathbb{E}_{Y|X=x}[(Y-c)^2\:|\:X=x]}{dc} &= 0 \\
&=\frac{d \mathbb{E}_{Y|X=x}[Y^2\:|\:X=x]+c^2-2\mathbb{E}_{Y|X=x}[Y\:|\:X=x]c}{dc}  \\
&= 2x-2\mathbb{E}_{Y|X=x}[Y\:|\:X=x] \\
\rightarrow c&=\mathbb{E}_{Y|X=x}[Y\:|\:X=x] = f(x) 
\end{split}
$$
### error of optimal [[statistical predictor]] $f(x) = \mathbb{E}_{Y|X=x}[Y\:|\:X=x]$

- for every constant $X=x_0$ the [[mean square error]] for an optimal [[statistical predictor]] $f(x) = \mathbb{E}_{Y|X=x}[Y\:|\:X=x]$ is equal to the [[conditional variance]] of $Y$ given $X=x$
$$
\mathbb{E}\left[(Y-\mathbb{E}_{Y|X=x_0}[Y\:|\:X])^2 | X=x_0 \right] = \mathbb{VAR}_{Y|X=x_0}\left[Y\:|\:X=x_0 \right]
$$
- the expected [[mean square error]] for an optimal [[statistical predictor]] $f(x) = \mathbb{E}_{Y|X}[Y\:|\:X]$ is equal to the [[expectation]] of the [[conditional variance]] of $Y$ over all possiple $X$ values 
- (remember $\mathbb{E}\left[(Y-\mathbb{E}_{Y|X}[Y\:|\:X])^2 | X \right]$ is a [[function]] of the [[random variable]] $X$)
$$
\mathbb{E}\left[\mathbb{E}\left[(Y-\mathbb{E}_{Y|X}[Y\:|\:X])^2 | X \right]\right] = \mathbb{E}\left[\mathbb{VAR}_{Y|X}\left[Y\:|\:X \right]\right]
$$
- for an optimal [[statistical predictor]] without any observation for $X$ the [[mean square error]] would be $\mathbb{VAR}\left[Y\right]$
- thus the [[mean square error]] improvemnt because of the observation $X=x_0$ would be
$$
\mathbb{VAR}\left[Y\right] -\mathbb{VAR}_{Y|X=x_0}\left[Y\:|\:X=x_0 \right] 
$$
- the [[mean square error]] improvemnt because of a general observation of the [[random variable]] $X$ would be the following
$$
\mathbb{VAR}\left[Y\right] - \mathbb{E}\left[\mathbb{VAR}_{Y|X}\left[Y\:|\:X \right]\right]
= \mathbb{VAR}\left[\mathbb{E}_{Y|X}\left[Y\:|\:X \right]\right]
= \mathbb{VAR}\left[f(X)\right]
$$
- according to the [[law of total probability]] for the [[variance]] the improvement of the [[mean square error]] due to an observation of the [[random variable]] $X$ is equal to the [[variance]] of the optimal [[statistical predictor]] $\mathbb{VAR}\left[\mathbb{E}_{Y|X}\left[Y\:|\:X \right]\right]$ (see [[variance bias trade-off]])
Tags: mathematics statistical_learning
<!--ID: 1674988747232-->
END




START
Basic
interpretation of the [[variance]] of a [[mean square error]] optimizing [[statistical predictor]]

Back: 
according to the [[law of total probability]] for the [[variance]] the improvement of the [[mean square error]] due to an observation of the [[random variable]] $X$ is equal to the [[variance]] of the optimal [[statistical predictor]] ($f(X) = \mathbb{E}_{Y|X}[Y\:|\:X=x]$) $\mathbb{VAR}\left[\mathbb{E}_{Y|X}\left[Y\:|\:X \right]\right]$ (see [[variance bias trade-off]])
$$
\mathbb{VAR}\left[Y\right] - \mathbb{E}\left[\mathbb{VAR}_{Y|X}\left[Y\:|\:X \right]\right]
= \mathbb{VAR}\left[\mathbb{E}_{Y|X}\left[Y\:|\:X \right]\right]
= \mathbb{VAR}\left[f(X)\right]
$$

### error of optimal [[statistical predictor]] $f(x) = \mathbb{E}_{Y|X=x}[Y\:|\:X=x]$

- for every constant $X=x_0$ the [[mean square error]] for an optimal [[statistical predictor]] $f(x) = \mathbb{E}_{Y|X=x}[Y\:|\:X=x]$ is equal to the [[conditional variance]] of $Y$ given $X=x$
$$
\mathbb{E}\left[(Y-\mathbb{E}_{Y|X=x_0}[Y\:|\:X])^2 | X=x_0 \right] = \mathbb{VAR}_{Y|X=x_0}\left[Y\:|\:X=x_0 \right]
$$
- the expected [[mean square error]] for an optimal [[statistical predictor]] $f(x) = \mathbb{E}_{Y|X}[Y\:|\:X]$ is equal to the [[expectation]] of the [[conditional variance]] of $Y$ over all possiple $X$ values 
- (remember $\mathbb{E}\left[(Y-\mathbb{E}_{Y|X}[Y\:|\:X])^2 | X \right]$ is a [[function]] of the [[random variable]] $X$)
$$
\mathbb{E}\left[\mathbb{E}\left[(Y-\mathbb{E}_{Y|X}[Y\:|\:X])^2 | X \right]\right] = \mathbb{E}\left[\mathbb{VAR}_{Y|X}\left[Y\:|\:X \right]\right]
$$
- for an optimal [[statistical predictor]] without any observation for $X$ the [[mean square error]] would be $\mathbb{VAR}\left[Y\right]$
- thus the [[mean square error]] improvemnt because of the observation $X=x_0$ would be
$$
\mathbb{VAR}\left[Y\right] -\mathbb{VAR}_{Y|X=x_0}\left[Y\:|\:X=x_0 \right] 
$$
- the [[mean square error]] improvemnt because of a general observation of the [[random variable]] $X$ would be the following
$$
\mathbb{VAR}\left[Y\right] - \mathbb{E}\left[\mathbb{VAR}_{Y|X}\left[Y\:|\:X \right]\right]
= \mathbb{VAR}\left[\mathbb{E}_{Y|X}\left[Y\:|\:X \right]\right]
$$
- according to the [[law of total probability]] for the [[variance]] the improvement of the [[mean square error]] due to an observation of the [[random variable]] $X$ is equal to the [[variance]] of the optimal [[statistical predictor]] $\mathbb{VAR}\left[\mathbb{E}_{Y|X}\left[Y\:|\:X \right]\right]$ (see [[variance bias trade-off]])
Tags: mathematics statistical_learning
<!--ID: 1674997183132-->
END