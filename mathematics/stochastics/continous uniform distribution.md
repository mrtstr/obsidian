
### continous uniform distribution
[[probability density function (PDF)]] of a [[probability mass function (PMF)]] with the same probability of taking all values inside an interval $[a,b]$ and 0 for all other values.
#### [[probability density function (PDF)]]
$$
f_X(X = x)=
\begin{cases}
\frac{1}{b-a}
,& \text{if } x \in [a,b]\\
0
,& \text{otherwise}
\end{cases}
$$
#### [[cumulative distribution function (CDF)]]

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
#### [[quantile function]]
Because [[cumulative distribution function (CDF)]] is continuous we can calculate $Q_X(p) = F^{-1}_X(p)$ by rearranging $p=\frac{x-a}{b-a}$:
$$
Q_X(p): [0,1] \mapsto \mathbb{R} = a+p(b-a)
$$
#### [[expectation]]

$$
\begin{split}
\mathbb{E}[X] 
&= \int_a^b x \frac{1}{b-a} dx \\
&= \frac{b^2 - a^2}{b-a} \frac{1}{2}  \\
&= \frac{(b-a)(b+a)}{b-a} \frac{1}{2}  \\
&= \frac{b+a}{2}  \\
\end{split}
$$

#### [[variance]]

$$
\begin{split}
\mathbb{E}\left[X^2\right] 
&= \int_a^b x^2 \frac{1}{b-a} dx \\
&= \frac{b^3 - a^3}{b-a} \frac{1}{3}  \\
\mathbb{VAR}\left[X\right] 
&= \mathbb{E}\left[X^2\right]  - \mathbb{E}\left[X\right] ^2\\
&= \frac{b^3 - a^3}{b-a} \frac{1}{3} - \left(\frac{b+a}{2}\right)^2\\
\end{split}
$$
- for $a=0$
$$
\begin{split}
\mathbb{VAR}\left[X\right] 
&= \frac{b^3}{b} \frac{1}{3} - \left(\frac{b}{2}\right)^2\\
&= \frac{b^2}{3} - \frac{b^2}{4}\\
&= \frac{b^2}{12}\\
\end{split}
$$


# anki

START
Basic
[[continous uniform distribution]]
- [[expectation]]
- [[variance]] for  $a=0$

Back: 
### continous uniform distribution
[[probability density function (PDF)]] of a [[probability mass function (PMF)]] with the same probability of taking all values inside an interval $[a,b]$ and 0 for all other values.
#### [[probability density function (PDF)]]
$$
f_X(X = x)=
\begin{cases}
\frac{1}{b-a}
,& \text{if } x \in [a,b]\\
0
,& \text{otherwise}
\end{cases}
$$
#### [[cumulative distribution function (CDF)]]

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

#### [[expectation]]

$$
\begin{split}
\mathbb{E}[X] 
&= \int_a^b x \frac{1}{b-a} dx \\
&= \frac{b^2 - a^2}{b-a} \frac{1}{2}  \\
&= \frac{(b-a)(b+a)}{b-a} \frac{1}{2}  \\
&= \frac{b+a}{2}  \\
\end{split}
$$

#### [[variance]]

$$
\begin{split}
\mathbb{E}\left[X^2\right] 
&= \int_a^b x^2 \frac{1}{b-a} dx \\
&= \frac{b^3 - a^3}{b-a} \frac{1}{3}  \\
\mathbb{VAR}\left[X^2\right] 
&= \mathbb{E}\left[X^2\right]  - \mathbb{E}\left[X\right] ^2\\
&= \frac{b^3 - a^3}{b-a} \frac{1}{3} - \left(\frac{b+a}{2}\right)^2\\
\end{split}
$$

- for $a=0$
$$
\begin{split}
\mathbb{VAR}\left[X\right] 
&= \frac{b^3}{b} \frac{1}{3} - \left(\frac{b}{2}\right)^2\\
&= \frac{b^2}{3} - \frac{b^2}{4}\\
&= \frac{b^2}{12}\\
\end{split}
$$

Tags: mathematics statistics
<!--ID: 1719154404934-->
END


START
Basic
[[continous uniform distribution]]
- verbal definition
- [[probability density function (PDF)]]
- [[cumulative distribution function (CDF)]]
- [[quantile function]]

Back: 
[[probability density function (PDF)]] of a [[probability mass function (PMF)]] with the same probability of taking all values inside an interval $[a,b]$ and 0 for all other values.

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
## [[cumulative distribution function (CDF)]]

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
Because [[cumulative distribution function (CDF)]] is continuous we can calculate $Q_X(p) = F^{-1}_X(p)$ by rearranging $p=\frac{x-a}{b-a}$:
$$
Q_X(p): [0,1] \mapsto \mathbb{R} = a+p(b-a)
$$
Tags: mathematics statistics
<!--ID: 1668943285985-->
END