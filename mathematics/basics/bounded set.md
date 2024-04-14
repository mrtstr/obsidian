#### bounded set
- a [[set]] $S$ is bounded if an [[upper bound]] and an [[lower bound]] exists


![[upper bound#upper bound]]

![[lower bound#lower bound]]







# anki

START
Basic
definition [[bounded set]]
Back: 
bounded set
- a [[set]] $S$ is bounded if an [[upper bound]] and an [[lower bound]] exists

#### upper bound
- given a [[set]] $A$ and a [[ordering|partial ordering]] $\leq$ and a subset of $A$ $A' \subseteq A$
- an element $b \in A$ is an **upper bound** of $A'$ if it satisfies the following condtion
$$
\forall s \in A': b \geq a
$$
- note $b$ does not have to be $\in A'$

#### lower bound
- given a [[set]] $A$ and a [[ordering|partial ordering]] $\leq$ and a subset of $A$ $A' \subseteq A$
- an element $b \in A$ is an **lower bound** of $A'$ if it satisfies the following condtion

$$
\forall s \in A': b \leq a
$$
- note $b$ does not have to be $\in A'$
____________________
#### partial ordering
- a [[relation]] $R$ on a [[set]] $A$ that is [[reflexive]], [[antisymmetric]] and [[transitive]]
- a [[set]] with a partial [[ordering]] is called partially ordered or **poset**

#### reflexive
- a [[relation]] $R$ on a [[set]] $B$ is [[reflexive]] if
$$
\forall a \in A: (a,a) \in R
$$

#### antisymmetric
- a [[relation]] $R$ on a [[set]] $B$ is [[antisymmetric]] if
$$
\forall a, b \in A: (a,b) \in R \land (b,a) \in R \rightarrow a =b
$$

#### transitive
- a [[relation]] $R$ on a [[set]] $B$ is [[transitive]] if
$$
\forall a, b, c \in A: (a,b) \in R \land (b,c) \in R \rightarrow (a,c) \in R
$$

#### relation
- a **[[relation]]** on a [[set]] $A$ is a [[set#subsets|subset]] of the [[catesian product]] $A \times A$ 
- a **binary [[relation]]** from a [[set]] $A$ to a [[set]] $B$ if it's a [[set#subsets|subset]] of [[catesian product]] $A \times B$ 
- **n-ary [[relation]]** if $A_1, ..., A_n$ relations is a [[set#subsets|subset]] of the [[catesian product]] $A_1 \times ... \times A_n$ 
- $a$ is related to $b$ by a [[relation]] $R$ is the following is true $aRb \Leftrightarrow (a, b) \in R$

#### catesian product
$$
\bigtimes_{i=1}^n A_1 = \left\{(a_1, ..., a_n)\: : \: \forall i \in [n]: a_i \in A_i \right\}
$$
- the [[catesian product]] of $n$ [[set|sets]] is a [[set]] of [[n tuple|n tuples]] with a [[cardinality]] of $\prod_{i \in [n]} |A_i|$  



Tags: mathematics
<!--ID: 1685349599102-->
END