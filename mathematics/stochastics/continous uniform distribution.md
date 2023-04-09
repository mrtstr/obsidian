[[probability density function]] of a [[discrete random variable]] with the same probability of taking all values inside an interval $[a,b]$ and 0 for all other values.
## [[probability density function]]
$$
f_X(X = x)=
\begin{cases}
\frac{1}{b-a}
,& \text{if } x \in [a,b]\\
0
,& \text{otherwise}
\end{cases}
$$
## [[CDF]]

$$
\begin{split}
F_X(x)&=
\begin{cases}
0 
,& \text{if } x<a \\
\int\limits_a^x\frac{1}{b-a}du
,& \text{if } x \in [a,b]\\
1
,& \text{if } x>b
\end{cases} \\
&= \begin{cases}
0 
,& \text{if } x<a \\
\frac{x-a}{b-a}
,& \text{if } x \in [a,b]\\
1
,& \text{if } x>b
\end{cases}
\end{split}
$$
## [[quantile function]]
Because [[CDF]] is continuous we can calculate $Q_X(p) = F^{-1}_X(p)$ by rearranging $p=\frac{x-a}{b-a}$:
$$
Q_X(p): [0,1] \mapsto \mathbb{R} = a+p(b-a)
$$
# anki

START
Basic
[[continous uniform distribution]]
- verbal definition
- [[probability density function]]
- [[CDF]]
- [[quantile function]]

Back: 
[[probability density function]] of a [[discrete random variable]] with the same probability of taking all values inside an interval $[a,b]$ and 0 for all other values.

## probability function
$$
f_X(X = x)=
\begin{cases}
\frac{1}{b-a}
,& \text{if } x \in [a,b]\\
0
,& \text{otherwise}
\end{cases}
$$
## [[CDF]]

$$
\begin{split}
F_X(x)&=
\begin{cases}
0 
,& \text{if } x<a \\
\int\limits_a^x\frac{1}{b-a}du
,& \text{if } x \in [a,b]\\
1
,& \text{if } x>b
\end{cases} \\
&= \begin{cases}
0 
,& \text{if } x<a \\
\frac{x-a}{b-a}
,& \text{if } x \in [a,b]\\
1
,& \text{if } x>b
\end{cases}
\end{split}
$$
## [[quantile function]]
Because [[CDF]] is continuous we can calculate $Q_X(p) = F^{-1}_X(p)$ by rearranging $p=\frac{x-a}{b-a}$:
$$
Q_X(p): [0,1] \mapsto \mathbb{R} = a+p(b-a)
$$
Tags: mathematics statistics
<!--ID: 1668943285985-->
END