### natural logarithm
[[logarithm]] with [[eulers number]] as the basis $\ln(x) = \log_e(x)$


### one identitiy natural logarithm

$$
\lim_{h \rightarrow 0} \frac{\ln(1 + h)}{h} = 1
$$

### proof for one identitiy natural logarithm
##### proof1

$$
\begin{split}
\lim_{h \rightarrow 0} \frac{\ln(1 + h)}{h} 
&=  \lim_{h \rightarrow 0} \frac{\frac{d\ln(1 + h)}{dh}}{\frac{dh}{dh}} \\
&=  \lim_{h \rightarrow 0} \frac{d\ln(1 + h)}{dh} \\
&=  \lim_{h \rightarrow 0} \frac{1}{1 + h} = 1 \\
\end{split}
$$

##### proof2

$$
\begin{split}
 
1 &= ln(e)\\
&=  \lim_{h \rightarrow 0} ln\left(\left(1 + h\right)^{\frac{1}{h}}\right) \\
&=  \lim_{h \rightarrow 0} \frac{\ln(1 + h)}{h} \\
\end{split}
$$

### limit identity of the natural logarithm

$$
\begin{split}
\ln(a) &= \lim_{h \rightarrow 0} \frac{a^h - 1}{h}
\end{split}
$$
### proof for limit identity of the natural logarithm
#### given
![[logarithm#Definition Logarithm]]

![[eulers number#theorem]]
#### proof
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


START
Basic
$$
\lim_{h \rightarrow 0} \frac{\ln(1 + h)}{h} = 
$$
with two proofs

Back: 

### theorem


$$
\lim_{h \rightarrow 0} \frac{\ln(1 + h)}{h} = 1
$$
### given
[[lhospital rule]]
$$
\begin{split}
\lim_{x \rightarrow c} \frac{f(x)}{g(x)} = \lim_{x \rightarrow c} \frac{\frac{df(x)}{dx}}{\frac{dg(x)}{dx}}
\end{split}
$$
theorem [[derivative]] of the [[natural logarithm]] of a [[function]]

$$
\begin{split}
\frac{d\ln\left(f(x)\right)}{dx} 
&= \frac{1}{f(x)} \frac{df(x)}{dx}  \\
\end{split}
$$

### proof1

$$
\begin{split}
\lim_{h \rightarrow 0} \frac{\ln(1 + h)}{h} 
&=  \lim_{h \rightarrow 0} \frac{\frac{d\ln(1 + h)}{dh}}{\frac{dh}{dh}} \\
&=  \lim_{h \rightarrow 0} \frac{d\ln(1 + h)}{dh} \\
&=  \lim_{h \rightarrow 0} \frac{1}{1 + h} = 1 \\
\end{split}
$$
### proof2

$$
\begin{split}
 
1 &= ln(e)\\
&=  \lim_{h \rightarrow 0} ln\left(\left(1 + h\right)^{\frac{1}{h}}\right) \\
&=  \lim_{h \rightarrow 0} \frac{\ln(1 + h)}{h} \\
\end{split}
$$

Tags: mathematics
<!--ID: 1697875981298-->
END