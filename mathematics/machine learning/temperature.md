### temperature
- setting for creativeness of a generative model by scaling the [[logit function|logits]] of the [[softmax function]]

- $T=1$: baseline.
- $T<1:$ **sharper** distribution → more deterministic (greedy-like).
- $T>1$: **flatter** distribution → more diverse/creative.


$$
P_i = \frac{\exp\left(\frac{Z_i}{T}\right)}{\sum_j \exp \left(\frac{Z_j}{T}\right)}
$$

# ------------

![[softmax function#softmax function]]


# anki


START
Basic
[[temperature]] of a generative [[neural network]]
Back: 
### temperature
- setting for creativeness of a generative model by scaling the [[logit function|logits]] of the [[softmax function]]

- $T=1$: baseline.
- $T<1:$ **sharper** distribution → more deterministic (greedy-like).
- $T>1$: **flatter** distribution → more diverse/creative.


$$
P_i = \frac{\exp\left(\frac{Z_i}{T}\right)}{\sum_j \exp \left(\frac{Z_j}{T}\right)}
$$

________________

### softmax function
- the [[softmax function]] $\mathrm{SOFTMAX}: \mathrm{R}^n \to [0,1]^{n}$ turns the input into a [[probability mass function (PMF)]]
	→ normalized positive output of the same dimensions

$$
\begin{split}
\mathrm{SOFTMAX}(Z) 
&= \frac{\exp{(Z_{(i,j)})}}{\sum_{k} \exp{(Z_{(i,k)})}}
\end{split}
$$

- used as output function in [[classification]] problems, for example with [[neural network]] and [[multinomial logistic regresssion]]

Tags: ml WS2526
<!--ID: 1761404411694-->
END
