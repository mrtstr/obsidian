## definition [[cholesky decomposition]]

Decompostion of a [[square matrix|square]] [[symmetric matrix|symmetric]] [[matrix]] $A$ in the [[matrix product]] of a lower [[triangular matrix]] $L$ and its [[transpose]].

$$
A = LL^T
$$

### existence [[cholesky decomposition]]
When $A$ is a [[LU decomposition|LU decomposition]] and is a [[symmetric matrix]] it also has a [[cholesky decomposition]]

$$
\begin{split}
A 
&= LU \\
&= LD\hat{U} \\
\Rightarrow A^T 
&= A = \left(LD\hat{U}\right)^T  \text{(symmetry)}\\
&=  \hat{U}^TD^TL^T = \hat{U}^TDL^T \\
\Rightarrow \hat{U} &= L^T \text{(uniqueness)} \\
\Rightarrow A &= LDL^T  \\
A &= LD^{\frac{1}{2}}D^{\frac{1}{2}}L^T  \\
&= \hat{L}\hat{L}^T \text{   with   } \hat{L}=LD^{\frac{1}{2}} \\
\end{split}
$$

### [[time complexity]] of the [[cholesky decomposition]]
- its $\frac{1}{6}n^3 \in \mathcal{O}(n^3)$ so it's 4 times faster than the [[LU decomposition]]


### example [[LU decomposition]] to [[cholesky decomposition]]

- given the following [[LU decomposition]]
$$
\begin{split}
A &=
\begin{pmatrix}
16  &\ -8 &\ 12 \\
-8  &\ 8 &\ 4 \\
12 &\ 4 &\ 35 \\  
\end{pmatrix} \\
&= LU \\
&=
\begin{pmatrix}
1  &\ 0 &\ 0 \\
\frac{1}{2}  &\ 1 &\ 0 \\
\frac{3}{4} &\ -\frac{5}{2} &\ 1 \\  
\end{pmatrix} 
\begin{pmatrix}
16  &\ -8 &\ 12 \\
0  &\ 4 &\ 10 \\
0 &\ 0 &\ 1 \\  
\end{pmatrix}
\end{split}
$$
- since $A$ is a [[symmetric matrix]] it has to have unique decomposition that $A= LDL^\top$ and a unique [[cholesky decomposition]] that $A= GG^\top$
$$
\begin{split}
A
&= LU \\
&= LDL^\top \\
D&=
\begin{pmatrix}
16  &\ 0 &\ 0 \\
0  &\ 4 &\ 0 \\
0 &\ 0 &\ 1 \\  
\end{pmatrix} \\
G&= LD^{\frac{1}{2}}
\begin{pmatrix}
1  &\ 0 &\ 0 \\
-\frac{1}{2}  &\ 1 &\ 0 \\
\frac{3}{4} &\ \frac{5}{2} &\ 1 \\  
\end{pmatrix} 
\begin{pmatrix}
4  &\ 0 &\ 0 \\
0  &\ 2 &\ 0 \\
0 &\ 0 &\ 1 \\  
\end{pmatrix} 
=\begin{pmatrix}
4  &\ 0 &\ 0 \\
-2  &\ 2 &\ 0 \\
3 &\ 5 &\ 1 \\  
\end{pmatrix} \\
A &=\begin{pmatrix}
4  &\  &\  \\
-2  &\ 2 &\  \\
3 &\ 5 &\ 1 \\  
\end{pmatrix} \begin{pmatrix}
4  &\ -2 &\ 3 \\
  &\ 2 &\ 5 \\
 &\  &\ 1 \\  
\end{pmatrix} 
=\begin{pmatrix}
16  &\ -8 &\ 12 \\
-8  &\ 8 &\ 4 \\
12 &\ 4 &\ 35 \\  
\end{pmatrix}
\end{split}
$$

# ----------------------------

![[triangular matrix#lower triangular matrix]]

![[symmetric matrix#Definition]]

![[LDU decomposition#definition LDU decomposition]]

![[LU decomposition#LU decomposition]]

![[LDU decomposition#relationship between LU decomposition and LDU decomposition]]

# anki

START
Basic
[[cholesky decomposition]]
- defintion
- existance with proof
- [[time complexity]]

Back: 
## definition [[cholesky decomposition]]

Decompostion of a [[square matrix|square]] [[symmetric matrix|symmetric]] [[matrix]] $A$ in the [[matrix product]] of a lower [[triangular matrix]] $L$ and its [[transpose]].

$$
A = LL^T
$$
## existence
When $A$ is a [[LU decomposition|LU decomposition]] and is a [[symmetric matrix]] it also has a [[cholesky decomposition]]

$$
\begin{split}
A 
&= LU \\
&= LD\hat{U} \\
\Rightarrow A^T 
&= A = \left(LD\hat{U}\right)^T  \text{(symmetry)}\\
&=  \hat{U}^TD^TL^T = \hat{U}^TDL^T \\
\Rightarrow \hat{U} &= L^T \text{(uniqueness)} \\
\Rightarrow A &= LDL^T  \\
A &= LD^{\frac{1}{2}}D^{\frac{1}{2}}L^T  \\
&= \hat{L}\hat{L}^T \text{   with   } \hat{L}=LD^{\frac{1}{2}} \\
\end{split}
$$

## [[time complexity]] of the [[cholesky decomposition]]
- its $\frac{1}{6}n^3 \in \mathcal{O}(n^3)$ so it's 4 times faster than the [[LU decomposition]]

## requirements
#### lower triangular matrix 
A [[matrix]] $L$ is a lower [[triangular matrix]] if all values obove the diagonal line are zero $\forall i < j: a_{ij} = 0$ 

$$
\begin{split}
L = \begin{pmatrix}
l_{(1:1)} &\ 0 &\ 0 \\
l_{(2:1)} &\ l_{(2:2)} &\ 0 \\
l_{(3:1)} &\ l_{(3:2)} &\ l_{(3:3)} \\  
\end{pmatrix}
\end{split}
$$

#### square matrix definition
$$
\begin{split}
A  \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{I} \right|}} 
&= \left(a_{i,j} \right)_{i \in \mathcal{I}, j \in \mathcal{I}} \\
&= \left(A^{(j)} \right)_{j \in \mathcal{I}}
= 
\begin{pmatrix}   A^{(1)} &   ... & A^{(\left| \mathcal{I} \right|)}  \end{pmatrix}\\
&= \left(A_{(i)} \right)_{i \in \mathcal{I}}
=  
\begin{pmatrix}   A_{(1)} \\   ... \\ A_{(\left| \mathcal{I} \right|)}   \end{pmatrix}
\end{split}
$$


#### definition LDU decomposition
A LUD decomposition of $A \in \mathbb{R}^{n \times n}$ if a factorization in a normalized lower [[triangular matrix]] $L$ and a normalized upper [[triangular matrix]] $U$ and a [[diagonal matrix]] $D$ such that the following is true

$$
A = LDU
$$


#### definition [[LU decomposition]]
A [[LU decomposition]] of $A \in \mathbb{R}^{n \times n}$ if a factorization in a normalized lower [[triangular matrix]] $L$ and an upper [[triangular matrix]] $U$ such that the following is true
$$
A = LU
$$

The [[LU decomposition]] can be derrived from the LDU decomposition and vide versa because the [[matrix product]] of a normalized triangular matrix and a [[diagonal matrix]] is a [[triangular matrix]] with the values $\{d_{11}, ..., d_{nn}\}$ on its diagonal instead of ones

$$
A = L(DU) = L\tilde{U}
$$

$$
\begin{split}
U &= \begin{pmatrix}
1         &\ u_{(1:2)} &\ u_{(1:3)} \\
0         &\ 1         &\ l_{(2:3)} \\
0         &\ 0         &\ 1 \\  
\end{pmatrix} \\
D &= \begin{pmatrix}
d_{11}         &\ 0         &\ 0 \\
0         &\ d_{22}          &\ 0 \\
0         &\ 0         &\ d_{33}  \\  
\end{pmatrix} \\
\tilde{U} &= DU = \begin{pmatrix}
d_{11}         &\ u_{(1:2)} &\ u_{(1:3)} \\
0         &\ d_{22}         &\ l_{(2:3)} \\
0         &\ 0         &\ d_{33} \\  
\end{pmatrix}

\end{split}
$$


Tags: mathematics linear_algebra
<!--ID: 1697968223644-->
END



START
Basic

- given the following [[LU decomposition]]
- calculate the [[cholesky decomposition]] of $A$
$$
\begin{split}
A &=
\begin{pmatrix}
16  &\ -8 &\ 12 \\
-8  &\ 8 &\ 4 \\
12 &\ 4 &\ 35 \\  
\end{pmatrix} \\
&= LU \\
&=
\begin{pmatrix}
1  &\ 0 &\ 0 \\
-\frac{1}{2}  &\ 1 &\ 0 \\
\frac{3}{4} &\ \frac{5}{2} &\ 1 \\  
\end{pmatrix} 
\begin{pmatrix}
16  &\ -8 &\ 12 \\
0  &\ 4 &\ 10 \\
0 &\ 0 &\ 1 \\  
\end{pmatrix}
\end{split}
$$

Back: 
### example [[LU decomposition]] to [[cholesky decomposition]]


- since $A$ is a [[symmetric matrix]] it has to have unique decomposition that $A= LDL^\top$ and a unique [[cholesky decomposition]] that $A= GG^\top$

$$
\begin{split}
A
&= LU \\
&= LDL^\top \\
D&=
\begin{pmatrix}
16  &\ 0 &\ 0 \\
0  &\ 4 &\ 0 \\
0 &\ 0 &\ 1 \\  
\end{pmatrix} \\
G&= LD^{\frac{1}{2}}
\begin{pmatrix}
1  &\ 0 &\ 0 \\
-\frac{1}{2}  &\ 1 &\ 0 \\
\frac{3}{4} &\ \frac{5}{2} &\ 1 \\  
\end{pmatrix} 
\begin{pmatrix}
4  &\ 0 &\ 0 \\
0  &\ 2 &\ 0 \\
0 &\ 0 &\ 1 \\  
\end{pmatrix} 
=\begin{pmatrix}
4  &\ 0 &\ 0 \\
-2  &\ 2 &\ 0 \\
3 &\ 5 &\ 1 \\  
\end{pmatrix} \\
A &=\begin{pmatrix}
4  &\  &\  \\
-2  &\ 2 &\  \\
3 &\ 5 &\ 1 \\  
\end{pmatrix} \begin{pmatrix}
4  &\ -2 &\ 3 \\
  &\ 2 &\ 5 \\
 &\  &\ 1 \\  
\end{pmatrix} 
=\begin{pmatrix}
16  &\ -8 &\ 12 \\
-8  &\ 8 &\ 4 \\
12 &\ 4 &\ 35 \\  
\end{pmatrix}
\end{split}
$$

_____________________

### cholesky decomposition

Decompostion of a [[square matrix|square]] [[symmetric matrix|symmetric]] [[matrix]] $A$ in the [[matrix product]] of a lower [[triangular matrix]] $L$ and its [[transpose]].

$$
A = LL^T
$$

When $A$ is a [[LU decomposition|LU decomposition]] and is a [[symmetric matrix]] it also has a [[cholesky decomposition]]

$$
\begin{split}
A 
&= LU \\
&= LD\hat{U} \\
\Rightarrow A^T 
&= A = \left(LD\hat{U}\right)^T  \text{(symmetry)}\\
&=  \hat{U}^TD^TL^T = \hat{U}^TDL^T \\
\Rightarrow \hat{U} &= L^T \text{(uniqueness)} \\
\Rightarrow A &= LDL^T  \\
A &= LD^{\frac{1}{2}}D^{\frac{1}{2}}L^T  \\
&= \hat{L}\hat{L}^T \text{   with   } \hat{L}=LD^{\frac{1}{2}} \\
\end{split}
$$


#### LDU decomposition
A LUD decomposition of $A \in \mathbb{R}^{n \times n}$ if a factorization in a normalized lower [[triangular matrix]] $L$ and a normalized upper [[triangular matrix]] $U$ and a [[diagonal matrix]] $D$ such that the following is true

$$
A = LDU
$$


#### [[LU decomposition]]
A [[LU decomposition]] of $A \in \mathbb{R}^{n \times n}$ if a factorization in a normalized lower [[triangular matrix]] $L$ and an upper [[triangular matrix]] $U$ such that the following is true
$$
A = LU
$$

The [[LU decomposition]] can be derrived from the LDU decomposition and vide versa because the [[matrix product]] of a normalized triangular matrix and a [[diagonal matrix]] is a [[triangular matrix]] with the values $\{d_{11}, ..., d_{nn}\}$ on its diagonal instead of ones

$$
A = L(DU) = L\tilde{U}
$$

$$
\begin{split}
U &= \begin{pmatrix}
1         &\ u_{(1:2)} &\ u_{(1:3)} \\
0         &\ 1         &\ l_{(2:3)} \\
0         &\ 0         &\ 1 \\  
\end{pmatrix} \\
D &= \begin{pmatrix}
d_{11}         &\ 0         &\ 0 \\
0         &\ d_{22}          &\ 0 \\
0         &\ 0         &\ d_{33}  \\  
\end{pmatrix} \\
\tilde{U} &= DU = \begin{pmatrix}
d_{11}         &\ u_{(1:2)} &\ u_{(1:3)} \\
0         &\ d_{22}         &\ l_{(2:3)} \\
0         &\ 0         &\ d_{33} \\  
\end{pmatrix}

\end{split}
$$


Tags: mathematics linear_algebra
<!--ID: 1722006505947-->
END