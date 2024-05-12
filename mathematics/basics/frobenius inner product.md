### frobenius inner product
- given [[matrix]] $A, B \in \mathbb{R}^{n \times m}$
- the [[frobenius inner product]] is defined as follows
$$
\langle A, B\rangle_F = \sum_{i \in [n]} \sum_{j \in [m]} a_{ij} b_{ij} 
$$
- the [[frobenius inner product]] can be expressed as the [[trace]] of the [[matrix product]]
$$
\langle A, B\rangle_F = \mathrm{trace}\left(A^\top B\right) = \mathrm{trace}\left(A B^\top\right)
$$
- the [[frobenius inner product]] induces the [[frobenius norm]]

#  ---------------------
![[trace#trace]]

![[frobenius norm#frobenius norm]]

# anki

START
Basic
[[frobenius inner product]]
- definition
- relationship to the [[trace]]
- relationship to the [[frobenius norm]]
Back: 
### frobenius inner product
- given [[matrix]] $A, B \in \mathbb{R}^{n \times m}$
- the [[frobenius inner product]] is defined as follows
$$
\langle A, B\rangle_F = \sum_{i \in [n]} \sum_{j \in [m]} a_{ij} b_{ij} 
$$
- the [[frobenius inner product]] can be expressed as the [[trace]] of the [[matrix product]]
$$
\langle A, B\rangle_F = \mathrm{trace}\left(A^\top B\right) = \mathrm{trace}\left(A B^\top\right)
$$
- the [[frobenius inner product]] induces the [[frobenius norm]]


_______________________

### trace
- given a [[square matrix]] $A \in \mathbb{R}^{n \times n}$
- the [[trace]] of $A$ is defined as the [[addition|sum]] of the main diagonal
$$
\mathrm{trace}(A) = \sum_{i \in [n]} a_{ii}
$$

### frobenius norm
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$ 
- the [[frobenius norm]] $||\cdot||_F$ is defined as follows

$$
||A||_F = \sqrt{\sum_{i \in [n]}\sum_{j \in [m]} |a_{ij}|^2}
$$
- the [[frobenius norm]] is not a [[operator norm]] but it is induced by the [[frobenius inner product]] $\langle A, B\rangle_F = trace(A^\top B)$
$$
||A||_F = \sqrt{\langle A, A\rangle_F} = \sqrt{trace(A^\top A)} 
$$


### inner product
- generalization of the 
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
<!--ID: 1715521606643-->
END