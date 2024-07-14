### convex function
- a [[function]] $f: X \to \mathbb{R}$ is [[convex function|convex]] if the following eqivalent statements are true

TODO add proofs

1) the [[hessian]] $\nabla^2 f(x)$ is [[definiteness of matrices|positive semi definite]] → only prositive curveture
$$
\begin{split}
\forall x \in X: \forall d \in X: d^\top \nabla^2 f(x)d \geq 0 
\end{split}
$$


2) the direct like connecting two points $\left(x, f(x)\right)$ and $\left(y, f(y)\right)$ is an upper bound for all values in $\left\{f(t): t \in [x, y]\right\}$ 

$$
\begin{split}
\forall x, y, \lambda \in [0,1] \in X: f\left(\lambda x + (1-\lambda) y \right) \leq \lambda f(x) + (1-\lambda) f(y)
\end{split}
$$

![[convex_function.png]]



3) the steepnes of the slope in every point $\nabla f(x)$ is bound by the scope of $\frac{f(y) - f(x)}{y - x}$
$$
\begin{split}
\forall x, y \in X: \nabla f(x)^\top (y - x) \leq f(y) - f(x)
\end{split}
$$

### check convexity
- calculate the [[hessian]] $\nabla f(x)$
- check if the [[hessian]] is [[definiteness of matrices|positive semi definitie]] for all $x$ 
- this can be done by using the main minor criterium:the [[determinant]] of all main minors need to be greater or equal than zero 
# ------------------
![[hessian#hessian of $f: mathbb{R} n to mathbb{R}$]]


![[definiteness of matrices#positive semi definite matrix]]

![[definiteness criteria for matrices#definiteness criteria for matrices]]

# anki


START
Basic
- how to check of a function is [[convex function|convex]]?

Back: 
### check convexity
- calculate the [[hessian]] $\nabla f(x)$
- check if the [[hessian]] is [[definiteness of matrices|positive semi definitie]] for all $x$ 
- this can be done by using the main minor criterium:the [[determinant]] of all main minors need to be greater or equal than zero 

### definiteness criteria for matrices
- given a sqare [[matrix]] $A \in \mathbb{R}^{m \times m}$ and let $A_1, ..., A_m$ be the main [[minor|minors]] auf $A$
$$
\begin{split}
A_1 &= (a_{11}) \\
A_2 &= \left(
\begin{matrix}
a_{11} & a_{12} \\
a_{21} & a_{22} \\
\end{matrix}
\right) \\
A_3 &= ...
\end{split}
$$
- $A$ is [[definiteness of matrices|positive definite]] exactly when $\forall k \in [m]: \det\left(A_k\right) > 0$
- $A$ is [[definiteness of matrices|positive semidefinite]] exactly when $\forall k \in [m]: \det\left(A_k\right) \geq 0$
- $A$ is [[definiteness of matrices|negative definite]] exactly when $\forall k \in [m]: \mathrm{sign}\left(\det\left(A_m\right)\right) = (-1)^k$
- $A$ is [[definiteness of matrices|negative semidefinite]] exactly when $\forall k \in [m]: \mathrm{sign}\left(\det\left(A_m\right)\right) \neq (-1)^{k+1}$
- $A$ is [[definiteness of matrices|indefinite]] if none of the other conditions is true

#### positive semi definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[definiteness of matrices|positive semi definite]] if the following is true
$$
\forall x \in \mathbb{R}^n : x^\top A x \geq0
$$
- in other words $f(x) = x^\top A x$ is a [[positive definite|positive semi definite]] [[function]]



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

### convex function
- a [[function]] $f: X \to \mathbb{R}$ is [[convex function|convex]] if the following eqivalent statements are true

1) the [[hessian]] $\nabla^2 f(x)$ is [[positive definite|positive semi definite]] → only prositive curveture
$$
\begin{split}
\forall x \in X: \forall d \in X: d^\top \nabla^2 f(x)d \geq 0 
\end{split}
$$


2) the direct like connecting two points $\left(x, f(x)\right)$ and $\left(y, f(y)\right)$ is an upper bound for all values in $\left\{f(t): t \in [x, y]\right\}$ 

$$
\begin{split}
\forall x, y, \lambda \in [0,1] \in X: f\left(\lambda x + (1-\lambda) y \right) \leq \lambda f(x) + (1-\lambda) f(y)
\end{split}
$$


3) the steepnes of the slope in every point $\nabla f(x)$ is bound by the scope of $\frac{f(y) - f(x)}{y - x}$
$$
\begin{split}
\forall x, y \in X: \nabla f(x)^\top (y - x) \leq f(y) - f(x)
\end{split}
$$

Tags: mathematics
<!--ID: 1720964044654-->
END

START
Basic
is $f(x_1, x_2) = 2 x_1^2 - x_2^2$ convex?

Back: 
- no because the [[hessian]] is the following
$$
\nabla^2 f = 
\left(\begin{matrix} 
4 & 0\\
0 & -2\\
\end{matrix}\right)
$$
- the [[determinant]] of the main minors is not greater or equal than zero
$$
\det
\left(\begin{matrix} 
4  \\
\end{matrix}\right) > 0
$$
$$
\det
\left(\begin{matrix} 
4 & 0\\
0 & -2\\
\end{matrix}\right) = -8
$$

### check convexity
- calculate the [[hessian]] $\nabla f(x)$
- check if the [[hessian]] is [[definiteness of matrices|positive semi definitie]] for all $x$ 
- this can be done by using the main minor criterium:the [[determinant]] of all main minors need to be greater or equal than zero 

### definiteness criteria for matrices
- given a sqare [[matrix]] $A \in \mathbb{R}^{m \times m}$ and let $A_1, ..., A_m$ be the main [[minor|minors]] auf $A$
$$
\begin{split}
A_1 &= (a_{11}) \\
A_2 &= \left(
\begin{matrix}
a_{11} & a_{12} \\
a_{21} & a_{22} \\
\end{matrix}
\right) \\
A_3 &= ...
\end{split}
$$
- $A$ is [[definiteness of matrices|positive definite]] exactly when $\forall k \in [m]: \det\left(A_k\right) > 0$
- $A$ is [[definiteness of matrices|positive semidefinite]] exactly when $\forall k \in [m]: \det\left(A_k\right) \geq 0$
- $A$ is [[definiteness of matrices|negative definite]] exactly when $\forall k \in [m]: \mathrm{sign}\left(\det\left(A_m\right)\right) = (-1)^k$
- $A$ is [[definiteness of matrices|negative semidefinite]] exactly when $\forall k \in [m]: \mathrm{sign}\left(\det\left(A_m\right)\right) \neq (-1)^{k+1}$
- $A$ is [[definiteness of matrices|indefinite]] if none of the other conditions is true

#### positive semi definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[definiteness of matrices|positive semi definite]] if the following is true
$$
\forall x \in \mathbb{R}^n : x^\top A x \geq0
$$
- in other words $f(x) = x^\top A x$ is a [[positive definite|positive semi definite]] [[function]]



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

### convex function
- a [[function]] $f: X \to \mathbb{R}$ is [[convex function|convex]] if the following eqivalent statements are true

1) the [[hessian]] $\nabla^2 f(x)$ is [[positive definite|positive semi definite]] → only prositive curveture
$$
\begin{split}
\forall x \in X: \forall d \in X: d^\top \nabla^2 f(x)d \geq 0 
\end{split}
$$


2) the direct like connecting two points $\left(x, f(x)\right)$ and $\left(y, f(y)\right)$ is an upper bound for all values in $\left\{f(t): t \in [x, y]\right\}$ 

$$
\begin{split}
\forall x, y, \lambda \in [0,1] \in X: f\left(\lambda x + (1-\lambda) y \right) \leq \lambda f(x) + (1-\lambda) f(y)
\end{split}
$$


3) the steepnes of the slope in every point $\nabla f(x)$ is bound by the scope of $\frac{f(y) - f(x)}{y - x}$
$$
\begin{split}
\forall x, y \in X: \nabla f(x)^\top (y - x) \leq f(y) - f(x)
\end{split}
$$

Tags: mathematics
<!--ID: 1720964044659-->
END

START
Basic
- 3 eqivalent conditions for a [[convex function]]
Back: 
### convex function
- a [[function]] $f: X \to \mathbb{R}$ is [[convex function|convex]] if the following eqivalent statements are true

1) the [[hessian]] $\nabla^2 f(x)$ is [[positive definite|positive semi definite]] → only prositive curveture
$$
\begin{split}
\forall x \in X: \forall d \in X: d^\top \nabla^2 f(x)d \geq 0 
\end{split}
$$


2) the direct like connecting two points $\left(x, f(x)\right)$ and $\left(y, f(y)\right)$ is an upper bound for all values in $\left\{f(t): t \in [x, y]\right\}$ 

$$
\begin{split}
\forall x, y, \lambda \in [0,1] \in X: f\left(\lambda x + (1-\lambda) y \right) \leq \lambda f(x) + (1-\lambda) f(y)
\end{split}
$$

![[convex_function 1.png]]

3) the steepnes of the slope in every point $\nabla f(x)$ is bound by the scope of $\frac{f(y) - f(x)}{y - x}$
$$
\begin{split}
\forall x, y \in X: \nabla f(x)^\top (y - x) \leq f(y) - f(x)
\end{split}
$$

Tags: mathematics
<!--ID: 1720964044663-->
END