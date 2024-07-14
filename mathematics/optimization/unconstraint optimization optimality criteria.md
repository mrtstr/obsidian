### unconstraint optimization optimality criteria
- the following criteria are for [[local minimum|local minima]] because finding global [[minimum]] for a general function is NP hard

### necessary optimality condition of first order
- let $x^*$ be a [[local minimum]] then the [[gradient]] has to be zero
$$
\nabla f(x^*) = 0
$$
- example for a non [[local minimum]] that satisfies the condition: $f(x) = x$ with $x^* =0$ 
- a point that satisfies $\nabla f(x^*) = 0$ is called a stationary point


### necessary optimality condition of second order
- let $x^*$ be a [[local minimum]] then the [[gradient]] has to be zero and its [[hessian]] has to be a [[definiteness of matrices#positive semi definite matrix|positive semi definite matrix]]

$$
\nabla f(x^*) = 0 \land \nabla^2 f(x^*) \text{ is positive semidefinite}
$$
- example for a non [[local minimum]] that satisfies the condition: $f(x) = x^3$ with $x^* =0$ 


### sufficient optimality condition of second order
- let $x^*$ be a point with [[gradient]] that is zero and its [[hessian]] has to be a [[definiteness of matrices#positive semi definite matrix|positive definite matrix]] then it has to be a [[local minimum]]

$$
\nabla f(x^*) = 0 \land \nabla^2 f(x^*) \text{ is positive definite}
$$

- example for a [[local minimum]] that does not satisfyhe condition: $f(x) = x^4$ with $x^* =0$ 
# ----------------------
![[gradient#gradient]]

![[hessian#hessian of $f: mathbb{R} n to mathbb{R}$]]

![[definiteness of matrices#positive semi definite matrix]]

![[definiteness of matrices#positive definite matrix]]

![[local minimum#local minimum]]

# anki


START
Basic
what can be said about the functions $f(x) = x^4$ and $f(x) = x^3$ and $x^* = 0$ regarding necessary optimality conditions?


Back: 
- $f(x) = x^3$ and $x^* = 0$ satisfies the nesseary first and second order optimality conditions 
$$
\begin{split}
\left.\frac{dx^3}{dx}\right|_{x=0}&=0 \\
\left.\frac{d^2x^3}{dxdx}\right|_{x=0}&=0 \leq 0 \\
\end{split}
$$
- we would need higher order [[derivative|derivatives]] to prove that it's not a minimum

- $f(x) = x^4$ and $x^* = 0$ is a [[local minimum]] and thus satisfies the nesseary first and second order optimality conditions

$$
\begin{split}
\left.\frac{dx^4}{dx}\right|_{x=0}&=0 \\
\left.\frac{d^2x^4}{dxdx}\right|_{x=0}&=0 \leq 0 \\
\end{split}
$$

- but it does not satisfy the sufficient optimality condition of second order because the second [[derivative]] ([[hessian]]) is zero and thus not [[definiteness of matrices|positive definite]]
→ we cannot prove it's a [[local minimum]]
___________________________

### sufficient optimality condition of second order
- let $x^*$ be a point with [[gradient]] that is zero and its [[hessian]] has to be a [[definiteness of matrices#positive semi definite matrix|positive definite matrix]] then it has to be a [[local minimum]]

$$
\nabla f(x^*) = 0 \land \nabla^2 f(x^*) \text{ is positive definite}
$$

- example for a [[local minimum]] that does not satisfyhe condition: $f(x) = x^4$ with $x^* =0$ 

### necessary optimality condition of first order
- let $x^*$ be a [[local minimum]] then the [[gradient]] has to be zero
$$
\nabla f(x^*) = 0
$$
- example for a non [[local minimum]] that satisfies the condition: $f(x) = x$ with $x^* =0$ 
- a point that satisfies $\nabla f(x^*) = 0$ is called a stationary point


### necessary optimality condition of second order
- let $x^*$ be a [[local minimum]] then the [[gradient]] has to be zero and its [[hessian]] has to be a [[definiteness of matrices#positive semi definite matrix|positive semi definite matrix]]

$$
\nabla f(x^*) = 0 \land \nabla^2 f(x^*) \text{ is positive semidefinite}
$$
- example for a non [[local minimum]] that satisfies the condition: $f(x) = x^3$ with $x^* =0$ 

### definiteness of matrices
#### positive definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[positive definite]] if the following is true
$$
\forall x \in \mathbb{R}^n \setminus{0}: x^\top A x >0
$$

- in other words $f(x) = x^\top A x$ is a [[positive definite]] [[function]]


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

#### gradient
- let $f: \mathbb{R}^m \to \mathbb{R}$ be a [[function]] then the [[gradient]] is a [[linear map]] $\nabla f(x): \mathbb{R}^m \to \mathbb{R}$ and is defined as follows

$$
\nabla f(x) = 
\left(
\begin{matrix}
\frac{\partial f}{\partial x_1} \\
... \\
\frac{\partial f}{\partial x_n} \\
\end{matrix}

\right)
\in \mathbb{R}^{n \times m}
$$
- the [[gradient]] gives the direction and the rate of fastest increase of $f$ because every of its elements $\frac{\partial f}{\partial x_i}$ gives the rate of change in the direction of the coordinate $x_i$ 


### local minimum
- given a [[function]] $f: X \to Y$
- the point $x^* \in X$ is called a [[local minimum]] if the following is true

$$
\forall y \in B_\epsilon(x^*) : f(x^*) \leq f(y)
$$

- with $\epsilon \to \infty$ the local minumum $x^*$ becomes a global minimum 
- if $\leq$ is replaced by $<$ the minimum $x^*$ becomes a strick minimum
- for a [[convex function]] $f(x)$ every [[local minimum]] is a gloabl [[minimum]]  
### ball
- given a [[set]] $A$ with a [[metric]] $d(\cdot,\cdot)$
- for each $x \in A$ and $\epsilon > 0$ the $\epsilon$-ball ($\epsilon$-nighbouhood) is defined as follows

$$
B_\epsilon(x) = \{y \in A: d(x, y) < \epsilon\}
$$
Tags: mathematics
<!--ID: 1720971143038-->
END

START
Basic
necessary optimality condition of first order
- definition
- example for a case where the condition is satisfies on a non [[local minimum]]
- how are point that satisfy this condition called?

necessary optimality condition of second order
- example for a case where the condition is satisfies on a non [[local minimum]]

sufficient optimality condition of second order
- example for [[local minimum]] where the condition is not satisfied

Back: 
### necessary optimality condition of first order
- let $x^*$ be a [[local minimum]] then the [[gradient]] has to be zero
$$
\nabla f(x^*) = 0
$$
- example for a non [[local minimum]] that satisfies the condition: $f(x) = x$ with $x^* =0$ 
- a point that satisfies $\nabla f(x^*) = 0$ is called a stationary point


### necessary optimality condition of second order
- let $x^*$ be a [[local minimum]] then the [[gradient]] has to be zero and its [[hessian]] has to be a [[definiteness of matrices#positive semi definite matrix|positive semi definite matrix]]

$$
\nabla f(x^*) = 0 \land \nabla^2 f(x^*) \text{ is positive semidefinite}
$$
- example for a non [[local minimum]] that satisfies the condition: $f(x) = x^3$ with $x^* =0$ 

### sufficient optimality condition of second order
- let $x^*$ be a point with [[gradient]] that is zero and its [[hessian]] has to be a [[definiteness of matrices#positive semi definite matrix|positive definite matrix]] then it has to be a [[local minimum]]

$$
\nabla f(x^*) = 0 \land \nabla^2 f(x^*) \text{ is positive definite}
$$

- example for a [[local minimum]] that does not satisfyhe condition: $f(x) = x^4$ with $x^* =0$ 

___________________________

### definiteness of matrices
#### positive definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[positive definite]] if the following is true
$$
\forall x \in \mathbb{R}^n \setminus{0}: x^\top A x >0
$$

- in other words $f(x) = x^\top A x$ is a [[positive definite]] [[function]]


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

#### gradient
- let $f: \mathbb{R}^m \to \mathbb{R}$ be a [[function]] then the [[gradient]] is a [[linear map]] $\nabla f(x): \mathbb{R}^m \to \mathbb{R}$ and is defined as follows

$$
\nabla f(x) = 
\left(
\begin{matrix}
\frac{\partial f}{\partial x_1} \\
... \\
\frac{\partial f}{\partial x_n} \\
\end{matrix}

\right)
\in \mathbb{R}^{n \times m}
$$
- the [[gradient]] gives the direction and the rate of fastest increase of $f$ because every of its elements $\frac{\partial f}{\partial x_i}$ gives the rate of change in the direction of the coordinate $x_i$ 


### local minimum
- given a [[function]] $f: X \to Y$
- the point $x^* \in X$ is called a [[local minimum]] if the following is true

$$
\forall y \in B_\epsilon(x^*) : f(x^*) \leq f(y)
$$

- with $\epsilon \to \infty$ the local minumum $x^*$ becomes a global minimum 
- if $\leq$ is replaced by $<$ the minimum $x^*$ becomes a strick minimum
- for a [[convex function]] $f(x)$ every [[local minimum]] is a gloabl [[minimum]]  
### ball
- given a [[set]] $A$ with a [[metric]] $d(\cdot,\cdot)$
- for each $x \in A$ and $\epsilon > 0$ the $\epsilon$-ball ($\epsilon$-nighbouhood) is defined as follows

$$
B_\epsilon(x) = \{y \in A: d(x, y) < \epsilon\}
$$
Tags: mathematics
<!--ID: 1720971143044-->
END