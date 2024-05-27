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

### relationship to other concepts
- every [[measurable space]] $(\Omega, \mathcal{A})$ has a non empty [[set]]  $\Omega$ and a [[sigma algebra]]  $\mathcal{A}$
- every a [[measurable space]] with a [[probability measure]] $\mathbb{P}$ is a [[probability space]]
- a [[measurable function]] mappes from one [[measurable space]] to another [[measurable space]]
- a [[measurable function]] from a [[probability space]] to a [[measurable space]] can induce a [[probability measure]] in its domain (thus its is a [[probability space]] too) 
- a [[random variable]] is a [[measurable function]] that mapps to the [[real numbers]]
- a [[random variable]] induces a [[probability space]] $(\mathbb{R}, \mathcal{B}(\mathbb{R}), \mathcal{P_X})$ by inducing a [[probability measure]] $\mathcal{P_X}$
# ------------------
![[measurable space#measurable space]]


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





START
Basic

relationship of the following concepts
- [[measurable space]]
- [[sigma algebra]]
- [[probability space]]
- [[probability measure]]
- [[measurable function]]
- [[random variable]]
- [[distribution]]

- is every [[random variable]] in a [[probability space]]?
- is very [[measurable space]] a [[probability space]]?
- does every [[random variable]] have a [[distribution]]?

Back: 

### relationship to other concepts
- every [[measurable space]] $(\Omega, \mathcal{A})$ has a nonempty [[set]] $\Omega$ and a [[sigma algebra]]  $\mathcal{A}$
- every a [[measurable space]] with a [[probability measure]] $\mathbb{P}$ is a [[probability space]]
- a [[measurable function]] mappes from one [[measurable space]] to another [[measurable space]]
- a [[measurable function]] from a [[probability space]] to a [[measurable space]] can induce a [[probability measure]] in its domain (thus its is a [[probability space]] too) 
- a [[random variable]] is a [[measurable function]] that mapps to the [[real numbers]]
- a [[random variable]] induces a [[probability space]] $(\mathbb{R}, \mathcal{B}(\mathbb{R}), \mathcal{P_X})$ by inducing a [[probability measure]] $\mathcal{P_X}$

________________

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


### random variable
- given a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$
- a [[function]] $X: \Omega \to \mathbb{R}$ from the [[sample space]] $\Omega$ to the [[real numbers]] $\mathbb{R}$ is a [[random variable]] if it's a [[measurable function]] $X: (\Omega, \mathcal{A}) \to \left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$ 

$$
\forall C \in \mathcal{B}(\mathbb{R}): X^{-1}(C) = \{\omega \in \Omega : X(\omega) \in C\} \in \mathcal{A}
$$


### measurable function
- given two [[measurable space|measurable spaces]] $\left(A, \mathcal{A}\right)$ and $\left(B, \mathcal{B}\right)$ with the [[set|sets]] $A$ and $B$ and their [[sigma algebra|sigma algebra]]
- the [[function]] $f: A\to B$ is a [[measurable function]] if every [[set]] in the [[sigma algebra]] of its codomain $\mathcal{B}$ can be mapped to a [[set]] in the domain [[sigma algebra]] $\mathcal{A}$ by the [[inverse function]] $f^{-1}:B \to A$
$$
\forall E \in \mathcal{B}: f^{-1}(E) = \{x \in A : f(x) \in E\} \in \mathcal{A}
$$
- notation for a [[measurable function]] $f: \left(A, \mathcal{A}\right) \to \left(B, \mathcal{B}\right)$



### measurable space
- a [[measurable space]] $\left(\Omega,\mathcal{A} )\right)$ is a [[set]] $\Omega$ equiped with a [[sigma algebra]] $\mathcal{A}$
- every [[probability space]] is by definition a [[measurable space]]



### probability space
- a [[probability space]] $(\Omega, \mathcal{A}, P)$ is a formal model for a [[random process]]
- if a [[measurable space]] $\left(\Omega, \mathcal{A}=\sigma(\Omega)\right)$ is equiped with a [[probability measure]] $P$ it is a [[probability space]]

### $\sigma$ algebra
- given a [[set]] $\Omega$ a $\sigma$-algebra $\mathcal{A}$ is a system of subsets of $\Omega$ with the following 3 base properties
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

Tags: mathematics statistics
<!--ID: 1716833666294-->
END