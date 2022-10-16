# Transpose of a [[matrix]]
## Definition
The [[transpose]] of [[matrix]] A is defined as follows 
$$
\begin{split}
A  \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}} 
&= \left(a_{i,j} \right)_{i \in \mathcal{I}, j \in \mathcal{J}} \\
&= \left(A^{(j)} \right)_{j \in \mathcal{J}}
= 
\begin{pmatrix}   A^{(1)} &   ... & A^{(\left| \mathcal{J} \right|)}  \end{pmatrix}\\
&= \left(A_{(i)} \right)_{i \in \mathcal{I}}
=  
\begin{pmatrix}   A_{(1)} \\   ... \\ A_{(\left| \mathcal{I} \right|)}   \end{pmatrix}
\end{split}
$$

$$
\begin{split}
A^\top  \in \mathbb{R^{\left| \mathcal{J} \right| \times \left| \mathcal{I} \right|}} 
&= \left(a_{i,j} \right)_{j \in \mathcal{J}, i \in \mathcal{I}} \\
&= \left(A_{(i)} \right)_{i \in \mathcal{I}}
= 
\begin{pmatrix}   A_{(1)} &   ... & A_{(\left| \mathcal{I} \right|)}  \end{pmatrix}\\
&= \left(A^{(j)} \right)_{j \in \mathcal{J}}
=  
\begin{pmatrix}   A^{(1)} \\   ... \\ A^{(\left| \mathcal{J} \right|)}   \end{pmatrix}
\end{split}
$$
## Properties
1) $\left(A_1A_2 \: .. \:A_k\right)^\top=A_k^\top  \: .. \: A_2^\top A_1^\top$ 
2) $\left(A+B\right)^\top=A^\top + B^\top$
3) $(cA)^\top =cA^\top$
4) $det(A)=det(A^\top)$ with its [[determinant]] $A^\top$
5) $A^\top A$ is [[definite quadratic form|positive-semidefinite]]
6) $\left(A^\top\right)^{-1}=\left(A^{-1}\right)^{\top}$ 


START
Basic
matrix transpose
- definition
- properties (6)
 
Back: 
# Transpose of a [[matrix]]
## Definition
The [[transpose]] of [[matrix]] A is defined as follows 
$$
\begin{split}
A  \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}} 
&= \left(a_{i,j} \right)_{i \in \mathcal{I}, j \in \mathcal{J}} \\
&= \left(A^{(j)} \right)_{j \in \mathcal{J}}
= 
\begin{pmatrix}   A^{(1)} &   ... & A^{(\left| \mathcal{J} \right|)}  \end{pmatrix}\\
&= \left(A_{(i)} \right)_{i \in \mathcal{I}}
=  
\begin{pmatrix}   A_{(1)} \\   ... \\ A_{(\left| \mathcal{I} \right|)}   \end{pmatrix}
\end{split}
$$

$$
\begin{split}
A^\top  \in \mathbb{R^{\left| \mathcal{J} \right| \times \left| \mathcal{I} \right|}} 
&= \left(a_{i,j} \right)_{j \in \mathcal{J}, i \in \mathcal{I}} \\
&= \left(A_{(i)} \right)_{i \in \mathcal{I}}
= 
\begin{pmatrix}   A_{(1)} &   ... & A_{(\left| \mathcal{I} \right|)}  \end{pmatrix}\\
&= \left(A^{(j)} \right)_{j \in \mathcal{J}}
=  
\begin{pmatrix}   A^{(1)} \\   ... \\ A^{(\left| \mathcal{J} \right|)}   \end{pmatrix}
\end{split}
$$
## Properties
1) $\left(A_1A_2 \: .. \:A_k\right)^\top=A_k^\top  \: .. \: A_2^\top A_1^\top$ 
2) $\left(A+B\right)^\top=A^\top + B^\top$
3) $(cA)^\top =cA^\top$
4) $det(A)=det(A^\top)$ with its [[determinant]] $A^\top$
5) $A^\top A$ is [[definite quadratic form|positive-semidefinite]]
6) $\left(A^\top\right)^{-1}=\left(A^{-1}\right)^{\top}$ 

Tags: mathematics, linear algebra
<!--ID: 1665328452046-->
END