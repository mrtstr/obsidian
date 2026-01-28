### entropy
- measure of the **average [[information content]]** $I$ contained in an observation of a [[random variable]] in bits (if the $\log_2$ is used)
- in other words the average amount of removed uncertainty by an observation 
- for a discrete random variable with the [[probability function]] $p_X$ the [[entropy]] is defined as follows

$$
\begin{split}
H(X) 
&= \mathbb{E}\left[-\log\left(p_X(X)\right)\right]  \\
&= - \sum p_X(x_i) \log\left(p_X(x_i)\right) \\
&= \mathbb{E}\left[I(X)\right]
\end{split}
$$

- $H(X)$ is positive, and its maximum value depends on the [[distribution]] of $X$
##### example
- [[bernoulli distribution]] with $p=0.9$ and $p=0.5$
- We see that the entropy is **higher** when $p=0.5$, indicating that this outcome is **more uncertain** and thus contains **more information per observation**.

$$
\begin{split}
H(X) &= - 0.1 \cdot \log_2(0.1) - 0.9 \cdot \log_2(0.9) = 0.33 + 0.14 = 0.47 \\
H(X) &= - 0.5 \cdot \log_2(0.5) - 0.5 \cdot \log_2(0.5) = \frac{1}{2} + \frac{1}{2} = 1 \\
\end{split}
$$

### differential entropy
- for continuous random variables the concept of [[entropy]] can be extended
- does not have an intuitive interpretation other than **measurement for uncertainty or spread**
- other than the [[entropy]] the differential entropy can be negative and is sensitive to scaling

- for a continuous random variable with the [[probability density function (PDF)]] $f_X$ the differential entropy is defined as follows

$$
H(X) = \mathbb{E}\left[-\log\left(f_X(X)\right)\right] = - \int_\mathbb{R} f_X(x) \log\left(f_X(x)\right) dx
$$
#### example
##### exponential distribution

$$
\begin{split}
H(X) 
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \ln\left(\lambda e^{-\lambda x})\right) dx \\
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \left(\ln(\lambda)  -\lambda x\right) dx \\
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \ln(\lambda) dx + \lambda \int_\mathbb{R} \lambda e^{-\lambda x}  x dx \\
&= - \ln(\lambda) + \lambda \int_\mathbb{R}  \mathbb{E}[X] \\
&= - \ln(\lambda) + \frac{\lambda}{\lambda} \\
&= 1 - \ln(\lambda) \\
\end{split}
$$

- the higher $\lambda$ is the less the PDF spreads thus $1-\ln(2)=0.3<1-\ln(1)=1$
##### standard normal distribution
- [[normal distribution]] with $\mu=0$ and $\sigma^2=1$

$$
\begin{split}
H(X) 
&= - \int_\mathbb{R} f(x) \ln\left(\frac{1}{\sqrt{2 \pi }}\exp{\left[-\frac{x^2}{2}\right]}\right) dx \\
&= - \int_\mathbb{R} f(x) \left( \frac{-1}{2} \ln\left(2 \pi\right) -\frac{x^2}{2} \right) dx \\
&= \frac{1}{2} \ln\left(2 \pi\right) \int_\mathbb{R} f(x) dx +  \frac{1}{2}\int_\mathbb{R} x^2 f(x) dx \\
&= \frac{1}{2} \ln\left(2 \pi\right)  +  \frac{1}{2} \mathbb{VAR}[X] \\
&= \frac{1}{2} \left(\ln\left(2 \pi\right) + 1 \right) \\
\end{split}
$$
# ------------
![[information content#information content]]

![[exponential distribution#plot]]


# -------------

![[exponential distribution#exponential distribution]]

![[exponential distribution#expectation]]

# anki

START
Basic
[[entropy]] of the [[standard normal distribution]]

Back: 

- [[normal distribution]] with $\mu=0$ and $\sigma^2=1$

$$
\begin{split}
H(X) 
&= - \int_\mathbb{R} f(x) \ln\left(\frac{1}{\sqrt{2 \pi }}\exp{\left[-\frac{x^2}{2}\right]}\right) dx \\
&= - \int_\mathbb{R} f(x) \left( \frac{-1}{2} \ln\left(2 \pi\right) -\frac{x^2}{2} \right) dx \\
&= \frac{1}{2} \ln\left(2 \pi\right) \int_\mathbb{R} f(x) dx +  \frac{1}{2}\int_\mathbb{R} x^2 f(x) dx \\
&= \frac{1}{2} \ln\left(2 \pi\right)  +  \frac{1}{2} \mathbb{VAR}[X] \\
&= \frac{1}{2} \left(\ln\left(2 \pi\right) + 1 \right) \\
\end{split}
$$

### differential entropy
- for continuous random variables the concept of [[entropy]] can be extended
- does not have an intuitive interpretation other than **measurement for uncertainty or spread**
- other than the [[entropy]] the differential entropy can be negative and is sensitive to scaling

- for a continuous random variable with the [[probability density function (PDF)]] $f_X$ the differential entropy is defined as follows

$$
H(X) = \mathbb{E}\left[-\log\left(f_X(X)\right)\right] = - \int_\mathbb{R} f_X(x) \log\left(f_X(x)\right) dx
$$


Tags: mathematics statistics SS25
<!--ID: 1748332617290-->
END


START
Basic
differential entropy
- definition
- interpretation
- difference to [[entropy]]

Back: 
### differential entropy
- for continuous random variables the concept of [[entropy]] can be extended
- does not have an intuitive interpretation other than **measurement for uncertainty or spread**
- other than the [[entropy]] the differential entropy can be negative and is sensitive to scaling

- for a continuous random variable with the [[probability density function (PDF)]] $f_X$ the differential entropy is defined as follows

$$
H(X) = \mathbb{E}\left[-\log\left(f_X(X)\right)\right] = - \int_\mathbb{R} f_X(x) \log\left(f_X(x)\right) dx
$$



### information content
- let $X$ be a discrete [[random variable]] = [[channel]] with a [[sample space]] $\Omega=\{p_1, ..., p_N\}$ with each possible outcome is called a [[signal]]
- each signal $\mathbb{P}(X=p_i)$ has a [[probability]] or relative frequency
- let $I(A)$ be a function that measures the [[information content]] of an [[event]] $A \in \mathcal{P}(\Omega)$ that satisfies the following conditions

1) **non-negativity and certainty**: $I(A) \geq 0$ with $I(A) = 0$ if and only if $\mathbb{P}(A) = 1$
2) **monotonicity**:  $\mathbb{P}(A) \geq \mathbb{P}(B) \Leftrightarrow I(A) \leq I(B)$
3) **additivity for independent events**if $A$ and $B$ are [[stochastic independent]] then $I(A \cup B) = I(A) + I(B)$

- only the following function satisfies all 3 conditions

$$
I(A) = \log\left(\frac{1}{\mathbb{P}(A)}\right)
$$

### entropy
- measure of the **average [[information content]]** $I$ contained in an observation of a [[random variable]] in bits (if the $\log_2$ is used)
- in other words the average amount of removed uncertainty by an observation 
- for a discrete random variable with the [[probability function]] $p_X$ the [[entropy]] is defined as follows

$$
\begin{split}
H(X) 
&= \mathbb{E}\left[-\log\left(p_X(X)\right)\right]  \\
&= - \sum p_X(x_i) \log\left(p_X(x_i)\right) \\
&= \mathbb{E}\left[I(X)\right]
\end{split}
$$

- $H(X)$ is positive, and its maximum value depends on the [[distribution]] of $X$

Tags: mathematics statistics SS25
<!--ID: 1745238828228-->
END


START
Basic
differential entropy
- differential entropy of the [[exponential distribution]] 
- which values lead to a high and low differential entropy?
Back: 
### differential entropy
- for continuous random variables the concept of [[entropy]] can be extended
- does not have an intuitive interpretation other than **measurement for uncertainty or spread**
- other than the [[entropy]] the differential entropy can be negative and is sensitive to scaling

- for a continuous random variable with the [[probability density function (PDF)]] $f_X$ the differential entropy is defined as follows

$$
H(X) = \mathbb{E}\left[-\log\left(f_X(X)\right)\right] = - \int_\mathbb{R} f_X(x) \log\left(f_X(x)\right) dx
$$

### entropy
- measure of the **average [[information content]]** $I$ contained in an observation of a [[random variable]] in bits (if the $\log_2$ is used)
- in other words the average amount of removed uncertainty by an observation 
- for a discrete random variable with the [[probability function]] $p_X$ the [[entropy]] is defined as follows

$$
\begin{split}
H(X) 
&= \mathbb{E}\left[-\log\left(p_X(X)\right)\right]  \\
&= - \sum p_X(x_i) \log\left(p_X(x_i)\right) \\
&= \mathbb{E}\left[I(X)\right]
\end{split}
$$

- $H(X)$ is positive, and its maximum value depends on the [[distribution]] of $X$

#### information content
- let $X$ be a discrete [[random variable]] = [[channel]] with a [[sample space]] $\Omega=\{p_1, ..., p_N\}$ with each possible outcome is called a [[signal]]
- each signal $\mathbb{P}(X=p_i)$ has a [[probability]] or relative frequency
- let $I(A)$ be a function that measures the [[information content]] of an [[event]] $A \in \mathcal{P}(\Omega)$ that satisfies the following conditions

1) **non-negativity and certainty**: $I(A) \geq 0$ with $I(A) = 0$ if and only if $\mathbb{P}(A) = 1$
2) **monotonicity**:  $\mathbb{P}(A) \geq \mathbb{P}(B) \Leftrightarrow I(A) \leq I(B)$
3) **additivity for independent events**if $A$ and $B$ are [[stochastic independent]] then $I(A \cap B) = I(A) + I(B)$

- only the following function satisfies all 3 conditions

$$
I(A) = \log\left(\frac{1}{\mathbb{P}(A)}\right)
$$

##### example
- [[exponential distribution]]
- the higher $\lambda$ is the less the PDF spreads thus $1-\ln(2)=0.3<1-\ln(1)=1$
$$
\begin{split}
H(X) 
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \ln\left(\lambda e^{-\lambda x})\right) dx \\
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \left(\ln(\lambda)  -\lambda x\right) dx \\
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \ln(\lambda) dx + \lambda \int_\mathbb{R} \lambda e^{-\lambda x}  x dx \\
&= - \ln(\lambda) + \lambda \int_\mathbb{R}  \mathbb{E}[X] \\
&= - \ln(\lambda) + \frac{\lambda}{\lambda} \\
&= 1 - \ln(\lambda) \\
\end{split}
$$

![[exp_dist.png]]

____________

### exponential distribution

- [[probability density function (PDF)]] of the [[exponential distribution]]

$$
f_X(x) = \lambda e^{-\lambda x}
$$

$$
\begin{split}
\int^\infty_0  e^{-\lambda x} dx
&=\frac{1}{\frac{d (-\lambda x)}{dx}} \left. \int^\infty_0  e^{t} dt \right|_{t=-\lambda x} \\
&=\frac{1}{-\lambda} \left[e^{-\infty} - e^0\right] \\
&=\frac{1}{\lambda}  \\
\end{split}
$$

#### expectation
- [[expectation]] of the [[exponential distribution]]

$$
\begin{split}
\mathbb{E}[X] 
&= \int_0^\infty x \lambda e^{-\lambda x} \\
&=  \left[x (-1) e^{-\lambda x}  \right]_0^\infty -\int_0^\infty \frac{x}{x} (-1) e^{-\lambda x} dx \\
&= -\left[xe^{-\lambda x}\right]_0^\infty +\int_0^\infty   e^{-\lambda x} dx \\
&= -0-0 +\int_0^\infty  \ e^{-\lambda x} dx \\
&= \int_0^\infty  e^{-\lambda x} dx \\
&= \frac{1}{-\lambda}  \left(e^{-\infty} - e^0\right) \\
&= \frac{1}{\lambda}   \\
\end{split}
$$



$$
\begin{split}
\lambda e^{-\lambda x} &= \frac{dg(x)}{x} \\
\Leftrightarrow g(x)&=  \int^x_0 \lambda e^{-\lambda t} dt \\
&=\frac{\lambda}{\frac{d (-\lambda x)}{dx}} \left. \int  e^{t} dt \right|_{t=-\lambda x} \\
&=\frac{\lambda}{-\lambda} e^{-\lambda x}  \\
&=- e^{-\lambda x}  \\
\end{split}
$$



### theorem [[integration by parts]]

$$
\begin{split}
\int f(x) \frac{dg(x)}{x}dx = f(x)g(x)-\int g(x) \frac{df(x)}{dx} dx
\end{split}
$$

### theorem [[integration by substitution]]

#### definit [[integral]]
$$
\begin{split}
\int_a^b f\left(g(x)\right) \frac{dg(x)}{x}dx = \int_{g(a)}^{g(b)} f\left(t\right) dt \quad \text{with} \quad t=g(x)
\end{split}
$$
#### infinit [[integral]]
$$
\begin{split}
\int f\left(g(x)\right) \frac{dg(x)}{x}dx = \left.\int f\left(t\right) dt \right|_{t=g(x)}
\end{split}
$$

Tags: mathematics statistics SS25
<!--ID: 1745238828231-->
END


START
Basic
[[entropy]]
- definition
- interpretation
- unit
- min and man value
- example [[bernoulli distribution]]

Back: 
### entropy
- measure of the **average [[information content]]** $I$ contained in an observation of a [[random variable]] in bits (if the $\log_2$ is used)
- in other words the average amount of removed uncertainty by an observation 
- for a discrete random variable with the [[probability function]] $p_X$ the [[entropy]] is defined as follows

$$
\begin{split}
H(X) 
&= \mathbb{E}\left[-\log\left(p_X(X)\right)\right]  \\
&= - \sum p_X(x_i) \log\left(p_X(x_i)\right) \\
&= \mathbb{E}\left[I(X)\right]
\end{split}
$$

- $H(X)$ is positive, and its maximum value depends on the [[distribution]] of $X$
### information content
- let $X$ be a discrete [[random variable]] = [[channel]] with a [[sample space]] $\Omega=\{p_1, ..., p_N\}$ with each possible outcome is called a [[signal]]
- each signal $\mathbb{P}(X=p_i)$ has a [[probability]] or relative frequency
- let $I(A)$ be a function that measures the [[information content]] of an [[event]] $A \in \mathcal{P}(\Omega)$ that satisfies the following conditions

1) **non-negativity and certainty**: $I(A) \geq 0$ with $I(A) = 0$ if and only if $\mathbb{P}(A) = 1$
2) **monotonicity**:  $\mathbb{P}(A) \geq \mathbb{P}(B) \Leftrightarrow I(A) \leq I(B)$
3) **additivity for independent events**if $A$ and $B$ are [[stochastic independent]] then $I(A \cap B) = I(A) + I(B)$

- only the following function satisfies all 3 conditions

$$
I(A) = \log\left(\frac{1}{\mathbb{P}(A)}\right)
$$
##### example
- [[bernoulli distribution]] with $p=0.9$ and $p=0.5$
- We see that the entropy is **higher** when $p=0.5$, indicating that this outcome is **more uncertain** and thus contains **more information per observation**.

$$
\begin{split}
H(X) &= - 0.1 \cdot \log_2(0.1) - 0.9 \cdot \log_2(0.9) = 0.33 + 0.14 = 0.47 \\
H(X) &= - 0.5 \cdot \log_2(0.5) - 0.5 \cdot \log_2(0.5) = \frac{1}{2} + \frac{1}{2} = 1 \\
\end{split}
$$

Tags: mathematics statistics SS25
<!--ID: 1745238828233-->
END