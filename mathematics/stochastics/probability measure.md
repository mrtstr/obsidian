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

# -----------
![[measurable space#measurable space]]

![[sigma algebra#$ sigma$ algebra]]

# anki





START
Basic
proof for the follwoing propertie of a [[probability measure]] plus base properties

$$
\begin{split}
P\left(A^c\right) 
&= 1 - P(A) \\
\end{split}
$$

Back: 
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

______________________
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

Tags: mathematics statistics
<!--ID: 1716645825917-->
END


START
Basic
[[probability measure]]
- definition
- base properties
- derived properties (without proof)

Back: 
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

______________________
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
Tags: mathematics statistics
<!--ID: 1716645825909-->
END


START
Basic
proof for the follwoing propertie of a [[probability measure]] plus base properties

$$
\begin{split}
P\left(A \cup B\right) 
&= P(A) + P(B) - P\left(A \cup B\right)  \\
\end{split}
$$

Back: 
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

______________________
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

Tags: mathematics statistics
<!--ID: 1716645825914-->
END
