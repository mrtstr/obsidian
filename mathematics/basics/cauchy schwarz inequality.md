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

### geometric interpreation [[cauchy schwarz inequality]]
- since $\langle a, b \rangle$ is equal to the length of [[vector]] $b$ times the length of [[vector]] $a$ in $b$ $(=b')$ the [[cauchy schwarz inequality]] says that the [[projection]] of one [[vector]] to another can never be longer than the [[vector]] itself
- equality can only happen when $a$ and $b$ are a scaled version of each other (they are [[linear independent|linear dependent]] and the angle between them is $0$ or $180$)
- when $a$ and $b$ are [[orthogonal]] the [[projection]] of one to the other is zero which is the other extreme case
$$
\begin{split}
&\langle a, b \rangle = ||b|| \cdot ||b'|| \leq ||a || \cdot ||b|| \\
\Rightarrow& ||b'|| \leq ||a||
\end{split}
$$

![[inner product#relationship to projection]]

### [[cauchy schwarz inequality]] for [[linear independent|linear dependen]] vectors
- when two [[vector]] $a$ and $b$ are [[linear independent|linear dependen]] both sides of the equation are equal

$$
\begin{split}
|\langle x , y \rangle|^2 \leq \langle x , x \rangle \cdot \langle y , y \rangle \\
|\langle x , \lambda x  \rangle|^2 \leq \langle x , x \rangle \cdot \langle \lambda x , \lambda x \rangle \\
\lambda^2|\langle x ,  x  \rangle|^2 \leq \langle x , x \rangle^2 \cdot \lambda^2 \\
\end{split}
$$

![[linear independent#linear independent]]

### examples for [[cauchy schwarz inequality]]
#### eucleadean [[norm]] / [[metric]]
$$
\begin{split}
\left(\sum_{i \in [n]} x_i y_i\right)^2 
&\leq \left(\sum_{i \in [n]} x_i^2\right) \cdot \left(\sum_{i \in [n]} y_i^2\right) \\
\left|\sum_{i \in [n]} x_i y_i\right| 
&\leq \left(\sum_{i \in [n]} x_i^2\right)^{\frac{1}{2}} \cdot \left(\sum_{i \in [n]} y_i^2\right)^{\frac{1}{2}}
\end{split}
$$

#### $L^2$ [[norm]] in the [[function space]]
- $f:\Omega \rightarrow \mathbb{R}$ and $g:\Omega \rightarrow \mathbb{R}$
$$
\begin{split}
\left(\int_\Omega f(x)g(x) dx \right)^2 
&\leq \left(\int_\Omega 
f(x)^2 dx\right) \cdot \left(\int_\Omega g(x)^2 dx\right) \\
\left|\int_\Omega f(x)g(x) dx \right| 
&\leq \left(\int_\Omega 
f(x)^2 dx\right)^{\frac{1}{2}} \cdot \left(\int_\Omega g(x)^2 dx\right)^{\frac{1}{2}}
\end{split}
$$
# --------------------

![[function space#$L p$ norm]]

![[inner products and norms#every inner product induces a norm]]

![[inner product#inner product]]

![[norm#norm]]
# anki

START
Basic
cauchy schwarz inequality (with proof)
- two versions
Back: 
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
_______________________
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
<!--ID: 1714582042911-->
END



START
Basic
geometric interpreatation of the [[cauchy schwarz inequality]]
- when are the extreme cases happening?
Back: 
### geometric interpreation [[cauchy schwarz inequality]]
- since $\langle a, b \rangle$ is equal to the length of [[vector]] $b$ times the length of [[vector]] $a$ in $b$ $(=b')$ the [[cauchy schwarz inequality]] says that the [[projection]] of one [[vector]] to another can never be longer than the [[vector]] itself
- equality can only happen when $a$ and $b$ are a scaled version of each other (they are [[linear independent|linear dependent]] and the angle between them is $0$ or $180$)
- when $a$ and $b$ are [[orthogonal]] the [[projection]] of one to the other is zero which is the other extreme case

$$
\begin{split}
&\langle a, b \rangle = ||b|| \cdot ||b'|| \leq ||a || \cdot ||b|| \\
\Rightarrow& ||b'|| \leq ||a||
\end{split}
$$

#### relationship [[inner product]] to [[projection]]
- given a [[vector]] $a$ and a [[vector]] $b$ then $\langle a, b \rangle$ is equal to the length of the [[projection]] of $a$ on $b$ [[multiplication|multiplied]] with the length of $b$ (and vice versa) 
- thus the [[inner product]] contains the information about the (unnormalized) length of the [[projection]] of one [[vector]] to another

![[projection 2.jpg]]

### [[cauchy schwarz inequality]] for [[linear independent|linear dependen]]  vectors
- when two [[vector]] $a$ and $b$ are [[linear independent|linear dependen]] both sides of the equation are equal

$$
\begin{split}
|\langle x , y \rangle|^2 \leq \langle x , x \rangle \cdot \langle y , y \rangle \\
|\langle x , \lambda x  \rangle|^2 \leq \langle x , x \rangle \cdot \langle \lambda x , \lambda x \rangle \\
\lambda^2|\langle x ,  x  \rangle|^2 \leq \langle x , x \rangle^2 \cdot \lambda^2 \\
\end{split}
$$

### linear independent
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- $v_1, ..., v_n \in V$ are [[linear independent]] if the following condition is true
$$
\forall \lambda_i \in \mathbb{K} :\sum\limits_{i \in [n]} v_i \lambda_i = 0 \Rightarrow \forall \lambda_i \in \mathbb{K}:  \lambda_i = 0
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
<!--ID: 1714894505852-->
END


START
Basic
examples for [[cauchy schwarz inequality]]
- eucledean space
- [[function space]]
Back: 
### examples for [[cauchy schwarz inequality]]
#### eucleadean [[norm]] / [[metric]]

$$
\begin{split}
\left(\sum_{i \in [n]} x_i y_i\right)^2 
&\leq \left(\sum_{i \in [n]} x_i^2\right) \cdot \left(\sum_{i \in [n]} y_i^2\right) \\
\left|\sum_{i \in [n]} x_i y_i\right| 
&\leq \left(\sum_{i \in [n]} x_i^2\right)^{\frac{1}{2}} \cdot \left(\sum_{i \in [n]} y_i^2\right)^{\frac{1}{2}}
\end{split}
$$

#### $L^2$ [[norm]] in the [[function space]]
- $f:\Omega \rightarrow \mathbb{R}$ and $g:\Omega \rightarrow \mathbb{R}$

$$
\begin{split}
\left(\int_\Omega f(x)g(x) dx \right)^2 
&\leq \left(\int_\Omega 
f(x)^2 dx\right) \cdot \left(\int_\Omega g(x)^2 dx\right) \\
\left|\int_\Omega f(x)g(x) dx \right| 
&\leq \left(\int_\Omega 
f(x)^2 dx\right)^{\frac{1}{2}} \cdot \left(\int_\Omega g(x)^2 dx\right)^{\frac{1}{2}}
\end{split}
$$

_______________________
#### $L^p$ [[norm]]

$$
||f||_p = \left(\int_{\Omega} |f(x)|^p dx \right)^{\frac{1}{p}}
$$


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
<!--ID: 1714833277644-->
END


START
Basic
what can be said about the [[cauchy schwarz inequality]] for [[linear independent|linear dependen]] vectors (with proof)
Back: 
### [[cauchy schwarz inequality]] for [[linear independent|linear dependen]]  vectors
- when two [[vector]] $a$ and $b$ are [[linear independent|linear dependen]] both sides of the equation are equal

$$
\begin{split}
|\langle x , y \rangle|^2 \leq \langle x , x \rangle \cdot \langle y , y \rangle \\
|\langle x , \lambda x  \rangle|^2 \leq \langle x , x \rangle \cdot \langle \lambda x , \lambda x \rangle \\
\lambda^2|\langle x ,  x  \rangle|^2 \leq \langle x , x \rangle^2 \cdot \lambda^2 \\
\end{split}
$$

### linear independent
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- $v_1, ..., v_n \in V$ are [[linear independent]] if the following condition is true
$$
\forall \lambda_i \in \mathbb{K} :\sum\limits_{i \in [n]} v_i \lambda_i = 0 \Rightarrow \forall \lambda_i \in \mathbb{K}:  \lambda_i = 0
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
<!--ID: 1714895503305-->
END