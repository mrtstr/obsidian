### PLU decomposition
A [[PLU decomposition]] of $A \in \mathbb{R}^{n \times n}$ if a factorization in a normalized lower [[triangular matrix]] $L$ and an upper [[triangular matrix]] $U$ and a [[permutation matrix]] $P$ such that the following is true
$$
PA = LU
$$
# ----------------------

![[triangular matrix#normalized lower triangular matrix]]

![[triangular matrix#upper triangular matrix]]

![[permutation matrix#Definition permutation matrix]]

### existence and uniqueness
every [[square matrix]] $A \in \mathbb{R}^{n \times n}$ has a [[LU decomposition]] with [[permutations]] but it's not unique

### [[time complexity]] of the [[PLU decomposition]]
- its $\in \mathcal{O}(n^3)$  

### process [[PLU decomposition]]
#### given

![[triangular matrix#inverse matrix inverse of a normalized triangular matrix]]

![[triangular matrix#matrix product multiplication of normalized triangular matrix]]

![[row echelon form#Definition row echelon form]]

![[frobenius matrix#Definition frobenius matrix]]

![[permutation matrix#Definition permutation matrix]]

![[frobenius matrix#swiching elements of frobenius matrix with permutation matrix permutation matrices]]


#### 1) reducing $A$ in a [[row echelon form]] by multiplying with [[permutation matrix|permutation matrices]] and [[frobenius matrix|frobenius matrices]]

For reach column  $j \in [1, ..., n]$ we want to create a [[pivot]] element $a_{j,j}$ by construct a [[frobenius matrix]] $L_i$ that makes all values below $a_{j,j}$ to zero. In case $a_{j,j}$ is zero we construct a [[permutation matrix]] $P_i$ that is swiching $a_{j,j}$ with a non-zero element in $a_{i,j} \in \{a_{i,j} | i < j\}$. Now the [[pivot]] element  $a_{j,j}$ is used to construct a [[frobenius matrix]] $L^{(i)}$ that is making all values below $a_{j,j}$ to zero (see [[LU decomposition]]).  The result of this process will be the upper [[triangular matrix]] $U$. 
$$
U = L^{(n)}P^{(n)}L^{(n-1)}P^{(n-1)}...L^{(2)}P^{(2)}L^{(1)}P^{(1)}A
$$


#### 2) separate the [[frobenius matrix|frobenius matrices]] $L_i$ from the [[permutation matrix|permutation matrices]] $P_i$
- since [[permutation matrix|permutation matrices]] are [[orthogonal matrix|orthogonal matrices]] and a because of the special properties of [[frobenius matrix|frobenius matrices]] the following operation is possible with $\widehat{L}^{(i)}$ still being a [[frobenius matrix]]
$$
\begin{split}
L^{(i)}P^{(i)} = P^{(i)}\widehat{L}^{(i)} \\
\Rightarrow \widehat{L}^{(i)} = P^{T(i)} L^{(i)}P^{(i)} 
\end{split}
$$

- This process is repeated until [[permutation matrix|permutation matrices]] and the [[frobenius matrix|frobenius matrices]] are seperated from each other
$$
\begin{split}
U 
&= L^{(n)}P^{(n)}L^{(n-1)}P^{(n-1)}...L^{(2)}P^{(2)}L^{(1)}P^{(1)}A \\
&= L^{(n)}P^{(n)}L^{(n-1)}P^{(n-1)}...P^{(2)}\widehat{L}^{(2)}P^{(1)}\widehat{L}^{(1)}A \\
&= L^{(n)}P^{(n)}L^{(n-1)}P^{(n-1)}...P^{(2)}P^{(1)}\widehat{\widehat{L}}^{(2)}\widehat{L}^{(1)}A \\
&.... \\
&= P^{(n)}P^{(n-1)}...P^{(2)}P^{(1)}\widehat{\dddot{\widehat{L}}}^{(n)}\widehat{\dddot{\widehat{L}}}^{(n-1)}...\widehat{\widehat{L}}^{(2)}\widehat{L}^{(1)}A \\
\end{split}
$$

#### 3) combining $P$ and $L$
- [[matrix product|multiply]] and [[inverse matrix|invert]] the [[frobenius matrix|frobenius matrices]] to calculcate the lower normalized [[triangular matrix]] $L$. This is easy because of the properties of normalized [[triangular matrix]].
- [[matrix product|multiply]] the [[permutation matrix|permutation matrices]] to calculcate the combined [[permutation matrix]] $P$
$$
\begin{split}
P&= P^{(n)}P^{(n-1)}...P^{(2)}P^{(1)}\\
L&= \left(\widehat{\dddot{\widehat{L}}}^{(n)}\widehat{\dddot{\widehat{L}}}^{(n-1)}...\widehat{\widehat{L}}^{(2)}\widehat{L}^{(1)} \right)^{-1}\\
\end{split}
$$


# anki

START
Basic
[[PLU decomposition]]
 - definition
 - [[time complexity]]
 - existence
 - uniqueness

Back: 
### Definition PLU decomposition ([[LU decomposition]] with [[permutations]])
A [[PLU decomposition]] of $A \in \mathbb{R}^{n \times n}$ if a factorization in a normalized lower [[triangular matrix]] $L$ and an upper [[triangular matrix]] $U$ and a [[permutation matrix]] $P$ such that the following is true
$$
PA = LU
$$
#### normalized lower triangular matrix 
A [[matrix]] $L$ is a lower [[triangular matrix]] if 
1) all values obove the diagonal line are zero $\forall i < j: a_{ij} = 0$
2) all values on the diagonal are one $\forall i: a_{ii} = 1$

$$
\begin{split}
L = \begin{pmatrix}
1         &\ 0         &\ 0 \\
l_{(2:1)} &\ 1         &\ 0 \\
l_{(3:1)} &\ l_{(3:2)} &\ 1 \\  
\end{pmatrix}
\end{split}
$$
#### upper triangular matrix 
A [[matrix]] $U$ is a upper [[triangular matrix]] if all values obove the diagonal line are zero $\forall i < j: a_{ij} = 0$ 
$$
\begin{split}
U = \begin{pmatrix}
u_{(1:1)} &\ u_{(1:2)} &\ u_{(1:3)} \\
0         &\ u_{(2:2)} &\ l_{(2:3)} \\
0         &\ 0         &\ u_{(3:3)} \\  
\end{pmatrix}
\end{split}
$$

####  [[permutation matrix]]
- [[matrix]] $P \in \mathbb{R}^{n \times n}$ with only one $1$ per row and column and everything else $0$
### example
$$
\begin{split}
P &= \begin{pmatrix}
0 &\ 0 &\ 1 \\
1 &\ 0 &\ 0 \\
0 &\ 1 &\ 0 \\  
\end{pmatrix} \\

\end{split}
$$
### existence and uniqueness
every [[square matrix]] $A \in \mathbb{R}^{n \times n}$ has a [[LU decomposition]] with [[permutations]] but it's not unique

Tags: mathematics linear_algebra
<!--ID: 1697960588096-->
END

START
Basic
[[PLU decomposition]]
- process
Back: 
## process [[PLU decomposition]]

#### 1) reducing $A$ in a [[row echelon form]] by multiplying with [[permutation matrix|permutation matrices]] and [[frobenius matrix|frobenius matrices]]

For reach column  $j \in [1, ..., n]$ we want to create a [[pivot]] element $a_{j,j}$ by construct a [[frobenius matrix]] $L_i$ that makes all values below $a_{j,j}$ to zero. In case $a_{j,j}$ is zero we construct a [[permutation matrix]] $P_i$ that is swiching $a_{j,j}$ with a non-zero element in $a_{i,j} \in \{a_{i,j} | i < j\}$. Now the [[pivot]] element  $a_{j,j}$ is used to construct a [[frobenius matrix]] $L^{(i)}$ that is making all values below $a_{j,j}$ to zero (see [[LU decomposition]]).  The result of this process will be the upper [[triangular matrix]] $U$. 
$$
U = L^{(n)}P^{(n)}L^{(n-1)}P^{(n-1)}...L^{(2)}P^{(2)}L^{(1)}P^{(1)}A
$$


#### 2) separate the [[frobenius matrix|frobenius matrices]] $L_i$ from the [[permutation matrix|permutation matrices]] $P_i$
- since [[permutation matrix|permutation matrices]] are [[orthogonal matrix|orthogonal matrices]] and a because of the special properties of [[frobenius matrix|frobenius matrices]] the following operation is possible with $\widehat{L}^{(i)}$ still being a [[frobenius matrix]]
$$
\begin{split}
L^{(i)}P^{(i)} = P^{(i)}\widehat{L}^{(i)} \\
\Rightarrow \widehat{L}^{(i)} = P^{T(i)} L^{(i)}P^{(i)} 
\end{split}
$$

- This process is repeated until [[permutation matrix|permutation matrices]] and the [[frobenius matrix|frobenius matrices]] are seperated from each other
$$
\begin{split}
U 
&= L^{(n)}P^{(n)}L^{(n-1)}P^{(n-1)}...L^{(2)}P^{(2)}L^{(1)}P^{(1)}A \\
&= L^{(n)}P^{(n)}L^{(n-1)}P^{(n-1)}...P^{(2)}\widehat{L}^{(2)}P^{(1)}\widehat{L}^{(1)}A \\
&= L^{(n)}P^{(n)}L^{(n-1)}P^{(n-1)}...P^{(2)}P^{(1)}\widehat{\widehat{L}}^{(2)}\widehat{L}^{(1)}A \\
&.... \\
&= P^{(n)}P^{(n-1)}...P^{(2)}P^{(1)}\widehat{\dddot{\widehat{L}}}^{(n)}\widehat{\dddot{\widehat{L}}}^{(n-1)}...\widehat{\widehat{L}}^{(2)}\widehat{L}^{(1)}A \\
\end{split}
$$

#### 3) combining $P$ and $L$
- [[matrix product|multiply]] and [[inverse matrix|invert]] the [[frobenius matrix|frobenius matrices]] to calculcate the lower normalized [[triangular matrix]] $L$. This is easy because of the properties of normalized [[triangular matrix]].
- [[matrix product|multiply]] the [[permutation matrix|permutation matrices]] to calculcate the combined [[permutation matrix]] $P$
$$
\begin{split}
P&= P^{(n)}P^{(n-1)}...P^{(2)}P^{(1)}\\
L&= \left(\widehat{\dddot{\widehat{L}}}^{(n)}\widehat{\dddot{\widehat{L}}}^{(n-1)}...\widehat{\widehat{L}}^{(2)}\widehat{L}^{(1)} \right)^{-1}\\
\end{split}
$$


## Definition PLU decomposition ([[LU decomposition]] with [[permutations]])
A [[PLU decomposition]] of $A \in \mathbb{R}^{n \times n}$ if a factorization in a normalized lower [[triangular matrix]] $L$ and an upper [[triangular matrix]] $U$ and a [[permutation matrix]] $P$ such that the following is true
$$
PA = LU
$$

## existence and uniqueness
every [[square matrix]] $A \in \mathbb{R}^{n \times n}$ has a [[LU decomposition]] with [[permutations]] but it's not unique
Tags: mathematics linear_algebra

## given
#### normalized lower triangular matrix 
A [[matrix]] $L$ is a lower [[triangular matrix]] if 
1) all values obove the diagonal line are zero $\forall i < j: a_{ij} = 0$
2) all values on the diagonal are one $\forall i: a_{ii} = 1$

$$
\begin{split}
L = \begin{pmatrix}
1         &\ 0         &\ 0 \\
l_{(2:1)} &\ 1         &\ 0 \\
l_{(3:1)} &\ l_{(3:2)} &\ 1 \\  
\end{pmatrix}
\end{split}
$$
#### upper triangular matrix 
A [[matrix]] $U$ is a upper [[triangular matrix]] if all values obove the diagonal line are zero $\forall i < j: a_{ij} = 0$ 
$$
\begin{split}
U = \begin{pmatrix}
u_{(1:1)} &\ u_{(1:2)} &\ u_{(1:3)} \\
0         &\ u_{(2:2)} &\ l_{(2:3)} \\
0         &\ 0         &\ u_{(3:3)} \\  
\end{pmatrix}
\end{split}
$$

####  [[permutation matrix]]
- [[matrix]] $P \in \mathbb{R}^{n \times n}$ with only one $1$ per row and column and everything else $0$
example
$$
\begin{split}
P &= \begin{pmatrix}
0 &\ 0 &\ 1 \\
1 &\ 0 &\ 0 \\
0 &\ 1 &\ 0 \\  
\end{pmatrix} \\

\end{split}
$$
#### [[inverse matrix|inverse]] of a normalized [[triangular matrix]]
$$
\begin{split}
U &= \begin{pmatrix}
1         &\ u_{(1:2)} &\ u_{(1:3)} \\
0         &\ 1         &\ l_{(2:3)} \\
0         &\ 0         &\ 1 \\  
\end{pmatrix} \\
U^{-1} &= \begin{pmatrix}
1         &\ -u_{(1:2)} &\ -u_{(1:3)} \\
0         &\ 1         &\ -u_{(2:3)} \\
0         &\ 0         &\ 1 \\  
\end{pmatrix} \\
UU^{-1}=U^{-1}U &=\begin{pmatrix}
1         &\ u_{(1:2)} &\ u_{(1:3)} \\
0         &\ 1         &\ u_{(2:3)} \\
0         &\ 0         &\ 1 \\  
\end{pmatrix}
\begin{pmatrix}
1         &\ -u_{(1:2)} &\ -u_{(1:3)} \\
0         &\ 1         &\ -u_{(2:3)} \\
0         &\ 0         &\ 1 \\  
\end{pmatrix} \\
&= \begin{pmatrix}
1         &\ u_{(1:2)}-u_{(1:2)} &\ u_{(1:3)}-u_{(1:3)} \\
0         &\ 1         &\ u_{(2:3)}-u_{(2:3)} \\
0         &\ 0         &\ 1 \\  
\end{pmatrix}
= \begin{pmatrix}
1         &\ 0 &\ 0 \\
0         &\ 1         &\ 0 \\
0         &\ 0         &\ 1 \\  
\end{pmatrix} \\
\end{split}
$$
#### [[matrix product|multiplication]] of normalized [[triangular matrix]]
$$
\begin{split}
U^{(1)} &= \begin{pmatrix}
1         &\ u_{(1:2)}^{(1)} &\ u_{(1:3)}^{(1)} \\
0         &\ 1         &\ u_{(2:3)}^{(1)} \\
0         &\ 0         &\ 1 \\  
\end{pmatrix} \\
U^{(2)} &= \begin{pmatrix}
1         &\ u_{(1:2)}^{(2)} &\ u_{(1:3)}^{(2)} \\
0         &\ 1         &\ u_{(2:3)}^{(1)} \\
0         &\ 0         &\ 1 \\  
\end{pmatrix} \\
U^{(1)}U^{(2)}=U^{(2)}U^{(1)} &=
\begin{pmatrix}
1         &\ u_{(1:2)}^{(1)}+u_{(1:2)}^{(2)} &\ u_{(1:3)}^{(1)}+u_{(1:3)}^{(2)} \\
0         &\ 1         &\ u_{(2:3)}^{(1)}+u_{(2:3)}^{(2)} \\
0         &\ 0         &\ 1 \\  
\end{pmatrix}

\end{split}
$$
#### Definition frobenius matrix
A frobenius [[matrix]] is a special form of lower normalized [[triangular matrix]] with the additional propertie that only one column can have non-zero entries below the diagonal 

examples
$$
\begin{split}
F_1 = \begin{pmatrix}
1         &\ 0         &\ 0 \\
f_{(2:1)} &\ 1         &\ 0 \\
f_{(3:1)} &\ 0 &\ 1 \\  
\end{pmatrix}\\
F_2 = \begin{pmatrix}
1         &\ 0         &\ 0 \\
0 &\ 1         &\ 0 \\
0 &\ f_{(3:2)} &\ 1 \\  
\end{pmatrix}
\end{split}
$$

#### Definition [[pivot]]
An elelemt $a_{ij}$ if m [[matrix]] $A$ is a [[pivot]] element if the following conditions are true
1) $a_{ij} \neq 0$
2) all elements below $a_{ij}$ are zero and all elements on the right of  $a_{ij}$ are zero $\forall k \geq i, l \leq j,(kl) \neq (ij) :a_{kl} = 0$
$$
\begin{split}
A = \begin{pmatrix}
a_{(1:1)} &\    a_{(1:2)}     &\ a_{(1:3)} \\
zero         &\ p             &\ a_{(2:3)} \\
zero		&\   zero         &\ a_{(3:3)} \\  
\end{pmatrix}
\end{split}
$$
#### Definition [[row echelon form]]
A [[matrix]] $A$ is in [[row echelon form]] if all non-zero rows have a [[pivot]]


#### swiching elements of [[frobenius matrix]] with [[permutation matrix|permutation matrices]]

$$
\begin{split}
&P_{xy} \text{ with} \\ 
&p_{xy}=p_{yx}=1 \\
&\forall i \neq x, y: p_{ii}=1  \\
&\forall i  \neq j, x, y: p_{ij}=0  \\
\end{split}
$$
- $P_{xy}A$ will swap the rows $x$ and $y$ of $A$ 
- $AP_{xy}$ will swap the column $x$ and $y$ of $A$ 

- if $F$ is a [[frobenius matrix]] $P_{ij} F P^T_{ij}$ with $i < j$ is again a [[frobenius matrix]] with the potentially non-zero elements $i$ and $j$ swiched

Tags: mathematics linear_algebra
<!--ID: 1697960648195-->
END