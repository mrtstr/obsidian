### definiteness of matrices
#### positive definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[positive definite]] if the following is true
$$
\forall x \in \mathbb{R}^n \setminus{0}: x^\top A x >0
$$

- in other words $f(x) = x^\top A x$ is a [[positive definite]] [[function]]

#### positive semi definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[definiteness of matrices|positive semi definite]] if the following is true
$$
\forall x \in \mathbb{R}^n : x^\top A x \geq0
$$
- in other words $f(x) = x^\top A x$ is a [[positive definite|positive semi definite]] [[function]]

#### negative definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[positive definite]] if the following is true
$$
\forall x \in \mathbb{R}^n \setminus{0}: x^\top A x < 0
$$

- in other words $f(x) = x^\top A x$ is a [[positive definite|negative definite]] [[function]]

#### negative semi definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[definiteness of matrices|positive semi definite]] if the following is true
$$
\forall x \in \mathbb{R}^n : x^\top A x \geq0
$$
- in other words $f(x) = x^\top A x$ is a [[positive definite|negative semi definite]] [[function]]

#### indefinite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[definiteness of matrices|indefinite]] if its neither positive nor negative (semi) definite
- that means the [[function]] $f(x) = x^\top A x$ can take positive as well as negative values


### definitness of $A^\top A$
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$
- $A^\top A$ is positive semi definit
$$
\begin{split}
x^\top A^\top Ax =  (Ax)^\top Ax = \langle Ax, Ax \rangle = ||Ax||^2 \geq 0
\end{split}
$$

- if $\mathrm{rank}(A) = m$  then $A^\top A$ is even positive definite

$$
\begin{split}
&x^\top A^\top Ax =  (Ax)^\top Ax = \langle Ax, Ax \rangle = ||Ax||^2 \geq 0 \\
&||Ax||^2 = 0 \Leftrightarrow Ax = 0 \\
&\mathrm{rank}(A) = m \Rightarrow A_{(*, 1)}, ..., A_{(*, m)} \text{ are linear independen} \\
\Rightarrow & Ax = 0 \Rightarrow x=0
\end{split}
$$
# ---------------------------

![[positive definite#positive definite function]]

# anki


START
Basic
what kann be said about the definitness of $A^\top A$ (with proof)
Back: 
### definitness of $A^\top A$
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$
- $A^\top A$ is positive semi definit
$$
\begin{split}
x^\top A^\top Ax =  (Ax)^\top Ax = \langle Ax, Ax \rangle = ||Ax||^2 \geq 0
\end{split}
$$

- if $\mathrm{rank}(A) = m$  then $A^\top A$ is even positive definite

$$
\begin{split}
&x^\top A^\top Ax =  (Ax)^\top Ax = \langle Ax, Ax \rangle = ||Ax||^2 \geq 0 \\
&||Ax||^2 = 0 \Leftrightarrow Ax = 0 \\
&\mathrm{rank}(A) = m \Rightarrow A_{(*, 1)}, ..., A_{(*, m)} \text{ are linear independen} \\
\Rightarrow & Ax = 0 \Rightarrow x=0
\end{split}
$$
____________________

### positive definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[positive definite]] if the following is true
$$
\forall x \in \mathbb{R}^n \setminus{0}: x^\top A x >0
$$

- in other words $f(x) = x^\top A x$ is a [[positive definite]] [[function]]

### positive semi definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[definiteness of matrices|positive semi definite]] if the following is true
$$
\forall x \in \mathbb{R}^n : x^\top A x \geq0
$$
- in other words $f(x) = x^\top A x$ is a [[positive definite|positive semi definite]] [[function]]

### negative definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[positive definite]] if the following is true
$$
\forall x \in \mathbb{R}^n \setminus{0}: x^\top A x < 0
$$

- in other words $f(x) = x^\top A x$ is a [[positive definite|negative definite]] [[function]]

### negative semi definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[definiteness of matrices|positive semi definite]] if the following is true
$$
\forall x \in \mathbb{R}^n : x^\top A x \geq0
$$
- in other words $f(x) = x^\top A x$ is a [[positive definite|negative semi definite]] [[function]]

### indefinite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[definiteness of matrices|indefinite]] if its neither positive nor negative (semi) definite
- that means the [[function]] $f(x) = x^\top A x$ can take positive as well as negative values

### positive definite
- a [[function]] $f: A \rightarrow B$ is [[positive definite]] on a neighbourhood $D$ of the [[origin]] if the following is true
$$
f(0) = 0 \land \forall v \in D: f(v) \geq 0
$$

Tags: mathematics linear_algebra
<!--ID: 1722281289976-->
END


START
Basic
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$ with  $\mathrm{rank}(A) = m$ 
- proof that $A^\top A$ is positive definite

Back: 
### definitness of $A^\top A$
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$
- $A^\top A$ is positive semi definit
$$
\begin{split}
x^\top A^\top Ax =  (Ax)^\top Ax = \langle Ax, Ax \rangle = ||Ax||^2 \geq 0
\end{split}
$$

- if $\mathrm{rank}(A) = m$  then $A^\top A$ is even positive definite

$$
\begin{split}
&x^\top A^\top Ax =  (Ax)^\top Ax = \langle Ax, Ax \rangle = ||Ax||^2 \geq 0 \\
&||Ax||^2 = 0 \Leftrightarrow Ax = 0 \\
&\mathrm{rank}(A) = m \Rightarrow A_{(*, 1)}, ..., A_{(*, m)} \text{ are linear independen} \\
\Rightarrow & Ax = 0 \Rightarrow x=0
\end{split}
$$
____________________

### positive definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[positive definite]] if the following is true
$$
\forall x \in \mathbb{R}^n \setminus{0}: x^\top A x >0
$$

- in other words $f(x) = x^\top A x$ is a [[positive definite]] [[function]]

### positive semi definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[definiteness of matrices|positive semi definite]] if the following is true
$$
\forall x \in \mathbb{R}^n : x^\top A x \geq0
$$
- in other words $f(x) = x^\top A x$ is a [[positive definite|positive semi definite]] [[function]]

### negative definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[positive definite]] if the following is true
$$
\forall x \in \mathbb{R}^n \setminus{0}: x^\top A x < 0
$$

- in other words $f(x) = x^\top A x$ is a [[positive definite|negative definite]] [[function]]

### negative semi definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[definiteness of matrices|positive semi definite]] if the following is true
$$
\forall x \in \mathbb{R}^n : x^\top A x \geq0
$$
- in other words $f(x) = x^\top A x$ is a [[positive definite|negative semi definite]] [[function]]

### indefinite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[definiteness of matrices|indefinite]] if its neither positive nor negative (semi) definite
- that means the [[function]] $f(x) = x^\top A x$ can take positive as well as negative values

### positive definite
- a [[function]] $f: A \rightarrow B$ is [[positive definite]] on a neighbourhood $D$ of the [[origin]] if the following is true
$$
f(0) = 0 \land \forall v \in D: f(v) \geq 0
$$

Tags: mathematics linear_algebra
<!--ID: 1722281289978-->
END


START
Basic
can a [[matrix]] be negative semi definite and positive semi definite at the same time? (with proof)
Back: 
- a square matrix containing only zeros is negative semi definite and positive semi definite because $\forall x \in \mathbb{R}^n : x^\top A x \geq0$ and $\forall x \in \mathbb{R}^n : x^\top A x \leq0$

____________________

### positive definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[positive definite]] if the following is true
$$
\forall x \in \mathbb{R}^n \setminus{0}: x^\top A x >0
$$

- in other words $f(x) = x^\top A x$ is a [[positive definite]] [[function]]

### positive semi definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[definiteness of matrices|positive semi definite]] if the following is true
$$
\forall x \in \mathbb{R}^n : x^\top A x \geq0
$$
- in other words $f(x) = x^\top A x$ is a [[positive definite|positive semi definite]] [[function]]

### negative definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[positive definite]] if the following is true
$$
\forall x \in \mathbb{R}^n \setminus{0}: x^\top A x < 0
$$

- in other words $f(x) = x^\top A x$ is a [[positive definite|negative definite]] [[function]]

### negative semi definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[definiteness of matrices|positive semi definite]] if the following is true
$$
\forall x \in \mathbb{R}^n : x^\top A x \geq0
$$
- in other words $f(x) = x^\top A x$ is a [[positive definite|negative semi definite]] [[function]]

### indefinite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[definiteness of matrices|indefinite]] if its neither positive nor negative (semi) definite
- that means the [[function]] $f(x) = x^\top A x$ can take positive as well as negative values

### positive definite
- a [[function]] $f: A \rightarrow B$ is [[positive definite]] on a neighbourhood $D$ of the [[origin]] if the following is true
$$
f(0) = 0 \land \forall v \in D: f(v) \geq 0
$$

Tags: mathematics linear_algebra
<!--ID: 1720964044638-->
END

START
Basic
definition: 
- positive definite [[matrix]]
- positive semi definite [[matrix]]
- negative definite [[matrix]]
- indefinite [[matrix]]

how is it related to the concept of a [[positive definite]] [[function]]?


Back: 
### positive definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[positive definite]] if the following is true
$$
\forall x \in \mathbb{R}^n \setminus{0}: x^\top A x >0
$$

- in other words $f(x) = x^\top A x$ is a [[positive definite]] [[function]]

### positive semi definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[definiteness of matrices|positive semi definite]] if the following is true
$$
\forall x \in \mathbb{R}^n : x^\top A x \geq0
$$
- in other words $f(x) = x^\top A x$ is a [[positive definite|positive semi definite]] [[function]]

### negative definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[positive definite]] if the following is true
$$
\forall x \in \mathbb{R}^n \setminus{0}: x^\top A x < 0
$$

- in other words $f(x) = x^\top A x$ is a [[positive definite|negative definite]] [[function]]

### negative semi definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[definiteness of matrices|positive semi definite]] if the following is true
$$
\forall x \in \mathbb{R}^n : x^\top A x \geq0
$$
- in other words $f(x) = x^\top A x$ is a [[positive definite|negative semi definite]] [[function]]

### indefinite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[definiteness of matrices|indefinite]] if its neither positive nor negative (semi) definite
- that means the [[function]] $f(x) = x^\top A x$ can take positive as well as negative values


____________________

### positive definite
- a [[function]] $f: A \rightarrow B$ is [[positive definite]] on a neighbourhood $D$ of the [[origin]] if the following is true
$$
f(0) = 0 \land \forall v \in D: f(v) \geq 0
$$

Tags: mathematics linear_algebra
<!--ID: 1720964044645-->
END
