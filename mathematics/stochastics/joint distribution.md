### joint distribution
- a collection of [[random variable|random variables]] $X_1: \Omega \to \mathbb{R}, ..., X_n: \Omega \to \mathbb{R}$ can be concidered as a single [[random variable]] $X: \Omega^n \to \mathbb{R}^n$ with a joint [[sample space]] $\Omega =\Omega_1 \times ... \times \Omega_n$ and a [[joint distribution]] $\mathcal{P}_X: \mathcal{B}\left(\mathbb{R}^n\right) \to [0,1]$

$$
\begin{split}
\mathcal{P}_X(B) 
&= \mathbb{P}(X^{-1}(\omega) \in B) \\
&= \left\{
\begin{pmatrix}   
\omega_1 \\   ... \\ \omega_n 
\end{pmatrix} 
:
\begin{pmatrix}   
X(\omega_1) \\   ... \\ X(\omega_n)
\end{pmatrix} 
 \in B \
\right\}  \\
\end{split}
$$



![[1920px-Multivariate_normal_sample.svg-1.png]]

### joint [[cumulative distribution function (CDF)]]
- a [[random variable]] with a [[joint distribution]] $\mathcal{P}_X$ has a joint [[cumulative distribution function (CDF)]] $F_X(x_1, ..., x_n): \mathbb{R}^n \to [0,1]$
$$
\begin{split}
F_X(x_1, ..., x_n)
&=\mathcal{P}_X\left((-\infty, x_1] \times ... \times (-\infty, x_n]\right) \\
&=\mathbb{P}(X_1 \leq x_1, ..., X_n \leq x_n)
\end{split}
$$

### joint [[probability density function (PDF)]] 
- a [[continuous probability space|continuous]] [[random variable]] with a [[differentiabe]] joint [[cumulative distribution function (CDF)]] $f_X(x_1, ..., x_n): \mathbb{R}^n \to [0,1]$ has joint [[probability density function (PDF)]] 
$$
\begin{split}
f_X(x_1, ..., x_n)
&=\frac{\partial^n F_X(x_1, ..., x_n)}{\partial x_1...\partial x_n} 
\end{split}
$$

### margianl [[probability density function (PDF)]] 
- given a [[continuous probability space|continuous]] [[random variable]] with a joint [[probability density function (PDF)]]  $f_X(x_1, ..., x_n): \mathbb{R}^n \to [0,1]$
- the [[probability density function (PDF)]] of one of its components can be calculated by intergrating over all other [[random variable|random variables]]
- this is called the marginal probability density function
$$
\begin{split}
f_{X_1}(x_1) 
= \int_{-\infty}^\infty... \int_{-\infty}^\infty f_X(x_1, ..., x_n) \mathrm{d}x_2 ... \mathrm{d}x_n
\end{split}
$$



### properties
- Joint PDFs encode the marginal distributions of each [[probability mass function (PMF)]]
$$f_X(x) = \int\limits_{-\infty}^{\infty} f_{XY}(x,y) \: dy$$
$$
f_{X_1}(x_1) = 
\int\limits_{-\infty}^{\infty}
...
\int\limits_{-\infty}^{\infty}
f_{\boldsymbol{X}}(\boldsymbol{x}) 
\: dx_{2} ... dx_n
$$
- for [[stochastic independent]] [[random variable]] the [[joint distribution]] is the product of the [[probability density function (PDF)|PDFs]]
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


# -----------------------

![[distribution#distribution]]

# anki

START
Basic
[[joint distribution]]: formal definition
Back: 
### joint distribution
- a collection of [[random variable|random variables]] $X_1: \Omega \to \mathbb{R}, ..., X_n: \Omega \to \mathbb{R}$ can be concidered as a single [[random variable]] $X: \Omega^n \to \mathbb{R}^n$ with a joint [[sample space]] $\Omega =\Omega_1 \times ... \times \Omega_n$ and a [[joint distribution]] $\mathcal{P}_X: \mathcal{B}\left(\mathbb{R}^n\right) \to [0,1]$

$$
\begin{split}
\mathcal{P}_X(B) 
&= \mathbb{P}(X^{-1}(\omega) \in B) \\
&= \left\{
\begin{pmatrix}   
\omega_1 \\   ... \\ \omega_n 
\end{pmatrix} 
:
\begin{pmatrix}   
X(\omega_1) \\   ... \\ X(\omega_n)
\end{pmatrix} 
 \in B \
\right\}  \\
\end{split}
$$
_________________________

### distribution
- given a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$ and a [[random variable]] $X: \Omega \to \mathbb{R}$ (which is a [[measurable function]] $X: (\Omega, \mathcal{A}) \to \left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$)
- $X$ is inducing the [[probability measure]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ from the [[borel sigma algebra]] $\mathcal{B}(\mathbb{R})$ it the interval $[0,1]$ (assigning a probability to each borel set $\subset \mathbb{R}$)
- $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ is called the [[distribution]] of $X$ and exists for every [[random variable]] 
$$
\begin{split}
\mathcal{P}_X(C) 
&= \mathbb{P}\left(X^{-1}(C \subseteq \mathbb{R})\right) \\
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) \in C\right\}\right) \\
\end{split}
$$

Tags: mathematics statistics
<!--ID: 1670766688737-->
END


START
Basic
- joint [[cumulative distribution function (CDF)]]
- joint [[probability density function (PDF)]] 
- margianl [[probability density function (PDF)]] 
Back: 


### joint [[cumulative distribution function (CDF)]]
- a [[random variable]] with a [[joint distribution]] $\mathcal{P}_X$ has a joint [[cumulative distribution function (CDF)]] $F_X(x_1, ..., x_n): \mathbb{R}^n \to [0,1]$
$$
\begin{split}
F_X(x_1, ..., x_n)
&=\mathcal{P}_X\left((-\infty, x_1] \times ... \times (-\infty, x_n]\right) \\
&=\mathbb{P}(X_1 \leq x_1, ..., X_n \leq x_n)
\end{split}
$$

### joint [[probability density function (PDF)]] 
- a [[continuous probability space|continuous]] [[random variable]] with a [[differentiabe]] joint [[cumulative distribution function (CDF)]] $f_X(x_1, ..., x_n): \mathbb{R}^n \to [0,1]$ has joint [[probability density function (PDF)]] 
$$
\begin{split}
f_X(x_1, ..., x_n)
&=\frac{\partial^n F_X(x_1, ..., x_n)}{\partial x_1...\partial x_n} 
\end{split}
$$

### margianl [[probability density function (PDF)]] 
- given a [[continuous probability space|continuous]] [[random variable]] with a joint [[probability density function (PDF)]]  $f_X(x_1, ..., x_n): \mathbb{R}^n \to [0,1]$
- the [[probability density function (PDF)]] of one of its components can be calculated by intergrating over all other [[random variable|random variables]]
- this is called the marginal probability density function
$$
\begin{split}
f_{X_1}(x_1) 
= \int_{-\infty}^\infty... \int_{-\infty}^\infty f_X(x_1, ..., x_n) \mathrm{d}x_2 ... \mathrm{d}x_n
\end{split}
$$

___________________

### joint distribution
- a collection of [[random variable|random variables]] $X_1: \Omega \to \mathbb{R}, ..., X_n: \Omega \to \mathbb{R}$ can be concidered as a single [[random variable]] $X: \Omega^n \to \mathbb{R}^n$ with a joint [[sample space]] $\Omega =\Omega_1 \times ... \times \Omega_n$ and a [[joint distribution]] $\mathcal{P}_X: \mathcal{B}\left(\mathbb{R}^n\right) \to [0,1]$

$$
\begin{split}
\mathcal{P}_X(B) 
&= \mathbb{P}(X^{-1}(\omega) \in B) \\
&= \left\{
\begin{pmatrix}   
\omega_1 \\   ... \\ \omega_n 
\end{pmatrix} 
:
\begin{pmatrix}   
X(\omega_1) \\   ... \\ X(\omega_n)
\end{pmatrix} 
 \in B \
\right\}  \\
\end{split}
$$

Tags: mathematics statistics
<!--ID: 1717943752211-->
END





START
Basic
properties (5) of the [[probability density function (PDF)|continuous joint PDF]] or the bivariante [[random variable]] $X,Y$ with the [[probability density function (PDF)]] $f_{XY}(x,y)$ and the multivariate [[random variable]] $\boldsymbol{X} =X_1,...,X_n$ with the [[probability density function (PDF)]] $f_{\boldsymbol{X}}(\boldsymbol{x})$.
- [[marginal distribution]]
- [[stochastic independent]] case
- normalization
- [[probability]] of the [[random variable]] being in a [[set]] $C$
- [[probability]] of the [[random variable]] being in a non [[countable]] [[set]] $C$

Back: 


- Joint PDFs encode the marginal distributions of each [[probability mass function (PMF)]]
$$f_X(x) = \int\limits_{-\infty}^{\infty} f_{XY}(x,y) \: dy$$
$$
f_{X_1}(x_1) = 
\int\limits_{-\infty}^{\infty}
...
\int\limits_{-\infty}^{\infty}
f_{\boldsymbol{X}}(\boldsymbol{x}) 
\: dx_{2} ... dx_n
$$
- for [[stochastic independent]] [[random variable]] the [[joint distribution]] is the product of the [[probability density function (PDF)|PDFs]]
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
[[cumulative distribution function (CDF)|joint CDF]]:
For the bivariante [[random variable]] $X,Y$ with the [[cumulative distribution function (CDF)|joint CDF]] $F_{XY}(x,y)$ and the multivariate [[random variable]] $\boldsymbol{X} =X_1,...,X_n$ with the [[cumulative distribution function (CDF)|joint CDF]] $F_{\boldsymbol{X}}(\boldsymbol{x})$.
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