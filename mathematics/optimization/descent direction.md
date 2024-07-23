### descent direction
- given a [[general descent method]]
- every direction $d^{(k)}$ is a [[descent direction]] if it satsifies the following condition with $\nu >0$

$$
- \frac{\nabla f \left(x^{(k)}\right)^\top d^{(k)}}{\left|\left|\nabla f \left(x^{(k)}\right)^\top\right|\right| \ \left|\left|d^{(k)}\right|\right|} = \cos(\phi) > \nu
$$
- if $\cos(\phi)=0$ we have no improvement at all because we move parallel to the current [[level set]] so we want a $\nu > 0$ with the maximal possible value being $\mu=1$ when $\nabla f \left(x^{(k)}\right) = d$ ([[cauchy schwarz inequality]])

![[IMG-20240723-WA0005.jpg]]

- note: the [[inner product]] pretween the [[gradient]] and the (normalized) direction is equivalent to the length of the [[projection]] of the [[gradient]] in the direction $d$ thus the share of $d$ that leads to an improvement 
$$
\left\langle - \nabla f \left(x^{(k)}\right), d\right\rangle = \left|\left| \mathrm{Proj}_d\left(\nabla f \left(x^{(k)}\right)\right) \right|\right| \cdot ||d||
$$

# ---------------------

![[general descent method#general descent method]]

![[cauchy schwarz inequality#cauchy schwarz inequality]]

![[projection#projection of vector vectors on eachother]]

# anki

START
Basic
- given a general [[general descent method]]
- which condition has $d$ to satsify to be a [[descent direction]]?
- How to measure the grade of descent in a point $x$?

### general descent method
- iterative algorithm for solving continious optimization problems
- for generally we start from a point $x^{(0)}$ and go steps of the length $\alpha^{(k)}$ in the direction $d$ untill we find a [[local minimum]]
$$
x^{(k+1)} = x^{(k)} + \alpha^{(k)} d^{(k)}
$$
Back: 

### descent direction
- given a [[general descent method]]
- every direction $d^{(k)}$ is a [[descent direction]] if it satsifies the following condition with $\nu >0$

$$
- \frac{\nabla f \left(x^{(k)}\right)^\top d^{(k)}}{\left|\left|\nabla f \left(x^{(k)}\right)^\top\right|\right| \ \left|\left|d^{(k)}\right|\right|} = \cos(\phi) > \nu
$$
- if $\cos(\phi)=0$ we have no improvement at all because we move parallel to the current [[level set]] so we want a $\nu > 0$ with the maximal possible value being $\mu=1$ when $\nabla f \left(x^{(k)}\right) = d$ ([[cauchy schwarz inequality]])

- note: the [[inner product]] pretween the [[gradient]] and the (normalized) direction is equivalent to the length of the [[projection]] of the [[gradient]] in the direction $d$ thus the share of $d$ that leads to an improvement 
$$
\left\langle - \nabla f \left(x^{(k)}\right), d\right\rangle = \left|\left| \mathrm{Proj}_d\left(\nabla f \left(x^{(k)}\right)\right) \right|\right| \cdot ||d||
$$

![[IMG-20240723-WA0005 1.jpg]]


_______________________

### cauchy schwarz inequality
- let $V$ be a [[vector space]] with an [[inner product]] $\langle \cdot , \cdot \rangle$ 
- then the following is true for all $x, y \in V$

$$
|\langle x , y \rangle|^2 \leq \langle x , x \rangle \cdot \langle y , y \rangle
$$
$$
|\langle x , y \rangle| \leq || x || \cdot || y ||
$$

### [[projection]] of [[vector|vectors]] on eachother
- let $b' = proj_b(a)$ be the projection of [[vector]] $a$ on [[vector]] $b$
- the length of $proj_b(a)$ is given by the [[inner product]] of $a$  and $b$ devided by the length of $b$ (because the length of the [[projection]] on $proj_b(a)$ does not depend on the length of $b$)

$$
||proj_b(a)|| = ||b'|| = \frac{\langle a,b \rangle}{||b||}
$$
- since $b'$ has the same direction as b the following is true
$$
proj_b(a) = b' = \frac{\langle a,b \rangle}{||b||} \frac{b}{||b||}
$$


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


### gradient descent
- iterative algorithm for solving continious optimization problems using the first order [[derivative]]
- for generally we start from a point $x^{(0)}$ and go steps of the length $\alpha^{(k)}$ in the direction $d$ untill we find a [[local minimum]]
$$
x^{(k+1)} = x^{(k)} + \alpha^{(k)} d^{(k)}
$$
- for [[gradient descent]] we use the negative [[gradient]] $\nabla f\left(x^{(k)}\right)$ as direction which is the direction of the steeptest desecent in point $x^{(k)}$
- we choose a stepsize $\alpha^{(k)} \in (0,1]$

$$
x^{(k+1)} = x^{(k)} - \alpha^{(k)} \nabla f\left(x^{(k)}\right)
$$

- this can be iterpreted as seaching the [[minimum]] of the [[linear aproximation]] of $f$ in each point


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
<!--ID: 1721024324921-->
END