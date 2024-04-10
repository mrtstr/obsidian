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

![[first order logic]]

## set operations

![[union#union of set sets]]

![[intersection of sets#intersection of set sets]]

![[difference of sets#difference of set sets]]

![[catesian product#catesian product]]

![[complement of a set#complement of a set]]

# anki
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

#### catesian product
$$
\bigtimes_{i=1}^n A_1 = \left\{(a_1, ..., a_n)\: : \: \forall i \in [n]: a_i \in A_i \right\}
$$
- the [[cartesian product]] of $n$ [[set|sets]] is a [[set]] of [[n tuple|n tuples]] with a [[cardinality]] of $\prod_{i \in [n]} |A_i|$  

#### complement of a set
$$
\begin{split}
A^c &= \mathbb{U} \setminus A \\
&= \{x : x \in \mathbb{U} \land x \notin  A\} \\
\end{split}
$$

Tags: mathematics
<!--ID: 1712752812659-->
END