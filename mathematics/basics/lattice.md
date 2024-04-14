#### lattice
- a [[ordering|partially ordered]] [[set]] $(A, \leq)$ is a **[[lattice]]** if it has a [[infimum]] $a \in A$ and a [[supremum]] $b \in A$

#### comlete lattice
- a [[lattice]] is complete if every subset $A' \subseteq A$ the [[infimum]] and [[supremum]] exists

# ----------------------
![[supremum#supremum]]

![[infimum#infimum]]


# anki

START
Basic
- definition [[lattice]]
- definition complete [[lattice]]
Back: 
#### lattice
- a [[ordering|partially ordered]] [[set]] $(A, \leq)$ is a **[[lattice]]** if it has a [[infimum]] $a \in A$ and a [[supremum]] $b \in A$

#### comlete lattice
- a [[lattice]] is complete if every subset $A' \subseteq A$ the [[infimum]] and [[supremum]] exists

____________________________
#### supremum
- least [[upper bound]] of a [[set]] = [[supremum]] = join
- given a [[set]] $A$ and a [[ordering|partial ordering]] $\leq$ and a subset of $A$ $A' \subseteq A$
- an element $b \in A$ is an **[[supremum]]** of $A'$ if it is the [[minimum]] of the [[set]] of [[upper bound|upper bounds]] $U$
$$
U = \{b \in A : \forall a \in A': a \leq b\}
$$
$$
b = min (U)
$$

#### infimum
- greatest [[lower bound]] of a [[set]] = infimum = meet
- given a [[set]] $A$ and a [[ordering|partial ordering]] $\leq$ and a subset of $A$ $A' \subseteq A$
- an element $b \in A$ is an **[[infimum]]** of $A'$ if it is the [[maximum]] of the [[set]] of [[lower bound|lower bounds]] $L$
$$
L = \{b \in A : \forall a \in A': b \leq a\}
$$
$$
b = max (U)
$$

#### upper bound
- given a [[set]] $A$ and a [[ordering|partial ordering]] $\leq$ and a subset of $A$ $A' \subseteq A$
- an element $b \in A$ is an **upper bound** of $A'$ if it satisfies the following condtion
$$
\forall s \in A': a \leq b
$$
- note $b$ does not have to be $\in A'$



#### lower bound
- given a [[set]] $A$ and a [[ordering|partial ordering]] $\leq$ and a subset of $A$ $A' \subseteq A$
- an element $b \in A$ is an **lower bound** of $A'$ if it satisfies the following condtion

$$
\forall s \in A': b \leq a
$$
- note $b$ does not have to be $\in A'$

#### maximal element or [[maximum]]
- given a [[set]] $A$ and a [[ordering|partial ordering]] $\leq$ 
- an element $b \in A$ is a **maximal element** if it satisfies the following condtion
$$
\forall a \in A: a \leq b
$$

#### minimal element or [[minimum]]
- given a [[set]] $A$ and a [[ordering|partial ordering]] $\leq$ 
- an element $b \in A$ is a **minimal element** if it satisfies the following condtion
$$
\forall a \in A: b \leq a
$$

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

Tags: mathematics
<!--ID: 1713085055859-->
END