## Definition
[[logarithm]] with [[eulers number]] as the basis $\ln(x) = \log_e(x)$

## properties
https://www.mathdoubts.com/natural-log-limit-rule-proof/
$$
\lim_{h \rightarrow 0} \frac{\ln(1 + h)}{h} = 1
$$
## [[limit]] identity of the [[natural logarithm]]
### theorem
$$
\begin{split}
e &= \lim_{h \rightarrow 0} \left(1 + h\right)^{\frac{1}{h}} \\
\Rightarrow \ln(a) &= \lim_{h \rightarrow 0} \frac{a^h - 1}{h}
\end{split}
$$
### given
![[logarithm#Definition Logarithm]]

![[eulers number#theorem]]
### [[proof]]
- the [[natural logarithm]] is defined as the [[inverse function]] of $e^x$
$$
\begin{split}
\ln(e) 
&= \lim_{h \rightarrow 0} \frac{e^h - 1}{h} \\
&= \lim_{h \rightarrow 0} \frac{{\lim_{h \rightarrow 0} \left(1 + h\right)^{\frac{1}{h}}}^h - 1}{h}  \\
&= \lim_{h \rightarrow 0} \frac{{ 1 + h} - 1}{h}  \\
&= \lim_{h \rightarrow 0} \frac{h}{h}  \\
&= 1  \\
\end{split}
$$

# anki
START
Basic
 [[natural logarithm]] summary
 - 2 [[limit]] identitys without proof

Back: 

$$
\lim_{h \rightarrow 0} \frac{\ln(1 + h)}{h} = 1
$$

$$
\ln(a) = \lim_{h \rightarrow 0} \frac{a^h - 1}{h}
$$
Tags: mathematics
<!--ID: 1689407672472-->
END


START
Basic
proof for [[limit]] identity of the [[natural logarithm]] $\ln(a) = \lim_{h \rightarrow 0} \frac{a^h - 1}{h}$

Back: 

### theorem
$$
\begin{split}
e &= \lim_{h \rightarrow 0} \left(1 + h\right)^{\frac{1}{h}} \\
\Rightarrow \ln(a) &= \lim_{h \rightarrow 0} \frac{a^h - 1}{h}
\end{split}
$$
### given


$$
\begin{split} 
f(x) &= b^x = y \\ \\
f^{-1}(y)
&=log_b(y) = x \\ \\
x &= f^{-1}\left(f(x)\right) \\
&= log_b(b^x)  \\\\
y &= f\left(f^{-1}(y)\right) \\
&= b^{log_b(y)}  \\
\end{split}
$$

$$
\begin{split}
e = \sum\limits_{k=0}^\infty \frac{1}{k!} \Rightarrow \\
e &= \lim_{n \rightarrow \infty} \left(1 + \frac{1}{n}\right)^n \\
&\Leftrightarrow_{h=\frac{1}{n}}
\\
e &= \lim_{h \rightarrow 0} \left(1 + h\right)^{\frac{1}{h}}
\end{split}
$$
### [[proof]]
- the [[natural logarithm]] is defined as the [[inverse function]] of $e^x$
$$
\begin{split}
\ln(e) 
&= \lim_{h \rightarrow 0} \frac{e^h - 1}{h} \\
&= \lim_{h \rightarrow 0} \frac{{\lim_{h \rightarrow 0} \left(1 + h\right)^{\frac{1}{h}}}^h - 1}{h}  \\
&= \lim_{h \rightarrow 0} \frac{{ 1 + h} - 1}{h}  \\
&= \lim_{h \rightarrow 0} \frac{h}{h}  \\
&= 1  \\
\end{split}
$$

Tags: mathematics
<!--ID: 1690016269203-->
END