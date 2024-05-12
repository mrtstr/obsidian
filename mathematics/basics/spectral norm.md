### spectral norm
- [[operator norm]] induces by the $l^2$ [[norm]]
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$

$$
||A||_{2\rightarrow 2} =  \sup_{x\neq 0} \frac{||Ax||_2}{||x||_2} = \sqrt{\sigma_{\max}(A^\top A)}
$$

# ----------------

![[operator norm#operator norm]]

![[norm#norm]]

# anki

START
Basic

 
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
$$
\begin{split}
\sup_{x\neq 0} \frac{\left|\left|Ax\right|\right|_Y}{||x||_X} 
&= \sup_{x\neq 0} \frac{\left|\left|Ax\right|\right|_Y \frac{1} {||x||_X}}{||x||_X\frac{1}{||x||_X}} \\
&= \sup_{x\neq 0} \frac{\left|\left|A\frac{x}{||x||_X}\right|\right|_Y}{\left|\left|\frac{x}{||x||_X}\right|\right|_X} \\
&= \sup_{||x||_X = 1} ||Ax||_Y
\end{split}
$$
- note: since $||\cdot||_X$ and $||\cdot||_Y$ can differt there are multiple [[operator norm|operator norms]]


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


Tags: mathematics linear_algebra

END