## relationship [[norm]] and [[metric]]
### every [[norm]] induces a [[metric]]
- the [[norm]] mesures the length of a [[vector]] $|| x ||$
- every [[norm]] induces a [[metric]]
$$
d(x, y) = || x - y ||
$$
#### proof
1) [[symmetric]] $d(x, y)=d(y, x)$
$$
\begin{split}
||x - y|| 
&= ||(-1)(y - x)|| \\ 
&= |-1| \cdot ||(y - x)|| \quad \text{ (absolutely homogeneous) } \\
&= ||(y - x)||
\end{split}
$$
2) [[positive definite]] follows from a [[norm]] being [[positive definite]]
$$
\begin{split}
&||v||=0 \leftrightarrow v = 0 \quad \text{ (norm is positive definite)} \\
&\text{let } v = x - y \\
\Rightarrow&||x - y||=0 \leftrightarrow x - y = 0 \\
\Rightarrow& ||x - y||=0 \leftrightarrow x = y
\end{split}
$$
3) greater or equal zero
![[norm#a norm is never negative]]
4) [[triangle inequality]]
$$
\begin{split}
&\forall v, w \in V: ||v + w|| \leq ||v|| + ||w|| \quad \text{ (triangle equality for norm)} \\
&\text{let } v = x - y \text{ and } w = y - z \\
\Rightarrow& ||x - y + y - z|| \leq ||x - y|| + ||y - z||  \\
\Rightarrow& ||x - z|| \leq ||x - y|| + ||y - z|| \\ 
\Rightarrow& d(x, z) \leq d(x, y) + d(y, z) \\ 
\end{split}
$$

#### example
- for example the eucledean distance between two [[vector|vectors]] $x, y \in V$
$$
d(x, y) = || x - y ||_2 = \left( \sum_{i \in [n]} |x_i - y_i|^2\right)^{\frac{1}{2}}
$$

### but not all [[metric|metrics]] induce a [[norm]]
- $d(x, 0) = || x||$ can often be a [[norm]] but not allways
$$
d(x, 0) = || x||
$$
1) the distance induced [[norm]] would be [[positive definite]]
$$
\begin{split}
d(x, y) \leftrightarrow x=y \\
d(x, 0) = || x|| \leftrightarrow x = 0
\end{split}
$$

# --------------------
![[norm#norm]]

![[metric#metric]]

# anki 
START
Basic
- prove that every [[norm]] induces a [[metric]]
- example for a [[norm]] induced [[metric]]
Back: 
### every [[norm]] induces a [[metric]]
- the [[norm]] mesures the length of a [[vector]] $|| x ||$
- every [[norm]] induces a [[metric]]
$$
d(x, y) = || x - y ||
$$
#### proof
1) [[symmetric]] $d(x, y)=d(y, x)$
$$
\begin{split}
||x - y|| 
&= ||(-1)(y - x)|| \\ 
&= |-1| \cdot ||(y - x)|| \quad \text{ (absolutely homogeneous) } \\
&= ||(y - x)||
\end{split}
$$
2) [[positive definite]] follows from a [[norm]] being [[positive definite]]
$$
\begin{split}
&||v||=0 \leftrightarrow v = 0 \quad \text{ (norm is positive definite)} \\
&\text{let } v = x - y \\
\Rightarrow&||x - y||=0 \leftrightarrow x - y = 0 \\
\Rightarrow& ||x - y||=0 \leftrightarrow x = y
\end{split}
$$
3) greater or equal zero
$$
\begin{split}
&\text{let } ||x|| < 0 \\
&0=|| x - x || \leq || x || + ||  (-1) x || = 2 || x || \cdot |-1| = 2 || x || \\
\Rightarrow& ||x|| \geq 0 \\
\Rightarrow& d(v,w) = ||v - w|| \geq 0 \\
\end{split}
$$
4) [[triangle inequality]]
$$
\begin{split}
&\forall v, w \in V: ||v + w|| \leq ||v|| + ||w|| \quad \text{ (triangle equality for norm)} \\
&\text{let } v = x - y \text{ and } w = y - z \\
\Rightarrow& ||x - y + y - z|| \leq ||x - y|| + ||y - z||  \\
\Rightarrow& ||x - z|| \leq ||x - y|| + ||y - z|| \\ 
\Rightarrow& d(x, z) \leq d(x, y) + d(y, z) \\ 
\end{split}
$$


#### example
- for example the eucledean distance between two [[vector|vectors]] $x, y \in V$
$$
d(x, y) = || x - y ||_2 = \left( \sum_{i \in [n]} |x_i - y_i|^2\right)^{\frac{1}{2}}
$$
___________________


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

## metric
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
3) never negative
$$
\forall x, y \in V: d(x, y) \geq 0
$$

4) [[triangle inequality]]
$$
\forall x, y, z \in V: d(x,z) \leq d(x,y) + d(y,z)
$$


Tags: mathematics
<!--ID: 1714493530679-->
END


START
Basic
how are [[norm|norms]] and [[metric|metrics]] related
Back: 
- [[metric]] defines a mesurement for the distance between two [[vector|vectors]]
- [[norm]] defines the length of a [[vector]] which is eqivalent to the distence of a [[vector]] to the [[origin]]
- the concepts are closely related

### some but not all [[metric|metrics]] induce a [[norm]]
- $d(x, 0) = || x||$ can often be a [[norm]] but not allways
$$
d(x, 0) = || x||
$$

### every [[norm]] induces a [[metric]]
- the [[norm]] mesures the length of a [[vector]] $|| x ||$
- every [[norm]] induces a [[metric]]
$$
d(x, y) = || x - y ||
$$
#### proof
1) [[symmetric]] $d(x, y)=d(y, x)$
$$
\begin{split}
||x - y|| 
&= ||(-1)(y - x)|| \\ 
&= |-1| \cdot ||(y - x)|| \quad \text{ (absolutely homogeneous) } \\
&= ||(y - x)||
\end{split}
$$
2) [[positive definite]] follows from a [[norm]] being [[positive definite]]
$$
\begin{split}
&||v||=0 \leftrightarrow v = 0 \quad \text{ (norm is positive definite)} \\
&\text{let } v = x - y \\
\Rightarrow&||x - y||=0 \leftrightarrow x - y = 0 \\
\Rightarrow& ||x - y||=0 \leftrightarrow x = y
\end{split}
$$
3) greater or equal zero
$$
\begin{split}
&\text{let } ||x|| < 0 \\
&0=|| x - x || \leq || x || + ||  (-1) x || = 2 || x || \cdot |-1| = 2 || x || \\
\Rightarrow& ||x|| \geq 0 \\
\Rightarrow& d(v,w) = ||v - w|| \geq 0 \\
\end{split}
$$
4) [[triangle inequality]]
$$
\begin{split}
&\forall v, w \in V: ||v + w|| \leq ||v|| + ||w|| \quad \text{ (triangle equality for norm)} \\
&\text{let } v = x - y \text{ and } w = y - z \\
\Rightarrow& ||x - y + y - z|| \leq ||x - y|| + ||y - z||  \\
\Rightarrow& ||x - z|| \leq ||x - y|| + ||y - z|| \\ 
\Rightarrow& d(x, z) \leq d(x, y) + d(y, z) \\ 
\end{split}
$$



#### example
- for example the eucledean distance between two [[vector|vectors]] $x, y \in V$
$$
d(x, y) = || x - y ||_2 = \left( \sum_{i \in [n]} |x_i - y_i|^2\right)^{\frac{1}{2}}
$$
___________________


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

## metric
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
3) never negative
$$
\forall x, y \in V: d(x, y) \geq 0
$$

4) [[triangle inequality]]
$$
\forall x, y, z \in V: d(x,z) \leq d(x,y) + d(y,z)
$$


Tags: mathematics
<!--ID: 1714493530687-->
END