### stochastic independent
- a collection of [[event|events]] $A_1, ..., A_k$ is [[stochastic independent]] if the following is true

$$
\forall I \subseteq [k]: P\left(\bigcap\limits_{i \in I} A_i \right) = \prod\limits_{i \in I} P(A_i) 
$$

### pairwise stochastic independent
- a collection of [[event|events]] $A_1, ..., A_k$ is [[stochastic independent]] if the follwoing is true

$$
\forall i \neq j \in [k]: P\left( A_i \cap A_j \right) =  P(A_i) P(A_j) 
$$
- [[stochastic independent]] events are allways pairwise stochastic independent but not the other way around

### stochastic independent $\rightarrow$ pairwise stochastic independent
- its trivial because if the condition is true $\forall I \subseteq [k]$ it also inclused all pairs

### pairwise stochastic independent $\nrightarrow$ stochastic independent
- given the [[sample space]] $\Omega = \{1,2,3, 4\}$ and the [[event|envents]] $A=\{1,2\}$, $B=\{2,3\}$ and $C=\{1,3\}$

$$
\begin{split}
\mathbb{P}(A) = \mathbb{P}(B) =\mathbb{P}(C) = \frac{1}{2}
\end{split}
$$

- the [[event|events]] are pairwise stochastic independent because

$$
\begin{split}
\mathbb{P}(A \cap B) = \mathbb{P}(A) \mathbb{P}(B) = \frac{1}{4} \\
\mathbb{P}(A \cap C) = \mathbb{P}(A) \mathbb{P}(C) = \frac{1}{4} \\
\mathbb{P}(B \cap C) = \mathbb{P}(B) \mathbb{P}(C) = \frac{1}{4} \\
\end{split}
$$

- but not [[stochastic independent]] because

$$
\begin{split}
\mathbb{P}(A \cap B \cap C) = \mathbb{P}(\emptyset)  = 0 \neq 
 \mathbb{P}(A)\mathbb{P}(B) \mathbb{P}(C) = \frac{1}{16} \\
\end{split}
$$

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
### stochastic independent [[random variable|random variables]]
Two [[random variable]] $X$ and $Y$ an [[stochastic independent]] iff the following statements are true
1) $F_{XY}(x, y) = F_X(x)F_Y(y)$
2) $f_{XY}(x, y) = f_X(x)f_Y(y)$

### [[conditional distribution]] of independent [[random variable|random variables]]
$$
f_{X\mid Y}(x \mid y) = f_X(x)
$$
proof:
$$
f_{X\mid Y}(x \mid y) 
= \frac{f_{X, Y}(x, y)}{f_Y(y)}
= \frac{f_Y(y)f_X(x)}{f_Y(y)}
= f_X(x)
$$

# Anki
START
Basic
stochastic independence
- definition (2 and multiple [[event space|events]])
- properties
1) $P(A \mid B) =$ ?
2) $A \perp B \Leftrightarrow A \perp \overline{B}$ (proof)

Back: 
### stochastic independent
- a collection of [[event|events]] $A_1, ..., A_k$ is [[stochastic independent]] if the following is true

$$
\forall I \subseteq [k]: P\left(\bigcap\limits_{i \in I} A_i \right) = \prod\limits_{i \in I} P(A_i) 
$$


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

Tags: mathematics statistics
<!--ID: 1666457499372-->
END



START
Basic
pairwise stochastic independent
- definition
- difference to [[stochastic independent]]
Back: 
### stochastic independent
- a collection of [[event|events]] $A_1, ..., A_k$ is [[stochastic independent]] if the following is true

$$
\forall I \subseteq [k]: P\left(\bigcap\limits_{i \in I} A_i \right) = \prod\limits_{i \in I} P(A_i) 
$$

### pairwise stochastic independent
- a collection of [[event|events]] $A_1, ..., A_k$ is [[stochastic independent]] if the follwoing is true

$$
\forall i \neq j \in [k]: P\left( A_i \cap A_j \right) =  P(A_i) P(A_j) 
$$
- [[stochastic independent]] events are allways pairwise stochastic independent but not the other way around

### stochastic independent $\rightarrow$ pairwise stochastic independent
- its trivial because if the condition is true $\forall I \subseteq [k]$ it also inclused all pairs

### pairwise stochastic independent $\nrightarrow$ stochastic independent
- given the [[sample space]] $\Omega = \{1,2,3, 4\}$ and the [[event|envents]] $A=\{1,2\}$, $B=\{2,3\}$ and $C=\{1,3\}$

$$
\begin{split}
\mathbb{P}(A) = \mathbb{P}(B) =\mathbb{P}(C) = \frac{1}{2}
\end{split}
$$

- the [[event|events]] are pairwise stochastic independent because

$$
\begin{split}
\mathbb{P}(A \cap B) = \mathbb{P}(A) \mathbb{P}(B) = \frac{1}{4} \\
\mathbb{P}(A \cap C) = \mathbb{P}(A) \mathbb{P}(C) = \frac{1}{4} \\
\mathbb{P}(B \cap C) = \mathbb{P}(B) \mathbb{P}(C) = \frac{1}{4} \\
\end{split}
$$

- but not [[stochastic independent]] because

$$
\begin{split}
\mathbb{P}(A \cap B \cap C) = \mathbb{P}(\emptyset)  = 0 \neq 
 \mathbb{P}(A)\mathbb{P}(B) \mathbb{P}(C) = \frac{1}{16} \\
\end{split}
$$

Tags: mathematics statistics
<!--ID: 1717336808317-->
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
Tags: mathematics statistics
<!--ID: 1666517556853-->
END

START
Basic
[[stochastic independent]] [[random variable]]
- proprieties of the PDF and CDF

Back: 
Two [[random variable]] $X$ and $Y$ an [[stochastic independent]] iff the following statements are true
1) $F_{XY}(x, y) = F_X(x)F_Y(y)$
2) $f_{XY}(x, y) = f_X(x)f_Y(y)$
Tags: mathematics statistics
<!--ID: 1670766688733-->
END


START
Basic
[[conditional distribution]] of independent [[random variable|random variables]] (with proof)
Back: 
$$
f_{X\mid Y}(x \mid y) = f_X(x)
$$
proof:
$$
f_{X\mid Y}(x \mid y) 
= \frac{f_{X, Y}(x, y)}{f_Y(y)}
= \frac{f_Y(y)f_X(x)}{f_Y(y)}
= f_X(x)
$$
Tags: mathematics statistics
<!--ID: 1671186732887-->
END


START
Basic
- proof that from pairwise stochastic independence does not follow [[stochastic independent|stochstic independence]]
- proof that from [[stochastic independent|stochstic independence]] follows pairwise stochastic independence

Back: 

### stochastic independent $\rightarrow$ pairwise stochastic independent
- its trivial because if the condition is true $\forall I \subseteq [k]$ it also inclused all pairs

### pairwise stochastic independent $\nrightarrow$ stochastic independent
- given the [[sample space]] $\Omega = \{1,2,3, 4\}$ and the [[event|envents]] $A=\{1,2\}$, $B=\{2,3\}$ and $C=\{1,3\}$

$$
\begin{split}
\mathbb{P}(A) = \mathbb{P}(B) =\mathbb{P}(C) = \frac{1}{2}
\end{split}
$$

- the [[event|events]] are pairwise stochastic independent because

$$
\begin{split}
\mathbb{P}(A \cap B) = \mathbb{P}(A) \mathbb{P}(B) = \frac{1}{4} \\
\mathbb{P}(A \cap C) = \mathbb{P}(A) \mathbb{P}(C) = \frac{1}{4} \\
\mathbb{P}(B \cap C) = \mathbb{P}(B) \mathbb{P}(C) = \frac{1}{4} \\
\end{split}
$$

- but not [[stochastic independent]] because

$$
\begin{split}
\mathbb{P}(A \cap B \cap C) = \mathbb{P}(\emptyset)  = 0 \neq 
 \mathbb{P}(A)\mathbb{P}(B) \mathbb{P}(C) = \frac{1}{16} \\
\end{split}
$$

_______________________

### stochastic independent
- a collection of [[event|events]] $A_1, ..., A_k$ is [[stochastic independent]] if the following is true

$$
\forall I \subseteq [k]: P\left(\bigcap\limits_{i \in I} A_i \right) = \prod\limits_{i \in I} P(A_i) 
$$

### pairwise stochastic independent
- a collection of [[event|events]] $A_1, ..., A_k$ is [[stochastic independent]] if the follwoing is true

$$
\forall i \neq j \in [k]: P\left( A_i \cap A_j \right) =  P(A_i) P(A_j) 
$$
- [[stochastic independent]] events are allways pairwise stochastic independent but not the other way around

Tags: mathematics statistics
<!--ID: 1717746139307-->
END