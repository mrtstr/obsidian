https://www.nagwa.com/en/explainers/656149079142/

## [[series]] definition of [[eulers number]]
$$
e = \sum\limits_{k=0}^\infty \frac{1}{k!}
$$
$$
e^\lambda = \sum\limits_{k=0}^\infty \frac{\lambda^k}{k!}
$$

## [[limit]] definition of [[eulers number]]

$$
e = \lim_{n \rightarrow \infty} \left(1 + \frac{1}{n}\right)^n
$$
which is eqivalent to:

$$
e = \lim_{x \rightarrow 0} \left(1 + x\right)^{\frac{1}{x}}
$$
## [[proof]] for $\sum\limits_{k=0}^\infty \frac{1}{k!} = \lim_{n \rightarrow \infty} \left(1 + \frac{1}{n}\right)^n$

![[binomial theorem#binomial theorem]]

![[binomial coefficient#Definition]]

$$
\begin{split}
\left(1 + \frac{1}{n}\right)^n 
&= \sum_{k=0}^n {n \choose k} \frac{1}{n^k} \cdot 1^{n-k} \\
&= \sum_{k=0}^n \frac{n!}{(n-k)!k!} \frac{1}{n^k} \\
&= \sum_{k=0}^n \frac{1}{k!} \frac{n!}{(n-k)!n^k} \\
&= \sum_{k=0}^n \frac{1}{k!} \frac{(n-k)!}{(n-k)!} \frac{n \cdot (n-1) \cdot \: ... \: (n-k-1) \cdot }{n^k} \\
&= \sum_{k=0}^n \frac{1}{k!}  \prod_{j=0}^{k-1} \left(\frac{n-j}{n}\right) \\
&= \sum_{k=0}^n \frac{1}{k!}  \prod_{j=0}^{k-1} \left(1-\frac{j}{n}\right) \\

\end{split}
$$

## [[proof]] for $e = \lim_{n \rightarrow \infty} \left(1 + \frac{1}{n}\right)^n$ given $\lim_{h \rightarrow 0} \frac{\ln(1 + h)}{h} = 1$


![[natural logarithm#properties]]

## proofs

# anki
START
Basic
definition of [[eulers number]] $e$ and $e^\lambda$ as a [[series]]
Back: 
$$
e = \sum\limits_{k=0}^\infty \frac{1}{k!}
$$
$$
e^\lambda = \sum\limits_{k=0}^\infty \frac{\lambda^k}{k!}
$$
Tags: mathematics
<!--ID: 1689407672478-->
END


START
Basic
definition of [[eulers number]] $e$ as a [[limit]]
Back:

$$
e = \lim_{n \rightarrow \infty} \left(1 + \frac{1}{n}\right)^n
$$
which is eqivalent to:

$$
e = \lim_{x \rightarrow 0} \left(1 + x\right)^{\frac{1}{x}}
$$
Tags: mathematics
<!--ID: 1689407672482-->
END

