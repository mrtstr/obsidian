### rational number
Rational Numbers: Quotients of [[integer|integers]]
$$
\mathbb{Q} = \left\{\frac{m}{n} | m,n \in \mathbb{Z}, n \neq0 \right\}
$$
### rational number rigoros definition
problem with naive definition: we want to define the following as eqivalent
$$
\frac{a}{b} = \frac{a \cdot k}{b \cdot k}
$$
1) we define a [[relation]] $M = \mathbb{Z} \times \mathbb{Z}^*$ 
2) we define a [[equivalence relation]] $\sim$ on $M$
$$
\sim = \left\{\left((a, b), (a', b')\right): (a, b), (a', b') \in M: a'b = ab' \right\}
$$
3) we define the [[rational numbers]] $\mathbb{Q}$ as the [[equivalence class|equivalence classes]] $\sim$ on $M$

#### [[addition]]
$$
\frac{a}{b} + \frac{a'}{b'} = \frac{a'b + b'a}{b'b} 
$$

#### [[multiplication]]
$$
\frac{a}{b} \cdot \frac{a'}{b'} = \frac{a'a}{b'b} 
$$
# ------------------
![[relation#relation]]

![[equivalence relation#eqivalence relation]]

![[equivalence class#equivalence class]]


# anki

START
Basic
rigorous definition of the [[rational numbers]]
Back: 
### rational number
Rational Numbers: Quotients of [[integer|integers]]
$$
\mathbb{Q} = \left\{\frac{m}{n} | m,n \in \mathbb{Z}, n \neq0 \right\}
$$
### rational number rigoros definition
problem with naive definition: we want to define the following as eqivalent
$$
\frac{a}{b} = \frac{a \cdot k}{b \cdot k}
$$
1) we define a [[relation]] $M = \mathbb{Z} \times \mathbb{Z}^*$ 
2) we define a [[equivalence relation]] $\sim$ on $M$
$$
\sim = \left\{\left((a, b), (a', b')\right): (a, b), (a', b') \in M: a'b = ab' \right\}
$$
3) we define the [[rational numbers]] $\mathbb{Q}$ as the [[equivalence class|equivalence classes]] $\sim$ on $M$

#### [[addition]]
$$
\frac{a}{b} + \frac{a'}{b'} = \frac{a'b + b'a}{b'b} 
$$

#### [[multiplication]]
$$
\frac{a}{b} \cdot \frac{a'}{b'} = \frac{a'a}{b'b} 
$$

__________________
#### equivalence class
- given a [[equivalence relation]] $\sim$ and a [[set]] $A$
- the [[equivalence class]] $[a]_\sim$ is defined as follows
$$
[a]_\sim = \{b \in A : a \sim b\}
$$

#### eqivalence relation
- a [[relation]] $\sim$ that is [[symmetric]], [[reflexive]] and [[transitive]] is called equivalence relation
- $a \sim b$ is another notation for $(a, b) \in \sim$


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
<!--ID: 1713078133336-->
END