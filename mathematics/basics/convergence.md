### convergence in $\mathbb{R}$
- given a [[sequence]] $a_n \in \mathbb{R}$  
- $a_n$ is converging against $a^*$ if the following is true

$$
\forall \epsilon>0: \exists N \in \mathbb{N}: n \geq N \Rightarrow |a_n - a^*| \leq \epsilon
$$

### convergence in a [[normed space]] $\left(V, +, \cdot, ||\cdot||\right)$
- given a [[sequence]] $v_n \in V$  
- $v_n$ is converging against $v^*$ if the following is true

$$
\begin{split}
&\forall \epsilon>0: \exists N \in \mathbb{N}: n \geq N \Rightarrow ||a_n - a^*|| \leq \epsilon \\
&\Leftrightarrow \\
&||v_n - v^* || \xrightarrow{n \rightarrow \infty} 0
\end{split}
$$
### [[convergence]] notations
$$
||v_n - v^* || \xrightarrow{n \rightarrow \infty} 0
$$
The following notations are equivalent:
$$
\lim_{n \rightarrow \infty} v_n  = v^*
$$
$$
v_n  \rightarrow v^*
$$
![[norm#norm]]


### convergence in $\mathbb{R}^n$
- given a [[sequence]] $a_n \in \mathbb{R}^n$  
- $a_n$ is converging against $a^*\in \mathbb{R}^n$ if every element is converging
$$
a_n  \rightarrow a^* \Leftrightarrow \forall i \in [n]: a_i \rightarrow a^*_i
$$
### examples [[convergence]]
- the followng [[sequence]] converges againt [[eulers number]]
$$
a_n =\left(1 + \frac{1}{n}\right)^n
$$
- converges against $0$
$$
a_n = \frac{1}{n}
$$

### [[convergence]] of a [[sequence]] of [[function]]
- given a [[sequence]] of [[function|functions]] $f_n: [a,b] \rightarrow \mathbb{R}$ 

#### [[convergence]] for the $L^1$ [[norm]]
- $f_n$ converges to $f$ for the $L^1$ [[norm]] in the following is true
$$
||f_n - f ||_1 \rightarrow 0 \Leftrightarrow \int^b_a |f_n(x) - f(x)| dx \rightarrow 0
$$
#### [[convergence]] for the $L^p$ [[norm]]
- $f_n$ converges to $f$ for the $L^p$ [[norm]] in the following is true
$$
||f_n - f ||_p \rightarrow 0 \Leftrightarrow \left(\int^b_a |f_n(x) - f(x)|^p dx\right)^{\frac{1}{p}} \rightarrow 0
$$
#### [[convergence]] for the $L^\infty$ [[norm]]
- $f_n$ converges to $f$ for the $L^\infty$ [[norm]] in the following is true
$$
||f_n - f ||_\infty \rightarrow 0 \Leftrightarrow \max_{a \leq x \leq b} |f_n(x) - f(x)| dx \rightarrow 0
$$
- this means that the distance between the functions has to go to zero for the complete domain
#### $||f_n - f ||_\infty \rightarrow 0 \Rightarrow ||f_n - f ||_1 \rightarrow 0$ but not the other way around


![[norm#norm for function space $f: Omega subset mathbb{R} d rightarrow mathbb{R}$]]

### [[convergence]] for $l^{p}$ implies element wise [[convergence]]
- let the [[sequence]] $x_n \in {\mathbb{R}^d}$ converge for the $l^p$ [[norm]]
- then $x_n$ converges for all other $l$ norms too
$$
\begin{split}
&\forall \epsilon>0: \exists N \in \mathbb{N}:  \forall n \geq N :||x_n - x^*||_p \leq \epsilon \\
\Rightarrow&\forall \epsilon>0: \exists N \in \mathbb{N}:  \forall n \geq N :\left(\sum_{i \in [n]} |(x_n)_i - x^*_i|^p \right)^{\frac{1}{p}} \leq \epsilon \\
\Rightarrow& \sum_{i \in [n]} |(x_n)_i - x^*_i|^p  \leq \epsilon^p \\
\Rightarrow& \forall i \in [n]: |(x_n)_i - x^*_i|^p  \leq \epsilon^p \\
\Rightarrow& \forall i \in [n]: |(x_n)_i - x^*_i|  \leq \epsilon \\
\Rightarrow& \forall i \in [n]: |(x_n)_i - x^*_i| \xrightarrow{n \rightarrow \infty} 0 \\
\end{split}
$$

### element wise [[convergence]] implies $l^{p}$ [[convergence]]
- let the [[sequence]] $x_n \in {\mathbb{R}^d}$ converge element wise $\forall i \in [d]: |(x_n)_i - x^*| \rightarrow 0$
- then $x_n$ converges for all other $l^p$ norms too
$$
\begin{split}
&\forall i \in [d]: \forall \epsilon_i>0: \exists N \in \mathbb{N}:  \forall n \geq N : |(x_n)_i - x^*|  \leq \epsilon_i \\
&\forall i \in [d]: |(x_n)_i - x^*|  \leq \epsilon \text{ with } \epsilon = \max_{i \in [d]} \epsilon_i \\
\Rightarrow& \forall i \in [d]: |(x_n)_i - x^*|^p  \leq \epsilon^p \\
\Rightarrow& \sum_{i \in [d]} |(x_n)_i - x^*|^p  \leq d \cdot \epsilon^p \\
\Rightarrow& \left(\sum_{i \in [d]} |(x_n)_i - x^*|^p\right)^{\frac{1}{p}}  \leq d^{\frac{1}{p}} \cdot \epsilon \\
\Rightarrow& ||x_n - x^*||_p \xrightarrow{n \rightarrow \infty} 0 \\
\end{split}
$$

### [[convergence]] for $l^{\infty}$ exactly when element wise [[convergence]]
- let the [[sequence]] $x_n \in {\mathbb{R}^d}$ 
$$
\begin{split}
&\forall \epsilon>0: \exists N \in \mathbb{N}:  \forall n \geq N : \max_{i \in [d]} |(x_n)_i - x^*_i| \leq \epsilon \\
\Rightarrow& \forall i \in [d] :  |(x_n)_i - x^*_i| \leq \cdot\epsilon \\
\Rightarrow& \forall i \in [n]: |(x_n)_i - x^*_i| \xrightarrow{n \rightarrow \infty} 0 \\
\end{split}
$$

$$
\begin{split}
&\forall i \in [n]: |(x_n)_i - x^*_i| \xrightarrow{n \rightarrow \infty} 0 \\
\Rightarrow& \forall i \in [d] : \forall \epsilon_i>0: \exists N \in \mathbb{N}:  \forall n \geq N : |(x_n)_i - x^*_i| \leq \epsilon_i \\
\Rightarrow& \max_{i \in [d]} |(x_n)_i - x^*_i| \leq \epsilon \text{ with } \epsilon = \max_{i \in [d]} \epsilon_i \\
\Rightarrow& ||(x_n)_i - x^*_i||_\infty \xrightarrow{n \rightarrow \infty} 0 \\
\end{split}
$$

# -----------------
![[norm#norm norms for $V subseteq mathbb{R} n$]]

![[limit#limit]]

# anki

START
Basic
definitions
- [[convergence]] in $\mathbb{R}$ with examples
- [[convergence]] in a [[normed space]] $\left(V, +, \cdot, ||\cdot||\right)$
- notations
Back: 
### convergence in $\mathbb{R}$
- given a [[sequence]] $a_n \in \mathbb{R}$  
- $a_n$ is converging against $a^*$ if the following is true

$$
\forall \epsilon>0: \exists N \in \mathbb{N}: n \geq N \Rightarrow |a_n - a^*| \leq \epsilon
$$

### convergence in a [[normed space]] $\left(V, +, \cdot, ||\cdot||\right)$
- given a [[sequence]] $v_n \in V$  
- $v_n$ is converging against $v^*$ if the following is true

$$
\begin{split}
&\forall \epsilon>0: \exists N \in \mathbb{N}: n \geq N \Rightarrow ||a_n - a^*|| \leq \epsilon \\
&\Leftrightarrow \\
&||v_n - v^* || \xrightarrow{n \rightarrow \infty} 0
\end{split}
$$
### [[convergence]] notations
$$
||v_n - v^* || \xrightarrow{n \rightarrow \infty} 0
$$
The following notations are equivalent:
$$
\lim_{n \rightarrow \infty} v_n  = v^*
$$
$$
v_n  \rightarrow v^*
$$
### examples [[convergence]]
- the followng [[sequence]] converges againt [[eulers number]]
$$
a_n =\left(1 + \frac{1}{n}\right)^n
$$
- converges against $0$
$$
a_n = \frac{1}{n}
$$

_______________________
### [[norm|norms]] for $V \subseteq \mathbb{R}^n$
#### $l^p$ [[norm]]

$$
||x||_p = \left(\sum_{i \in [n]} |x_i|^p \right)^{\frac{1}{p}}
$$
#### $l^1$ [[norm]]
$$
||x||_1 = \sum_{i \in [n]} |x_i| 
$$
#### euclidian [[norm]] ($l^2$)
$$
||x||_2 = \left(\sum_{i \in [n]} |x_i|^2 \right)^{\frac{1}{2}}
$$

#### infinity [[norm]] ($l^\infty$)
$$
||x||_\infty = \left(\sum_{i \in [n]} |x_i|^\infty \right)^{\frac{1}{\infty}} = \max_{i \in [n]} |x_i|
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

### vector space
a [[vector space]] $(V, +, \cdot)$ on a [[field]] $\mathbb{K}$ (e.g $\mathbb{R}$) is defined by 3 elements
1) a [[set]] $V$
2) a [[addition]] operation $+: V \times V \rightarrow V$
3) a [[multiplication]] operation $\cdot: \mathbb{K} \times V \rightarrow V$
- note: $v \in V$ is called [[vector]] and $\lambda \in \mathbb{K}$ is called a [[scalar]]

$(V, +, \cdot)$ is a [[vector space]] of the following conditions are true $u, v, w \in V$ and $\lambda, \mu \in \mathbb{K}$
1) $(V, +)$ is [[commutative]]: 
$$
v + w = w + v
$$
2) $(V, +)$ is [[associative]]: 
$$
(u + v) + w = u + (w + v)
$$

3) $(V, +)$ has a [[neutral element]] $0$ 
$$
v+0=v
$$
4) additive [[inverse elements]]
for every $v \in V$ has exists an additive [[inverse elements]] $v' \in V$ such that $v + v' = 0$

5) $(V, +, \cdot)$ are [[distributive]] for multiplications with scalars
$$
\begin{split}
\lambda \cdot (v + w) = \lambda \cdot v + \lambda \cdot w \\
v \cdot (\lambda + \mu) = v \cdot \lambda + v \cdot \mu
\end{split}
$$
6) $(V, \cdot)$ is [[associative]] with scalars 
$$
(\lambda \cdot \mu) + v = \lambda \cdot (\mu \cdot v)
$$
7) $(V, \cdot)$ has a [[neutral element]] $1$ 
$$
v \cdot 1 = v
$$


Tags: mathematics
<!--ID: 1714389589863-->
END


START
Basic
definitions
[[convergence]] of a [[sequence]] of [[function]]
- for the $L^1$ [[norm]]
- for the $L^\infty$ [[norm]]
- is it equivalent?
Back: 
### [[convergence]] of a [[sequence]] of [[function]]
- given a [[sequence]] of [[function|functions]] $f_n: [a,b] \rightarrow \mathbb{R}$ 

#### [[convergence]] for the $L^1$ [[norm]]
- $f_n$ converges to $f$ for the $L^1$ [[norm]] in the following is true
$$
||f_n - f ||_1 \rightarrow 0 \Leftrightarrow \int^b_a |f_n(x) - f(x)| dx \rightarrow 0
$$
#### [[convergence]] for the $L^p$ [[norm]]
- $f_n$ converges to $f$ for the $L^p$ [[norm]] in the following is true
$$
||f_n - f ||_p \rightarrow 0 \Leftrightarrow \left(\int^b_a |f_n(x) - f(x)|^p dx\right)^{\frac{1}{p}} \rightarrow 0
$$
#### [[convergence]] for the $L^\infty$ [[norm]]
- $f_n$ converges to $f$ for the $L^\infty$ [[norm]] in the following is true
$$
||f_n - f ||_\infty \rightarrow 0 \Leftrightarrow \max_{a \leq x \leq b} |f_n(x) - f(x)| dx \rightarrow 0
$$
- this means that the distance between the functions has to go to zero for the complete domain
#### $||f_n - f ||_\infty \rightarrow 0 \Rightarrow ||f_n - f ||_1 \rightarrow 0$ but not the other way around

_______________________
### [[norm]] for [[function space]] $f: \Omega \subset \mathbb{R}^d \rightarrow \mathbb{R}$ 
#### $L^p$ [[norm]]

$$
||f||_p = \left(\int_{\Omega} |f(x)|^p dx \right)^{\frac{1}{p}}
$$
#### $L^\infty$ [[norm]]
$$
||f||_\infty = \max_{x \in \Omega} |f(x)|
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
<!--ID: 1714411582368-->
END



START
Basic
how to prove that a [[sequence]] $a_n \in \mathbb{R}^n$ converges?

Back: 
### convergence in $\mathbb{R}^n$
- given a [[sequence]] $a_n \in \mathbb{R}^n$  
- $a_n$ is converging against $a^*\in \mathbb{R}^n$ if every element is converging
$$
a_n  \rightarrow a^* \Leftrightarrow \forall i \in [n]: a_i \rightarrow a^*_i
$$
_______________________
### convergence in $\mathbb{R}$
- given a [[sequence]] $a_n \in \mathbb{R}$  
- $a_n$ is converging against $a^*$ if the following is true

$$
\forall \epsilon>0: \exists N \in \mathbb{N}: n \geq N \Rightarrow |a_n - a^*| \leq \epsilon
$$

Tags: mathematics
<!--ID: 1714411582374-->
END


START
Basic
proof that [[convergence]] for $l^{p}$ implies element wise [[convergence]]
Back: 
- let the [[sequence]] $x_n \in {\mathbb{R}^d}$ converge for the $l^p$ [[norm]]
- then $x_n$ converges for all other $l$ norms too
$$
\begin{split}
&\forall \epsilon>0: \exists N \in \mathbb{N}:  \forall n \geq N :||x_n - x^*||_p \leq \epsilon \\
\Rightarrow&\forall \epsilon>0: \exists N \in \mathbb{N}:  \forall n \geq N :\left(\sum_{i \in [n]} |(x_n)_i - x^*_i|^p \right)^{\frac{1}{p}} \leq \epsilon \\
\Rightarrow& \sum_{i \in [n]} |(x_n)_i - x^*_i|^p  \leq \epsilon^p \\
\Rightarrow& \forall i \in [n]: |(x_n)_i - x^*_i|^p  \leq \epsilon^p \\
\Rightarrow& \forall i \in [n]: |(x_n)_i - x^*_i|  \leq \epsilon \\
\Rightarrow& \forall i \in [n]: |(x_n)_i - x^*_i| \xrightarrow{n \rightarrow \infty} 0 \\
\end{split}
$$

_______________________

### convergence in $\mathbb{R}$
- given a [[sequence]] $a_n \in \mathbb{R}$  
- $a_n$ is converging against $a^*$ if the following is true

$$
\forall \epsilon>0: \exists N \in \mathbb{N}: n \geq N \Rightarrow |a_n - a^*| \leq \epsilon
$$

### convergence in a [[normed space]] $\left(V, +, \cdot, ||\cdot||\right)$
- given a [[sequence]] $v_n \in V$  
- $v_n$ is converging against $v^*$ if the following is true

$$
\begin{split}
&\forall \epsilon>0: \exists N \in \mathbb{N}: n \geq N \Rightarrow ||a_n - a^*|| \leq \epsilon \\
&\Leftrightarrow \\
&||v_n - v^* || \xrightarrow{n \rightarrow \infty} 0
\end{split}
$$
### [[convergence]] notations
$$
||v_n - v^* || \xrightarrow{n \rightarrow \infty} 0
$$
The following notations are equivalent:
$$
\lim_{n \rightarrow \infty} v_n  = v^*
$$
$$
v_n  \rightarrow v^*
$$


### [[norm|norms]] for $V \subseteq \mathbb{R}^n$
#### $l^p$ [[norm]]

$$
||x||_p = \left(\sum_{i \in [n]} |x_i|^p \right)^{\frac{1}{p}}
$$
#### $l^1$ [[norm]]
$$
||x||_1 = \sum_{i \in [n]} |x_i| 
$$
#### euclidian [[norm]] ($l^2$)
$$
||x||_2 = \left(\sum_{i \in [n]} |x_i|^2 \right)^{\frac{1}{2}}
$$

#### infinity [[norm]] ($l^\infty$)
$$
||x||_\infty = \left(\sum_{i \in [n]} |x_i|^\infty \right)^{\frac{1}{\infty}} = \max_{i \in [n]} |x_i|
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

END


START
Basic
prove that element wise [[convergence]] implies $l^{p}$ [[convergence]]
Back: 

- let the [[sequence]] $x_n \in {\mathbb{R}^d}$ converge element wise $\forall i \in [d]: |(x_n)_i - x^*| \rightarrow 0$
- then $x_n$ converges for all other $l^p$ norms too
$$
\begin{split}
&\forall i \in [d]: \forall \epsilon_i>0: \exists N \in \mathbb{N}:  \forall n \geq N : |(x_n)_i - x^*|  \leq \epsilon_i \\
&\forall i \in [d]: |(x_n)_i - x^*|  \leq \epsilon \text{ with } \epsilon = \max_{i \in [d]} \epsilon_i \\
\Rightarrow& \forall i \in [d]: |(x_n)_i - x^*|^p  \leq \epsilon^p \\
\Rightarrow& \sum_{i \in [d]} |(x_n)_i - x^*|^p  \leq d \cdot \epsilon^p \\
\Rightarrow& \left(\sum_{i \in [d]} |(x_n)_i - x^*|^p\right)^{\frac{1}{p}}  \leq d^{\frac{1}{p}} \cdot \epsilon \\
\Rightarrow& ||x_n - x^*||_p \xrightarrow{n \rightarrow \infty} 0 \\
\end{split}
$$

_______________________

### convergence in $\mathbb{R}$
- given a [[sequence]] $a_n \in \mathbb{R}$  
- $a_n$ is converging against $a^*$ if the following is true

$$
\forall \epsilon>0: \exists N \in \mathbb{N}: n \geq N \Rightarrow |a_n - a^*| \leq \epsilon
$$

### convergence in a [[normed space]] $\left(V, +, \cdot, ||\cdot||\right)$
- given a [[sequence]] $v_n \in V$  
- $v_n$ is converging against $v^*$ if the following is true

$$
\begin{split}
&\forall \epsilon>0: \exists N \in \mathbb{N}: n \geq N \Rightarrow ||a_n - a^*|| \leq \epsilon \\
&\Leftrightarrow \\
&||v_n - v^* || \xrightarrow{n \rightarrow \infty} 0
\end{split}
$$
### [[convergence]] notations
$$
||v_n - v^* || \xrightarrow{n \rightarrow \infty} 0
$$
The following notations are equivalent:
$$
\lim_{n \rightarrow \infty} v_n  = v^*
$$
$$
v_n  \rightarrow v^*
$$


### [[norm|norms]] for $V \subseteq \mathbb{R}^n$
#### $l^p$ [[norm]]

$$
||x||_p = \left(\sum_{i \in [n]} |x_i|^p \right)^{\frac{1}{p}}
$$
#### $l^1$ [[norm]]
$$
||x||_1 = \sum_{i \in [n]} |x_i| 
$$
#### euclidian [[norm]] ($l^2$)
$$
||x||_2 = \left(\sum_{i \in [n]} |x_i|^2 \right)^{\frac{1}{2}}
$$

#### infinity [[norm]] ($l^\infty$)
$$
||x||_\infty = \left(\sum_{i \in [n]} |x_i|^\infty \right)^{\frac{1}{\infty}} = \max_{i \in [n]} |x_i|
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

END


START
Basic
prove that [[convergence]] for $l^{\infty}$ exactly when element wise [[convergence]]
Back: 
- let the [[sequence]] $x_n \in {\mathbb{R}^d}$ 
$$
\begin{split}
&\forall \epsilon>0: \exists N \in \mathbb{N}:  \forall n \geq N : \max_{i \in [d]} |(x_n)_i - x^*_i| \leq \epsilon \\
\Rightarrow& \forall i \in [d] :  |(x_n)_i - x^*_i| \leq \cdot\epsilon \\
\Rightarrow& \forall i \in [n]: |(x_n)_i - x^*_i| \xrightarrow{n \rightarrow \infty} 0 \\
\end{split}
$$

$$
\begin{split}
&\forall i \in [n]: |(x_n)_i - x^*_i| \xrightarrow{n \rightarrow \infty} 0 \\
\Rightarrow& \forall i \in [d] : \forall \epsilon_i>0: \exists N \in \mathbb{N}:  \forall n \geq N : |(x_n)_i - x^*_i| \leq \epsilon_i \\
\Rightarrow& \max_{i \in [d]} |(x_n)_i - x^*_i| \leq \epsilon \text{ with } \epsilon = \max_{i \in [d]} \epsilon_i \\
\Rightarrow& ||(x_n)_i - x^*_i||_\infty \xrightarrow{n \rightarrow \infty} 0 \\
\end{split}
$$

_______________________

### convergence in $\mathbb{R}$
- given a [[sequence]] $a_n \in \mathbb{R}$  
- $a_n$ is converging against $a^*$ if the following is true

$$
\forall \epsilon>0: \exists N \in \mathbb{N}: n \geq N \Rightarrow |a_n - a^*| \leq \epsilon
$$

### convergence in a [[normed space]] $\left(V, +, \cdot, ||\cdot||\right)$
- given a [[sequence]] $v_n \in V$  
- $v_n$ is converging against $v^*$ if the following is true

$$
\begin{split}
&\forall \epsilon>0: \exists N \in \mathbb{N}: n \geq N \Rightarrow ||a_n - a^*|| \leq \epsilon \\
&\Leftrightarrow \\
&||v_n - v^* || \xrightarrow{n \rightarrow \infty} 0
\end{split}
$$
### [[convergence]] notations
$$
||v_n - v^* || \xrightarrow{n \rightarrow \infty} 0
$$
The following notations are equivalent:
$$
\lim_{n \rightarrow \infty} v_n  = v^*
$$
$$
v_n  \rightarrow v^*
$$


### [[norm|norms]] for $V \subseteq \mathbb{R}^n$
#### $l^p$ [[norm]]

$$
||x||_p = \left(\sum_{i \in [n]} |x_i|^p \right)^{\frac{1}{p}}
$$
#### $l^1$ [[norm]]
$$
||x||_1 = \sum_{i \in [n]} |x_i| 
$$
#### euclidian [[norm]] ($l^2$)
$$
||x||_2 = \left(\sum_{i \in [n]} |x_i|^2 \right)^{\frac{1}{2}}
$$

#### infinity [[norm]] ($l^\infty$)
$$
||x||_\infty = \left(\sum_{i \in [n]} |x_i|^\infty \right)^{\frac{1}{\infty}} = \max_{i \in [n]} |x_i|
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

END