### sequential quadratic programming
- efficient methode for solving [[constraint optimization problem]] with only equality constraints
- given the following [[constraint optimization problem]] with the objective [[function]] $f: \mathbb{R}^m \to \mathbb{R}$ and equality constraints $g: \mathbb{R}^m \to \mathbb{R}^n$  
$$
\begin{split}
\min_{x \in \mathbb{R}^m} &f(x) \\
\mathrm{s.t.} \: &g(x)=0 \\
\end{split}
$$
- the gole is to minimize the following [[lagrangian of a CNLP]] of the [[unconstraint optimization problem]] by minimizing the [[quadratic aproximation]] ([[newton method]])
$$
\mathcal{L}\left(x, \lambda\right) = f(x) - g(x) \lambda   
$$
- $F(x, \lambda)$ is the [[gradient]] of the [[lagrangian of a CNLP]] $\nabla_{x, \lambda} \mathcal{L}\left(x, \lambda\right)$ 
$$
F(x, \lambda) = \nabla_{x, \lambda} \mathcal{L}\left(x, \lambda\right) =  \left(\begin{matrix}
\nabla f(x) -  \nabla g(x) \lambda \\
g(x)
\end{matrix}\right) = 0
$$
- $\nabla_{x, \lambda} F(x, \lambda)$ is the [[hessian]] of the [[lagrangian of a CNLP]] $\nabla_{x, \lambda} \mathcal{L}\left(x, \lambda\right)$ or the [[gradient]] of $F(x, \lambda)$
$$
\nabla_{x, \lambda} F(x, \lambda) 
= \left(\begin{matrix}
\frac{\partial^2\mathcal{L}\left(x, \lambda\right)}{\partial x \partial x} & \frac{\partial^2\mathcal{L}\left(x, \lambda\right)}{\partial x \partial \lambda} \\
\frac{\partial^2\mathcal{L}\left(x, \lambda\right)}{\partial \lambda \partial x} & \frac{\partial^2\mathcal{L}\left(x, \lambda\right)}{\partial \lambda \partial \lambda}
\end{matrix}\right)
= \left(\begin{matrix}
\nabla^2 f(x) -  \nabla^2 g(x)\lambda & - \nabla g(x)  \\
\nabla g(x)^\top & 0
\end{matrix}\right)
$$
##### newton step
- then we can performe a [[newton method]] step to minimize the problem
$$
\left(\begin{matrix}
x^{(k+1)} \\
\lambda^{(k+1)}
\end{matrix}\right)
=
\left(\begin{matrix}
x^{(k)} \\
\lambda^{(k)}
\end{matrix}\right)
+ \alpha^{(k)}
\left(\begin{matrix}
\nabla^2 f(x) -  \nabla^2 g(x) & - \nabla g(x)  \\
\nabla g(x)^\top & 0
\end{matrix}\right)^{-1}
\left(\begin{matrix}
\nabla f(x) -  \nabla g(x) \lambda \\
g(x)
\end{matrix}\right)
$$

##### transformation into a quadratic problem
- while minimizing the [[quadratic aproximation]] of the [[lagrangian of a CNLP]] we can transform the problem as follows

$$
\begin{split}
d &=  arg\min q(d) \\
&= arg\min \mathcal{L}\left(x, \lambda\right) + d^\top \nabla_{x, \lambda} \mathcal{L}\left(x, \lambda\right) + \frac{1}{2} d^\top 
\left(\begin{matrix}
\frac{\partial^2\mathcal{L}\left(x, \lambda\right)}{\partial x \partial x} & \frac{\partial^2\mathcal{L}\left(x, \lambda\right)}{\partial x \partial \lambda} \\
\frac{\partial^2\mathcal{L}\left(x, \lambda\right)}{\partial \lambda \partial x} & \frac{\partial^2\mathcal{L}\left(x, \lambda\right)}{\partial \lambda \partial \lambda}
\end{matrix}\right)
d \\
&= arg\min d^\top \left(\begin{matrix}
\nabla f(x) -  \nabla g(x) \lambda \\
g(x)
\end{matrix}\right)
+ \frac{1}{2} d^\top 
\left(\begin{matrix}
\nabla^2 f(x) -  \nabla^2 g(x)\lambda & - \nabla g(x)  \\
\nabla g(x)^\top & 0
\end{matrix}\right) d \\
&= arg\min d^\top \left(\begin{matrix}
c\left(x, \lambda\right) \\
g(x)
\end{matrix}\right)
+ \frac{1}{2} d^\top 
\left(\begin{matrix}
H\left(x, \lambda\right) & - \nabla g(x)  \\
\nabla g(x)^\top & 0
\end{matrix}\right) d \\
\end{split} \\
$$


$$
\begin{split}
c\left(x, \lambda\right) &= \nabla f(x) -  \nabla g(x) \lambda \\
H\left(x, \lambda\right) &= \nabla^2 f(x) -  \nabla^2 g(x)\lambda \\
\end{split}
$$
- when adding the equality constraint $g(x) + \nabla g(x)^\top d$ we can transorm the problem in an quadratic optimization problem

$$
\begin{split}
0
&= \frac{\partial }{\partial d} q(d) \\
&= \left(\begin{matrix}
c\left(x, \lambda\right)  \\
g(x)
\end{matrix}\right) 
+
\left(\begin{matrix}
H\left(x, \lambda\right) & - \nabla g(x)  \\
\nabla g(x)^\top & 0
\end{matrix}\right) d \\
\Rightarrow  0 &= g(x) + \nabla g(x)^\top d \\
\end{split} \\
$$

$$
\begin{split}
\min_{x \in \mathbb{R}^m} & \frac{1}{2} d^\top H\left(x^{(k)}, \lambda^{(k)}\right)d + d^\top c\left(x^{(k)}, \lambda^{(k)}\right)  \\
\mathrm{s.t.} \: &g\left(x^{(k)}\right)+\nabla g\left(x^{(k)}\right)^\top d=0 \\
\end{split}
$$


# -----------------------------

![[quadratic aproximation#quadratic aproximationof $f: mathbb{R} m to mathbb{R}$]]

![[newton method#newton method]]

![[lagrangian of a CNLP#lagrangian of a CNLP]]

![[constraint optimization problem]]


# anki


START
Basic
newton methode for [[constraint optimization problem]] with only equality constraints

Back: 
- efficient methode for solving [[constraint optimization problem]] with only equality constraints
- given the following [[constraint optimization problem]] with the objective [[function]] $f: \mathbb{R}^m \to \mathbb{R}$ and equality constraints $g: \mathbb{R}^m \to \mathbb{R}^n$  
$$
\begin{split}
\min_{x \in \mathbb{R}^m} &f(x) \\
\mathrm{s.t.} \: &g(x)=0 \\
\end{split}
$$
- the gole is to minimize the following [[lagrangian of a CNLP]] of the [[unconstraint optimization problem]] by minimizing the [[quadratic aproximation]] ([[newton method]])
$$
\mathcal{L}\left(x, \lambda\right) = f(x) - g(x) \lambda   
$$
- $F(x, \lambda)$ is the [[gradient]] of the [[lagrangian of a CNLP]] $\nabla_{x, \lambda} \mathcal{L}\left(x, \lambda\right)$ 
$$
F(x, \lambda) = \nabla_{x, \lambda} \mathcal{L}\left(x, \lambda\right) =  \left(\begin{matrix}
\nabla f(x) -  \nabla g(x) \lambda \\
g(x)
\end{matrix}\right) = 0
$$
- $\nabla_{x, \lambda} F(x, \lambda)$ is the [[hessian]] of the [[lagrangian of a CNLP]] $\nabla_{x, \lambda} \mathcal{L}\left(x, \lambda\right)$ or the [[gradient]] of $F(x, \lambda)$
$$
\nabla_{x, \lambda} F(x, \lambda) 
= \left(\begin{matrix}
\frac{\partial^2\mathcal{L}\left(x, \lambda\right)}{\partial x \partial x} & \frac{\partial^2\mathcal{L}\left(x, \lambda\right)}{\partial x \partial \lambda} \\
\frac{\partial^2\mathcal{L}\left(x, \lambda\right)}{\partial \lambda \partial x} & \frac{\partial^2\mathcal{L}\left(x, \lambda\right)}{\partial \lambda \partial \lambda}
\end{matrix}\right)
= \left(\begin{matrix}
\nabla^2 f(x) -  \nabla^2 g(x)\lambda & - \nabla g(x)  \\
\nabla g(x)^\top & 0
\end{matrix}\right)
$$
##### newton step
- then we can performe a [[newton method]] step to minimize the problem
$$
\left(\begin{matrix}
x^{(k+1)} \\
\lambda^{(k+1)}
\end{matrix}\right)
=
\left(\begin{matrix}
x^{(k)} \\
\lambda^{(k)}
\end{matrix}\right)
+ \alpha^{(k)}
\left(\begin{matrix}
\nabla^2 f(x) -  \nabla^2 g(x) & - \nabla g(x)  \\
\nabla g(x)^\top & 0
\end{matrix}\right)^{-1}
\left(\begin{matrix}
\nabla f(x) -  \nabla g(x) \lambda \\
g(x)
\end{matrix}\right)
$$


_______________________

### lagrangian of a CNLP
- methode for seaching for stanary points of an [[constraint optimization problem]] by tansforming it in an unconstrain optimization problem → searching for [[kkt conditions|kkt points]]
- the [[lagrangian of a CNLP]] is defined as follows:
$$
\mathcal{L}\left(x, \lambda, \mu\right) = f(x) - \lambda^\top  g(x) - \mu^\top  h(x)
$$

- to find [[kkt conditions|kkt points]] we solve the following system of equations:

$$
\begin{split}
\nabla_x \mathcal{L}\left(x, \lambda, \mu\right)&=f(x) - \lambda^\top  \nabla g(x) - \mu^\top  \nabla h(x)= 0 \\
\nabla_\lambda \mathcal{L}\left(x, \lambda, \mu\right)&= g(x)= 0 \\
\nabla_\mu \mathcal{L}\left(x, \lambda, \mu\right)&= h(x) \geq 0 \\
\end{split}
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
<!--ID: 1721813631684-->
END



START
Basic
[[sequential quadratic programming (SQP)]]
- how to transform a [[constraint optimization problem]] with only inequality conditions into a quadratic problem

Back: 
### sequential quadratic programming
- efficient methode for solving [[constraint optimization problem]] with only equality constraints
- given the following [[constraint optimization problem]] with the objective [[function]] $f: \mathbb{R}^m \to \mathbb{R}$ and equality constraints $g: \mathbb{R}^m \to \mathbb{R}^n$  
$$
\begin{split}
\min_{x \in \mathbb{R}^m} &f(x) \\
\mathrm{s.t.} \: &g(x)=0 \\
\end{split}
$$
- the gole is to minimize the following [[lagrangian of a CNLP]] of the [[unconstraint optimization problem]] by minimizing the [[quadratic aproximation]] ([[newton method]])
$$
\mathcal{L}\left(x, \lambda\right) = f(x) - g(x) \lambda   
$$
- $F(x, \lambda)$ is the [[gradient]] of the [[lagrangian of a CNLP]] $\nabla_{x, \lambda} \mathcal{L}\left(x, \lambda\right)$ 
$$
F(x, \lambda) = \nabla_{x, \lambda} \mathcal{L}\left(x, \lambda\right) =  \left(\begin{matrix}
\nabla f(x) -  \nabla g(x) \lambda \\
g(x)
\end{matrix}\right) = 0
$$
- $\nabla_{x, \lambda} F(x, \lambda)$ is the [[hessian]] of the [[lagrangian of a CNLP]] $\nabla_{x, \lambda} \mathcal{L}\left(x, \lambda\right)$ or the [[gradient]] of $F(x, \lambda)$
$$
\nabla_{x, \lambda} F(x, \lambda) 
= \left(\begin{matrix}
\frac{\partial^2\mathcal{L}\left(x, \lambda\right)}{\partial x \partial x} & \frac{\partial^2\mathcal{L}\left(x, \lambda\right)}{\partial x \partial \lambda} \\
\frac{\partial^2\mathcal{L}\left(x, \lambda\right)}{\partial \lambda \partial x} & \frac{\partial^2\mathcal{L}\left(x, \lambda\right)}{\partial \lambda \partial \lambda}
\end{matrix}\right)
= \left(\begin{matrix}
\nabla^2 f(x) -  \nabla^2 g(x)\lambda & - \nabla g(x)  \\
\nabla g(x)^\top & 0
\end{matrix}\right)
$$

##### transformation into a quadratic problem
- while minimizing the [[quadratic aproximation]] of the [[lagrangian of a CNLP]] we can transform the problem as follows

$$
\begin{split}
d &=  arg\min q(d) \\
&= arg\min \mathcal{L}\left(x, \lambda\right) + d^\top \nabla_{x, \lambda} \mathcal{L}\left(x, \lambda\right) + \frac{1}{2} d^\top 
\left(\begin{matrix}
\frac{\partial^2\mathcal{L}\left(x, \lambda\right)}{\partial x \partial x} & \frac{\partial^2\mathcal{L}\left(x, \lambda\right)}{\partial x \partial \lambda} \\
\frac{\partial^2\mathcal{L}\left(x, \lambda\right)}{\partial \lambda \partial x} & \frac{\partial^2\mathcal{L}\left(x, \lambda\right)}{\partial \lambda \partial \lambda}
\end{matrix}\right)
d \\
&= arg\min d^\top \left(\begin{matrix}
\nabla f(x) -  \nabla g(x) \lambda \\
g(x)
\end{matrix}\right)
+ \frac{1}{2} d^\top 
\left(\begin{matrix}
\nabla^2 f(x) -  \nabla^2 g(x)\lambda & - \nabla g(x)  \\
\nabla g(x)^\top & 0
\end{matrix}\right) d \\
&= arg\min d^\top \left(\begin{matrix}
c\left(x, \lambda\right) \\
g(x)
\end{matrix}\right)
+ \frac{1}{2} d^\top 
\left(\begin{matrix}
H\left(x, \lambda\right) & - \nabla g(x)  \\
\nabla g(x)^\top & 0
\end{matrix}\right) d \\
\end{split} \\
$$


$$
\begin{split}
c\left(x, \lambda\right) &= \nabla f(x) -  \nabla g(x) \lambda \\
H\left(x, \lambda\right) &= \nabla^2 f(x) -  \nabla^2 g(x)\lambda \\
\end{split}
$$
- when adding the equality constraint $g(x) + \nabla g(x)^\top d$ we can transorm the problem in an quadratic optimization problem

$$
\begin{split}
0
&= \frac{\partial }{\partial d} q(d) \\
&= \left(\begin{matrix}
c\left(x, \lambda\right)  \\
g(x)
\end{matrix}\right) 
+
\left(\begin{matrix}
H\left(x, \lambda\right) & - \nabla g(x)  \\
\nabla g(x)^\top & 0
\end{matrix}\right) d \\
\Rightarrow  0 &= g(x) + \nabla g(x)^\top d \\
\end{split} \\
$$

$$
\begin{split}
\min_{x \in \mathbb{R}^m} & \frac{1}{2} d^\top H\left(x^{(k)}, \lambda^{(k)}\right)d + d^\top c\left(x^{(k)}, \lambda^{(k)}\right)  \\
\mathrm{s.t.} \: &g\left(x^{(k)}\right)+\nabla g\left(x^{(k)}\right)^\top d=0 \\
\end{split}
$$


_______________________

### quadratic aproximationof $f: \mathbb{R}^m \to \mathbb{R}$
- given a [[function]] $f: \mathbb{R}^m \to \mathbb{R}$ the following is a [[quadratic aproximation]] (or quadratic model) of $f$ of point $x_0$

$$
q_{x_0}(d) = f(x_0) + \nabla f(x_0)^\top d + \frac{1}{2} \nabla  d^\top f(x_0) d
$$

- this is eqivalent to a [[taylor series#second taylor apploximation $f: mathbb{R} m to mathbb{R}$|second degree taylor apploximation]]


### lagrangian of a CNLP
- methode for seaching for stanary points of an [[constraint optimization problem]] by tansforming it in an unconstrain optimization problem → searching for [[kkt conditions|kkt points]]
- the [[lagrangian of a CNLP]] is defined as follows:
$$
\mathcal{L}\left(x, \lambda, \mu\right) = f(x) - \lambda^\top  g(x) - \mu^\top  h(x)
$$

- to find [[kkt conditions|kkt points]] we solve the following system of equations:

$$
\begin{split}
\nabla_x \mathcal{L}\left(x, \lambda, \mu\right)&=f(x) - \lambda^\top  \nabla g(x) - \mu^\top  \nabla h(x)= 0 \\
\nabla_\lambda \mathcal{L}\left(x, \lambda, \mu\right)&= g(x)= 0 \\
\nabla_\mu \mathcal{L}\left(x, \lambda, \mu\right)&= h(x) \geq 0 \\
\end{split}
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
<!--ID: 1721813631691-->
END