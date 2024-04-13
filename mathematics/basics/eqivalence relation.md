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
### properties
#### $a \sim b \Leftrightarrow [a]_\sim = [b]_\sim$
$$
\begin{split}
c \in [a]_{\sim} &\Rightarrow c \sim a \sim b \\
&\Rightarrow c \sim b \qquad \text{(transitiv)} \\
&\Rightarrow c \in [b]_\sim \\
\end{split}
$$
(the other direction has to be true too because [[eqivalence relation]] are [[symmetric]])

#### $a \sim b \Leftrightarrow [a]_\sim \cap [b]_\sim \neq \emptyset$
$$
\begin{split}
a \sim b 
&\Rightarrow a \in [a]_\sim \qquad &\text{(reflexiv)} \\
&\Rightarrow a \in [b]_\sim  \\
&\Rightarrow a \in [a]_\sim \cap [b]_\sim \\
\end{split}
$$

$$
\begin{split}
[a]_\sim \cap [b]_\sim \neq \emptyset
&\Rightarrow \exists a: a \in [b]_\sim \\
&\Rightarrow a \sim b \\
\end{split}
$$

#### every [[eqivalence relation]] $\sim$ induces a [[partition]]

![[equivalence class#equivalence class]]

![[partition#partition of a set]]

- if a [[set]] $A$ is split into [[equivalence class|equivalence classes]] every element has to be in a [[equivalence class]] and the [[equivalence class|equivalence classes]] have to be [[disjunct]]
- example: $\sim = \{(a, b): a, b \in \mathbb{Z}: a \equiv b \: mod \: 3\}$ and $A = [8]_0$
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

START
Basic
proof the following propertie of [[eqivalence relation]]
$a \sim b \Leftrightarrow [a]_\sim = [b]_\sim$
Back: 

$$
\begin{split}
c \in [a]_{\sim} &\Rightarrow c \sim a \sim b \\
&\Rightarrow c \sim b \qquad \text{(transitiv)} \\
&\Rightarrow c \in [b]_\sim \\
\end{split}
$$
(the other direction follows from [[symmetric|symmetrie]])


__________________
#### equivalence class
- given a [[eqivalence relation]] $\sim$ and a [[set]] $A$
- the [[equivalence class]] $[a]_\sim$ is defined as follows
$$
[a]_\sim = \{b \in A : a \sim b\}
$$

#### eqivalence relation
- a [[relation]] $\sim$ that is [[symmetric]], [[reflexive]] and [[transitive]] is called equivalence relation
- $a \sim b$ is another notation for $(a, b) \in \sim$

#### reflexive
- a [[relation]] $R$ on a [[set]] $B$ is [[reflexive]] if
$$
\forall a \in A: (a,a) \in R
$$

#### symmetric
- a [[relation]] $R$ on a [[set]] $B$ is [[symmetric]] if
$$
\forall a, b \in A: (a,b) \in R \rightarrow (b, a) \in R
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
<!--ID: 1713022670141-->
END

START
Basic
proof the following propertie of [[eqivalence relation]]
$a \sim b \Leftrightarrow [a]_\sim \cap [b]_\sim \neq \emptyset$

Back: 

$$
\begin{split}
a \sim b 
&\Rightarrow a \in [a]_\sim \qquad &\text{(reflexiv)} \\
&\Rightarrow a \in [b]_\sim  \\
&\Rightarrow a \in [a]_\sim \cap [b]_\sim \\
\end{split}
$$

$$
\begin{split}
[a]_\sim \cap [b]_\sim \neq \emptyset
&\Rightarrow \exists a: a \in [b]_\sim \\
&\Rightarrow a \sim b \\
\end{split}
$$

__________________

#### equivalence class
- given a [[eqivalence relation]] $\sim$ and a [[set]] $A$
- the [[equivalence class]] $[a]_\sim$ is defined as follows
$$
[a]_\sim = \{b \in A : a \sim b\}
$$


#### eqivalence relation
- a [[relation]] $\sim$ that is [[symmetric]], [[reflexive]] and [[transitive]] is called equivalence relation
- $a \sim b$ is another notation for $(a, b) \in \sim$

#### reflexive
- a [[relation]] $R$ on a [[set]] $B$ is [[reflexive]] if
$$
\forall a \in A: (a,a) \in R
$$

#### symmetric
- a [[relation]] $R$ on a [[set]] $B$ is [[symmetric]] if
$$
\forall a, b \in A: (a,b) \in R \rightarrow (b, a) \in R
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
<!--ID: 1713022670147-->
END


START
Basic
relationship of [[equivalence class]] and [[partition]] with example

Back: 
#### every [[eqivalence relation]] $\sim$ induces a [[partition]]
- if a [[set]] $A$ is split into [[equivalence class|equivalence classes]] every element has to be in a [[equivalence class]] and the [[equivalence class|equivalence classes]] have to be [[disjunct]]
- example: $\sim = \{(a, b): a, b \in \mathbb{Z}: a \equiv b \: mod \: 3\}$ and $A = [8]_0$

##### equivalence class
- given a [[eqivalence relation]] $\sim$ and a [[set]] $A$
- the [[equivalence class]] $[a]_\sim$ is defined as follows
$$
[a]_\sim = \{b \in A : a \sim b\}
$$
#### partition of a [[set]]
Let $A$ be a [[set]] and $A_1,..., A_n \subseteq A$ subsets of $A$. $A_1,..., A_n$ are a [[partition]] of $A$ if the following is true:
1) $\bigcup_{i \in [n]} A_i = A$  
2) $A_i \cap A_j = \emptyset \: \forall i \neq j \in [n]$  
__________________



#### eqivalence relation
- a [[relation]] $\sim$ that is [[symmetric]], [[reflexive]] and [[transitive]] is called equivalence relation
- $a \sim b$ is another notation for $(a, b) \in \sim$

#### reflexive
- a [[relation]] $R$ on a [[set]] $B$ is [[reflexive]] if
$$
\forall a \in A: (a,a) \in R
$$

#### symmetric
- a [[relation]] $R$ on a [[set]] $B$ is [[symmetric]] if
$$
\forall a, b \in A: (a,b) \in R \rightarrow (b, a) \in R
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
<!--ID: 1713022670152-->
END