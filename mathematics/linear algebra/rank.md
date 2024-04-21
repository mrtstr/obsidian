### rank
- for a [[matrix]] $A \in \mathbb{R}^{n\times m}$ the [[rank]] of $A$ are the number of [[vector space#dimensions of a vector space|dimensions]] of its [[column space]]

$$
\begin{split}
\mathrm{rank}(A)
&=\dim(\mathrm{range}(A) \subseteq \mathbb{R}^n) \\
&=\dim\left(\mathrm{span}\left(A_{(1, *)}, ..., A_{(n, *)}\right) \subseteq \mathbb{R}^n \right)
\end{split}
$$

![[vector space#dimensions of a vector space]]

![[column space#column space]]





## Definition

- The [[rank]] is equal to the number of [[linear independent]] columns vectors $A_{(*,j)}$
- The [[rank]] is equal to the number of [[linear independent]] row vectors $A_{(i,*)}$
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
# ---------------------
![[matrix#matrix]]


![[vector space#vector space]]

# Anki

START
Basic
definition [[rank]] (and concepts where it's based on: 5)

Back: 
### rank
- for a [[matrix]] $A \in \mathbb{R}^{n\times m}$ the [[rank]] of $A$ is the number of [[vector space#dimensions of a vector space|dimensions]] of its [[column space]]

$$
\begin{split}
\mathrm{rank}(A)
&=\dim(\mathrm{range}(A) \subseteq \mathbb{R}^n) \\
&=\dim\left(\mathrm{span}\left(A_{(1, *)}, ..., A_{(n, *)}\right) \subseteq \mathbb{R}^n \right)
\end{split}
$$
_____________

### dimensions of a [[vector space]]
- let $B$ be a [[vector space]] and $B$ be a [[basis]] of $V$
- the dimensions of $V$ are defines as the [[cardinality]] of its [[basis]]
- note: the [[vector space]] $\{{0}\}$ has per definition zero dimension 
$$
\dim(V) = |B|
$$
### basis
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- $\{v_1, ..., v_n\}$ is a [[basis]] of $V$ if
1) $\{v_1, ..., v_n\}$ is a spanning [[set]] of $V$
2) $\{v_1, ..., v_n\}$ is [[linear independent]]


### linear independent
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- $v_1, ..., v_n \in V$ are [[linear independent]] if the following condition is true
$$
\forall \lambda_i \in \mathbb{K} :\sum\limits_{i \in [n]} v_i \lambda_i = 0 \Rightarrow \forall \lambda_i \in \mathbb{K}:  \lambda_i = 0
$$


### spanning [[set]] of a [[vector space]]
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- the [[set]] $\{v_1, ..., v_n\}$ is a **spanning set** or **generating set** of $V$ if $\mathrm{span}(v_1, ..., v_n) = V$
$$
\mathrm{span}(v_1, ..., v_n) = \{w \in V: \lambda_1, ... \lambda_n \in \mathbb{K}: w = \lambda_1 \cdot v_1 + ... + \lambda_n \cdot v_n\} = V
$$

### column space
- the [[column space]] of a [[matrix]] $A \in \mathbb{R}^{n \times m}$ is defined as the [[linear combinations]] if its column vectors $A_{(1, *)}, ..., A_{(n, *)}  \in \mathbb{R}^m$
$$
\begin{split}
\mathrm{range}(A)
&=\left\{ Ax: x \in \mathbb{R}^m\right\} \subseteq\mathbb{R}^n \\
&=\mathrm{span}\left(A_{(1, *)}, ..., A_{(n, *)}\right) \\
&=\{w \in \mathbb{R}^n: \lambda_1, ... \lambda_n \in \mathbb{R}: w = \lambda_1 \cdot A_{(1, *)} + ... + \lambda_n \cdot A_{(n, *)}\} \\
\end{split}
$$

Tags: mathematics linear_algebra
<!--ID: 1713684157513-->
END

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
Tags: mathematics linear_algebra
<!--ID: 1665824261699-->
END