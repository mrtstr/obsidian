### eqivalence [[relation]]
- a relation $\sim$ that is [[symmetric]], [[reflexive]] and [[transitive]] is called equivalence relation
- $a \sim b$ is another notation for $(a, b) \in \sim$


### examples
#### equality $=$ on $\mathbb{R}$
$$
\{(a,b): a,b \in A: a = b\}
$$
- [[symmetric]] because $a = b \Leftrightarrow b=a$
- [[transitive]] because $a=b \land b=c \Leftrightarrow a=c$
- [[reflexive]] because $a=a$

#### all elements related
$$
\{(a,b): \forall a,b \in A\}
$$

#### [[floor function]] induced [[eqivalence relation]]

$$
\{(a,b): \forall a,b \in \mathbb{R}: \lfloor a \rfloor = \lfloor b \rfloor\}
$$
#### absolute function $|\cdot|: \mathbb{R} \rightarrow \mathbb{R}_{\geq 0}$ induces [[eqivalence relation]]

$$
\{(a,b): \forall a,b \in \mathbb{R}: |a|  =  |b| \}
$$

# -----------------------
![[relation#relation]]


![[reflexive#reflexive]]

![[symmetric#symmetric]]

![[transitive#transitive]]

# anki

START
Basic
[[eqivalence relation]]
- definition
- 4 examples
Back: 
### eqivalence relation
- a [[relation]] $\sim$ that is [[symmetric]], [[reflexive]] and [[transitive]] is called equivalence relation
- $a \sim b$ is another notation for $(a, b) \in \sim$

### examples
#### equality $=$ on $\mathbb{R}$
$$
\{(a,b): a,b \in A: a = b\}
$$
- [[symmetric]] because $a = b \Leftrightarrow b=a$
- [[transitive]] because $a=b \land b=c \Leftrightarrow a=c$
- [[reflexive]] because $a=a$

#### all elements related
$$
\{(a,b): \forall a,b \in A\}
$$

#### [[floor function]] induced [[eqivalence relation]]

$$
\{(a,b): \forall a,b \in \mathbb{R}: \lfloor a \rfloor = \lfloor b \rfloor\}
$$
### absolute function $|\cdot|: \mathbb{R} \rightarrow \mathbb{R}_{\geq 0}$ induces [[eqivalence relation]]

$$
\{(a,b): \forall a,b \in \mathbb{R}: |a|  =  |b| \}
$$

__________________
### reflexive
- a [[relation]] $R$ on a [[set]] $B$ is [[reflexive]] if
$$
\forall a \in A: (a,a) \in R
$$

### symmetric
- a [[relation]] $R$ on a [[set]] $B$ is [[symmetric]] if
$$
\forall a, b \in A: (a,b) \in R \rightarrow (b, a) \in R
$$


### transitive
- a [[relation]] $R$ on a [[set]] $B$ is [[transitive]] if
$$
\forall a, b, c \in A: (a,b) \in R \land (b,c) \in R \rightarrow (a,c) \in R
$$



### relation
- a **[[relation]]** on a [[set]] $A$ is a [[set#subsets|subset]] of the [[catesian product]] $A \times A$ 
- a **binary [[relation]]** from a [[set]] $A$ to a [[set]] $B$ if it's a [[set#subsets|subset]] of [[catesian product]] $A \times B$ 
- **n-ary [[relation]]** if $A_1, ..., A_n$ relations is a [[set#subsets|subset]] of the [[catesian product]] $A_1 \times ... \times A_n$ 
- $a$ is related to $b$ by a [[relation]] $R$ is the following is true $aRb \Leftrightarrow (a, b) \in R$

### catesian product
$$
\bigtimes_{i=1}^n A_1 = \left\{(a_1, ..., a_n)\: : \: \forall i \in [n]: a_i \in A_i \right\}
$$
- the [[catesian product]] of $n$ [[set|sets]] is a [[set]] of [[n tuple|n tuples]] with a [[cardinality]] of $\prod_{i \in [n]} |A_i|$  

Tags: mathematics
<!--ID: 1712941205020-->
END