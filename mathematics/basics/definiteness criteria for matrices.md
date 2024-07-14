### definiteness criteria for matrices
- given a sqare [[matrix]] $A \in \mathbb{R}^{m \times m}$ and let $A_1, ..., A_m$ be the main [[minor|minors]] auf $A$
$$
\begin{split}
A_1 &= (a_{11}) \\
A_2 &= \left(
\begin{matrix}
a_{11} & a_{12} \\
a_{21} & a_{22} \\
\end{matrix}
\right) \\
A_3 &= ...
\end{split}
$$
- $A$ is [[definiteness of matrices|positive definite]] exactly when $\forall k \in [m]: \det\left(A_k\right) > 0$
- $A$ is [[definiteness of matrices|positive semidefinite]] exactly when $\forall k \in [m]: \det\left(A_k\right) \geq 0$
- $A$ is [[definiteness of matrices|negative definite]] exactly when $\forall k \in [m]: \mathrm{sign}\left(\det\left(A_m\right)\right) = (-1)^k$
- $A$ is [[definiteness of matrices|negative semidefinite]] exactly when $\forall k \in [m]: \mathrm{sign}\left(\det\left(A_m\right)\right) \neq (-1)^{k+1}$
- $A$ is [[definiteness of matrices|indefinite]] if none of the other conditions is true
# ---------------

![[definiteness of matrices#definiteness of matrices]]

![[determinant#determinant]]

# anki

START
Basic
hot to check the definiteness of a [[matrix]]?
Back: 
### definiteness criteria for matrices
- given a sqare [[matrix]] $A \in \mathbb{R}^{m \times m}$ and let $A_1, ..., A_m$ be the main [[minor|minors]] auf $A$
$$
\begin{split}
A_1 &= (a_{11}) \\
A_2 &= \left(
\begin{matrix}
a_{11} & a_{12} \\
a_{21} & a_{22} \\
\end{matrix}
\right) \\
A_3 &= ...
\end{split}
$$
- $A$ is [[definiteness of matrices|positive definite]] exactly when $\forall k \in [m]: \det\left(A_k\right) > 0$
- $A$ is [[definiteness of matrices|positive semidefinite]] exactly when $\forall k \in [m]: \det\left(A_k\right) \geq 0$
- $A$ is [[definiteness of matrices|negative definite]] exactly when $\forall k \in [m]: \mathrm{sign}\left(\det\left(A_m\right)\right) = (-1)^k$
- $A$ is [[definiteness of matrices|negative semidefinite]] exactly when $\forall k \in [m]: \mathrm{sign}\left(\det\left(A_m\right)\right) \neq (-1)^{k+1}$
- $A$ is [[definiteness of matrices|indefinite]] if none of the other conditions is true

____________________

### positive definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[positive definite]] if the following is true
$$
\forall x \in \mathbb{R}^n \setminus{0}: x^\top A x >0
$$

- in other words $f(x) = x^\top A x$ is a [[positive definite]] [[function]]

### positive semi definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[definiteness of matrices|positive semi definite]] if the following is true
$$
\forall x \in \mathbb{R}^n : x^\top A x \geq0
$$
- in other words $f(x) = x^\top A x$ is a [[positive definite|positive semi definite]] [[function]]

### negative definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[positive definite]] if the following is true
$$
\forall x \in \mathbb{R}^n \setminus{0}: x^\top A x < 0
$$

- in other words $f(x) = x^\top A x$ is a [[positive definite|negative definite]] [[function]]

### negative semi definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[definiteness of matrices|positive semi definite]] if the following is true
$$
\forall x \in \mathbb{R}^n : x^\top A x \geq0
$$
- in other words $f(x) = x^\top A x$ is a [[positive definite|negative semi definite]] [[function]]

### indefinite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[definiteness of matrices|indefinite]] if its neither positive nor negative (semi) definite
- that means the [[function]] $f(x) = x^\top A x$ can take positive as well as negative values

### positive definite
- a [[function]] $f: A \rightarrow B$ is [[positive definite]] on a neighbourhood $D$ of the [[origin]] if the following is true
$$
f(0) = 0 \land \forall v \in D: f(v) \geq 0
$$

### determinant
- let $A \in \mathbb{R}^{n \times n}$ be a [[square matrix]] 
- its [[determinant]] $\det(A)$ is defined as follows (here developed after column $i$)
$$
\det(A) = 
\left\{
\begin{matrix}
a_{11} \qquad &n=1 \\
\sum_{j \in [n]} a_{ij}(-1)^{i+j}\det(M_{ij}) \qquad &n>1   \\
\end{matrix}
\right.
$$
- the [[determinant]] can also be developed after a row $j$
$$
\det(A) = 
\left\{
\begin{matrix}
a_{11} \qquad &n=1 \\
\sum_{i \in [n]} a_{ij}(-1)^{i+j}\det(M_{ij}) \qquad &n>1   \\
\end{matrix}
\right.
$$



![[det.png]]


Tags: mathematics linear_algebra
<!--ID: 1720964044649-->
END