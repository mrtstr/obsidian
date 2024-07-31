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
- $\mathrm{argmin} ||Ax - b||_2$ always has a solution if $\mathrm{rank}(A)=m$

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

### solving linear least squares with the [[QR decomposition]]
- given the normal equation of the [[linear least squares]] minimizing solution $A^\top Ax^*   = A^\top b$
- and the [[QR decomposition]] of $A \in \mathbb{R}^{n \times m}$ with an [[orthogonal matrix]] $Q_1 \in \mathbb{R}^{m \times m}$ and a [[triangular matrix]] $R \in \mathbb{R}^{m \times m}$ auch that $A=Q_1R_1$

$$
\begin{split}
A^\top Ax   &= A^\top b \\ 
(Q_1R_1)^\top Q_1R_1x &= (Q_1R_1)^\top\\ 
R_1^\top Q_1^\top Q_1R_1x &=  R_1^\top Q_1^\top b\\ 
R_1x  &= Q_1^\top b \\ 
\end{split}
$$

1) calculate the [[QR decomposition]] $A=Q_1R_1$
2) calculate $y = Q_1^\top b$
3) solve $R_1x = y$ for $x$ using the [[triangular matrix|triangular]] shape of $R$

### condition of the linear least square solutions
- the [[linear least squares]] can be solved on two ways

1) using the [[cholesky decomposition]] and the normal equation $A^\top Ax = A^\top b$
2) using the [[QR decomposition]] and solving $R_1x  = Q_1^\top b$ 

- however $A^\top Ax = A^\top b$ has a [[condition]] of $\kappa(A^\top A)=\kappa(A)^2$
- while solving $R_1x  = Q_1^\top b$ is eqivalent to solving $Q_1^{-\top}  R_1x = Q_1 R_1x = AX = b$ and thus has a [[condition]] $\kappa(A)$

![[condition#condition]]

![[condition of a matrix#condition of a square matrix]]


![[condition of a matrix#condition of $A top A$]]
# ---------------------------------

![[cholesky decomposition#cholesky decomposition]]


![[linear equation system#solvig a linear equation system]]


![[QR decomposition#QR decomposition]]

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
- $\mathrm{argmin} ||Ax - b||_2$ always has a solution if $\mathrm{rank}(A)=m$

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

- if $\mathrm{rank}(A) = m$  then $A^\top A$ is even positive definite

$$
\begin{split}
&x^\top A^\top Ax =  (Ax)^\top Ax = \langle Ax, Ax \rangle = ||Ax||^2 \geq 0 \\
&||Ax||^2 = 0 \Leftrightarrow Ax = 0 \\
&\mathrm{rank}(A) = m \Rightarrow A_{(*, 1)}, ..., A_{(*, m)} \text{ are linear independen} \\
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
- $\mathrm{argmin} ||Ax - b||_2$ always has a solution if $\mathrm{rank}(A)=m$

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

- if $\mathrm{rank}(A) = m$  then $A^\top A$ is even positive definite

$$
\begin{split}
&x^\top A^\top Ax =  (Ax)^\top Ax = \langle Ax, Ax \rangle = ||Ax||^2 \geq 0 \\
&||Ax||^2 = 0 \Leftrightarrow Ax = 0 \\
&\mathrm{rank}(A) = m \Rightarrow A_{(*, 1)}, ..., A_{(*, m)} \text{ are linear independen} \\
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
- and if $\mathrm{rank}(A)=m$ then $A^\top A$ is positive definite and thus has a inverse


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
&\mathrm{rank}(A) = m \Rightarrow A_{(*, 1)}, ..., A_{(*, m)} \text{ are linear independen} \\
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

START
Basic
- given an overdeterminded [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$

$$
x = \mathrm{argmin} ||Ax - b||_2
$$

- how to solve [[linear least squares]] using the [[QR decomposition]]

Back: 
### solving linear least squares with the [[QR decomposition]]
- given the normal equation of the [[linear least squares]] minimizing solution $A^\top Ax^*   = A^\top b$
- and the [[QR decomposition]] of $A \in \mathbb{R}^{n \times m}$ with an [[orthogonal matrix]] $Q_1 \in \mathbb{R}^{m \times m}$ and a [[triangular matrix]] $R \in \mathbb{R}^{m \times m}$ auch that $A=Q_1R_1$

$$
\begin{split}
A^\top Ax   &= A^\top b \\ 
(Q_1R_1)^\top Q_1R_1x &= (Q_1R_1)^\top\\ 
R_1^\top Q_1^\top Q_1R_1x &=  R_1^\top Q_1^\top b\\ 
R_1x  &= Q_1^\top b \\ 
\end{split}
$$

1) calculate the [[QR decomposition]] $A=Q_1R_1$
2) calculate $y = Q_1^\top b$
3) solve $R_1x = y$ for $x$ using the [[triangular matrix|triangular]] shape of $R$

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


### QR decomposition
- for every [[matrix]] $A \in \mathbb{R}^{n \times m}$ with $n \geq m$ there exists a [[orthogonal matrix]] $Q \in \mathbb{R}^{n \times n}$ and a [[triangular matrix]] $R \in \mathbb{R}^{n \times m}$ auch that $A=QR$
- furthermore there exists an [[orthogonal matrix]] $Q_1 \in \mathbb{R}^{n \times m}$ and a [[triangular matrix]] $R_1 \in \mathbb{R}^{m \times m}$ auch that $A=Q_1R_1$

$$
\begin{split}
A 
&= QR \\
&= \left(\begin{matrix}Q_1 & Q_2\end{matrix}\right)\left(\begin{matrix}R_1 \\ 0\end{matrix}\right) \\
&= Q_1R_1 \\
\end{split}
$$
- can be used for approximating the solution of an overdetermined [[linear equation system]] using [[linear least squares]]]]


------------------------

### linear least squares
- given an overdeterminded [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$
- since there is no exact soltion the approach is to find the best fitting solution that minimizes the squared deviation
$$
x = \mathrm{argmin} ||Ax - b||_2
$$
- here always exists a solution


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
- and if $\mathrm{rank}(A)=m$ then $A^\top A$ is positive definite and thus has a inverse



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
&\mathrm{rank}(A) = m \Rightarrow A_{(*, 1)}, ..., A_{(*, m)} \text{ are linear independen} \\
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


$$
\begin{split}
\nabla f (x) &=  A^\top\left(Ax -b\right)  \\
\end{split}
$$

Tags: mathematics
<!--ID: 1722342554294-->
END

START
Basic
- given an overdeterminded [[linear equation system]] with [[matrix]] $A \in \mathbb{R}^{n \times m}$ and [[vector|vectors]] $x \in \mathbb{R}^{m}$ and $b \in \mathbb{R}^{n}$ with $n \ge m$

$$
x = \mathrm{argmin} ||Ax - b||_2
$$

- explain two methodes of solving the problem
- compare the approaches regarding their [[condition]]

Back: 
### condition of the linear least square solutions
- the [[linear least squares]] can be solved on two ways

1) using the [[cholesky decomposition]] and the normal equation $A^\top Ax = A^\top b$
2) using the [[QR decomposition]] and solving $R_1x  = Q_1^\top b$ 

- however $A^\top Ax = A^\top b$ has a [[condition]] of $\kappa(A^\top A)=\kappa(A)^2$
- while solving $R_1x  = Q_1^\top b$ is eqivalent to solving $Q_1^{-\top}  R_1x = Q_1 R_1x = AX = b$ and thus has a [[condition]] $\kappa(A)$


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

### solving linear least squares with the [[QR decomposition]]
- given the normal equation of the [[linear least squares]] minimizing solution $A^\top Ax^*   = A^\top b$
- and the [[QR decomposition]] of $A \in \mathbb{R}^{n \times m}$ with an [[orthogonal matrix]] $Q_1 \in \mathbb{R}^{m \times m}$ and a [[triangular matrix]] $R \in \mathbb{R}^{m \times m}$ auch that $A=Q_1R_1$

$$
\begin{split}
A^\top Ax   &= A^\top b \\ 
(Q_1R_1)^\top Q_1R_1x &= (Q_1R_1)^\top\\ 
R_1^\top Q_1^\top Q_1R_1x &=  R_1^\top Q_1^\top b\\ 
R_1x  &= Q_1^\top b \\ 
\end{split}
$$

1) calculate the [[QR decomposition]] $A=Q_1R_1$
2) calculate $y = Q_1^\top b$
3) solve $R_1x = y$ for $x$ using the [[triangular matrix|triangular]] shape of $R$


------------------------


### condition
- given a [[function]] $F: X \subset \mathbb{R}^m \to Y \subset \mathbb{R}^n$ 
- given input data $x$ and perturbed input data $\tilde x = x + \Delta x$ 
- the [[condition]] of $F$ is the smallest number $\kappa\left(F\right)$ such that the following is true

$$
\frac{||F(x) - F(\tilde x)||}{||F(x)||} \leq \kappa\left(F\right) \cdot \frac{||x - \tilde x||}{||x||}
$$


### condition of a square matrix
- given a [[regular matrix|regular]] [[square matrix]] $A \in \mathbb{R}^{m \times m}$ 
- the [[condition]] of the $A$ for a arbitray [[operator norm]] is defined as follows
$$
\kappa(A) = \left|\left|A^{-1}\right|\right| \cdot \left|\left|A\right|\right|
$$
- the [[condition of a matrix]] anwsers the question of how big the relative error of $x$ would be when $b$ is pertubed by an error vector $e$ (or $A$ is pertubed)
$$
Ax=b + e
$$

### upper bound of the condition of a sqaure matrix
$$
\kappa(A) = \left|\left|A^{-1}\right|\right| \cdot \left|\left|A\right|\right| \leq \left|\left|AA^{-1}\right|\right| = 1
$$

### condition of a non square matrix
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$ with [[rank]] $m$ 
- the [[condition]] of the $A$ for a arbitray [[operator norm]] is defined as follows
$$
\kappa(A) = \frac{\max_{||x||=1} ||Ax||}{\min_{||x||=1} ||Ax||}
$$



### condition
- given a [[function]] $F: X \subset \mathbb{R}^m \to Y \subset \mathbb{R}^n$ 
- given input data $x$ and perturbed input data $\tilde x = x + \Delta x$ 
- the [[condition]] of $F$ is the smallest number $\kappa\left(F\right)$ such that the following is true

$$
\frac{||F(x) - F(\tilde x)||}{||F(x)||} \leq \kappa\left(F\right) \cdot \frac{||x - \tilde x||}{||x||}
$$



### QR decomposition
- for every [[matrix]] $A \in \mathbb{R}^{n \times m}$ with $n \geq m$ there exists a [[orthogonal matrix]] $Q \in \mathbb{R}^{n \times n}$ and a [[triangular matrix]] $R \in \mathbb{R}^{n \times m}$ auch that $A=QR$
- furthermore there exists an [[orthogonal matrix]] $Q_1 \in \mathbb{R}^{n \times m}$ and a [[triangular matrix]] $R_1 \in \mathbb{R}^{m \times m}$ auch that $A=Q_1R_1$

$$
\begin{split}
A 
&= QR \\
&= \left(\begin{matrix}Q_1 & Q_2\end{matrix}\right)\left(\begin{matrix}R_1 \\ 0\end{matrix}\right) \\
&= Q_1R_1 \\
\end{split}
$$
- can be used for approximating the solution of an overdetermined [[linear equation system]] using [[linear least squares]]

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
- and if $\mathrm{rank}(A)=m$ then $A^\top A$ is positive definite and thus has a inverse




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
&\mathrm{rank}(A) = m \Rightarrow A_{(*, 1)}, ..., A_{(*, m)} \text{ are linear independen} \\
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


$$
\begin{split}
\nabla f (x) &=  A^\top\left(Ax -b\right)  \\
\end{split}
$$

Tags: mathematics
<!--ID: 1722344586568-->
END

