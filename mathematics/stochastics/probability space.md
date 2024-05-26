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

# ------------------

![[probability measure#probability measure]]


![[sigma algebra#$ sigma$ algebra]]

# anki

START
Basic
[[probability space]]
- definition plus definition of components
- base + derived properties without proof

Back: 
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

________________
### $\sigma$ algebra
- given a [[set]] $\Omega$ a $\sigma$-algebra $\mathcal{A}$ is a system of subsets of $\Omega$ with the following 3 base properties
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
proof
$$
\begin{split}
A,B \in \mathcal{A} 
&\Rightarrow A^c, B^c \in \mathcal{A} \\
&\Rightarrow \left(A^c \cup B^c\right)^c \in \mathcal{A} \\
&\Rightarrow A \cap B \in \mathcal{A} \qquad \text{(de morgans law)} \\
\end{split}
$$


#### a [[sigma algebra]] is [[closure|closed]] over [[difference of sets]]
$$
A, B \in \mathcal{A} \Rightarrow A \setminus B \in \mathcal{A}
$$
proof
$$
\begin{split}
A,B \in \mathcal{A} 
&\Rightarrow A \cap B^c \in \mathcal{A} \\
&\Rightarrow \{x : x \in A \land x \in \Omega \land x \notin B\} \subseteq \mathcal{A} \\
&\Rightarrow \{x : x \in A \land x \notin B\} \subseteq \mathcal{A} \\
&\Rightarrow A \setminus B \in \mathcal{A}  \\
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
<!--ID: 1664442661959-->
END




START
Basic
die throw example: how does the [[probability space]] look like?

Back: 
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

________________
### $\sigma$ algebra
- given a [[set]] $\Omega$ a $\sigma$-algebra $\mathcal{A}$ is a system of subsets of $\Omega$ with the following 3 base properties
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

- probability of the [[union]]
$$
\begin{split}
P\left(A \cup B\right) 
&= P(A) + P(B) - P\left(A \cup B\right)  \\
\end{split}
$$

Tags: mathematics statistics
<!--ID: 1716713552921-->
END