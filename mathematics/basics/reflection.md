### reflection
![[IMG-20240731-WA0003.jpg]]
$$
\begin{split}
\mathrm{refl}_b(a) 
&= a - 2 ||\mathrm{proj}_b(a)|| \\
&=a - 2 \frac{\langle a, b\rangle}{||b||^2} b  \\
&=a - 2 \frac{a^\top b}{||b||^2} b  \\
\end{split}
$$

### relection as orthogonal matrix
- can be represented by an [[orthogonal matrix]] $Q$ such that $\mathrm{refl}_b(a) = Qa$

$$
\begin{split}
Q_{(i,j)}
&=\delta_{i,j} - 2 \frac{b_ib_j}{||b||^2} 
 \\
 Q
&=I - 2 \frac{bb^\top}{||b||^2} 
 \\
\end{split}
$$


##### proof
$$
\begin{split}
\mathrm{refl}_b(a)_{i} 

&= \sum_{j \in [n]} Q_{(i, j)} a_j \\
&= \sum_{j \in [n]} \left(\delta_{i,j} - 2 \frac{b_ib_j}{||b||^2}\right) a_j \\
&= a_i- \frac{2}{||b||^2} b_i \sum_{j \in [n]}   b_j a_j \\
&= a_i- \frac{2}{||b||^2} b_i a^\top b \\
&=a_i - 2 \frac{a^\top b}{||b||^2} b_i  \\
\Rightarrow \mathrm{refl}_b(a) =& Qa\\
\end{split}
$$





# -------------------


![[vector subtraction#vector subtraction]]


![[projection#projection of vector vectors on eachother]]


# anki

START
Basic
[[reflection]] of [[vector|vectors]]
- visual interpretation
- equation
Back: 

$$
\begin{split}
\mathrm{refl}_b(a) 
&= a - 2 ||\mathrm{proj}_b(a)|| \\
&=a - 2 \frac{\langle a, b\rangle}{||b||^2} b  \\
&=a - 2 \frac{a^\top b}{||b||^2} b  \\
\end{split}
$$

![[IMG-20240731-WA0003 1.jpg]]

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


### vector subtraction
![[Vector_subtraction.svg 2.png]]
Tags: mathematics linear_algebra
<!--ID: 1722447604128-->
END


START
Basic
[[reflection]] as a [[orthogonal matrix]] (with proof)
$$
\begin{split}
\mathrm{refl}_b(a) 
&=a - 2 \frac{a^\top b}{||b||^2} b  \\
\end{split}
$$

Back: 
### relection as orthogonal matrix
- can be represented by an [[orthogonal matrix]] $Q$ such that $\mathrm{refl}_b(a) = Qa$

$$
\begin{split}
Q_{(i,j)}
&=\delta_{i,j} - 2 \frac{b_ib_j}{||b||^2} 
 \\
 Q
&=I - 2 \frac{bb^\top}{||b||^2} 
 \\
\end{split}
$$


##### proof
$$
\begin{split}
\mathrm{refl}_b(a)_{i} 

&= \sum_{j \in [n]} Q_{(i, j)} a_j \\
&= \sum_{j \in [n]} \left(\delta_{i,j} - 2 \frac{b_ib_j}{||b||^2}\right) a_j \\
&= a_i- \frac{2}{||b||^2} b_i \sum_{j \in [n]}   b_j a_j \\
&= a_i- \frac{2}{||b||^2} b_i a^\top b \\
&=a_i - 2 \frac{a^\top b}{||b||^2} b_i  \\
\Rightarrow \mathrm{refl}_b(a) =& Qa\\
\end{split}
$$


### reflection
$$
\begin{split}
\mathrm{refl}_b(a) 
&= a - 2 ||\mathrm{proj}_b(a)|| \\
&=a - 2 \frac{\langle a, b\rangle}{||b||^2} b  \\
&=a - 2 \frac{a^\top b}{||b||^2} b  \\
\end{split}
$$

![[IMG-20240731-WA0003 2.jpg]]

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


### vector subtraction

![[Vector_subtraction.svg 3.png]]

Tags: mathematics linear_algebra
<!--ID: 1722447604131-->
END