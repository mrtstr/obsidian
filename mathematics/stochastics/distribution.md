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

### relationship to other conecpts
- the [[distribution]] of a [[random variable]] of a theoretical construct
- in practice functions that are specifing the [[distribution]] are used instead
	→  [[cumulative distribution function (CDF)]], [[probability mass function (PMF)]] [[probability density function (PDF)]]

- every [[random variable]] $X: \Omega \to \mathbb{R}$ in a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$ has a [[distribution]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ 

$$
\begin{split}
\mathcal{P}_X(C)= \mathbb{P}\left(X^{-1}(C )\right) \\
 \\
\end{split}
$$
- every [[distribution]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ (and thus every [[random variable]]) has a [[cumulative distribution function (CDF)]] 

$$
F_X(x) = \mathcal{P}_X((-\infty, x])
$$
- every [[random variable]] in a [[discrete probability space]] has a [[probability mass function (PMF)]]

$$
\begin{split}
f_X(x) = \mathcal{P}_X(\{x\}) \\
\end{split}
$$
- some but not all [[random variable]] in a [[continuous probability space]] have a [[probability density function (PDF)]] because eventhough they might have a [[cumulative distribution function (CDF)]] it is not allways [[differentiable]]

$$
f_X(x) = \frac{dF_X(x)}{dx}
$$

# -----------------

![[random variable#a random variable induces a probability measure]]

![[random variable#random variable]]


# anki




START
Basic
[[distribution]] of a [[random variable]]
- definition
- relationship to the conecpt [[probability measure]]

Back: 
### distribution
- given a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$ and a [[random variable]] $X: \Omega \to \mathbb{R}$ (which is a  [[measurable function]] $X: (\Omega, \mathcal{A}) \to \left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$)
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
- thus $X^{-1}(A)$ and $X^{-1}(B)$ have to be [[mathematics/basics/disjoint]]

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
____________________________

### random variable
- given a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$
- a [[function]] $X: \Omega \to \mathbb{R}$ from the [[sample space]] $\Omega$ to the [[real numbers]] $\mathbb{R}$ is a [[random variable]] if it's a [[measurable function]] $X: (\Omega, \mathcal{A}) \to \left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$ 

$$
\forall C \in \mathbb{R}: X^{-1}(C) = \{\omega \in \Omega : X(\omega) \in C\} \in \mathcal{A}
$$

- this is the case exactly when the following is true (given the [[inverse function]] $X^{-1}: \mathbb{R} \to \Omega$)
$$
\forall x \in \mathbb{R}: X^{-1}\left((-\infty, x]\right) = \{\omega \in \Omega: X(\omega) \in (-\infty, x]\} \in \mathcal{A}
$$
TODO add proof

### measurable function
- given two [[measurable space|measurable spaces]] $\left(A, \mathcal{A}\right)$ and $\left(B, \mathcal{B}\right)$ with the [[set|sets]] $A$ and $B$ and their [[sigma algebra|sigma algebra]]
- the [[function]] $f: A\to B$ is a [[measurable function]] if every [[set]] in the [[sigma algebra]] of its codomain $\mathcal{B}$ can be mapped to a [[set]] in the domain [[sigma algebra]] $\mathcal{A}$ by the [[inverse function]] $f^{-1}:B \to A$
$$
\forall E \in \mathcal{B}: f^{-1}(E) = \{x \in A : f(x) \in E\} \in \mathcal{A}
$$
- notation for a [[measurable function]] $f: \left(A, \mathcal{A}\right) \to \left(B, \mathcal{B}\right)$

### borel sigma algebra
- the [[borel sigma algebra]] $\mathcal{B}(\mathbb{R})$ is a [[sigma algebra]] on the [[real numbers]] 
- thus $\left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$ are a [[measurable space]] 
- $\mathcal{B}(\mathbb{R}) \subset \mathcal{P}(\mathbb{R})$ does contain all substs of $\mathbb{R}$ for which need a probability assigned to it


### measurable space
- a [[measurable space]] $\left(\Omega,\mathcal{A} = \sigma(\Omega)\right)$ is a [[set]] $\Omega$ equiped with a [[sigma algebra]] $\mathcal{A}$
- every [[probability space]] is by definition a [[measurable space]]

### $\sigma$ algebra
- given a [[set]] $\Omega$ a $\sigma$-algebra $\mathcal{A}=\sigma(\Omega)$ is a system of subsets of $\Omega$ with the following 3 base properties
- used to describe the properties of an [[event space]] of a [[probability space]]

1) the base [[set]] $\Omega$ is in its $\sigma$-algebra

$$
\begin{split}
&\Omega \in \mathcal{A} \\
\end{split}
$$
2) [[empty set]] is in  $\sigma$-algebra

$$
\begin{split}
&\emptyset \in \mathcal{A} \\
\end{split}
$$
3) $\mathcal{A}$ is [[closure|closed]] over the [[complement]]

$$
\begin{split}
&A \in \mathcal{A} \Rightarrow A^c \in \mathcal{A} \\
\end{split}
$$

4) $\mathcal{A}$ is [[closure|closed]] over the [[union]]

$$
\begin{split}
&A_1, ..., A_n \in \mathcal{A} \Rightarrow \bigcup_{i \in [n]} A_i \in \mathcal{A} \\
\end{split}
$$
- a [[sigma algebra]] is [[closure|closed]] over [[intersection]]
$$
A, B \in \mathcal{A} \Rightarrow A \cap B \in \mathcal{A}
$$

- a [[sigma algebra]] is [[closure|closed]] over [[difference of sets]]
$$
A, B \in \mathcal{A} \Rightarrow A \setminus B \in \mathcal{A}
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
proof
$$
\begin{split}
P\left(A \cup A^c\right) 
&= 1 \\ 
&= P\left(A\right) + P\left(A^c\right) \\
\Rightarrow P\left(A^c\right) &= 1 - P(A) \\
\end{split}
$$

- probability of the [[union]]
$$
\begin{split}
P\left(A \cup B\right) 
&= P(A) + P(B) - P\left(A \cup B\right)  \\
\end{split}
$$
proof

$$
\begin{split}
P\left(A \cup B\right) 
&= \left(A \cup (A^c \cap B)\right)  \\
&= P(A) + \left(A^c \cap B\right)  \\
&= P(A) + P(B) - P\left(A \cup B\right) \\

P\left(A^c \cap B\right) + P\left(A \cap B\right) 
&= P\left(\left(A^c \cap B\right) \cup \left(A \cap B\right)\right)  \\
&= P\left(B\right)  \\
&= P(A) + P(B) - P\left(A \cup B\right)  \\
\Rightarrow P\left(A^c \cap B\right) &=  P(B) - P\left(A \cup B\right)  \\
\end{split}
$$


### probability space
- a [[probability space]] $(\Omega, \mathcal{A}, P)$ is a formal model for a [[random process]]
- if a [[measurable space]] $\left(\Omega, \mathcal{A}=\sigma(\Omega)\right)$ is equiped with a [[probability measure]] $P$ it is a [[probability space]]

#### [[sample space]] $\Omega$
- the nonempty [[set]] $\Omega$ is the [[sample space]] of a [[random experiment]] of it contains all posible outcomes
- the elements of the [[sample space]] are called outcomes $\omega \in \Omega$  
- e.g. for a die throw $\Omega = \left\{1,2,3,4,5,6\right\}$
- can be [[countable]] (in a discrete [[probability space]]) or [[countable|noncountable]] (in a continuous [[probability space]])

#### [[event space]] $\mathcal{A}=\sigma(\Omega)$ 
- [[sigma algebra]] on the [[sample space]]
- an [[event]] is a [[set]] of outcomes $\omega \in \Omega$  
- the [[event space]] is a [[set]] of all possible [[event|envents]] and thus contains subsets of the [[sample space]] $\Omega$ and thus is a subset of the [[power set]] of $\Omega$
$$\mathcal{A} \subseteq \mathcal{P}(\Omega) = \{A \mid A \subseteq \Omega \}$$

- e.g. for a die throw: a [[set]] of numbers between 1 and 6

#### [[probability measure]] $P$
- a [[probability measure]] on the [[measurable space]] $(\Omega, \mathcal{A})$ that assignes a [[probability]] to each event $P: \mathcal{A} \to [0,1]$
- e.g. for a die throw: $P\left(\left\{2,4,6\right\}\right) = \frac{1}{2}$ 

Tags: mathematics statistics
<!--ID: 1716733308279-->
END



START
Basic
relationship of the following concepts
- [[probability space]]
- [[random variable]]
- [[distribution]]
- [[cumulative distribution function (CDF)]]
- [[probability mass function (PMF)]]
- [[probability density function (PDF)]]

does every [[random variable]] have a ...?
- [[distribution]]
- [[cumulative distribution function (CDF)]]
- [[probability mass function (PMF)]]
- [[probability density function (PDF)]]

Back: 
### relationship to other conecpts
- the [[distribution]] of a [[random variable]] of a theoretical construct
- in practice functions that are specifing the [[distribution]] are used instead
	→  [[cumulative distribution function (CDF)]],  [[probability mass function (PMF)]] [[probability density function (PDF)]]

- every [[random variable]] $X: \Omega \to \mathbb{R}$ in a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$ has a [[distribution]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ 

$$
\begin{split}
\mathcal{P}_X(C)= \mathbb{P}\left(X^{-1}(C )\right) \\
 \\
\end{split}
$$
- every [[distribution]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ (and thus every [[random variable]]) has a [[cumulative distribution function (CDF)]] 

$$
F_X(x) = \mathcal{P}_X((-\infty, x])
$$
- every [[random variable]] in a [[discrete probability space]] has a [[probability mass function (PMF)]]

$$
\begin{split}
f_X(x) = \mathcal{P}_X(\{x\}) \\
\end{split}
$$
- some but not all [[random variable]] in a [[continuous probability space]] have a [[probability density function (PDF)]] because eventhough they might have a [[cumulative distribution function (CDF)]] it is not allways [[differentiable]]

$$
f_X(x) = \frac{dF_X(x)}{dx}
$$

____________________________

### distribution
- given a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$ and a [[random variable]] $X: \Omega \to \mathbb{R}$ (which is a  [[measurable function]] $X: (\Omega, \mathcal{A}) \to \left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$)
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

- given two [[mathematics/basics/disjoint]] subsets of the [[real numbers]] $A, B \subseteq \mathbb{R}$
- fist we need to show that the image (of $X^{-1}$) of two [[mathematics/basics/disjoint]] [[set|sets]] is still [[mathematics/basics/disjoint]] 
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
- thus $X^{-1}(A)$ and $X^{-1}(B)$ have to be [[mathematics/basics/disjoint]]

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

### random variable
- given a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$
- a [[function]] $X: \Omega \to \mathbb{R}$ from the [[sample space]] $\Omega$ to the [[real numbers]] $\mathbb{R}$ is a [[random variable]] if it's a [[measurable function]] $X: (\Omega, \mathcal{A}) \to \left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$ 

$$
\forall C \in \mathbb{R}: X^{-1}(C) = \{\omega \in \Omega : X(\omega) \in C\} \in \mathcal{A}
$$

- this is the case exactly when the following is true (given the [[inverse function]] $X^{-1}: \mathbb{R} \to \Omega$)
$$
\forall x \in \mathbb{R}: X^{-1}\left((-\infty, x]\right) = \{\omega \in \Omega: X(\omega) \in (-\infty, x]\} \in \mathcal{A}
$$
TODO add proof

### measurable function
- given two [[measurable space|measurable spaces]] $\left(A, \mathcal{A}\right)$ and $\left(B, \mathcal{B}\right)$ with the [[set|sets]] $A$ and $B$ and their [[sigma algebra|sigma algebra]]
- the [[function]] $f: A\to B$ is a [[measurable function]] if every [[set]] in the [[sigma algebra]] of its codomain $\mathcal{B}$ can be mapped to a [[set]] in the domain [[sigma algebra]] $\mathcal{A}$ by the [[inverse function]] $f^{-1}:B \to A$
$$
\forall E \in \mathcal{B}: f^{-1}(E) = \{x \in A : f(x) \in E\} \in \mathcal{A}
$$
- notation for a [[measurable function]] $f: \left(A, \mathcal{A}\right) \to \left(B, \mathcal{B}\right)$

### measurable space
- a [[measurable space]] $\left(\Omega,\mathcal{A} = \sigma(\Omega)\right)$ is a [[set]] $\Omega$ equiped with a [[sigma algebra]] $\mathcal{A}$
- every [[probability space]] is by definition a [[measurable space]]

### $\sigma$ algebra
- given a [[set]] $\Omega$ a $\sigma$-algebra $\mathcal{A}=\sigma(\Omega)$ is a system of subsets of $\Omega$ with the following 3 base properties
- used to describe the properties of an [[event space]] of a [[probability space]]

1) the base [[set]] $\Omega$ is in its $\sigma$-algebra

$$
\begin{split}
&\Omega \in \mathcal{A} \\
\end{split}
$$
2) [[empty set]] is in  $\sigma$-algebra

$$
\begin{split}
&\emptyset \in \mathcal{A} \\
\end{split}
$$
3) $\mathcal{A}$ is [[closure|closed]] over the [[complement]]

$$
\begin{split}
&A \in \mathcal{A} \Rightarrow A^c \in \mathcal{A} \\
\end{split}
$$

4) $\mathcal{A}$ is [[closure|closed]] over the [[union]]

$$
\begin{split}
&A_1, ..., A_n \in \mathcal{A} \Rightarrow \bigcup_{i \in [n]} A_i \in \mathcal{A} \\
\end{split}
$$
- a [[sigma algebra]] is [[closure|closed]] over [[intersection]]
$$
A, B \in \mathcal{A} \Rightarrow A \cap B \in \mathcal{A}
$$

- a [[sigma algebra]] is [[closure|closed]] over [[difference of sets]]
$$
A, B \in \mathcal{A} \Rightarrow A \setminus B \in \mathcal{A}
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
- given a [[countable]] collection of [[mathematics/basics/disjoint]] events $(A_n)_{n \in \mathbb{N}}$ 
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
proof
$$
\begin{split}
P\left(A \cup A^c\right) 
&= 1 \\ 
&= P\left(A\right) + P\left(A^c\right) \\
\Rightarrow P\left(A^c\right) &= 1 - P(A) \\
\end{split}
$$

- probability of the [[union]]
$$
\begin{split}
P\left(A \cup B\right) 
&= P(A) + P(B) - P\left(A \cup B\right)  \\
\end{split}
$$
proof

$$
\begin{split}
P\left(A \cup B\right) 
&= \left(A \cup (A^c \cap B)\right)  \\
&= P(A) + \left(A^c \cap B\right)  \\
&= P(A) + P(B) - P\left(A \cup B\right) \\

P\left(A^c \cap B\right) + P\left(A \cap B\right) 
&= P\left(\left(A^c \cap B\right) \cup \left(A \cap B\right)\right)  \\
&= P\left(B\right)  \\
&= P(A) + P(B) - P\left(A \cup B\right)  \\
\Rightarrow P\left(A^c \cap B\right) &=  P(B) - P\left(A \cup B\right)  \\
\end{split}
$$



Tags: mathematics statistics
<!--ID: 1716795478780-->
END