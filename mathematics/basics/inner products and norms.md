## inner products and norms

### every [[inner product]] induces a [[norm]]
$$
||x|| = \sqrt{\langle x, x \rangle}
$$
$$
||x||^2 = \langle x, x \rangle
$$
### proof
1) [[positive definite]] follows directy for the [[inner product]] being [[positive definite]]
$$
\langle x, x \rangle \geq 0 \Rightarrow ||x|| = \sqrt{\langle x, x \rangle} \geq 0
$$

2) absolutly [[homogeneous]]
$$
\begin{split}
||\lambda x|| 
&= \sqrt{\langle \lambda x, \lambda x \rangle} \\
&= \sqrt{\lambda^2\langle  x,  x \rangle} \quad \text{(linearity of inner product)}\\
&= \sqrt{\lambda^2} \sqrt{\langle  x,  x \rangle} \\
&= |\lambda| \cdot || x||  \\
\end{split}
$$
3) [[triangle inequality]]

### some [[norm|norms]] induce [[inner product|inner products]]
However, a norm ||⋅||is induced by an inner product if and only if it satisfies the parallelogram law:

||x+y||2+||x−y||2=2(||x||2+||y||2)
# ------------------

![[inner product#inner product]]

![[norm#norm]]


# anki

START
Basic
proof that every [[inner product]] induces a [[norm]]
Back: 

### every [[inner product]] induces a [[norm]]
$$
||x|| = \sqrt{\langle x, x \rangle}
$$
$$
||x||^2 = \langle x, x \rangle
$$
### proof
1) [[positive definite]] follows directy for the [[inner product]] being [[positive definite]]
$$
\langle x, x \rangle \geq 0 \Rightarrow ||x|| = \sqrt{\langle x, x \rangle} \geq 0
$$

2) absolutly [[homogeneous]]
$$
\begin{split}
||\lambda x|| 
&= \sqrt{\langle \lambda x, \lambda x \rangle} \\
&= \sqrt{\lambda^2\langle  x,  x \rangle} \quad \text{(linearity of inner product)}\\
&= \sqrt{\lambda^2} \sqrt{\langle  x,  x \rangle} \\
&= |\lambda| \cdot || x||  \\
\end{split}
$$
3) [[triangle inequality]]

_______________________

### cauchy schwarz inequality
- let $V$ be a [[vector space]] with an [[inner product]] $\langle \cdot , \cdot \rangle$ 
- then the following is true for all $x, y \in V$

$$
|\langle x , y \rangle|^2 \leq \langle x , x \rangle \cdot \langle y , y \rangle
$$
eqivalent:
$$
|\langle x , y \rangle| \leq || x || \cdot || y ||
$$


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

### every [[inner product]] induces a [[norm]]
$$
||x|| = \sqrt{\langle x, x \rangle}
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
<!--ID: 1714582042906-->
END