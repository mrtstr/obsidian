### determinant
- let $A \in \mathbb{R}^{n \times n}$ be a [[square matrix]] 
- its [[determinant]] $\det(A)$ is defined as follows
$$
\det(A) = 
\left\{
\begin{matrix}
a_{11} \qquad &n=1 \\
\sum_{j \in [n]} a_{1j}(-1)^{i+j}\det(M_{ij}) \qquad &n>1   \\
\end{matrix}
\right.
$$

![[minor#minor]]

![[det.png]]

### sarrus rule
- for calculation a [[determinant]] of [[matrix]] from $\mathbb{R}^{2 \times 2}$ and $\mathbb{R}^{3 \times 3}$
#### [[determinant]] of $A \in \mathbb{R}^{2 \times 2}$
$$
\begin{split}
A 
&= \det
\left(\begin{matrix}
a_{11} \ a_{21} \\ 
a_{12} \ a_{22}
\end{matrix}\right)
\\
&= a_{11}a_{22}-a_{12}a_{21}
\end{split}
$$
#### [[determinant]] of $A \in \mathbb{R}^{3 \times 3}$

![[Sarrus_rule1.svg.png]]

# ----------------------
![[square matrix#square matrix]]

### properties
#### [[determinant]] of the [[inverse matrix]]
- the [[determinant]] of a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is equal to the [[determinant]] of its [[inverse matrix]] to the power of $-1$
$$
\det(A)^{-1} = \det\left(A^{-1}\right)
$$

#### [[determinant]] of the [[transpose]]
- the [[determinant]] of a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is equal to the [[determinant]] of its [[transpose]] 
$$
\det(A) = \det\left(A^{T}\right)
$$

![[columnspace and rowspace dimensions are equal#the column space has the same number of dimensions as the row space]]

#### [[determinant]] of a [[regular matrix]]
- if the [[determinant]] of a [[square matrix]] $A \in \mathbb{R}^{n \times n}$ is not zero it is [[inverse matrix|invertable]] and a [[regular matrix]]

![[regular matrix#regular matrix]]



- the [[determinant]] of a [[matrix]] $A \in \mathbb{R}^{n \times n}$ multipled with a scalar
$$
\det(k \cdot A) = k^n \det\left(A\right)
$$

- the [[determinant]] of a [[matrix product]] of a [[matrix]] $A \in \mathbb{R}^{n \times n}$ and [[matrix]] $B \in \mathbb{R}^{n \times n}$ 
$$
\det(AB) = \det(A)\det(B)
$$


Die **Determinante** einer Matrix ist genau dann **gleich Null**, wenn 

-   eine Zeile/Spalte **nur Nullen** enthält, oder
-   zwei Zeilen/Spalten **gleich** sind, oder
-   Zeilen/Spalten zusammen das **Vielfache (eine Linearkombination)** von anderen Zeilen/Spalten sind.


### interpretation
- given a geometry $\in \mathbb{R}^n$ defined by its $n$ corners as [[vector|vectors]] $v_1,..., v_n \in \mathbb{R}^n$
- the volumen of the geometry is $u$
- after transforming $v_1,..., v_n \in \mathbb{R}^n$ with the [[linear function]] $f(x)=Ax$ the volumen of geometry defined by the vectors $v_i'=Av_i$ will be $u'=\det(A)u$ 
$$
\begin{split}
V 
&= 
\left(\begin{matrix}
v_1 \\ 
... \\ 
v_n
\end{matrix}\right)
\\
V' 
&= 
\left(\begin{matrix}
v_1' \\ 
... \\ 
v_n'
\end{matrix}\right)
&= AV \\
vol(V') &= vol(V) \det(A)
\end{split}
$$
# anki
START
Basic
- definition [[determinant]]
Back: 
### determinant
- let $A \in \mathbb{R}^{n \times n}$ be a [[square matrix]] 
- its [[determinant]] $\det(A)$ is defined as follows
$$
\det(A) = 
\left\{
\begin{matrix}
a_{11} \qquad &n=1 \\
\sum_{j \in [n]} a_{1j}(-1)^{i+j}\det(M_{ij}) \qquad &n>1   \\
\end{matrix}
\right.
$$

### minor
- [[determinant]] of a smaller [[square matrix]] cut out from another [[square matrix]] by removing one or more columns and rows
- $M_{ij}$ defined as the [[square matrix|square submatrix]] with column $i$ and row $j$ removed from another [[square matrix]] $A$ 
$$
\det(M_{ij}) = \det\left((a_{lk})_{l \in [n] \setminus \{i\}, k \in [n] \setminus \{j\}}\right)
$$

![[det 1.png]]
____________________

### matrix
$$
\begin{split}
A  \in \mathbb{R}^{n  \times m}
&= \left(a_{i,j} \right)_{i \in [n], j \in [m]} \\
&= \left(A_{(*:j)} \right)_{j \in [m]}
= 
\begin{pmatrix}   A_{(*:1)} &   ... & A_{(*:m}   \end{pmatrix}\\
&= \left(A_{(i:*)} \right)_{i \in [n]}
=  
\begin{pmatrix}   A_{(1:*)} \\   ... \\ A_{(n:*)}   \end{pmatrix}
\end{split}
$$
Tags: mathematics
<!--ID: 1713099059611-->
END


START
Basic
how to calculate the [[determinant]] of a [[matrix]]?
Back: 
### $n>3$: develop after a column

![[det 2.png]]

### sarrus rule
- for calculation a [[determinant]] of [[matrix]] from $\mathbb{R}^{2 \times 2}$ and $\mathbb{R}^{3 \times 3}$
#### [[determinant]] of $A \in \mathbb{R}^{2 \times 2}$
$$
\begin{split}
A 
&= \det
\left(\begin{matrix}
a_{11} \ a_{21} \\ 
a_{12} \ a_{22}
\end{matrix}\right)
\\
&= a_{11}a_{22}-a_{12}a_{21}
\end{split}
$$
#### [[determinant]] of $A \in \mathbb{R}^{3 \times 3}$

![[Sarrus_rule1.svg 1.png]]

____________________
### determinant
- let $A \in \mathbb{R}^{n \times n}$ be a [[square matrix]] 
- its [[determinant]] $\det(A)$ is defined as follows
$$
\det(A) = 
\left\{
\begin{matrix}
a_{11} \qquad &n=1 \\
\sum_{j \in [n]} a_{1j}(-1)^{i+j}\det(M_{ij}) \qquad &n>1   \\
\end{matrix}
\right.
$$

### minor
- [[determinant]] of a smaller [[square matrix]] cut out from another [[square matrix]] by removing one or more columns and rows
- $M_{ij}$ defined as the [[square matrix|square submatrix]] with column $i$ and row $j$ removed from another [[square matrix]] $A$ 
$$
\det(M_{ij}) = \det\left((a_{lk})_{l \in [n] \setminus \{i\}, k \in [n] \setminus \{j\}}\right)
$$



### matrix
$$
\begin{split}
A  \in \mathbb{R}^{n  \times m}
&= \left(a_{i,j} \right)_{i \in [n], j \in [m]} \\
&= \left(A_{(*:j)} \right)_{j \in [m]}
= 
\begin{pmatrix}   A_{(*:1)} &   ... & A_{(*:m}   \end{pmatrix}\\
&= \left(A_{(i:*)} \right)_{i \in [n]}
=  
\begin{pmatrix}   A_{(1:*)} \\   ... \\ A_{(n:*)}   \end{pmatrix}
\end{split}
$$
Tags: mathematics
<!--ID: 1713099059617-->
END


START
Basic
[[determinant]] properties
- [[regular matrix]]
- [[transpose]] [[matrix]]
- [[inverse matrix]]
- [[matrix]] multiplied with a scalar
- [[matrix product]] of [[matrix|matrices]]

Back: 
- if the [[determinant]] of a [[square matrix]] $A \in \mathbb{R}^{n \times n}$ is not zero it is [[inverse matrix|invertable]] and a [[regular matrix]]



- the [[determinant]] of a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is equal to the [[determinant]] of its [[transpose]] 
$$
\det(A) = \det\left(A^{T}\right)
$$

- the [[determinant]] of a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is equal to the [[determinant]] of its [[inverse matrix]] to the power of $-1$
$$
\det(A)^{-1} = \det\left(A^{-1}\right)
$$

- the [[determinant]] of a [[matrix]] $A \in \mathbb{R}^{n \times n}$ multipled with a scalar
$$
\det(k \cdot A) = k^n \det\left(A\right)
$$

- the [[determinant]] of a [[matrix product]] of a [[matrix]] $A \in \mathbb{R}^{n \times n}$ and [[matrix]] $B \in \mathbb{R}^{n \times n}$ 
$$
\det(AB) = \det(A)\det(B)
$$


____________________

#### regular matrix
a [[square matrix]] $A \in \mathbb{R}^{n \times n}$ is a [[regular matrix]] when the following equivalent properties are true
1) $\exists B \in \mathbb{R}^{n \times n} \quad with \: AB=BA=I$ ($A$ has an [[inverse matrix]])
2) $\exists B \in \mathbb{R}^{n \times n} \quad with \: A^\top B=BA^\top=I$ (the [[transpose]] of $A$ has an [[inverse matrix]])
3) $rank(A)=n$ ($A$ has a full [[rank]])
4) $det(A) \neq 0$ ($A$ has a [[determinant]] that is not zero)
5) $Ax=0 \Rightarrow x=0$
6) $\left\{ A^{(i)}\right\}_{i \in \mathcal{I}}$ are [[linear independent]]  
7) $\left\{ A_{(j)}\right\}_{j \in \mathcal{J}}$ are [[linear independent]] 


#### determinant
- let $A \in \mathbb{R}^{n \times n}$ be a [[square matrix]] 
- its [[determinant]] $\det(A)$ is defined as follows
$$
\det(A) = 
\left\{
\begin{matrix}
a_{11} \qquad &n=1 \\
\sum_{j \in [n]} a_{1j}(-1)^{i+j}\det(M_{ij}) \qquad &n>1   \\
\end{matrix}
\right.
$$

#### minor
- [[determinant]] of a smaller [[square matrix]] cut out from another [[square matrix]] by removing one or more columns and rows
- $M_{ij}$ defined as the [[square matrix|square submatrix]] with column $i$ and row $j$ removed from another [[square matrix]] $A$ 
$$
\det(M_{ij}) = \det\left((a_{lk})_{l \in [n] \setminus \{i\}, k \in [n] \setminus \{j\}}\right)
$$


#### matrix
$$
\begin{split}
A  \in \mathbb{R}^{n  \times m}
&= \left(a_{i,j} \right)_{i \in [n], j \in [m]} \\
&= \left(A_{(*:j)} \right)_{j \in [m]}
= 
\begin{pmatrix}   A_{(*:1)} &   ... & A_{(*:m}   \end{pmatrix}\\
&= \left(A_{(i:*)} \right)_{i \in [n]}
=  
\begin{pmatrix}   A_{(1:*)} \\   ... \\ A_{(n:*)}   \end{pmatrix}
\end{split}
$$
Tags: mathematics
<!--ID: 1713099059620-->
END


START
Basic
[[determinant]] geometric interpretation

Back: 
### interpretation
- given a geometry $\in \mathbb{R}^n$ defined by its $n$ corners as [[vector|vectors]] $v_1,..., v_n \in \mathbb{R}^n$
- the volumen of the geometry is $u$
- after transforming $v_1,..., v_n \in \mathbb{R}^n$ with the [[linear function]] $f(x)=Ax$ the volumen of geometry defined by the vectors $v_i'=Av_i$ will be $u'=\det(A)u$ 

$$
\begin{split}
V 
&= 
\left(\begin{matrix}
v_1 \\ 
... \\ 
v_n
\end{matrix}\right)
\\
V' 
&= 
\left(\begin{matrix}
v_1' \\ 
... \\ 
v_n'
\end{matrix}\right)
&= AV \\
vol(V') &= vol(V) \det(A)
\end{split}
$$

____________________

#### regular matrix
a [[square matrix]] $A \in \mathbb{R}^{n \times n}$ is a [[regular matrix]] when the following equivalent properties are true
1) $\exists B \in \mathbb{R}^{n \times n} \quad with \: AB=BA=I$ ($A$ has an [[inverse matrix]])
2) $\exists B \in \mathbb{R}^{n \times n} \quad with \: A^\top B=BA^\top=I$ (the [[transpose]] of $A$ has an [[inverse matrix]])
3) $rank(A)=n$ ($A$ has a full [[rank]])
4) $det(A) \neq 0$ ($A$ has a [[determinant]] that is not zero)
5) $Ax=0 \Rightarrow x=0$
6) $\left\{ A^{(i)}\right\}_{i \in \mathcal{I}}$ are [[linear independent]]  
7) $\left\{ A_{(j)}\right\}_{j \in \mathcal{J}}$ are [[linear independent]] 


#### determinant
- let $A \in \mathbb{R}^{n \times n}$ be a [[square matrix]] 
- its [[determinant]] $\det(A)$ is defined as follows
$$
\det(A) = 
\left\{
\begin{matrix}
a_{11} \qquad &n=1 \\
\sum_{j \in [n]} a_{1j}(-1)^{i+j}\det(M_{ij}) \qquad &n>1   \\
\end{matrix}
\right.
$$

#### minor
- [[determinant]] of a smaller [[square matrix]] cut out from another [[square matrix]] by removing one or more columns and rows
- $M_{ij}$ defined as the [[square matrix|square submatrix]] with column $i$ and row $j$ removed from another [[square matrix]] $A$ 
$$
\det(M_{ij}) = \det\left((a_{lk})_{l \in [n] \setminus \{i\}, k \in [n] \setminus \{j\}}\right)
$$


#### matrix
$$
\begin{split}
A  \in \mathbb{R}^{n  \times m}
&= \left(a_{i,j} \right)_{i \in [n], j \in [m]} \\
&= \left(A_{(*:j)} \right)_{j \in [m]}
= 
\begin{pmatrix}   A_{(*:1)} &   ... & A_{(*:m}   \end{pmatrix}\\
&= \left(A_{(i:*)} \right)_{i \in [n]}
=  
\begin{pmatrix}   A_{(1:*)} \\   ... \\ A_{(n:*)}   \end{pmatrix}
\end{split}
$$
Tags: mathematics
<!--ID: 1713099059623-->
END


