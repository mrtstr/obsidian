### eigenvectors and eigenvalues
- let $A \in \mathbb{R}^{n \times n}$ be a [[matrix]] a non-zero [[vector]] $v \in \mathbb{R}^n$ if there exists a [[scalar]] $\lambda \in \mathbb{R}$ which i such that $v$ is only scaled but not rotated by the [[linear map|linear transformation]] by $A$
$$
Av=\lambda v
$$
- $v$ is called an [[eigenvector]] and $\lambda$ s called [[eigenvalue]] of $A$

#### calculation of eigenvalues
- [[eigenvalue]] can be calculated by solving the roots of the characteristic [[polynomial]]


$$
\det(A-\lambda I) = 0
$$
- that means $A$ has up to $n$ [[eigenvalue]] because the [[polynomial]] can have multiple roots at one [[eigenvalue]]

##### proof
- using the fact that for a general $B \in \mathbb{R}^{n \times n}$ there exists a non-zero solution for $Bx=0$ exactly when $\det(B)=0$
$$
\begin{split}
&Av=\lambda v \\
\Rightarrow &(A - \lambda I)v&=0 \\
\Rightarrow &\det(A - \lambda I)&=0 \\

\end{split}
$$
#### number of eigenvalues and eigenvectors

- if $\lambda$ is a simple [[root]] (i.e., algebraic multiplicity = 1) of the characteristic [[polynomial]] there are an infinite number of [[eigenvector]] but all of them are [[linear independent]] i.e. there are all scaled version of the same [[vector]]
- if the algebraic multiplicity if $\lambda$ is $m$ then there are between one and $m$ [[linear independent]] [[eigenvector]] associated with $\lambda$

![[determinant#determinant]]


# anki




START
Basic
[[eigenvectors and eigenvalues]]
- definition
- calculation of [[eigenvalue]] with proof
- how many [[linear independent]] [[eigenvector]] exist?
Back: 

### eigenvectors and eigenvalues
- let $A \in \mathbb{R}^{n \times n}$ be a [[matrix]] a non-zero [[vector]] $v \in \mathbb{R}^n$ if there exists a [[scalar]] $\lambda \in \mathbb{R}$ which i such that $v$ is only scaled but not rotated by the [[linear map|linear transformation]] by $A$
$$
Av=\lambda v
$$
- $v$ is called an [[eigenvector]] and $\lambda$ s called [[eigenvalue]] of $A$

#### calculation of eigenvalues
- [[eigenvalue]] can be calculated by solving the roots of the characteristic [[polynomial]]


$$
\det(A-\lambda I) = 0
$$
- that means $A$ has up to $n$ [[eigenvalue]] because the [[polynomial]] can have multiple roots at one [[eigenvalue]]

##### proof
- using the fact that for a general $B \in \mathbb{R}^{n \times n}$ there exists a non-zero solution for $Bx=0$ exactly when $\det(B)=0$
$$
\begin{split}
&Av=\lambda v \\
\Rightarrow &(A - \lambda I)v&=0 \\
\Rightarrow &\det(A - \lambda I)&=0 \\

\end{split}
$$
#### number of eigenvalues and eigenvectors

- if $\lambda$ is a simple [[root]] (i.e., algebraic multiplicity = 1) of the characteristic [[polynomial]] there are an infinite number of [[eigenvector]] but all of them are [[linear independent]] i.e. there are all scaled version of the same [[vector]]
- if the algebraic multiplicity if $\lambda$ is $m$ then there are between one and $m$ [[linear independent]] [[eigenvector]] associated with $\lambda$

_________________

### diagonalizable matrix
- a [[matrix]] $A \in \mathbb{R}^{n\times n}$ is a [[diagonalizable matrix]] if there exists a [[inverse matrix|inverable matrix]] $B\in \mathbb{R}^{n\times n}$ and a [[diagonal matrix]] $D=diag(\lambda_1, ..., \lambda_n)\in \mathbb{R}^{n\times n}$ such that the following decomposition is possible

$$
A = BDB^{-1}
$$

#### existence of diagonalizable matrix
- this is the case exactly when $A$ has  $n$ [[linear independent]] [[eigenvector]], which is guaranteed if has $n$ distinct [[eigenvalue]] 
- the [[eigenvalue]] of $A$ are always $\lambda_1$, ..., $\lambda_n$
- note: the reverse is not true i.e. if $A$ is a [[diagonal matrix]] it doesn't need to have distinct eigenvalues
###### proof
- let $\lambda_1, ..., \lambda_n$ be the [[eigenvalue]] of $A$ with the corresponding [[eigenvector]] $v_i$ $\Rightarrow Av_i = \lambda_iv_i$
- since $v_1,..., v_n$ are [[linear independent]] $B=(v_1, ..., v_n)$ is invertable

$$
\begin{split}
Av_i &= \lambda_iv_i \\
\Rightarrow AB_{(*, j)} &= (BD)_{(*, j)} \\
\Rightarrow AB &= BD \\
\Rightarrow A &= BDB^{-1} \\
\end{split}
$$



#### powers of diagonalizable matrix
- the following is true for powers of [[diagonalizable matrix]] with $D^m=diag(\lambda_1^m, ..., \lambda_n^m)\in \mathbb{R}^{n\times n}$

$$
A^m = BD^mB^{-1}
$$

- $A$ is an [[inverse matrix|invertible matrix]] it can't have [[eigenvalue]] that are zero

###### proof

$$
\begin{split}
A^2 = AA
&=  BDB^{-1}BDB^{-1} \\
&=  BDDB^{-1} \\
&=  BD^2B^{-1} \\
...
\end{split}
$$

#### invariant shifts
- if $A = BDB^{-1}$ then $A+\lambda I  = B\tilde DB^{-1}$ with $\tilde D = diag(\lambda_1 + \lambda, ..., \lambda_n + \lambda)$

###### proof

$$
\begin{split}
A+\lambda I 
&= BDB^{-1} +\lambda I \\
&= BDB^{-1} +\lambda BIB^{-1} \\
&= B(D+\lambda I)B^{-1}  \\
&= B\tilde DB^{-1}  \\
\end{split}
$$

#### diagonalization of symmetric matrices
- if $A$ is a [[symmetric matrix]] then $B$ is an [[orthogonal matrix]] because $B^T=B^{-1}$ 

Tags: mathematics basics SS25
<!--ID: 1752664226884-->
END