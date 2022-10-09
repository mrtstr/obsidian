# Matrix Product
## Definition
$$
\begin{split}
A  \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}} 
&= \left(a_{i,j} \right)_{i \in \mathcal{I}, j \in \mathcal{J}} \\
&= \left(A^{(i)} \right)_{i \in \mathcal{I}}
= 
\begin{pmatrix}   A^{(1)} &   ... & A^{(\left| \mathcal{I} \right|)}  \end{pmatrix}\\
&= \left(A_{(j)} \right)_{j \in \mathcal{J}}
=  
\begin{pmatrix}   A_{(1)} \\   ... \\ A_{(\left| \mathcal{J} \right|)}   \end{pmatrix}
\end{split}
$$
$$
AB=\left(\sum\limits_{j \in \mathcal{J}} a_{ij}b_{jk}\right)_{i \in \mathcal{I},\: k \in \mathcal{K}}
=
\left(A^{(i)}{B_{(k)}^\top}\right)_{i \in \mathcal{I},\: k \in \mathcal{K}}
$$
## Properties
1) $AB \neq BA$ [[commutative|non commutative]]
2) $A(B+C)=AB+BC$ [[distributive]]
3) $\left(AB\right)C = A\left(BC\right)$ [[associative]]
4) $c\left(AB\right)=(cA)B= (AB)c = A(Bc)$ [[commutative]] with a [[scalar]] 

START
Basic
matrix multiplication
- definition
- properties (4)
 
Back: 
## Definition
$$
\begin{split}
A  \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}} 
&= \left(a_{i,j} \right)_{i \in \mathcal{I}, j \in \mathcal{J}} \\
&= \left(A^{(i)} \right)_{i \in \mathcal{I}}
= 
\begin{pmatrix}   A^{(1)} &   ... & A^{(\left| \mathcal{I} \right|)}  \end{pmatrix}\\
&= \left(A_{(j)} \right)_{j \in \mathcal{J}}
=  
\begin{pmatrix}   A_{(1)} \\   ... \\ A_{(\left| \mathcal{J} \right|)}   \end{pmatrix}
\end{split}
$$
$$
AB=\left(\sum\limits_{j \in \mathcal{J}} a_{ij}b_{jk}\right)_{i \in \mathcal{I},\: k \in \mathcal{K}}
=
\left(A^{(i)}{B_{(k)}^\top}\right)_{i \in \mathcal{I},\: k \in \mathcal{K}}
$$
## Properties
1) $AB \neq BA$ [[commutative|non commutative]]
2) $A(B+C)=AB+BC$ [[distributive]]
3) $\left(AB\right)C = A\left(BC\right)$ [[associative]]
4) $c\left(AB\right)=(cA)B= (AB)c = A(Bc)$ [[commutative]] with a [[scalar]] 

Tags: mathematics, linear algebra
<!--ID: 1665328452040-->
END