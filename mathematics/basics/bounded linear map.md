### bounded linear map
- given two [[banach space|banach spaces]] $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ and a [[linear map]] $A: X\rightarrow Y$
- $A$ is a [[bounded linear map]] if the followng is true

$$
\exists C>0: \forall x \in X : ||Ax||_Y \leq C ||x||_X
$$
- it says that the [[image]] of a [[bounded set]] also has to be a [[bounded set]]

### bounded linear maps are a [[banach space]]
- every [[bounded linear map]] has a [[operator norm]] and is [[cauchy complete]] and thus is a [[banach space]]
TODO add proof

### every [[bounded linear map]] is a [[continuous function]]
TODO add proof

### every [[continuous function|continuous]] [[linear map]] is [[bounded linear map|bounded]]
TODO add proof
# ----------------

![[linear map#linear map]]

![[banach space#banach spaces]]

![[norm#norm]]

![[cauchy complete#cauchy complete]]

# anki

START
Basic
definition: [[bounded linear map]] and related concepts (3)
- relationship to [[bounded set]]
Back: 
### linear function
- let $F:V \rightarrow W$ be a [[function]] from one [[vector space]] $(V, +, \cdot)$ to another [[vector space]] $(W,\oplus, \odot)$ 
- $F$ is a [[linear map]] if the following is true

$$
\forall v,w \in V, \lambda , \mu \in \mathbb{K}:F(\lambda v + \mu w) = \lambda \odot F(v) \oplus \mu \odot F(W) 
$$

### bounded linear function
- given two [[banach space|banach spaces]] $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ and a [[linear map]] $A: X\rightarrow Y$
- $A$ is a [[bounded linear map]] if the followng is true

$$
\exists C>0: \forall x \in X : ||Ax||_Y \leq C ||x||_X
$$
- it says that the [[image]] of a [[bounded set]] also has to be a [[bounded set]]
__________________


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
<!--ID: 1715456214977-->
END



START
Basic
releationship
- [[bounded linear map]] vs [[continuous function|continuous]] [[linear map]]
- [[bounded linear map]] vs [[banach space]]
Back: 
### bounded linear maps are a [[banach space]]
- every [[bounded linear map]] has a [[operator norm]] and is [[cauchy complete]] and thus is a [[banach space]]


### every [[bounded linear map]] is a [[continuous function]]


### every [[continuous function|continuous]] [[linear map]] is [[bounded linear map|bounded]]

__________________
### linear function
- let $F:V \rightarrow W$ be a [[function]] from one [[vector space]] $(V, +, \cdot)$ to another [[vector space]] $(W,\oplus, \odot)$ 
- $F$ is a [[linear map]] if the following is true

$$
\forall v,w \in V, \lambda , \mu \in \mathbb{K}:F(\lambda v + \mu w) = \lambda \odot F(v) \oplus \mu \odot F(W) 
$$

### bounded linear function
- given two [[banach space|banach spaces]] $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ and a [[linear map]] $A: X\rightarrow Y$
- $A$ is a [[bounded linear map]] if the followng is true

$$
\exists C>0: \forall x \in X : ||Ax||_Y \leq C ||x||_X
$$
- it says that the [[image]] of a [[bounded set]] also has to be a [[bounded set]]

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
<!--ID: 1715458120901-->
END