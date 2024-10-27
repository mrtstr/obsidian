
### approximated ml estimator
- the [[maximum likelihood estimator]] is found by setting the [[derivative]] of the [[logarithm]] of the [[likelihood function]] to zero
- this can be approximated by using the [[newton methode]] and an initial guess for the estimator $\hat\vartheta_n^{(0)}$

- one parameter case:

$$
Q_n(\vartheta) = \frac{d}{d \vartheta} \ln{f_\vartheta}(X) = 0
$$

- multi parameter case:

$$
Q_n(\vartheta) = \nabla \ln{f_\vartheta}(X) = 0
$$

- [[linear approximation]] $l(d) \approx Q_n(\vartheta)$

$$
\begin{split}
l(d)  
&= Q_n(\hat\vartheta_n) + \nabla Q_n(\hat\vartheta_n)^\top d = 0 \\
\Rightarrow d &= -\nabla Q_n(\hat\vartheta_n)^{-\top }Q_n(\hat\vartheta_n)
\end{split}
$$

$$
\begin{split}
\hat\vartheta^{(1)}_{ML} 
&= \hat\vartheta_n^{(0)} + d \\
&= \hat\vartheta_n^{(0)} -\nabla Q_n(\hat\vartheta^{(0)}_n)^{-\top }Q_n(\hat\vartheta_n^{(0)}) \\
\end{split}
$$

### approximated ml estimator is $\sqrt{n}$ consitent 
$$
\begin{split}
\sqrt{n}\left(\hat\vartheta^{(1)}_{ML} - \vartheta \right) 
&= \sqrt{n}\left(\hat\vartheta^{(1)}_{ML} - \vartheta \right) \\
&= \sqrt{n}\left(DQ_n\left(\hat\vartheta_n^{(0)}\right)^{-1}Q_n\left(\hat\vartheta^{(0)}_n\right) - \hat\vartheta_n - \vartheta \right) \\

\end{split}
$$

TODO finish proof

# ----------------
![[estimator consitency#$ sqrt{n}$ consitency]]


![[maximum likelihood estimator#calculation of the maximum likelihood estimator]]

![[linear approximation#linear aproximation of $f: mathbb{R} m to mathbb{R}$]]

![[root finding problem#solving the root finding problem with the newton methode]]

![[newton methode#newton method]]


# anki

START
Basic
[[approximated ml estimator]]
- methode
- consitency (without proof)
Back: 

### approximated ml estimator
- the [[maximum likelihood estimator]] is found by setting the [[derivative]] of the [[logarithm]] of the [[likelihood function]] to zero
- this can be approximated by using the [[newton methode]] and an initial guess for the estimator $\hat\vartheta_n^{(0)}$

- one parameter case:

$$
Q_n(\vartheta) = \frac{d}{d \vartheta} \ln{f_\vartheta}(X) = 0
$$

- multi parameter case:

$$
Q_n(\vartheta) = \nabla \ln{f_\vartheta}(X) = 0
$$

- [[linear approximation]] $l(d) \approx Q_n(\vartheta)$

$$
\begin{split}
l(d)  
&= Q_n(\hat\vartheta_n) + \nabla Q_n(\hat\vartheta_n)^\top d = 0 \\
\Rightarrow d &= -\nabla Q_n(\hat\vartheta_n)^{-\top }Q_n(\hat\vartheta_n)
\end{split}
$$

$$
\begin{split}
\hat\vartheta^{(1)}_{ML} 
&= \hat\vartheta_n^{(0)} + d \\
&= \hat\vartheta_n^{(0)} -\nabla Q_n(\hat\vartheta^{(0)}_n)^{-\top }Q_n(\hat\vartheta_n^{(0)}) \\
\end{split}
$$
### approximated ml estimator is $\sqrt{n}$ consitent 

___________

### linear aproximation of $f: \mathbb{R}^m \to \mathbb{R}$
- given a [[function]] $f: \mathbb{R}^m \to \mathbb{R}$ the following is a [[linear approximation]] (or linear model) of $f$ of point $x_0$

$$
l_{x_0}(d) = f(x_0) + \nabla f(x_0)^\top d
$$

- this is eqivalent to a [[taylor series#second taylor apploximation $f: mathbb{R} m to mathbb{R}$|first degree taylor apploximation]]


### calculation of the maximum likelihood estimator
- given $n$ samples $X_1, ..., X_n \sim f_X(x | \theta)$ with a [[n fold statistical model]] the [[likelihood function]] will look like the following

$$
\varrho(\vartheta) = \prod_{i=1}^n f_X(X_i | \theta)
$$
- to calculate the maximum we need the [[derivative]] but we can use the fact that the paramter that maximizes the [[likelihood function]] will also maximize the [[logarithm]] of the [[likelihood function]]
$$
arg\max_\vartheta  \ln(\varrho(x, \vartheta)) = arg\max_\vartheta  \varrho(x, \vartheta)
$$
- thus we can maximize the following function instead
$$
\ln(\varrho(\vartheta)) = \sum_{i=1}^n \ln(f_X(X_i | \theta))
$$
$$
\frac{d\ln(\varrho(\vartheta))}{d\vartheta} = \sum_{i=1}^n \frac{d\ln\left(f_X(X_i | \theta)\right)}{d\vartheta} = 0
$$


### newton method
- iterative algorithm for solving continious optimization problems using the second [[derivative]] ([[hessian]])
- useses a direction that minimizes the [[quadratic aproximation]] of $f$ in point $x^{(k)}$ 
$$
\begin{split}
d 
&= arg\min  f\left(x^{(k)}\right) + \nabla f\left(x^{(k)}\right)^\top d + \frac{1}{2} \nabla^2  d^\top f\left(x^{(k)}\right) d \\
&= arg\min  \nabla f\left(x^{(k)}\right)^\top d + \frac{1}{2} \nabla^2  d^\top f\left(x^{(k)}\right) d \\
\Rightarrow& \nabla f\left(x^{(k)}\right) +  \nabla^2  f\left(x^{(k)}\right) d = 0 \\
\Rightarrow& d = - \nabla^2  f\left(x^{(k)}\right)^{-1} \nabla f\left(x^{(k)}\right) \\
\end{split}
$$
- with the [[gradient descent]] method the [[linear approximation]] is used which does not have a minimum thus we can only get a direction (negative [[gradient]])
- but with the [[newton methode]] the [[quadratic aproximation]] is minimized thus the step size is already incuded in $d$ → $\alpha=1$

$$
x^{(k+1)} = x^{(k)} - \nabla^2  f\left(x^{(k)}\right)^{-1} \nabla f\left(x^{(k)}\right)
$$


Tags: mathematics statistics WS2425
<!--ID: 1729757165035-->
END