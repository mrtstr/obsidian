
### [[law of total probability]] for [[event|events]]
- given a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ and a [[partition]] of the [[sample space]] $\Omega$ $B = \{B_i \mid i=1,2,...,k\}$ 
- the following is true
$$
\mathbb{P}(A)=\sum\limits_{i=1}^{k}\mathbb{P}(B_i)\cdot \mathbb{P}(A \mid B_i)
$$

![[Selection_002.png]]

#### proof
$$
\begin{split}
\mathbb{P}(A) 
&=\mathbb{P}(A \cap \Omega)  \\
&=\mathbb{P}\left(A \cap \bigcup_{i=1}^{k} B_i\right)  \\
&=\mathbb{P}\left( \bigcup_{i=1}^{k} A \cap B_i\right)  \\
&=\sum\limits_{i=1}^{k}\mathbb{P}\left(  A \cap B_i\right) \\
&=\sum\limits_{i=1}^{k}\mathbb{P}(B_i) \cdot \frac{\mathbb{P}\left(  A \cap B_i\right)}{\mathbb{P}(B_i)} \\
&= \sum\limits_{i=1}^{k}\mathbb{P}(B_i)\cdot \mathbb{P}(A \mid B_i) \\
\end{split}
$$

### [[law of total probability]] for a [[random variable]]

With the [[multiplication rule]] $f_{XY}(x,y) =f_{X\mid Y}(x \mid y) \cdot f_Y(y)$ we can express the [[marginal distribution]] as the following to get the [[law of total probability]] for [[continuous random variable]]
$$
f_{X}(x) = 
\int\limits^{\infty}_{-\infty} f_{X\mid Y}(x \mid y) f_Y(y) dy
$$
### [[law of total probability]] for a [[probability mass function (PMF)]]
$$
f_{X}(x) = 
\sum\limits_{all \:y} f_{X\mid Y}(x \mid y) f_Y(y)
$$
# ---------------
![[partition#partition of a set]]

![[conditional probability#conditional probability]]

# anki

START
Basic
[[law of total probability]] with proof
Back: 
### law of total probability
- given a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ and a [[partition]] of the [[sample space]] $\Omega$ $B = \{B_i \mid i=1,2,...,k\}$ 
- the following is true
$$
\mathbb{P}(A)=\sum\limits_{i=1}^{k}\mathbb{P}(B_i)\cdot \mathbb{P}(A \mid B_i)
$$

![[Selection_002.png]]

#### proof
$$
\begin{split}
\mathbb{P}(A) 
&=\mathbb{P}(A \cap \Omega)  \\
&=\mathbb{P}\left(A \cap \bigcup_{i=1}^{k} B_i\right)  \\
&=\mathbb{P}\left( \bigcup_{i=1}^{k} A \cap B_i\right)  \\
&=\sum\limits_{i=1}^{k}\mathbb{P}\left(  A \cap B_i\right) \\
&=\sum\limits_{i=1}^{k}\mathbb{P}(B_i) \cdot \frac{\mathbb{P}\left(  A \cap B_i\right)}{\mathbb{P}(B_i)} \\
&= \sum\limits_{i=1}^{k}\mathbb{P}(B_i)\cdot \mathbb{P}(A \mid B_i) \\
\end{split}
$$
_________________


### partition of a [[set]]
Let $A$ be a [[set]] and $A_1,..., A_n \subseteq A$ subsets of $A$. $A_1,..., A_n$ are a [[partition]] of $A$ if the following is true:
1) $\bigcup_{i \in [n]} A_i = A$  
2) $A_i \cap A_j = \emptyset \: \forall i \neq j \in [n]$  

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


Tags: mathematics statistics
<!--ID: 1666457499354-->
END


START
Basic
[[law of total probability]]
- [[continuous random variable]] 
- [[probability mass function (PMF)]]
Back: 
## [[law of total probability]] for a [[continuous random variable]]

With the [[multiplication rule]] $f_{XY}(x,y) =f_{X\mid Y}(x \mid y) \cdot f_Y(y)$ we can express the [[marginal distribution]] as the following to get the [[law of total probability]] for [[continuous random variable]]
$$
f_{X}(x) = 
\int\limits^{\infty}_{-\infty} f_{X\mid Y}(x \mid y) f_Y(y) dy
$$
## [[law of total probability]] for a [[probability mass function (PMF)]]

$$
f_{X}(x) = 
\sum\limits_{all \:y} f_{X\mid Y}(x \mid y) f_Y(y)
$$

Tags: mathematics statistics
<!--ID: 1671186732883-->
END