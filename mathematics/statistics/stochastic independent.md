Two [[discrete random variable|random variables]] are [[stochastic independent|independent]] if the occurrence of [[event space|event]] $B$ does not change the [[probability]] that [[event space|event]] also happened

## Definition $A \perp B$
$$P(A \cap B) = P(A)P(B)$$

$$P\left(\bigcap\limits_{i=1}^{k} A_i \right) = \prod\limits_{i=1}^{k} P(A_i) $$
## Properties $A \perp B$
1) $P(A \mid B) = P(A)$
2) $A \perp B \Leftrightarrow A \perp \overline{B}$
$$
\begin{split}
P(A \cup \overline{B})
&=P(A)-P(A \cup B)
&=P(A)-P(A) P(B) \\
&=P(A)(1- P(B))\\
&=P(A)P(\overline{B}) 
\end{split}
$$

START
Basic
stochastic independence
- definition (2 and multiple [[event space|events]])
- properties
1) $P(A \mid B) =$ ?
2) $A \perp B \Leftrightarrow A \perp \overline{B}$ (proof)

Back: 
Two [[discrete random variable|random variables]] are [[stochastic independent|independent]] if the occurrence of [[event space|event]] $B$ does not change the [[probability]] that [[event space|event]] also happened

## Definition $A \perp B$
$$P(A \cap B) = P(A)P(B)$$

$$P\left(\bigcap\limits_{i=1}^{k} A_i \right) = \prod\limits_{i=1}^{k} P(A_i) $$
## Properties $A \perp B$
1) $P(A \mid B) = P(A)$
2) $A \perp B \Leftrightarrow A \perp \overline{B}$
$$
\begin{split}
P(A \cup \overline{B})
&=P(A)-P(A \cup B)
&=P(A)-P(A) P(B) \\
&=P(A)(1- P(B))\\
&=P(A)P(\overline{B}) 
\end{split}
$$

Tags: mathematics, statistics
<!--ID: 1666457499372-->
END


START
Basic
- probability of a coin showing head after $n$ tries (and only number before)
- probability of a coin showing head sooner or later after infinite tries

Back: 
the coin tosses are [[stochastic independent]]:
$$
p_n = \sum\limits_{i=1}^n \frac{1}{2}^i=\frac{1}{2} \cdot \frac{1}{4} \cdot...
$$
$$
\lim\limits_{n \rightarrow \infty} p_n = 1
$$
Tags: mathematics, statistics
<!--ID: 1666517556853-->
END