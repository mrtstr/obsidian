### reflection
- the [[reflection]] of a [[vector]] $a$ on a [[vector]] $b$ is defined as follows

$$
\begin{split}
\mathrm{proj}_b(a) &= a + x \\ 
\Rightarrow x &= \mathrm{proj}_b(a) - a \\ 

\mathrm{refl}_b(a) 
&= a + 2 x \\
&= 2 ||\mathrm{proj}_b(a)|| - a \\
&=2 \frac{\langle a, b\rangle}{||b||^2} b - a \\
\end{split}
$$

![[IMG-20240801-WA0002.jpg]]

### orthogonal refelction
- the [[reflection]] of a [[vector]] $a$ on hypterplane [[orthogonal]] to [[vector]] $b$ is the inverted [[reflection]] 

$$
\mathrm{orefl}_b(a) = - \mathrm{refl}_b(a) = a - 2 \frac{\langle a, b\rangle}{||b||^2} b  
$$
- given a [[vector]] $a$ and $b$
- the normalized [[vector]] $u$ (with $||u||=1$) should define a hyperplane such that $a$ is the [[orthogonal]] [[reflection]] of $b$
$$
a =\mathrm{orefl}_u(b) \Rightarrow u = \frac{a-b}{||a-b||}
$$

![[IMG-20240801-WA0004.jpg]]

### orthogonal refelction as orthogonal matrix
- the orthogonal refelction can be represented as a [[linear map|linear transformation]] with an [[orthogonal matrix]] $Q$ such that $\mathrm{orefl}_b(a) = Q_ba$

$$
\begin{split}
Q_{(i,j)}
&=\delta_{i,j} - 2 \frac{b_ib_j}{||b||^2} 
 \\
 Q_b
&=I - 2 \frac{bb^\top}{||b||^2} 
 \\
\end{split}
$$


##### proof

$$
\begin{split}
\mathrm{orefl}_b(a)_{i}  
&= a_{i}  - 2 \frac{\langle a, b\rangle}{||b||^2} b_{i}  \\
&= a_{i}  -  \sum_{j \in [n]} \frac{2}{||b||^2}   a_jb_j b_{i}  \\
&= \sum_{j \in [n]} \left(\delta_{i,j} - \frac{2}{||b||^2}   b_j b_{i}\right)  a_j \\
\Rightarrow Q_{(i, j)} =& \delta_{i,j} - \frac{2}{||b||^2}   b_j b_{i}\\
\Rightarrow Q =& I - \frac{2}{||b||^2}   b b^\top\\
\end{split}
$$


$$
\begin{split}
\Rightarrow Q  Q^\top 
=& \left(I - \frac{2}{||b||^2}   b b^\top\right) \left(I - \frac{2}{||b||^2}   b b^\top\right)^\top  \\
=& \left(I - \frac{2}{||b||^2}   b b^\top\right) \left(I - \frac{2}{||b||^2}   b b^\top\right)  \\
=& I -2 \frac{2}{||b||^2}   b b^\top + \frac{4}{||b||^4}   b b^\top b b^\top  \\
=& I -4 \frac{1}{||b||^2}   b b^\top + 4 \frac{\langle b, b\rangle}{||b||^4}     b b^\top  \\
=& I -4 \frac{1}{||b||^2}   b b^\top + \frac{4}{||b||^2}    b b^\top  \\
=& I  \\
\end{split}
$$




# -------------------


![[vector subtraction#vector subtraction]]


![[projection#projection of vector vectors on eachother]]


# anki

START
Basic
- [[reflection]] of [[vector|vectors]]
- [[reflection]] on an [[orthogonal]] hyperplane

- equation, proof and visulal interpretation
Back: 
### reflection
- the [[reflection]] of a [[vector]] $a$ on a [[vector]] $b$ is defined as follows

$$
\begin{split}
\mathrm{proj}_b(a) &= a + x \\ 
\Rightarrow x &= \mathrm{proj}_b(a) - a \\ 

\mathrm{refl}_b(a) 
&= a + 2 x \\
&= 2 ||\mathrm{proj}_b(a)|| - a \\
&=2 \frac{\langle a, b\rangle}{||b||^2} b - a \\
\end{split}
$$

![[IMG-20240801-WA0002 1.jpg]]

### orthogonal refelction
- the [[reflection]] of a [[vector]] $a$ on hypterplane [[orthogonal]] to [[vector]] $b$ is the inverted [[reflection]] 

$$
\mathrm{orefl}_b(a) = - \mathrm{refl}_b(a) = a - 2 \frac{\langle a, b\rangle}{||b||^2} b  
$$
- given a [[vector]] $a$ and $b$
- the normalized [[vector]] $u$ (with $||u||=1$) should define a hyperplane such that $a$ is the [[orthogonal]] [[reflection]] of $b$
$$
a =\mathrm{orefl}_u(b) \Rightarrow u = \frac{a-b}{||a-b||}
$$

![[IMG-20240801-WA0004 1.jpg]]


### [[projection]] of [[vector|vectors]] on eachother
- let $b' = proj_b(a)$ be the projection of [[vector]] $a$ on [[vector]] $b$
- the length of $proj_b(a)$ is given by the [[inner product]] of $a$  and $b$ devided by the length of $b$ (because the length of the [[projection]] on $proj_b(a)$ does not depend on the length of $b$)

$$
||\mathrm{proj}_b(a)|| = ||b'|| = \frac{\langle a,b \rangle}{||b||}
$$
- since $b'$ has the same direction as b the following is true
$$
\mathrm{proj}_b(a) = b' = \frac{\langle a,b \rangle}{||b||} \frac{b}{||b||}
$$



Tags: mathematics linear_algebra
<!--ID: 1722447604128-->
END


START
Basic
[[reflection#orthogonal refelction|orthogonal refelction]] as a [[orthogonal matrix]] (with proof) and check that its [[orthogonal]]

$$
\begin{split}
\mathrm{orefl}_b(a) 
&=a - 2 \frac{a^\top b}{||b||^2} b  \\
\end{split}
$$

Back: 
### orthogonal refelction as orthogonal matrix
- the orthogonal refelction can be represented as a [[linear map|linear transformation]] with an [[orthogonal matrix]] $Q$ such that $\mathrm{orefl}_b(a) = Q_ba$

$$
\begin{split}
Q_{(i,j)}
&=\delta_{i,j} - 2 \frac{b_ib_j}{||b||^2} 
 \\
 Q_b
&=I - 2 \frac{bb^\top}{||b||^2} 
 \\
\end{split}
$$


##### proof

$$
\begin{split}
\mathrm{orefl}_b(a)_{i}  
&= a_{i}  - 2 \frac{\langle a, b\rangle}{||b||^2} b_{i}  \\
&= a_{i}  -  \sum_{j \in [n]} \frac{2}{||b||^2}   a_jb_j b_{i}  \\
&= \sum_{j \in [n]} \left(\delta_{i,j} - \frac{2}{||b||^2}   b_j b_{i}\right)  a_j \\
\Rightarrow Q_{(i, j)} =& \delta_{i,j} - \frac{2}{||b||^2}   b_j b_{i}\\
\Rightarrow Q =& I - \frac{2}{||b||^2}   b b^\top\\
\end{split}
$$


$$
\begin{split}
\Rightarrow Q  Q^\top 
=& \left(I - \frac{2}{||b||^2}   b b^\top\right) \left(I - \frac{2}{||b||^2}   b b^\top\right)^\top  \\
=& \left(I - \frac{2}{||b||^2}   b b^\top\right) \left(I - \frac{2}{||b||^2}   b b^\top\right)  \\
=& I -2 \frac{2}{||b||^2}   b b^\top + \frac{4}{||b||^4}   b b^\top b b^\top  \\
=& I -4 \frac{1}{||b||^2}   b b^\top + 4 \frac{\langle b, b\rangle}{||b||^4}     b b^\top  \\
=& I -4 \frac{1}{||b||^2}   b b^\top + \frac{4}{||b||^2}    b b^\top  \\
=& I  \\
\end{split}
$$

______________________________

### reflection
- the [[reflection]] of a [[vector]] $a$ on a [[vector]] $b$ is defined as follows

$$
\begin{split}
\mathrm{proj}_b(a) &= a + x \\ 
\Rightarrow x &= \mathrm{proj}_b(a) - a \\ 

\mathrm{refl}_b(a) 
&= a + 2 x \\
&= 2 ||\mathrm{proj}_b(a)|| - a \\
&=2 \frac{\langle a, b\rangle}{||b||^2} b - a \\
\end{split}
$$

![[IMG-20240801-WA0002 3.jpg]]

### orthogonal refelction
- the [[reflection]] of a [[vector]] $a$ on hypterplane [[orthogonal]] to [[vector]] $b$ is the inverted [[reflection]] 

$$
\mathrm{orefl}_b(a) = - \mathrm{refl}_b(a) = a - 2 \frac{\langle a, b\rangle}{||b||^2} b  
$$


### [[projection]] of [[vector|vectors]] on eachother
- let $b' = proj_b(a)$ be the projection of [[vector]] $a$ on [[vector]] $b$
- the length of $proj_b(a)$ is given by the [[inner product]] of $a$  and $b$ devided by the length of $b$ (because the length of the [[projection]] on $proj_b(a)$ does not depend on the length of $b$)

$$
||\mathrm{proj}_b(a)|| = ||b'|| = \frac{\langle a,b \rangle}{||b||}
$$
- since $b'$ has the same direction as b the following is true
$$
\mathrm{proj}_b(a) = b' = \frac{\langle a,b \rangle}{||b||} \frac{b}{||b||}
$$




Tags: mathematics linear_algebra
<!--ID: 1722447604131-->
END


START
Basic
- given a [[vector]] $a$ and $b$
- the normalized [[vector]] $u$ (with $||u||=1$) should define a hyperplane such that $a$ is the [[orthogonal]] [[reflection]] of $b$

$$
a =\mathrm{orefl}_u(b)
$$

- expression for [[vector]] $u$

Back: 

### orthogonal refelction
- the [[reflection]] of a [[vector]] $a$ on hypterplane [[orthogonal]] to [[vector]] $b$ is the inverted [[reflection]] 

$$
\mathrm{orefl}_b(a) = - \mathrm{refl}_b(a) = a - 2 \frac{\langle a, b\rangle}{||b||^2} b  
$$
- given a [[vector]] $a$ and $b$
- the normalized [[vector]] $u$ (with $||u||=1$) should define a hyperplane such that $a$ is the [[orthogonal]] [[reflection]] of $b$
$$
a =\mathrm{orefl}_u(b) \Rightarrow u = \frac{a-b}{||a-b||}
$$

![[IMG-20240801-WA0004 2.jpg]]


### reflection
- the [[reflection]] of a [[vector]] $a$ on a [[vector]] $b$ is defined as follows

$$
\begin{split}
\mathrm{proj}_b(a) &= a + x \\ 
\Rightarrow x &= \mathrm{proj}_b(a) - a \\ 

\mathrm{refl}_b(a) 
&= a + 2 x \\
&= 2 ||\mathrm{proj}_b(a)|| - a \\
&=2 \frac{\langle a, b\rangle}{||b||^2} b - a \\
\end{split}
$$

![[IMG-20240801-WA0002 4.jpg]]


### [[projection]] of [[vector|vectors]] on eachother
- let $b' = proj_b(a)$ be the projection of [[vector]] $a$ on [[vector]] $b$
- the length of $proj_b(a)$ is given by the [[inner product]] of $a$  and $b$ devided by the length of $b$ (because the length of the [[projection]] on $proj_b(a)$ does not depend on the length of $b$)

$$
||\mathrm{proj}_b(a)|| = ||b'|| = \frac{\langle a,b \rangle}{||b||}
$$
- since $b'$ has the same direction as b the following is true
$$
\mathrm{proj}_b(a) = b' = \frac{\langle a,b \rangle}{||b||} \frac{b}{||b||}
$$



Tags: mathematics linear_algebra
<!--ID: 1722513882597-->
END