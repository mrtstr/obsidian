### matrix induced inner product
- every [[symmetric matrix]] $A \in \mathbb{R}^{n \times n}$ induces an [[inner product]]
$$
\langle x, y \rangle_A = y^\top Ax
$$
TODO: add proof
# ------------------
![[inner product#inner product]]

# anki

START
Basic
relationship [[matrix]] and [[inner product]]
Back: 
### matrix induced inner product
- every [[symmetric matrix]] $A \in \mathbb{R}^{n \times n}$ induces an [[inner product]]
$$
\langle x, y \rangle_A = y^\top Ax
$$

TODO: add proof
___________________
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

Tags: mathematics
<!--ID: 1714495264983-->
END