### expected sales
- stock $s$ is constant
- the demand $d$ is a [[random variable]] with the [[probability density function (PDF)]] $f(d)$ and the [[cumulative distribution function (CDF)]] $F(d)$

$$
\begin{split}
\mathrm{E}[\min\{s, D\}] 
&= \int_0^\infty \min\{s, d\} f(d) dd \\
&=  \int_0^s d f(d) dd + s \int_s^\infty f(d) dd \\
&=  \int_0^s d f(d) dd + s \left(1-F(s)\right) \\
&=  s\cdot F(s) - \int_0^s  F(d) dd + s - sF(s) \\
&=  \underbrace{s}_{\int_0^s1 dd} - \int_0^s  F(d) dd  \\
&=  \int_0^s \left(1-F(d)\right) dd \\
\end{split}
$$

$$
\begin{split}
\int_0^s d f(d) dd
&= \left[d\cdot F(d)\right]_0^s - \int_0^s  F(d) dd \\
&= s\cdot F(s) - \int_0^s  F(d) dd \\
\end{split}
$$

#### gradient wrt the stock

$$
\begin{split}
\frac{\partial}{\partial s}\mathrm{E}[\min\{s, D\}] 
&= 1-F(s) \\
\end{split}
$$

#### optimality for problems with diminishing marginal returns
- given multiple warehouses/products and a total inventory target, the optimality condition is that the **marginal gains ([[gradient]]) are equal**. (in a problem with diminishing marginal returns)

$$
\begin{split}
1-F_i(s_i) &= 1-F_j(s_j) :=\lambda \\
s_i &= F_i^{-1}(\lambda)
\end{split}
$$

- if we are maximizing the profit we have the following condition with the profit contribution $p_i$ of the warehouse / product combination $i$

$$
\begin{split}
(1-F_i(s_i))*p_i &= (1-F_j(s_j))*p_j :=\lambda \\
s_i &= F_i^{-1}\left( 1-\frac{\lambda}{p_i}\right) \\
\end{split}
$$

- both problems have just a single variable and are monotone → can be solved with bisection efficiently





# anki

START
Basic
proof for the following

$$
\begin{split}
\frac{\partial}{\partial s}\mathrm{E}[\min\{s, D\}] 
&= 1-F(d) \\
\end{split}
$$

Back: 
### expected sales

$$
\begin{split}
\mathrm{E}[\min\{s, D\}] 
&= \int_0^\infty \min\{s, d\} f(d) dd \\
&=  \int_0^s d f(d) dd + s \int_s^\infty f(d) dd \\
&=  \int_0^s d f(d) dd + s \left(1-F(s)\right) \\
&=  s\cdot F(s) - \int_0^s  F(d) dd + s - sF(s) \\
&=  \underbrace{s}_{\int_0^s1 dd} - \int_0^s  F(d) dd  \\
&=  \int_0^s \left(1-F(d)\right) dd \\
\end{split}
$$

$$
\begin{split}
\int_0^s d f(d) dd
&= \left[d\cdot F(d)\right]_0^s - \int_0^s  F(d) dd \\
&= s\cdot F(s) - \int_0^s  F(d) dd \\
\end{split}
$$

#### gradient wrt the stock

$$
\begin{split}
\frac{\partial}{\partial s}\mathrm{E}[\min\{s, D\}] 
&= 1-F(s) \\
\end{split}
$$

Tags: mathematics WS2526
<!--ID: 1768678971884-->
END