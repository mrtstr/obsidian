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
### interpretation of the [[hessian]]
- let $f: \mathbb{R}^m \to \mathbb{R}$ be a [[function]] mapping from a [[banach space]] $(\mathbb{R}^m, ||\cdot||)$ to a [[banach space]] $(\mathbb{R}, ||\cdot||)$
- the following [[bounded linear map]] represented by the [[matrix]] $\nabla^2 f(x) \in \mathbb{R}^{m \times m}$ ansewers:
	- if we are in point $x \in \mathbb{R}^m$ and go in the direction $h \in \mathbb{R}^m$ how does the rate of change ([[gradient]]) in direction $k \in \mathbb{R}^m$ change
	- in other words: change of the rate of change in one direction when going in another direction
$$
\begin{split}
D^2f(x)[h][k] 
&= h^\top \nabla^2 f(x) k \\
\end{split}
$$
- note that because $\nabla^2 f(x) \in \mathbb{R}^{n \times n}$ is a [[symmetric matrix]] the directions $h$ and $k$ are interchangeably
- in optimization we are often interprestet in the curvature in one direction $d \in \mathbb{R}^m$ that is calculated as followins $d^\top \nabla^2 f(x) d$ 

$$
\begin{split}
D^2f(x)[h][k] 
&= d^\top \nabla^2 f(x) d \\
\end{split}
$$

# ----------------
![[jacobian#jacobian]]

![[higher order derivative#second order derivative]]

![[higher order derivative#interpretation second order derivative]]

![[derivative#general derivative]]

# anki

START
Basic
second order derivative of $f: \mathbb{R}^n \to \mathbb{R}$
- what kind of function is it in general $f: X \to Y$and for the case $f: \mathbb{R}^n \to \mathbb{R}$?
- how can the function be interpreted and be represented?
Back: 

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

### interpretation of the [[hessian]]
- let $f: \mathbb{R}^m \to \mathbb{R}$ be a [[function]] mapping from a [[banach space]] $(\mathbb{R}^m, ||\cdot||)$ to a [[banach space]] $(\mathbb{R}, ||\cdot||)$
- the following [[bounded linear map]] represented by the [[matrix]] $\nabla^2 f(x) \in \mathbb{R}^{m \times m}$ ansewers:
	- if we are in point $x \in \mathbb{R}^m$ and go in the direction $h \in \mathbb{R}^m$ how does the rate of change ([[gradient]]) in direction $k \in \mathbb{R}^m$ change
	- in other words: change of the rate of change in one direction when going in another direction
$$
\begin{split}
D^2f(x)[h][k] 
&= h^\top \nabla^2 f(x) k \\
\end{split}
$$
- note that because $\nabla^2 f(x) \in \mathbb{R}^{n \times n}$ is a [[symmetric matrix]] the directions $h$ and $k$ are interchangeably
- in optimization we are often interprestet in the curvature in one direction $d \in \mathbb{R}^m$ that is calculated as followins $d^\top \nabla^2 f(x) d$ 

$$
\begin{split}
D^2f(x)[h][k] 
&= d^\top \nabla^2 f(x) d \\
\end{split}
$$


### second order derivative
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- the second order derivative is calculated by deriving the [[derivative]] $Df(x)$ wich is a [[bounded linear map]] is derived again
$$
D^2f(x) = D(Df)(x)
$$
- while the [[derivative]] $Df(x)[h]: X \to Y$ is a [[function]] that mappes $X$ to the space of [[bounded linear map]] from $X$ to $Y$ the second order derivative is mapping $X$ to a [[bounded linear map]] that maps $X$ to a [[bounded linear map]] from $X$ to $Y$ 

$$
D^2f(x)[h][k]: X \to L\left(X, L(X, Y)\right)
$$
- because of the [[linear map|linearity]] we can transform $L(X, L(X, Y))$ to a [[bounded linear map]] from $X \times X$ to $Y$
$$
D^2f(x)[h, k]: X \to L\left(X \times X, Y\right)
$$
### interpretation second order derivative
- [[derivative]] is a [[linear map|linear]] approximation of a [[function]] $f: X \to Y$ in a point $x_0$ and discribes the rate of change regarding a direction $h$
- the second order [[derivative]] describes the **rate of change of the rate of change** → how much the **rate of change** when going in the direction $h$ will change when going in direction $k$

![[second_der 2.png]]

- the plotted [[function]] $f: \mathbb{R}^2 \to \mathbb{R}$ given a direction $h$ (red line) 
----------------------------------------------
### general derivative
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- the [[derivative]] operator $Df: X \to L(X,Y)$ is a [[function]] that maps elements of $X$ to a [[bounded linear map]] $Df(x)[h]: X \to Y$
- the [[bounded linear map]] $Df(x)[h]: X \to Y$ is the [[derivative]] of $f$ in point $x \in X$ and can be interpreted as a linear approximation of $f$ in point $x$
- in the case of $f: \mathbb{R}^{m} \to \mathbb{R}^{n}$ the [[derivative]] $Df(x)[h] = Ah$ can be expressed as a [[matrix]] $A \in \mathbb{R}^{n \times m}$
$$
\lim_{||h||_X \to 0} \frac{||f(x+h) - f(x) - Df(x)[h]||_Y}{||h||_X} = 0
$$

- this eqivalent definition is often easier to work with:
$$
f(x + h) = f(x) + Df(x)[h] + \varphi(h) \quad \text{with} \quad \lim_{h \to 0} \frac{||\varphi(h)||_Y}{||h||_X} = 0
$$


#### [[derivative]] as a [[linear map|linear]] approximation
- given a [[function]] $f: X \to Y$ the [[derivative]]  $Df(x)[h]: X \to Y$ is a [[linear map|linear]] approximation of $f$ in the point $x \in X$ relative to the origin
- since the [[derivative]] $Df(x)[h]: X \to Y$ is an approvimation relative to the origin the following would be a [[linear map|linear]] approximation of $f$ 
$$
\widehat{f_{x}}(h) = f(x) + Df(x)[h]
$$
- for example the [[function]] $f: \mathbb{R}^2 \to \mathbb{R}$ can be expressed in a $\mathbb{R}^3$ with each point in the plain $x \in \mathbb{R}^2$ is mapped to a $y \in \mathbb{R}$
- thus the [[derivative]] $Df(x)[h]: \mathbb{R}^2 \to \mathbb{R} = Ah$ with $A \in \mathbb{R}^{1 \times 2}$ would be a plain in the $\mathbb{R}^3$



Tags: mathematics statistics
<!--ID: 1720946541772-->
END


START
Basic
given a [[function]] $f: \mathbb{R}^n \to \mathbb{R}$
- definition of $\nabla^2 f(x)$
- what does the following function answer?
- what does the following function for $h=k=d$?

$$
\begin{split}
D^2f(x)[h][k] 
&= h^\top \nabla^2 f(x) k \\
\end{split}
$$

Back: 

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

### interpretation of the [[hessian]]
- let $f: \mathbb{R}^m \to \mathbb{R}$ be a [[function]] mapping from a [[banach space]] $(\mathbb{R}^m, ||\cdot||)$ to a [[banach space]] $(\mathbb{R}, ||\cdot||)$
- the following [[bounded linear map]] represented by the [[matrix]] $\nabla^2 f(x) \in \mathbb{R}^{m \times m}$ ansewers:
	- if we are in point $x \in \mathbb{R}^m$ and go in the direction $h \in \mathbb{R}^m$ how does the rate of change ([[gradient]]) in direction $k \in \mathbb{R}^m$ change
	- in other words: change of the rate of change in one direction when going in another direction

$$
\begin{split}
D^2f(x)[h][k] 
&= h^\top \nabla^2 f(x) k \\
\end{split}
$$

- note that because $\nabla^2 f(x) \in \mathbb{R}^{n \times n}$ is a [[symmetric matrix]] the directions $h$ and $k$ are interchangeably
- in optimization we are often interprestet in the curvature in one direction $d \in \mathbb{R}^m$ that is calculated as followins $d^\top \nabla^2 f(x) d$ 

----------------------------------------------

### second order derivative
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- the second order derivative is calculated by deriving the [[derivative]] $Df(x)$ wich is a [[bounded linear map]] is derived again
$$
D^2f(x) = D(Df)(x)
$$
- while the [[derivative]] $Df(x)[h]: X \to Y$ is a [[function]] that mappes $X$ to the space of [[bounded linear map]] from $X$ to $Y$ the second order derivative is mapping $X$ to a [[bounded linear map]] that maps $X$ to a [[bounded linear map]] from $X$ to $Y$ 

$$
D^2f(x)[h][k]: X \to L\left(X, L(X, Y)\right)
$$
- because of the [[linear map|linearity]] we can transform $L(X, L(X, Y))$ to a [[bounded linear map]] from $X \times X$ to $Y$
$$
D^2f(x)[h, k]: X \to L\left(X \times X, Y\right)
$$
### interpretation second order derivative
- [[derivative]] is a [[linear map|linear]] approximation of a [[function]] $f: X \to Y$ in a point $x_0$ and discribes the rate of change regarding a direction $h$
- the second order [[derivative]] describes the **rate of change of the rate of change** → how much the **rate of change** when going in the direction $h$ will change when going in direction $k$

![[second_der 2.png]]

- the plotted [[function]] $f: \mathbb{R}^2 \to \mathbb{R}$ given a direction $h$ (red line) 

### general derivative
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- the [[derivative]] operator $Df: X \to L(X,Y)$ is a [[function]] that maps elements of $X$ to a [[bounded linear map]] $Df(x)[h]: X \to Y$
- the [[bounded linear map]] $Df(x)[h]: X \to Y$ is the [[derivative]] of $f$ in point $x \in X$ and can be interpreted as a linear approximation of $f$ in point $x$
- in the case of $f: \mathbb{R}^{m} \to \mathbb{R}^{n}$ the [[derivative]] $Df(x)[h] = Ah$ can be expressed as a [[matrix]] $A \in \mathbb{R}^{n \times m}$
$$
\lim_{||h||_X \to 0} \frac{||f(x+h) - f(x) - Df(x)[h]||_Y}{||h||_X} = 0
$$

- this eqivalent definition is often easier to work with:
$$
f(x + h) = f(x) + Df(x)[h] + \varphi(h) \quad \text{with} \quad \lim_{h \to 0} \frac{||\varphi(h)||_Y}{||h||_X} = 0
$$


#### [[derivative]] as a [[linear map|linear]] approximation
- given a [[function]] $f: X \to Y$ the [[derivative]]  $Df(x)[h]: X \to Y$ is a [[linear map|linear]] approximation of $f$ in the point $x \in X$ relative to the origin
- since the [[derivative]] $Df(x)[h]: X \to Y$ is an approvimation relative to the origin the following would be a [[linear map|linear]] approximation of $f$ 
$$
\widehat{f_{x}}(h) = f(x) + Df(x)[h]
$$
- for example the [[function]] $f: \mathbb{R}^2 \to \mathbb{R}$ can be expressed in a $\mathbb{R}^3$ with each point in the plain $x \in \mathbb{R}^2$ is mapped to a $y \in \mathbb{R}$
- thus the [[derivative]] $Df(x)[h]: \mathbb{R}^2 \to \mathbb{R} = Ah$ with $A \in \mathbb{R}^{1 \times 2}$ would be a plain in the $\mathbb{R}^3$



Tags: mathematics statistics
<!--ID: 1720946541776-->
END