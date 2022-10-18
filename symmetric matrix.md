## Definition
A [[square matrix]] $A  \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{I} \right|}}$ is symmetric when:
$$
\begin{split}
A  \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{I} \right|}} 
&= \left(a_{i,j} \right)_{i \in \mathcal{I}, j \in \mathcal{I}} \\
&= \left(A^{(j)} \right)_{j \in \mathcal{I}}
= 
\begin{pmatrix}   A^{(1)} &   ... & A^{(\left| \mathcal{I} \right|)}  \end{pmatrix}\\
&= \left(A_{(i)} \right)_{i \in \mathcal{I}}
=  
\begin{pmatrix}   A_{(1)} \\   ... \\ A_{(\left| \mathcal{I} \right|)}   \end{pmatrix}
\end{split}
$$
1) $A = A^\top$ ($A$ is equal to its [[transpose]])
2) $\forall i,j \in \mathcal{I}: a_{ij} = a_{ji}$
3) $A^{(i)} = A_{(i)}$ (the ith column vector is equal to the ith row vector)

## Properties
1) $A, B$ are [[symmetric matrix|symmetric]] then $A+B$ is a [[symmetric matrix]]
2) $A, B$ are [[symmetric matrix|symmetric]] then $AB$ is not [[symmetric matrix|symmetric]] in general (only iff $AB=BA$)
3) $A^\top = A \Leftrightarrow (A^n) = (A^n)^\top$
4) when A [[regular matrix]]: $A^\top = A \Leftrightarrow (A^{-1}) = (A^{-1})^\top$ ($A$ is [[symmetric matrix|symmetric]] iff it's [[inverse matrix]] is [[symmetric matrix|symmetric]])
5) every [[symmetric matrix]] is a [[normal matrix]]
6) $A$ [[symmetric matrix|symmetric]] then $XAX^\top$ is [[symmetric matrix|symmetric]] 


START
Basic
symmetric matrix
- definition (3)
- properties (6)

Back:
## Definition
A [[square matrix]] $A  \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{I} \right|}}$ is symmetric when:
$$
\begin{split}
A  \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{I} \right|}} 
&= \left(a_{i,j} \right)_{i \in \mathcal{I}, j \in \mathcal{I}} \\
&= \left(A^{(j)} \right)_{j \in \mathcal{I}}
= 
\begin{pmatrix}   A^{(1)} &   ... & A^{(\left| \mathcal{I} \right|)}  \end{pmatrix}\\
&= \left(A_{(i)} \right)_{i \in \mathcal{I}}
=  
\begin{pmatrix}   A_{(1)} \\   ... \\ A_{(\left| \mathcal{I} \right|)}   \end{pmatrix}
\end{split}
$$
1) $A = A^\top$ ($A$ is equal to its [[transpose]])
2) $\forall i,j \in \mathcal{I}: a_{ij} = a_{ji}$
3) $A^{(i)} = A_{(i)}$ (the ith column vector is equal to the ith row vector)

## Properties
1) $A, B$ are [[symmetric matrix|symmetric]] then $A+B$ is a [[symmetric matrix]]
2) $A, B$ are [[symmetric matrix|symmetric]] then $AB$ is not [[symmetric matrix|symmetric]] in general (only iff $AB=BA$)
3) $A^\top = A \Leftrightarrow (A^n) = (A^n)^\top$
4) when A [[regular matrix]]: $A^\top = A \Leftrightarrow (A^{-1}) = (A^{-1})^\top$ ($A$ is [[symmetric matrix|symmetric]] iff it's [[inverse matrix]] is [[symmetric matrix|symmetric]])
5) every [[symmetric matrix]] is a [[normal matrix]]
6) $A$ [[symmetric matrix|symmetric]] then $XAX^\top$ is [[symmetric matrix|symmetric]] 

Tags: mathematics, linear algebra
<!--ID: 1666105989005-->
END