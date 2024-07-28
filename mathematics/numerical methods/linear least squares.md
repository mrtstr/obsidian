### linear least squares
- given an overdeterminded [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- since there is no exact soltion the approach is to find the best fitting solution that minimizes the squared deviation
$$
x = \mathrm{argmin} ||Ax - b||_2
$$

### normal equation
- by setting the [[derivative]] of the objective function to zero we get the **normal equation**$A^\top Ax = A^\top b$
- every solution that minimizes the rquared residuals will satisfy $A^\top Ax = A^\top b$
$$
\begin{split}
f(x) &= \frac{1}{2}||Ax - b||_2^2 \\
Df(x)[h] &= A^\top\left(Ax -b\right) = 0 \\
\Rightarrow & A^\top Ax = A^\top b \\
\end{split}
$$

# --------------------------

![[derivative#$F(x): mathbb{R} {m} to mathbb{R} = frac{1}{2} Ax -b _2 2$]]


# anki

START
Basic
[[linear least squares]]
- defintion
- property of the solution
 
Back: 
### linear least squares
- given an overdeterminded [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- since there is no exact soltion the approach is to find the best fitting solution that minimizes the squared deviation
$$
x = \mathrm{argmin} ||Ax - b||_2
$$

### normal equation
- by setting the [[derivative]] of the objective function to zero we get the **normal equation**$A^\top Ax = A^\top b$
- every solution that minimizes the rquared residuals will satisfy $A^\top Ax = A^\top b$
$$
\begin{split}
f(x) &= \frac{1}{2}||Ax - b||_2^2 \\
Df(x)[h] &= A^\top\left(Ax -b\right) = 0 \\
\Rightarrow & A^\top Ax = A^\top b \\
\end{split}
$$

------------------------
### linear equation system
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$ and tvo [[vector]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$
$$
\begin{split}
Ax&=b  \\
A_{(*,1)}x_1 + ...+ A_{(*,m)}x_m&=b  \\
\end{split}
$$
- $n$ = number of equation
- $m$ = number of unknown valiables


#### $F(x): \mathbb{R}^{m} \to \mathbb{R} = \frac{1}{2}||Ax -b||_2^2$
- the [[derivative]] $DF(x)[h]: \mathbb{R}^{m} \to L( \mathbb{R}^{m},  \mathbb{R})$ has to be [[bounded linear map]] mapping from the $\mathbb{R}^{m}$ to $\mathbb{R}$ with $h \in \mathbb{R}^{m}$
- from the definition we know the following:
$$
F(x + h) = F(x) + DF(x)[h] + \varphi(h) \quad \text{with} \quad \lim_{h \to 0} \frac{||\varphi(h)||}{||h||} = 0 
$$


$$
\begin{split}
F (x + h) 
&= \frac{1}{2}||A(x+h) -b||_2^2 \\
&= \frac{1}{2}\langle (Ax -b) + Ah, (Ax -b) + Ah\rangle \\
&= \frac{1}{2}\langle Ax -b, Ax -b\rangle + \frac{1}{2}\langle Ah, Ah\rangle + \langle Ax -b, Ah\rangle \\
&= \underbrace{\frac{1}{2}||Ax-b||_2^2}_{f(X)} + \underbrace{\frac{1}{2}||Ah||_2^2}_{\varphi(H)} +  \underbrace{\langle Ax -b, Ah \rangle}_{Df(x)[h]}  \\
\end{split}
$$

- show that $\varphi(h)$ is converging fast enough

$$
\begin{split}
\frac{\varphi(h)}{||h||} 
&= \frac{1}{2} \frac{||Ah||^2}{||h||} \\
&= \frac{1}{2} ||h|| \frac{||Ah||^2}{||h||^2} \\
&= \frac{1}{2} ||h|| \left(\frac{||Ah||}{||h||}\right)^2 \\
&\leq \frac{1}{2} ||h|| \left(\sup_{||y|| \neq 0}\frac{||Ay||}{||y||}\right)^2 \\
&= \frac{1}{2} ||h|| \cdot ||A||^2 \xrightarrow{h \to 0} 0 \\
\end{split}
$$


$$
\begin{split}
Df(x)[h] 
&= \langle Ax -b, Ah \rangle \\
&= \left(Ax -b\right)^\top Ah \\
Df(x)
&= \left(Ax -b\right)^\top A \\
\nabla f (x)
&= \left(\left(Ax -b\right)^\top A\right)^\top \\
&= A^\top\left(Ax -b\right)  \\
\end{split}
$$

Tags: mathematics
<!--ID: 1722180274131-->
END