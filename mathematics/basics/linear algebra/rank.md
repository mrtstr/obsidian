# Rank
![[matrix#Matrix#Matrix Definition]]
For a [[matrix]] $A$ with the column vectors $A^{(j)}$ and the represented linear function $F$.
$$F(x) = Ax: \mathbb{R}^{\left| \mathcal{J} \right|} \mapsto Im(A) = Span\left((A_{(j)})_{i \in \mathcal{I}}\right) \in \mathbb{R}^{\left| \mathcal{I} \right|}$$
## Definition

- The [[rank]] is equal to the number of [[linear independent]] columns vectors $A^{(j)}$
- The [[rank]] is equal to the number of [[linear independent]] row vectors $A_{(i)}$
- The [[rank]] is equal to the dimensions of the [[column space]]
$$
rank(A) = dim(range(A))
$$
- the [[rank]] is equal to the total number of column vectors $\left| \mathcal{J} \right|$ minus the [[nullity]]
$$
\underbrace{
rank(A)
}_\text{\# linear independent column vectors Aj}
  = 
\underbrace{
\left| \mathcal{J} \right|
}_\text{\# all column vectors Aj}
-
\underbrace{
nullity(A)
}_\text{\# linear dependent column vectors Aj}
$$






START
Basic
rank
- definition (4)
 
Back: 
# Rank
For a [[matrix]] $A$ with the column vectors $A^{(j)}$ and the represented linear function $F$.
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
$$F(x) = Ax: \mathbb{R}^{\left| \mathcal{J} \right|} \mapsto Im(A) = Span\left((A_{(j)})_{i \in \mathcal{I}}\right) \in \mathbb{R}^{\left| \mathcal{I} \right|}$$
## Definition

- The [[rank]] is equal to the number of [[linear independent]] columns vectors $A^{(j)}$
- The [[rank]] is equal to the number of [[linear independent]] row vectors $A_{(i)}$
- The [[rank]] is equal to the dimensions of the [[column space]]
$$
rank(A) = dim(range(A))
$$
- the [[rank]] is equal to the total number of column vectors $\left| \mathcal{J} \right|$ minus the [[nullity]]
$$
\underbrace{
rank(A)
}_\text{\# linear independent column vectors Aj}
  = 
\underbrace{
\left| \mathcal{J} \right|
}_\text{\# all column vectors Aj}
-
\underbrace{
nullity(A)
}_\text{\# linear dependent column vectors Aj}
$$
![[Pasted image 20221015081452.png]]
Tags: mathematics, linear algebra
<!--ID: 1665824261699-->
END