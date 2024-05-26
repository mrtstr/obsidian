### borel sigma algebra
- the [[borel sigma algebra]] $\mathcal{B}(\mathbb{R})$ is a [[sigma algebra]] on the [[real numbers]] 
- thus $\left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$ are a [[measurable space]] 
- $\mathcal{B}(\mathbb{R}) \subset \mathcal{P}(\mathbb{R})$ does contain all substs of $\mathbb{R}$ for which need a probability assigned to it
- the concept of the [[borel sigma algebra]] is needed because using all subsets of $\mathbb{R}$ ([[power set]]) would cause problems in the axiomatic build up of probability theory
# ---------------
![[measurable space#measurable space]]

![[sigma algebra#$ sigma$ algebra]]

# anki

START
Basic
[[borel sigma algebra]]
- definition
- relationship to the concept [[measurable space]]
- why is the concept needed?

Back: 
### borel sigma algebra
- the [[borel sigma algebra]] $\mathcal{B}(\mathbb{R})$ is a [[sigma algebra]] on the [[real numbers]] 
- thus $\left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$ are a [[measurable space]] 
- $\mathcal{B}(\mathbb{R}) \subset \mathcal{P}(\mathbb{R})$ does contain all substs of $\mathbb{R}$ for which need a probability assigned to it
- the concept of the [[borel sigma algebra]] is needed because using all subsets of $\mathbb{R}$ ([[power set]]) would cause problems in the axiomatic build up of probability theory
__________________


### measurable space
- a [[measurable space]] $\left(\Omega,\mathcal{A} = \sigma(\Omega)\right)$ is a [[set]] $\Omega$ equiped with a [[sigma algebra]]
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
<!--ID: 1716733308271-->
END