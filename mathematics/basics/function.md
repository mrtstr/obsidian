## function
### definition function
- a [[function]] $f$ is map of elements from one [[set]] $A$ to the elements of another [[set]] $B$ such that all elements of $A$ are mapped to exactly one element from $B$
- the [[set]] $A$ is called the **domain** and the [[set]] $B$ is called the **co-domain**
- formal a [[function]] is a [[relation]] from one [[set]] to another [[set]] that satisfies the following two conditions:
$$
\begin{split}
&f: A \rightarrow B \\
\Rightarrow& R_f= \{(x, y): x \in A: f(x) = y\} = graph(f)\\
&\forall a \in A: \exists b \in B: (a, b) \in R_f \\
&(a, b) \in R_f \land  (a, c) \in R_f \Rightarrow b = c\\
\end{split}
$$
- for every subset of $C\subseteq A$ we define a [[set]] $f(C)$ as follows
$$
\begin{split}
f(C) = \{y \in B: \exists c \in C: f(c) = b\}
\end{split}
$$
### image of a [[function]]
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
### grapf of a [[function]]
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
### properties

![[injective#injective]]

![[surjective#surjective]]

![[bijective#bijective]]

### derrived functions

![[inverse function#inverse function]]

![[composition#composition]]
# anki
START
Basic
definitions
- function (formal definition)
- domain and codomain
- image and preimage
- image of a [[function]]
- grapf of a [[function]] and its [[cardinality]]

Back: 
### function
- a [[function]] $f$ is map of elements from one [[set]] $A$ to the elements of another [[set]] $B$ such that all elements of $A$ are ampped to exactly one element from $B$
- the [[set]] $A$ is called the **domain** and the [[set]] $B$ is called the **co-domain**
- formal a [[function]] is a [[relation]] from one [[set]] to another [[set]] that satisfies the following two conditions:
$$
\begin{split}
&f: A \rightarrow B \\
\Rightarrow& R_f= \{(x, y): x \in A: f(x) = y\} = graph(f)\\
&\forall a \in A: \exists b \in B: (a, b) \in R_f \\
&(a, b) \in R_f \land  (a, c) \in R_f \Rightarrow b = c\\
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
<!--ID: 1712909533962-->
END


START
Basic
definitions
- [[injective]]
- [[surjective]]
- [[bijective]]
Back: 

### injective
- a [[function]] $f: A \rightarrow B$ is [[injective]] (or one to one) if the following is true
$$
\forall x_1, x_2 \in A: f(x_1) = f(x_2) \Rightarrow x_1=x_2
$$

### surjective
- a [[function]] $f: A \rightarrow B$ is [[surjective]] if the following is true
$$
\forall y \in B: \exists x: f(x) = y
$$

### bijective
- a [[function]] $f: A \rightarrow B$ is [[bijective]] if its [[injective]] and [[surjective]]


Tags: mathematics
<!--ID: 1712909533968-->
END


START
Basic
definition and when are they defined:
- inverse function
- composition
Back: 
### inverse function
Given a [[bijective]] [[function]] $f:X \rightarrow Y$ then $f^{-1}:Y \rightarrow X$ is the [[inverse function]] of $f$ if the following condition is true

$$
\begin{split}
\forall x \in X, y \in Y: f^{-1}(y) = x \Leftrightarrow f(x) = y
\end{split}
$$
#### implications

$$
\forall x \in X: f^{-1}\left(f(x)\right) = x
$$
$$
\forall y \in Y: f\left(f^{-1}(y)\right) = y
$$


### composition
- given two [[function|functions]] $f:A \rightarrow B$ and $g:B \rightarrow C$ then the [[composition]] $g \circ f: A \rightarrow C$ is defined as follows
$$
g \circ f (x) = f\left(g(x)\right)
$$
- the [[composition]] only exists when the codomain of $f$ is a subset of the domain of $g$

____________________

#### function
- a [[function]] $f$ is map of elements from one [[set]] $A$ to the elements of another [[set]] $B$ such that all elements of $A$ are ampped to exactly one element from $B$
- the [[set]] $A$ is called the **domain** and the [[set]] $B$ is called the **co-domain**
- formal a [[function]] is a [[relation]] from one [[set]] to another [[set]] that satisfies the following two conditions:
$$
\begin{split}
&f: A \rightarrow B \\
\Rightarrow& R_f= \{(x, y): x \in A: f(x) = y\} = graph(f)\\
&\forall a \in A: \exists b \in B: (a, b) \in R_f \\
&(a, b) \in R_f \land  (a, c) \in R_f \Rightarrow b = c\\
\end{split}
$$

#### injective
- a [[function]] $f: A \rightarrow B$ is [[injective]] (or one to one) if the following is true
$$
\forall x_1, x_2 \in A: f(x_1) = f(x_2) \Rightarrow x_1=x_2
$$

#### surjective
- a [[function]] $f: A \rightarrow B$ is [[surjective]] if the following is true
$$
\forall y \in B: \exists x: f(x) = y
$$

#### bijective
- a [[function]] $f: A \rightarrow B$ is [[bijective]] if its [[injective]] and [[surjective]]

Tags: mathematics
<!--ID: 1712910476484-->
END



START
Basic
give 2 examples each for [[function]] that are
- [[injective]] but not [[surjective]]
- [[surjective]] but not [[injective]]

one based on the [[real number]] and one based on a self defined [[set]]
Back: 
#### [[injective]] but not [[surjective]]
$$
\begin{split}
&f : A = \{a_1, a_2\} \rightarrow B = \{b_1, b_2, b_3\} \\
&graph(f) = \{(a_1, b_1), (a_2, b_2)\}
\end{split}
$$
$$
f: \mathbb{R}_{\geq 0} \rightarrow \mathbb{R}: f(x) = x
$$
#### [[surjective]] but not [[injective]]
$$
\begin{split}
&f : A = \{a_1\} \rightarrow B = \{b_1, b_2\} \\
&graph(f) = \{(a_1, b_1), (a_1, b_2)\}
\end{split}
$$
$$
f: \mathbb{R} \rightarrow \mathbb{R}_{\geq 0}: f(x) = x^2
$$


________________________

#### injective
- a [[function]] $f: A \rightarrow B$ is [[injective]] (or one to one) if the following is true
$$
\forall x_1, x_2 \in A: f(x_1) = f(x_2) \Rightarrow x_1=x_2
$$

#### surjective
- a [[function]] $f: A \rightarrow B$ is [[surjective]] if the following is true
$$
\forall y \in B: \exists x: f(x) = y
$$

Tags: mathematics
<!--ID: 1712994707347-->
END