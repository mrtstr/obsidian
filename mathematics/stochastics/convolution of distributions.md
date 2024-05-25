# convolution of distributions
- given the two [[stochastic independent]] [[random variable|random variables]] $X_1 \perp X_2$ with the [[probability density function|probability density functions]] / [[probability function|probability functions]] $f_{X_1}(x_1)$ and $f_{X_2}(x_2)$
- the [[convolution of distributions|convolution of the distributions]] the [[probability density function]] / [[probability function]] of the sum $Y = X_1 + X_2$ $f_Y(y)$

# convolutions of [[discrete distribution|discrete distributions]]
$$
\begin{split}
f_Y(y) 
=& P(Y = y) \\
=& P(X_1 + X_2 = y) 
= \sum\limits_{\{ (x_1, x_2) \mid y = x_1 + x_2 \}} f_{X_1X_2}(x_1, x_2) 
= \sum\limits_{\{ (x_1, x_2) \mid y = x_1 + x_2 \}} f_{X_1}(x_1)  f_{X_2}(x_2)\\
=& \sum\limits_{x_1 \in \Omega_{X_1}} f_{X_1}(x_1)  f_{X_2}(y -x_1)
= \sum\limits_{x_2 \in \Omega_{X_2}} f_{X_1}(y -x_2) f_{X_2}(x_2)  \\
\end{split}
$$

$$
\begin{split}
F_Y(y) 
=& P(Y \leq y) \\
=& \sum\limits_{x_1  \in \Omega_{X_1}} P(x_1 + X_2 \leq y \cap X_1 = x_1)  \\
=& \sum\limits_{x_1  \in \Omega_{X_1}} P(x_1 + X_2 \leq y) P(X_1 = x_1)  \\
=& \sum\limits_{x_1  \in \Omega_{X_1}} P(X_2 \leq y - x_1) P(X_1 = x_1)  \\
=& \sum\limits_{x_1  \in \Omega_{X_1}} F_{X_2}(y - x_1 ) f_{X_1}(x_1)  \\
f_Y(y) 
&= \frac{dF_Y(y)}{dy} \\
=& \sum\limits_{x_1  \in \Omega_{X_1}} f_{X_1}(x_1)  f_{X_2}(y -x_1)  \\
\end{split}
$$

# convolutions of [[continuous random variable|continuous distributions]]
$$
\begin{split}
F_Y(y) 
=& P(Y \leq y) \\
=& \int\limits_{\Omega_{X_1}} P(X_1 + X_2 \leq y \cap X_1 = x_1) dx_1 \\
=& \int\limits_{\Omega_{X_1}} P(X_1 + X_2 \leq y) P(X_1 = x_1) dx_1 \\
=& \int\limits_{\Omega_{X_1}} P(X_2 \leq y - x_1) P(X_1 = x_1) dx_1 \\
=& \int\limits_{\Omega_{X_1}} F_{X_2}(y - x_1 ) f_{X_1}(x_1) dx_1 \\
f_Y(y) 
&= \frac{dF_Y(y)}{dy} \\
=& \int\limits_{\Omega_{X_1}} f_{X_1}(x_1)  f_{X_2}(y -x_1) dx_1 \\
=& \int\limits_{\Omega_{X_2}} f_{X_1}(y -x_2) f_{X_2}(x_2)  dx_2\\
\end{split}
$$

# Anki

START
Basic
convolutions of [[discrete distribution|discrete distributions]]
- definition
- proof
Back: 
- given the two [[stochastic independent]] [[probability mass function (PMF)]] $X_1 \perp X_2$ with the / [[probability function|probability functions]] $f_{X_1}(x_1)$ and $f_{X_2}(x_2)$
- the [[convolution of distributions|convolution of the distributions]] the [[probability function]] of the sum $Y = X_1 + X_2$ $f_Y(y)$

$$
\begin{split}
f_Y(y) 
=& P(Y = y) \\
=& P(X_1 + X_2 = y) 
= \sum\limits_{\{ (x_1, x_2) \mid y = x_1 + x_2 \}} f_{X_1X_2}(x_1, x_2) 
= \sum\limits_{\{ (x_1, x_2) \mid y = x_1 + x_2 \}} f_{X_1}(x_1)  f_{X_2}(x_2)\\
=& \sum\limits_{x_1 \in \Omega_{X_1}} f_{X_1}(x_1)  f_{X_2}(y -x_1)
= \sum\limits_{x_2 \in \Omega_{X_2}} f_{X_1}(y -x_2) f_{X_2}(x_2)  \\
\end{split}
$$

Tags: mathematics statistics
<!--ID: 1671642994788-->
END


START
Basic
convolutions of [[continuous random variable|continuous distributions]]
- definition
- proof
Back: 
- given the two [[stochastic independent]] [[continuous random variable]] $X_1 \perp X_2$ with the [[probability density function|probability density functions]] $f_{X_1}(x_1)$ and $f_{X_2}(x_2)$
- the [[convolution of distributions|convolution of the distributions]] the [[probability density function]] of the sum $Y = X_1 + X_2$ $f_Y(y)$

$$
\begin{split}
F_Y(y) 
=& P(Y \leq y) \\
=& \int\limits_{\Omega_{X_1}} P(X_1 + X_2 \leq y \cap X_1 = x_1) dx_1 \\
=& \int\limits_{\Omega_{X_1}} P(X_1 + X_2 \leq y) P(X_1 = x_1) dx_1 \\
=& \int\limits_{\Omega_{X_1}} P(X_2 \leq y - x_1) P(X_1 = x_1) dx_1 \\
=& \int\limits_{\Omega_{X_1}} F_{X_2}(y - x_1 ) f_{X_1}(x_1) dx_1 \\
f_Y(y) 
&= \frac{dF_Y(y)}{dy} \\
=& \int\limits_{\Omega_{X_1}} f_{X_1}(x_1)  f_{X_2}(y -x_1) dx_1 \\
=& \int\limits_{\Omega_{X_2}} f_{X_1}(y -x_2) f_{X_2}(x_2)  dx_2\\
\end{split}
$$

Tags: mathematics statistics
<!--ID: 1671650835737-->
END