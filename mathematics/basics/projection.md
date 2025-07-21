
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

![[projection 3.jpg]]


### relationship [[projection]] to the [[cosine]]
- the [[cosine]] is the length of the [[projection]] of a [[vector]] $a$ to a [[vector]] $b$ devided by the length of $a$

$$
\begin{split}
\cos(\phi) = \frac{ankathte}{hypotenuse} = \frac{||b'||}{||a||} = 
\frac{||proj_b(a)||}{||a||} = \frac{\langle a,b\rangle}{||a||\cdot||b||}
\end{split}
$$

$$
\underbrace{||proj_a(b)||}_{\cos{\phi} \cdot ||b||} \cdot ||a|| 
=
\underbrace{||proj_b(a)||}_{\cos{\phi} \cdot ||a||} \cdot ||b||
$$

### projection into the column space
- [[projection]] of a [[vector]] $b$ to the [[column space]] of [[matrix]] $A$ is defined as $P_A(b)$
- $b - AP_A(b)$ has to be [[orthogonal]] to the [[column space]] of $A$ 

$$
\begin{split}
\langle A, b-AP_A(b) \rangle &= A^\top \left(b-AP_A(b)\right) = 0 \\
A^\top b  &= A^\top AP_A(b)\\
P_A(b)  &= \left(A^\top A \right)^{-1}A^\top b

\end{split}
$$



![[Pasted image 20221009111212.png]]


### projection into an orthonormal subspace
- given the [[orthonormal]] [[basis]] $V=V_1,..., V_n \in \mathbb{R}^{d \times n}$ with $V^\top V=I$
- let $P_V(X)$ be the [[projection]] of $X$ into $\mathrm{span}(V_1, ..., V_n)$

$$
\begin{split}
&V^\top \left(VP_V(X) - X\right) = 0 \\ 
&V^\top X = V^\top VP_V(X) = P_V(X) \\ 

\end{split}
$$


# anki

START
Basic
[[projection]] into an [[orthonormal]] [[subspace]] with proof
Back: 
### projection into an orthonormal subspace
- given the [[orthonormal]] [[basis]] $V=V_1,..., V_n \in \mathbb{R}^{d \times n}$ with $V^\top V=I$
- let $P_V(X)$ be the [[projection]] of $X$ into $\mathrm{span}(V_1, ..., V_n)$

$$
\begin{split}
&V^\top \left(VP_V(X) - X\right) = 0 \\ 
&V^\top X = V^\top VP_V(X) = P_V(X) \\ 

\end{split}
$$


### projection into the column space
- [[projection]] of a [[vector]] $b$ to the [[column space]] of [[matrix]] $A$ is defined as $P_A(b)$
- $b - AP_A(b)$ has to be [[orthogonal]] to the [[column space]] of $A$ 

$$
\begin{split}
\langle A, b-AP_A(b) \rangle &= A^\top \left(b-AP_A(b)\right) = 0 \\
A^\top b  &= A^\top AP_A(b)\\
P_A(b)  &= \left(A^\top A \right)^{-1}A^\top b

\end{split}
$$



![[Pasted image 20221009111212.png]]
Tags: mathematics linear_algebra SS25
<!--ID: 1753118033401-->
END


START
Basic
[[projection]] into the [[column space]] of a [[matrix]] with proof
Back: 
### projection into the column space
- [[projection]] of a [[vector]] $b$ to the [[column space]] of [[matrix]] $A$ is defined as $P_A(b)$
- $b - AP_A(b)$ has to be [[orthogonal]] to the [[column space]] of $A$ 

$$
\begin{split}
\langle A, b-AP_A(b) \rangle &= A^\top \left(b-AP_A(b)\right) = 0 \\
A^\top b  &= A^\top AP_A(b)\\
P_A(b)  &= \left(A^\top A \right)^{-1}A^\top b

\end{split}
$$



![[Pasted image 20221009111212.png]]
Tags: mathematics linear_algebra SS25
<!--ID: 1665308790789-->
END


START
Basic
[[projection]] of [[vector|vectors]] on eachother
- equation
Back: 
### [[projection]] of [[vector|vectors]] on eachother
- let $b' = proj_b(a)$ be the projection of [[vector]] $a$ on [[vector]] $b$
- the length of $proj_b(a)$ is given by the [[inner product]] of $a$  and $b$ devided by the length of $b$ (because the length of the [[projection]] on $proj_b(a)$ does not depend on the length of $b$)

$$
||proj_b(a)|| = ||b'|| = \frac{\langle a,b \rangle}{||b||}
$$
- since $b'$ has the same direction as b the following is true
$$
proj_b(a) = b' = \frac{\langle a,b \rangle}{||b||} \frac{b}{||b||}
$$

![[projection 4.jpg]]

#### relationship [[inner product]] to [[projection]]

- given a [[vector]] $a$ and a [[vector]] $b$ then $\langle a, b \rangle$ is equal to the length of the [[projection]] of $a$ on $b$ [[multiplication|multiplied]] with the length of $b$ (and vice versa) 
- thus the [[inner product]] contains the information about the (unnormalized) length of the [[projection]] of one [[vector]] to another



_______________________


### inner product
- let $(V, +, \cdot)$ be a [[vector space]]
-  [[function]]  $\langle\cdot,\cdot\rangle: V \times V \rightarrow \mathbb{R}$ is an [[inner product]] if the following conditions are true
1) [[linear map|linearity]] (regarding both elemements because of the [[symmetric]])

$$
\forall x,y,z \in V, \lambda \in \mathbb{R}:\langle x + \lambda y , z \rangle = \langle x , z  \rangle + \lambda \langle  y , z \rangle
$$
2) [[symmetric]]

$$
\forall x,y \in V: \langle x  , y \rangle = \langle y  , x \rangle
$$
3) [[positive definite]]

$$
\forall x \in V: \langle x  , x \rangle  \leftrightarrow x=0 
$$
$$
\forall x \in V: \langle x  , x \rangle  \geq 0
$$



### norm
- generalization of the concept of **length of a [[vector]]**
- let $V$ be a [[vector space]]
- the [[function]] $||\:.||: V \rightarrow \mathbb{R^+}$ is a [[norm]] is it satisfies the following conditions
1) [[positive definite]]
$$
||x||=0 \Leftrightarrow x = 0
$$

2) absolutely [[homogeneous]]
$$
\forall x \in V, \lambda \in \mathbb{K}: ||\lambda \cdot x|| = |\lambda| \cdot ||x||
$$
3) [[triangle inequality]]
$$
\forall v, w \in V: ||v + w|| \leq ||v|| + ||w||
$$


Tags: mathematics
<!--ID: 1714834319817-->
END


START
Basic
relationship [[projection]] to the [[cosine]]
Back: 

### relationship [[projection]] to the [[cosine]]
- the [[cosine]] is the length of the [[projection]] of a [[vector]] $a$ to a [[vector]] $b$ devided by the length of $a$
$$
\begin{split}
\cos(\phi) = \frac{ankathte}{hypotenuse} = \frac{||b'||}{||a||} = 
\frac{||proj_b(a)||}{||a||} = \frac{\langle a,b\rangle}{||a||\cdot||b||}
\end{split}
$$
![[projection 6.jpg]]


### [[projection]] of [[vector|vectors]] on eachother
- let $b'$ be the projection of [[vector]] $a$ on [[vector]] $b$
- the length of $b'$ is given by the [[inner product]] of $a$  and $b$ devided by the length of $b$ (because the length of the [[projection]] on $proj_b(a) = b$ does not depend on the length of $b$)

$$
||proj_b(a)||=||b'|| = \frac{\langle a,b \rangle}{||b||}
$$
- since $b'$ has the same direction as b the following is true
$$
proj_b(a) = b' = \frac{\langle a,b \rangle}{||b||} \frac{b}{||b||}
$$


#### relationship [[inner product]] to [[projection]]

- given a [[vector]] $a$ and a [[vector]] $b$ then $\langle a, b \rangle$ is equal to the length of the [[projection]] of $a$ on $b$ [[multiplication|multiplied]] with the length of $b$ (and vice versa) 
- thus the [[inner product]] contains the information about the (unnormalized) length of the [[projection]] of one [[vector]] to another


Tags: mathematics
<!--ID: 1715272168170-->
END


START
Basic
- proof and geometric interpretation for the following
$$
||proj_a(b)||  \cdot ||a|| 
=
||proj_b(a)||  \cdot ||b||
$$
Back: 
$$
\underbrace{||proj_a(b)||}_{\cos{\phi} \cdot ||b||} \cdot ||a|| 
=
\underbrace{||proj_b(a)||}_{\cos{\phi} \cdot ||a||} \cdot ||b||
$$
### relationship [[projection]] to the [[cosine]]
- the [[cosine]] is the length of the [[projection]] of a [[vector]] $a$ to a [[vector]] $b$ devided by the length of $a$
$$
\begin{split}
\cos(\phi) = \frac{ankathte}{hypotenuse} = \frac{||b'||}{||a||} = 
\frac{||proj_b(a)||}{||a||} = \frac{\langle a,b\rangle}{||a||\cdot||b||}
\end{split}
$$
![[projection 7.jpg]]


### [[projection]] of [[vector|vectors]] on eachother
- let $b'$ be the projection of [[vector]] $a$ on [[vector]] $b$
- the length of $b'$ is given by the [[inner product]] of $a$  and $b$ devided by the length of $b$ (because the length of the [[projection]] on $proj_b(a) = b$ does not depend on the length of $b$)

$$
||proj_b(a)||=||b'|| = \frac{\langle a,b \rangle}{||b||}
$$
- since $b'$ has the same direction as b the following is true
$$
proj_b(a) = b' = \frac{\langle a,b \rangle}{||b||} \frac{b}{||b||}
$$


#### relationship [[inner product]] to [[projection]]

- given a [[vector]] $a$ and a [[vector]] $b$ then $\langle a, b \rangle$ is equal to the length of the [[projection]] of $a$ on $b$ [[multiplication|multiplied]] with the length of $b$ (and vice versa) 
- thus the [[inner product]] contains the information about the (unnormalized) length of the [[projection]] of one [[vector]] to another


Tags: mathematics
<!--ID: 1716645825924-->
END