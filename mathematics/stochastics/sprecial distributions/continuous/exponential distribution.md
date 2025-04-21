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

### cumulative distribution function
- [[cumulative distribution function (CDF)]] of the [[exponential distribution]]

$$
\begin{split}
F(x)
&= \int_0^x \lambda e^{-\lambda t} dt \\
&= \frac{\lambda}{\frac{d (-\lambda x)}{dx}} \int_0^{-\lambda x}  e^{t} dt \\
&= -1  \left[e^{t}\right]_0^{-\lambda x} dt \\
&= -1   \left(e^{-\lambda x} - e^{0}\right) \\
&= 1 - e^{-\lambda x} \\
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

# --------------------

![[integration by parts#theorem integration by parts]]

![[integration by substitution#theorem integration by substitution]]

# anki


START
Basic
[[exponential distribution]] summary
- [[probability density function (PDF)]]
- [[cumulative distribution function (CDF)]]
- [[expectation]]

Back: 
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

### cumulative distribution function
- [[cumulative distribution function (CDF)]] of the [[exponential distribution]]

$$
\begin{split}
F(x)
&= \int_0^x \lambda e^{-\lambda t} dt \\
&= \frac{\lambda}{\frac{d (-\lambda x)}{dx}} \int_0^{-\lambda x}  e^{t} dt \\
&= -1  \left[e^{t}\right]_0^{-\lambda x} dt \\
&= -1   \left(e^{-\lambda x} - e^{0}\right) \\
&= 1 - e^{-\lambda x} \\
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

__________


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
<!--ID: 1717761256380-->
END


START
Basic
[[exponential distribution]]
- [[probability density function (PDF)]] and proof that its normalized

Back: 
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

### cumulative distribution function
- [[cumulative distribution function (CDF)]] of the [[exponential distribution]]

$$
\begin{split}
F(x)
&= \int_0^x \lambda e^{-\lambda t} dt \\
&= \frac{\lambda}{\frac{d (-\lambda x)}{dx}} \int_0^{-\lambda x}  e^{t} dt \\
&= -1  \left[e^{t}\right]_0^{-\lambda x} dt \\
&= -1   \left(e^{-\lambda x} - e^{0}\right) \\
&= 1 - e^{-\lambda x} \\
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

__________


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

END


START
Basic
[[exponential distribution]]
- definition
- [[cumulative distribution function (CDF)]] with proof

Back: 
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

### cumulative distribution function
- [[cumulative distribution function (CDF)]] of the [[exponential distribution]]

$$
\begin{split}
F(x)
&= \int_0^x \lambda e^{-\lambda t} dt \\
&= \frac{\lambda}{\frac{d (-\lambda x)}{dx}} \int_0^{-\lambda x}  e^{t} dt \\
&= -1  \left[e^{t}\right]_0^{-\lambda x} dt \\
&= -1   \left(e^{-\lambda x} - e^{0}\right) \\
&= 1 - e^{-\lambda x} \\
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

__________

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

END


START
Basic
[[exponential distribution]]
- definition
- [[expectation]] with proof

Back: 
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

_______________


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

END
