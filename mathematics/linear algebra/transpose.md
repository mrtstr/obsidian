### transpose
The [[transpose]] of [[matrix]] A is defined as follows 
$$
\begin{split}
A^\top  \in \mathbb{R}^{m \times n}
&= \left(a_{i,j} \right)_{j \in [m], i \in [n]} \\
&= \left(A_{(i)} \right)_{i \in [n]}
= 
\begin{pmatrix}   A_{(1)} &   ... & A_{(n)}  \end{pmatrix}\\
&= \left(A^{(j)} \right)_{j \in [m]}
=  
\begin{pmatrix}   A^{(1)} \\   ... \\ A^{(m)}   \end{pmatrix}
\end{split}
$$

### Properties
1) $\left(A_1A_2 \: .. \:A_k\right)^\top=A_k^\top  \: .. \: A_2^\top A_1^\top$ 
2) $\left(A+B\right)^\top=A^\top + B^\top$
3) $(cA)^\top =cA^\top$
4) $det(A)=det(A^\top)$ with its [[determinant]] $A^\top$
5) $A^\top A$ is [[definite quadratic form|positive-semidefinite]]
6) $\left(A^\top\right)^{-1}=\left(A^{-1}\right)^{\top}$ 

# ---------------------
![[matrix#matrix]]

# anki
START
Basic
[[matrix]] transpose
- definition
- properties (6)
 
Back: 
### transpose
$$
\begin{split}
A^\top  \in \mathbb{R}^{m \times n}
&= \left(a_{i,j} \right)_{j \in [m], i \in [n]} \\
&= \left(A_{(i)} \right)_{i \in [n]}
= 
\begin{pmatrix}   A_{(1)} &   ... & A_{(n)}  \end{pmatrix}\\
&= \left(A^{(j)} \right)_{j \in [m]}
=  
\begin{pmatrix}   A^{(1)} \\   ... \\ A^{(m)}   \end{pmatrix}
\end{split}
$$
### Properties
1) $\left(A_1A_2 \: .. \:A_k\right)^\top=A_k^\top  \: .. \: A_2^\top A_1^\top$ 
2) $\left(A+B\right)^\top=A^\top + B^\top$
3) $(cA)^\top =cA^\top$
4) $det(A)=det(A^\top)$ with its [[determinant]] $A^\top$
5) $A^\top A$ is [[definite quadratic form|positive-semidefinite]]
6) $\left(A^\top\right)^{-1}=\left(A^{-1}\right)^{\top}$ 

__________________
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
<!--ID: 1665328452046-->
END