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

### existence of a solution
- given an overdeterminded [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- $\mathrm{argmin} ||Ax - b||_2$ always has a solution if $\mathrm{rank}(A)=n$

##### proof

$$
\begin{split}
A^\top Ax = A^\top b \\
\Rightarrow x = \left(A^\top A\right)^{-1} A^\top b \\
\end{split}
$$
- and if $\mathrm{rank}(A)=n$ then $A^\top A$ is positive definite and thus has a inverse


### algorithm: solving linear least squares with the normal equation
- solving the normal equation using the [[cholesky decomposition]] in $\mathcal{O}\left((n+m)n^2\right)$
$$
\begin{split}
A^\top Ax = A^\top b \\
\end{split}
$$
1) calculate the [[cholesky decomposition]]  $A^\top A =GG^\top$
2) calculate $A^\top b=y$
3) $G z=y$ 
4) $G^\top x=z$

![[cholesky decomposition#cholesky decomposition]]


![[linear equation system#solvig a linear equation system]]

### solving linear least squares with the [[mathematics/numerical methods/QR decomposition]]
# ---------------------------------

![[definiteness of matrices#definitness of $A top A$]]

# --------------------------

![[derivative#$F(x): mathbb{R} {m} to mathbb{R} = frac{1}{2} Ax -b _2 2$]]


# anki

START
Basic
[[linear least squares]]
- defintion
- existence of a solution
- property of the solution
 
Back: 
### linear least squares
- given an overdeterminded [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- since there is no exact soltion the approach is to find the best fitting solution that minimizes the squared deviation
$$
x = \mathrm{argmin} ||Ax - b||_2
$$
- here always exists a solution

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

### existence of a solution
- given an overdeterminded [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- $\mathrm{argmin} ||Ax - b||_2$ always has a solution if $\mathrm{rank}(A)=n$

##### proof

$$
\begin{split}
A^\top Ax = A^\top b \\
\Rightarrow x = \left(A^\top A\right)^{-1} A^\top b \\
\end{split}
$$
- and if $\mathrm{rank}(A)=n$ then $A^\top A$ is positive definite and thus has a inverse


------------------------

### definitness of $A^\top A$
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$
- $A^\top A$ is positive semi definit
$$
\begin{split}
x^\top A^\top Ax =  (Ax)^\top Ax = \langle Ax, Ax \rangle = ||Ax||^2 \geq 0
\end{split}
$$

- if $\mathrm{rank}(A) = n$  then $A^\top A$ is even positive definite

$$
\begin{split}
&x^\top A^\top Ax =  (Ax)^\top Ax = \langle Ax, Ax \rangle = ||Ax||^2 \geq 0 \\
&||Ax||^2 = 0 \Leftrightarrow Ax = 0 \\
&\mathrm{rank}(A) = n \Rightarrow A_{(*, 1)}, ..., A_{(*, n)} \text{ are linear independen} \\
\Rightarrow & Ax = 0 \Rightarrow x=0
\end{split}
$$

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


# anki

START
Basic
- given an overdeterminded [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$

$$
x = \mathrm{argmin} ||Ax - b||_2
$$

- when does the problem have a solution (with proof)

Back: 
### linear least squares
- given an overdeterminded [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- since there is no exact soltion the approach is to find the best fitting solution that minimizes the squared deviation
$$
x = \mathrm{argmin} ||Ax - b||_2
$$
- here always exists a solution

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

### existence of a solution
- given an overdeterminded [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- $\mathrm{argmin} ||Ax - b||_2$ always has a solution if $\mathrm{rank}(A)=n$

##### proof

$$
\begin{split}
A^\top Ax = A^\top b \\
\Rightarrow x = \left(A^\top A\right)^{-1} A^\top b \\
\end{split}
$$
- and if $\mathrm{rank}(A)=n$ then $A^\top A$ is positive definite and thus has a inverse


------------------------

### definitness of $A^\top A$
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$
- $A^\top A$ is positive semi definit
$$
\begin{split}
x^\top A^\top Ax =  (Ax)^\top Ax = \langle Ax, Ax \rangle = ||Ax||^2 \geq 0
\end{split}
$$

- if $\mathrm{rank}(A) = n$  then $A^\top A$ is even positive definite

$$
\begin{split}
&x^\top A^\top Ax =  (Ax)^\top Ax = \langle Ax, Ax \rangle = ||Ax||^2 \geq 0 \\
&||Ax||^2 = 0 \Leftrightarrow Ax = 0 \\
&\mathrm{rank}(A) = n \Rightarrow A_{(*, 1)}, ..., A_{(*, n)} \text{ are linear independen} \\
\Rightarrow & Ax = 0 \Rightarrow x=0
\end{split}
$$

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
<!--ID: 1722281289960-->
END

START
Basic
- given an overdeterminded [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$

$$
x = \mathrm{argmin} ||Ax - b||_2
$$

- how to solve [[linear least squares]] using the normal equation
- time complexity

Back: 

### algorithm: solving linear least squares with the normal equation
- solving the normal equation using the [[cholesky decomposition]] in $\mathcal{O}\left((n+m)n^2\right)$
$$
\begin{split}
A^\top Ax = A^\top b \\
\end{split}
$$
1) calculate the [[cholesky decomposition]]  $A^\top A =GG^\top$
2) calculate $A^\top b=y$
3) $G z=y$ 
4) $G^\top x=z$

### cholesky decomposition
Decompostion of a [[square matrix|square]] [[symmetric matrix|symmetric]] [[matrix]] $A$ in the [[matrix product]] of a lower [[triangular matrix]] $L$ and its [[transpose]].

$$
A = LL^T
$$



### solvig a linear equation system

- given the [[PLU decomposition]] (or [[cholesky decomposition]] of $A$ is a [[symmetric matrix]]) auf $A$ auch that $PA=LU$

$$
\begin{split}
P^{-1}LUx &= b \\
\Rightarrow LUx &= Pb \\
\Rightarrow Ly &= Pb \text{ with } y=Ux \\
\end{split}
$$
1) solve $Ly = Pb$ for $y$ using the triangular shape of $L$
2) solve $Ux=y$ for $x$ using the triangular shape of $U$



### linear least squares
- given an overdeterminded [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- since there is no exact soltion the approach is to find the best fitting solution that minimizes the squared deviation
$$
x = \mathrm{argmin} ||Ax - b||_2
$$
- here always exists a solution

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

### existence of a solution
- given an overdeterminded [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- $\mathrm{argmin} ||Ax - b||_2$ always has a solution if $\mathrm{rank}(A)=n$

##### proof

$$
\begin{split}
A^\top Ax = A^\top b \\
\Rightarrow x = \left(A^\top A\right)^{-1} A^\top b \\
\end{split}
$$
- and if $\mathrm{rank}(A)=n$ then $A^\top A$ is positive definite and thus has a inverse


------------------------

### definitness of $A^\top A$
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$
- $A^\top A$ is positive semi definit
$$
\begin{split}
x^\top A^\top Ax =  (Ax)^\top Ax = \langle Ax, Ax \rangle = ||Ax||^2 \geq 0
\end{split}
$$

- if $\mathrm{rank}(A) = n$  then $A^\top A$ is even positive definite

$$
\begin{split}
&x^\top A^\top Ax =  (Ax)^\top Ax = \langle Ax, Ax \rangle = ||Ax||^2 \geq 0 \\
&||Ax||^2 = 0 \Leftrightarrow Ax = 0 \\
&\mathrm{rank}(A) = n \Rightarrow A_{(*, 1)}, ..., A_{(*, n)} \text{ are linear independen} \\
\Rightarrow & Ax = 0 \Rightarrow x=0
\end{split}
$$

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
<!--ID: 1722281289966-->
END

