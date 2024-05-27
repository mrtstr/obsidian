
### probability mass function (PMF)
- given a [[random variable]] $X$ in a [[discrete probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ (the [[sample space]] $\Omega$ is [[countable]]) with a [[distribution]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$
- we can define the [[probability mass function (PMF)]] $f_X: \mathbb{R} \to [0,1]$ that is assigning a [[probability]] to each outcome in the [[sample space]]
- since $X: \Omega \to \mathbb{R}$ is a [[function]] each $\omega \in \Omega$ is assigned to exactitly one $x \in \mathbb{R}$ thus given two [[disjoint]] [[set|sets]] of $A, B \subset \mathbb{R} \to X^{-1}(A), X^{-1}(A) \subset \Omega$ are [[disjoint]] 
$$
\begin{split}
f_X(x) 
&= \mathcal{P}_X(\{x\}) \\
&= \mathbb{P}\left(X^{-1}(\{x\})\right) \\
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) = x\right\}\right) \\
&= \mathbb{P}\left(X =x\right) \\
\end{split}
$$
- from the [[probability mass function (PMF)]] we can calculate the [[probability]] that $X$ takes a value in a [[set]] of [[real numbers]] $C$
$$
\mathbb{P}(X \in C \subseteq \mathbb{R}) = \sum\limits_{x_i \in C} f_X(x_i)
$$

### difference [[probability mass function (PMF)|PMF]] to the [[distribution]] 
- the [[distribution]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ mapps every [[borel sigma algebra|borel set]] $\in \mathcal{B}(\mathbb{R})$ to a probability and is defined for every [[random variable]]
- the [[probability mass function (PMF)]] $f_X: \mathbb{R} \to [0,1]$ assignes a probability to each [[real numbers|real number]] and is only defined for [[discrete probability space|discrete]] [[random variable]]
- for a [[discrete probability space|discrete]] [[random variable]] the [[probability mass function (PMF)]] specifies the [[distribution]] because it can be used to assign a probaility to each [[set]] of [[real numbers]]

### Example
The [[sample space]] is containing all possible outcomes $\Omega = \left\{H, T\right\}^{10}$ with $\left|\Omega\right|=2^{10}$. We can define a [[probability mass function (PMF)]] on $\Omega$ that is counting the number of heads $X: \Omega \mapsto \left\{1,..,10\right\}$. 
For every [[set]] of numbers we can define an [[event]] with a [[probability]].
$$
\begin{split}
&C = \{10\} \\
&\Rightarrow \left\{ X \in \Omega \right\} =  \left\{\omega \mid X(\omega) \in C\right\} = \{HHHHHHHHHH\} \\
&\Rightarrow P\left(\left\{ X \in \Omega \right\}\right) = \frac{1}{2^{10}}
\\ \\
&C = \{9, 10\} \\
&\Rightarrow \left\{ X \in \Omega \right\} =  \left\{\omega \mid X(\omega) \in C\right\} = \{H^{10}, TH^9, HTH^8, ...\} \\
&\Rightarrow P\left(\left\{ X \in \Omega \right\}\right) = \frac{1 + 10}{2^{10}}
\end{split}
$$ 

# ----------------------

![[distribution#distribution]]

![[continuous probability space#continuous probability space]]

![[random variable#a random variable induces a probability measure]]


![[random variable#random variable]]




## [[bernoulli distribution|bernoulli distribution]]
![[bernoulli distribution#probability function]]
## [[discrete uniform distribution]]
![[discrete uniform distribution#probability function]]
## [[binomial distribution]]
![[binomial distribution#probability function]]
### [[poisson distribution]]
![[poisson distribution#probability function]]
### [[hypergeometric distribution]]
![[hypergeometric distribution#probability function]]





# ----------------------


START
Basic
[[probability mass function (PMF)]]:
- definition
- difference to the distribution
Back: 
### probability mass function (PMF)
- given a [[random variable]] $X$ in a [[discrete probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ (the [[sample space]] $\Omega$ is [[countable]]) with a [[distribution]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$
- we can define the [[probability mass function (PMF)]] $f_X: \Omega \to [0,1]$ that is assigning a [[probability]] to each outcome in the [[sample space]]
- since $X: \Omega \to \mathbb{R}$ is a [[function]] each $\omega \in \Omega$ is assigned to exactitly one $x \in \mathbb{R}$ thus given two [[disjoint]] [[set|sets]] of $A, B \subset \mathbb{R} \to X^{-1}(A), X^{-1}(A) \subset \Omega$ are [[disjoint]] 
$$
\begin{split}
f_X(x) 
&= \mathcal{P}_X(\{x\}) \\
&= \mathbb{P}\left(X^{-1}(\{x\})\right) \\
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) = x\right\}\right) \\
&= \mathbb{P}\left(X =x\right) \\
\end{split}
$$
- from the [[probability mass function (PMF)]] we can calculate the [[probability]] that $X$ takes a value in a [[set]] of [[real numbers]] $C$
$$
\mathbb{P}(X \in C \subseteq \mathbb{R}) = \sum\limits_{x_i \in C} f_X(x_i)
$$

### difference [[probability mass function (PMF)|PMF]] to the [[distribution]] 
- the [[distribution]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ mapps every [[borel sigma algebra|borel set]] $\in \mathcal{B}(\mathbb{R})$ to a probability and is defined for every [[random variable]]
- the [[probability mass function (PMF)]] $f_X: \mathbb{R} \to [0,1]$ assignes a probability to each [[real numbers|real number]] and is only defined for [[discrete probability space|discrete]] [[random variable]]
- for a [[discrete probability space|discrete]] [[random variable]] the [[probability mass function (PMF)]] specifies the [[distribution]] because it can be used to assign a probaility to each [[set]] of [[real numbers]]


______________________
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
- a [[function]] $X: \Omega \to \mathbb{R}$ from the [[sample space]] $\Omega$ to the [[real numbers]] $\mathbb{R}$ is a [[random variable]] if it's a [[measurable function]] $X: (\Omega, \mathcal{A}) \to \left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$ from the [[measurable space]] of $(\Omega, \mathcal{A})$ to the [[real numbers]] with the [[borel sigma algebra]] (which are a [[measurable space]] too)
- this is the case exactly when the following is true (given the [[inverse function]] $X^{-1}: \mathbb{R} \to \Omega$)
$$
\forall x \in \mathbb{R}: X^{-1}\left((-\infty, x]\right) = \{\omega \in \Omega: X(\omega) \in (-\infty, x]\} \in \mathcal{A}
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
- thus $X^{-1}(A)$ and $X^{-1}(B)$ have to be [[disjoint]]

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
<!--ID: 1664442661951-->
END


START
Basic
- 10 coint tosses with the with a random variable $X: \Omega \to \mathbb{R}$ that es equal to the number of heads
- how does the [[sample space]] $\Omega$ and the [[probability mass function (PMF)]] look like?

Back: 

### Example
The [[sample space]] is containing all possible outcomes $\Omega = \left\{H, T\right\}^{10}$ with $\left|\Omega\right|=2^{10}$. We can define a [[probability mass function (PMF)]] on $\Omega$ that is counting the number of heads $X: \Omega \mapsto \left\{1,..,10\right\}$. 
For every [[set]] of numbers we can define an [[event]] with a [[probability]].
$$
\begin{split}
&C = \{10\} \\
&\Rightarrow \left\{ X \in \Omega \right\} =  \left\{\omega \mid X(\omega) \in C\right\} = \{HHHHHHHHHH\} \\
&\Rightarrow P\left(\left\{ X \in \Omega \right\}\right) = \frac{1}{2^{10}}
\\ \\
&C = \{9, 10\} \\
&\Rightarrow \left\{ X \in \Omega \right\} =  \left\{\omega \mid X(\omega) \in C\right\} = \{H^{10}, TH^9, HTH^8, ...\} \\
&\Rightarrow P\left(\left\{ X \in \Omega \right\}\right) = \frac{1 + 10}{2^{10}}
\end{split}
$$ 




### probability mass function (PMF)
- given a [[random variable]] $X$ in a [[discrete probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ (the [[sample space]] $\Omega$ is [[countable]]) with a [[distribution]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$
- we can define the [[probability mass function (PMF)]] $f_X: \Omega \to [0,1]$ that is assigning a [[probability]] to each outcome in the [[sample space]]
- since $X: \Omega \to \mathbb{R}$ is a [[function]] each $\omega \in \Omega$ is assigned to exactitly one $x \in \mathbb{R}$ thus given two [[disjoint]] [[set|sets]] of $A, B \subset \mathbb{R} \to X^{-1}(A), X^{-1}(A) \subset \Omega$ are [[disjoint]] 
$$
\begin{split}
f_X(x) 
&= \mathcal{P}_X(\{x\}) \\
&= \mathbb{P}\left(X^{-1}(\{x\})\right) \\
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) = x\right\}\right) \\
&= \mathbb{P}\left(X =x\right) \\
\end{split}
$$
- from the [[probability mass function (PMF)]] we can calculate the [[probability]] that $X$ takes a value in a [[set]] of [[real numbers]] $C$
$$
\mathbb{P}(X \in C \subseteq \mathbb{R}) = \sum\limits_{x_i \in C} f_X(x_i)
$$
______________________
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
- a [[function]] $X: \Omega \to \mathbb{R}$ from the [[sample space]] $\Omega$ to the [[real numbers]] $\mathbb{R}$ is a [[random variable]] if it's a [[measurable function]] $X: (\Omega, \mathcal{A}) \to \left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$ from the [[measurable space]] of $(\Omega, \mathcal{A})$ to the [[real numbers]] with the [[borel sigma algebra]] (which are a [[measurable space]] too)
- this is the case exactly when the following is true (given the [[inverse function]] $X^{-1}: \mathbb{R} \to \Omega$)
$$
\forall x \in \mathbb{R}: X^{-1}\left((-\infty, x]\right) = \{\omega \in \Omega: X(\omega) \in (-\infty, x]\} \in \mathcal{A}
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
- thus $X^{-1}(A)$ and $X^{-1}(B)$ have to be [[disjoint]]

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
<!--ID: 1667211139255-->
END



START
Basic
[[discrete distribution]] of a [[probability mass function (PMF)]]:
- definition
- example
Back: 
Given a [[probability mass function (PMF)]] $X: \Omega \mapsto \mathbb{R}$ on a [[sample space]] $\Omega$ we can derive [[event|events]] for all [[set|sets]] of real values $C \subseteq \mathbb{R}$ on the original [[probability space]].
The [[discrete distribution]] of a [[probability mass function (PMF)]] is the collection of the [[probability|probabilities]] of these [[event|events]] $X \in C$.
$$

\left\{P(X \in C) \mid C \subseteq \mathbb{R} \right\} = \left\{P\left(\left\{\omega \mid X(\omega) \in C\right\} \right) \mid C \subseteq \mathbb{R}\right\}

$$

### Example: tossing a coin 10 times
The [[sample space]] is containing all possible outcomes $\Omega = \left\{H, T\right\}^{10}$ with $\left|\Omega\right|=2^{10}$. We can define a [[random variable]] on $\Omega$ that is counting the number of heads $X: \Omega \mapsto \left\{1,..,10\right\}$. 
For every [[set]] of numbers we can define an [[event]] with a [[probability]].
$$
\begin{split}
&C = \{10\} \\
&\Rightarrow \left\{ X \in \Omega \right\} =  \left\{\omega \mid X(\omega) \in C\right\} = \{HHHHHHHHHH\} \\
&\Rightarrow P\left(\left\{ X \in \Omega \right\}\right) = \frac{1}{2^{10}}
\\ \\
&C = \{9, 10\} \\
&\Rightarrow \left\{ X \in \Omega \right\} =  \left\{\omega \mid X(\omega) \in C\right\} = \{H^{10}, TH^9, HTH^8, ...\} \\
&\Rightarrow P\left(\left\{ X \in \Omega \right\}\right) = \frac{1 + 10}{2^{10}}
\end{split}
$$ 
Tags: mathematics statistics
<!--ID: 1667204899520-->
END


START
Basic
## important [[discrete distribution]] summary
- [[probability function]]
- explainaition
Back: 

### [[bernoulli distribution]]
- binary [[random experiment]] 
- $p=$ probability of positive outcome
$$
\begin{split}
f_X(x | p) &= 
\begin{cases}
    p,& \text{if } x= 1\\
    1-p,& \text{if } x= 0\\
    0,              & \text{otherwise}
\end{cases} \\
&= 
\begin{cases}
    p^x (1-p)^{1-x},& \text{if } x= 0,1\\
    0,              & \text{otherwise}
\end{cases}
\end{split}
$$
### [[binomial distribution]]
- $n =$ number of [[bernoulli distribution|bernoulli experiments]] 
- $p=$ probability of positive outcome
- $x=$ number of positive outcomes

$$
f_X(X = x | n, p)= 
\begin{cases}
\overbrace{{n \choose x}}^\text{number of valid splits }
\overbrace{p^{x}(1-p)^{n-x}}^\text{ probability per split}
 
,& \text{if } x \in \{0,1,2,..., n\}\\
0
,& \text{otherwise}
\end{cases}
$$

### [[poisson distribution]]
- $\lambda = np$ with $n =$ number of [[bernoulli distribution|bernoulli experiments]] and $p=$ probability of positive outcome
- assumtions: $p \ll 1 \Leftrightarrow x \ll n$
- $x=$ number of positive outcomes
$$
f_X(x | \lambda) =
\begin{cases}
\frac{\lambda^xe^{-\lambda}}{x!}
& \text{if } x \in \{0,1,2,..., n\}\\
0
& \text{otherwise}
\end{cases}
$$

### [[hypergeometric distribution]]
- $n =$ number of [[unordered sampling without replacement|unordered samples without replacement]] 
- $a=$ number of positive balls
- $b=$ number of negative balls
- $x=$ number of positive outcomes
$$
f_X({x|a,b,n}) = \frac{
{a \choose x}{b \choose n-x}
}{{a+b \choose n}}
\quad for \: max\{0, n-b\}<x<min\{n, a\}
$$
### [[discrete uniform distribution]]
- has the same probability of taking all integers inside a range $\{a,...,b\}$ and 0 for all other values

$$
f_X(X = x | a, b)= 
\begin{cases}
\frac{1}{b-a+1}
,& \text{if } x \in \{a,a+1,...,b-1, b\}\\
0
,& \text{otherwise}
\end{cases}
$$

Tags: mathematics statistics
<!--ID: 1678520971208-->
END