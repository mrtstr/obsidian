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

# anki

START
Basic
calculate the [[gradient]] of $f(x)=x^\top Ax$ and the [[hessian]]
Back: 

$\nabla f(x)=(A^\top + A)x$

$\nabla^2 f(x)=A^\top + A$

Tags: mathematics SS25
<!--ID: 1753031200148-->
END