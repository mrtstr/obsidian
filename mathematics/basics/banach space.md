### banach spaces
- [[norm|normed]] [[vector space|space]] that is [[cauchy complete]] with resprect to the [[metric]] induces by its norm is a [[banach space]]

### [[banach space]] [[function space]]

- [[continuous function|continouse]] and bounded [[function]] with the $L^2$ or $L^\infty$ [[norm]] are [[banach space|banach spaces]] 

# ---------------
![[norm#norm]]

![[cauchy complete#cauchy complete]]

# anki

START
Basic
- definition [[banach space]] and [[hilbert space]]
- their relationship

Back: 

- every [[hilbert space]] is a [[banach space]] because every [[inner product]] induces a [[norm]] (but not the other way around)

### banach spaces
- [[norm|normed]] [[vector space|space]] that is [[cauchy complete]] with resprect to the [[metric]] induces by its norm is a [[banach space]]

### hilbert spaces
- [[vector space]] with an [[inner product]] that is [[cauchy complete]] with resprect to the [[metric]] induces by its [[inner product]] is a [[hilbert space]]

___________________________

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
#### note
- the following conndiction is not sufficient to show that $x_n$ is a [[cauchy sequence]]
$$
\forall \epsilon > 0:\exists N: 
\forall n \geq N: d(x_n,x_{n+1}) < \epsilon
$$
- e.g: $x_n = \sqrt{n}$: eventhough $\sqrt{n}-\sqrt{n+1}$ becomes arbitrary small $\sqrt{n}-\sqrt{m}$ does not

### inner product
- let $(V, +, \cdot)$ be a [[vector space]]
-  [[function]]  $\langle\cdot,\cdot\rangle: V \times V \rightarrow \mathbb{R}$ is an [[inner product]] if the following conditions are true
1) [[linear map|linearity]] (regarding both elemements because of the [[symmetric]])

$$
\forall x,y,z \in V, \lambda \in \mathbb{R}:\langle x + \lambda y , z \rangle = \langle x , z  \rangle + \lambda \langle  y , z \rangle
$$
2) [[symmetric]]

$$
\forall x,y \in V: \langle x  , y \rangle = \langle y  , x \rangle
$$
3) [[positive definite]]

$$
\forall x \in V: \langle x  , x \rangle  \leftrightarrow x=0 
$$
$$
\forall x \in V: \langle x  , x \rangle  \geq 0
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


### metric
- generalization of the distance between [[vector|vectors]]
- let $V$ be a [[set]]
- a [[function]] $d: V \times V \rightarrow (0, \infty)$ is a [[metric]] if the followng conditions are true

1) [[symmetric]]
$$
\forall x, y \in V: d(x,y) = d(y,x)
$$
2) [[positive definite]]
$$
d(x, y) \leftrightarrow x=y
$$
$$
\forall x, y \in V: d(x, y) \geq 0
$$
3) [[triangle inequality]]
$$
\forall x, y, z \in V: d(x,z) \leq d(x,y) + d(y,z)
$$


Tags: mathematics
<!--ID: 1715360397340-->
END


START
Basic
one example and two non examples for:
- [[banach space]] 
- [[hilbert space]]


Back: 
- $\left(\mathbb{R}^n, ||\cdot||_p\right)$ is a [[banach space]] and $\left(\mathbb{R}^n, \langle \: \cdot \: \rangle \right)$ is a [[hilbert space]]
- $\left(\mathbb{R}_{\geq0}, ||\cdot||_p\right)$ is not a [[banach space]] and  $\left(\mathbb{R}_{\geq0}, \langle \: \cdot \: \rangle \right)$ is not a [[hilbert space]]
	- it's not [[cauchy complete]] because $x_n = \frac{1}{n}$ is a [[cauchy sequence]] but does not converge in $\mathbb{R}_{\geq0}$
- $\left(\mathbb{Q}, ||\cdot||_p\right)$ is not a [[banach space]] and  $\left(\mathbb{Q}, \langle \: \cdot \: \rangle \right)$ is not a [[hilbert space]]
	- it's not [[cauchy complete]] because $x_n = \left(1+\frac{1}{n}\right)^n$ is a [[cauchy sequence]] but does not converge in $\mathbb{Q}$
___________________________
### banach spaces
- [[norm|normed]] [[vector space|space]] that is [[cauchy complete]] with resprect to the [[metric]] induces by its norm is a [[banach space]]

### hilbert spaces
- [[vector space]] with an [[inner product]] that is [[cauchy complete]] with resprect to the [[metric]] induces by its [[inner product]] is a [[hilbert space]]
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
#### note
- the following conndiction is not sufficient to show that $x_n$ is a [[cauchy sequence]]
$$
\forall \epsilon > 0:\exists N: 
\forall n \geq N: d(x_n,x_{n+1}) < \epsilon
$$
- e.g: $x_n = \sqrt{n}$: eventhough $\sqrt{n}-\sqrt{n+1}$ becomes arbitrary small $\sqrt{n}-\sqrt{m}$ does not

### inner product
- let $(V, +, \cdot)$ be a [[vector space]]
-  [[function]]  $\langle\cdot,\cdot\rangle: V \times V \rightarrow \mathbb{R}$ is an [[inner product]] if the following conditions are true
1) [[linear map|linearity]] (regarding both elemements because of the [[symmetric]])

$$
\forall x,y,z \in V, \lambda \in \mathbb{R}:\langle x + \lambda y , z \rangle = \langle x , z  \rangle + \lambda \langle  y , z \rangle
$$
2) [[symmetric]]

$$
\forall x,y \in V: \langle x  , y \rangle = \langle y  , x \rangle
$$
3) [[positive definite]]

$$
\forall x \in V: \langle x  , x \rangle  \leftrightarrow x=0 
$$
$$
\forall x \in V: \langle x  , x \rangle  \geq 0
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


### metric
- generalization of the distance between [[vector|vectors]]
- let $V$ be a [[set]]
- a [[function]] $d: V \times V \rightarrow (0, \infty)$ is a [[metric]] if the followng conditions are true

1) [[symmetric]]
$$
\forall x, y \in V: d(x,y) = d(y,x)
$$
2) [[positive definite]]
$$
d(x, y) \leftrightarrow x=y
$$
$$
\forall x, y \in V: d(x, y) \geq 0
$$
3) [[triangle inequality]]
$$
\forall x, y, z \in V: d(x,z) \leq d(x,y) + d(y,z)
$$


Tags: mathematics
<!--ID: 1715456214966-->
END


START
Basic
example for a [[function space]] that is a [[banach space]]

Back: 
### [[banach space]] [[function space]]

- [[continuous function|continouse]] and bounded [[function]] with the $L^2$ or $L^\infty$ [[norm]] are [[banach space|banach spaces]] 

___________________________
### banach spaces
- [[norm|normed]] [[vector space|space]] that is [[cauchy complete]] with resprect to the [[metric]] induces by its norm is a [[banach space]]

### hilbert spaces
- [[vector space]] with an [[inner product]] that is [[cauchy complete]] with resprect to the [[metric]] induces by its [[inner product]] is a [[hilbert space]]

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
#### note
- the following conndiction is not sufficient to show that $x_n$ is a [[cauchy sequence]]
$$
\forall \epsilon > 0:\exists N: 
\forall n \geq N: d(x_n,x_{n+1}) < \epsilon
$$
- e.g: $x_n = \sqrt{n}$: eventhough $\sqrt{n}-\sqrt{n+1}$ becomes arbitrary small $\sqrt{n}-\sqrt{m}$ does not

### inner product
- let $(V, +, \cdot)$ be a [[vector space]]
-  [[function]]  $\langle\cdot,\cdot\rangle: V \times V \rightarrow \mathbb{R}$ is an [[inner product]] if the following conditions are true
1) [[linear map|linearity]] (regarding both elemements because of the [[symmetric]])

$$
\forall x,y,z \in V, \lambda \in \mathbb{R}:\langle x + \lambda y , z \rangle = \langle x , z  \rangle + \lambda \langle  y , z \rangle
$$
2) [[symmetric]]

$$
\forall x,y \in V: \langle x  , y \rangle = \langle y  , x \rangle
$$
3) [[positive definite]]

$$
\forall x \in V: \langle x  , x \rangle  \leftrightarrow x=0 
$$
$$
\forall x \in V: \langle x  , x \rangle  \geq 0
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


### metric
- generalization of the distance between [[vector|vectors]]
- let $V$ be a [[set]]
- a [[function]] $d: V \times V \rightarrow (0, \infty)$ is a [[metric]] if the followng conditions are true

1) [[symmetric]]
$$
\forall x, y \in V: d(x,y) = d(y,x)
$$
2) [[positive definite]]
$$
d(x, y) \leftrightarrow x=y
$$
$$
\forall x, y \in V: d(x, y) \geq 0
$$
3) [[triangle inequality]]
$$
\forall x, y, z \in V: d(x,z) \leq d(x,y) + d(y,z)
$$


Tags: mathematics
<!--ID: 1715456214970-->
END