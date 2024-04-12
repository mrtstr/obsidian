## set
- non-ordered collection of objects in our underlying universe $\mathbb{U}$
- are only charaterized by their elemets
- can be defined by explicitly listing its elements $\{a_1, ..., a_n\}$ or based on a superset with a [[first order logic]] condition $\{ x\in S : condition(x) \}$


### spacial sets
$$
\begin{split}
[n] &= \{1, ..., n\} \\
[n]_0 &= \{0, ..., n\} \\
\end{split}
$$
![[universe#universe $ mathbb{U}$]]

![[empty set#empty set $ emptyset$]]

### set equality

$$
\begin{split}
S = T \Leftrightarrow \forall x: x \in S \leftrightarrow x \in T \\
\end{split}
$$

### subsets

$$
\begin{split}
S \subseteq T \Leftrightarrow \forall x: x \in S \rightarrow x \in T \\
\end{split}
$$

### finite set
- if a set $S$ has exactly $n$ elements ($|S| = n$) it's a finite set 

![[first order logic#first order logic]]

## set operations

![[union#union of set sets]]

![[intersection#intersection of set sets]]

![[difference of sets#difference of set sets]]

![[catesian product#catesian product]]

![[complement#complement of a set]]

## properties
#### the [[neutral element]] of [[union]] is the [[empty set]]
$$
\begin{split}
A \cup \emptyset 
&= \left\{ x \: : \: x \in A \lor x \in \emptyset \right\} \\
&= \left\{ x \: : \: x \in A  \right\} \qquad \text{(since the empty set is a subset of A)} \\
&= A \\
\end{split}
$$
#### the [[neutral element]] of [[intersection]] is the [[universe]]
$$
\begin{split}
A \cap \mathbb{U}
&= \left\{ x \: : \: x \in A \land x \in \mathbb{U} \right\} \\
&= \left\{ x \: : \: x \in A  \right\}  \qquad \text{(since A is a subset of U)} \\
&= A \\
\end{split}
$$
#### the [[empty set]] is dominant in the [[intersection]]
$$
\begin{split}
A \cap \emptyset 
&= \left\{ x \: : \: x \in A \land x \in \emptyset \right\} \\
&= \left\{ x \: : \: x \in \emptyset \right\}  \qquad \text{(since the empty set is a subset of A)} \\
&= \emptyset \\
\end{split}
$$
#### the [[universe]] is dominant in the [[union]]
$$
\begin{split}
A \cup \mathbb{U} 
&= \left\{ x \: : \: x \in A \lor x \in \mathbb{U} \right\} \\
&= \left\{ x \: : \: x \in \mathbb{U} \right\} \qquad \text{(since A is a subset of U)} \\
&= \emptyset \\
\end{split}
$$
#### the [[complement]] is its own [[inverse function|inverse]]
$$
\begin{split}
\left(A^c\right)^c &= \mathbb{U} \setminus A \\
&= \left\{x : x \in \mathbb{U} \land x \notin  A^c\right\} \\
&= \left\{x : x \in \mathbb{U} \land x \notin  \left\{x : x \in \mathbb{U} \land x \notin  A\right\}\right\} \\
&= \left\{x : x \in \mathbb{U} \land x \in  A\right\} \\
&= A \\
\end{split}
$$
#### [[union]] with own [[complement]]
$$
\begin{split}
A \cup A^c 
&= \left\{ x \: : \: x \in A \lor x \in A^c \right\} \\
&= \left\{ x \: : \: x \in A \lor x \in \left\{x : x \in \mathbb{U} \land x \notin  A\right\} \right\} \\
&= \left\{ x \: : \: x \in A \lor \left(x  \in \mathbb{U} \land x \notin  A \right) \right\} \\
&= \left\{ x \: : \: 
\left( x \in A \lor x \notin  A \right)
\land
\left(x  \in \mathbb{U} \lor x \notin  A \right) \right\} \\
&= \left\{ x \: : \: 
\mathbb{U}
\land
\mathbb{U} \right\} \\
&=\mathbb{U}
\end{split}
$$
#### [[intersection]] with own [[complement]]
$$
\begin{split}
A \cap A^c 
&= \left\{ x \: : \: x \in A \land x \in A^c \right\} \\
&= \left\{ x \: : \: x \in A \land x \in \left\{x : x \in \mathbb{U} \land x \notin  A\right\} \right\} \\
&= \left\{ x \: : \: x \in A \land x  \in \mathbb{U} \land x \notin  A  \right\} \\
&=\emptyset
\end{split}
$$

#### [[commutative|commutativity]] of the [[union]] and the [[intersection]]
- its [[commutative]] because $and$ and $or$ are [[commutative]]

![[commutative]]

$$
\begin{split}
A \cap B = B \cap A  \\
A \cup B = B \cup A  \\
\end{split}
$$

#### [[distributive|distributivity]] of the [[union]] and the [[intersection]]

![[distributive]]

$$
\begin{split}
(A \cap B) \cup C 
&= \left\{ x \: : \: \left(x \in A \land x \in B \right) \lor x \in C \right\} \\
&= \left\{ x \: : \: 
\left(x \in A \lor x \in C \right)
\land 
\left(x \in B \lor x \in C \right) 
\right\} \\
&=(A \cup C) \cap (B \cup C)
\end{split}
$$

$$
\begin{split}
(A \cup B) \cap C 
&= \left\{ x \: : \: \left(x \in A \lor x \in B \right) \land x \in C \right\} \\
&= \left\{ x \: : \: 
\left(x \in A \land x \in C \right)
\lor 
\left(x \in B \land x \in C \right) 
\right\} \\
&=(A \cap C) \cup (B \cap C)
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

#### absorbation rule
$$
\begin{split}
A \cup (A \cap B)
&= \left\{ x \: : \: x \in A \lor (x \in A \land x \in B) \right\} \\
&= \left\{ x \: : \: (x \in A \lor x \in A) \land (x \in A \lor x \in B) \right\} \\
&= \left\{ x \: : \: x \in A  \land (x \in A \lor x \in B) \right\} \\
&= \left\{ x \: : \: x \in A \right\} \qquad (\text{since } A \rightarrow A \lor B)  \\
&= A
\end{split}
$$

$$
\begin{split}
A \cap (A \cup B)
&= \left\{ x \: : \: x \in A \land (x \in A \lor x \in B) \right\} \\
&= \left\{ x \: : \: (x \in A \land x \in A) \lor (x \in A \land x \in B) \right\} \\
&= \left\{ x \: : \: x \in A  \lor (x \in A \land x \in B) \right\} \\
&= \left\{ x \: : \: x \in A \right\} \qquad (\text{since } A \rightarrow A \lor B)  \\
&= A
\end{split}
$$

# anki


START
Basic
absorbation rule with proof (2)
Back: 
#### absorbation rule
$$
\begin{split}
A \cup (A \cap B)
&= \left\{ x \: : \: x \in A \lor (x \in A \land x \in B) \right\} \\
&= \left\{ x \: : \: (x \in A \lor x \in A) \land (x \in A \lor x \in B) \right\} \\
&= \left\{ x \: : \: x \in A  \land (x \in A \lor x \in B) \right\} \\
&= \left\{ x \: : \: x \in A \right\} \qquad (\text{since } A \rightarrow A \lor B)  \\
&= A
\end{split}
$$

$$
\begin{split}
A \cap (A \cup B)
&= \left\{ x \: : \: x \in A \land (x \in A \lor x \in B) \right\} \\
&= \left\{ x \: : \: (x \in A \land x \in A) \lor (x \in A \land x \in B) \right\} \\
&= \left\{ x \: : \: x \in A  \lor (x \in A \land x \in B) \right\} \\
&= \left\{ x \: : \: x \in A \right\} \qquad (\text{since } A \rightarrow A \lor B)  \\
&= A
\end{split}
$$
____________
#### union of [[set|sets]] 
$$
A \cup B = \left\{ x \: : \: x \in A \lor x \in B \right\}
$$

#### intersection of [[set|sets]] 
$$
A \cap B = \left\{ x \: : \: x \in A \land x \in B \right\}
$$

#### difference of [[set|sets]] 
$$
A \setminus B = \left\{ x \: : \: x \in A \land x \notin B \right\}
$$
#### complement of a set
$$
\begin{split}
A^c &= \mathbb{U} \setminus A \\
&= \{x : x \in \mathbb{U} \land x \notin  A\} \\
\end{split}
$$
Tags: mathematics
<!--ID: 1712845470876-->
END


START
Basic
de morgan’s laws with proof (2)
Back: 
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
___________
#### union of [[set|sets]] 
$$
A \cup B = \left\{ x \: : \: x \in A \lor x \in B \right\}
$$

#### intersection of [[set|sets]] 
$$
A \cap B = \left\{ x \: : \: x \in A \land x \in B \right\}
$$

#### difference of [[set|sets]] 
$$
A \setminus B = \left\{ x \: : \: x \in A \land x \notin B \right\}
$$
#### complement of a set
$$
\begin{split}
A^c &= \mathbb{U} \setminus A \\
&= \{x : x \in \mathbb{U} \land x \notin  A\} \\
\end{split}
$$
Tags: mathematics
<!--ID: 1712845470882-->
END


START
Basic
proof [[commutative|commutativity]] and [[distributive|distributivity]] of the [[union]] and the [[intersection]] (4)

#### [[commutative]]
a operation is commutative if the following is true in general
$$
a \circ b = b \circ a
$$

#### [[distributive]]
two operations $\circ$ and $\times$ are distributive if the following is true in general
$$
(a \times b) \circ b = (a \circ c) \times (b \circ c)
$$
Back: 
#### [[commutative|commutativity]] of the [[union]] and the [[intersection]]
- its [[commutative]] because $and$ and $or$ are [[commutative]]


$$
\begin{split}
A \cap B = B \cap A  \\
A \cup B = B \cup A  \\
\end{split}
$$

#### [[distributive|distributivity]] of the [[union]] and the [[intersection]]


$$
\begin{split}
(A \cap B) \cup C 
&= \left\{ x \: : \: \left(x \in A \land x \in B \right) \lor x \in C \right\} \\
&= \left\{ x \: : \: 
\left(x \in A \lor x \in C \right)
\land 
\left(x \in B \lor x \in C \right) 
\right\} \\
&=(A \cup C) \cap (B \cup C)
\end{split}
$$

$$
\begin{split}
(A \cup B) \cap C 
&= \left\{ x \: : \: \left(x \in A \lor x \in B \right) \land x \in C \right\} \\
&= \left\{ x \: : \: 
\left(x \in A \land x \in C \right)
\lor 
\left(x \in B \land x \in C \right) 
\right\} \\
&=(A \cap C) \cup (B \cap C)
\end{split}
$$
__________________
#### union of [[set|sets]] 
$$
A \cup B = \left\{ x \: : \: x \in A \lor x \in B \right\}
$$

#### intersection of [[set|sets]] 
$$
A \cap B = \left\{ x \: : \: x \in A \land x \in B \right\}
$$

Tags: mathematics
<!--ID: 1712845470886-->
END

START
Basic
[[set|set theory]] (with proof)
- the [[complement]] is its own [[inverse function|inverse]]
- [[union]] with own [[complement]]
- [[intersection]] with own [[complement]]
Back: 
#### the [[complement]] is its own [[inverse function|inverse]]
$$
\begin{split}
\left(A^c\right)^c &= \mathbb{U} \setminus A \\
&= \left\{x : x \in \mathbb{U} \land x \notin  A^c\right\} \\
&= \left\{x : x \in \mathbb{U} \land x \notin  \left\{x : x \in \mathbb{U} \land x \notin  A\right\}\right\} \\
&= \left\{x : x \in \mathbb{U} \land x \in  A\right\} \\
&= A \\
\end{split}
$$
#### [[union]] with own [[complement]]
$$
\begin{split}
A \cup A^c 
&= \left\{ x \: : \: x \in A \lor x \in A^c \right\} \\
&= \left\{ x \: : \: x \in A \lor x \in \left\{x : x \in \mathbb{U} \land x \notin  A\right\} \right\} \\
&= \left\{ x \: : \: x \in A \lor \left(x  \in \mathbb{U} \land x \notin  A \right) \right\} \\
&= \left\{ x \: : \: 
\left( x \in A \lor x \notin  A \right)
\land
\left(x  \in \mathbb{U} \lor x \notin  A \right) \right\} \\
&= \left\{ x \: : \: 
\mathbb{U}
\land
\mathbb{U} \right\} \\
&=\mathbb{U}
\end{split}
$$
#### [[intersection]] with own [[complement]]
$$
\begin{split}
A \cap A^c 
&= \left\{ x \: : \: x \in A \land x \in A^c \right\} \\
&= \left\{ x \: : \: x \in A \land x \in \left\{x : x \in \mathbb{U} \land x \notin  A\right\} \right\} \\
&= \left\{ x \: : \: x \in A \land x  \in \mathbb{U} \land x \notin  A  \right\} \\
&=\emptyset
\end{split}
$$
____________________
#### union of [[set|sets]] 
$$
A \cup B = \left\{ x \: : \: x \in A \lor x \in B \right\}
$$

#### intersection of [[set|sets]] 
$$
A \cap B = \left\{ x \: : \: x \in A \land x \in B \right\}
$$

#### difference of [[set|sets]] 
$$
A \setminus B = \left\{ x \: : \: x \in A \land x \notin B \right\}
$$
#### complement of a set
$$
\begin{split}
A^c &= \mathbb{U} \setminus A \\
&= \{x : x \in \mathbb{U} \land x \notin  A\} \\
\end{split}
$$
Tags: mathematics
<!--ID: 1712845470889-->
END

START
Basic
dominant and [[neutral element]] for the [[union]] and [[intersection]]
Back: 
#### the [[neutral element]] of [[union]] is the [[empty set]]
$$
\begin{split}
A \cup \emptyset 
&= \left\{ x \: : \: x \in A \lor x \in \emptyset \right\} \\
&= \left\{ x \: : \: x \in A  \right\} \qquad \text{(since the empty set is a subset of A)} \\
&= A \\
\end{split}
$$
#### the [[neutral element]] of [[intersection]] is the [[universe]]
$$
\begin{split}
A \cap \mathbb{U}
&= \left\{ x \: : \: x \in A \land x \in \mathbb{U} \right\} \\
&= \left\{ x \: : \: x \in A  \right\}  \qquad \text{(since A is a subset of U)} \\
&= A \\
\end{split}
$$
#### the [[empty set]] is dominant in the [[intersection]]
$$
\begin{split}
A \cap \emptyset 
&= \left\{ x \: : \: x \in A \land x \in \emptyset \right\} \\
&= \left\{ x \: : \: x \in \emptyset \right\}  \qquad \text{(since the empty set is a subset of A)} \\
&= \emptyset \\
\end{split}
$$
#### the [[universe]] is dominant in the [[union]]
$$
\begin{split}
A \cup \mathbb{U} 
&= \left\{ x \: : \: x \in A \lor x \in \mathbb{U} \right\} \\
&= \left\{ x \: : \: x \in \mathbb{U} \right\} \qquad \text{(since A is a subset of U)} \\
&= \emptyset \\
\end{split}
$$
________________
#### union of [[set|sets]] 
$$
A \cup B = \left\{ x \: : \: x \in A \lor x \in B \right\}
$$

#### intersection of [[set|sets]] 
$$
A \cap B = \left\{ x \: : \: x \in A \land x \in B \right\}
$$



Tags: mathematics
<!--ID: 1712845470892-->
END



START
Basic
[[set]]
- concept
- how can it be defined
- special sets (3)
- defintion equality, subset and finite sets
- definition 
Back: 

- non-ordered collection of objects in our underlying universe $\mathbb{U}$
- are only charaterized by their elemets
- can be defined by explicitly listing its elements $\{a_1, ..., a_n\}$ or based on a superset with a [[first order logic]] condition $\{ x\in S : condition(x) \}$


### spacial sets

$$
\begin{split}
[n] &= \{1, ..., n\} \\
[n]_0 &= \{0, ..., n\} \\
\end{split}
$$
#### universe $\mathbb{U}$
- [[union]] of all relevant objects

#### empty set $\emptyset$ 
- [[set]] with not elements
- $\emptyset$ is a subset of every [[set]] (even of itself)

### set equality

$$
\begin{split}
S = T \Leftrightarrow \forall x: x \in S \leftrightarrow x \in T \\
\end{split}
$$

### subsets

$$
\begin{split}
S \subseteq T \Leftrightarrow \forall x: x \in S \rightarrow x \in T \\
\end{split}
$$

### finite set
- if a set $S$ has exactly $n$ elements ($|S| = n$) it's a finite set 

Tags: mathematics
<!--ID: 1712752812655-->
END


START
Basic
definitions of 5 basic [[set]] operations

Back: 
#### union of [[set|sets]] 
$$
A \cup B = \left\{ x \: : \: x \in A \lor x \in B \right\}
$$

#### intersection of [[set|sets]] 
$$
A \cap B = \left\{ x \: : \: x \in A \land x \in B \right\}
$$

#### difference of [[set|sets]] 
$$
A \setminus B = \left\{ x \: : \: x \in A \land x \notin B \right\}
$$
#### complement of a set
$$
\begin{split}
A^c &= \mathbb{U} \setminus A \\
&= \{x : x \in \mathbb{U} \land x \notin  A\} \\
\end{split}
$$

#### catesian product
$$
\bigtimes_{i=1}^n A_1 = \left\{(a_1, ..., a_n)\: : \: \forall i \in [n]: a_i \in A_i \right\}
$$
- the [[catesian product]] of $n$ [[set|sets]] is a [[set]] of [[n tuple|n tuples]] with a [[cardinality]] of $\prod_{i \in [n]} |A_i|$  

Tags: mathematics
<!--ID: 1712752812659-->
END