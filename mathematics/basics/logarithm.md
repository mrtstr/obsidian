# Definition Logarithm
- the [[logarithm]] is the [[inverse function]] of the [[exponential]]

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

```functionplot
---
title: 
xLabel: x
yLabel: ln(x)
bounds: [-0.1,5,-3,2]
disableZoom: true
grid: true
---
f(x) = log(x)
```

# Properties
## [[addition]] inside a [[logarithm]]
$$
\begin{split}
log_b(x+y) = log_b(x) \cdot log_b(y)
\end{split}
$$
### Proof
$$
\begin{split}
n &= b^x \Leftrightarrow x = log_b(n) \\
m &= b^y \Leftrightarrow y = log_b(m)  \\ \\
nm &= b^x \cdot b^y = b^{x + y} \\
log_b(nm) &= log_b\left(b^{x + y}\right) = x+y = log_n(n)+log_n(m) \\
\end{split}
$$
## [[substraction]] inside a [[logarithm]]
$$
\begin{split}
log_b\left(x-y\right) = \frac{log_b(x)}{log_b(y)}
\end{split}
$$
### Proof
$$
\begin{split}
n &= b^x \Leftrightarrow x = log_b(n) \\
m &= b^y \Leftrightarrow y = log_b(m)  \\ \\
\frac{n}{m} &= \frac{b^x}{b^y} = b^{x - y} \\
log_b\left(\frac{n}{m}\right) &= log_b\left(b^{x - y}\right) = x-y = log_n(n)-log_n(m) \\
\end{split}
$$
## [[exponential]] inside a [[logarithm]]

$$
\begin{split}
log_b(x^y) = y \cdot log_b(x)
\end{split}
$$
### Proof
$$
\begin{split}
x &= b^k  \Leftrightarrow k = log_b(x)   \\ \\
log_b\left(x^y\right) &= log_b\left(\left(b^k\right)^y\right) =  log_b\left(b^{ky}\right) \\
&=yk = y \cdot log_b(x)
\end{split}
$$
## basis transformation
$$
\begin{split}
log_b(x) = \frac{log_a(x)}{log_a(b)}
\end{split}
$$

### Proof
$$
\begin{split}
x &= b^m  \Leftrightarrow m = log_b(x)   \\
x &= a^n  \Leftrightarrow n = log_a(x)   \\\\
x &= b^m \\
log_a\left(x\right) 
&= log_a\left(b^m\right) \\
&= m \cdot log_a\left(b\right) \\
&= log_b(x) \cdot log_a\left(b\right)   \\
\Rightarrow  log_b(x) &= \frac{log_a\left(x\right)}{log_a\left(b\right)}  \\


\end{split}
$$


# anki
START
Basic
[[logarithm]]
- definition plus two basic properties derived from the definition
- properties with proof
	- [[addition]] inside a [[logarithm]]
	- [[substraction]] inside a [[logarithm]]
	- [[exponential]] inside a [[logarithm]]
	- basis transformation

Back: 
## Definition
- the [[logarithm]] is the [[inverse function]] of the [[exponential]]

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

# Properties
## [[addition]] inside a [[logarithm]]
$$
\begin{split}
log_b(x+y) = log_b(x) \cdot log_b(y)
\end{split}
$$
### Proof
$$
\begin{split}
n &= b^x \Leftrightarrow x = log_b(n) \\
m &= b^y \Leftrightarrow y = log_b(m)  \\ \\
nm &= b^x \cdot b^y = b^{x + y} \\
log_b(nm) &= log_b\left(b^{x + y}\right) = x+y = log_n(n)+log_n(m) \\
\end{split}
$$
## [[substraction]] inside a [[logarithm]]
$$
\begin{split}
log_b\left(x-y\right) = \frac{log_b(x)}{log_b(y)}
\end{split}
$$
### Proof
$$
\begin{split}
n &= b^x \Leftrightarrow x = log_b(n) \\
m &= b^y \Leftrightarrow y = log_b(m)  \\ \\
\frac{n}{m} &= \frac{b^x}{b^y} = b^{x - y} \\
log_b\left(\frac{n}{m}\right) &= log_b\left(b^{x - y}\right) = x-y = log_n(n)-log_n(m) \\
\end{split}
$$
## [[exponential]] inside a [[logarithm]]

$$
\begin{split}
log_b(x^y) = y \cdot log_b(x)
\end{split}
$$
### Proof
$$
\begin{split}
x &= b^k  \Leftrightarrow k = log_b(x)   \\ \\
log_b\left(x^y\right) &= log_b\left(\left(b^k\right)^y\right) =  log_b\left(b^{ky}\right) \\
&=yk = y \cdot log_b(x)
\end{split}
$$
## basis transformation
$$
\begin{split}
log_b(x) = \frac{log_a(x)}{log_a(b)}
\end{split}
$$

### Proof
$$
\begin{split}
x &= b^m  \Leftrightarrow m = log_b(x)   \\
x &= a^n  \Leftrightarrow n = log_a(x)   \\\\
x &= b^m \\
log_a\left(x\right) 
&= log_a\left(b^m\right) \\
&= m \cdot log_a\left(b\right) \\
&= log_b(x) \cdot log_a\left(b\right)   \\
\Rightarrow  log_b(x) &= \frac{log_a\left(x\right)}{log_a\left(b\right)}  \\


\end{split}
$$

Tags: mathematics
<!--ID: 1683367530129-->
END