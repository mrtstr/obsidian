### open set
- generalization of an open interval on a line for general [[vector space|vector spaces]]
- given a [[metric]] [[vector space|space]] $(A, d)$
- a subset $U \subset A$ is a [[open and closed sets|open set]] there is for every element $x \in A$ there exists a [[ball]] centered around $x$ that is a subset of $A$ 

$$
\forall x \in U: \exists \epsilon > 0: B_{\epsilon}(x) \subset U
$$
→ that means every [[set]] that does not have a [[maximum]] / [[minimum]]

### closed set
- given a [[metric]] [[vector space|space]] $(A, d)$
- a subset $U \subset A$ is [[open and closed sets| closed set]] is its [[complement]] $U^c = A \setminus U$ is open

$$
\forall x \in U^c: \exists \epsilon > 0: B_{\epsilon}(x) \subset U^c
$$
→ when the [[complement]] of a [[set]] does not have a [[maximum]] / [[minimum]]

### examples
#### example open but not closed set

$$
(a, b) = \{x \in \mathbb{R}: x > a \land x < b \}
$$
-  is open 
- is not closed because $(a, b)^c = \{x \in \mathbb{R}: x \leq a \land x \geq b \}$ is not open

proof 
- given a [[metric]] $d(x, y) = |x - y|$
$$
x \in (a, b) \Rightarrow B_\epsilon(x) = (x- \epsilon, x + \epsilon) \subset (a, b)
$$
#### example closed but not open set
$$[a, b] = \{x \in \mathbb{R}: x \geq a \land x \leq b \}$$
 - is not open
 - is closed because $[a, b]^c = \{x \in \mathbb{R}: x < a \land x > b \}$ is open

#### example open and closed
- the [[real numbers]] $\mathbb{R}$ are open and closed at the same time because the [[empty set]] $\emptyset$ is also open and closed at the same time

#### example either open not closed
$$
(a, b] = \{x \in \mathbb{R}: x > a \land x \leq b \}
$$



![[ball#ball]]

![[complement#complement of a set]]

![[metric#metric]]

# anki
START
Basic
definitions
- [[open and closed sets]]
 
Back: 
### open set
- generalization of an open interval on a line for general [[vector space|vector spaces]]
- given a [[metric]] [[vector space|space]] $(A, d)$
- a subset $U \subset A$ is a [[open and closed sets|open set]] there is for every element $x \in A$ there exists a [[ball]] centered around $x$ that is a subset of $A$ 

$$
\forall x \in U: \exists \epsilon > 0: B_{\epsilon}(x) \subset U
$$
→ that means every [[set]] that does not have a [[maximum]] / [[minimum]]

### closed set
- given a [[metric]] [[vector space|space]] $(A, d)$
- a subset $U \subset A$ is [[open and closed sets| closed set]] is its [[complement]] $U^c = A \setminus U$ is open

$$
\forall x \in U^c: \exists \epsilon > 0: B_{\epsilon}(x) \subset U^c
$$
→ when the [[complement]] of a [[set]] does not have a [[maximum]] / [[minimum]]


### ball
- given a [[set]] $A$ with a [[metric]] $d(\cdot,\cdot)$
- for each $x \in A$ and $\epsilon > 0$ the $\epsilon$-ball ($\epsilon$-nighbouhood) is defined as follows

$$
B_\epsilon(x) = \{y \in A: d(x, y) < \epsilon\}
$$

### complement of a set
$$
\begin{split}
A^c &= \mathbb{U} \setminus A \\
&= \{x : x \in \mathbb{U} \land x \notin  A\} \\
\end{split}
$$

### metric
- generalization of the distance between [[vector|vectors]]
- let $V$ be a [[set]]
- a [[function]] $d: V \times V \rightarrow (0, \infty)$ is a [[metric]] if the followng conditions are true

1) [[symmetric]]
$$
\forall x, y \in V: d(x,y) = d(y,x)
$$
2) [[positive definite]]
$$
d(x, y) \leftrightarrow x=y
$$
$$
\forall x, y \in V: d(x, y) \geq 0
$$
3) [[triangle inequality]]
$$
\forall x, y, z \in V: d(x,z) \leq d(x,y) + d(y,z)
$$


Tags: mathematics
<!--ID: 1715272168176-->
END


START
Basic
examples for all possibilies regarding [[open and closed sets]]
 
Back: 

#### example open but not closed set

$$
(a, b) = \{x \in \mathbb{R}: x > a \land x < b \} \subset \mathbb{R}
$$
-  is open 
- is not closed because $(a, b)^c = \{x \in \mathbb{R}: x \leq a \land x \geq b \}  \subset \mathbb{R}$ is not open
proof 
- given a [[metric]] $d(x, y) = |x - y|$
$$
x \in (a, b) \Rightarrow B_\epsilon(x) = (x- \epsilon, x + \epsilon) \subset (a, b)
$$
#### example closed but not open set
$$[a, b] = \{x \in \mathbb{R}: x \geq a \land x \leq b \}  \subset \mathbb{R}$$
 - is not open
 - is closed because $[a, b]^c = \{x \in \mathbb{R}: x < a \land x > b \}  \subset \mathbb{R}$ is open

#### example open and closed
- the [[real numbers]] $\mathbb{R}$ are open and closed at the same time because the [[empty set]] $\emptyset$ is also open and closed at the same time

#### example either open not closed
$$
(a, b] = \{x \in \mathbb{R}: x > a \land x \leq b \}  \subset \mathbb{R}
$$

_______________
### open set
- generalization of an open interval on a line for general [[vector space|vector spaces]]
- given a [[metric]] [[vector space|space]] $(A, d)$
- a subset $U \subset A$ is a [[open and closed sets|open set]] there is for every element $x \in A$ there exists a [[ball]] centered around $x$ that is a subset of $A$ 

$$
\forall x \in U: \exists \epsilon > 0: B_{\epsilon}(x) \subset U
$$
→ that means every [[set]] that does not have a [[maximum]] / [[minimum]]

### closed set
- given a [[metric]] [[vector space|space]] $(A, d)$
- a subset $U \subset A$ is [[open and closed sets| closed set]] is its [[complement]] $U^c = A \setminus U$ is open

$$
\forall x \in U^c: \exists \epsilon > 0: B_{\epsilon}(x) \subset U^c
$$
→ when the [[complement]] of a [[set]] does not have a [[maximum]] / [[minimum]]


### ball
- given a [[set]] $A$ with a [[metric]] $d(\cdot,\cdot)$
- for each $x \in A$ and $\epsilon > 0$ the $\epsilon$-ball ($\epsilon$-nighbouhood) is defined as follows

$$
B_\epsilon(x) = \{y \in A: d(x, y) < \epsilon\}
$$

### complement of a set
$$
\begin{split}
A^c &= \mathbb{U} \setminus A \\
&= \{x : x \in \mathbb{U} \land x \notin  A\} \\
\end{split}
$$

### metric
- generalization of the distance between [[vector|vectors]]
- let $V$ be a [[set]]
- a [[function]] $d: V \times V \rightarrow (0, \infty)$ is a [[metric]] if the followng conditions are true

1) [[symmetric]]
$$
\forall x, y \in V: d(x,y) = d(y,x)
$$
2) [[positive definite]]
$$
d(x, y) \leftrightarrow x=y
$$
$$
\forall x, y \in V: d(x, y) \geq 0
$$
3) [[triangle inequality]]
$$
\forall x, y, z \in V: d(x,z) \leq d(x,y) + d(y,z)
$$


Tags: mathematics
<!--ID: 1715272168180-->
END


START
Basic
prof that the following is a [[open and closed sets|open set]]
$$
(a, b) = \{x \in \mathbb{R}: x > a \land x < b \} \subset \mathbb{R}
$$
- is it also closed?
Back: 

-  is open 
- is not closed because $(a, b)^c = \{x \in \mathbb{R}: x \leq a \land x \geq b \}  \subset \mathbb{R}$ is not open
proof 
- given a [[metric]] $d(x, y) = |x - y|$
$$
x \in (a, b) \Rightarrow B_\epsilon(x) = (x- \epsilon, x + \epsilon) \subset (a, b)
$$

_______________
### open set
- generalization of an open interval on a line for general [[vector space|vector spaces]]
- given a [[metric]] [[vector space|space]] $(A, d)$
- a subset $U \subset A$ is a [[open and closed sets|open set]] there is for every element $x \in A$ there exists a [[ball]] centered around $x$ that is a subset of $A$ 

$$
\forall x \in U: \exists \epsilon > 0: B_{\epsilon}(x) \subset U
$$
→ that means every [[set]] that does not have a [[maximum]] / [[minimum]]

### closed set
- given a [[metric]] [[vector space|space]] $(A, d)$
- a subset $U \subset A$ is [[open and closed sets| closed set]] is its [[complement]] $U^c = A \setminus U$ is open

$$
\forall x \in U^c: \exists \epsilon > 0: B_{\epsilon}(x) \subset U^c
$$
→ when the [[complement]] of a [[set]] does not have a [[maximum]] / [[minimum]]


### ball
- given a [[set]] $A$ with a [[metric]] $d(\cdot,\cdot)$
- for each $x \in A$ and $\epsilon > 0$ the $\epsilon$-ball ($\epsilon$-nighbouhood) is defined as follows

$$
B_\epsilon(x) = \{y \in A: d(x, y) < \epsilon\}
$$

### complement of a set
$$
\begin{split}
A^c &= \mathbb{U} \setminus A \\
&= \{x : x \in \mathbb{U} \land x \notin  A\} \\
\end{split}
$$

### metric
- generalization of the distance between [[vector|vectors]]
- let $V$ be a [[set]]
- a [[function]] $d: V \times V \rightarrow (0, \infty)$ is a [[metric]] if the followng conditions are true

1) [[symmetric]]
$$
\forall x, y \in V: d(x,y) = d(y,x)
$$
2) [[positive definite]]
$$
d(x, y) \leftrightarrow x=y
$$
$$
\forall x, y \in V: d(x, y) \geq 0
$$
3) [[triangle inequality]]
$$
\forall x, y, z \in V: d(x,z) \leq d(x,y) + d(y,z)
$$


Tags: mathematics
<!--ID: 1715272168182-->
END