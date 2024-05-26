### [[matrix]] product

$$
\begin{split}
AB &=\left(\sum\limits_{l \in [k]} a_{il}b_{lj}\right)_{i \in [n],\: j \in [m]} \in \mathbb{R}^{n \times m} \\
&=
\left(A_{(i, *)}{B_{(*, j)}^\top}\right)_{i \in [n],\: j \in [m]} \\
&= \left(\begin{matrix} 
\left(AB_{(*, 1)}^\top\right)^\top \\ ... \\ \left(AB_{(*, m)}^\top\right)^\top 
\end{matrix}\right)
\end{split}
$$

### Properties
1) $AB \neq BA$ [[commutative|non commutative]]
2) $A(B+C)=AB+BC$ [[distributive]]
3) $\left(AB\right)C = A\left(BC\right)$ [[associative]]
4) $c\left(AB\right)=(cA)B= (AB)c = A(Bc)$ [[commutative]] with a [[scalar]] 

# ---------------------
![[matrix#matrix]]

# anki
START
Basic
matrix multiplication
- definition
- properties (4)
 
Back: 
### matrix product
$$
\begin{split}
AB &=\left(\sum\limits_{l \in [k]} a_{il}b_{lj}\right)_{i \in [n],\: j \in [m]} \in \mathbb{R}^{n \times m} \\
&=
\left(A_{(i, *)}{B_{(*, j)}^\top}\right)_{i \in [n],\: j \in [m]} \\
&= \left(\begin{matrix} 
\left(AB_{(*, 1)}^\top\right)^\top \\ ... \\ \left(AB_{(*, m)}^\top\right)^\top 
\end{matrix}\right)
\end{split}
$$
### Properties
1) $AB \neq BA$ [[commutative|non commutative]]
2) $A(B+C)=AB+BC$ [[distributive]]
3) $\left(AB\right)C = A\left(BC\right)$ [[associative]]
4) $c\left(AB\right)=(cA)B= (AB)c = A(Bc)$ [[commutative]] with a [[scalar]] 

__________________________
### matrix
- can be represented by a two-dimensional [[array]]
- is a 2. Order [[tensor]] 
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


Tags: mathematics linear_algebra
<!--ID: 1665328452040-->
END