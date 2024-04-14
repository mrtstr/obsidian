### [[matrix]] product

$$
AB=\left(\sum\limits_{j \in [m]} a_{ij}b_{jk}\right)_{i \in [n],\: k \in [k]}
=
\left(A^{(i)}{B_{(k)}^\top}\right)_{i \in [n],\: k \in [k]}
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
AB=\left(\sum\limits_{j \in \mathcal{J}} a_{ij}b_{jk}\right)_{i \in \mathcal{I},\: k \in \mathcal{K}}
=
\left(A^{(i)}{B_{(k)}^\top}\right)_{i \in \mathcal{I},\: k \in \mathcal{K}}
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