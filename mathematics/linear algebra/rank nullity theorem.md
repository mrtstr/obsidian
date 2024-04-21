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

#### proof
# --------------------
![[dimensions#dimensions of a vector space]]

![[basis#basis]]

![[nullspace#nullspace]]

![[rank#rank]]
# anki

START
Basic
[[rank nullity theorem]] with proof
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


Tags: mathematics linear_algebra
<!--ID: 1665824261696-->
END