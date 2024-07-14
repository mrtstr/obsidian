### taylor series $f: \mathbb{R} \to \mathbb{R}$ 
- [[series]] that apploximates a [[function]] $f: \mathbb{R} \to \mathbb{R}$ with a [[power series]] concideres at a point $x_0$ 
$$
\begin{split}
\widehat{f}(x, x_0) 
&= \sum_{n=0}^\infty 
\frac{1}{n!}
\left. \frac{d^n f(x)}{d^n x} \right|_{x=x_0}
 \left(x-x_0\right)^n \\
&= \sum_{n=0}^\infty a_n (x-x_0)^n \text{ with }a_n=\frac{1}{n!}
\left. \frac{d^n f(x)}{d^n x} \right|_{x=x_0}
\end{split}
\tag{taylor series}
$$
- if [[function]] $f$ is an [[analytic function]] $\widehat{f}(x, x_0)$ converges to $f(x)$ in each $x$



### taylor apploximation $f: \mathbb{R} \to \mathbb{R}$ 
- when stopping the [[taylor series]] at a specific $n=k$ it's an approximation of $f$ with a [[polynomial]] $kth$ grade
- the higher the $k$ the more accureate the apploximation will be
$$
\begin{split}
\widehat{f_k}(x, x_0) 
&= \sum_{n=0}^k 
\frac{1}{n!}
\left. \frac{d^n f(x)}{d^n x} \right|_{x=x_0}
 \left(x-x_0\right)^n \\
\end{split}
\tag{taylor approximation}
$$
### second degree taylor apploximation $f: \mathbb{R}^m \to \mathbb{R}$

$$
\begin{split}
\widehat{f_k}(x, x_0) 
&= \sum_{n=0}^k 
f(x_0) + \nabla f(x_0)^\top x + \frac{1}{2} \nabla  x^\top f(x_0) x + o(||x||^2)
\end{split}

$$


# anki


START
Basic
second taylor apploximation $f: \mathbb{R}^m \to \mathbb{R}$: definition
Back: 
### second taylor apploximation $f: \mathbb{R}^m \to \mathbb{R}$

$$
\begin{split}
\widehat{f_k}(x, x_0) 
&= \sum_{n=0}^k 
f(x_0) + \nabla f(x_0)^\top x + \frac{1}{2} \nabla  x^\top f(x_0) x + o(||x||^2)
\end{split}

$$

Tags: mathematics
<!--ID: 1720949577274-->
END

START
Basic
[[taylor series]] of $f: \mathbb{R} \to \mathbb{R}$: definition
Back: 
### taylor series $f: \mathbb{R} \to \mathbb{R}$ 
- [[series]] that apploximates a [[function]] $f(x)$ with a [[power series]] concideres at a point $x_0$ 
$$
\begin{split}
\widehat{f}(x, x_0) 
&= \sum_{n=0}^\infty 
\frac{1}{n!}
\left. \frac{d^n f(x)}{d^n x} \right|_{x=x_0}
 \left(x-x_0\right)^n \\
&= \sum_{n=0}^\infty a_n (x-x_0)^n \text{ with }a_n=\frac{1}{n!}
\left. \frac{d^n f(x)}{d^n x} \right|_{x=x_0}
\end{split}
\tag{taylor series}
$$
- if [[function]] $f$ is an [[analytic function]] $\widehat{f}(x, x_0)$ converges to $f(x)$ in each $x$

Tags: mathematics
<!--ID: 1690103676760-->
END

START
Basic
definition of the taylor aproximation of $f: \mathbb{R} \to \mathbb{R}$ 
Back: 
### taylor apploximation $f: \mathbb{R} \to \mathbb{R}$ 
- when stopping the [[taylor series]] at a specific $n=k$ it's an approximation of $f$ with a [[polynomial]] $kth$ grade
- the higher the $k$ the more accureate the apploximation will be
$$
\begin{split}
\widehat{f_k}(x, x_0) 
&= \sum_{n=0}^k 
\frac{1}{n!}
\left. \frac{d^n f(x)}{d^n x} \right|_{x=x_0}
 \left(x-x_0\right)^n \\
\end{split}
\tag{taylor approximation}
$$

Tags: mathematics
<!--ID: 1690103676765-->
END