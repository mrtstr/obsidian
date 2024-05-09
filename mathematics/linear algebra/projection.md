
### [[projection]] of [[vector|vectors]] on eachother
- let $b'$ be the projection of [[vector]] $a$ on [[vector]] $b$
- the length of $b'$ is given by the [[inner product]] of $a$  and $b$ devided by the length of $b$ (because the length of the [[projection]] on $b$ does not depend on the length of $b$)

$$
||b'|| = \frac{\langle a,b \rangle}{||b||}
$$
- since $b'$ has the same direction as b the following is true
$$
b' = \frac{\langle a,b \rangle}{||b||} \frac{b}{||b||}
$$

![[projection 3.jpg]]


### relationship [[projection]] to the [[cosine]]
- the [[cosine]] is the length of the [[projection]] of a [[vector]] $a$ to a [[vector]] $b$ devided by the length of $a$


### [[projection]] into the [[column space]]
Projection of a [[vector]] $b$ to the [[column space]] of [[matrix]] $A$
- $b - Ax$ has to be [[orthogonal]] to the [[column space]] of $A$
→ $A^\top \left(b-Ax\right) = 0$A^\top b
→ $A^\top b  = A^\top Ax$
→ $x  = \left(A^\top A \right)^{-1}A^\top b$

![[Pasted image 20221009111212.png]]


START
Basic
Projection of a [[vector]] $b$ to the [[column space]] of [[matrix]] $A$
Back: 
- $b - Ax$ has to be [[orthogonal]] to the [[column space]] of $A$
→ $A^\top \left(b-Ax\right) = 0$A^\top b
→ $A^\top b  = A^\top Ax$
→ $x  = \left(A^\top A \right)^{-1}A^\top b$

![[Pasted image 20221009111212.png]]
Tags: mathematics linear_algebra
<!--ID: 1665308790789-->
END


START
Basic
[[projection]] of [[vector|vectors]] on eachother
- equation
Back: 
### [[projection]] of [[vector|vectors]] on eachother
- let $b'$ be the projection of [[vector]] $a$ on [[vector]] $b$
- the length of $b'$ is given by the [[inner product]] of $a$  and $b$ devided by the length of $b$ (because the length of the [[projection]] on $b$ does not depend on the length of $b$)

$$
||b'|| = \frac{\langle a,b \rangle}{||b||}
$$
- since $b'$ has the same direction as b the following is true
$$
b' = \frac{\langle a,b \rangle}{||b||} \frac{b}{||b||}
$$

![[projection 4.jpg]]

#### relationship [[inner product]] to [[projection]]

- given a [[vector]] $a$ and a [[vector]] $b$ then $\langle a, b \rangle$ is equal to the length of the [[projection]] of $a$ on $b$ [[multiplication|multiplied]] with the length of $b$ (and vice versa) 
- thus the [[inner product]] contains the information about the (unnormalized) length of the [[projection]] of one [[vector]] to another



_______________________


### inner product
- let $(V, +, \cdot)$ be a [[vector space]]
-  [[function]]  $\langle\cdot,\cdot\rangle: V \times V \rightarrow \mathbb{R}$ is an [[inner product]] if the following conditions are true
1) [[linear function|linearity]] (regarding both elemements because of the [[symmetric]])

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

### [[projection]] of [[vector|vectors]] on eachother
- let $b'$ be the projection of [[vector]] $a$ on [[vector]] $b$
- the length of $b'$ is given by the [[inner product]] of $a$  and $b$ devided by the length of $b$ (because the length of the [[projection]] on $b$ does not depend on the length of $b$)

$$
||b'|| = \frac{\langle a,b \rangle}{||b||}
$$
- since $b'$ has the same direction as b the following is true
$$
b' = \frac{\langle a,b \rangle}{||b||} \frac{b}{||b||}
$$



#### relationship [[inner product]] to [[projection]]

- given a [[vector]] $a$ and a [[vector]] $b$ then $\langle a, b \rangle$ is equal to the length of the [[projection]] of $a$ on $b$ [[multiplication|multiplied]] with the length of $b$ (and vice versa) 
- thus the [[inner product]] contains the information about the (unnormalized) length of the [[projection]] of one [[vector]] to another


Tags: mathematics
<!--ID: 1715272168170-->
END