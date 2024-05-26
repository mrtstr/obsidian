### rank nullity theorem
- let $A \in \mathbb{R}^{n \times m}$ 
- then $n$ is equal to the [[rank]] of $A$ plus the [[dimensions]] of the [[nullspace]] of $A$
$$
\begin{split}
n 
&= \mathrm{rank}(A) + \dim\left(N(A)\right) \\
&= \dim\left(\mathrm{span}\left(A_{(*, 1)}, ..., A_{(*, m)}\right) \subseteq \mathbb{R}^n \right) + \dim\left(\left\{ x \in \mathbb{R}^{m} \mid Ax=0 \right\}
\subseteq\mathbb{R}^{m}\right) \\
\end{split}
$$
- in other words the number of all column vectors is equal to the number of [[linear independent]] column vectors plus the number of linear dependent column vectors

$$
\underbrace{
\mathrm{rank}(A)
}_\text{\# linear independent column vectors Aj} 
+
\underbrace{
\dim\left(N(A)\right)
}_\text{\# linear dependent column vectors Aj} 
= 
\underbrace{
n
}_\text{\# all column vectors Aj}
$$
![[Pasted image 20221015081452.png]]

#### proof TODO add proof
- from the definition of the [[rank]] follows that $\mathrm{rank}(A)=\dim\left(\mathrm{span}\left(A_{(1, *)}, ..., A_{(n, *)}\right) \subseteq \mathbb{R}^m \right)$ is equal to the number of [[linear independent]] column [[vector|vectors]] of $A$
- we need to show that $\dim\left(N(A)\right)=\dim\left(\left\{ x \in \mathbb{R}^{m} \mid Ax=0 \right\}\right)$ is equal to the number of linear dependent column vectors of $A$
- if all column [[vector|vectors]] $A_{(*, j)}$ are [[linear independent]] $N(A) = \{0\} \rightarrow \dim\left(N(A)\right) =0$ follows from the defintion of [[linear independent]]
- for every linear dependent column [[vector|vectors]] $A_{(*, j)}$ there is a now element in element in the basis if $N(A)$ (TODO add proof)
# --------------------
![[dimensions#dimensions of a vector space]]

![[basis#basis]]

![[nullspace#nullspace]]

![[rank#rank]]
# anki

START
Basic
[[rank nullity theorem]] with explainantion
Back: 
### rank nullity theorem
- let $A \in \mathbb{R}^{n \times m}$ 
- then $n$ is equal to the [[rank]] of $A$ plus the [[dimensions]] of the [[nullspace]] of $A$
$$
\begin{split}
n 
&= \mathrm{rank}(A) + \dim\left(N(A)\right) \\
&= \dim\left(\mathrm{span}\left(A_{(*, 1)}, ..., A_{(*, m)}\right) \subseteq \mathbb{R}^n \right) + \dim\left(\left\{ x \in \mathbb{R}^{m} \mid Ax=0 \right\}
\subseteq\mathbb{R}^{m}\right) \\
\end{split}
$$
- in other words the number of all column vectors is equal to the number of [[linear independent]] column vectors plus the number of linear dependent column vectors

$$
\underbrace{
\mathrm{rank}(A)
}_\text{\# linear independent column vectors Aj} 
+
\underbrace{
\dim\left(N(A)\right)
}_\text{\# linear dependent column vectors Aj} 
= 
\underbrace{
n
}_\text{\# all column vectors Aj}
$$
![[Pasted image 20221015081452.png]]

#### proof TODO add proof
- from the definition of the [[rank]] follows that $\mathrm{rank}(A)=\dim\left(\mathrm{span}\left(A_{(1, *)}, ..., A_{(n, *)}\right) \subseteq \mathbb{R}^m \right)$ is equal to the number of [[linear independent]] column [[vector|vectors]] of $A$
- we need to show that $\dim\left(N(A)\right)=\dim\left(\left\{ x \in \mathbb{R}^{m} \mid Ax=0 \right\}\right)$ is equal to the number of linear dependent column vectors of $A$
- if all column [[vector|vectors]] $A_{(*, j)}$ are [[linear independent]] $N(A) = \{0\} \rightarrow \dim\left(N(A)\right) =0$ follows from the defintion of [[linear independent]]
- for every linear dependent column [[vector|vectors]] $A_{(*, j)}$ there is a now element in element in the basis if $N(A)$ (TODO add proof)


_________________
### column space
- the [[column space]] of a [[matrix]] $A \in \mathbb{R}^{n \times m}$ is defined as the [[linear combinations]] if its column vectors $A_{(1, *)}, ..., A_{(n, *)}  \in \mathbb{R}^m$
$$
\begin{split}
\mathrm{colspace}(A)
&=\mathrm{span}\left(A_{(*, 1)}, ..., A_{(*, 1)}\right) \\
&=\left\{ Ax: x \in \mathbb{R}^m\right\} \subseteq\mathbb{R}^n \\
&=\{w \in \mathbb{R}^n: \lambda_1, ... \lambda_n \in \mathbb{R}: w = \lambda_1 \cdot A_{(*, 1)} + ... + \lambda_n \cdot A_{(*, m)}\} \\
\end{split}
$$


### dimensions of a [[vector space]]
- let $B$ be a [[vector space]] and $B$ be a [[basis]] of $V$
- the dimensions of $V$ are defines as the [[cardinality]] of its [[basis]]
- note: the [[vector space]] $\{{0}\}$ has per definition zero dimension 
- note: since every [[basis]] of a [[vector space]] has the same [[cardinality]] (see [[basis#every basis of a vector space has the same cardinality|here]]) the [[dimensions]] of a [[vector space]] is equal to the [[cardinality]] of all of its [[basis]]
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


Tags: mathematics linear_algebra
<!--ID: 1665824261696-->
END