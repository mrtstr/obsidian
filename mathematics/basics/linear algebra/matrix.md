# Matrix
- can be represented by a two-dimensional [[array]]
- is a 2. Order [[tensor]] 
- [[matrix calculus]]
## Matrix Definition
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
## Represented linear map
A matrix $A\in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}}$ represents a [[unique]] [[linear function]] $F(x)$ that maps the $\mathbb{R}^{\left| \mathcal{J} \right|}$ to its [[column space]] $Im(A) = Span\left((A_{(j)})_{i \in \mathcal{I}}\right) \in \mathbb{R}^{\left| \mathcal{I} \right|}$

$$F(x) = Ax: \mathbb{R}^{\left| \mathcal{J} \right|} \mapsto Im(A) = Span\left((A_{(j)})_{i \in \mathcal{I}}\right) \in \mathbb{R}^{\left| \mathcal{I} \right|}$$
![[Pasted image 20221015082805.png]]

## Operations
### [[matrix product|Product]]
$$
AB=\left(\sum\limits_{j \in \mathcal{J}} a_{ij}b_{jk}\right)_{i \in \mathcal{I},\: k \in \mathcal{K}}
=
\left(A^{(i)}{B_{(k)}^\top}\right)_{i \in \mathcal{I},\: k \in \mathcal{K}}
$$
### [[transpose|Transpose]] $A^\top$
$$
\begin{split}
A^\top  \in \mathbb{R^{\left| \mathcal{J} \right| \times \left| \mathcal{I} \right|}} 
&= \left(a_{i,j} \right)_{j \in \mathcal{J}, i \in \mathcal{I}} \\
&= \left(A_{(j)} \right)_{j \in \mathcal{J}}
= 
\begin{pmatrix}   A_{(1)} &   ... & A_{(\left| \mathcal{J} \right|)}  \end{pmatrix}\\
&= \left(A^{(i)} \right)_{i \in \mathcal{I}}
=  
\begin{pmatrix}   A^{(1)} \\   ... \\ A^{(\left| \mathcal{I} \right|)}   \end{pmatrix}
\end{split}
$$
### [[inverse matrix|Inverse]] $A^{-1}$
- exist for [[regular matrix]]
$$
AA^{-1} = A^{-1}A = I
$$

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
 
## Properties
1) $\left(A_1A_2 \: .. \:A_k\right)^\top=A_k^\top  \: .. \: A_2^\top A_1^\top$ 
2) $\left(A+B\right)^\top=A^\top + B^\top$
3) $(cA)^\top =cA^\top$
4) $det(A)=det(A^\top)$ with its [[determinant]] $A^\top$
5) $A^\top A$ is [[definite quadratic form|positive-semidefinite]]
6) $\left(A^\top\right)^{-1}=\left(A^{-1}\right)^{\top}$ 

Tags: mathematics linear_algebra
END


START
Basic
matrix
- definition
- induced map 
Back: 
## Definition
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

## induced linear map
A matrix $A\in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}}$ represents a [[unique]] [[linear function]] $F(x)$ that maps the $\mathbb{R}^{\left| \mathcal{J} \right|}$ to its [[column space]] $Im(A) = Span\left((A_{(j)})_{i \in \mathcal{I}}\right) \in \mathbb{R}^{\left| \mathcal{I} \right|}$

$$F(x) = Ax: \mathbb{R}^{\left| \mathcal{J} \right|} \mapsto Im(A) = Span\left((A_{(j)})_{i \in \mathcal{I}}\right) \in \mathbb{R}^{\left| \mathcal{I} \right|}$$

Tags: mathematics linear_algebra
<!--ID: 1665308790802-->
END