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


![[quadratic aproximation#quadratic aproximationof $f: mathbb{R} m to mathbb{R}$]]


![[general descent method]]



START
Basic
[[newton method]]
- definition
- direction
- step size

Back: 
### general descent method
- iterative algorithm for solving continious optimization problems
- for generally we start from a point $x^{(0)}$ and go steps of the length $\alpha^{(k)}$ in the direction $d$ untill we find a [[local minimum]]
$$
x^{(k+1)} = x^{(k)} + \alpha^{(k)} d^{(k)}
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
- with the [[gradient descent]] method the [[linear aproximation]] is used which does not have a minimum thus we can only get a direction (negative [[gradient]])
- but with the [[newton method]] the [[quadratic aproximation]] is minimized thus the step size is already incuded in $d$ → $\alpha=1$

### quadratic aproximationof $f: \mathbb{R}^m \to \mathbb{R}$
- given a [[function]] $f: \mathbb{R}^m \to \mathbb{R}$ the following is a [[quadratic aproximation]] (or quadratic model) of $f$ of point $x_0$

$$
q_{x_0}(d) = f(x_0) + \nabla f(x_0)^\top d + \frac{1}{2} \nabla  d^\top f(x_0) d
$$


_______________________

### gradient descent
- iterative algorithm for solving continious optimization problems using the first order [[derivative]]
- [[gradient descent]] is a [[general descent method]] where we use the negative [[gradient]] $\nabla f\left(x^{(k)}\right)$ as direction which is the direction of the steeptest desecent in point $x^{(k)}$
- we choose a stepsize $\alpha^{(k)} \in (0,1]$

$$
x^{(k+1)} = x^{(k)} - \alpha^{(k)} \nabla f\left(x^{(k)}\right)
$$

- this can be iterpreted as seaching the [[minimum]] of the [[linear aproximation]] of $f$ in each point


Tags: mathematics
<!--ID: 1721058003148-->
END