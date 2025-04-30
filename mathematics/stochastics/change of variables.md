### change of variables for probability
- given a [[measurable space]] and the [[random variable]] $X: \Omega \to \mathbb{R}^n$ and the [[inverse function|invertable]] [[differentiable]] function $f: \mathbb{R}^n \to \mathbb{R}^m$
- the [[probability density function (PDF)]] $Y=f(X)$ is given by the following 

$$
\begin{split}
p_Y(y) &= p_X\left(f^{-1}(y)\right) \cdot \left|\frac{df^{-1}(y)}{dy} \right| \\
p_Y(y) &= p_X\left(f^{-1}(y)\right) \cdot \left|\det\nabla f^{-1}\right|
\end{split}
$$
#### proof
- based on the definition of the [[lebesgue measure]] as a volume measure and the geometric interpretation of the [[determinant]]

$$
\frac{\lambda\left(f^{-1}\left(B_\epsilon(y)\right)\right)}{\lambda\left(B_\epsilon(y)\right)} 
\approx  \cdot \left|\det \nabla f^{-1}\left(y\right)\right| \quad \text{as } \epsilon \to 0
$$

- we approximate the [[probability density function (PDF)]] of $Y$ using an infinitesimal small [[ball]]

$$
\begin{split}
p_Y(y) 
&= \lim_{\epsilon \to \infty} \frac{\mathbb{P}\left(Y \in B_\epsilon (y)\right)}{\lambda\left(B_\epsilon (y)\right)} \\
&= \lim_{\epsilon \to \infty}  \frac{\mathbb{P}\left(X \in f^{-1}\left(B_\epsilon (y)\right)\right)}{\lambda\left(B_\epsilon (y)\right)} \\
&= \lim_{\epsilon \to \infty}  \frac{\mathcal{P}_X\left(f^{-1}\left(B_\epsilon (y)\right)\right)}{\lambda\left(B_\epsilon (y)\right)} \cdot \frac{\lambda\left(f^{-1}\left(B_\epsilon (y)\right)\right)}{\lambda\left(f^{-1}\left(B_\epsilon (y)\right)\right)} \\
&= \lim_{\epsilon \to \infty}  \frac{\mathcal{P}_X\left(f^{-1}\left(B_\epsilon (y)\right)\right)}{\lambda\left(f^{-1}\left(B_\epsilon (y)\right)\right)} \cdot \frac{\lambda\left(f^{-1}\left(B_\epsilon (y)\right)\right)}{\lambda\left(B_\epsilon (y)\right)} \\
&= p_X\left(f^{-1}\left(y\right)\right) \cdot \left|\det \nabla f^{-1}\left(y\right)\right|  \\
\end{split}
$$


- we use the fact that $Y$ is a transformation of $X$ and thus has the same source [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ and thus can be measured with $\mathbb{P}$

$$
\begin{split}
\mathcal{P}_Y\left(B_\epsilon (y)\right) 
&= \mathbb{P}\left(Y \in B_\epsilon (y)\right) \\
&= \mathbb{P}\left(\{\omega \in \Omega :Y\left(X(\omega)\right) \\ \in B_\epsilon (y)\}\right) \\
&= \mathbb{P}\left(\{\omega \in \Omega :f\left(X(\omega)\right) \\ \in B_\epsilon (y)\}\right) \\
&= \mathbb{P}\left(\{\omega \in \Omega :X(\omega) \\ \in f^{-1}\left(B_\epsilon (y)\right)\}\right) \\
&= \mathbb{P}\left(X \in f^{-1}\left(B_\epsilon (y)\right)\right) \\
&= \mathcal{P}_X\left(f^{-1}\left(B_\epsilon (y)\right)\right) \\
\end{split}
$$

# -----------------
![[probability density function (PDF)#probability density function]]

![[determinant#determinant]]

![[lebesgue measure#lebesgue measure]]

![[radon nikodym theorem#radon nikodym theorem]]


# anki


START
Basic
[[change of variables]] with proof

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
- based on the definition of the [[lebesgue measure]] as a volume measure and the geometric interpretation of the [[determinant]]

$$
\frac{\lambda\left(f^{-1}\left(B_\epsilon(y)\right)\right)}{\lambda\left(B_\epsilon(y)\right)} 
\approx  \cdot \left|\det \nabla f^{-1}\left(y\right)\right| \quad \text{as } \epsilon \to 0
$$

- we approximate the [[probability density function (PDF)]] of $Y$ using an infinitesimal small [[ball]]

$$
\begin{split}
p_Y(y) 
&= \lim_{\epsilon \to \infty} \frac{\mathbb{P}\left(Y \in B_\epsilon (y)\right)}{\lambda\left(B_\epsilon (y)\right)} \\
&= \lim_{\epsilon \to \infty}  \frac{\mathbb{P}\left(X \in f^{-1}\left(B_\epsilon (y)\right)\right)}{\lambda\left(B_\epsilon (y)\right)} \\
&= \lim_{\epsilon \to \infty}  \frac{\mathcal{P}_X\left(f^{-1}\left(B_\epsilon (y)\right)\right)}{\lambda\left(B_\epsilon (y)\right)} \cdot \frac{\lambda\left(f^{-1}\left(B_\epsilon (y)\right)\right)}{\lambda\left(f^{-1}\left(B_\epsilon (y)\right)\right)} \\
&= \lim_{\epsilon \to \infty}  \frac{\mathcal{P}_X\left(f^{-1}\left(B_\epsilon (y)\right)\right)}{\lambda\left(f^{-1}\left(B_\epsilon (y)\right)\right)} \cdot \frac{\lambda\left(f^{-1}\left(B_\epsilon (y)\right)\right)}{\lambda\left(B_\epsilon (y)\right)} \\
&= p_X\left(f^{-1}\left(y\right)\right) \cdot \left|\det \nabla f^{-1}\left(y\right)\right|  \\
\end{split}
$$


- we use the fact that $Y$ is a transformation of $X$ and thus has the same source [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ and thus can be measured with $\mathbb{P}$

$$
\begin{split}
\mathcal{P}_Y\left(B_\epsilon (y)\right) 
&= \mathbb{P}\left(Y \in B_\epsilon (y)\right) \\
&= \mathbb{P}\left(\{\omega \in \Omega :Y\left(X(\omega)\right) \\ \in B_\epsilon (y)\}\right) \\
&= \mathbb{P}\left(\{\omega \in \Omega :f\left(X(\omega)\right) \\ \in B_\epsilon (y)\}\right) \\
&= \mathbb{P}\left(\{\omega \in \Omega :X(\omega) \\ \in f^{-1}\left(B_\epsilon (y)\right)\}\right) \\
&= \mathbb{P}\left(X \in f^{-1}\left(B_\epsilon (y)\right)\right) \\
&= \mathcal{P}_X\left(f^{-1}\left(B_\epsilon (y)\right)\right) \\
\end{split}
$$

__________________

### probability density function
- a [[probability density function (PDF)]] is a [[measurable function]] $p: \mathbb{R} \to [0, \infty)$ that describes how a [[probability measure]] $\mathcal{P}$ on $\left(\mathbb{R}^n, \mathcal{B}(\mathbb{R}^n)\right)$ is [[absolutely continuous]] with respect to the [[lebesgue measure]] $\lambda$ (see [[radon nikodym theorem]])

$$
\begin{split}
&p(\omega) = \frac{d\mathcal{P}}{d\lambda} (\omega) \\
\Rightarrow &d\mathcal{P}(\omega) = p(\omega)d\lambda(\omega) \\
\end{split}
$$
- thus for all $A \subseteq \mathbb{R}$

$$
\begin{split}
\mathcal{P}(A) = \int_A  d\mathcal{P}(\omega) 
&= \int_A  p(\omega) d\lambda(\omega) = \int_A  p(\omega) d\omega \\
\end{split}
$$

- intuitively, the [[probability density function (PDF)]] weights the [[lebesgue measure]] to build the [[probability measure]] $\mathcal{P}$
- instead of describing the [[probability density function (PDF)]] as a differential equation often it makes sense to describe the ratio of the measurement of an infinitesimal small [[ball]] around the point $\omega$

$$
\begin{split}
&p(\omega) \approx \frac{\mathcal{P}\left(B_\epsilon (\omega)\right)}{\lambda \left(B_\epsilon (\omega)\right)} \quad \text{as } \epsilon \to 0  \\
&p\left(g(\omega)\right) \approx \frac{\mathcal{P}\left(B_\epsilon \left(g(\omega)\right)\right)}{\lambda \left(B_\epsilon \left(g(\omega)\right)\right)} \quad \text{as } \epsilon \to 0  \\
\end{split}
$$

### lebesgue measure
- the [[lebesgue measure]] is a [[measure]] that assigns size, length or volume to sets
- similar but more flexible than the [[riemann integral]] (in $\mathbb{R}^n$ they are interchangeable)
- for higher dimensions the [[lebesgue measure]] $\lambda^n: \mathcal{B} ({\mathbb{R}^n}) \to [0, \infty)$ forms a [[product measure space]] using the [[catesian product]]  over the dimensions of $\mathbb{R}$ 

$$
\begin{split}
\lambda([a,b]) 
&= \int_a^b1 \: d\lambda(x)  &\text{(length of an interval)} \\
&= b-a   \\
\lambda^2 ([a_1,b_1] \times [a_2,b_2])
&= \int_{[a_1,b_1] \times [a_2,b_2]}1 \: d\lambda(x_1, x_2) &\text{(volumn of a box)} \\ 
&= \int_{a_1}^{b_1} \int_{a_2}^{b_2} 1 \, d\lambda^1(y) \, d\lambda^1(x) \\
&= \int_{a_1}^{b_1}\int_{a_2}^{b_2}1 \: dx_1dx_2  \\
&= (b_1-a_1)(b_2-a_2)  \\
\lambda^n\left( \bigtimes_{i=1}^n [a_i, b_i] \right)
&= \int_{\bigtimes_{i=1}^n [a_i, b_i]} 1 \, d\lambda^n(x_1, \dots, x_n) & \text{(volume of an $n$-box)} \\
&= \int_{a_1}^{b_1} \cdots \int_{a_n}^{b_n} 1 \, d\lambda^1(x_n) \cdots d\lambda^1(x_1) \\
&= \prod_{i=1}^n (b_i - a_i)
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
- given two [[measure]]  $\nu$ and $\lambda$ on the same [[measurable space]] $(\Omega, \mathcal{A})$ 
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


START
Basic
- given a [[measurable space]] and the [[random variable]] $X: \Omega \to \mathbb{R}^n$ and the [[inverse function|invertable]] [[differentiable]] function $f: \mathbb{R}^n \to \mathbb{R}^m$
- given the [[random variable]] $Y=f(X)$ 
- prove the following relationship of the [[probability density function (PDF)]] of $Y$ and the pushdown [[probability measure]] of $X$

$$
\begin{split}
p_Y(y) 
&\approx \frac{\mathcal{P}_X\left(f^{-1}\left(B_\epsilon (y)\right)\right)}{\lambda\left(B_\epsilon (y)\right)} \\
\end{split}
$$

Back: 
- we approximate the [[probability density function (PDF)]] of $Y$ using an infinitesimal small [[ball]]

$$
\begin{split}
p_Y(y) 
&\approx \frac{\mathbb{P}\left(Y \in B_\epsilon (y)\right)}{\lambda\left(B_\epsilon (y)\right)} \\
&\approx \frac{\mathbb{P}\left(X \in f^{-1}\left(B_\epsilon (y)\right)\right)}{\lambda\left(B_\epsilon (y)\right)} \\
&\approx \frac{\mathcal{P}_X\left(f^{-1}\left(B_\epsilon (y)\right)\right)}{\lambda\left(B_\epsilon (y)\right)} \\
\end{split}
$$

- we use the fact that $Y$ is a transformation of $X$ and thus has the same source [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ and thus can be measured with $\mathbb{P}$

$$
\begin{split}
\mathcal{P}_Y\left(B_\epsilon (y)\right) 
&= \mathbb{P}\left(Y \in B_\epsilon (y)\right) \\
&= \mathbb{P}\left(\{\omega \in \Omega :Y\left(X(\omega)\right) \\ \in B_\epsilon (y)\}\right) \\
&= \mathbb{P}\left(\{\omega \in \Omega :f\left(X(\omega)\right) \\ \in B_\epsilon (y)\}\right) \\
&= \mathbb{P}\left(\{\omega \in \Omega :X(\omega) \\ \in f^{-1}\left(B_\epsilon (y)\right)\}\right) \\
&= \mathbb{P}\left(X \in f^{-1}\left(B_\epsilon (y)\right)\right) \\
&= \mathcal{P}_X\left(f^{-1}\left(B_\epsilon (y)\right)\right) \\
\end{split}
$$

__________________
### probability density function
- a [[probability density function (PDF)]] is a [[measurable function]] $p: \mathbb{R} \to [0, \infty)$ that describes how a [[probability measure]] $\mathcal{P}$ on $\left(\mathbb{R}^n, \mathcal{B}(\mathbb{R}^n)\right)$ is [[absolutely continuous]] with respect to the [[lebesgue measure]] $\lambda$ (see [[radon nikodym theorem]])

$$
\begin{split}
&p(\omega) = \frac{d\mathcal{P}}{d\lambda} (\omega) \\
\Rightarrow &d\mathcal{P}(\omega) = p(\omega)d\lambda(\omega) \\
\end{split}
$$
- thus for all $A \subseteq \mathbb{R}$

$$
\begin{split}
\mathcal{P}(A) = \int_A  d\mathcal{P}(\omega) 
&= \int_A  p(\omega) d\lambda(\omega) = \int_A  p(\omega) d\omega \\
\end{split}
$$

- intuitively, the [[probability density function (PDF)]] weights the [[lebesgue measure]] to build the [[probability measure]] $\mathcal{P}$
- instead of describing the [[probability density function (PDF)]] as a differential equation often it makes sense to describe the ratio of the measurement of an infinitesimal small [[ball]] around the point $\omega$

$$
\begin{split}
&p(\omega) \approx \frac{\mathcal{P}\left(B_\epsilon (\omega)\right)}{\lambda \left(B_\epsilon (\omega)\right)} \quad \text{as } \epsilon \to 0  \\
&p\left(g(\omega)\right) \approx \frac{\mathcal{P}\left(B_\epsilon \left(g(\omega)\right)\right)}{\lambda \left(B_\epsilon \left(g(\omega)\right)\right)} \quad \text{as } \epsilon \to 0  \\
\end{split}
$$

### lebesgue measure
- the [[lebesgue measure]] is a [[measure]] that assigns size, length or volume to sets
- similar but more flexible than the [[riemann integral]] (in $\mathbb{R}^n$ they are interchangeable)
- for higher dimensions the [[lebesgue measure]] $\lambda^n: \mathcal{B} ({\mathbb{R}^n}) \to [0, \infty)$ forms a [[product measure space]] using the [[catesian product]]  over the dimensions of $\mathbb{R}$ 

$$
\begin{split}
\lambda([a,b]) 
&= \int_a^b1 \: d\lambda(x)  &\text{(length of an interval)} \\
&= b-a   \\
\lambda^2 ([a_1,b_1] \times [a_2,b_2])
&= \int_{[a_1,b_1] \times [a_2,b_2]}1 \: d\lambda(x_1, x_2) &\text{(volumn of a box)} \\ 
&= \int_{a_1}^{b_1} \int_{a_2}^{b_2} 1 \, d\lambda^1(y) \, d\lambda^1(x) \\
&= \int_{a_1}^{b_1}\int_{a_2}^{b_2}1 \: dx_1dx_2  \\
&= (b_1-a_1)(b_2-a_2)  \\
\lambda^n\left( \bigtimes_{i=1}^n [a_i, b_i] \right)
&= \int_{\bigtimes_{i=1}^n [a_i, b_i]} 1 \, d\lambda^n(x_1, \dots, x_n) & \text{(volume of an $n$-box)} \\
&= \int_{a_1}^{b_1} \cdots \int_{a_n}^{b_n} 1 \, d\lambda^1(x_n) \cdots d\lambda^1(x_1) \\
&= \prod_{i=1}^n (b_i - a_i)
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
- given two [[measure]] $\nu$ and $\lambda$ on the same [[measurable space]] $(\Omega, \mathcal{A})$ 
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
<!--ID: 1745991645673-->
END
