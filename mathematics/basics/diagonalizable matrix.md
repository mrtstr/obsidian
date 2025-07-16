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

# anki




START
Basic
[[diagonal matrix]]
- definition
- sufficient condition
- powers of a [[diagonal matrix]]
- invariant shifts
- diagonalization of symmetric matrices
Back: 
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
<!--ID: 1752603832851-->
END

START
Basic
[[diagonal matrix]]
- definition
- proof for: sufficient existance condition

Back: 
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



Tags: mathematics basics SS25
<!--ID: 1752603832854-->
END


START
Basic
[[diagonal matrix]]
- definition
- proof for: invariant shifts

Back: 
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



Tags: mathematics basics SS25
<!--ID: 1752603832857-->
END