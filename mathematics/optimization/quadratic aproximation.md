### quadratic aproximationof $f: \mathbb{R}^m \to \mathbb{R}$
- given a [[function]] $f: \mathbb{R}^m \to \mathbb{R}$ the following is a [[quadratic aproximation]] (or quadratic model) of $f$ of point $x_0$

$$
q_{x_0}(d) = f(x_0) + \nabla f(x_0)^\top d + \frac{1}{2} \nabla  d^\top f(x_0) d
$$

- this is eqivalent to a [[taylor series#second taylor apploximation $f: mathbb{R} m to mathbb{R}$|second degree taylor apploximation]]

# -------------------

![[taylor series#second degree taylor apploximation $f: mathbb{R} m to mathbb{R}$]]

![[hessian#hessian of $f: mathbb{R} n to mathbb{R}$]]

# anki



START
Basic
quadratic aproximation of a [[function]] $f: \mathbb{R}^m \to \mathbb{R}$
Back: 

### quadratic aproximationof $f: \mathbb{R}^m \to \mathbb{R}$
- given a [[function]] $f: \mathbb{R}^m \to \mathbb{R}$ the following is a [[quadratic aproximation]] (or quadratic model) of $f$ of point $x_0$

$$
q_{x_0}(d) = f(x_0) + \nabla f(x_0)^\top d + \frac{1}{2} \nabla  d^\top f(x_0) d
$$

- this is eqivalent to a [[taylor series#second taylor apploximation $f: mathbb{R} m to mathbb{R}$|second degree taylor apploximation]]
____________________


### second taylor apploximation $f: \mathbb{R}^m \to \mathbb{R}$

$$
\begin{split}
\widehat{f_k}(x, x_0) 
&= \sum_{n=0}^k 
f(x_0) + \nabla f(x_0)^\top x + \frac{1}{2} \nabla  x^\top f(x_0) x + o(||x||^2)
\end{split}

$$

### hessian of $f: \mathbb{R}^n \to \mathbb{R}$ 
- let $f: \mathbb{R}^m \to \mathbb{R}$ be a [[function]] mapping from a [[banach space]] $(\mathbb{R}^m, ||\cdot||)$ to a [[banach space]] $(\mathbb{R}, ||\cdot||)$
- second order [[derivative]] of a [[function]] $f: X \to Y$ and represents a [[bounded linear map]] $D^2f(x)[h][k]: X \to L(X, L(X, Y)) = L(X \times X, Y)$
- for a [[function]] $f: \mathbb{R}^m \to \mathbb{R}$ the [[higher order derivative|second order derivative]] maps the $\mathbb{R}^m$ to a [[bounded linear map]] $L(\mathbb{R}^m \times \mathbb{R}^m, \mathbb{R})$ that can is representaed by [[matrix]] $\nabla^2 f(x) \in \mathbb{R}^{m \times m}$ 
$$
\begin{split}
D^2f(x)[h][k] 
&= h^\top \nabla^2 f(x) k \\
\end{split}
$$

- the [[matrix]] $\nabla^2 f(x) \in \mathbb{R}^{n \times n}$ is called the [[hessian]] and is deinfed as follows

$$
\nabla^2 f(x) =
\left(
\begin{matrix}
\frac{\partial^2 f}{\partial x_1\partial x_1} & ... & \frac{\partial^2 f}{\partial x_1\partial x_m} \\
 & ... &  \\
\frac{\partial^2 f}{\partial x_m\partial x_1} &...& \frac{\partial^2 f}{\partial x_m\partial x_m} \\
\end{matrix}
\right)
\in \mathbb{R}^{m \times m}
$$

Tags: mathematics
<!--ID: 1720949577262-->
END