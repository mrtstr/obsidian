### cumulative distribution function (CDF)
- a [[function]] $F: \mathbb{R} \to [0,1]$ is a [[cumulative distribution function (CDF)]] if
1)  $F$ is [[monotonic function|monote increasing]] [[function]] 
2) $\lim_{x \to - \infty} F(x) = 0$
3) $\lim_{x \to \infty} F(x) = 1$

### [[cumulative distribution function (CDF)|CDFs]] and [[probability measure|probability measures]] induce each other
- for each [[cumulative distribution function (CDF)]] $F: \mathbb{R} \to [0,1]$ there exists a [[probability measure]] $\mathcal{P}:\mathcal{B}(\mathbb{R}) \to [0,1]$ and vise versa
$$
\begin{split}
F_X(x) &= \mathcal{P}_X((-\infty, x]) \\ 
\mathcal{P}((a, b]) &= F(b) - F(a) \\ 
\end{split}
$$
#### proof
- fist we need to show that $F(x) = \mathcal{P}_X((-\infty, x])$ is a [[cumulative distribution function (CDF)]]
$$
\lim_{x \to -\infty} \mathcal{P}_X((-\infty, x]) = \mathcal{P}_X(\emptyset) = 0
$$
$$
\lim_{x \to \infty} \mathcal{P}_X((-\infty, x]) = \mathcal{P}_X(\mathbb{R}) = 1
$$
- $F(x) = \mathcal{P}_X((-\infty, x])$ is monotone increasing
$$
\begin{split}
&x \leq y \\
\Rightarrow &\left\{\omega \in \Omega: X(\omega) \in (-\infty, x]\right\} \subseteq \left\{\omega \in \Omega: X(\omega) \in (-\infty, y]\right\}  \\


\Rightarrow& \mathbb{P}\left(X^{-1}\left((-\infty, y]\right)\right) =\mathbb{P}\left(X^{-1}\left((-\infty, x]\right)\right) + 
 \mathbb{P}\left(X^{-1}\left((x, y]\right)\right)\\
\Rightarrow& \mathbb{P}\left(X^{-1}\left((-\infty, x]\right)\right) \leq\mathbb{P}\left(X^{-1}\left((-\infty, y]\right)\right) 
\end{split}
$$
- the second part is to show that $\mathcal{P}((a, b]) = F(b) - F(a)$ is a [[probability measure]]
$$
\begin{split}
\mathcal{P}_X(\mathbb{R}) 
&= \lim_{a \to - \infty} \lim_{b \to  \infty} \mathcal{P}((a, b]) \\
&= \lim_{a \to - \infty} \lim_{b \to  \infty} F(b) - F(a) \\
&= \lim_{b \to  \infty} F(b)  - \lim_{a \to - \infty} F(a) \\
&= 1 - 0 \\
\end{split}
$$

$$
\begin{split}
\mathcal{P}_X(\emptyset) 
&= \lim_{a \to c} \lim_{b \to  c} \mathcal{P}((a, b]) \\
&= \lim_{a \to c} \lim_{b \to  c}  F(b) - F(a) \\
&=  \lim_{b \to  c}  F(b) - \lim_{a \to c} F(a) \\
&= F(c) - F(c) \\
&=  0 \\
\end{split}
$$

[[disjoint]]

### every [[random variable]] has a [[cumulative distribution function (CDF)|CDF]]
- every [[random variable]] $X: \Omega \to \mathbb{R}$ has a [[distribution]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1] = \mathbb{P}\left(X^{-1}(C)\right)$  (which is a [[probability measure]] on $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$) 
- [[probability measure]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ induces a [[cumulative distribution function (CDF)]] $F_X(x) = \mathcal{P}_X((-\infty, x])$
- thus every [[random variable]] $X$ also has a [[cumulative distribution function (CDF)]] $F_X$

$$
\begin{split}
F_X(x) 
&= \mathcal{P}_X((-\infty, x]) \\ 
&= \mathbb{P}\left(X^{-1}((-\infty, x])\right) \\
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) \in (-\infty, x]\right\}\right) \\
&= \mathbb{P}\left(x \leq X\right) \\
\end{split}
$$


### $F(x + y) = F(x) + \mathcal{P}((x, x+y])$
- it followns directry from the properties of [[probability measure]] and the fact that $F(x) = \mathcal{P}((\infty, x])$ has [[probability measure]] on $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$ 

$$
\begin{split}
\mathcal{P}((-\infty, x+y])  
= \mathcal{P}((-\infty, x] \cup(x, x+y]) \\
= \mathcal{P}((-\infty, x]) + \mathcal{P}((x, x+y]) \\
\end{split}
$$



### limits
$$
F_X(x^-) = \lim_{y \rightarrow x, y < x} F_X(y)
$$
$$
F_X(x^+) = \lim_{y \rightarrow x, y > x} F_X(y)
$$
#### Properties
1) $P(X \leq x)=F_X(x)$
2) $P(X=x) = F_X(x) - F_X(x^+)$
3) $P(X<x)=F_X(x^-)$
4) $F_X(x)=F_X(x^+)$ continuity from the right ([[discrete distribution|discrete]] and [[continuous random variable|continuous]])
5) $F_X(x)=F_X(x^+)=F_X(x^-)$ continuity from the both sides ([[continuous random variable|continuous]])
	- proof: its because $f_X(x)=0$
### empirical CDF 
Approximated CDF from [[statistical sample|samples]] 
$\widehat{F}_X(x)=\frac{1}{n} \sum\limits_{i=1}^n\mathbb{I}[x_i \leq x]$ 

### relationship [[cumulative distribution function (CDF)]] to the [[quantile function]] $Q_X(q)$
- $Q_X(q)$ is the smallest values with a [[cumulative distribution function (CDF)]] less or equal than $q$  
$$Q_X(q) = \inf\left\{x \mid q \leq F_X(x)\right\}$$
- $Q_X(q)$ is the inverse of the [[cumulative distribution function (CDF)]]
$$Q_X(q)=F_X^{-1}(q)\quad with \: q = F_X(x)=P(X \leq x)$$



# -----------------

![[distribution#distribution]]

![[random variable#a random variable induces a probability measure]]

![[probability measure#probability measure]]

![[random variable#random variable]]



# anki



START
Basic
proof that every [[random variable]] has a [[cumulative distribution function (CDF)]]

Back: 
### every [[random variable]] has a [[cumulative distribution function (CDF)|CDF]]
- every [[random variable]] $X: \Omega \to \mathbb{R}$ has a [[distribution]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1] = \mathbb{P}\left(X^{-1}(C)\right)$  (which is a [[probability measure]] on $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$) 
- [[probability measure]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ induces a [[cumulative distribution function (CDF)]] $F_X(x) = \mathcal{P}_X((-\infty, x])$
- thus every [[random variable]] $X$ also has a [[cumulative distribution function (CDF)]] $F_X$

$$
\begin{split}
F_X(x) 
&= \mathcal{P}_X((-\infty, x]) \\ 
&= \mathbb{P}\left(X^{-1}((-\infty, x])\right) \\
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) \in (-\infty, x]\right\}\right) \\
&= \mathbb{P}\left(x \leq X\right) \\
\end{split}
$$



### cumulative distribution function (CDF)
- a [[function]] $F: \mathbb{R} \to [0,1]$ is a [[cumulative distribution function (CDF)]] if
1)  $F$ is [[monotonic function|monote increasing]] [[function]] 
2) $\lim_{x \to - \infty} F(x) = 0$
3) $\lim_{x \to \infty} F(x) = 1$

### [[cumulative distribution function (CDF)|CDFs]] and [[probability measure|probability measures]] induce each other
- for each [[cumulative distribution function (CDF)]] $F: \mathbb{R} \to [0,1]$ there exists a [[probability measure]] $\mathcal{P}:\mathcal{B}(\mathbb{R}) \to [0,1]$ and vise versa
$$
\begin{split}
F_X(x) &= \mathcal{P}_X((-\infty, x]) \\ 
\mathcal{P}((a, b]) &= F(b) - F(a) \\ 
\end{split}
$$
#### proof
- fist we need to show that $F(x) = \mathcal{P}_X((-\infty, x])$ is a [[cumulative distribution function (CDF)]]
$$
\lim_{x \to -\infty} \mathcal{P}_X((-\infty, x]) = \mathcal{P}_X(\emptyset) = 0
$$
$$
\lim_{x \to \infty} \mathcal{P}_X((-\infty, x]) = \mathcal{P}_X(\mathbb{R}) = 1
$$
- $F(x) = \mathcal{P}_X((-\infty, x])$ is monotone increasing
$$
\begin{split}
&x \leq y \\
\Rightarrow &\left\{\omega \in \Omega: X(\omega) \in (-\infty, x]\right\} \subseteq \left\{\omega \in \Omega: X(\omega) \in (-\infty, y]\right\}  \\


\Rightarrow& \mathbb{P}\left(X^{-1}\left((-\infty, y]\right)\right) =\mathbb{P}\left(X^{-1}\left((-\infty, x]\right)\right) + 
 \mathbb{P}\left(X^{-1}\left((x, y]\right)\right)\\
\Rightarrow& \mathbb{P}\left(X^{-1}\left((-\infty, x]\right)\right) \leq\mathbb{P}\left(X^{-1}\left((-\infty, y]\right)\right) 
\end{split}
$$




### distribution
- given a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$ and a [[random variable]] $X: \Omega \to \mathbb{R}$ (which is a [[measurable function]] $X: (\Omega, \mathcal{A}) \to \left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$)
- $X$ is inducing the [[probability measure]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ from the [[borel sigma algebra]] $\mathcal{B}(\mathbb{R})$ it the interval $[0,1]$ (assigning a probability to each borel set $\subset \mathbb{R}$)
- $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ is called the [[distribution]] of $X$ and exists for every [[random variable]] 
$$
\begin{split}
\mathcal{P}_X(C) 
&= \mathbb{P}\left(X^{-1}(C \subseteq \mathbb{R})\right) \\
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) \in C\right\}\right) \\
\end{split}
$$

### a [[random variable]] induces a [[probability measure]]
- given a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$ and a [[measurable function]] $X: (\Omega, \mathcal{A}) \to (\mathbb{R}, \mathcal{B})$ we can define a [[probability measure]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ 

$$
\begin{split}
\mathcal{P}_X(C \subseteq \mathbb{R}) 
&= \mathbb{P}\left(X^{-1}(C) \subseteq \Omega\right) \\
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) \in C\right\}\right) \\
\end{split}
$$


#### proof
- the first proberties of a [[probability measure]] is trivial
$$
\begin{split}
\mathcal{P}_X(\emptyset \subseteq \mathbb{R}) 
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) \in \emptyset \right\}\right) \\
&=  \mathbb{P}\left( \emptyset \right) 
= 0
\end{split}
$$
- since $X: \Omega \to \mathbb{R}$ is a [[function]] all elements of the [[sample space]] $\Omega$ have to be mapped to a [[real numbers|real number]] and $P\left( \Omega \right) = 1$ is given by the definition of a [[probability function]]
$$
\begin{split}
\mathcal{P}_X(\mathbb{R}) 
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) \in \mathbb{R}\right\}\right) \\
&=  \mathbb{P}\left( \Omega \right) 
= 1
\end{split}
$$

- given two [[disjoint]] subsets of the [[real numbers]] $A, B \subseteq \mathbb{R}$
- fist we need to show that the image (of $X^{-1}$) of two [[disjoint]] [[set|sets]] is still [[disjoint]] 
$$
\begin{split}
A \cap B = \emptyset \Leftrightarrow X^{-1}(A) \cap X^{-1}(B) = \emptyset
\end{split}
$$
- because of the properties of the [[function]] we know the follwoing
$$
\begin{split}
\forall x, y \in \mathbb{R}: X(\omega) = x \land \mathbb{R}: X(\omega) = y &\Rightarrow x = y \\
\Leftrightarrow \\
\forall x, y \in \mathbb{R}: X^{-1}(x) = X^{-1}(y) &\Rightarrow x = y
\end{split}
$$
- thus $X^{-1}(A)$ and $X^{-1}(B)$ have to be [[disjoint]]

$$
\begin{split}
\mathcal{P}_X(A \cup B) 
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) \in A \cup B \right\}\right) \\
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) \in A  \right\} \cup \left\{\omega \in \Omega : X(\omega) \in  B \right\}\right) \\
&= \mathbb{P}\left( X^{-1}(A) \cup X^{-1}(B)\right) \\
&= \mathbb{P}\left( X^{-1}(A)\right) + \mathbb{P}\left( X^{-1}(B)\right)  \\

&= \mathcal{P}_X(A) + \mathcal{P}_X(B) \\
\end{split}
$$


__________________

### probability measure
- given a [[measurable space]] $(\Omega, \mathcal{A})$ of a [[set]] $\Omega$ equiped with a [[sigma algebra]] $\mathcal{A}$ a [[function]] $P: \mathcal{A} \mapsto [0,1]$ is a [[probability measure]]
$$
P: \mathcal{A} \mapsto [0,1]
$$

- the probability of the [[empty set]] is zero
$$
\begin{split}
P(\emptyset) = 0 \\
\end{split}
$$

- the [[probability]] of the [[sample space]] is one
$$
\begin{split}
P(\Omega) = 1 \\
\end{split}
$$
- given a [[countable]] collection of [[disjunct]] events $(A_n)_{n \in \mathbb{N}}$ 
$$
\begin{split}
P\left(\bigcup_{i \in \mathbb{N}} A_i \right) = \sum_{i \in \mathbb{N}} P(A_i) \\
\end{split}
$$
#### derived properties
- propability of the [[complement]]
$$
\begin{split}
P\left(A^c\right) 
&= 1 - P(A) \\
\end{split}
$$

- probability of the [[union]]
$$
\begin{split}
P\left(A \cup B\right) 
&= P(A) + P(B) - P\left(A \cup B\right)  \\
\end{split}
$$


### random variable
- given a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$
- a [[function]] $X: \Omega \to \mathbb{R}$ from the [[sample space]] $\Omega$ to the [[real numbers]] $\mathbb{R}$ is a [[random variable]] if it's a [[measurable function]] $X: (\Omega, \mathcal{A}) \to \left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$ from the [[measurable space]] of $(\Omega, \mathcal{A})$ to the [[real numbers]] with the [[borel sigma algebra]] (which are a [[measurable space]] too)
- this is the case exactly when the following is true (given the [[inverse function]] $X^{-1}: \mathbb{R} \to \Omega$)
$$
\forall x \in \mathbb{R}: X^{-1}\left((-\infty, x]\right) = \{\omega \in \Omega: X(\omega) \in (-\infty, x]\} \in \mathcal{A}
$$

Tags: mathematics statistics
<!--ID: 1664619948160-->
END

START
Basic
[[cumulative distribution function (CDF)]]
- definition
- relationship to [[probability measure]] (no proof)
- relationship to random variables (no proof)
Back: 
### cumulative distribution function (CDF)
- a [[function]] $F: \mathbb{R} \to [0,1]$ is a [[cumulative distribution function (CDF)]] if
1)  $F$ is [[monotonic function|monote increasing]] [[function]] 
2) $\lim_{x \to - \infty} F(x) = 0$
3) $\lim_{x \to \infty} F(x) = 1$

### [[cumulative distribution function (CDF)|CDFs]] and [[probability measure|probability measures]] induce each other
- for each [[cumulative distribution function (CDF)]] $F: \mathbb{R} \to [0,1]$ there exists a [[probability measure]] $\mathcal{P}:\mathcal{B}(\mathbb{R}) \to [0,1]$ and vise versa
$$
\begin{split}
F_X(x) &= \mathcal{P}_X((-\infty, x]) \\ 
\mathcal{P}((a, b]) &= F(b) - F(a) \\ 
\end{split}
$$
#### proof
- fist we need to show that $F(x) = \mathcal{P}_X((-\infty, x])$ is a [[cumulative distribution function (CDF)]]
$$
\lim_{x \to -\infty} \mathcal{P}_X((-\infty, x]) = \mathcal{P}_X(\emptyset) = 0
$$
$$
\lim_{x \to \infty} \mathcal{P}_X((-\infty, x]) = \mathcal{P}_X(\mathbb{R}) = 1
$$
- $F(x) = \mathcal{P}_X((-\infty, x])$ is monotone increasing
$$
\begin{split}
&x \leq y \\
\Rightarrow &\left\{\omega \in \Omega: X(\omega) \in (-\infty, x]\right\} \subseteq \left\{\omega \in \Omega: X(\omega) \in (-\infty, y]\right\}  \\


\Rightarrow& \mathbb{P}\left(X^{-1}\left((-\infty, y]\right)\right) =\mathbb{P}\left(X^{-1}\left((-\infty, x]\right)\right) + 
 \mathbb{P}\left(X^{-1}\left((x, y]\right)\right)\\
\Rightarrow& \mathbb{P}\left(X^{-1}\left((-\infty, x]\right)\right) \leq\mathbb{P}\left(X^{-1}\left((-\infty, y]\right)\right) 
\end{split}
$$
- the second part is to show that $\mathcal{P}((a, b]) = F(b) - F(a)$ is a [[probability measure]]
$$
\begin{split}
\mathcal{P}_X(\mathbb{R}) 
&= \lim_{a \to - \infty} \lim_{b \to  \infty} \mathcal{P}((a, b]) \\
&= \lim_{a \to - \infty} \lim_{b \to  \infty} F(b) - F(a) \\
&= \lim_{b \to  \infty} F(b)  - \lim_{a \to - \infty} F(a) \\
&= 1 - 0 \\
\end{split}
$$

$$
\begin{split}
\mathcal{P}_X(\emptyset) 
&= \lim_{a \to c} \lim_{b \to  c} \mathcal{P}((a, b]) \\
&= \lim_{a \to c} \lim_{b \to  c}  F(b) - F(a) \\
&=  \lim_{b \to  c}  F(b) - \lim_{a \to c} F(a) \\
&= F(c) - F(c) \\
&=  0 \\
\end{split}
$$



### every [[random variable]] has a [[cumulative distribution function (CDF)|CDF]]
- since every [[random variable]] $X: \Omega \to \mathbb{R}$ has a [[distribution]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ every $X$ also has a [[cumulative distribution function (CDF)]] $F_X$

$$
\begin{split}
F_X(x) 
&= \mathcal{P}_X((-\infty, x]) \\ 
&= \mathbb{P}\left(X^{-1}((-\infty, x])\right) \\
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) \in (-\infty, x]\right\}\right) \\
&= \mathbb{P}\left(x \leq X\right) \\
\end{split}
$$

__________________

### distribution
- given a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$ and a [[random variable]] $X: \Omega \to \mathbb{R}$ (which is a [[measurable function]] $X: (\Omega, \mathcal{A}) \to \left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$)
- $X$ is inducing the [[probability measure]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ from the [[borel sigma algebra]] $\mathcal{B}(\mathbb{R})$ it the interval $[0,1]$ (assigning a probability to each borel set $\subset \mathbb{R}$)
- $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ is called the [[distribution]] of $X$ and exists for every [[random variable]] 
$$
\begin{split}
\mathcal{P}_X(C) 
&= \mathbb{P}\left(X^{-1}(C \subseteq \mathbb{R})\right) \\
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) \in C\right\}\right) \\
\end{split}
$$


### a [[random variable]] induces a [[probability measure]]
- given a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$ and a [[measurable function]] $X: (\Omega, \mathcal{A}) \to (\mathbb{R}, \mathcal{B})$ we can define a [[probability measure]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ 

$$
\begin{split}
\mathcal{P}_X(C \subseteq \mathbb{R}) 
&= \mathbb{P}\left(X^{-1}(C) \subseteq \Omega\right) \\
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) \in C\right\}\right) \\
\end{split}
$$


### probability measure
- given a [[measurable space]] $(\Omega, \mathcal{A})$ of a [[set]] $\Omega$ equiped with a [[sigma algebra]] $\mathcal{A}$ a [[function]] $P: \mathcal{A} \mapsto [0,1]$ is a [[probability measure]]
$$
P: \mathcal{A} \mapsto [0,1]
$$

- the probability of the [[empty set]] is zero
$$
\begin{split}
P(\emptyset) = 0 \\
\end{split}
$$

- the [[probability]] of the [[sample space]] is one
$$
\begin{split}
P(\Omega) = 1 \\
\end{split}
$$
- given a [[countable]] collection of [[disjoint]] events $(A_n)_{n \in \mathbb{N}}$ 
$$
\begin{split}
P\left(\bigcup_{i \in \mathbb{N}} A_i \right) = \sum_{i \in \mathbb{N}} P(A_i) \\
\end{split}
$$
#### derived properties
- propability of the [[complement]]
$$
\begin{split}
P\left(A^c\right) 
&= 1 - P(A) \\
\end{split}
$$

- probability of the [[union]]
$$
\begin{split}
P\left(A \cup B\right) 
&= P(A) + P(B) - P\left(A \cup B\right)  \\
\end{split}
$$


### random variable
- given a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$
- a [[function]] $X: \Omega \to \mathbb{R}$ from the [[sample space]] $\Omega$ to the [[real numbers]] $\mathbb{R}$ is a [[random variable]] if it's a [[measurable function]] $X: (\Omega, \mathcal{A}) \to \left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$ from the [[measurable space]] of $(\Omega, \mathcal{A})$ to the [[real numbers]] with the [[borel sigma algebra]] (which are a [[measurable space]] too)
- this is the case exactly when the following is true (given the [[inverse function]] $X^{-1}: \mathbb{R} \to \Omega$)
$$
\forall x \in \mathbb{R}: X^{-1}\left((-\infty, x]\right) = \{\omega \in \Omega: X(\omega) \in (-\infty, x]\} \in \mathcal{A}
$$


Tags: mathematics statistics
<!--ID: 1664619948163-->
END




START
Basic
proof the following property of the [[cumulative distribution function (CDF)]]

$$F(x + y) = F(x) + \mathcal{P}((x, x+y])$$
Back: 

### $F(x + y) = F(x) + \mathcal{P}((x, x+y])$
- it followns directry from the properties of [[probability measure]] and the fact that $F(x) = \mathcal{P}((\infty, x])$ has [[probability measure]] on $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$ 


$$
\begin{split}
\mathcal{P}((-\infty, x+y])  
= \mathcal{P}((-\infty, x] \cup(x, x+y]) \\
= \mathcal{P}((-\infty, x]) + \mathcal{P}((x, x+y]) \\
\end{split}
$$

### [[cumulative distribution function (CDF)|CDFs]] and [[probability measure|probability measures]] induce each other
- for each [[cumulative distribution function (CDF)]] $F: \mathbb{R} \to [0,1]$ there exists a [[probability measure]] $\mathcal{P}:\mathcal{B}(\mathbb{R}) \to [0,1]$ and vise versa
$$
\begin{split}
F_X(x) &= \mathcal{P}_X((-\infty, x]) \\ 
\mathcal{P}((a, b]) &= F(b) - F(a) \\ 
\end{split}
$$
#### proof
- fist we need to show that $F(x) = \mathcal{P}_X((-\infty, x])$ is a [[cumulative distribution function (CDF)]]
$$
\lim_{x \to -\infty} \mathcal{P}_X((-\infty, x]) = \mathcal{P}_X(\emptyset) = 0
$$
$$
\lim_{x \to \infty} \mathcal{P}_X((-\infty, x]) = \mathcal{P}_X(\mathbb{R}) = 1
$$
- $F(x) = \mathcal{P}_X((-\infty, x])$ is monotone increasing
$$
\begin{split}
&x \leq y \\
\Rightarrow &\left\{\omega \in \Omega: X(\omega) \in (-\infty, x]\right\} \subseteq \left\{\omega \in \Omega: X(\omega) \in (-\infty, y]\right\}  \\


\Rightarrow& \mathbb{P}\left(X^{-1}\left((-\infty, y]\right)\right) =\mathbb{P}\left(X^{-1}\left((-\infty, x]\right)\right) + 
 \mathbb{P}\left(X^{-1}\left((x, y]\right)\right)\\
\Rightarrow& \mathbb{P}\left(X^{-1}\left((-\infty, x]\right)\right) \leq\mathbb{P}\left(X^{-1}\left((-\infty, y]\right)\right) 
\end{split}
$$



### probability measure
- given a [[measurable space]] $(\Omega, \mathcal{A})$ of a [[set]] $\Omega$ equiped with a [[sigma algebra]] $\mathcal{A}$ a [[function]] $P: \mathcal{A} \mapsto [0,1]$ is a [[probability measure]]
$$
P: \mathcal{A} \mapsto [0,1]
$$

- the probability of the [[empty set]] is zero
$$
\begin{split}
P(\emptyset) = 0 \\
\end{split}
$$

- the [[probability]] of the [[sample space]] is one
$$
\begin{split}
P(\Omega) = 1 \\
\end{split}
$$
- given a [[countable]] collection of [[disjunct]] events $(A_n)_{n \in \mathbb{N}}$ 
$$
\begin{split}
P\left(\bigcup_{i \in \mathbb{N}} A_i \right) = \sum_{i \in \mathbb{N}} P(A_i) \\
\end{split}
$$
#### derived properties
- propability of the [[complement]]
$$
\begin{split}
P\left(A^c\right) 
&= 1 - P(A) \\
\end{split}
$$

- probability of the [[union]]
$$
\begin{split}
P\left(A \cup B\right) 
&= P(A) + P(B) - P\left(A \cup B\right)  \\
\end{split}
$$
________________________

### cumulative distribution function (CDF)
- a [[function]] $F: \mathbb{R} \to [0,1]$ is a [[cumulative distribution function (CDF)]] if
1)  $F$ is [[monotonic function|monote increasing]] [[function]] 
2) $\lim_{x \to - \infty} F(x) = 0$
3) $\lim_{x \to \infty} F(x) = 1$

Tags: mathematics statistics
<!--ID: 1716803446392-->
END























START
Basic
Cumulative Distribution Function (CDF)
- how to estimate if from a sample
Back: 
empirical CDF: approximated CDF from [[statistical sample|samples]] 
$\widehat{F}_X(x)=\frac{1}{n} \sum\limits_{i=1}^n\mathbb{I}[x_i \leq x]$ 
Tags: mathematics statistics
<!--ID: 1664619948167-->
END

START
Basic
 Relationship CDF $F_X(q)$ and [[quantile function]] $Q_X(q)$
Back: 

- $Q_X(q)$ is the smallest values with a [[cumulative distribution function (CDF)]] less or equal than $q$  
$$Q_X(q) = \inf\left\{x \mid q \leq F_X(x)\right\}$$
- $Q_X(q)$ is the inverse of the [[cumulative distribution function (CDF)]]
$$Q_X(q)=F_X^{-1}(q)\quad with \: q = F_X(x)=P(X \leq x)$$

Tags: mathematics statistics
<!--ID: 1664619948170-->
END


START
Basic
- Definition of $F_X(x^+)$ and $F_X(x^-)$
- continuity of ([[discrete distribution|discrete]] and [[continuous random variable|continuous]]) [[cumulative distribution function (CDF)]]
- $P(X<x)$ and $P(X=x)$ in relationship to the limits of the [[cumulative distribution function (CDF)]]
Back: 
## limits
$$
F_X(x^-) = \lim_{y \rightarrow x, y < x} F_X(y)
$$
$$
F_X(x^+) = \lim_{y \rightarrow x, y > x} F_X(y)
$$
#### Properties
1) $P(X \leq x)=F_X(x)$
2) $P(X=x) = F_X(x) - F_X(x^+)$
3) $P(X<x)=F_X(x^-)$
4) $F_X(x)=F_X(x^+)$ continuity from the right ([[discrete distribution|discrete]] and [[continuous random variable|continuous]])
5) $F_X(x)=F_X(x^+)=F_X(x^-)$ continuity from the both sides ([[continuous random variable|continuous]])
	- proof: its because $f_X(x)=0$
Tags: mathematics statistics
<!--ID: 1668957370731-->
END