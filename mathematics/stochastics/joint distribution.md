Let $X_1,...,X_n$ be [[random variable|random variables]]. We can define a joint [[sample space]] $\Omega =\Omega_1 \times ... \times \Omega_n$ and a joint [[event space]] $\mathcal{F}=\mathcal{P}(\Omega)$. For every $C \subseteq \mathbb{R}^n$ we can define an [[event]] $\in \mathcal{F}$.

$$

X_1,...,X_n \in C  = 

\left\{
\begin{pmatrix}   
\omega_1 \\   ... \\ \omega_n 
\end{pmatrix} 
\mid 
\begin{pmatrix}   
X(\omega_1) \\   ... \\ X(\omega_n)
\end{pmatrix} 
 \in C
\right\} 
\in \mathcal{F}
$$

The [[joint distribution]] is a collection of all probabilities of the [[event|events]] for all $C \subseteq \mathbb{R}^n$

$$
\left\{P((X_1,...,X_n) \in C) \mid C \subseteq \mathbb{R}^n \right\} = \left\{P\left(
\left\{
\begin{pmatrix}   
\omega_1 \\   ... \\ \omega_n 
\end{pmatrix} 
\mid 
\begin{pmatrix}   
X(\omega_1) \\   ... \\ X(\omega_n)
\end{pmatrix} 
 \in C\right\} \right)
\mid C \subseteq \mathbb{R}^n\right\}
$$


![[1920px-Multivariate_normal_sample.svg-1.png]]

## Joint [[continuous PDF]] $f_{XY}(x,y)$
- Joint PDFs encode the marginal distributions of each [[discrete random variable]]
$$f_X(x) = \int\limits_{-\infty}^{\infty} f_{XY}(x,y) \: dy$$
- for [[stochastic independent]] [[random variable]] the [[joint distribution]] is the product of the [[continuous PDF|PDFs]]
$$X \perp Y \Leftrightarrow f_{XY}(x, y) = f_X(x)f_Y(y)$$
- the integral over the [[joint distribution|joint PDF]] is normalized
$$
\int\limits_{-\infty}^{\infty}
\int\limits_{-\infty}^{\infty}
f_{XY}(x, y) dx dy = 1.
$$
- for every [[set]] $C$ the integral over $C$ is non-negative
$$
P\left((X,Y) \in C\right)
=
\int\limits_{c_1}
\int\limits_{c_2}
f_{XY}(x, y) dx dy
\geq 0
$$
- for every [[countable]] [[set]] $C$ the following is true
$$
P\left((X,Y) \in C\right)
=
\int\limits_{c_1}
\int\limits_{c_2}
f_{XY}(x, y) dx dy
= 0
$$
![[Screenshot from 2022-12-11 11-08-42.png]]


## Joint [[CDF]] $F_{XY}(x,y)$
- $F_{XY}(x,y)=P(X \leq x, Y \leq y)$ 
- $X \perp Y \Leftrightarrow F_{XY}(x, y) = F_X(x)F_Y(y)$ 
$$
F_X(x)=\lim\limits_{y \rightarrow \infty}F_{XY}(x,y) = 
\int\limits_{-\infty}^{x}
\int\limits_{-\infty}^{\infty}
f_{XY}(x, y) dy dx
$$

# anki

START
Basic
[[joint distribution]]: formal definition
Back: 
Let $X_1,...,X_n$ be [[random variable|random variables]]. We can define a joint [[sample space]] $\Omega =\Omega_1 \times ... \times \Omega_n$ and a joint [[event space]] $\mathcal{F}=\mathcal{P}(\Omega)$. For every $C \subseteq \mathbb{R}^n$ we can define an [[event]] $\in \mathcal{F}$.

$$

X_1,...,X_n \in C  = 

\left\{
\begin{pmatrix}   
\omega_1 \\   ... \\ \omega_n 
\end{pmatrix} 
\mid 
\begin{pmatrix}   
X(\omega_1) \\   ... \\ X(\omega_n)
\end{pmatrix} 
 \in C
\right\} 
\in \mathcal{F}
$$

The [[joint distribution]] is a collection of all probabilities of the [[event|events]] for all $C \subseteq \mathbb{R}^n$

$$
\left\{P((X_1,...,X_n) \in C) \mid C \subseteq \mathbb{R}^n \right\} = \left\{P\left(
\left\{
\begin{pmatrix}   
\omega_1 \\   ... \\ \omega_n 
\end{pmatrix} 
\mid 
\begin{pmatrix}   
X(\omega_1) \\   ... \\ X(\omega_n)
\end{pmatrix} 
 \in C\right\} \right)
\mid C \subseteq \mathbb{R}^n\right\}
$$

Tags: mathematics, statistics
<!--ID: 1670766688737-->
END


START
Basic
Joint [[continuous PDF]] $f_{XY}(x,y)$: properties (5)
Back: 
## 
- Joint PDFs encode the marginal distributions of each [[discrete random variable]]
$$f_X(x) = \int\limits_{-\infty}^{\infty} f_{XY}(x,y) \: dy$$
- for [[stochastic independent]] [[random variable]] the [[joint distribution]] is the product of the [[continuous PDF|PDFs]]
$$X \perp Y \Leftrightarrow f_{XY}(x, y) = f_X(x)f_Y(y)$$
- the integral over the [[joint distribution|joint PDF]] is normalized
$$
\int\limits_{-\infty}^{\infty}
\int\limits_{-\infty}^{\infty}
f_{XY}(x, y) dx dy = 1.
$$
- for every [[set]] $C$ the integral over $C$ is non-negative
$$
P\left((X,Y) \in C\right)
=
\int\limits_{c_1}
\int\limits_{c_2}
f_{XY}(x, y) dx dy
\geq 0
$$
- for every [[countable]] [[set]] $C$ the following is true
$$
P\left((X,Y) \in C\right)
=
\int\limits_{c_1}
\int\limits_{c_2}
f_{XY}(x, y) dx dy
= 0
$$
![[Screenshot from 2022-12-11 11-08-42.png]]


Tags: mathematics, statistics
<!--ID: 1670766688739-->
END

Joint [[CDF]] $F_{XY}(x,y)$
START
Basic
Joint [[CDF]] $F_{XY}(x,y)$: 
- definition
- of [[stochastic independent]] [[random variable]]
- marginal CDF
Back: 

- $F_{XY}(x,y)=P(X \leq x, Y \leq y)$ 
- $X \perp Y \Leftrightarrow F_{XY}(x, y) = F_X(x)F_Y(y)$ 
$$
F_X(x)=\lim\limits_{y \rightarrow \infty}F_{XY}(x,y) = 
\int\limits_{-\infty}^{x}
\int\limits_{-\infty}^{\infty}
f_{XY}(x, y) dy dx
$$

Tags: mathematics, statistics
<!--ID: 1670766688742-->
END