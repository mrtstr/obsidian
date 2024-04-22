### partial ordering
- a [[relation]] $R$ on a [[set]] $A$ that is [[reflexive]], [[antisymmetric]] and [[transitive]]
- a [[set]] with a partial [[ordering]] is called partially ordered or **poset**

### further definitions
#### coparable elements
- $a, b \in A$ are **comparable** if $(a, b) \in R \lor (b, a) \in R$

#### total orderin
- a [[ordering]] is called a **total [[ordering]]** if alle elements pairs are comparable
$$
\forall a,b \in A: (a,b) \in R \lor (b, a) \in R
$$

### the [[maximum]] of a ordered [[set]] is uniqe
- let $(A, \leq)$ be a ordered [[set]] and let $m \in A$ be a [[maximum]] of $A$ 
- $m$ is unique
#### proof
let $(A, \leq)$ be a ordered [[set]] and let $m_1, m_2 \in A$ both be [[maximum|maxima]] of $A$ 
$$
\begin{split}
m_1 \text{ is a maximum } &\Rightarrow m_2 \leq m_1 \\
m_2 \text{ is a maximum } &\Rightarrow m_1 \leq m_2 \\
m_2 \leq m_1 \land m_1 \leq m_2 &\Rightarrow m_1 = m_2 \quad \text(antisymmetry)
\end{split}
$$

### properties of ordered sets
![[maximum#maximal element or maximum]]

![[minimum#minimal element or minimum]]


![[upper bound#upper bound]]

![[lower bound#lower bound]]

![[supremum#supremum]]

![[infimum#infimum]]



# ----------------------
![[reflexive#reflexive]]

![[antisymmetric#antisymmetric]]

![[transitive#transitive]]


# anki
START
Basic
definitions
- partial ordering
- total orderin
Back: 
#### partial ordering
- a [[relation]] $R$ on a [[set]] $A$ that is [[reflexive]], [[antisymmetric]] and [[transitive]]
- a [[set]] with a partial [[ordering]] is called partially ordered or **poset**


#### coparable elements
- $a, b \in A$ are **comparable** if $(a, b) \in R \lor (b, a) \in R$

#### total orderin
- a [[ordering]] is called a **total [[ordering]]** if alle elements pairs are comparable
$$
\forall a,b \in A: (a,b) \in R \lor (b, a) \in R
$$

____________________________

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
<!--ID: 1713084947411-->
END



START
Basic
- definition [[maximum]]
- definition [[upper bound]]
- difference [[maximum]] and [[upper bound]]
- when are they equivalent
Back: 
difference:
- the [[maximum]] of a [[set]] has to be an elemente of the [[set]] but a [[upper bound]] does not
- a [[upper bound]] of a [[set]] $A$ that is also an element of the $A$ is a [[maximum]]

#### maximal element or [[maximum]]
- given a [[set]] $A$ and a [[ordering|partial ordering]] $\leq$ 
- an element $b \in A$ is a **maximal element** if it satisfies the following condtion
$$
\forall a \in A: a \leq b
$$
#### upper bound
- given a [[set]] $A$ and a [[ordering|partial ordering]] $\leq$ and a subset of $A$ $A' \subseteq A$
- an element $b \in A$ is an **upper bound** of $A'$ if it satisfies the following condtion
$$
\forall s \in A': a \leq b
$$
- note $b$ does not have to be $\in A'$

#### minimal element or [[minimum]]
- given a [[set]] $A$ and a [[ordering|partial ordering]] $\leq$ 
- an element $b \in A$ is a **minimal element** if it satisfies the following condtion
$$
\forall a \in A: b \leq a
$$

#### lower bound
- given a [[set]] $A$ and a [[ordering|partial ordering]] $\leq$ and a subset of $A$ $A' \subseteq A$
- an element $b \in A$ is an **lower bound** of $A'$ if it satisfies the following condtion

$$
\forall s \in A': b \leq a
$$
- note $b$ does not have to be $\in A'$

____________________________
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
<!--ID: 1713084947417-->
END


START
Basic
- definition meet
- definition [[upper bound]]
- when are they equivalent
Back: 
they are eqivalent if there is only one upper bound

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

____________________________
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
<!--ID: 1713084947422-->
END


START
Basic
proof that the [[maximum]] of a ordered [[set]] is uniqe
Back: 
- let $(A, \leq)$ be a ordered [[set]] and let $m \in A$ be a [[maximum]] of $A$ 
- $m$ is unique
#### proof
let $(A, \leq)$ be a ordered [[set]] and let $m_1, m_2 \in A$ both be [[maximum|maxima]] of $A$ 
$$
\begin{split}
m_1 \text{ is a maximum } &\Rightarrow m_2 \leq m_1 \\
m_2 \text{ is a maximum } &\Rightarrow m_1 \leq m_2 \\
m_2 \leq m_1 \land m_1 \leq m_2 &\Rightarrow m_1 = m_2 \quad \text(antisymmetry)
\end{split}
$$

____________________________
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
<!--ID: 1713770310244-->
END