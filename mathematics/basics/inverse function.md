## inverse function
### definition
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

# -----------------------------

![[function#definition function]]

![[injective#injective]]

![[surjective#surjective]]

![[bijective#bijective]]


# anki
START
Basic
 [[inverse function]]
 - definition
 - conditions
 - implications
Back: 
## inverse function
### definition
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
____________________________

### definition function
- a [[function]] $f$ is map of elements from one [[set]] $A$ to the elements of another [[set]] $B$ such that all elements of $A$ are ampped to exactly one element from $B$
- formal a [[function]] is a [[relation]] from one [[set]] to another [[set]] that satisfies the following two conditions:
$$
\begin{split}
&f: A \rightarrow B \\
\Rightarrow& R_f= \{(x, y): x \in A: f(x) = y\} = graph(f)\\
&\forall a \in A: \exists b \in B: (a, b) \in R_f \\
&(a, b) \in R_f \land  (a, c) \in R_f \Rightarrow b = c\\
\end{split}
$$

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
<!--ID: 1682941753044-->
END


# anki
START
Basic
proof that a [[function]] that is not [[injective]] or [[surjective]] can't have a [[inverse function]] 

Back: 
#### non [[injective]]
- let $f: A \rightarrow B$ be a non [[injective]] [[function]]
$$
\begin{split}
\Rightarrow& \exists x_1, x_2, y: (x_1, y) \in  graph(f) \land (x_2, y) \in  graph(f) \land x_1 \neq x_2 \\
\Rightarrow& (y, x_1) \in  graph(f^{-1}) \land (y, x_2) \in  graph(f^{-1}) \land x_1 \neq x_2 \\
\blacksquare

\end{split}
$$

#### non [[surjective]]
- let $f: A \rightarrow B$ be a non [[surjective]] [[function]]
$$
\begin{split}
\Rightarrow& \exists y \in B: \forall x \in A : (x, y) \notin  graph(f) \\
\Rightarrow& \exists y \in B: \forall x \in A : (y, x) \notin  graph(f^{-1}) \\
\blacksquare
\end{split}
$$
____________________________

### inverse function
Given a [[bijective]] [[function]] $f:X \rightarrow Y$ then $f^{-1}:Y \rightarrow X$ is the [[inverse function]] of $f$ if the following condition is true

$$
\begin{split}
\forall x \in X, y \in Y: f^{-1}(y) = x \Leftrightarrow f(x) = y
\end{split}
$$


### definition function
- a [[function]] $f$ is map of elements from one [[set]] $A$ to the elements of another [[set]] $B$ such that all elements of $A$ are ampped to exactly one element from $B$
- formal a [[function]] is a [[relation]] from one [[set]] to another [[set]] that satisfies the following two conditions:
$$
\begin{split}
&f: A \rightarrow B \\
\Rightarrow& R_f= \{(x, y): x \in A: f(x) = y\} = graph(f)\\
&\forall a \in A: \exists b \in B: (a, b) \in R_f \\
&(a, b) \in R_f \land  (a, c) \in R_f \Rightarrow b = c\\
\end{split}
$$

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
<!--ID: 1713005972241-->
END