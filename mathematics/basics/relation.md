## relation
- generalized [[function]]
- a **[[relation]]** on a [[set]] $A$ is a [[set#subsets|subset]] of the [[catesian product]] $A \times A$ 
- a **binary [[relation]]** from a [[set]] $A$ to a [[set]] $B$ if it's a [[set#subsets|subset]] of [[catesian product]] $A \times B$ 
- **n-ary [[relation]]** if $A_1, ..., A_n$ relations is a [[set#subsets|subset]] of the [[catesian product]] $A_1 \times ... \times A_n$ 
- $a$ is related to $b$ by a [[relation]] $R$ is the following is true $aRb \Leftrightarrow (a, b) \in R$

![[catesian product#catesian product]]

## [[relation]] and [[function]]
- every [[function]] $f: A \rightarrow B$ is a [[relation]] from $A$ to $B$ where the [[relation]] is the [[function#grapf of a function|graph of f]] $graph(f) \subseteq A \times B$ 
- not every [[relation]] is the [[function#grapf of a function|graph]] of a [[function]]: 
	- $\{(a, b_1), (a, b_2)\}$ is a [[relation]] but a garpf of a [[function]]
	- $A = \{a_1, a_2\}$ and $B = \{b_1\}$ $R=\{(a_1, b_1)\}$ is a [[relation]] but not a [[function]]

![[function#definition function]]

## properties
![[reflexive#reflexive]]

![[symmetric#symmetric]]

![[antisymmetric#antisymmetric]]

![[asymmetric#asymmetric]]

![[transitive#transitive]]

![[eqivalence relation#eqivalence relation]]

# anki
START
Basic
definition: [[relation]]
- on a [[set]]
- from a [[set]] to a [[set]]
- on multiple [[set|sets]]

Back: 
### relation
- a **[[relation]]** on a [[set]] $A$ is a [[set#subsets|subset]] of the [[catesian product]] $A \times A$ 
- a **binary [[relation]]** from a [[set]] $A$ to a [[set]] $B$ if it's a [[set#subsets|subset]] of [[catesian product]] $A \times B$ 
- **n-ary [[relation]]** if $A_1, ..., A_n$ relations is a [[set#subsets|subset]] of the [[catesian product]] $A_1 \times ... \times A_n$ 
- $a$ is related to $b$ by a [[relation]] $R$ is the following is true $aRb \Leftrightarrow (a, b) \in R$
__________________
### catesian product
$$
\bigtimes_{i=1}^n A_1 = \left\{(a_1, ..., a_n)\: : \: \forall i \in [n]: a_i \in A_i \right\}
$$
- the [[catesian product]] of $n$ [[set|sets]] is a [[set]] of [[n tuple|n tuples]] with a [[cardinality]] of $\prod_{i \in [n]} |A_i|$  


### function
- a [[function]] $f$ is map of elements from one [[set]] $A$ to the elements of another [[set]] $B$ such that all elements of $A$ are ampped to exactly one element from $B$
- the [[set]] $A$ is called the **domain** and the [[set]] $B$ is called the **co-domain**
$$
\begin{split}
&f: A \rightarrow B \\
&\forall a \in A: \exists b \in B: f(a) = b
\end{split}
$$
- for every subset of $C\subseteq A$ we define a [[set]] $f(C)$ as follows
$$
\begin{split}
f(C) = \{y \in B: \exists c \in C: f(c) = b\}
\end{split}
$$
#### image of a [[function]]
- if $x \in A$ then $y=f(x) \in B$ is the **image** of $x$ and $x$ is the **preimage** of $y$
$$
\forall x \in A
$$
- the **image of function** is a [[set]] containing the images for all elements of $A$ is a subset of $B$
$$
\begin{split}
im(f) 
&= f(A) \\
&= \{f(a): a \in A\} \\
&\subseteq B
\end{split}
$$
#### grapf of a [[function]]
- the grapf of a [[function]] is defined as a [[set]] of [[n tuple|pairs]] of elements from the domain with treir images
$$
\begin{split}
graph(f) 
&= f(A) \\
&= \{(a,b): a \in A, b=f(a) \in im(f) \subseteq B\} \\
\end{split}
$$
- the [[cardinality]] of the graph of a [[function]] is equal to the [[cardinality]] of its domain
$$
\begin{split}
|graph(f)| = |A| 
\end{split}
$$

Tags: mathematics
<!--ID: 1712933490539-->
END


START
Basic

proof that
- every [[function]] defines a binary [[relation]]
- not every binary [[relation]] defines a [[function]]

Back: 
### [[relation]] and [[function]]
- every [[function]] $f: A \rightarrow B$ is a [[relation]] from $A$ to $B$ where the [[relation]] is the [[function#grapf of a function|graph of f]] $graph(f) \subseteq A \times B$ 
- not every [[relation]] is the [[function#grapf of a function|graph]] of a [[function]]: 
	- $\{(a, b_1), (a, b_2)\}$ is a [[relation]] but a garph of a [[function]]
	- $A = \{a_1, a_2\}$ and $B = \{b_1\}$ $R=\{(a_1, b_1)\}$ is a [[relation]] but not a [[function]]
__________________
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


### function
- a [[function]] $f$ is map of elements from one [[set]] $A$ to the elements of another [[set]] $B$ such that all elements of $A$ are ampped to exactly one element from $B$
- the [[set]] $A$ is called the **domain** and the [[set]] $B$ is called the **co-domain**
$$
\begin{split}
&f: A \rightarrow B \\
&\forall a \in A: \exists b \in B: f(a) = b
\end{split}
$$
- for every subset of $C\subseteq A$ we define a [[set]] $f(C)$ as follows
$$
\begin{split}
f(C) = \{y \in B: \exists c \in C: f(c) = b\}
\end{split}
$$
#### image of a [[function]]
- if $x \in A$ then $y=f(x) \in B$ is the **image** of $x$ and $x$ is the **preimage** of $y$
$$
\forall x \in A
$$
- the **image of function** is a [[set]] containing the images for all elements of $A$ is a subset of $B$
$$
\begin{split}
im(f) 
&= f(A) \\
&= \{f(a): a \in A\} \\
&\subseteq B
\end{split}
$$
#### grapf of a [[function]]
- the grapf of a [[function]] is defined as a [[set]] of [[n tuple|pairs]] of elements from the domain with treir images
$$
\begin{split}
graph(f) 
&= f(A) \\
&= \{(a,b): a \in A, b=f(a) \in im(f) \subseteq B\} \\
\end{split}
$$
- the [[cardinality]] of the graph of a [[function]] is equal to the [[cardinality]] of its domain
$$
\begin{split}
|graph(f)| = |A| 
\end{split}
$$

Tags: mathematics
<!--ID: 1712933490545-->
END



START
Basic
definitions for
- [[reflexive]]
- [[symmetric]]
- [[antisymmetric]]
- [[asymmetric]]
- [[transitive]]

Back: 
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


### antisymmetric
- a [[relation]] $R$ on a [[set]] $B$ is [[antisymmetric]] if
$$
\forall a, b \in A: (a,b) \in R \land (b,a) \in R \rightarrow a =b
$$


### asymmetric
- a [[relation]] $R$ on a [[set]] $B$ is [[asymmetric]] if
$$
\forall a, b \in A: (a,b) \in R  \rightarrow (b,a) \notin R
$$


### transitive
- a [[relation]] $R$ on a [[set]] $B$ is [[transitive]] if
$$
\forall a, b, c \in A: (a,b) \in R \land (b,c) \in R \rightarrow (a,c) \in R
$$



__________________
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
<!--ID: 1712933490547-->
END



START
Basic
- proof that [[asymmetric]] $\Rightarrow$ [[antisymmetric]] [[relation|relations]]?
- proof that [[antisymmetric]] $\neq$ [[asymmetric]] [[relation|relations]]?
- when is it equivalent?
Back: 
#### [[asymmetric]] $\Rightarrow$ [[antisymmetric]] [[relation|relations]]?
$$
\begin{split}
&(a,b) \in R  \rightarrow (b,a) \notin R \\
\Rightarrow& (a,b) \in R \land (b,a) \in R = F \\
\Rightarrow& (a,b) \in R \land (b,a) \in R \rightarrow a = T \\
\end{split}
$$
#### [[antisymmetric]] $\neq$ [[asymmetric]] [[relation|relations]]?
- $R = \{(a,b), (b,a), (a,a)\}$ is [[antisymmetric]] but not [[asymmetric]]

#### when is it equivalent?
- if $\forall a \in A: (a,a) \notin R$ [[antisymmetric]] and [[asymmetric]] are eqiuivalent

### antisymmetric
- a [[relation]] $R$ on a [[set]] $B$ is [[antisymmetric]] if
$$
\forall a, b \in A: (a,b) \in R \land (b,a) \in R \rightarrow a =b
$$


### asymmetric
- a [[relation]] $R$ on a [[set]] $B$ is [[asymmetric]] if
$$
\forall a, b \in A: (a,b) \in R  \rightarrow (b,a) \notin R
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
<!--ID: 1712933490551-->
END


START
Basic
a [[relation]] with the following properties is called?

$$
\forall a \in A: (a,a) \in R
$$
$$
\forall y \in B: \exists x: (x,y) \in R
$$

$$
\forall a, b, c \in A: (a,b) \in R \land (b,c) \in R \rightarrow (a,c) \in R
$$

$$
\forall x_1, x_2 \in A: (x_1, x_2) \in R \Rightarrow x_1=x_2
$$

$$
\forall a, b \in A: (a,b) \in R \rightarrow (b, a) \in R
$$
Back: 
#### [[reflexive]]
$$
\forall a \in A: (a,a) \in R
$$
#### [[surjective]]
$$
\forall y \in B: \exists x: (x,y) \in R
$$
#### [[transitive]]
$$
\forall a, b, c \in A: (a,b) \in R \land (b,c) \in R \rightarrow (a,c) \in R
$$
#### [[injective]]
$$
\forall x_1, x_2 \in A: (x_1, x_2) \in R \Rightarrow x_1=x_2
$$
#### [[symmetric]]
$$
\forall a, b \in A: (a,b) \in R \rightarrow (b, a) \in R
$$

Tags: mathematics
<!--ID: 1712994707341-->
END