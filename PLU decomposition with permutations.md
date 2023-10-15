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

#### given

![[triangular matrix#inverse matrix inverse of a normalized triangular matrix]]

![[triangular matrix#matrix product multiplication of normalized triangular matrix]]

![[row echelon form#Definition row echelon form]]

![[frobenius matrix#Definition frobenius matrix]]

### reducing $A$ in a [[row echelon form]]

1) For reach column  $j \in [1, ..., n]$ select the [[pivot]] element $a_{i,i}$ and construct a [[frobenius matrix]] $L_i$ that makes $a_{i,i}$ to a [[pivot]] element by making all values below $a_{i,i}$ to zero. This is possible when $a_{i,i} \neq 0$, otherwise the [[LU decomposition without permutations]] without [[permutation matrix|permutations]] is not possible. The result of this process will be the upper [[triangular matrix]] $U = L^{(n)}L^{(n-1)}...L^{(1)}A$
2) [[matrix product|multiply]] and [[inverse matrix|invert]] the [[frobenius matrix|frobenius matrices]] to calculcate the lower normalized [[triangular matrix]] $L = \left(L^{(n)}L^{(n-1)}...L^{(1)}\right)^{-1}$. This is easy because of the properties of  normalized [[triangular matrix]]

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

### example [[LU decomposition without permutations]]

$$
\begin{split}
A &= A^{(1)} = \begin{pmatrix}
1  &\ 3 &\ -1 \\
2  &\ 8 &\ 4 \\
-1 &\ 3 &\ 4 \\  
\end{pmatrix} \\
A^{(2)} = L^{(1)} A^{(1)} &= 
\begin{pmatrix}
1                              &\ 0         &\ 0 \\
-\frac{a^{(1)}_{(2:1)}}{a^{(1)}_{(1:1)}}   &\ 1         &\ 0 \\
-\frac{a^{(1)}_{(3:1)}}{a^{(1)}_{(1:1)}}   &\ 0         &\ 1  \\  
\end{pmatrix} 
\begin{pmatrix}
1  &\ 3 &\ -1 \\
2  &\ 8 &\ 4 \\
-1 &\ 3 &\ 4 \\  
\end{pmatrix} \\
&= 
\begin{pmatrix}
1    &\ 0     &\ 0 \\
-2   &\ 1    &\ 0 \\
1    &\ 0     &\ 1  \\  
\end{pmatrix} 
\begin{pmatrix}
1  &\ 3 &\ -1 \\
2  &\ 8 &\ 4 \\
-1 &\ 3 &\ 4 \\  
\end{pmatrix} \\
&=
\begin{pmatrix}
1  &\ 3 &\ -1 \\
0  &\ 2 &\ 6 \\
0 &\ 6 &\ 3 \\  
\end{pmatrix} \\



A^{(3)} = L^{(2)} A^{(2)} &= 
\begin{pmatrix}
1  &\ 0        &\ 0 \\
0  &\ 1         &\ 0 \\
0  &\ -\frac{a^{(2)}_{(3:2)}}{a^{(2)}_{(2:2)}}        &\ 1  \\  
\end{pmatrix} 
\begin{pmatrix}
1  &\ 3 &\ -1 \\
0  &\ 2 &\ 6 \\
0 &\ 6 &\ 3 \\  
\end{pmatrix} \\
&= 
\begin{pmatrix}
1   &\ 0     &\ 0 \\
0   &\ 1     &\ 0 \\
0   &\ -3    &\ 1  \\  
\end{pmatrix} 
\begin{pmatrix}
1  &\ 3 &\ -1 \\
2  &\ 8 &\ 4 \\
-1 &\ 3 &\ 4 \\  
\end{pmatrix} \\
&=
\begin{pmatrix}
1  &\ 3 &\ -1 \\
0  &\ 2 &\ 6 \\
0 &\ 0 &\ -15 \\  
\end{pmatrix} \\
U = A^{(n)} = A^{(3)} &= L^{(3)}L^{(2)}L^{(1)}A
=
\begin{pmatrix}
1  &\ 3 &\ -1 \\
0  &\ 2 &\ 6 \\
0 &\ 0 &\ -15 \\  
\end{pmatrix} \\
\\



\Rightarrow L = \left(L^{(3)}L^{(2)}L^{(1)}\right)^{-1} 
&= 
\begin{pmatrix}
1         &\ 0&\ 0\\
-l^{(1)}_{(2:1)}         &1 &\ 0 \\
-l^{(1)}_{(3:1)}         &\ -l^{(2)}_{(3:1)}  &\ 1 \\  
\end{pmatrix}
= 
\begin{pmatrix}
1    &\ 0     &\ 0 \\
2   &\ 1    &\ 0 \\
-1    &\ 3     &\ 1  \\ 
\end{pmatrix} \\
\\
\Rightarrow A &= LU  
\end{split}
$$
