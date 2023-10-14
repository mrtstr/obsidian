# triangular matrix
## lower triangular matrix 
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
## upper triangular matrix 
A [[matrix]] $U$ is an upper [[triangular matrix]] if all values obove the diagonal line are zero $\forall i < j: a_{ij} = 0$ 
$$
\begin{split}
U = \begin{pmatrix}
u_{(1:1)} &\ u_{(1:2)} &\ u_{(1:3)} \\
0         &\ u_{(2:2)} &\ l_{(2:3)} \\
0         &\ 0         &\ u_{(3:3)} \\  
\end{pmatrix}
\end{split}
$$


## properties
### [[matrix product]] of [[triangular matrix|matrices]] 
- if $L_1$ and $L_2$ are lower triangular matrices the product of  $L_1$ and $L_2$ is also a lower triangular matrix $L_1L2 = L_3$
- if $U_1$ and $U_2$ are upper triangular matrices the product of  $U_1$ and $U_2$ is also a lower upper matrix $U_1U2 = U_3$
#### [[determinant]] of a [[triangular matrix]]
the [[determinant]] of a [[triangular matrix]] is equal to the product of its diagonal element
$$
\begin{split}
det(L) = \prod_{i=1}^n l_{ii} \\
det(U) = \prod_{i=1}^n u_{ii} \\
\end{split}
$$
#### [[inverse matrix]] of a [[triangular matrix]]
- [[inverse matrix]] of an upper [[triangular matrix]] is an upper [[triangular matrix]] 
- [[inverse matrix]] of a lower [[triangular matrix]] is a lower [[triangular matrix]] 

# normalized triangular matrix
## normalized lower triangular matrix 
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
## normalized upper triangular matrix 
A [[matrix]] $U$ is an upper [[triangular matrix]] if 
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
## properties

### [[determinant]] of a normalized [[triangular matrix]]
the [[determinant]] of a  normalized[[triangular matrix]] is equal to the product of its diagonal element which are all one
$$
\begin{split}
det(L) = \prod_{i=1}^n l_{ii} = 1\\
det(U) = \prod_{i=1}^n u_{ii} = 1 \\
\end{split}
$$
### [[inverse matrix|inverse]] of a normalized [[triangular matrix]]
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
### [[matrix product|multiplication]] of normalized [[triangular matrix]]
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

# Anki

START
Basic
[[matrix product|multiplication]] of normalized [[triangular matrix]]
Back: 
### [[matrix product|multiplication]] of normalized [[triangular matrix]]
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

### normalized lower triangular matrix 
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

### normalized upper triangular matrix 
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
<!--ID: 1697283008830-->
END

START
Basic
[[inverse matrix|inverse]] of a normalized [[triangular matrix]]
Back: 
### [[inverse matrix|inverse]] of a normalized [[triangular matrix]]

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

### normalized lower triangular matrix 
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

### normalized upper triangular matrix 
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
<!--ID: 1697283008835-->
END

START
Basic
[[triangular matrix]]
- definition of 2 different kinds
- properties (3)
Back: 

## lower triangular matrix 
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
## upper triangular matrix 
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


## properties
### [[matrix product]] of [[triangular matrix|matrices]] 
- if $L_1$ and $L_2$ are lower triangular matrices the product of  $L_1$ and $L_2$ is also a lower triangular matrix $L_1L2 = L_3$
- if $U_1$ and $U_2$ are upper triangular matrices the product of  $U_1$ and $U_2$ is also a lower upper matrix $U_1U2 = U_3$
#### [[determinant]] of a [[triangular matrix]]
the [[determinant]] of a [[triangular matrix]] is equal to the product of its diagonal element
$$
\begin{split}
det(L) = \prod_{i=1}^n l_{ii} \\
det(U) = \prod_{i=1}^n u_{ii} \\
\end{split}
$$
#### [[inverse matrix]] of a [[triangular matrix]]
- [[inverse matrix]] of a upper [[triangular matrix]] is a upper [[triangular matrix]] 
- [[inverse matrix]] of a lower [[triangular matrix]] is a lower [[triangular matrix]] 


Tags: mathematics linear_algebra
<!--ID: 1696746884818-->
END


START
Basic
normalized [[triangular matrix]]
- definition of 2 different kinds
- properties (3)
Back: 

## normalized lower triangular matrix 
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
## normalized upper triangular matrix 
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
## properties

### [[determinant]] of a normalized [[triangular matrix]]
the [[determinant]] of a  normalized[[triangular matrix]] is equal to the product of its diagonal element which are all one
$$
\begin{split}
det(L) = \prod_{i=1}^n l_{ii} = 1\\
det(U) = \prod_{i=1}^n u_{ii} = 1 \\
\end{split}
$$
### [[inverse matrix|inverse]] of a normalized [[triangular matrix]]
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
### [[matrix product|multiplication]] of normalized [[triangular matrix]]
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
<!--ID: 1697283008839-->
END