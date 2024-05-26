## Definition [[permutation matrix]]
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
## [[inverse matrix|inverse]] of a [[permutation matrix]]

A [[permutation matrix]] is a [[orthogonal matrix]] thus its [[transpose]] is equal to its [[inverse matrix]]
![[orthogonal matrix]]

### proof
$$
\begin{split}
&PP^T = \left( \sum_{i=1}^n p_{i,k}p_{j,k} \right)_{1\leq i \leq n, 1\leq j \leq n} =\left( \mathbb{I}\left[i=j\right] \right)_{1\leq i \leq n, 1\leq j \leq n} = I  \\ 
\end{split}
$$

￼￼￼￼￼permutation matrix￼￼ swaping rows and columns
 
Pxy withpxy=pyx=1∀i≠x,y:pii=1∀i≠j,x,y:pij=0
 ￼PxyA￼ will swap the rows ￼x￼ and ￼y￼ of ￼A￼ 
 ￼APxy￼ will swap the column ￼x￼ and ￼y￼ of ￼A￼ 

## example swich rows 1 and 2 and columns 1 and 3

$$
\begin{split}
A = \begin{pmatrix}
a_{(1:1)} &\ a_{(1:2)} &\ a_{(1:3)} \\
a_{(2:1)} &\ a_{(2:2)} &\ a_{(2:3)} \\
a_{(3:1)} &\ a_{(3:2)} &\ a_{(3:3)} \\  
\end{pmatrix}
\end{split}
$$
$$
\begin{split}
P_{12} &= \begin{pmatrix}
0 &\ 1 &\ 0 \\
1 &\ 0 &\ 0 \\
0 &\ 0 &\ 1 \\  
\end{pmatrix} \\
P_{13} &= \begin{pmatrix}
0 &\ 0 &\ 1 \\
0 &\ 1 &\ 0 \\
1 &\ 0 &\ 0 \\  
\end{pmatrix} \\
P_{12}AP_{13} &=
\begin{pmatrix}
0 &\ 1 &\ 0 \\
1 &\ 0 &\ 0 \\
0 &\ 0 &\ 1 \\  
\end{pmatrix}
\begin{pmatrix}
a_{(1:1)} &\ a_{(1:2)} &\ a_{(1:3)} \\
a_{(2:1)} &\ a_{(2:2)} &\ a_{(2:3)} \\
a_{(3:1)} &\ a_{(3:2)} &\ a_{(3:3)} \\  
\end{pmatrix}
\begin{pmatrix}
0 &\ 1 &\ 0 \\
1 &\ 0 &\ 0 \\
0 &\ 0 &\ 1 \\  
\end{pmatrix} \\
&= 
\begin{pmatrix}
a_{(2:1)} &\ a_{(2:2)} &\ a_{(2:3)} \\
a_{(1:1)} &\ a_{(1:2)} &\ a_{(1:3)} \\
a_{(3:1)} &\ a_{(3:2)} &\ a_{(3:3)} \\  
\end{pmatrix}
\begin{pmatrix}
0 &\ 1 &\ 0 \\
1 &\ 0 &\ 0 \\
0 &\ 0 &\ 1 \\  
\end{pmatrix} \\
&= 
\begin{pmatrix}
a_{(2:3)} &\ a_{(2:2)} &\ a_{(2:1)} \\
a_{(1:3)} &\ a_{(1:2)} &\ a_{(1:1)} \\
a_{(3:3)} &\ a_{(3:2)} &\ a_{(3:1)} \\  
\end{pmatrix}
\end{split}
$$
# Anki

START
Basic
[[inverse matrix]] of a [[permutation matrix]] with proof

Back: 
#### Definition
- [[matrix]] $P \in \mathbb{R}^{n \times n}$ with only one $1$ per row and column and everything else $0$
- $P$ is a [[orthogonal matrix]] ([[transpose]] is equal to its [[inverse matrix]]  $P^{-1}=P^{T}$) 

A [[permutation matrix]] is a [[orthogonal matrix]] thus its [[transpose]] is equal to its [[inverse matrix]]

### proof
$$
\begin{split}
&PP^T = \left( \sum_{i=1}^n p_{i,k}p_{j,k} \right)_{1\leq i \leq n, 1\leq j \leq n} =\left( \mathbb{I}\left[i=j\right] \right)_{1\leq i \leq n, 1\leq j \leq n} = I  \\ 
\end{split}
$$

Tags: mathematics linear_algebra
<!--ID: 1697359286535-->
END


START
Basic
[[permutation matrix]]
- definition
- propertie (1)
- swaping rows and columns

Back: 
#### Definition
- [[matrix]] $P \in \mathbb{R}^{n \times n}$ with only one $1$ per row and column and everything else $0$
- $P$ is a [[orthogonal matrix]] ([[transpose]] is equal to its [[inverse matrix]]  $P^{-1}=P^{T}$) 


#### [[permutation matrix]] swaping rows and columns
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

Tags: mathematics linear_algebra
<!--ID: 1696694242793-->
END


START
Basic
swich rows 1 and 2 and columns 1 and 3 of [[matrix]] $A$ using [[matrix product|matrix multiplication]]

$$
\begin{split}
A = \begin{pmatrix}
a_{(1:1)} &\ a_{(1:2)} &\ a_{(1:3)} \\
a_{(2:1)} &\ a_{(2:2)} &\ a_{(2:3)} \\
a_{(3:1)} &\ a_{(3:2)} &\ a_{(3:3)} \\  
\end{pmatrix}
\end{split}
$$

Back: 
#### Definition
- [[matrix]] $P \in \mathbb{R}^{n \times n}$ with only one $1$ per row and column and everything else $0$
- $P$ is a [[orthogonal matrix]]

#### [[permutation matrix]] swaping rows and columns
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
### example swich rows 1 and 2 and columns 1 and 3

$$
\begin{split}
A = \begin{pmatrix}
a_{(1:1)} &\ a_{(1:2)} &\ a_{(1:3)} \\
a_{(2:1)} &\ a_{(2:2)} &\ a_{(2:3)} \\
a_{(3:1)} &\ a_{(3:2)} &\ a_{(3:3)} \\  
\end{pmatrix}
\end{split}
$$
$$
\begin{split}
P_{12} &= \begin{pmatrix}
0 &\ 1 &\ 0 \\
1 &\ 0 &\ 0 \\
0 &\ 0 &\ 1 \\  
\end{pmatrix} \\
P_{13} &= \begin{pmatrix}
0 &\ 0 &\ 1 \\
0 &\ 1 &\ 0 \\
1 &\ 0 &\ 0 \\  
\end{pmatrix} \\
P_{12}AP_{13} &=
\begin{pmatrix}
0 &\ 1 &\ 0 \\
1 &\ 0 &\ 0 \\
0 &\ 0 &\ 1 \\  
\end{pmatrix}
\begin{pmatrix}
a_{(1:1)} &\ a_{(1:2)} &\ a_{(1:3)} \\
a_{(2:1)} &\ a_{(2:2)} &\ a_{(2:3)} \\
a_{(3:1)} &\ a_{(3:2)} &\ a_{(3:3)} \\  
\end{pmatrix}
\begin{pmatrix}
0 &\ 1 &\ 0 \\
1 &\ 0 &\ 0 \\
0 &\ 0 &\ 1 \\  
\end{pmatrix} \\
&= 
\begin{pmatrix}
a_{(2:1)} &\ a_{(2:2)} &\ a_{(2:3)} \\
a_{(1:1)} &\ a_{(1:2)} &\ a_{(1:3)} \\
a_{(3:1)} &\ a_{(3:2)} &\ a_{(3:3)} \\  
\end{pmatrix}
\begin{pmatrix}
0 &\ 1 &\ 0 \\
1 &\ 0 &\ 0 \\
0 &\ 0 &\ 1 \\  
\end{pmatrix} \\
&= 
\begin{pmatrix}
a_{(2:3)} &\ a_{(2:2)} &\ a_{(2:1)} \\
a_{(1:3)} &\ a_{(1:2)} &\ a_{(1:1)} \\
a_{(3:3)} &\ a_{(3:2)} &\ a_{(3:1)} \\  
\end{pmatrix}
\end{split}
$$
Tags: mathematics linear_algebra
<!--ID: 1696746884821-->
END