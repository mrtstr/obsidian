ank
## [[series]] definition of [[eulers number]]
$$
e = \sum\limits_{k=0}^\infty \frac{1}{k!}
\tag{definition eulers number}
$$
## [[series]] identity of exponential [[function]]
### theorem
$$
e^\lambda = \sum\limits_{k=0}^\infty \frac{\lambda^k}{k!}
$$
### given
![[taylor series#taylor series]]

### proof
$$
\begin{split}
f(\lambda) &= e^\lambda \\
\widehat{f}(\lambda, x_0 = 0) 
&= \sum_{n=0}^\infty 
\frac{1}{n!}
\left. \frac{d^n e^\lambda}{d^n \lambda} \right|_{\lambda=0}
 \left(\lambda-0\right)^n \\
 &= \sum_{n=0}^\infty \frac{\lambda^n}{n!} \cdot e_0  \\
 &= \sum_{n=0}^\infty \frac{\lambda^n}{n!}   \\
\end{split}
$$

## [[limit]] identity of [[eulers number]]
### theorem

$$
\begin{split}
e = \sum\limits_{k=0}^\infty \frac{1}{k!} \Rightarrow \\
e &= \lim_{n \rightarrow \infty} \left(1 + \frac{1}{n}\right)^n \\
&\Leftrightarrow_{h=\frac{1}{n}}
\\
e &= \lim_{h \rightarrow 0} \left(1 + h\right)^{\frac{1}{h}}

\end{split}
\tag{limit identity of e}
$$

### given
![[eulers number#series definition of eulers number]]

![[binomial theorem#binomial theorem]]

![[binomial coefficient#Definition]]
### [[proof]]
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


$$
\begin{split}
\lim_{n \rightarrow \infty} \frac{1}{k!}  \prod_{j=0}^{k-1} \left(1-\frac{j}{n}\right) 
=& \frac{1}{k!} \lim_{n \rightarrow \infty} \prod_{j=0}^{k-1} \left(1-\frac{j}{n}\right) \\
=& \frac{1}{k!}
\end{split}
$$

https://proofwiki.org/wiki/Euler%27s_Number:_Limit_of_Sequence_implies_Limit_of_Series


## [[derivative]] of $e^x$
### theorem

$$
\begin{split}
\ln(a) &= \lim_{h \rightarrow 0} \frac{a^h - 1}{h} \\
\Rightarrow 
\frac{de^x}{dx} &= e^x
\end{split}
$$

### given
$$
\frac{df(x)}{dx} = \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h}
$$

$$
\begin{split}
&e = \sum\limits_{k=0}^\infty \frac{1}{k!} \\
\Rightarrow & \ln(a) = \lim_{h \rightarrow 0} \frac{a^h - 1}{h} \\
\end{split}
$$
### [[proof]]
$$
\begin{split}
\frac{de^x}{dx} &=  \lim_{h \rightarrow 0} \frac{e^{x+h} - e^x}{h} \\
&=  \lim_{h \rightarrow 0} \frac{e^{x} \left(e^{h} - 1\right)}{h} \\
&= e^{x} \lim_{h \rightarrow 0} \frac{   e^{h} - 1}{h} \\
&= e^{x} \ln(e) \\
&= e^{x} \\

\end{split}
$$



# anki

START
Basic
[[eulers number]] summary
- definition of [[eulers number]] $e$ as a [[series]]
- definition of [[eulers number]] $e$ as a [[series]]
- definition of [[eulers number]] $e$ as a [[limit]]
Back: 
definition of [[eulers number]] $e$ as a [[series]]
$$
e = \sum\limits_{k=0}^\infty \frac{1}{k!}
$$
[[series]] identity of exponential [[function]] with proof
$$
e^\lambda = \sum\limits_{k=0}^\infty \frac{\lambda^k}{k!}
$$
definition of [[eulers number]] $e$ as a [[limit]]
$$
\begin{split}
e &= \lim_{n \rightarrow \infty} \left(1 + \frac{1}{n}\right)^n \\
&\Leftrightarrow_{h=\frac{1}{n}}
\\
e &= \lim_{h \rightarrow 0} \left(1 + h\right)^{\frac{1}{h}}

\end{split}
\tag{limit identity of e}
$$
Tags: mathematics
<!--ID: 1690103676776-->
END

START
Basic
definition of [[eulers number]] $e$ as a [[series]]
Back: 
$$
e = \sum\limits_{k=0}^\infty \frac{1}{k!}
$$

Tags: mathematics
<!--ID: 1689407672478-->
END

START
Basic
[[series]] identity of exponential [[function]] with proof
Back: 

### theorem
$$
e^\lambda = \sum\limits_{k=0}^\infty \frac{\lambda^k}{k!}
$$
### given
$$
\begin{split}
\widehat{f}(x, x_0) 
&= \sum_{n=0}^\infty 
\frac{1}{n!}
\left. \frac{d^n f(x)}{d^n x} \right|_{x=x_0}
 \left(x-x_0\right)^n \\
&= \sum_{n=0}^\infty a_n (x-x_0)^n \text{ with }a_n=\frac{1}{n!}
\left. \frac{d^n f(x)}{d^n x} \right|_{x=x_0}
\end{split}
\tag{taylor series}
$$

### proof
$$
\begin{split}
f(\lambda) &= e^\lambda \\
\widehat{f}(\lambda, x_0 = 0) 
&= \sum_{n=0}^\infty 
\frac{1}{n!}
\left. \frac{d^n e^\lambda}{d^n \lambda} \right|_{\lambda=0}
 \left(\lambda-0\right)^n \\
 &= \sum_{n=0}^\infty \frac{\lambda^n}{n!} \cdot e_0  \\
 &= \sum_{n=0}^\infty \frac{\lambda^n}{n!}   \\
\end{split}
$$



Tags: mathematics
<!--ID: 1690103676779-->
END




START
Basic
[[proof]] for 
$$
\frac{de^x}{dx} = e^x
$$
Back: 
### theorem
$$
\begin{split}
\ln(a) &= \lim_{h \rightarrow 0} \frac{a^h - 1}{h} \\
\Rightarrow 
\frac{de^x}{dx} &= e^x
\end{split}
$$
### given
$$
\frac{df(x)}{dx} = \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h}
$$

$$
\begin{split}
&e = \sum\limits_{k=0}^\infty \frac{1}{k!} \\
\Rightarrow & \ln(a) = \lim_{h \rightarrow 0} \frac{a^h - 1}{h} \\
\end{split}
$$
### [[proof]]
$$
\begin{split}
\frac{de^x}{dx} &=  \lim_{h \rightarrow 0} \frac{e^{x+h} - e^x}{h} \\
&=  \lim_{h \rightarrow 0} \frac{e^{x} \left(e^{h} - 1\right)}{h} \\
&= e^{x} \lim_{h \rightarrow 0} \frac{   e^{h} - 1}{h} \\
&= e^{x} \ln(e) \\
&= e^{x} \\

\end{split}
$$


Tags: mathematics
<!--ID: 1690016269208-->
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

START
Basic
two equivalent [[limit]] identitys of [[eulers number]] with proof
Back:
### theorem

$$
\begin{split}
e = \sum\limits_{k=0}^\infty \frac{1}{k!} \Rightarrow \\
e &= \lim_{n \rightarrow \infty} \left(1 + \frac{1}{n}\right)^n \\
&\Leftrightarrow_{h=\frac{1}{n}}
\\
e &= \lim_{h \rightarrow 0} \left(1 + h\right)^{\frac{1}{h}}
\end{split}
$$

### given
$$
e = \sum\limits_{k=0}^\infty \frac{1}{k!}
$$

$$
(x+y)^n = \sum_{k=0}^n {n \choose k} x^{n-k} y^k
$$

$$
\begin{split}
{n \choose k}
&= \frac{n!}{k!(n-k)!} \\
&= C_{n,k} \\
&= \frac{P_{n,k}}{k!} \\
\end{split}
$$
### [[proof]]
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


$$
\begin{split}
\lim_{n \rightarrow \infty} \frac{1}{k!}  \prod_{j=0}^{k-1} \left(1-\frac{j}{n}\right) 
=& \frac{1}{k!} \lim_{n \rightarrow \infty} \prod_{j=0}^{k-1} \left(1-\frac{j}{n}\right) \\
=& \frac{1}{k!}
\end{split}
$$

Tags: mathematics
<!--ID: 1689498258684-->
END