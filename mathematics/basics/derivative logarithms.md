![[derivative#definition derivative]]

## [[derivative]] of the [[natural logarithm]]
### given
![[natural logarithm#properties]]
![[logarithm#theorem]]


### theorem
$$
\frac{d\ln(ax)}{dx} = \frac{1}{ax}
$$
### proof
$$
\begin{split}
\frac{d\ln(ax)}{dx} 
&= \lim_{h \rightarrow 0} \frac{\ln(ax+h) - \ln(ax)}{h} \\
&= \lim_{h \rightarrow 0} \frac{\ln\left(\frac{ax+h}{ax}\right)}{h} \\
&= \lim_{h \rightarrow 0} \frac{\ln\left(1 + \frac{h}{ax}\right)}{h} \\
&= \lim_{t \rightarrow 0} \frac{\ln\left(1 + t\right)}{t \cdot ax} \quad with \quad t=\frac{h}{ax} \\
&= \frac{1}{ax} \lim_{t \rightarrow 0} \frac{\ln\left(1 + t\right)}{t \cdot ax}  \\
&= \frac{1}{ax}  \\
\end{split}
$$

## [[derivative]] of the [[logarithm]]
### given
![[logarithm#theorem]]

![[derivative logarithms#theorem]]

### theorem

$$
\frac{d\log_b(ax)}{dx} = \frac{1}{\ln(b)ax}
$$
### proof
$$
\begin{split}
\frac{d\log_b(ax)}{dx} 
&= \frac{d\frac{\ln(ax)}{\ln(b)}}{dx}  \\
&= \frac{1}{\ln(b)} \frac{d\ln(ax)}{dx}  \\
&= \frac{1}{\ln(b)} \frac{1}{ax}  \\

\end{split}
$$
# anki
START
Basic
[[derivative]] of the [[natural logarithm]] $\frac{d\ln(ax)}{dx}$ with [[proof]]

Back: 
### theorem
$$
\frac{d\ln(ax)}{dx} = \frac{1}{ax}
$$
### given
$$
\lim_{h \rightarrow 0} \frac{\ln(1 + h)}{h} = 1
$$
$$
\begin{split}
log_b\left(\frac{x}{y}\right) = log_b(x) - log_b(y)
\end{split}
$$

### proof
$$
\begin{split}
\frac{d\ln(ax)}{dx} 
&= \lim_{h \rightarrow 0} \frac{\ln(ax+h) - \ln(ax)}{h} \\
&= \lim_{h \rightarrow 0} \frac{\ln\left(\frac{ax+h}{ax}\right)}{h} \\
&= \lim_{h \rightarrow 0} \frac{\ln\left(1 + \frac{h}{ax}\right)}{h} \\
&= \lim_{t \rightarrow 0} \frac{\ln\left(1 + t\right)}{t \cdot ax} \quad with \quad t=\frac{h}{ax} \\
&= \frac{1}{ax} \lim_{t \rightarrow 0} \frac{\ln\left(1 + t\right)}{t \cdot ax}  \\
&= \frac{1}{ax}  \\
\end{split}
$$

Tags: mathematics
<!--ID: 1690611536702-->
END

START
Basic
[[derivative]] of the [[logarithm]] $\frac{d\log_b(ax)}{dx}$ with [[proof]]

Back: 
### theorem

$$
\frac{d\log_b(ax)}{dx} = \frac{1}{\ln(b)ax}
$$
### given
$$
\begin{split}
log_b(x) = \frac{log_a(x)}{log_a(b)}
\end{split}
$$
$$
\lim_{h \rightarrow 0} \frac{\ln(1 + h)}{h} = 1
$$
$$
\begin{split}
log_b\left(\frac{x}{y}\right) = log_b(x) - log_b(y)
\end{split}
$$

### proof
$$
\begin{split}
\frac{d\log_b(ax)}{dx} 
&= \frac{d\frac{\ln(ax)}{\ln(b)}}{dx}  \\
&= \frac{1}{\ln(b)} \frac{d\ln(ax)}{dx}  \\
&= \frac{1}{\ln(b)} \frac{1}{ax}  \\

\end{split}
$$

$$
\begin{split}
\frac{d\ln(ax)}{dx} 
&= \lim_{h \rightarrow 0} \frac{\ln(ax+h) - \ln(ax)}{h} \\
&= \lim_{h \rightarrow 0} \frac{\ln\left(\frac{ax+h}{ax}\right)}{h} \\
&= \lim_{h \rightarrow 0} \frac{\ln\left(1 + \frac{h}{ax}\right)}{h} \\
&= \lim_{t \rightarrow 0} \frac{\ln\left(1 + t\right)}{t \cdot ax} \quad with \quad t=\frac{h}{ax} \\
&= \frac{1}{ax} \lim_{t \rightarrow 0} \frac{\ln\left(1 + t\right)}{t \cdot ax}  \\
&= \frac{1}{ax}  \\
\end{split}
$$
Tags: mathematics
<!--ID: 1690611536708-->
END