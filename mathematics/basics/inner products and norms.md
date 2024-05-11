

### every [[inner product]] induces a [[norm]]
$$
||x|| = \sqrt{\langle x, x \rangle}
$$
$$
||x||^2 = \langle x, x \rangle
$$
### proof
1) [[positive definite]] follows directy for the [[inner product]] being [[positive definite]]
$$
\langle x, x \rangle \geq 0 \Rightarrow ||x|| = \sqrt{\langle x, x \rangle} \geq 0
$$

2) absolutly [[homogeneous]]
$$
\begin{split}
||\lambda x|| 
&= \sqrt{\langle \lambda x, \lambda x \rangle} \\
&= \sqrt{\lambda^2\langle  x,  x \rangle} \quad \text{(linearity of inner product)}\\
&= \sqrt{\lambda^2} \sqrt{\langle  x,  x \rangle} \\
&= |\lambda| \cdot || x||  \\
\end{split}
$$
3) [[triangle inequality]]

$$
\begin{split}
|| x+y ||^2  
&\leq \left(|| x || + || y ||\right)^2  \\
\langle x+y, x+y \rangle 
&\leq || x ||^2 + || y ||^2 + 2|| x || \cdot || y || \\
\langle x, x \rangle + \langle y, y \rangle + 2\langle x, y \rangle
&\leq  \langle x, x \rangle + \langle y, y \rangle + 2\sqrt{\langle x, x \rangle} \cdot \sqrt{\langle y, y \rangle}\\
\langle x, y \rangle
&\leq  \sqrt{\langle x, x \rangle} \cdot \sqrt{\langle y, y \rangle}  \quad \text{(cauchy schwarz)} \\
\end{split}
$$


![[cauchy schwarz inequality#cauchy schwarz inequality]]




### some [[norm|norms]] induce [[inner product|inner products]]
However, a norm ||⋅||is induced by an inner product if and only if it satisfies the parallelogram law:

||x+y||2+||x−y||2=2(||x||2+||y||2)
# ------------------

![[inner product#inner product]]

![[norm#norm]]


# anki

START
Basic
proof that every [[inner product]] induces a [[norm]]
Back: 

### every [[inner product]] induces a [[norm]]
$$
||x|| = \sqrt{\langle x, x \rangle}
$$
$$
||x||^2 = \langle x, x \rangle
$$
### proof
1) [[positive definite]] follows directy for the [[inner product]] being [[positive definite]]
$$
\langle x, x \rangle \geq 0 \Rightarrow ||x|| = \sqrt{\langle x, x \rangle} \geq 0
$$

2) absolutly [[homogeneous]]
$$
\begin{split}
||\lambda x|| 
&= \sqrt{\langle \lambda x, \lambda x \rangle} \\
&= \sqrt{\lambda^2\langle  x,  x \rangle} \quad \text{(linearity of inner product)}\\
&= \sqrt{\lambda^2} \sqrt{\langle  x,  x \rangle} \\
&= |\lambda| \cdot || x||  \\
\end{split}
$$

3) [[triangle inequality]]
$$
\begin{split}
|| x+y ||^2  
&= \langle x+y, x+y \rangle \\
&= \langle x, x \rangle + \langle y, y \rangle + 2\langle x, y \rangle \\
\left(|| x || + || y ||\right)^2 
&= || x ||^2 + || y ||^2 + 2|| x || \cdot || y || \\
&= \langle x, x \rangle + \langle y, y \rangle + 2\sqrt{\langle x, x \rangle} \cdot \sqrt{\langle y, y \rangle} \\
|| x+y ||  \leq || x || + || y || &\Leftrightarrow \langle x, y \rangle \leq \sqrt{\langle x, x \rangle} \cdot \sqrt{\langle y, y \rangle} \quad \text{(cauchy schwarz)}
\end{split}
$$

_______________________

### cauchy schwarz inequality
- let $V$ be a [[vector space]] with an [[inner product]] $\langle \cdot , \cdot \rangle$ 
- then the following is true for all $x, y \in V$

$$
|\langle x , y \rangle|^2 \leq \langle x , x \rangle \cdot \langle y , y \rangle
$$
eqivalent:
$$
|\langle x , y \rangle| \leq || x || \cdot || y ||
$$


#### proof
$$
\begin{split}
0 &\leq \left\langle \frac{x}{||x||} - \frac{y}{||y||} , \frac{x}{||x||} - \frac{y}{||y||}  \right\rangle \quad \text{(positive definit)} \\
0 &\leq   \frac{\left\langle x,x\right\rangle}{||x||^2} + \frac{\left\langle y,y\right\rangle}{||y||^2} - 2 \frac{\left\langle x,y\right\rangle}{||x|| \cdot ||y||} \\
0 &\leq   \frac{\left\langle x,x\right\rangle}{\sqrt{\langle x, x \rangle}^2} + \frac{\left\langle y,y\right\rangle}{\sqrt{\langle y, y \rangle}^2} - 2 \frac{\left\langle x,y\right\rangle}{||x|| \cdot ||y||} \\ 
0 &\leq   2 - 2 \frac{\left\langle x,y\right\rangle}{||x|| \cdot ||y||} \\ 
0 &\leq   ||x|| \cdot ||y|| -  \left\langle x,y\right\rangle \\ 
\left\langle x,y\right\rangle &\leq   ||x|| \cdot ||y||  \\ 
\end{split}
$$

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

### every [[inner product]] induces a [[norm]]
$$
||x|| = \sqrt{\langle x, x \rangle}
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


Tags: mathematics
<!--ID: 1714582042906-->
END


START
Basic
geometric reason why every [[inner product]] induces a [[norm]]
Back: 

### geometric relationship [[inner product]] and [[norm]]
- the [[inner product]] describes the unnormalized length of the [[projection]] auf one [[vector]] to another
- the length of the [[projection]] of a [[vector]] $x$ on itself equal to its length and thus $\langle x,x \rangle = ||x||^2$

#### [[inner product]] and [[projection]]

- given a [[vector]] $a$ and a [[vector]] $b$ then $\langle a, b \rangle$ is equal to the length of the [[projection]] of $a$ on $b$ [[multiplication|multiplied]] with the length of $b$ (and vice versa) 
- thus the [[inner product]] contains the information about the (unnormalized) length of the [[projection]] of one [[vector]] to another


![[projection.jpg]]


_______________________
### every [[inner product]] induces a [[norm]]
$$
||x|| = \sqrt{\langle x, x \rangle}
$$
$$
||x||^2 = \langle x, x \rangle
$$
### proof
1) [[positive definite]] follows directy for the [[inner product]] being [[positive definite]]
$$
\langle x, x \rangle \geq 0 \Rightarrow ||x|| = \sqrt{\langle x, x \rangle} \geq 0
$$

2) absolutly [[homogeneous]]
$$
\begin{split}
||\lambda x|| 
&= \sqrt{\langle \lambda x, \lambda x \rangle} \\
&= \sqrt{\lambda^2\langle  x,  x \rangle} \quad \text{(linearity of inner product)}\\
&= \sqrt{\lambda^2} \sqrt{\langle  x,  x \rangle} \\
&= |\lambda| \cdot || x||  \\
\end{split}
$$

3) [[triangle inequality]]
$$
\begin{split}
|| x+y ||^2  
&\leq \left(|| x || + || y ||\right)^2  \\
\langle x+y, x+y \rangle 
&\leq || x ||^2 + || y ||^2 + 2|| x || \cdot || y || \\
\langle x, x \rangle + \langle y, y \rangle + 2\langle x, y \rangle
&\leq  \langle x, x \rangle + \langle y, y \rangle + 2\sqrt{\langle x, x \rangle} \cdot \sqrt{\langle y, y \rangle}\\
\langle x, y \rangle
&\leq  \sqrt{\langle x, x \rangle} \cdot \sqrt{\langle y, y \rangle}  \quad \text{(cauchy schwarz)} \\
\end{split}
$$


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


Tags: mathematics
<!--ID: 1714827693819-->
END


START
Basic
relationship between
- [[norm]]
- [[inner product]]
- [[metric]]
Back: 
[[inner product]] $\xrightarrow{induces}$ [[norm]] $\xrightarrow{induces}$ [[metric]]

[[inner product]]: angle / length of [[projection]]
[[norm]]: length of [[vector]]
[[metric]]: distance betwen [[vector|vectors]]


### every [[inner product]] induces a [[norm]]
$$
||x|| = \sqrt{\langle x, x \rangle}
$$
$$
||x||^2 = \langle x, x \rangle
$$


### every [[norm]] induces a [[metric]]
- the [[norm]] mesures the length of a [[vector]] $|| x ||$
- every [[norm]] induces a [[metric]]
$$
d(x, y) = || x - y ||
$$


### geometric relationship [[inner product]] and [[norm]]
- the length of the [[projection]] of a [[vector]] $x$ on itself equal to its length and thus $\langle x,x \rangle = ||x||^2$

#### [[inner product]] and [[projection]]
- given a [[vector]] $a$ and a [[vector]] $b$ then $\langle a, b \rangle$ is equal to the length of the [[projection]] of $a$ on $b$ [[multiplication|multiplied]] with the length of $b$ (and vice versa) 
- thus the [[inner product]] contains the information about the (unnormalized) length of the [[projection]] of one [[vector]] to another


![[projection 5.jpg]]

### geometric interpretation between [[norm]] and [[metric]]
- the [[norm]] mesures the length of a [[vector]] $|| x ||$
- thus a every [[norm]] induces a [[metric]] messurement for the **distance between [[vector|vectors]]** 
$$
d(x, y) = || x - y ||
$$
- for example the eucledean distance between two [[vector|vectors]] $x, y \in V$
$$
d(x, y) = || x - y ||_2 = \left( \sum_{i \in [n]} |x_i - y_i|^2\right)^{\frac{1}{2}}
$$


_______________________

### proof that every [[inner product]] induces a [[norm]]
1) [[positive definite]] follows directy for the [[inner product]] being [[positive definite]]
$$
\langle x, x \rangle \geq 0 \Rightarrow ||x|| = \sqrt{\langle x, x \rangle} \geq 0
$$

2) absolutly [[homogeneous]]
$$
\begin{split}
||\lambda x|| 
&= \sqrt{\langle \lambda x, \lambda x \rangle} \\
&= \sqrt{\lambda^2\langle  x,  x \rangle} \quad \text{(linearity of inner product)}\\
&= \sqrt{\lambda^2} \sqrt{\langle  x,  x \rangle} \\
&= |\lambda| \cdot || x||  \\
\end{split}
$$

3) [[triangle inequality]]
$$
\begin{split}
|| x+y ||^2  
&\leq \left(|| x || + || y ||\right)^2  \\
\langle x+y, x+y \rangle 
&\leq || x ||^2 + || y ||^2 + 2|| x || \cdot || y || \\
\langle x, x \rangle + \langle y, y \rangle + 2\langle x, y \rangle
&\leq  \langle x, x \rangle + \langle y, y \rangle + 2\sqrt{\langle x, x \rangle} \cdot \sqrt{\langle y, y \rangle}\\
\langle x, y \rangle
&\leq  \sqrt{\langle x, x \rangle} \cdot \sqrt{\langle y, y \rangle}  \quad \text{(cauchy schwarz)} \\
\end{split}
$$



#### proof that every [[norm]] induces a [[metric]]
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
&0=|| x - x || \leq || x || + ||  (-1) x || = 2 || x || \cdot |-1| = 2 || x || \\
\Rightarrow& ||x|| \geq 0
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
<!--ID: 1714839935069-->
END