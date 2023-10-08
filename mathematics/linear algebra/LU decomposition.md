Note we will focus on a [[square matrix]] $A \in \mathbb{R}^{n \times n}$ but it's also possible for general [[matrix]] $A \in \mathbb{R}^{n \times m}$
## definition [[LU decomposition]]
A [[LU decomposition]] of $A \in \mathbb{R}^{n \times n}$ if a factorization in a normalized lower [[triangular matrix]] $L$ and an upper [[triangular matrix]] $U$ such that the following is true
$$
A = LU
$$

![[triangular matrix#normalized lower triangular matrix]]
![[triangular matrix#upper triangular matrix]]

## definition LDU decomposition
A LUD decomposition of $A \in \mathbb{R}^{n \times n}$ if a factorization in a normalized lower [[triangular matrix]] $L$ and a normalized upper [[triangular matrix]] $U$ and a [[diagonal matrix]] $D$ such that the following is true

$$
A = LDU
$$


![[triangular matrix#normalized lower triangular matrix]]
![[diagonal matrix#diagonal matrix]]
![[triangular matrix#normalized upper triangular matrix]]

## relationship between [[LU decomposition]] and LDU decomposition
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
# Anki

START
Basic
definition [[LU decomposition]]
Back: 
## definition [[LU decomposition]]
A [[LU decomposition]] of $A \in \mathbb{R}^{n \times n}$ if a factorization in a normalized lower [[triangular matrix]] $L$ and an upper [[triangular matrix]] $U$ such that the following is true
$$
A = LU
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


Tags: mathematics linear_algebra
<!--ID: 1696752218858-->
END

START
Basic
definition LDU decomposition
Back: 
## definition LDU decomposition
A LUD decomposition of $A \in \mathbb{R}^{n \times n}$ if a factorization in a normalized lower [[triangular matrix]] $L$ and a normalized upper [[triangular matrix]] $U$ and a [[diagonal matrix]] $D$ such that the following is true

$$
A = LDU
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
#### diagonal matrix
A [[matrix]] $D$ is a [[diagonal matrix]] when all values that are not on the diagonal are zero
$$
\begin{split}
D \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}}   & =  \left( d_{i, j}\right)_{i \in \mathcal{I}, j \in \mathcal{J}} \text{ with } \forall i \neq j : d_{ij} = 0 \\
\end{split}
$$
$$
\begin{split}
D = \begin{pmatrix}
d_{11}         &\ 0         &\ 0 \\
0         &\ d_{22}          &\ 0 \\
0         &\ 0         &\ d_{33}  \\  
\end{pmatrix}
\end{split}
$$
#### normalized upper triangular matrix 
A [[matrix]] $U$ is a upper [[triangular matrix]] if 
1) all values obove the diagonal line are zero $\forall i < j: a_{ij} = 0$ 
2) all values on the diagonal are one $\forall i: a_{ii} = 1$
$$
\begin{split}
U = \begin{pmatrix}
1         &\ u_{(1:2)} &\ u_{(1:3)} \\
0         &\ 1         &\ l_{(2:3)} \\
0         &\ 0         &\ 1 \\  
\end{pmatrix}
\end{split}
$$

Tags: mathematics linear_algebra
<!--ID: 1696752218865-->
END

START
Basic
relationship between [[LU decomposition]] and LDU decomposition
Back: 
## relationship between [[LU decomposition]] and LDU decomposition
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

## definition [[LU decomposition]]
A [[LU decomposition]] of $A \in \mathbb{R}^{n \times n}$ if a factorization in a normalized lower [[triangular matrix]] $L$ and an upper [[triangular matrix]] $U$ such that the following is true
$$
A = LU
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


## definition LDU decomposition
A LUD decomposition of $A \in \mathbb{R}^{n \times n}$ if a factorization in a normalized lower [[triangular matrix]] $L$ and a normalized upper [[triangular matrix]] $U$ and a [[diagonal matrix]] $D$ such that the following is true

$$
A = LDU
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
#### diagonal matrix
A [[matrix]] $D$ is a [[diagonal matrix]] when all values that are not on the diagonal are zero
$$
\begin{split}
D \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}}   & =  \left( d_{i, j}\right)_{i \in \mathcal{I}, j \in \mathcal{J}} \text{ with } \forall i \neq j : d_{ij} = 0 \\
\end{split}
$$
$$
\begin{split}
D = \begin{pmatrix}
d_{11}         &\ 0         &\ 0 \\
0         &\ d_{22}          &\ 0 \\
0         &\ 0         &\ d_{33}  \\  
\end{pmatrix}
\end{split}
$$
Tags: mathematics linear_algebra
<!--ID: 1696752218870-->
END