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

### convergence of the newton method
- the [[newton methode]] converges quandraticly
TODO add proof

![[convergence rates#quadratic convergent]]

### properties of the newton direction
- the newton direction $d$ is a descent direction of $\nabla f(x)^\top d < 0$
$$
d = - \nabla^2  f\left(x^{(k)}\right)^{-1} \nabla f\left(x^{(k)}\right)
$$

- thus the following condition has to hold true, but this is not nessiraity true for a general function $f$ because the [[hessian matrix]] $\nabla^2  f\left(x^{(k)}\right)$ does not have to be positive semi definite
$$
\nabla f(x)^\top \nabla^2  f\left(x^{(k)}\right)^{-1} \nabla f\left(x^{(k)}\right) < 0
$$

![[descent direction#descent direction]]

### newton step for a quadratic function
- given the qudratic function $f: \mathbb{R}^{m} \to \mathbb{R}$ 
- one newton step will find the exact solution of the problem
$$
\begin{split}
f(x) &= \frac{1}{2} x^\top Q x + c^\top x \\
\nabla f(x) &=  Q x + c \\
\nabla^2 f(x) &=  Q  \\
d 
&= - \nabla^2 f(x)^{-1} \nabla f(x) \\
&= - Q^{-1} \left(Q x + c\right) \\
&= -  x - Q^{-1}c \\
x^{(1)} 
&= x^{(0)} x^{(0)} - Q^{-1}c \\
&= - Q^{-1}c \\
\end{split}
$$
# ----------------------


![[quadratic aproximation#quadratic aproximationof $f: mathbb{R} m to mathbb{R}$]]


![[general descent method]]



START
Basic
[[newton methode]]
- definition
- direction
- step size
- convergence

Back: 
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

### convergence of the newton method
- the [[newton methode]] converges quandraticly

#### quadratic convergent
- a [[convergence|convergent]] sequence $\left\{x^{(k)}\right\}$ with a limit $x^*$ is **quadratic convergent** if the following is true

$$
\exists K: \exists \omega \in [0,\infty): \forall k > K: \frac{\left|\left| x^{(k+1)} -x^* \right|\right|}{\left|\left| x^{(k)} -x^* \right|\right|^2} \leq \omega
$$




### quadratic aproximationof $f: \mathbb{R}^m \to \mathbb{R}$
- given a [[function]] $f: \mathbb{R}^m \to \mathbb{R}$ the following is a [[quadratic aproximation]] (or quadratic model) of $f$ of point $x_0$

$$
q_{x_0}(d) = f(x_0) + \nabla f(x_0)^\top d + \frac{1}{2} \nabla  d^\top f(x_0) d
$$

_______________________

### general descent method
- iterative algorithm for solving continious optimization problems
- for generally we start from a point $x^{(0)}$ and go steps of the length $\alpha^{(k)}$ in the direction $d$ untill we find a [[local minimum]]
$$
x^{(k+1)} = x^{(k)} + \alpha^{(k)} d^{(k)}
$$


### gradient descent
- iterative algorithm for solving continious optimization problems using the first order [[derivative]]
- [[gradient descent]] is a [[general descent method]] where we use the negative [[gradient]] $\nabla f\left(x^{(k)}\right)$ as direction which is the direction of the steeptest desecent in point $x^{(k)}$
- we choose a stepsize $\alpha^{(k)} \in (0,1]$

$$
x^{(k+1)} = x^{(k)} - \alpha^{(k)} \nabla f\left(x^{(k)}\right)
$$

- this can be iterpreted as seaching the [[minimum]] of the [[linear approximation]] of $f$ in each point


Tags: mathematics
<!--ID: 1721058003148-->
END



START
Basic
if the newton direction allways a descent direction?



Back: 
### properties of the newton direction
- the newton direction $d$ is a descent direction of $\nabla f(x)^\top d < 0$
$$
d = - \nabla^2  f\left(x^{(k)}\right)^{-1} \nabla f\left(x^{(k)}\right)
$$

- thus the following condition has to hold true, but this is not nessiraity true for a general function $f$ because the [[hessian matrix]] $\nabla^2  f\left(x^{(k)}\right)$ does not have to be positive semi definite
$$
\nabla f(x)^\top \nabla^2  f\left(x^{(k)}\right)^{-1} \nabla f\left(x^{(k)}\right) < 0
$$
_______________________

### descent direction
- given a [[general descent method]]
- every direction $d^{(k)}$ is a [[descent direction]] if it satsifies the following condition with $\nu >0$

$$
- \frac{\nabla f \left(x^{(k)}\right)^\top d^{(k)}}{\left|\left|\nabla f \left(x^{(k)}\right)^\top\right|\right| \ \left|\left|d^{(k)}\right|\right|} = \cos(\phi) > \nu
$$
- if $\cos(\phi)=0$ we have no improvement at all because we move parallel to the current [[level set]] so we want a $\nu > 0$ with the maximal possible value being $\mu=1$ when $\nabla f \left(x^{(k)}\right) = d$ ([[cauchy schwarz inequality]])


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

### convergence of the newton method
- the [[newton methode]] converges quandraticly

#### quadratic convergent
- a [[convergence|convergent]] sequence $\left\{x^{(k)}\right\}$ with a limit $x^*$ is **quadratic convergent** if the following is true

$$
\exists K: \exists \omega \in [0,\infty): \forall k > K: \frac{\left|\left| x^{(k+1)} -x^* \right|\right|}{\left|\left| x^{(k)} -x^* \right|\right|^2} \leq \omega
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


### gradient descent
- iterative algorithm for solving continious optimization problems using the first order [[derivative]]
- [[gradient descent]] is a [[general descent method]] where we use the negative [[gradient]] $\nabla f\left(x^{(k)}\right)$ as direction which is the direction of the steeptest desecent in point $x^{(k)}$
- we choose a stepsize $\alpha^{(k)} \in (0,1]$

$$
x^{(k+1)} = x^{(k)} - \alpha^{(k)} \nabla f\left(x^{(k)}\right)
$$

- this can be iterpreted as seaching the [[minimum]] of the [[linear approximation]] of $f$ in each point


Tags: mathematics
<!--ID: 1722870435343-->
END



START
Basic
find the minimum of the following function using the [[newton methode]]

$$
\begin{split}
f(x) &= \frac{1}{2} x^\top Q x + c^\top x \\
\end{split}
$$

Back: 
### newton step for a quadratic function
- given the qudratic function $f: \mathbb{R}^{m} \to \mathbb{R}$ 
- one newton step will find the exact solution of the problem
$$
\begin{split}
f(x) &= \frac{1}{2} x^\top Q x + c^\top x \\
\nabla f(x) &=  Q x + c \\
\nabla^2 f(x) &=  Q  \\
d 
&= - \nabla^2 f(x)^{-1} \nabla f(x) \\
&= - Q^{-1} \left(Q x + c\right) \\
&= -  x - Q^{-1}c \\
x^{(1)} 
&= x^{(0)} x^{(0)} - Q^{-1}c \\
&= - Q^{-1}c \\
\end{split}
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

- with the [[gradient descent]] method the [[linear approximation]] is used which does not have a minimum thus we can only get a direction (negative [[gradient]])
- but with the [[newton methode]] the [[quadratic aproximation]] is minimized thus the step size is already incuded in $d$ → $\alpha=1$

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


### gradient descent
- iterative algorithm for solving continious optimization problems using the first order [[derivative]]
- [[gradient descent]] is a [[general descent method]] where we use the negative [[gradient]] $\nabla f\left(x^{(k)}\right)$ as direction which is the direction of the steeptest desecent in point $x^{(k)}$
- we choose a stepsize $\alpha^{(k)} \in (0,1]$

$$
x^{(k+1)} = x^{(k)} - \alpha^{(k)} \nabla f\left(x^{(k)}\right)
$$

- this can be iterpreted as seaching the [[minimum]] of the [[linear approximation]] of $f$ in each point


Tags: mathematics
<!--ID: 1722870435348-->
END