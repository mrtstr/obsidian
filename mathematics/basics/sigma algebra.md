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

# --------------
![[set#de morgan’s laws]]



START
Basic
[[sigma algebra]]
- definition
- for what is it used?
- base properties 
- derrived properties (without proof)


Back: 
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

Tags: mathematics statistics
<!--ID: 1716645825928-->
END



START
Basic
proof that a [[sigma algebra]] is [[closure|closed]] over [[intersection]]

Back: 

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


____________________

#### de morgan’s laws
$$
\begin{split}
(A \cup B)^c
&= \left\{ x \: : \: x \in \mathbb{U} \land x \notin (A \cup B) \right\} \\
&= \left\{ x \: : \: x \in \mathbb{U} \land  (x \notin A \land x \notin B) \right\} \\
&= \left\{ x \: : \: x \in \mathbb{U} \land  x \notin A \land x \notin B \right\} \\
&= \left\{ x \: : \: (x \in \mathbb{U} \land  x \notin A) \land (x \in \mathbb{U} \land  x \notin B) \right\} \\
&= \left\{ x \: : \: x \in \mathbb{U} \land  x \notin A \right\} \cap
\left\{ x \: : \: x \in \mathbb{U} \land  x \notin B \right\}\\
&= A^c \cap B^c
\end{split}
$$

$$
\begin{split}
(A \cap B)^c
&= \left\{ x \: : \: x \in \mathbb{U} \land x \notin (A \cap B) \right\} \\
&= \left\{ x \: : \: x \in \mathbb{U} \land  (x \notin A \lor x \notin B) \right\} \\
&= \left\{ x \: : \: (x \in \mathbb{U} \land  x \notin A) \lor (x \in \mathbb{U} \land  x \notin B) \right\} \\
&= \left\{ x \: : \: x \in \mathbb{U} \land  x \notin A \right\} \cup
\left\{ x \: : \: x \in \mathbb{U} \land  x \notin B \right\}\\
&= A^c \cup B^c
\end{split}
$$


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
<!--ID: 1716645825931-->
END


START
Basic
proof that a [[sigma algebra]] is [[closure|closed]] over [[intersection]]

Back: 
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


____________________

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



#### de morgan’s laws
$$
\begin{split}
(A \cup B)^c
&= \left\{ x \: : \: x \in \mathbb{U} \land x \notin (A \cup B) \right\} \\
&= \left\{ x \: : \: x \in \mathbb{U} \land  (x \notin A \land x \notin B) \right\} \\
&= \left\{ x \: : \: x \in \mathbb{U} \land  x \notin A \land x \notin B \right\} \\
&= \left\{ x \: : \: (x \in \mathbb{U} \land  x \notin A) \land (x \in \mathbb{U} \land  x \notin B) \right\} \\
&= \left\{ x \: : \: x \in \mathbb{U} \land  x \notin A \right\} \cap
\left\{ x \: : \: x \in \mathbb{U} \land  x \notin B \right\}\\
&= A^c \cap B^c
\end{split}
$$

$$
\begin{split}
(A \cap B)^c
&= \left\{ x \: : \: x \in \mathbb{U} \land x \notin (A \cap B) \right\} \\
&= \left\{ x \: : \: x \in \mathbb{U} \land  (x \notin A \lor x \notin B) \right\} \\
&= \left\{ x \: : \: (x \in \mathbb{U} \land  x \notin A) \lor (x \in \mathbb{U} \land  x \notin B) \right\} \\
&= \left\{ x \: : \: x \in \mathbb{U} \land  x \notin A \right\} \cup
\left\{ x \: : \: x \in \mathbb{U} \land  x \notin B \right\}\\
&= A^c \cup B^c
\end{split}
$$




Tags: mathematics statistics

END