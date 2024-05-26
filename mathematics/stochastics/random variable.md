### random variable
- given a [[probability space]] $\left(\Omega, \mathcal{A} , P\right)$
- a [[function]] $X: \Omega \to \mathbb{R}$ from the [[sample space]] $\Omega$ to the [[real numbers]] $\mathbb{R}$ is a [[random variable]] if it's a [[measurable function]] $X: (\Omega, \mathcal{A}) \to (\mathbb{R}, \mathcal{B})$
- this is the case exactly when the following is true (given the [[inverse function]] $X^{-1}: \mathbb{R} \to \Omega$)
$$
\forall x \in \mathbb{R}: X^{-1}\left((-\infty, x]\right) = \{\omega \in \Omega: X(\omega) \in (-\infty, x]\} \in \mathcal{A}
$$

#### proof
- to show that the given condition is sufficient to show that $X$ is a [[measurable function]] we will prove the following
$$
\begin{split}
\forall x \in \mathbb{R}: &X^{-1}\left((-\infty, x]\right)  \in \mathcal{A} \\
&\Rightarrow \\
\forall x < y \in \mathbb{R}: &X^{-1}\left([y, x]\right)  \in \mathcal{A} \\
&\Rightarrow \\
\forall E \subseteq \mathbb{R}: &X^{-1}\left(E\right)  \in \mathcal{A}
\end{split}
$$
- first part
$$
\begin{split}
&\forall x \in \mathbb{R} \forall \epsilon > 0 \in \mathbb{R}: X^{-1}\left((-\infty, x]\right)  \in \mathcal{A} \land X^{-1}\left((-\infty, x + \epsilon]\right)  \in \mathcal{A} \\
&\Rightarrow X^{-1}\left((-\infty, y]\right) \setminus X^{-1}\left((-\infty, x]\right)  \in \mathcal{A} \qquad \text{(a sigma algbra is closed over difference)} \\
&\Rightarrow\forall x < y \in \mathbb{R}:  X^{-1}\left([x, y]\right)   \in \mathcal{A} \\
\end{split}
$$
- the second part can be proved because a [[sigma algebra]] is closed over [[union]]

### a [[random variable]] induces a [[probability measure]]
- given a [[probability space]] $\left(\Omega, \mathcal{A} , P\right)$ and a [[measurable function]] $X: (\Omega, \mathcal{A}) \to (\mathbb{R}, \mathcal{B})$ we can define a [[probability measure]] $\mathcal{P}_X: \mathcal{B} \to [0,1]$ 

$$
\mathcal{P}_X(E \subseteq \mathbb{R}) 
= P\left(X^{-1}(E) \subseteq \Omega\right) = P\left(\left\{\omega \in \Omega : X(\omega) \in C\right\}\right)
$$
- in a [[continuous probability space]] this [[probability measure]] is called [[probability density function (PDF)]]
- in a [[discrete probability space]] this [[probability measure]] is called [[probability mass function (PMF)]]

#### proof
- the first proberties of a [[probability measure]] is trivial
$$
\begin{split}
\mathcal{P}_X(\emptyset \subseteq \mathbb{R}) 
&= P\left(\left\{\omega \in \Omega : X(\omega) \in \emptyset \right\}\right) \\
&=  P\left( \emptyset \right) 
= 0
\end{split}
$$
- since $X: \Omega \to \mathbb{R}$ is a [[function]] all elements of the [[sample space]] $\Omega$ have to be mapped to a [[real numbers|real number]] and $P\left( \Omega \right) = 1$ is given by the definition of a [[probability function]]
$$
\begin{split}
\mathcal{P}_X(\mathbb{R}) 
&= P\left(\left\{\omega \in \Omega : X(\omega) \in \mathbb{R}\right\}\right) \\
&=  P\left( \Omega \right) 
= 1
\end{split}
$$

- given two [[disjunct]] subsets of the [[real numbers]] $A, B \subseteq \mathbb{R}$
$$
\begin{split}
\mathcal{P}_X(A \cup B) 
&= P\left(\left\{\omega \in \Omega : X(\omega) \in A \cup B \right\}\right) \\
&= P\left(\left\{\omega \in \Omega : X(\omega) \in A  \right\} \cup \left\{\omega \in \Omega : X(\omega) \in  B \right\}\right) \\
&= P\left(\left\{\omega \in \Omega : X(\omega) \in A  \right\}\right) + P\left(\left\{\omega \in \Omega : X(\omega) \in  B \right\}\right) \\
&= \mathcal{P}_X(A) + \mathcal{P}_X(B) \\
\end{split}
$$

# --------------------------
![[measurable function#measurable function]]

![[measurable space#measurable space]]

![[sigma algebra#$ sigma$ algebra]]

![[probability measure#probability measure]]

![[probability space#probability space]]

# anki


START
Basic
[[random variable]]
- definition and definition for concept where its based on

Back: 
### random variable
- given a [[probability space]] $\left(\Omega, \mathcal{A} , P\right)$
- a [[function]] $X: \Omega \to \mathbb{R}$ from the [[sample space]] $\Omega$ to the [[real numbers]] $\mathbb{R}$ is a [[random variable]] if it's a [[measurable function]] $X: (\Omega, \mathcal{A}) \to (\mathbb{R}, \mathcal{B})$
- this is the case exactly when the following is true
$$
\forall x \in \mathbb{R}: X^{-1}\left((-\infty, x]\right) = \{\omega \in \Omega: X(\omega) \in (-\infty, x]\} \in \mathcal{A}
$$

#### proof
- to show that the given condition is sufficient to show that $X$ is a [[measurable function]] we will prove the following
$$
\begin{split}
\forall x \in \mathbb{R}: &X^{-1}\left((-\infty, x]\right)  \in \mathcal{A} \\
&\Rightarrow \\
\forall x < y \in \mathbb{R}: &X^{-1}\left([y, x]\right)  \in \mathcal{A} \\
&\Rightarrow \\
\forall E \subseteq \mathbb{R}: &X^{-1}\left(E\right)  \in \mathcal{A}
\end{split}
$$
- first part
$$
\begin{split}
&\forall x \in \mathbb{R} \forall \epsilon > 0 \in \mathbb{R}: X^{-1}\left((-\infty, x]\right)  \in \mathcal{A} \land X^{-1}\left((-\infty, x + \epsilon]\right)  \in \mathcal{A} \\
&\Rightarrow X^{-1}\left((-\infty, y]\right) \setminus X^{-1}\left((-\infty, x]\right)  \in \mathcal{A} \qquad \text{(a sigma algbra is closed over difference)} \\
&\Rightarrow\forall x < y \in \mathbb{R}:  X^{-1}\left([x, y]\right)   \in \mathcal{A} \\
\end{split}
$$
- the second part can be proved because a [[sigma algebra]] is closed over [[union]]

### measurable function
- given two [[measurable space|measurable spaces]] $\left(A, \sigma_A\right)$ and $\left(B, \sigma_B\right)$ with the [[set|sets]] $A$ and $B$ and their [[sigma algebra|sigma algebra]]
- the [[function]] $f: A\to B$ is a [[measurable function]] if every [[set]] in the [[sigma algebra]] of its codomain $\sigma_B$ can be mapped to a [[set]] in the domain [[sigma algebra]] $\sigma_B$ by the [[inverse function]] $f^{-1}$
$$
\forall E \in \sigma_B: f^{-1}(E) = \{x \in A : f(x) \in E\} \in \sigma_A
$$
- notation for a [[measurable function]] $f: \left(X, \sigma_X\right) \to \left(Y, \sigma_Y\right)$


____________________________

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
2) $\mathcal{A}$ is [[closure|closed]] over the [[complement]]

$$
\begin{split}
&A \in \mathcal{A} \Rightarrow A^c \in \mathcal{A} \\
\end{split}
$$

3) $\mathcal{A}$ is [[closure|closed]] over the [[union]]

$$
\begin{split}
&A_1, ..., A_n \in \mathcal{A} \Rightarrow \bigcup_{i \in [n]} A_i \in \mathcal{A} \\
\end{split}
$$
#### a [[sigma algebra]] is [[closure|closed]] over [[intersection]]
$$
A, B \in \mathcal{A} \Rightarrow A \cap B \in \mathcal{A}
$$

#### a [[sigma algebra]] is [[closure|closed]] over [[difference of sets]]
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
<!--ID: 1667211139251-->
END



START
Basic
- proof that a [[function]] $X: \Omega \to \mathbb{R}$ from the [[sample space]] $\Omega$ to the [[real numbers]] $\mathbb{R}$ that satisfies the following condition is a [[measurable function]]

$$
\forall x \in \mathbb{R}: X^{-1}\left((-\infty, x]\right) = \{\omega \in \Omega: X(\omega) \in (-\infty, x]\} \in \mathcal{A}
$$

Back: 
### random variable
- given a [[probability space]] $\left(\Omega, \mathcal{A} , P\right)$
- a [[function]] $X: \Omega \to \mathbb{R}$ from the [[sample space]] $\Omega$ to the [[real numbers]] $\mathbb{R}$ is a [[random variable]] if it's a [[measurable function]] $X: (\Omega, \mathcal{A}) \to (\mathbb{R}, \mathcal{B})$
- this is the case exactly when the following is true
$$
\forall x \in \mathbb{R}: X^{-1}\left((-\infty, x]\right) = \{\omega \in \Omega: X(\omega) \in (-\infty, x]\} \in \mathcal{A}
$$

#### proof
- to show that the given condition is sufficient to show that $X$ is a [[measurable function]] we will prove the following
$$
\begin{split}
\forall x \in \mathbb{R}: &X^{-1}\left((-\infty, x]\right)  \in \mathcal{A} \\
&\Rightarrow \\
\forall x < y \in \mathbb{R}: &X^{-1}\left([y, x]\right)  \in \mathcal{A} \\
&\Rightarrow \\
\forall E \subseteq \mathbb{R}: &X^{-1}\left(E\right)  \in \mathcal{A}
\end{split}
$$
- first part
$$
\begin{split}
&\forall x \in \mathbb{R} \forall \epsilon > 0 \in \mathbb{R}: X^{-1}\left((-\infty, x]\right)  \in \mathcal{A} \land X^{-1}\left((-\infty, x + \epsilon]\right)  \in \mathcal{A} \\
&\Rightarrow X^{-1}\left((-\infty, y]\right) \setminus X^{-1}\left((-\infty, x]\right)  \in \mathcal{A} \qquad \text{(a sigma algbra is closed over difference)} \\
&\Rightarrow\forall x < y \in \mathbb{R}:  X^{-1}\left([x, y]\right)   \in \mathcal{A} \\
\end{split}
$$
- the second part can be proved because a [[sigma algebra]] is closed over [[union]]

### measurable function
- given two [[measurable space|measurable spaces]] $\left(A, \sigma_A\right)$ and $\left(B, \sigma_B\right)$ with the [[set|sets]] $A$ and $B$ and their [[sigma algebra|sigma algebra]]
- the [[function]] $f: A\to B$ is a [[measurable function]] if every [[set]] in the [[sigma algebra]] of its codomain $\sigma_B$ can be mapped to a [[set]] in the domain [[sigma algebra]] $\sigma_B$ by the [[inverse function]] $f^{-1}$
$$
\forall E \in \sigma_B: f^{-1}(E) = \{x \in A : f(x) \in E\} \in \sigma_A
$$
- notation for a [[measurable function]] $f: \left(X, \sigma_X\right) \to \left(Y, \sigma_Y\right)$


____________________________

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
2) $\mathcal{A}$ is [[closure|closed]] over the [[complement]]

$$
\begin{split}
&A \in \mathcal{A} \Rightarrow A^c \in \mathcal{A} \\
\end{split}
$$

3) $\mathcal{A}$ is [[closure|closed]] over the [[union]]

$$
\begin{split}
&A_1, ..., A_n \in \mathcal{A} \Rightarrow \bigcup_{i \in [n]} A_i \in \mathcal{A} \\
\end{split}
$$
#### a [[sigma algebra]] is [[closure|closed]] over [[intersection]]
$$
A, B \in \mathcal{A} \Rightarrow A \cap B \in \mathcal{A}
$$

#### a [[sigma algebra]] is [[closure|closed]] over [[difference of sets]]
$$
A, B \in \mathcal{A} \Rightarrow A \setminus B \in \mathcal{A}
$$



Tags: mathematics statistics
<!--ID: 1716713552914-->
END



START
Basic
- proof that a [[random variable]] induces a [[probability measure]] on the [[real numbers]]
- how is this [[probability measure]] called in a [[discrete probability space]] and [[continuous probability space]]?
Back: 
### a [[random variable]] induces a [[probability measure]]
- given a [[probability space]] $\left(\Omega, \mathcal{A} , P\right)$ and a [[measurable function]] $X: (\Omega, \mathcal{A}) \to (\mathbb{R}, \mathcal{B})$ we can define a [[probability measure]] $\mathcal{P}_X: \mathcal{B} \to [0,1]$ 

$$
\mathcal{P}_X(E \subseteq \mathbb{R}) 
= P\left(X^{-1}(E) \subseteq \Omega\right) = P\left(\left\{\omega \in \Omega : X(\omega) \in C\right\}\right)
$$
- in a [[continuous probability space]] this [[probability measure]] is called [[probability density function (PDF)]]
- in a [[discrete probability space]] this [[probability measure]] is called [[probability mass function (PMF)]]

#### proof
- the first proberties of a [[probability measure]] is trivial
$$
\begin{split}
\mathcal{P}_X(\emptyset \subseteq \mathbb{R}) 
&= P\left(\left\{\omega \in \Omega : X(\omega) \in \emptyset \right\}\right) \\
&=  P\left( \emptyset \right) 
= 0
\end{split}
$$
- since $X: \Omega \to \mathbb{R}$ is a [[function]] all elements of the [[sample space]] $\Omega$ have to be mapped to a [[real numbers|real number]] and $P\left( \Omega \right) = 1$ is given by the definition of a [[probability function]]
$$
\begin{split}
\mathcal{P}_X(\mathbb{R}) 
&= P\left(\left\{\omega \in \Omega : X(\omega) \in \mathbb{R}\right\}\right) \\
&=  P\left( \Omega \right) 
= 1
\end{split}
$$

- given two [[disjunct]] subsets of the [[real numbers]] $A, B \subseteq \mathbb{R}$
$$
\begin{split}
\mathcal{P}_X(A \cup B) 
&= P\left(\left\{\omega \in \Omega : X(\omega) \in A \cup B \right\}\right) \\
&= P\left(\left\{\omega \in \Omega : X(\omega) \in A  \right\} \cup \left\{\omega \in \Omega : X(\omega) \in  B \right\}\right) \\
&= P\left(\left\{\omega \in \Omega : X(\omega) \in A  \right\}\right) + P\left(\left\{\omega \in \Omega : X(\omega) \in  B \right\}\right) \\
&= \mathcal{P}_X(A) + \mathcal{P}_X(B) \\
\end{split}
$$


### random variable
- given a [[probability space]] $\left(\Omega, \mathcal{A} , P\right)$
- a [[function]] $X: \Omega \to \mathbb{R}$ from the [[sample space]] $\Omega$ to the [[real numbers]] $\mathbb{R}$ is a [[random variable]] if it's a [[measurable function]] $X: (\Omega, \mathcal{A}) \to (\mathbb{R}, \mathcal{B})$
- this is the case exactly when the following is true
$$
\forall x \in \mathbb{R}: X^{-1}\left((-\infty, x]\right) = \{\omega \in \Omega: X(\omega) \in (-\infty, x]\} \in \mathcal{A}
$$


### measurable function
- given two [[measurable space|measurable spaces]] $\left(A, \sigma_A\right)$ and $\left(B, \sigma_B\right)$ with the [[set|sets]] $A$ and $B$ and their [[sigma algebra|sigma algebra]]
- the [[function]] $f: A\to B$ is a [[measurable function]] if every [[set]] in the [[sigma algebra]] of its codomain $\sigma_B$ can be mapped to a [[set]] in the domain [[sigma algebra]] $\sigma_B$ by the [[inverse function]] $f^{-1}$
$$
\forall E \in \sigma_B: f^{-1}(E) = \{x \in A : f(x) \in E\} \in \sigma_A
$$
- notation for a [[measurable function]] $f: \left(X, \sigma_X\right) \to \left(Y, \sigma_Y\right)$


### [[probability measure]] $P$
- [[function]] that assigned a probability to each event
$$
P: \mathcal{A} \mapsto [0,1]
$$
- e.g. for a die throw: $P\left(\left\{2,4,6\right\}\right) = \frac{1}{2}$ 
#### base properties
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


____________________________


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
2) $\mathcal{A}$ is [[closure|closed]] over the [[complement]]

$$
\begin{split}
&A \in \mathcal{A} \Rightarrow A^c \in \mathcal{A} \\
\end{split}
$$

3) $\mathcal{A}$ is [[closure|closed]] over the [[union]]

$$
\begin{split}
&A_1, ..., A_n \in \mathcal{A} \Rightarrow \bigcup_{i \in [n]} A_i \in \mathcal{A} \\
\end{split}
$$
#### a [[sigma algebra]] is [[closure|closed]] over [[intersection]]
$$
A, B \in \mathcal{A} \Rightarrow A \cap B \in \mathcal{A}
$$

#### a [[sigma algebra]] is [[closure|closed]] over [[difference of sets]]
$$
A, B \in \mathcal{A} \Rightarrow A \setminus B \in \mathcal{A}
$$

Tags: mathematics statistics
<!--ID: 1716713552918-->
END