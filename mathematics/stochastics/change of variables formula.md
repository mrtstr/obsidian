### change of variables formula
- given a [[measurable space]] and the [[random variable]] $X: \Omega \to \mathbb{R}^n$ and the [[inverse function|invertable]] [[differentiable]] function $f: \mathbb{R}^n \to \mathbb{R}^m$
- the [[probability density function (PDF)]] $Y=f(X)$ is given by the following 

$$
\begin{split}
p_Y(y) &= p_X\left(f^{-1}(y)\right) \cdot \left|\frac{df^{-1}(y)}{dy} \right| \\
p_Y(y) &= p_X\left(f^{-1}(y)\right) \cdot \left|\det\nabla f^{-1}\right|
\end{split}
$$
#### proof
based on the definition of the [[lebesgue measure]] as a volume measure

$$
\lambda\left(f^{-1}\left(B_\epsilon(y)\right)\right) 
\approx \lambda\left(B_\epsilon(y)\right) \cdot \left|\det \nabla f^{-1}\left(y\right)\right| \quad \text{as } \epsilon \to 0
$$

$$
\begin{split}
\int_{f^{-1}\left(B_\epsilon (y)\right)} p_X(x) dx 
&=  p_X\left(f^{-1}\left(y\right)\right) \lambda\left(f^{-1}\left(B_\epsilon (y)\right)\right)  \\
&=  p_X\left(f^{-1}\left(y\right)\right) \lambda\left(B_\epsilon(y)\right) \cdot \left|\det \nabla f^{-1}\left(y\right)\right|    \\
\end{split}
$$

$$
\begin{split}
p_Y(y) 
&= \frac{\mathbb{P}\left(Y \in B_\epsilon (y)\right)}{\lambda\left(B_\epsilon (y)\right)} \\
&= \frac{\mathbb{P}\left(X \in f^{-1}\left(B_\epsilon (y)\right)\right)}{\lambda\left(B_\epsilon (y)\right)} \\
&= \frac{1}{\lambda\left(B_\epsilon (y)\right)} \int_{f^{-1}\left(B_\epsilon (y)\right)} p_X(x) dx \\
&= \frac{1}{\lambda\left(B_\epsilon (y)\right)} p_X\left(f^{-1}\left(y\right)\right) \lambda\left(B_\epsilon(y)\right) \cdot \left|\det \nabla f^{-1}\left(y\right)\right|    \\
&=  p_X\left(f^{-1}\left(y\right)\right)  \cdot \left|\det \nabla f^{-1}\left(y\right)\right|    \\
\end{split}
$$

# -----------------

![[lebesgue measure#lebesgue measure]]

![[radon nikodym theorem#radon nikodym theorem]]


# anki

# anki

START
Basic
[[change of variables formula]] with proof

Back: 
### change of variables formula
- given a [[measurable space]] and the [[random variable]] $X: \Omega \to \mathbb{R}^n$ and the [[inverse function|invertable]] [[differentiable]] function $f: \mathbb{R}^n \to \mathbb{R}^m$
- the [[probability density function (PDF)]] $Y=f(X)$ is given by the following 

$$
\begin{split}
p_Y(y) &= p_X\left(f^{-1}(y)\right) \cdot \left|\frac{df^{-1}(y)}{dy} \right| \\
p_Y(y) &= p_X\left(f^{-1}(y)\right) \cdot \left|\det\nabla f^{-1}\right|
\end{split}
$$
#### proof
based on the definition of the [[lebesgue measure]] as a volume measure

$$
\lambda\left(f^{-1}\left(B_\epsilon(y)\right)\right) 
\approx \lambda\left(B_\epsilon(y)\right) \cdot \left|\det \nabla f^{-1}\left(y\right)\right| \quad \text{as } \epsilon \to 0
$$

$$
\begin{split}
\int_{f^{-1}\left(B_\epsilon (y)\right)} p_X(x) dx 
&=  p_X\left(f^{-1}\left(y\right)\right) \lambda\left(f^{-1}\left(B_\epsilon (y)\right)\right)  \\
&=  p_X\left(f^{-1}\left(y\right)\right) \lambda\left(B_\epsilon(y)\right) \cdot \left|\det \nabla f^{-1}\left(y\right)\right|    \\
\end{split}
$$

$$
\begin{split}
p_Y(y) 
&= \frac{\mathbb{P}\left(Y \in B_\epsilon (y)\right)}{\lambda\left(B_\epsilon (y)\right)} \\
&= \frac{\mathbb{P}\left(X \in f^{-1}\left(B_\epsilon (y)\right)\right)}{\lambda\left(B_\epsilon (y)\right)} \\
&= \frac{1}{\lambda\left(B_\epsilon (y)\right)} \int_{f^{-1}\left(B_\epsilon (y)\right)} p_X(x) dx \\
&= \frac{1}{\lambda\left(B_\epsilon (y)\right)} p_X\left(f^{-1}\left(y\right)\right) \lambda\left(B_\epsilon(y)\right) \cdot \left|\det \nabla f^{-1}\left(y\right)\right|    \\
&=  p_X\left(f^{-1}\left(y\right)\right)  \cdot \left|\det \nabla f^{-1}\left(y\right)\right|    \\
\end{split}
$$

__________________

### lebesgue measure
- the [[lebesgue measure]] is a way to assign a "size" or "length" to subsets of the $\mathbb{R}^n$ 
- for intervals in the $\mathbb{R}^n$ it is defined as follows, but there also exists a definition for a general subset

$$
\begin{split}
\lambda([a,b]) &= b-a  &\text{(length of an interval)} \\
\lambda([a_1,b_1] \times [a_2,b_2]) &= (b_1-a_1)(b_2-a_2) &\text{(volumn of a box)} \\
\lambda\left( \bigtimes_{i \in [n]} [a_i,b_i] \right) &= \prod_{i \in [n]}(b_i-a_i) &\text{(volumn of a n-box)} \\
\end{split}
$$


- in a **discrete** setting (countable sets), a measure can be defined by a sum:

$$
\begin{split}
\mathbb{\lambda}(A) 
&= \sum_{\omega \in A}  \lambda(\{\omega\}) \\
\end{split}
$$

- in the continuous case thus, we **must use integration** instead of summation
$$
\begin{split}
\lambda(A) 
&= \int_\Omega \mathbb{I}[\omega \in A] d\lambda(\omega) \\
&= \int_A  d\lambda(\omega) \\
\end{split}
$$

- in $\mathbb{R}^n$ the [[lebesgue measure]] and the [[riemann integral]] are the same because they agree on length


$$
\begin{split}
\mathbb{\lambda}([a,b]) 
&= \int_{[a, b]}  d\lambda(\omega) = b - a\\
\end{split}
$$


- for an interval $[a,b]$ and a regular function $g$:

$$
\begin{split}
\int_{[a, b]} g(\omega)  d\lambda(\omega) = \int_a^b g(\omega)  d\omega\\
\end{split}
$$
### lebesgue measures for probability
- on a [[measurable space]] $\left(\Omega,\mathcal{A} \right)$ the [[lebesgue measure]] $\lambda$ is a [[probability measure]] if $\lambda(\Omega)=1$
- on a finite $\Omega$ we can define a [[probability measure]] by rescaling
$$
\lambda_p(A) = \frac{\lambda(A)}{\lambda(\Omega)}
$$

- on infinite sets $\Omega$ we need a [[probability density function (PDF)]] $p: \Omega \to \mathbb{R}^n$ that decays fast enough such that

$$
\begin{split}
\mathbb{\lambda}(\Omega) 
&= \int_{\Omega} p(\omega)  d\lambda(\omega) =1\\

\end{split}
$$

$$
\begin{split}
\mathbb{\lambda}([a,b]) 
&= \int_{[a, b]} p(\omega) d\lambda(\omega) = b - a\\
\end{split}
$$


### probability measure
- given a [[measurable space]] $(\Omega, \mathcal{A})$ of a [[set]] $\Omega$ equiped with a [[sigma algebra]] $\mathcal{A}$ a [[function]] $P: \mathcal{A} \mapsto [0,1]$ is a [[probability measure]]
$$
P: \mathcal{A} \mapsto [0,1]
$$
- the probability of the [[empty set]] is zero

$$
\begin{split}
P(\emptyset) = 0 \\
\end{split}
$$
- the [[probability]] of the [[sample space]] is one
$$
\begin{split}
P(\Omega) = 1 \\
\end{split}
$$
- given a [[countable]] collection of [[mathematics/basics/disjoint]] events $(A_n)_{n \in \mathbb{N}}$ 
$$
\begin{split}
P\left(\bigcup_{i \in \mathbb{N}} A_i \right) = \sum_{i \in \mathbb{N}} P(A_i) \\
\end{split}
$$
### radon nikodym theorem
- given two [[probability measure]] $\nu$ and $\lambda$ on the same [[measurable space]] $(\Omega, \mathcal{A})$ 
- $\nu$ is [[absolutely continuous]] to $\lambda$ which means $\lambda(A) = 0 \Rightarrow \nu(A) = 0$
- this means that $\nu$ is just a scaled version of $\lambda$ and there exists a function $f=\frac{d\nu}{d\lambda}$ that compensates for that

$$
\begin{split}
\mathbb{\nu}(A) 
&= \int_\Omega \mathbb{I}[\omega \in A] d\nu \\
&= \int_A  d\nu \\

&= \int_A \frac{d\nu}{d\lambda} d\lambda \\
\end{split}
$$

#### intuition
- intuitively f answers how dense $\nu$ is to $\lambda$ at each point $\omega$ 

#### common application
- when $\lambda$ is a [[lebesgue measure]] on $\mathbb{R}^n$ $\nu$ is a [[probability measure]] of a [[random variable]]
- then $f$ is the [[probability density function (PDF)]] of $X$
- In this setting, computing probabilities becomes an [[riemann integral]]


### measurable space
- a [[measurable space]] $\left(\Omega,\mathcal{A} )\right)$ is a [[set]] $\Omega$ equipped with a [[sigma algebra]] $\mathcal{A}$
- every [[probability space]] is by definition a [[measurable space]]

Tags: mathematics statistics SS25
<!--ID: 1745950810550-->
END
