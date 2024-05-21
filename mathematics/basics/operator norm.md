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
proof:
- let $\hat{x} = arg\max \frac{\left|\left|Ax\right|\right|_Y}{||x||_X}$ 
- we can scale or normalize $\hat{x}$ without changing the result because of the [[norm]] is [[homogeneous]]
$$
\begin{split}
\frac{\left|\left|A\hat{x}\right|\right|_Y}{||\hat{x}||_X} 
&= \frac{\left|\left|A\hat{x}\right|\right|_Y \frac{1} {||\hat{x}||_X}}{||\hat{x}||_X\frac{1}{||\hat{x}||_X}} \\
&=  \frac{\left|\left|A\frac{x}{||\hat{x}||_X}\right|\right|_Y}{\left|\left|\frac{x}{||\hat{x}||_X}\right|\right|_X} \\
\end{split}
$$
- thus we can restrict the definition to just [[norm|normalized]] [[vector|vectors]] without impact on the result $\sup_{||x||_X = 1} ||Ax||_Y$
- note: since $||\cdot||_X$ and $||\cdot||_Y$ can differt there are multiple [[operator norm|operator norms]]

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
### interpretation
- the [[operator norm]] of the [[function]] $||A||_{X \rightarrow Y}$ is the maximal factor by which it can lengthen a [[vector]] over its [[domain]]

### examples
![[column sum norm#column sum norm]]

![[row sum norm#row sum norm]]

![[spectral norm#spectral norm]]
# -------------------

![[linear map#linear map]]

![[norm#norm]]

![[banach space#banach spaces]]

![[cauchy complete#cauchy complete]]



# anki

START
Basic
[[operator norm]]
- definition
- geometric interpreation
Back: 
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
proof:
- let $\hat{x} = arg\max \frac{\left|\left|Ax\right|\right|_Y}{||x||_X}$ 
- we can scale or normalize $\hat{x}$ without changing the result because of the [[norm]] is [[homogeneous]]
$$
\begin{split}
\frac{\left|\left|A\hat{x}\right|\right|_Y}{||\hat{x}||_X} 
&= \frac{\left|\left|A\hat{x}\right|\right|_Y \frac{1} {||\hat{x}||_X}}{||\hat{x}||_X\frac{1}{||\hat{x}||_X}} \\
&=  \frac{\left|\left|A\frac{x}{||\hat{x}||_X}\right|\right|_Y}{\left|\left|\frac{x}{||\hat{x}||_X}\right|\right|_X} \\
\end{split}
$$
- thus we can restrict the definition to just [[norm|normalized]] [[vector|vectors]] without impact on the result $\sup_{||x||_X = 1} ||Ax||_Y$
- note: since $||\cdot||_X$ and $||\cdot||_Y$ can differt there are multiple [[operator norm|operator norms]]

### interpretation
- the [[operator norm]] of the [[function]] $||A||_{X \rightarrow Y}$ is the maximal factor by which it can lengthen a [[vector]] over its [[domain]]

__________________
### linear function
- let $F:V \rightarrow W$ be a [[function]] from one [[vector space]] $(V, +, \cdot)$ to another [[vector space]] $(W,\oplus, \odot)$ 
- $F$ is a [[linear map]] if the following is true

$$
\forall v,w \in V, \lambda , \mu \in \mathbb{K}:F(\lambda v + \mu w) = \lambda \odot F(v) \oplus \mu \odot F(W) 
$$


### banach spaces
- [[norm|normed]] [[vector space|space]] that is [[cauchy complete]] with resprect to the [[metric]] induces by its norm is a [[banach space]]

### norm
- generalization of the concept of **length of a [[vector]]**
- let $V$ be a [[vector space]]
- the [[function]] $||\:.||: V \rightarrow \mathbb{R^+}$ is a [[norm]] is it satisfies the following conditions
1) [[positive definite]]
$$
||x||=0 \Leftrightarrow x = 0
$$

2) absolutely [[homogeneous]]
$$
\forall x \in V, \lambda \in \mathbb{K}: ||\lambda \cdot x|| = |\lambda| \cdot ||x||
$$
3) [[triangle inequality]]
$$
\forall v, w \in V: ||v + w|| \leq ||v|| + ||w||
$$


### cauchy complete
- a [[metric]] [[vector space|space]] $(X, d)$ is **complete** if every [[cauchy sequence]] in $X$ also has a [[limit]] in $X$
	→ no points are missing inside or at the boundarys


Tags: mathematics linear_algebra
<!--ID: 1715456214980-->
END


START
Basic
proof for the following:
$$
||A||_{X \rightarrow Y} = \sup_{x\neq 0} \frac{||Ax||_Y}{||x||_X} = \sup_{||x||_X = 1} ||Ax||_Y
$$

what does this define?

Back: 
- let $\hat{x} = arg\max \frac{\left|\left|Ax\right|\right|_Y}{||x||_X}$ 
- we can scale or normalize $\hat{x}$ without changing the result because of the [[norm]] is [[homogeneous]]
$$
\begin{split}
\frac{\left|\left|A\hat{x}\right|\right|_Y}{||\hat{x}||_X} 
&= \frac{\left|\left|A\hat{x}\right|\right|_Y \frac{1} {||\hat{x}||_X}}{||\hat{x}||_X\frac{1}{||\hat{x}||_X}} \\
&=  \frac{\left|\left|A\frac{x}{||\hat{x}||_X}\right|\right|_Y}{\left|\left|\frac{x}{||\hat{x}||_X}\right|\right|_X} \\
\end{split}
$$
- thus we can restrict the definition to just [[norm|normalized]] [[vector|vectors]] without impact on the result $\sup_{||x||_X = 1} ||Ax||_Y$


__________________

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
proof:
- let $\hat{x} = arg\max \frac{\left|\left|Ax\right|\right|_Y}{||x||_X}$ 
- we can just scale or normalize $\hat{x}$ because of the [[norm]] is [[homogeneous]]
$$
\begin{split}
\frac{\left|\left|A\hat{x}\right|\right|_Y}{||\hat{x}||_X} 
&= \frac{\left|\left|A\hat{x}\right|\right|_Y \frac{1} {||\hat{x}||_X}}{||\hat{x}||_X\frac{1}{||\hat{x}||_X}} \\
&=  \frac{\left|\left|A\frac{x}{||\hat{x}||_X}\right|\right|_Y}{\left|\left|\frac{x}{||\hat{x}||_X}\right|\right|_X} \\
\end{split}
$$
- thus we can restrict the definition to just [[norm|normalized]] [[vector|vectors]] without impact on the result $\sup_{||x||_X = 1} ||Ax||_Y$
- note: since $||\cdot||_X$ and $||\cdot||_Y$ can differt there are multiple [[operator norm|operator norms]]

### linear function
- let $F:V \rightarrow W$ be a [[function]] from one [[vector space]] $(V, +, \cdot)$ to another [[vector space]] $(W,\oplus, \odot)$ 
- $F$ is a [[linear map]] if the following is true

$$
\forall v,w \in V, \lambda , \mu \in \mathbb{K}:F(\lambda v + \mu w) = \lambda \odot F(v) \oplus \mu \odot F(W) 
$$


### banach spaces
- [[norm|normed]] [[vector space|space]] that is [[cauchy complete]] with resprect to the [[metric]] induces by its norm is a [[banach space]]

### norm
- generalization of the concept of **length of a [[vector]]**
- let $V$ be a [[vector space]]
- the [[function]] $||\:.||: V \rightarrow \mathbb{R^+}$ is a [[norm]] is it satisfies the following conditions
1) [[positive definite]]
$$
||x||=0 \Leftrightarrow x = 0
$$

2) absolutely [[homogeneous]]
$$
\forall x \in V, \lambda \in \mathbb{K}: ||\lambda \cdot x|| = |\lambda| \cdot ||x||
$$
3) [[triangle inequality]]
$$
\forall v, w \in V: ||v + w|| \leq ||v|| + ||w||
$$


### cauchy complete
- a [[metric]] [[vector space|space]] $(X, d)$ is **complete** if every [[cauchy sequence]] in $X$ also has a [[limit]] in $X$
	→ no points are missing inside or at the boundarys


Tags: mathematics linear_algebra
<!--ID: 1715456214983-->
END



START
Basic
[[operator norm]]
- 3 examples with interpretation
Back: 

### column sum norm
- [[operator norm]] induces by the $l^1$ [[norm]]
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$

$$
||A||_{\infty\rightarrow \infty} =  \sup_{x\neq 0} \frac{||Ax||_\infty}{||x||_\infty} = \max_{i \in [n]} \sum_{j \in [m]} |a_{ij}|
$$


### row sum norm
- [[operator norm]] induces by the $l^\infty$ [[norm]]
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$

$$
||A||_{\infty\rightarrow \infty} =  \sup_{x\neq 0} \frac{||Ax||_\infty}{||x||_\infty} = \max_{i \in [n]} \sum_{j \in [m]} |a_{ij}|
$$


### spectral norm
- [[operator norm]] induces by the $l^2$ [[norm]]
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$

$$
||A||_{2\rightarrow 2} =  \sup_{x\neq 0} \frac{||Ax||_2}{||x||_2} = \sqrt{\sigma_{\max}(A^\top A)}
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
proof:
$$
\begin{split}
\sup_{x\neq 0} \frac{\left|\left|Ax\right|\right|_Y}{||x||_X} 
&= \sup_{x\neq 0} \frac{\left|\left|Ax\right|\right|_Y \frac{1} {||x||_X}}{||x||_X\frac{1}{||x||_X}} \\
&= \sup_{x\neq 0} \frac{\left|\left|A\frac{x}{||x||_X}\right|\right|_Y}{\left|\left|\frac{x}{||x||_X}\right|\right|_X} \\
&= \sup_{||x||_X = 1} ||Ax||_Y
\end{split}
$$
- note: since $||\cdot||_X$ and $||\cdot||_Y$ can differt there are multiple [[operator norm|operator norms]]

### interpretation
- the [[operator norm]] of the [[function]] $||A||_{X \rightarrow Y}$ is the maximal factor by which it can lengthen a [[vector]] over its [[domain]]

__________________
### linear function
- let $F:V \rightarrow W$ be a [[function]] from one [[vector space]] $(V, +, \cdot)$ to another [[vector space]] $(W,\oplus, \odot)$ 
- $F$ is a [[linear map]] if the following is true

$$
\forall v,w \in V, \lambda , \mu \in \mathbb{K}:F(\lambda v + \mu w) = \lambda \odot F(v) \oplus \mu \odot F(W) 
$$


### banach spaces
- [[norm|normed]] [[vector space|space]] that is [[cauchy complete]] with resprect to the [[metric]] induces by its norm is a [[banach space]]

### norm
- generalization of the concept of **length of a [[vector]]**
- let $V$ be a [[vector space]]
- the [[function]] $||\:.||: V \rightarrow \mathbb{R^+}$ is a [[norm]] is it satisfies the following conditions
1) [[positive definite]]
$$
||x||=0 \Leftrightarrow x = 0
$$

2) absolutely [[homogeneous]]
$$
\forall x \in V, \lambda \in \mathbb{K}: ||\lambda \cdot x|| = |\lambda| \cdot ||x||
$$
3) [[triangle inequality]]
$$
\forall v, w \in V: ||v + w|| \leq ||v|| + ||w||
$$


### cauchy complete
- a [[metric]] [[vector space|space]] $(X, d)$ is **complete** if every [[cauchy sequence]] in $X$ also has a [[limit]] in $X$
	→ no points are missing inside or at the boundarys


Tags: mathematics linear_algebra
<!--ID: 1715456214986-->
END


START
Basic
proof that [[operator norm]] is submultiplicative

Back: 

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
proof:
$$
\begin{split}
\sup_{x\neq 0} \frac{\left|\left|Ax\right|\right|_Y}{||x||_X} 
&= \sup_{x\neq 0} \frac{\left|\left|Ax\right|\right|_Y \frac{1} {||x||_X}}{||x||_X\frac{1}{||x||_X}} \\
&= \sup_{x\neq 0} \frac{\left|\left|A\frac{x}{||x||_X}\right|\right|_Y}{\left|\left|\frac{x}{||x||_X}\right|\right|_X} \\
&= \sup_{||x||_X = 1} ||Ax||_Y
\end{split}
$$
- note: since $||\cdot||_X$ and $||\cdot||_Y$ can differt there are multiple [[operator norm|operator norms]]


__________________
### linear function
- let $F:V \rightarrow W$ be a [[function]] from one [[vector space]] $(V, +, \cdot)$ to another [[vector space]] $(W,\oplus, \odot)$ 
- $F$ is a [[linear map]] if the following is true

$$
\forall v,w \in V, \lambda , \mu \in \mathbb{K}:F(\lambda v + \mu w) = \lambda \odot F(v) \oplus \mu \odot F(W) 
$$


### banach spaces
- [[norm|normed]] [[vector space|space]] that is [[cauchy complete]] with resprect to the [[metric]] induces by its norm is a [[banach space]]

### norm
- generalization of the concept of **length of a [[vector]]**
- let $V$ be a [[vector space]]
- the [[function]] $||\:.||: V \rightarrow \mathbb{R^+}$ is a [[norm]] is it satisfies the following conditions
1) [[positive definite]]
$$
||x||=0 \Leftrightarrow x = 0
$$

2) absolutely [[homogeneous]]
$$
\forall x \in V, \lambda \in \mathbb{K}: ||\lambda \cdot x|| = |\lambda| \cdot ||x||
$$
3) [[triangle inequality]]
$$
\forall v, w \in V: ||v + w|| \leq ||v|| + ||w||
$$


### cauchy complete
- a [[metric]] [[vector space|space]] $(X, d)$ is **complete** if every [[cauchy sequence]] in $X$ also has a [[limit]] in $X$
	→ no points are missing inside or at the boundarys


Tags: mathematics linear_algebra
<!--ID: 1716139877285-->
END