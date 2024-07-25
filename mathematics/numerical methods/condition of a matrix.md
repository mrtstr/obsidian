### condition of a matrix
- given a [[regular matrix]] $A \in \mathbb{R}^{m \times m}$ 
- the [[condition]] of the $A$ for a arbitray [[operator norm]] is defined as follows
$$
\kappa(A) = \left|\left|A^{-1}\right|\right| \cdot \left|\left|A\right|\right|
$$
- the [[condition of a matrix]] anwsers the question of how big the relative error of $x$ would be when $b$ is pertubed by an error vector $e$ (or $A$ is pertubed)
$$
Ax=b + e
$$
- the result for x would be $x=A^{-1}b$ with an error $A^{-1}e$ thus the relative error would be as follows

$$
\begin{split}
\frac{||A^{-1}b||}{||A^{-1}e||} / \frac{||b||}{||e||} 
&= \frac{||A^{-1}b||}{||b||}  \frac{||e||}{||A^{-1}e||} \\
&\leq ||A^{-1}||  \frac{||e||}{||A^{-1}e||} \frac{||A||}{||A||}  \\
&\leq ||A^{-1}||  \frac{||e||}{||AA^{-1}e||} ||A||  \\
&\leq ||A^{-1}|| \cdot ||A||  \\
\end{split}
$$
### upper bound of the [[condition of a matrix]]
$$
\kappa(A) = \left|\left|A^{-1}\right|\right| \cdot \left|\left|A\right|\right| \leq \left|\left|AA^{-1}\right|\right| = 1
$$
# --------------------

![[condition#condition]]

![[operator norm#operator norm]]

![[operator norm#the operator norm is submultiplicative]]

# anki

START
Basic
[[condition of a matrix]]
- defintion
- what does it answer? (with proof)
Back: 
### condition of a matrix
- given a [[regular matrix]] $A \in \mathbb{R}^{m \times m}$ 
- the [[condition]] of the $A$ for a arbitray [[operator norm]] is defined as follows
$$
\kappa(A) = \left|\left|A^{-1}\right|\right| \cdot \left|\left|A\right|\right|
$$
- the [[condition of a matrix]] anwsers the question of how big the relative error of $x$ would be when $b$ is pertubed by an error vector $e$ (or $A$ is pertubed)
$$
Ax=b + e
$$
- the result for x would be $x=A^{-1}b$ with an error $A^{-1}e$ thus the relative error would be as follows

$$
\begin{split}
\frac{||A^{-1}b||}{||A^{-1}e||} / \frac{||b||}{||e||} 
&= \frac{||A^{-1}b||}{||b||}  \frac{||e||}{||A^{-1}e||} \\
&\leq ||A^{-1}||  \frac{||e||}{||A^{-1}e||} \frac{||A||}{||A||}  \\
&\leq ||A^{-1}||  \frac{||e||}{||AA^{-1}e||} ||A||  \\
&\leq ||A^{-1}|| \cdot ||A||  \\
\end{split}
$$

------------------------


### condition
- given a [[function]] $F: X \subset \mathbb{R}^m \to Y \subset \mathbb{R}^n$ 
- given input data $x$ and perturbed input data $\tilde x = x + \Delta x$ 
- the [[condition]] of $F$ is the smallest number $\kappa\left(F\right)$ such that the following is true

$$
\frac{||F(x) - F(\tilde x)||}{||F(x)||} \leq \kappa\left(F\right) \cdot \frac{||x - \tilde x||}{||x||}
$$


### operator norm
- an [[operator norm]] is a [[norm]] in a [[function space]] that is induced by the [[norm|norms]] of the [[domain]] and codomain [[banach space]]
- given two [[banach space|banach spaces]] $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ and a [[linear map]] $A: X\rightarrow Y$
$$
||A||_{X \rightarrow Y} = \inf\{C \geq 0: ||Ax||_Y \leq C ||x||_X\}
$$
- for a nonempty [[domain]] $X \neq \emptyset$ the [[operator norm]] can be exapressed as follows.
 $$
||A||_{X \rightarrow Y} = \sup_{x\neq 0} \frac{||Ax||_Y}{||x||_X} = \sup_{||x||_X = 1} ||Ax||_Y
$$

### the [[operator norm]] is submultiplicative
- given two [[linear map|linear maps]] $A: X \to Y$ and $B: Y \to Z$ the following inequallity holds true
$$
||BA||_{X \to Z} \leq ||A||_{X \to Y} ||B||_{Y \to Z}
$$
 $$
 \begin{split}
||BA||_{X \to Z} 
&= \sup_{x\neq 0} \frac{||BAx||_Z}{||x||_X} \\
&= \sup_{x\neq 0, Ax \neq 0} \frac{||BAx||_Z}{||Ax||_{Y}}  \frac{||Ax||_Y}{||x||_X} \\
&\leq \sup_{Ax \neq 0} \frac{||BAx||_Z}{||Ax||_{Y}} \cdot \sup_{x \neq 0} \frac{||Ax||_Y}{||x||_X} \\
&= \sup_{y \neq 0} \frac{||By||_Z}{||y||_{Y}} \cdot \sup_{x \neq 0} \frac{||Ax||_Y}{||x||_X}  \\
&= ||A||_{X \to Y} ||B||_{Y \to Z}
\end{split}
$$





### [[inverse function|inverse]] [[matrix]] $A^{-1}$
- exist for [[regular matrix]] (for a general [[matrix]] see [[pseudo inverse matrix]])
- the [[inverse matrix]] $A^{-1}$ induces a linear [[function]] $f^{-1}(y)=A^{-1}y$ which is the [[inverse function]] of the linear function induces by $A$ $f(x)=Ax$
- A [[regular matrix]] $A$ [[matrix product|multiplied]] with its inverse $A^{-1}$ is equal to the [[identity matrix]] $I$
$$
AA^{-1} = A^{-1}A = I
$$

Tags: mathematics linear_algebra
<!--ID: 1721921970392-->
END


START
Basic

- what is the [[condition of a matrix]] of the [[matrix]] $A$ regarding the $1$ [[norm]]?
- what does it answer? 

$$
A
=\left(
\begin{matrix}
1 & 5 \\
-3 & 0 \\
\end{matrix}
\right) \\
$$

Back: 
$$
\det(A) = 15
$$
$$
A^{-1}
=\frac{1}{15}\left(
\begin{matrix}
0 & -5 \\
3 & 1 \\
\end{matrix}
\right) \\
$$

$$
\begin{split}
||A||_1 &= \max\{3, 0\} = 3 \\
||A^{-1}||_1 &= \max\left\{0, \frac{5}{15\cdot 15}\right\} = \frac{1}{45} \\
\kappa(A) &= ||A^{-1}||_1 ||A||_1 = \frac{3}{45} \cdot 3 = \frac{1}{15} \\
\end{split}
$$



------------------------

### column sum norm
- [[operator norm]] induces by the $l^1$ [[norm]]
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$

$$
||A||_{1\rightarrow 1} =  \sup_{x\neq 0} \frac{||Ax||_1}{||x||_1} =  \max_{j \in [m]} \sum_{i \in [n]} |a_{ij}|
$$

### inverse of a matrix $\in\mathbb{R}^{2\times 2}$ 

$$
\begin{split}
A
&=\left(
\begin{matrix}
a & b \\
c & d \\
\end{matrix}
\right) \\
A^{-1}
&=\frac{1}{\det(A)}\left(
\begin{matrix}
d & -b \\
-c & a \\
\end{matrix}
\right) \\
&=\frac{1}{ad-bc}\left(
\begin{matrix}
d & -b \\
-c & a \\
\end{matrix}
\right)
\end{split}
$$
#### proof
$$
\begin{split}
\left(
\begin{matrix}
a & b \\
c & d \\
\end{matrix}
\right) 
\frac{1}{ad-bc}\left(
\begin{matrix}
d & -b \\
-c & a \\
\end{matrix}
\right)
=\frac{1}{ad-bc}\left(
\begin{matrix}
ad-bc & ab-ab \\
cd-cd & ad-bc \\
\end{matrix}
\right) 
=\left(
\begin{matrix}
1 & 0 \\
0 & 1 \\
\end{matrix}
\right) 
\end{split}
$$

### condition of a matrix
- given a [[regular matrix]] $A \in \mathbb{R}^{m \times m}$ 
- the [[condition]] of the $A$ for a arbitray [[operator norm]] is defined as follows
$$
\kappa(A) = \left|\left|A^{-1}\right|\right| \cdot \left|\left|A\right|\right|
$$
- the [[condition of a matrix]] anwsers the question of how big the relative error of $x$ would be when $b$ is pertubed by an error vector $e$ (or $A$ is pertubed)
$$
Ax=b + e
$$
- the result for x would be $x=A^{-1}b$ with an error $A^{-1}e$ thus the relative error would be as follows

$$
\begin{split}
\frac{||A^{-1}b||}{||A^{-1}e||} / \frac{||b||}{||e||} 
&= \frac{||A^{-1}b||}{||b||}  \frac{||e||}{||A^{-1}e||} \\
&\leq ||A^{-1}||  \frac{||e||}{||A^{-1}e||} \frac{||A||}{||A||}  \\
&\leq ||A^{-1}||  \frac{||e||}{||AA^{-1}e||} ||A||  \\
&\leq ||A^{-1}|| \cdot ||A||  \\
\end{split}
$$


### condition
- given a [[function]] $F: X \subset \mathbb{R}^m \to Y \subset \mathbb{R}^n$ 
- given input data $x$ and perturbed input data $\tilde x = x + \Delta x$ 
- the [[condition]] of $F$ is the smallest number $\kappa\left(F\right)$ such that the following is true

$$
\frac{||F(x) - F(\tilde x)||}{||F(x)||} \leq \kappa\left(F\right) \cdot \frac{||x - \tilde x||}{||x||}
$$


### operator norm
- an [[operator norm]] is a [[norm]] in a [[function space]] that is induced by the [[norm|norms]] of the [[domain]] and codomain [[banach space]]
- given two [[banach space|banach spaces]] $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ and a [[linear map]] $A: X\rightarrow Y$
$$
||A||_{X \rightarrow Y} = \inf\{C \geq 0: ||Ax||_Y \leq C ||x||_X\}
$$
- for a nonempty [[domain]] $X \neq \emptyset$ the [[operator norm]] can be exapressed as follows.
 $$
||A||_{X \rightarrow Y} = \sup_{x\neq 0} \frac{||Ax||_Y}{||x||_X} = \sup_{||x||_X = 1} ||Ax||_Y
$$

### the [[operator norm]] is submultiplicative
- given two [[linear map|linear maps]] $A: X \to Y$ and $B: Y \to Z$ the following inequallity holds true
$$
||BA||_{X \to Z} \leq ||A||_{X \to Y} ||B||_{Y \to Z}
$$
 $$
 \begin{split}
||BA||_{X \to Z} 
&= \sup_{x\neq 0} \frac{||BAx||_Z}{||x||_X} \\
&= \sup_{x\neq 0, Ax \neq 0} \frac{||BAx||_Z}{||Ax||_{Y}}  \frac{||Ax||_Y}{||x||_X} \\
&\leq \sup_{Ax \neq 0} \frac{||BAx||_Z}{||Ax||_{Y}} \cdot \sup_{x \neq 0} \frac{||Ax||_Y}{||x||_X} \\
&= \sup_{y \neq 0} \frac{||By||_Z}{||y||_{Y}} \cdot \sup_{x \neq 0} \frac{||Ax||_Y}{||x||_X}  \\
&= ||A||_{X \to Y} ||B||_{Y \to Z}
\end{split}
$$





### [[inverse function|inverse]] [[matrix]] $A^{-1}$
- exist for [[regular matrix]] (for a general [[matrix]] see [[pseudo inverse matrix]])
- the [[inverse matrix]] $A^{-1}$ induces a linear [[function]] $f^{-1}(y)=A^{-1}y$ which is the [[inverse function]] of the linear function induces by $A$ $f(x)=Ax$
- A [[regular matrix]] $A$ [[matrix product|multiplied]] with its inverse $A^{-1}$ is equal to the [[identity matrix]] $I$
$$
AA^{-1} = A^{-1}A = I
$$

Tags: mathematics linear_algebra
<!--ID: 1721921970398-->
END


START
Basic

upper bound of the [[condition of a matrix]]  (with proof)

Back: 

### upper bound of the [[condition of a matrix]]
$$
\kappa(A) = \left|\left|A^{-1}\right|\right| \cdot \left|\left|A\right|\right| \leq \left|\left|AA^{-1}\right|\right| = 1
$$
------------------------


### condition of a matrix
- given a [[regular matrix]] $A \in \mathbb{R}^{m \times m}$ 
- the [[condition]] of the $A$ for a arbitray [[operator norm]] is defined as follows
$$
\kappa(A) = \left|\left|A^{-1}\right|\right| \cdot \left|\left|A\right|\right|
$$
- the [[condition of a matrix]] anwsers the question of how big the relative error of $x$ would be when $b$ is pertubed by an error vector $e$ (or $A$ is pertubed)
$$
Ax=b + e
$$
- the result for x would be $x=A^{-1}b$ with an error $A^{-1}e$ thus the relative error would be as follows

$$
\begin{split}
\frac{||A^{-1}b||}{||A^{-1}e||} / \frac{||b||}{||e||} 
&= \frac{||A^{-1}b||}{||b||}  \frac{||e||}{||A^{-1}e||} \\
&\leq ||A^{-1}||  \frac{||e||}{||A^{-1}e||} \frac{||A||}{||A||}  \\
&\leq ||A^{-1}||  \frac{||e||}{||AA^{-1}e||} ||A||  \\
&\leq ||A^{-1}|| \cdot ||A||  \\
\end{split}
$$


### condition
- given a [[function]] $F: X \subset \mathbb{R}^m \to Y \subset \mathbb{R}^n$ 
- given input data $x$ and perturbed input data $\tilde x = x + \Delta x$ 
- the [[condition]] of $F$ is the smallest number $\kappa\left(F\right)$ such that the following is true

$$
\frac{||F(x) - F(\tilde x)||}{||F(x)||} \leq \kappa\left(F\right) \cdot \frac{||x - \tilde x||}{||x||}
$$


### operator norm
- an [[operator norm]] is a [[norm]] in a [[function space]] that is induced by the [[norm|norms]] of the [[domain]] and codomain [[banach space]]
- given two [[banach space|banach spaces]] $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ and a [[linear map]] $A: X\rightarrow Y$
$$
||A||_{X \rightarrow Y} = \inf\{C \geq 0: ||Ax||_Y \leq C ||x||_X\}
$$
- for a nonempty [[domain]] $X \neq \emptyset$ the [[operator norm]] can be exapressed as follows.
 $$
||A||_{X \rightarrow Y} = \sup_{x\neq 0} \frac{||Ax||_Y}{||x||_X} = \sup_{||x||_X = 1} ||Ax||_Y
$$

### the [[operator norm]] is submultiplicative
- given two [[linear map|linear maps]] $A: X \to Y$ and $B: Y \to Z$ the following inequallity holds true
$$
||BA||_{X \to Z} \leq ||A||_{X \to Y} ||B||_{Y \to Z}
$$
 $$
 \begin{split}
||BA||_{X \to Z} 
&= \sup_{x\neq 0} \frac{||BAx||_Z}{||x||_X} \\
&= \sup_{x\neq 0, Ax \neq 0} \frac{||BAx||_Z}{||Ax||_{Y}}  \frac{||Ax||_Y}{||x||_X} \\
&\leq \sup_{Ax \neq 0} \frac{||BAx||_Z}{||Ax||_{Y}} \cdot \sup_{x \neq 0} \frac{||Ax||_Y}{||x||_X} \\
&= \sup_{y \neq 0} \frac{||By||_Z}{||y||_{Y}} \cdot \sup_{x \neq 0} \frac{||Ax||_Y}{||x||_X}  \\
&= ||A||_{X \to Y} ||B||_{Y \to Z}
\end{split}
$$





### [[inverse function|inverse]] [[matrix]] $A^{-1}$
- exist for [[regular matrix]] (for a general [[matrix]] see [[pseudo inverse matrix]])
- the [[inverse matrix]] $A^{-1}$ induces a linear [[function]] $f^{-1}(y)=A^{-1}y$ which is the [[inverse function]] of the linear function induces by $A$ $f(x)=Ax$
- A [[regular matrix]] $A$ [[matrix product|multiplied]] with its inverse $A^{-1}$ is equal to the [[identity matrix]] $I$
$$
AA^{-1} = A^{-1}A = I
$$

Tags: mathematics linear_algebra
<!--ID: 1721921970401-->
END