### gradient descent
- iterative algorithm for solving continious optimization problems using the first order [[derivative]]
- [[gradient descent]] is a [[general descent method]] where we use the negative [[gradient]] $\nabla f\left(x^{(k)}\right)$ as direction which is the direction of the steeptest desecent in point $x^{(k)}$
- we choose a stepsize $\alpha^{(k)} \in (0,1]$

$$
x^{(k+1)} = x^{(k)} - \alpha^{(k)} \nabla f\left(x^{(k)}\right)
$$

- this can be iterpreted as seaching the [[minimum]] of the [[linear aproximation]] of $f$ in each point

### convergence of gradient descent
- [[gradient descent]] with the [[armijo line search]] is converging linearly against a [[local minimum]]

![[armijo line search#armijo condition]]

![[convergence rates#linear convergent]]
# ---------------------------

![[general descent method#general descent method]]

![[linear aproximation#linear aproximation of $f: mathbb{R} m to mathbb{R}$]]

![[derivative#derivative as a vector in the direction of the steepest ascent]]


# anki

START
Basic
[[gradient descent]]
- definition and difference to a [[general descent method]]
- convergence

Back: 
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

- this can be iterpreted as seaching the [[minimum]] of the [[linear aproximation]] of $f$ in each point

### convergence of gradient descent
- [[gradient descent]] with the [[armijo line search]] is converging linearly against a [[local minimum]]

### armijo condition
- condition for a sufficiently large decending step size
- based on a tuning parameter $\gamma \in (0,1]$ 
$$
f(x + \alpha d) < f(x) + \gamma \alpha \nabla f(x)^\top d
$$
- to calculate a stepsize that satsifies the condition there are multiple methods e.g. select $\beta \in (0, 1)$ and try $\alpha = \beta^i$ until $\alpha$ satisfies the armijo condition 


### linear convergent
- a [[convergence|convergent]] sequence $\left\{x^{(k)}\right\}$ with a limit $x^*$ is **linearly convergent** if the following is true

$$
\exists K: \exists \kappa \in [0,1]: \forall k > K: \frac{\left|\left| x^{(k+1)} -x^* \right|\right|}{\left|\left| x^{(k)} -x^* \right|\right|} \leq \kappa
$$


_______________________
#### [[derivative]] as a [[vector]] in the direction of the steepest ascent
- before the forcus was on what the [[derivative]] $Df(x_0)[h]: X \to Y, Df(x_0)[h]=Ah$ does, but now we will focus thee properties of $A$ itself
- let's assume that $f: \mathbb{R}^m \to \mathbb{R}$ and thus $h, A^\top \in \mathbb{R}^m$ 
- we know that the [[derivative]] $Df(x_0)[h]=Ah = \langle A^\top, h \rangle = ||proj_h(A^\top)|| \cdot ||h||$ is the rate of change in the direction $h$ and the length of the [[projection]] of $A$ on the direction $h$
- from the [[cauchy schwarz inequality]] we know that the length of the [[projection]] of $A^\top$ on any $h$ is less or equal then the length of $A^\top$ itself with a maximum reachen at $h = A^\top$ 
$$
||proj_h(A^\top)|| \leq ||A^\top||
$$
- thus the [[vector]] $\frac{A^\top}{||A^\top||}$ is pointing in the direction of the steepest ascent
$$
\begin{split}
arg\max_{||h||=1} ||proj_h\left(A^\top\right)|| 
=arg\max_{||h||=1} \langle A^\top, h \rangle 
&= \frac{A^\top}{||A^\top||} \\ 
\end{split}
$$
- to get the rate of change in the direction of the steepest asecent we can just plug $h^* = \frac{A^\top}{||A^\top||}$ it into the [[derivative]] to see that the steepest rate if ascent is equal to the length of the [[vector]] $A^\top$
$$
Df(x)\left[\frac{A^\top}{||A^\top||}\right] = \frac{AA^\top}{||A^\top||} = \frac{\langle A, A \rangle}{||A^\top||} = \frac{||A^\top||^2}{||A^\top||} = ||A^\top||\in \mathbb{R}
$$
- this result can be generalized for a function $f: \mathbb{R}^m \to \mathbb{R}^n$ by treating $f$ as $n$ scalar functions $f_i$ 

### linear aproximation of $f: \mathbb{R}^m \to \mathbb{R}$
- given a [[function]] $f: \mathbb{R}^m \to \mathbb{R}$ the following is a [[linear aproximation]] (or linear model) of $f$ of point $x_0$

$$
l_{x_0}(d) = f(x_0) + \nabla f(x_0)^\top d
$$

- this is eqivalent to a [[taylor series#second taylor apploximation $f: mathbb{R} m to mathbb{R}$|first degree taylor apploximation]]


### local minimum
- given a [[function]] $f: X \to Y$
- the point $x^* \in X$ is called a [[local minimum]] if the following is true

$$
\forall y \in B_\epsilon(x^*) : f(x^*) \leq f(y)
$$

- with $\epsilon \to \infty$ the local minumum $x^*$ becomes a global minimum 
- if $\leq$ is replaced by $<$ the minimum $x^*$ becomes a strick minimum
- for a [[convex function]] $f(x)$ every [[local minimum]] is a gloabl [[minimum]]  

Tags: mathematics
<!--ID: 1721024324927-->
END


START
Basic
[[gradient descent]]
- when does it converge?
- how fast does it converge?

Back: 
### convergence of gradient descent
- [[gradient descent]] with the [[armijo line search]] is converging linearly against a [[local minimum]]

### armijo condition
- condition for a sufficiently large decending step size
- based on a tuning parameter $\gamma \in (0,1]$ 
$$
f(x + \alpha d) < f(x) + \gamma \alpha \nabla f(x)^\top d
$$
- to calculate a stepsize that satsifies the condition there are multiple methods e.g. select $\beta \in (0, 1)$ and try $\alpha = \beta^i$ until $\alpha$ satisfies the armijo condition 


### linear convergent
- a [[convergence|convergent]] sequence $\left\{x^{(k)}\right\}$ with a limit $x^*$ is **linearly convergent** if the following is true

$$
\exists K: \exists \kappa \in [0,1]: \forall k > K: \frac{\left|\left| x^{(k+1)} -x^* \right|\right|}{\left|\left| x^{(k)} -x^* \right|\right|} \leq \kappa
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

- this can be iterpreted as seaching the [[minimum]] of the [[linear aproximation]] of $f$ in each point

### local minimum
- given a [[function]] $f: X \to Y$
- the point $x^* \in X$ is called a [[local minimum]] if the following is true

$$
\forall y \in B_\epsilon(x^*) : f(x^*) \leq f(y)
$$

- with $\epsilon \to \infty$ the local minumum $x^*$ becomes a global minimum 
- if $\leq$ is replaced by $<$ the minimum $x^*$ becomes a strick minimum
- for a [[convex function]] $f(x)$ every [[local minimum]] is a gloabl [[minimum]]  

Tags: mathematics
<!--ID: 1721056221182-->
END