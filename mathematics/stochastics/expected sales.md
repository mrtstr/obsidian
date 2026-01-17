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
&= \frac{\partial}{\partial s}\int_0^s \left(1-F(d)\right) dd \\
&= \int_0^s \frac{\partial}{\partial s}\left(1-F(d)\right) dd \\
&= \int_0^s \frac{\partial}{\partial s}1-\frac{\partial}{\partial s}F(d) dd \\
&= \int_0^s -\frac{\partial}{\partial s}F(d) dd \\
&= -F(s) + F(0) \\
&= 1-F(s) \\
\end{split}
$$

$$
\begin{split}
F_i(s_i) &= F_j(s_j) :=x \\
s_i &= F_i^{-1}(x)
\end{split}
$$

$$
\begin{split}
(1-F_i(s_i))*p_i &= (1-F_j(s_j))*p_j :=\lambda \\
s_i &= F_i^{-1}\left( 1-\frac{\lambda}{p}\right) \\
\end{split}
$$







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
&= \frac{\partial}{\partial s}\int_0^s \left(1-F(d)\right) dd \\
&= \int_0^s \frac{\partial}{\partial s}\left(1-F(d)\right) dd \\
&= \int_0^s \frac{\partial}{\partial s}1-\frac{\partial}{\partial s}F(d) dd \\
&= \int_0^s -\frac{\partial}{\partial s}F(d) dd \\
&= -F(s) + F(0) \\
&= 1-F(s) \\
\end{split}
$$


Tags: mathematics WS2526
<!--ID: 1768678971884-->
END