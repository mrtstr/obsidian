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
- $F_X(x) = \mathcal{P}_X((-\infty, x])$
- 
### every [[random variable]] has a [[cumulative distribution function (CDF)|CDF]]
- thus every [[random variable]] $X: \Omega \to \mathbb{R}$ in a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$ has a [[cumulative distribution function (CDF)]] $F_X$ because $X$ induces a [[probability measure]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ of the [[measurable space]] $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$ (the [[distribution]])
- since every [[random variable]] $X: \Omega \to \mathbb{R}$ has a [[distribution]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ every $X$ has also a [[cumulative distribution function (CDF)]] $F_X$

$$
\begin{split}
F_X(x) 
&= \mathcal{P}_X((-\infty, x]) \\ 
&= \mathbb{P}\left(X^{-1}((-\infty, x])\right) \\
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) \in (-\infty, x]\right\}\right) \\
&= \mathbb{P}\left(X \leq X\right) \\
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
why does every [[random variable]] have a [[cumulative distribution function (CDF)]]
Back: 
- a [[random variable]] induces a [[probability measure]] and every [[probability measure]] has a [[cumulative distribution function (CDF)]]

### cumulative distribution function (CDF)
- a [[function]] $F: \mathbb{R} \to [0,1]$ is a [[cumulative distribution function (CDF)]] if
1)  $F$ is [[monotonic function|monote increasing]] [[function]] 
2) $\lim_{x \to - \infty} F(x) = 0$
3) $\lim_{x \to \infty} F(x) = 1$

- for each [[cumulative distribution function (CDF)]] $F: \mathbb{R} \to [0,1]$ there exists a [[probability measure]] $\mathcal{P}:\mathcal{B}(\mathbb{R}) \to [0,1]$ and vise versa
$$
\begin{split}
F_X(x) &= \mathcal{P}_X((-\infty, x]) \\ 
\mathcal{P}((a, b]) &= F(b) - F(a) \\ 
\end{split}
$$
- thus every [[random variable]] $X: \Omega \to \mathbb{R}$ in a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$ has a [[cumulative distribution function (CDF)]] $F_X$ because $X$ induces a [[probability measure]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ of the [[measurable space]] $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$ (the [[distribution]])
- since every [[random variable]] $X: \Omega \to \mathbb{R}$ has a [[distribution]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ every $X$ has also a [[cumulative distribution function (CDF)]] $F_X$

$$
\begin{split}
F_X(x) 
&= \mathcal{P}_X((-\infty, x]) \\ 
&= \mathbb{P}\left(X^{-1}((-\infty, x])\right) \\
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) \in (-\infty, x]\right\}\right) \\
&= \mathbb{P}\left(X \leq X\right) \\
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
- relationship to [[probability measure]]
- relationship to random variables
Back: 
### cumulative distribution function (CDF)
- a [[function]] $F: \mathbb{R} \to [0,1]$ is a [[cumulative distribution function (CDF)]] if
1)  $F$ is [[monotonic function|monote increasing]] [[function]] 
2) $\lim_{x \to - \infty} F(x) = 0$
3) $\lim_{x \to \infty} F(x) = 1$

- for each [[cumulative distribution function (CDF)]] $F: \mathbb{R} \to [0,1]$ there exists a [[probability measure]] $\mathcal{P}:\mathcal{B}(\mathbb{R}) \to [0,1]$ and vise versa
$$
\begin{split}
F_X(x) &= \mathcal{P}_X((-\infty, x]) \\ 
\mathcal{P}((a, b]) &= F(b) - F(a) \\ 
\end{split}
$$
- thus every [[random variable]] $X: \Omega \to \mathbb{R}$ in a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$ has a [[cumulative distribution function (CDF)]] $F_X$ because $X$ induces a [[probability measure]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ of the [[measurable space]] $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$ (the [[distribution]])
- since every [[random variable]] $X: \Omega \to \mathbb{R}$ has a [[distribution]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ every $X$ has also a [[cumulative distribution function (CDF)]] $F_X$

$$
\begin{split}
F_X(x) 
&= \mathcal{P}_X((-\infty, x]) \\ 
&= \mathbb{P}\left(X^{-1}((-\infty, x])\right) \\
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) \in (-\infty, x]\right\}\right) \\
&= \mathbb{P}\left(X \leq X\right) \\
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
<!--ID: 1664619948163-->
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