### root finding problem
- given [[function]] $f(x): \mathbb{R}^m \to \mathbb{R}^n$ and the equation system $f(x) = b$ and the following non-linear equation system

$$
F(x) = f(x) - b =0
$$

### solving the root finding problem with the newton methode
- in this special case the [[function]] is treated like the [[gradient]] thus the newton direction reads as follows
$$
d = F(x)^{-\top} F(x)
$$

$$
F(x)^\top = \left(\begin{matrix}
\frac{\partial F_1}{\partial x_1} & \frac{\partial F_1}{\partial x_2} \\
\frac{\partial F_2}{\partial x_1} & \frac{\partial F_2}{\partial x_2} \\
\end{matrix} \right)
$$
### examples
$$
\begin{split}
F(x)&=|x| \\
\nabla F(x)&=sign(x) \\
d
&=-\nabla F(x)^{-\top} F(x)\\
&=-sign(x) |x|\\
&=-x\\
x^{(1)}&=x^{(0)}+d = x^{(0)}-x^{(0)} = 0\\
\end{split}
$$



# -----------------
![[newton methode#newton method]]


# anki

START
Basic
solve the [[root finding problem]] $F(x)=0$ using the [[newton methode]]

$$
\begin{split}
F(x)&=|x| \\
\end{split}
$$
Back: 
### examples
$$
\begin{split}
F(x)&=|x| \\
\nabla F(x)&=sign(x) \\
d
&=-\nabla F(x)^{-\top} F(x)\\
&=-sign(x) |x|\\
&=-x\\
x^{(1)}&=x^{(0)}+d = x^{(0)}-x^{(0)} = 0\\
\end{split}
$$




### root finding problem
- given [[function]] $f(x): \mathbb{R}^m \to \mathbb{R}^n$ and the equation system $f(x) = b$ and the following non-linear equation system

$$
F(x) = f(x) - b =0
$$

### solving the root finding problem with the newton methode
- in this special case the [[function]] is treated like the [[gradient]] thus the newton direction reads as follows
$$
d = F(x)^{-\top} F(x)
$$

$$
F(x)^\top = \left(\begin{matrix}
\frac{\partial F_1}{\partial x_1} & \frac{\partial F_1}{\partial x_2} \\
\frac{\partial F_2}{\partial x_1} & \frac{\partial F_2}{\partial x_2} \\
\end{matrix} \right)
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
- but with the [[newton methode]] the [[quadratic aproximation]] is minimized thus the step size is already incuded in $d$ → $\alpha=1$

$$
x^{(k+1)} = x^{(k)} - \nabla^2  f\left(x^{(k)}\right)^{-1} \nabla f\left(x^{(k)}\right)
$$


Tags: mathematics linear_algebra
<!--ID: 1722870435353-->
END


START
Basic
[[root finding problem]]
- definition
- how to solve it using the [[newton methode]]
Back: 
### root finding problem
- given [[function]] $f(x): \mathbb{R}^m \to \mathbb{R}^n$ and the equation system $f(x) = b$ and the following non-linear equation system

$$
F(x) = f(x) - b =0
$$

### solving the root finding problem with the newton methode
- in this special case the [[function]] is treated like the [[gradient]] thus the newton direction reads as follows
$$
d = F(x)^{-\top} F(x)
$$

$$
F(x)^\top = \left(\begin{matrix}
\frac{\partial F_1}{\partial x_1} & \frac{\partial F_1}{\partial x_2} \\
\frac{\partial F_2}{\partial x_1} & \frac{\partial F_2}{\partial x_2} \\
\end{matrix} \right)
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
- but with the [[newton methode]] the [[quadratic aproximation]] is minimized thus the step size is already incuded in $d$ → $\alpha=1$

$$
x^{(k+1)} = x^{(k)} - \nabla^2  f\left(x^{(k)}\right)^{-1} \nabla f\left(x^{(k)}\right)
$$


Tags: mathematics linear_algebra
<!--ID: 1722870435357-->
END