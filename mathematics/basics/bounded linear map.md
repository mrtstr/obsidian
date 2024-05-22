### bounded linear map
- given two [[banach space|banach spaces]] $(X, +, \cdot, ||\cdot||_X)$ and $(Y, \oplus, \odot , ||\cdot||_Y)$ and a [[linear map]] $A: X\rightarrow Y$
- $A$ is a [[bounded linear map]] if the followng is true

1) [[bounded set|boundedness]]

$$
\exists C>0: \forall x \in X : ||Ax||_Y \leq C ||x||_X
$$
2) [[linear map|linearity]]

$$
\forall x_1,x_2 \in X, \lambda , \mu \in \mathbb{R}:F(\lambda x_1 + \mu x_2) = \lambda \odot F(x_1) \oplus \mu \odot F(x_2) 
$$

- we define $L(X,Y)$ as the [[set]] of all [[bounded linear map|bounded linear maps]] mapping from $X$ to $Y$
$$
L(X,Y) = \{A: X\to Y: A \text{ is linear and bounded}\}
$$
- every [[bounded linear map]] in a finite space can be expressed as a [[matrix]]

$$
f(x): \mathbb{R}^{m} \to \mathbb{R}^{n} = Ax
$$

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

![[cauchy sequence#cauchy sequence]]
# anki

START
Basic
definition: [[bounded linear map]] and related concepts (3)
- general form
Back: 

### bounded linear map
- given two [[banach space|banach spaces]] $(X, +, \cdot, ||\cdot||_X)$ and $(Y, \oplus, \odot , ||\cdot||_Y)$ and a [[linear map]] $A: X\rightarrow Y$
- $A$ is a [[bounded linear map]] if the followng is true

1) [[bounded set|boundedness]]

$$
\exists C>0: \forall x \in X : ||Ax||_Y \leq C ||x||_X
$$
2) [[linear map|linearity]]

$$
\forall x_1,x_2 \in X, \lambda , \mu \in \mathbb{R}:F(\lambda x_1 + \mu x_2) = \lambda \odot F(x_1) \oplus \mu \odot F(x_2) 
$$

- we define $L(X,Y)$ as the [[set]] of all [[bounded linear map|bounded linear maps]] mapping from $X$ to $Y$
$$
L(X,Y) = \{A: X\to Y: A \text{ is linear and bounded}\}
$$
- every [[bounded linear map]] in a finite space can be expressed as a [[matrix]]

$$
f(x): \mathbb{R}^{m} \to \mathbb{R}^{n} = Ax
$$

__________________


### banach spaces
- [[norm|normed]] [[vector space|space]] that is [[cauchy complete]] with resprect to the [[metric]] induces by its norm is a [[banach space]]

### cauchy complete
- a [[metric]] [[vector space|space]] $(X, d)$ is **complete** if every [[cauchy sequence]] in $X$ also has a [[limit]] in $X$
	→ no points are missing inside or at the boundarys

### cauchy sequence
- given a [[metric]] [[vector space|space]] $(X, d)$
- a [[sequence]] $x_n$ is a [[cauchy sequence]] if the following is true

$$
\forall \epsilon > 0:\exists N: 
\forall n,m \geq N: d(x_n,x_m) < \epsilon
$$
→ the elements become arbitrarily close to each other as the [[sequence]] progresses

### linear function
- let $F:V \rightarrow W$ be a [[function]] from one [[vector space]] $(V, +, \cdot)$ to another [[vector space]] $(W,\oplus, \odot)$ 
- $F$ is a [[linear map]] if the following is true

$$
\forall v,w \in V, \lambda , \mu \in \mathbb{K}:F(\lambda v + \mu w) = \lambda \odot F(v) \oplus \mu \odot F(W) 
$$


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
<!--ID: 1715456214977-->
END



START
Basic
releationship
- [[bounded linear map]] vs [[continuous function|continuous]] [[linear map]]
- [[bounded linear map]] vs [[banach space]]
- [[bounded linear map]] vs [[matrix]]
Back: 
### bounded linear maps are a [[banach space]]
- every [[bounded linear map]] has a [[operator norm]] and is [[cauchy complete]] and thus is a [[banach space]]


### every [[bounded linear map]] is a [[continuous function]]


### every [[continuous function|continuous]] [[linear map]] is [[bounded linear map|bounded]]

__________________
### bounded linear map
- given two [[banach space|banach spaces]] $(X, +, \cdot, ||\cdot||_X)$ and $(Y, \oplus, \odot , ||\cdot||_Y)$ and a [[linear map]] $A: X\rightarrow Y$
- $A$ is a [[bounded linear map]] if the followng is true

1) [[bounded set|boundedness]]

$$
\exists C>0: \forall x \in X : ||Ax||_Y \leq C ||x||_X
$$
2) [[linear map|linearity]]

$$
\forall x_1,x_2 \in X, \lambda , \mu \in \mathbb{R}:F(\lambda x_1 + \mu x_2) = \lambda \odot F(x_1) \oplus \mu \odot F(x_2) 
$$

- we define $L(X,Y)$ as the [[set]] of all [[bounded linear map|bounded linear maps]] mapping from $X$ to $Y$
$$
L(X,Y) = \{A: X\to Y: A \text{ is linear and bounded}\}
$$
- every [[bounded linear map]] in a finite space can be expressed as a [[matrix]]

$$
f(x): \mathbb{R}^{m} \to \mathbb{R}^{n} = Ax
$$

### linear map
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

### cauchy sequence
- given a [[metric]] [[vector space|space]] $(X, d)$
- a [[sequence]] $x_n$ is a [[cauchy sequence]] if the following is true

$$
\forall \epsilon > 0:\exists N: 
\forall n,m \geq N: d(x_n,x_m) < \epsilon
$$
→ the elements become arbitrarily close to each other as the [[sequence]] progresses

Tags: mathematics linear_algebra
<!--ID: 1715458120901-->
END