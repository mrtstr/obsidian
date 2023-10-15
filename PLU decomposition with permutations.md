## [[LU decomposition without permutations]] with [[permutations]]

### Definition PLU decomposition ([[LU decomposition without permutations]] with [[permutations]])
A [[PLU decomposition with permutations]] of $A \in \mathbb{R}^{n \times n}$ if a factorization in a normalized lower [[triangular matrix]] $L$ and an upper [[triangular matrix]] $U$ and a [[permutation matrix]] $P$ such that the following is true
$$
PA = LU
$$

![[triangular matrix#normalized lower triangular matrix]]
![[triangular matrix#upper triangular matrix]]

![[permutation matrix#Definition permutation matrix]]

### existence and uniqueness
every [[square matrix]] $A \in \mathbb{R}^{n \times n}$ has a [[LU decomposition without permutations]] with [[permutations]] but it's not unique

### process [[PLU decomposition with permutations]]
#### given

![[triangular matrix#inverse matrix inverse of a normalized triangular matrix]]

![[triangular matrix#matrix product multiplication of normalized triangular matrix]]

![[row echelon form#Definition row echelon form]]

![[frobenius matrix#Definition frobenius matrix]]

![[permutation matrix#Definition permutation matrix]]




#### reducing $A$ in a [[row echelon form]] by multiplying with [[permutation matrix|permutation matrices]] and [[frobenius matrix|frobenius matrices]]

1) For reach column  $j \in [1, ..., n]$ we want to create a [[pivot]] element $a_{j,j}$ by construct a [[frobenius matrix]] $L_i$ that makes all values below $a_{j,j}$ to zero. In case $a_{j,j}$ is zero we construct a [[permutation matrix]] $P_i$ that is swiching $a_{j,j}$ with a non-zero element in $a_{i,j} \in \{a_{i,j} | i < j\}$.
$$
U = L^{(n)}P^{(n)}L^{(n-1)}P^{(n-1)}...L^{(2)}P^{(2)}L^{(1)}P^{(1)}A
$$
2) separate the [[frobenius matrix|frobenius matrices]] $L_i$ from the [[permutation matrix|permutation matrices]] $P_i$
![[frobenius matrix#swiching elements with permutation matrix permutation matrices]]
2) 
3) 
4) and  $a_{i,i}$ to a [[pivot]] element by making all values below $a_{i,i}$ to zero. This is possible when $a_{i,i} \neq 0$, otherwise the [[LU decomposition without permutations]] without [[permutation matrix|permutations]] is not possible. The result of this process will be the upper [[triangular matrix]] $U = L^{(n)}L^{(n-1)}...L^{(1)}A$
5) [[matrix product|multiply]] and [[inverse matrix|invert]] the [[frobenius matrix|frobenius matrices]] to calculcate the lower normalized [[triangular matrix]] $L = \left(L^{(n)}L^{(n-1)}...L^{(1)}\right)^{-1}$. This is easy because of the properties of  normalized [[triangular matrix]]

$$
\begin{split}
A &= A^{(1)} = \begin{pmatrix}
a^{(1)}_{(1:1)}         &\ a^{(1)}_{(1:2)} &\ a^{(1)}_{(1:3)} \\
a^{(1)}_{(2:1)}         &\ a^{(1)}_{(2:2)} &\ a^{(1)}_{(2:3)} \\
a^{(1)}_{(3:1)}         &\ a^{(1)}_{(3:2)} &\ a^{(1)}_{(3:3)} \\  
\end{pmatrix} \\
A^{(2)} &= L^{(1)} A^{(1)} = 
\begin{pmatrix}
1                              &\ 0         &\ 0 \\
-\frac{a^{(1)}_{(2:1)}}{a^{(1)}_{(1:1)}}   &\ 1         &\ 0 \\
-\frac{a^{(1)}_{(3:1)}}{a^{(1)}_{(1:1)}}   &\ 0         &\ 1  \\  
\end{pmatrix} 
\begin{pmatrix}
a^{(1)}_{(1:1)}         &\ a^{(1)}_{(1:2)} &\ a^{(1)}_{(1:3)} \\
a^{(1)}_{(2:1)}         &\ a^{(1)}_{(2:2)} &\ a^{(1)}_{(2:3)} \\
a^{(1)}_{(3:1)}         &\ a^{(1)}_{(3:2)} &\ a^{(1)}_{(3:3)} \\  
\end{pmatrix}
=
\begin{pmatrix}
a^{(2)}_{(1:1)}  &\ a^{(2)}_{(1:2)} &\ a^{(2)}_{(1:3)} \\
0                &\ a^{(2)}_{(2:2)} &\ a^{(2)}_{(2:3)} \\
0                &\ a^{(2)}_{(3:2)} &\ a^{(2)}_{(3:3)} \\  
\end{pmatrix} \\
A^{(3)} &= L^{(2)} A^{(2)} = 
\begin{pmatrix}
1  &\ 0        &\ 0 \\
0  &\ 1         &\ 0 \\
0  &\ -\frac{a^{(2)}_{(3:2)}}{a^{(2)}_{(2:2)}}        &\ 1  \\  
\end{pmatrix} 
\begin{pmatrix}
a^{(2)}_{(1:1)}  &\ a^{(2)}_{(1:2)} &\ a^{(2)}_{(1:3)} \\
0                &\ a^{(2)}_{(2:2)} &\ a^{(2)}_{(2:3)} \\
0                &\ a^{(2)}_{(3:2)} &\ a^{(2)}_{(3:3)} \\  
\end{pmatrix} 
=
\begin{pmatrix}
a^{(3)}_{(1:1)}  &\ a^{(3)}_{(1:2)} &\ a^{(3)}_{(1:3)} \\
0                &\ a^{(3)}_{(2:2)} &\ a^{(3)}_{(2:3)} \\
0                &\ 0               &\ a^{(3)}_{(3:3)} \\  
\end{pmatrix}  \\
U &= A^{(n)} = A^{(3)} = L^{(3)}L^{(2)}L^{(1)}A \\
\Rightarrow L &= \left(L^{(3)}L^{(2)}L^{(1)}\right)^{-1} = 
\begin{pmatrix}
1         &\ 0&\ 0\\
-l^{(1)}_{(2:1)}         &1 &\ 0 \\
-l^{(1)}_{(3:1)}         &\ -l^{(2)}_{(3:1)}  &\ 1 \\  
\end{pmatrix} \\
\Rightarrow A &= LU  
\end{split}
$$

