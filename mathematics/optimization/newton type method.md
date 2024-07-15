### newton type method
- [[newton method]] with an approximated [[hessian]] $B$
- with $B = \nabla^2 f\left(x^{(k)}\right)$ it's the [[newton method]]

$$
x^{(k+1)} = x^{(k)} - \alpha^{(k)}  B^{-1} \nabla f\left(x^{(k)}\right)
$$
- the approximation can be done for example with the BFGS method


### convergence of the newton type method
- the [[newton type method]] can converge superlinear in a (possibly small area around the [[local minimum]]) when the following conditions are satisfied
1) the negative gradient is used when the newton type direction is not a descenting direction
2) [[armijo line search]] is used


![[convergence rates#superlinear convergent]]


![[newton method#newton method]]


# anki


START
Basic
[[newton type method]]
- definition
- convergende

Back: 
### newton type method
- [[newton method]] with an approximated [[hessian]] $B$
- with $B = \nabla^2 f\left(x^{(k)}\right)$ it's the [[newton method]]

$$
x^{(k+1)} = x^{(k)} - \alpha^{(k)}  B^{-1} \nabla f\left(x^{(k)}\right)
$$
- the approximation can be done for example with the BFGS method

### convergence of the newton type method
- the [[newton type method]] can converge superlinear in a (possibly small area around the [[local minimum]]) when the following conditions are satisfied
1) the negative gradient is used when the newton type direction is not a descenting direction
2) [[armijo line search]] is used


### superlinear convergent
- a [[convergence|convergent]] sequence $\left\{x^{(k)}\right\}$ with a limit $x^*$ is **superlinear convergent** if there exists a linear converging sequence $\kappa^{(k)} \xrightarrow{k \to \infty} 0$ and $\kappa^{(k)} \in [0,1]:$ such that the following is true

$$
\exists K: \forall k > K: \frac{\left|\left| x^{(k+1)} -x^* \right|\right|}{\left|\left| x^{(k)} -x^* \right|\right|} \leq \kappa^{(k)}
$$

_______________________
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

- with the [[gradient descent]] method the [[linear aproximation]] is used which does not have a minimum thus we can only get a direction (negative [[gradient]])
- but with the [[newton method]] the [[quadratic aproximation]] is minimized thus the step size is already incuded in $d$ → $\alpha=1$

$$
x^{(k+1)} = x^{(k)} - \nabla^2  f\left(x^{(k)}\right)^{-1} \nabla f\left(x^{(k)}\right)
$$

### quadratic aproximationof $f: \mathbb{R}^m \to \mathbb{R}$
- given a [[function]] $f: \mathbb{R}^m \to \mathbb{R}$ the following is a [[quadratic aproximation]] (or quadratic model) of $f$ of point $x_0$

$$
q_{x_0}(d) = f(x_0) + \nabla f(x_0)^\top d + \frac{1}{2} \nabla  d^\top f(x_0) d
$$

### general descent method
- iterative algorithm for solving continious optimization problems
- for generally we start from a point $x^{(0)}$ and go steps of the length $\alpha^{(k)}$ in the direction $d$ untill we find a [[local minimum]]
$$
x^{(k+1)} = x^{(k)} + \alpha^{(k)} d^{(k)}
$$




Tags: mathematics
<!--ID: 1721061309921-->
END