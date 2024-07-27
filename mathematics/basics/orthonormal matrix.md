### orthonormal matrix
- a [[orthogonal matrix]] with a [[determinant]] of $1$ is a [[orthonormal matrix]]

![[orthogonal matrix#orthogonal matrix]]


START
Basic
[[orthonormal matrix]]
- definition
- difference to an [[orthogonal matrix]]
 
Back: 

### orthonormal matrix
- a [[orthogonal matrix]] with a [[determinant]] of $1$ is a [[orthonormal matrix]]

### determinant of a orthogonal matrix

$$
\det(Q) \in \{1, -1\}
$$

#### proof
$$
\begin{split}
\det\left(QQ^\top\right) 
&= \det\left(I\right) = 1 \\
&= \det\left(Q\right)\det\left(Q^\top\right) \\
&= \det\left(Q\right)\det\left(Q\right)  \\
\Rightarrow \det(Q) &\in \{1, -1\}
\end{split}
$$


### orthogonal matrix
- a [[orthogonal matrix]] is a [[matrix]] $Q \in \mathbb{R}^{n \times n}$ with a [[transpose]] that is equal to its [[inverse matrix]]  
$$
Q^{-1}=Q^{T} \Leftrightarrow Q^\top Q = QQ^\top = I
$$

- from $QQ^\top = Q^\top Q = I$ it follows that column [[vector|vectors]] $Q_{(*,j)}$ (and row [[vector|vectors]] $Q_{(i,*)}$) that are not on the diagonal are [[orthogonal]] (perpendicular) to each other 
$$
\left\langle Q_{(*,j)} Q_{(*,k)}\right\rangle = Q_{(*,j)}^\top Q_{(*,k)} = \left\{\begin{matrix} 1 &\text{if } j=k \\ 0 & \text{else} \end{matrix} \right.
$$
- from $\left\langle Q_{(*,j)} Q_{(*,j)}\right\rangle = 1$ follows that all column and row [[vector|vectors]] need to be normalized
$$
\begin{split}
&\left\langle Q_{(*,j)} Q_{(*,j)}\right\rangle = 1 \\ 
\Rightarrow& \sqrt{\left\langle Q_{(*,j)} Q_{(*,j)}\right\rangle} = ||Q_{(*,j)}|| = 1 \\ 

\end{split}
$$
------------------------

### properties of the [[determinant]]

$$
\det(A) = \det\left(A^{T}\right)
$$


$$
\det(AB) = \det(A)\det(B)
$$


### every [[inner product]] induces a [[norm]]
$$
||x|| = \sqrt{\langle x, x \rangle}
$$
$$
||x||^2 = \langle x, x \rangle
$$
Tags: mathematics linear_algebra

END