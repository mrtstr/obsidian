### softmax function
- the [[softmax function]] $\mathrm{SOFTMAX}: \mathrm{R}^n \to [0,1]^{n}$ turns the input into a [[probability mass function (PMF)]]
	→ normalized positive output of the same dimensions

$$
\begin{split}
\mathrm{SOFTMAX}(Z)_i 
&= \frac{\exp{(Z_{i})}}{\sum_{k} \exp{(Z_{k})}}
\end{split}
$$

- used as output function in [[classification]] problems, for example with [[neural network]] and [[multinomial logistic regresssion]]

#### derivative of the softmax

$$
\begin{split}
\frac{\partial \mathrm{SOFTMAX}(Z)_i }{\partial Z_j}
=& \frac{\partial }{\partial Z_j} \frac{\exp{(Z_{i})}}{\sum_{k} \exp{(Z_{k})}} \\
=& \frac{\partial }{\partial Z_j} \frac{\exp{(Z_{i})}}{\sum_{k} \exp{(Z_{k})}} \\
=& \frac{\partial \exp{(Z_{i})}}{\partial Z_j} \frac{1}{\sum_{k} \exp{(Z_{k})}}+ \exp{(Z_{i})}\frac{\left(\sum_{k} \exp{(Z_{k})}\right)^{-2}}{\partial Z_j} \\
=& \mathrm{SOFTMAX}(Z)_j \cdot \mathrm{I} \left[i=j\right]+ \frac{-\exp{(Z_{i})}}{\left(\sum_{k} \exp{(Z_{k})}\right)^{-2}} \frac{\sum_{k} \exp{(Z_{k})}}{\partial Z_j}\\
=& \mathrm{SOFTMAX}(Z)_j \cdot \mathrm{I} \left[i=j\right]+ \frac{-\exp{(Z_{i})}}{\left(\sum_{k} \exp{(Z_{k})}\right)^{-2}} \exp{(Z_{j})}\\
=& \mathrm{SOFTMAX}(Z)_j \cdot \mathrm{I} \left[i=j\right]-\mathrm{SOFTMAX}(Z)_j\mathrm{SOFTMAX}(Z)_i\\
=& \begin{cases}
\mathrm{SOFTMAX}(Z)_j (1- \mathrm{SOFTMAX}(Z)_j) & ,for\ i=j \\
-\mathrm{SOFTMAX}(Z)_j \mathrm{SOFTMAX}(Z)_i  & ,for\ i\neq j  \\
\end{cases}
\end{split}
$$

# anki

START
Basic
[[softmax function]]
- definition
- [[derivative]] (no proof)
- application
Back: 
### softmax function
- the [[softmax function]] $\mathrm{SOFTMAX}: \mathrm{R}^n \to [0,1]^{n}$ turns the input into a [[probability mass function (PMF)]]
	→ normalized positive output of the same dimensions

$$
\begin{split}
\mathrm{SOFTMAX}(Z)_i 
&= \frac{\exp{(Z_{i})}}{\sum_{k} \exp{(Z_{k})}}
\end{split}
$$

- used as output function in [[classification]] problems, for example with [[neural network]] and [[multinomial logistic regresssion]]

#### derivative of the softmax

$$
\begin{split}
\frac{\partial \mathrm{SOFTMAX}(Z)_i }{\partial Z_j}
=& \frac{\partial }{\partial Z_j} \frac{\exp{(Z_{i})}}{\sum_{k} \exp{(Z_{k})}} \\
=& \frac{\partial }{\partial Z_j} \frac{\exp{(Z_{i})}}{\sum_{k} \exp{(Z_{k})}} \\
=& \frac{\partial \exp{(Z_{i})}}{\partial Z_j} \frac{1}{\sum_{k} \exp{(Z_{k})}}+ \exp{(Z_{i})}\frac{\left(\sum_{k} \exp{(Z_{k})}\right)^{-2}}{\partial Z_j} \\
=& \mathrm{SOFTMAX}(Z)_j \cdot \mathrm{I} \left[i=j\right]+ \frac{-\exp{(Z_{i})}}{\left(\sum_{k} \exp{(Z_{k})}\right)^{-2}} \frac{\sum_{k} \exp{(Z_{k})}}{\partial Z_j}\\
=& \mathrm{SOFTMAX}(Z)_j \cdot \mathrm{I} \left[i=j\right]+ \frac{-\exp{(Z_{i})}}{\left(\sum_{k} \exp{(Z_{k})}\right)^{-2}} \exp{(Z_{j})}\\
=& \mathrm{SOFTMAX}(Z)_j \cdot \mathrm{I} \left[i=j\right]-\mathrm{SOFTMAX}(Z)_j\mathrm{SOFTMAX}(Z)_i\\
=& \begin{cases}
\mathrm{SOFTMAX}(Z)_j (1- \mathrm{SOFTMAX}(Z)_j) & ,for\ i=j \\
-\mathrm{SOFTMAX}(Z)_j \mathrm{SOFTMAX}(Z)_i  & ,for\ i\neq j  \\
\end{cases}
\end{split}
$$


Tags: mathematics SS25
<!--ID: 1752949761743-->
END

START
Basic
[[derivative]] of the [[softmax function]] with calculation

Back: 
### softmax function
- the [[softmax function]] $\mathrm{SOFTMAX}: \mathrm{R}^n \to [0,1]^{n}$ turns the input into a [[probability mass function (PMF)]]
	→ normalized positive output of the same dimensions

$$
\begin{split}
\mathrm{SOFTMAX}(Z)_i 
&= \frac{\exp{(Z_{i})}}{\sum_{k} \exp{(Z_{k})}}
\end{split}
$$

- used as output function in [[classification]] problems, for example with [[neural network]] and [[multinomial logistic regresssion]]

#### derivative of the softmax

$$
\begin{split}
\frac{\partial \mathrm{SOFTMAX}(Z)_i }{\partial Z_j}
=& \frac{\partial }{\partial Z_j} \frac{\exp{(Z_{i})}}{\sum_{k} \exp{(Z_{k})}} \\
=& \frac{\partial }{\partial Z_j} \frac{\exp{(Z_{i})}}{\sum_{k} \exp{(Z_{k})}} \\
=& \frac{\partial \exp{(Z_{i})}}{\partial Z_j} \frac{1}{\sum_{k} \exp{(Z_{k})}}+ \exp{(Z_{i})}\frac{\left(\sum_{k} \exp{(Z_{k})}\right)^{-2}}{\partial Z_j} \\
=& \mathrm{SOFTMAX}(Z)_j \cdot \mathrm{I} \left[i=j\right]+ \frac{-\exp{(Z_{i})}}{\left(\sum_{k} \exp{(Z_{k})}\right)^{-2}} \frac{\sum_{k} \exp{(Z_{k})}}{\partial Z_j}\\
=& \mathrm{SOFTMAX}(Z)_j \cdot \mathrm{I} \left[i=j\right]+ \frac{-\exp{(Z_{i})}}{\left(\sum_{k} \exp{(Z_{k})}\right)^{-2}} \exp{(Z_{j})}\\
=& \mathrm{SOFTMAX}(Z)_j \cdot \mathrm{I} \left[i=j\right]-\mathrm{SOFTMAX}(Z)_j\mathrm{SOFTMAX}(Z)_i\\
=& \begin{cases}
\mathrm{SOFTMAX}(Z)_j (1- \mathrm{SOFTMAX}(Z)_j) & ,for\ i=j \\
-\mathrm{SOFTMAX}(Z)_j \mathrm{SOFTMAX}(Z)_i  & ,for\ i\neq j  \\
\end{cases}
\end{split}
$$

Tags: mathematics WS2526
<!--ID: 1764496843811-->
END