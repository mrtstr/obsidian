Note we will focus on a [[square matrix]] $A \in \mathbb{R}^{n \times n}$ but it's also possible for general [[matrix]] $A \in \mathbb{R}^{n \times m}$
## [[LU decomposition]] without [[permutations]]
### definition [[LU decomposition]]
A [[LU decomposition]] of $A \in \mathbb{R}^{n \times n}$ if a factorization in a normalized lower [[triangular matrix]] $L$ and an upper [[triangular matrix]] $U$ such that the following is true
$$
A = LU
$$

![[triangular matrix#normalized lower triangular matrix]]
![[triangular matrix#upper triangular matrix]]


### existence
- not every $A \in \mathbb{R}^{n \times n}$ has a [[LU decomposition]]

### uniqueness
- when $A \in \mathbb{R}^{n \times m}$ has a LUD decomposition its unique
- when $A \in \mathbb{R}^{n \times n}$ has a LU decomposition its unique

### process [[LU decomposition]]

![[triangular matrix#inverse matrix inverse of a normalized triangular matrix]]

![[triangular matrix#matrix product multiplication of normalized triangular matrix]]

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
### example [[LU decomposition]]

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



## LDU decomposition
### definition LDU decomposition
A LUD decomposition of $A \in \mathbb{R}^{n \times n}$ if a factorization in a normalized lower [[triangular matrix]] $L$ and a normalized upper [[triangular matrix]] $U$ and a [[diagonal matrix]] $D$ such that the following is true

$$
A = LDU
$$


![[triangular matrix#normalized lower triangular matrix]]
![[diagonal matrix#diagonal matrix]]
![[triangular matrix#normalized upper triangular matrix]]

### relationship between [[LU decomposition]] and LDU decomposition
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

### existence

### uniqueness
- when $A \in \mathbb{R}^{n \times m}$ has a LUD decomposition its unique
- when $A \in \mathbb{R}^{n \times n}$ has a LU decomposition its unique





## [[LU decomposition]] with [[permutations]]

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



START
Basic
[[LU decomposition]] without [[permutations]]: process with proofs
Back: 

### process [[LU decomposition]]


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

### given
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
### example [[LU decomposition]]

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

Tags: mathematics linear_algebra
<!--ID: 1697283008842-->
END


START
Basic
[[LU decomposition]] without [[permutations]] of the following [[matrix]]
$$

A  = \begin{pmatrix}
1  &\ 3 &\ -1 \\
2  &\ 8 &\ 4 \\
-1 &\ 3 &\ 4 \\  
\end{pmatrix} \\

$$

Back: 

### example [[LU decomposition]]

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

### process [[LU decomposition]]


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

### given
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

Tags: mathematics linear_algebra
<!--ID: 1697283008845-->
END