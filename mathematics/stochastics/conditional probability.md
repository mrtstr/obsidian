

### conditional probability
Probability of [[event space|event]] $A$ happened given that we know [[event space|event]] $B$ happened
$$
\begin{split}
P\left(A \mid B\right) 
&= \frac{P\left(A \cap B\right)}{P\left(B\right)} \\
&= \frac{P\left(B \mid A\right)P\left(A\right)}{P\left(B\right)} \\
&= \frac{P\left(A \mid B\right)P\left(B\right)}{P\left(B\right)}
\end{split}
$$
![[Selection_001.png]]

### an [[event]] induces a [[probability space|conditional probability space]]
- given a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ and an [[event]] $B \in \mathcal{A}$
- $B$ induces an [[conditional probability]] space $\left(B , \mathcal{A}_B, \mathbb{P}(\:\cdot\: | B)\right)$ with the trace [[sigma algebra|trace sigma algebra]] $\mathcal{A}_B$ and the [[probability measure]] $\mathbb{P}(\:\cdot\: | B)$

$$
\begin{split}
&\mathcal{A}_B = \mathcal{A} \cap B \\
&\mathbb{P}(A | B) = \frac{\mathbb{P}\left(A \cap B\right)}{\mathbb{P}\left(B\right)}
\end{split}
$$

#### proof that $\mathbb{P}(\:\cdot\: | B)$ is a [[probability measure]]

$$
\begin{split}
&\mathbb{P}(B | B) 
= \frac{\mathbb{P}\left(B \cap B\right)}{\mathbb{P}\left(B\right)}
= \frac{\mathbb{P}\left(B\right)}{\mathbb{P}\left(B\right)}
=1
\end{split}
$$


$$
\begin{split}
&\mathbb{P}(\emptyset | B) 
= \frac{\mathbb{P}\left(B \cap \emptyset\right)}{\mathbb{P}\left(B\right)}
= \frac{\mathbb{P}\left(\emptyset\right)}{\mathbb{P}\left(B\right)}
=0
\end{split}
$$

$$
\begin{split}
\mathbb{P}(A \: \dot{\cup} \: C | B) 
&= \frac{\mathbb{P}\left(B \cap (A \: \dot{\cup} \: C)\right)}{\mathbb{P}\left(B\right)} \\
&= \frac{\mathbb{P}\left((B \cap A) \: \dot{\cup} \: (B \cap C))\right)}{\mathbb{P}\left(B\right)} \\
&= \frac{\mathbb{P}\left((B \cap A)\right) + \mathbb{P}\left((B \cap C))\right)}{\mathbb{P}\left(B\right)} \\
&= \frac{\mathbb{P}\left(B \cap A\right)}{\mathbb{P}\left(B\right)} + \frac{\mathbb{P}\left(B \cap C)\right)}{\mathbb{P}\left(B\right)} \\
&= \mathbb{P}(A | B)  + \mathbb{P}(C | B)  \\
\end{split}
$$


![[sigma algebra#trace sigma algebra]]

### decomposition on the [[intersection]] of [[event space|events]] 
$$
P(A \cap B) = P(B) P(A \mid B) = P(A) P(B \mid A)
$$
$$
\begin{split}
P\left(\bigcap_{i=1}^{n} A_i \right)= &
P\left(A_1\right) \cdot 
P\left(A_2 \mid A_1\right) \cdot
P\left(A_3 \mid A_1 \cap A_2 \right) \cdot \:... \: \cdot
P\left(A_n \mid A_1 \cap A_2 \cap \:... \: A_{n-1} \right) \\
=&\prod\limits_{i=1}^{k}P \left( A_i \Bigm\vert
\bigcap_{j=1}^{i-1} A_j \right)
\end{split}
$$

# -------------------
![[probability measure#probability measure]]

![[probability space#probability space]]

# Anki
START
Basic
conditional probability
- definition
- decomposition on the [[intersection]] of [[event space|events]] 
Back: 
## conditional probability
Probability of [[event space|event]] $A$ happened given that we know [[event space|event]] $B$ happened
$$
\begin{split}
P\left(A \mid B\right) 
&= \frac{P\left(A \cap B\right)}{P\left(B\right)} \\
&= \frac{P\left(B \mid A\right)P\left(A\right)}{P\left(B\right)} \\
&= \frac{P\left(A \mid B\right)P\left(B\right)}{P\left(B\right)}
\end{split}
$$
![[Selection_001.png]]

## decomposition on the [[intersection]] of [[event space|events]] 
$$
P(A \cap B) = P(B) P(A \mid B) = P(A) P(B \mid A)
$$
$$
\begin{split}
P\left(\bigcap_{i=1}^{n} A_i \right)= &
P\left(A_1\right) \cdot 
P\left(A_2 \mid A_1\right) \cdot
P\left(A_3 \mid A_1 \cap A_2 \right) \cdot \:... \: \cdot
P\left(A_n \mid A_1 \cap A_2 \cap \:... \: A_{n-1} \right) \\
=&\prod\limits_{i=1}^{k}P \left( A_i \Bigm\vert
\bigcap_{j=1}^{i-1} A_j \right)
\end{split}
$$

Tags: mathematics statistics
<!--ID: 1666457499349-->
END


START
Basic
- given a [[partitioned sample space]] $\{B_1, ..., B_n\}$
- proof for the following
$$
\begin{split}
P(A | X) = \sum_{all B_j} P(A| B, X) P(B_j | X)
\end{split}
$$
Back: 

$$
\begin{split}
P(A | X) 
&= \frac{P(A , X) }{P(X)} \\
&= \sum_{all B_j} \frac{P(A , X, B_j) }{P(X)} \\
&= \sum_{all B_j} \frac{P(A | X, B_j) P(B_j | X) P(X) }{P(X)} \\
&= \sum_{all B_j} P(A| B, X) P(B_j | X)
\end{split}
$$
Tags: mathematics statistics
<!--ID: 1707456323135-->
END



START
Basic
proof that an [[event]] induces a [[probability space|conditional probability space]]
Back: 
### an [[event]] induces a [[probability space|conditional probability space]]
- given a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ and an [[event]] $B \in \mathcal{A}$
- $B$ induces an [[conditional probability]] space $\left(B , \mathcal{A}_B, \mathbb{P}(\:\cdot\: | B)\right)$ with the trace [[sigma algebra|trace sigma algebra]] $\mathcal{A}_B$ and the [[probability measure]] $\mathbb{P}(\:\cdot\: | B)$

$$
\begin{split}
&\mathcal{A}_B = \mathcal{A} \cap B \\
&\mathbb{P}(A | B) = \frac{\mathbb{P}\left(A \cap B\right)}{\mathbb{P}\left(B\right)}
\end{split}
$$

#### proof that $\mathbb{P}(\:\cdot\: | B)$ is a [[probability measure]]

$$
\begin{split}
&\mathbb{P}(B | B) 
= \frac{\mathbb{P}\left(B \cap B\right)}{\mathbb{P}\left(B\right)}
= \frac{\mathbb{P}\left(B\right)}{\mathbb{P}\left(B\right)}
=1
\end{split}
$$


$$
\begin{split}
&\mathbb{P}(\emptyset | B) 
= \frac{\mathbb{P}\left(B \cap \emptyset\right)}{\mathbb{P}\left(B\right)}
= \frac{\mathbb{P}\left(\emptyset\right)}{\mathbb{P}\left(B\right)}
=0
\end{split}
$$

$$
\begin{split}
\mathbb{P}(A \: \dot{\cup} \: C | B) 
&= \frac{\mathbb{P}\left(B \cap (A \: \dot{\cup} \: C)\right)}{\mathbb{P}\left(B\right)} \\
&= \frac{\mathbb{P}\left((B \cap A) \: \dot{\cup} \: (B \cap C))\right)}{\mathbb{P}\left(B\right)} \\
&= \frac{\mathbb{P}\left((B \cap A)\right) + \mathbb{P}\left((B \cap C))\right)}{\mathbb{P}\left(B\right)} \\
&= \frac{\mathbb{P}\left(B \cap A\right)}{\mathbb{P}\left(B\right)} + \frac{\mathbb{P}\left(B \cap C)\right)}{\mathbb{P}\left(B\right)} \\
&= \mathbb{P}(A | B)  + \mathbb{P}(C | B)  \\
\end{split}
$$



### trace sigma algebra
- let $A$ be a nonempty [[set]] and let $\mathcal{A}$ be a [[sigma algebra]] on $A$
- let $B \subseteq A$ be a subset of $A$ then $\mathcal{B}$ is a [[sigma algebra]] on $B$

$$
\mathcal{B} = \{B \cap S: S \in \mathcal{A}\}
$$
#### proof

1) since $\emptyset \in \mathcal{A}$ and the [[empty set]] has to be in $B$

$$
B \cap \emptyset = \emptyset \in \mathcal{B}
$$

2) since $A \in \mathcal{A}$ and  $B$ is a subset of $A$ their [[intersection]] has to be in $\mathcal{B}$ 

$$
B \cap A = B \in \mathcal{B}
$$

3) $\mathcal{B}$ is [[closure|closed]] over the [[union]]

$$
\begin{split}
&X, Y \in \mathcal{B}\\
\Rightarrow& \exists X', Y' \in \mathcal{A}: X = X' \cap B \land Y = Y' \cap B \\
\Rightarrow&  X' \cup  Y' \in \mathcal{A} \\
\Rightarrow&  (X' \cup  Y') \cap B \in \mathcal{B} \\
\Rightarrow&  (X' \cap B) \cup (X' \cap B) \in \mathcal{B} \\
\Rightarrow&  X \cup Y \in \mathcal{B} \\
\end{split}
$$


3) $\mathcal{A}$ is [[closure|closed]] over the [[complement]]
$$
\begin{split}
&X \in \mathcal{B}\\
\Rightarrow& \exists X' \in \mathcal{A}: X = X' \cap B \\
\Rightarrow&  X'^c \in \mathcal{A} \\
\Rightarrow&  X'^c \cap B = X^c \in \mathcal{B} \\
\end{split}
$$


_________________

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
<!--ID: 1717774107169-->
END



START
Basic
proof that $\mathbb{P}(A | B) = \frac{\mathbb{P}\left(A \cap B\right)}{\mathbb{P}\left(B\right)}$ is a [[probability measure]]

Back: 
#### proof that $\mathbb{P}(\:\cdot\: | B)$ is a [[probability measure]]

$$
\begin{split}
&\mathbb{P}(B | B) 
= \frac{\mathbb{P}\left(B \cap B\right)}{\mathbb{P}\left(B\right)}
= \frac{\mathbb{P}\left(B\right)}{\mathbb{P}\left(B\right)}
=1
\end{split}
$$


$$
\begin{split}
&\mathbb{P}(\emptyset | B) 
= \frac{\mathbb{P}\left(B \cap \emptyset\right)}{\mathbb{P}\left(B\right)}
= \frac{\mathbb{P}\left(\emptyset\right)}{\mathbb{P}\left(B\right)}
=0
\end{split}
$$

$$
\begin{split}
\mathbb{P}(A \: \dot{\cup} \: C | B) 
&= \frac{\mathbb{P}\left(B \cap (A \: \dot{\cup} \: C)\right)}{\mathbb{P}\left(B\right)} \\
&= \frac{\mathbb{P}\left((B \cap A) \: \dot{\cup} \: (B \cap C))\right)}{\mathbb{P}\left(B\right)} \\
&= \frac{\mathbb{P}\left((B \cap A)\right) + \mathbb{P}\left((B \cap C))\right)}{\mathbb{P}\left(B\right)} \\
&= \frac{\mathbb{P}\left(B \cap A\right)}{\mathbb{P}\left(B\right)} + \frac{\mathbb{P}\left(B \cap C)\right)}{\mathbb{P}\left(B\right)} \\
&= \mathbb{P}(A | B)  + \mathbb{P}(C | B)  \\
\end{split}
$$




_________________

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
<!--ID: 1717774107174-->
END