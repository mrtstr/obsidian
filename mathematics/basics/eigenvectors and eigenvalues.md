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
- this means that $\lambda$ is an [[eigenvalue]] it has to make the columns of $A - \lambda I$ linear dependent when being subtracted from the diagonal

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
- if $A$ is a [[diagonalizable matrix]] it has exactly $n$ [[linear independent]] [[eigenvalue]]. In this case for each $\lambda$ the algebraic multiplicity has to be equal to the number of [[linear independent]] [[eigenvector]]


### relationship of the eigenvalues and the determinant
$$
\det(A) = \prod_{i=1}^n \lambda_i
$$
##### proof

$$
\det(A-\lambda I) = (-1)^n(\lambda - \lambda_1)(\lambda - \lambda_2)...(\lambda - \lambda_n)
$$

- when we set $\lambda=0$ he have the following which proves the claim

$$
\det(A-0 I) = \det(A) = (-1)^n(- \lambda_1)( - \lambda_2)...(- \lambda_n) = \prod_{i=1}^n \lambda_i
$$
### relationship of the eigenvalues and the trace

$$
\mathrm{trace}(A) = \sum_{i=1}^n \lambda_i
$$

##### proof for a diagonalizable matrix
- where we assume that $A=BDB^{-1}$ is a [[diagonalizable matrix]] but there is a proof without that assumption
$$
\begin{split}
\mathrm{trace}(A) 
&= \mathrm{trace}(BDB^{-1}) \\
&= \mathrm{trace}(D) \\
&=  \sum_{i=1}^n \lambda_i \\
\end{split}
$$
# ------------

![[diagonalizable matrix#diagonalizable matrix]]

![[determinant#determinant]]


# anki




START
Basic
[[eigenvectors and eigenvalues]]
- definition
- calculation of [[eigenvalue]] with proof
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
- this means that $\lambda$ is an [[eigenvalue]] it has to make the columns of $A - \lambda I$ linear dependent when being subtracted from the diagonal

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
- if $A$ is a [[diagonalizable matrix]] it has exactly $n$ [[linear independent]] [[eigenvalue]]. In this case for each $\lambda$ the algebraic multiplicity has to be equal to the number of [[linear independent]] [[eigenvector]]


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


Tags: mathematics basics SS25
<!--ID: 1752664226884-->
END


START
Basic
[[eigenvectors and eigenvalues]]
- definition
- how many [[eigenvalue]] and [[linear independent]] [[eigenvector]] exist?
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
- this means that $\lambda$ is an [[eigenvalue]] it has to make the columns of $A - \lambda I$ linear dependent when being subtracted from the diagonal

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
- if $A$ is a [[diagonalizable matrix]] it has exactly $n$ [[linear independent]] [[eigenvalue]]. In this case for each $\lambda$ the algebraic multiplicity has to be equal to the number of [[linear independent]] [[eigenvector]]


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


Tags: mathematics basics SS25
<!--ID: 1752671518295-->
END


START
Basic
[[eigenvectors and eigenvalues]]
- relationship to the [[determinant]] with proof
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
- this means that $\lambda$ is an [[eigenvalue]] it has to make the columns of $A - \lambda I$ linear dependent when being subtracted from the diagonal

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
- if $A$ is a [[diagonalizable matrix]] it has exactly $n$ [[linear independent]] [[eigenvalue]]. In this case for each $\lambda$ the algebraic multiplicity has to be equal to the number of [[linear independent]] [[eigenvector]]


### relationship of the eigenvalues and the determinant
$$
\det(A) = \prod_{i=1}^n \lambda_i
$$
##### proof

$$
\det(A-\lambda I) = (-1)^n(\lambda - \lambda_1)(\lambda - \lambda_2)...(\lambda - \lambda_n)
$$

- when we set $\lambda=0$ he have the following which proves the claim

$$
\det(A-0 I) = \det(A) = (-1)^n(- \lambda_1)( - \lambda_2)...(- \lambda_n) = \prod_{i=1}^n \lambda_i
$$

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




Tags: mathematics basics SS25
<!--ID: 1752671518298-->
END


START
Basic
[[eigenvectors and eigenvalues]]
- relationship to the [[trace]]
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
- this means that $\lambda$ is an [[eigenvalue]] it has to make the columns of $A - \lambda I$ linear dependent when being subtracted from the diagonal

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
- if $A$ is a [[diagonalizable matrix]] it has exactly $n$ [[linear independent]] [[eigenvalue]]. In this case for each $\lambda$ the algebraic multiplicity has to be equal to the number of [[linear independent]] [[eigenvector]]



### relationship of the eigenvalues and the trace

$$
\mathrm{trace}(A) = \sum_{i=1}^n \lambda_i
$$

##### proof for a diagonalizable matrix
- where we assume that $A=BDB^{-1}$ is a [[diagonalizable matrix]] but there is a proof without that assumption
$$
\begin{split}
\mathrm{trace}(A) 
&= \mathrm{trace}(BDB^{-1}) \\
&= \mathrm{trace}(D) \\
&=  \sum_{i=1}^n \lambda_i \\
\end{split}
$$



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



### trace
- given a [[square matrix]] $A \in \mathbb{R}^{n \times n}$
- the [[trace]] of $A$ is defined as the [[addition|sum]] of the main diagonal
$$
\mathrm{trace}(A) = \sum_{i \in [n]} a_{ii}
$$


Tags: mathematics basics SS25
<!--ID: 1752671518301-->
END