### measurable function
- given two [[measurable space|measurable spaces]] $\left(A, \sigma_A\right)$ and $\left(B, \sigma_B\right)$ with the [[set|sets]] $A$ and $B$ and their [[sigma algebra|sigma algebra]]
- the [[function]] $f: A\to B$ is a [[measurable function]] if every [[set]] in the [[sigma algebra]] of its codomain $\sigma_B$ can be mapped to a [[set]] in the domain [[sigma algebra]] $\sigma_B$ by the [[inverse function]] $f^{-1}:B \to A$
$$
\forall E \in \sigma_B: f^{-1}(E) = \{x \in A : f(x) \in E\} \in \sigma_A
$$
- notation for a [[measurable function]] $f: \left(X, \sigma_X\right) \to \left(Y, \sigma_Y\right)$


# ----------------------
![[measurable space#measurable space]]

![[sigma algebra#$ sigma$ algebra]]

# anki

START
Basic
[[measurable function]]
- definition
- notation

Back: 
### measurable function
- given two [[measurable space|measurable spaces]] $\left(A, \sigma_A\right)$ and $\left(B, \sigma_B\right)$ with the [[set|sets]] $A$ and $B$ and their [[sigma algebra|sigma algebra]]
- the [[function]] $f: A\to B$ is a [[measurable function]] if every [[set]] in the [[sigma algebra]] of its codomain $\sigma_B$ can be mapped to a [[set]] in the domain [[sigma algebra]] $\sigma_B$ by the [[inverse function]] $f^{-1}$
$$
\forall E \in \sigma_B: f^{-1}(E) = \{x \in A : f(x) \in E\} \in \sigma_A
$$
- notation for a [[measurable function]] $f: \left(X, \sigma_X\right) \to \left(Y, \sigma_Y\right)$

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
<!--ID: 1716713552907-->
END