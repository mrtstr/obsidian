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
With the [[vector notation]] $\boldsymbol{X} =X_1,...,X_n$ this is equivalent to the following 
$$
\boldsymbol{X} \in C  = 
\left\{\omega\mid 
\boldsymbol{X}(\boldsymbol{\omega}) 
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
$$
\left\{P(\boldsymbol{X} \in C) \mid C \subseteq \mathbb{R}^n \right\} = \left\{P\left(
\left\{
\boldsymbol{\omega}
\mid 
\boldsymbol{X}(\boldsymbol{\omega})
 \in C\right\} \right)
\mid C \subseteq \mathbb{R}^n\right\}
$$


![[1920px-Multivariate_normal_sample.svg-1.png]]

## Joint [[probability density function]] 

For the bivariante [[random variable]] $X,Y$ with the [[probability density function]] $f_{XY}(x,y)$ and the multivariate [[random variable]] $\boldsymbol{X} =X_1,...,X_n$ with the [[probability density function]] $f_{\boldsymbol{X}}(\boldsymbol{x})$.

- Joint PDFs encode the marginal distributions of each [[discrete random variable]]
$$f_X(x) = \int\limits_{-\infty}^{\infty} f_{XY}(x,y) \: dy$$
$$
f_{X_1}(x_1) = 
\int\limits_{-\infty}^{\infty}
...
\int\limits_{-\infty}^{\infty}
f_{\boldsymbol{X}}(\boldsymbol{x}) 
\: dx_{2} ... dx_n
$$
- for [[stochastic independent]] [[random variable]] the [[joint distribution]] is the product of the [[probability density function|PDFs]]
$$
X \perp Y \Leftrightarrow f_{XY}(x, y) = f_X(x)f_Y(y)
$$
$$
\perp \boldsymbol{X} \Leftrightarrow f_{\boldsymbol{X}}(\boldsymbol{x}) = \prod\limits_{i=1}^n f_{X_i}(x_i)
$$
- the integral over the [[joint distribution|joint PDF]] is normalized
$$
\int\limits_{-\infty}^{\infty}
\int\limits_{-\infty}^{\infty}
f_{XY}(x, y) dx dy = 1.
$$
$$
\int\limits_{-\infty}^{\infty}
...
\int\limits_{-\infty}^{\infty}
f_{\boldsymbol{X}}(\boldsymbol{x}) 
\: d\boldsymbol{x} = 1.
$$
- for every [[set]] $C$ the integral over $C$ is non-negative
$$
P\left((X,Y) \in C \subseteq \mathbb{R}^2\right)
=
\int\limits_{c_1}
\int\limits_{c_2}
f_{XY}(x, y) dx dy
\geq 0
$$
$$
P\left(\boldsymbol{X} \in C \subseteq \mathbb{R}^n\right)
=
\int\limits_{C}
f_{\boldsymbol{X}}(\boldsymbol{x}) d\boldsymbol{x}
\geq 0
$$
- for every non [[countable]] [[set]] $C$ the following is true
$$
P\left((X,Y) \in C \subseteq \mathbb{R}^2\right)
=
\int\limits_{c_1}
\int\limits_{c_2}
f_{XY}(x, y) dx dy
= 0
$$
$$
P\left(\boldsymbol{X} \in C \subseteq \mathbb{R}^n\right)
=
\int\limits_{C}
f_{\boldsymbol{X}}(\boldsymbol{x}) d\boldsymbol{x}
 = 0
$$
![[Screenshot from 2022-12-11 11-08-42.png]]


## Joint [[CDF]]
For the bivariante [[random variable]] $X,Y$ with the [[CDF|joint CDF]] $F_{XY}(x,y)$ and the multivariate [[random variable]] $\boldsymbol{X} =X_1,...,X_n$ with the [[CDF|joint CDF]] $F_{\boldsymbol{X}}(\boldsymbol{x})$.

- $F_{XY}(x,y)=P(X \leq x, Y \leq y)$ and $F_{\boldsymbol{X}}(\boldsymbol{x})=P(X_1 \leq x_1, ..., X_n \leq x_n)$
- $X \perp Y \Leftrightarrow F_{XY}(x, y) = F_X(x)F_Y(y)$ and $\perp \boldsymbol{X} \Leftrightarrow F_{\boldsymbol{X}}(\boldsymbol{x}) = \prod\limits_{i=1}^n F_{X_i}(x_i)$
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
With the [[vector notation]] $\boldsymbol{X} =X_1,...,X_n$ this is equivalent to the following 
$$
\boldsymbol{X} \in C  = 
\left\{\omega\mid 
\boldsymbol{X}(\boldsymbol{\omega}) 
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
$$
\left\{P(\boldsymbol{X} \in C) \mid C \subseteq \mathbb{R}^n \right\} = \left\{P\left(
\left\{
\boldsymbol{\omega}
\mid 
\boldsymbol{X}(\boldsymbol{\omega})
 \in C\right\} \right)
\mid C \subseteq \mathbb{R}^n\right\}
$$


Tags: mathematics statistics
<!--ID: 1670766688737-->
END


START
Basic
properties (5) of the [[probability density function|continuous joint PDF]] or the bivariante [[random variable]] $X,Y$ with the [[probability density function]] $f_{XY}(x,y)$ and the multivariate [[random variable]] $\boldsymbol{X} =X_1,...,X_n$ with the [[probability density function]] $f_{\boldsymbol{X}}(\boldsymbol{x})$.
- [[marginal distribution]]
- [[stochastic independent]] case
- normalization
- [[probability]] of the [[random variable]] being in a [[set]] $C$
- [[probability]] of the [[random variable]] being in a non [[countable]] [[set]] $C$

Back: 


- Joint PDFs encode the marginal distributions of each [[discrete random variable]]
$$f_X(x) = \int\limits_{-\infty}^{\infty} f_{XY}(x,y) \: dy$$
$$
f_{X_1}(x_1) = 
\int\limits_{-\infty}^{\infty}
...
\int\limits_{-\infty}^{\infty}
f_{\boldsymbol{X}}(\boldsymbol{x}) 
\: dx_{2} ... dx_n
$$
- for [[stochastic independent]] [[random variable]] the [[joint distribution]] is the product of the [[probability density function|PDFs]]
$$
X \perp Y \Leftrightarrow f_{XY}(x, y) = f_X(x)f_Y(y)
$$
$$
\perp \boldsymbol{X} \Leftrightarrow f_{\boldsymbol{X}}(\boldsymbol{x}) = \prod\limits_{i=1}^n f_{X_i}(x_i)
$$
- the integral over the [[joint distribution|joint PDF]] is normalized
$$
\int\limits_{-\infty}^{\infty}
\int\limits_{-\infty}^{\infty}
f_{XY}(x, y) dx dy = 1.
$$
$$
\int\limits_{-\infty}^{\infty}
...
\int\limits_{-\infty}^{\infty}
f_{\boldsymbol{X}}(\boldsymbol{x}) 
\: d\boldsymbol{x} = 1.
$$
- for every [[set]] $C$ the integral over $C$ is non-negative
$$
P\left((X,Y) \in C \subseteq \mathbb{R}^2\right)
=
\int\limits_{c_1}
\int\limits_{c_2}
f_{XY}(x, y) dx dy
\geq 0
$$
$$
P\left(\boldsymbol{X} \in C \subseteq \mathbb{R}^n\right)
=
\int\limits_{C}
f_{\boldsymbol{X}}(\boldsymbol{x}) d\boldsymbol{x}
\geq 0
$$
- for every non [[countable]] [[set]] $C$ the following is true
$$
P\left((X,Y) \in C \subseteq \mathbb{R}^2\right)
=
\int\limits_{c_1}
\int\limits_{c_2}
f_{XY}(x, y) dx dy
= 0
$$
$$
P\left(\boldsymbol{X} \in C \subseteq \mathbb{R}^n\right)
=
\int\limits_{C}
f_{\boldsymbol{X}}(\boldsymbol{x}) d\boldsymbol{x}
 = 0
$$
![[Screenshot from 2022-12-11 11-08-42.png]]


Tags: mathematics statistics
<!--ID: 1670766688739-->
END


START
Basic
[[CDF|joint CDF]]:
For the bivariante [[random variable]] $X,Y$ with the [[CDF|joint CDF]] $F_{XY}(x,y)$ and the multivariate [[random variable]] $\boldsymbol{X} =X_1,...,X_n$ with the [[CDF|joint CDF]] $F_{\boldsymbol{X}}(\boldsymbol{x})$.
- definition
- of [[stochastic independent]] [[random variable]]
- marginal CDF
Back: 

- $F_{XY}(x,y)=P(X \leq x, Y \leq y)$ and $F_{\boldsymbol{X}}(\boldsymbol{x})=P(X_1 \leq x_1, ..., X_n \leq x_n)$
- $X \perp Y \Leftrightarrow F_{XY}(x, y) = F_X(x)F_Y(y)$ and $\perp \boldsymbol{X} \Leftrightarrow F_{\boldsymbol{X}}(\boldsymbol{x}) = \prod\limits_{i=1}^n F_{X_i}(x_i)$
$$
F_X(x)=\lim\limits_{y \rightarrow \infty}F_{XY}(x,y) = 
\int\limits_{-\infty}^{x}
\int\limits_{-\infty}^{\infty}
f_{XY}(x, y) dy dx
$$


Tags: mathematics statistics
<!--ID: 1670766688742-->
END