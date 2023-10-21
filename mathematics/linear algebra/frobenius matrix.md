## Definition frobenius matrix
A frobenius [[matrix]] is a special form of lower normalized [[triangular matrix]] with the additional propertie that only one column can have non-zero entries below the diagonal 

![[triangular matrix#normalized lower triangular matrix]]

### examples
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

## swiching elements of [[frobenius matrix]] with [[permutation matrix|permutation matrices]]

![[permutation matrix#permutation matrix swaping rows and columns]]

- $P_{ij} F P^T_{ij}$ with $i < j$ is again a [[frobenius matrix]] with the potentially non-zero elements $i$ and $j$ swiched
### example
$$
\begin{split}
P_{xy} F P^T_{xy} 
&= 
\begin{pmatrix}
1 &\ 0 &\ 0 \\
0 &\ 0 &\ 1 \\
0 &\ 1 &\ 0 \\  
\end{pmatrix}
\begin{pmatrix}
1         &\ 0         &\ 0 \\
f_{(2:1)} &\ 1         &\ 0 \\
f_{(3:1)} &\ 0 &\ 1 \\  
\end{pmatrix} 
\begin{pmatrix}
1 &\ 0 &\ 0 \\
0 &\ 0 &\ 1 \\
0 &\ 1 &\ 0 \\  
\end{pmatrix} \\
&= 
\begin{pmatrix}
1         &\ 0 &\ 0 \\
f_{(3:1)} &\ 0 &\ 1 \\
f_{(2:1)} &\ 1 &\ 0 \\  
\end{pmatrix} 
\begin{pmatrix}
1 &\ 0 &\ 0 \\
0 &\ 0 &\ 1 \\
0 &\ 1 &\ 0 \\  
\end{pmatrix} \\
&= 
\begin{pmatrix}
1         &\ 0         &\ 0 \\
f_{(3:1)} &\ 1         &\ 0 \\
f_{(2:1)} &\ 0 &\ 1 \\  
\end{pmatrix} 
\end{split}
$$

# Anki

START
Basic
definition [[frobenius matrix]]
Back: 
A frobenius [[matrix]] is a special form of lower normalized [[triangular matrix]] with the additional propertie that only one column can have non-zero entries below the diagonal 

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

Tags: mathematics linear_algebra
<!--ID: 1697359286531-->
END


START
Basic
swiching elements of a [[frobenius matrix]] with [[permutation matrix|permutation matrices]]
with example for 
$$
\begin{pmatrix}
1         &\ 0         &\ 0 \\
f_{(2:1)} &\ 1         &\ 0 \\
f_{(3:1)} &\ 0 &\ 1 \\  
\end{pmatrix} 
$$
Back: 

- $P_{ij} F P^T_{ij}$ with $i < j$ is again a [[frobenius matrix]] with the potentially non-zero elements $i$ and $j$ swiched
### example
$$
\begin{split}
P_{xy} F P_{xy} 
&= 
\begin{pmatrix}
1 &\ 0 &\ 0 \\
0 &\ 0 &\ 1 \\
0 &\ 1 &\ 0 \\  
\end{pmatrix}
\begin{pmatrix}
1         &\ 0         &\ 0 \\
f_{(2:1)} &\ 1         &\ 0 \\
f_{(3:1)} &\ 0 &\ 1 \\  
\end{pmatrix} 
\begin{pmatrix}
1 &\ 0 &\ 0 \\
0 &\ 0 &\ 1 \\
0 &\ 1 &\ 0 \\  
\end{pmatrix} \\
&= 
\begin{pmatrix}
1         &\ 0 &\ 0 \\
f_{(3:1)} &\ 0 &\ 1 \\
f_{(2:1)} &\ 1 &\ 0 \\  
\end{pmatrix} 
\begin{pmatrix}
1 &\ 0 &\ 0 \\
0 &\ 0 &\ 1 \\
0 &\ 1 &\ 0 \\  
\end{pmatrix} \\
&= 
\begin{pmatrix}
1         &\ 0         &\ 0 \\
f_{(3:1)} &\ 1         &\ 0 \\
f_{(2:1)} &\ 0 &\ 1 \\  
\end{pmatrix} 
\end{split}
$$

### [[permutation matrix]] swaping rows and columns
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


### definition [[frobenius matrix]]
A frobenius [[matrix]] is a special form of lower normalized [[triangular matrix]] with the additional propertie that only one column can have non-zero entries below the diagonal 

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

Tags: mathematics linear_algebra
<!--ID: 1697359583180-->
END