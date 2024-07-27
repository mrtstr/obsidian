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

### determinant of an orthogonal matrix

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

### rank of an orthogonal matrix
- given na [[orthogonal matrix]] is a [[matrix]] $Q \in \mathbb{R}^{n \times n}$
- $A$ has a full [[rank]] $\mathrm{rank}(Q)=n$

$$
\mathrm{rank}(Q)=n
$$
#### proof
- $A$ has an [[inverse matrix]] thus needs to have a full [[rank]]


# ----------------------------

![[determinant#properties]]

![[inner products and norms#every inner product induces a norm]]

![[inner product#relationship inner product to projection]]


START
Basic
[[orthogonal matrix]]
- definition
- properties of the column and row vectors with proof
 
Back: 
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

### every [[inner product]] induces a [[norm]]
$$
||x|| = \sqrt{\langle x, x \rangle}
$$
$$
||x||^2 = \langle x, x \rangle
$$
Tags: mathematics linear_algebra

END


START
Basic
[[determinant]] of a [[orthogonal matrix]] with proof
[[rank]] of a [[orthogonal matrix]] with proof
 
Back: 

### rank of an orthogonal matrix
- given na [[orthogonal matrix]] is a [[matrix]] $Q \in \mathbb{R}^{n \times n}$
- $A$ has a full [[rank]] $\mathrm{rank}(Q)=n$

$$
\mathrm{rank}(Q)=n
$$
#### proof
- $A$ has an [[inverse matrix]] thus needs to have a full [[rank]]


### determinant of an orthogonal matrix

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