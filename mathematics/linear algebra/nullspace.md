# Nullspace or Kernel

![[matrix#Matrix#Matrix Definition]]
For a [[matrix]] $A$ with the column vectors $A^{(j)}$ and the represented linear function $F$.
$$F(x) = Ax: \mathbb{R}^{\left| \mathcal{J} \right|} \mapsto Im(A) = Span\left((A_{(j)})_{i \in \mathcal{I}}\right) \in \mathbb{R}^{\left| \mathcal{I} \right|}$$


## Definition

$$
kernel(A)=\left\{ x \in \mathbb{R}^{\mathcal{\left|J\right |}} \mid Ax=0 \right\}
\subseteq\mathbb{R^{\left| \mathcal{J} \right|}}
$$
## Properties
- $kernel(A) \subseteq \mathbb{R^{\left| \mathcal{J} \right| }}$ 
- $\mathbf{0} \in kern(A)$ 
- $dim(kern(A)) = \left| \mathcal{J} \right| - dim(range(A))$ [[rank nullity theorem]]
- $dim(kern(A)) = nullity(A)$ (dimensions are the [[nullity]])
- $dim(kern(A))$ = number of linear dependent rows


## Explanation 
In the [[nullspace]] are the vectors in the domain of $F(x)$ that map to zero. Thus, there are linear dependent column vectors $A^{(j)}$ needed for that to be the case. For $x$ to be in the [[nullspace]] the elements $(x)_{j}$ that is multiplied with the linear dependent column vectors $A^{(j)}$ has to be $\neq 0$ and all the other $(x)_{j}$ have to be $=0$. Thus, the dimensions of the [[nullspace]] are equal to the number of linear dependent column vectors $A^{(j)}$ and the [[nullity]]



START
Basic
Nullspace or Kernel
- definition
- properties (5)
- explanation
Back: 
# Nullspace or Kernel

For a [[matrix]] $A$ with the column vectors $A^{(j)}$ and the represented linear function $F$.
$$
A =\left(A^{(j)} \right)_{j \in \mathcal{J}}
= 
\begin{pmatrix}   A^{(1)}    ... & A^{(\left| \mathcal{J} \right|)}  \end{pmatrix}
\in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}}
$$
$$F(x) = Ax: \mathbb{R}^{\left| \mathcal{J} \right|} \mapsto Im(A) = Span\left((A_{(j)})_{i \in \mathcal{I}}\right) \in \mathbb{R}^{\left| \mathcal{I} \right|}$$


## Definition

$$
kernel(A)=\left\{ x \in \mathbb{R}^{\mathcal{\left|J\right |}} \mid Ax=0 \right\}
\subseteq\mathbb{R^{\left| \mathcal{J} \right|}}
$$
## Properties
- $kernel(A) \subseteq \mathbb{R^{\left| \mathcal{J} \right| }}$ 
- $\mathbf{0} \in kern(A)$ 
- $dim(kern(A)) = \left| \mathcal{J} \right| - dim(range(A))$ [[rank nullity theorem]]
- $dim(kern(A)) = nullity(A)$ (dimensions are the [[nullity]])
- $dim(kern(A))$ = number of linear dependent rows


## Explanation 
In the [[nullspace]] are the vectors in the domain of $F(x)$ that map to zero. Thus, there are linear dependent column vectors $A^{(j)}$ needed for that to be the case. For $x$ to be in the [[nullspace]] the elements $(x)_{j}$ that is multiplied with the linear dependent column vectors $A^{(j)}$ has to be $\neq 0$ and all the other $(x)_{j}$ have to be $=0$. Thus, the dimensions of the [[nullspace]] are equal to the number of linear dependent column vectors $A^{(j)}$ and the [[nullity]]
![[Pasted image 20221015081452.png]]
Tags: mathematics linear_algebra
<!--ID: 1665824261708-->
END