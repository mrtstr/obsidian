- Sequence $(x_1, ..., x_t)  \rightarrow (y_1, ..., y_t)$ to sequence operation
- each output vecor $y$ can be interpreted as a weighted sum of all input vectors $(x_1, ..., x_t)$ ([[dot product]] with a normalized weight [[vector]])
	→ each $y_i$ contains the context of all input vectors $(x_1, ..., x_t)$
$$
\begin{split}
&y_i = \sum_j w_{ij} x_i \in \mathbb{R}^{k} \\
&\text{with }\sum_j w_{ij}  = 1 \\
\end{split}
$$
The equation can be written as a [[matrix product]]

$$
\begin{split}
Y &= \begin{pmatrix}   y_1 \\   ... \\ y_t  \end{pmatrix}^\top \in \mathbb{R}^{k \times t} \\
X &= \begin{pmatrix}   x_1 \\   ... \\ x_t  \end{pmatrix}^\top \in \mathbb{R}^{k \times t}  \\
W &= \left(w_{ij}\right) \in \mathbb{R}^{k \times k}  \\
Y &= WX 
\end{split}
$$
## Simple non leaned attention weights
- use [[normalized]] [[dot product]] as weights
- [[dot product]] is a metric for now close the [[embeddings]] $x_i$ and $x_j$ are
	→ [[consine similariy]]
$$
w_{ij} =  \frac{x_ix_j^\top}{||x_ix_j^\top||}
$$

## learned weights
- we learn parameters $W_Q \in \mathbb{R}^{k \times k}$, $W_K \in \mathbb{R}^{k \times k}$ and $W_V \in \mathbb{R}^{k \times k}$
$$
\begin{split}
Q = XW_Q \\
K = KW_K \\
V = XW_V \\
\end{split}
$$
- insted of just taking the [[dot product]] between the input [[embeddings]] we tranform them with a [[linear layer]] before which is equal to a [[matrix product]] with a [[matrix]] of learned parameters 
- afterward we normalize the therm with the size of the context $t$
- and take the [[softmax function]] to make sure every row is normalized
$$
\begin{split}
Y = softmax\left(\frac{QK^\top}{\sqrt{t}}\right)V
\end{split}
$$


# anki

START
Basic
[[self attention]]
- concept
- basic approach
- approach with lerned transformations

Back: 
- Sequence $(x_1, ..., x_t)  \rightarrow (y_1, ..., y_t)$ to sequence operation
- each output vecor $y$ can be interpreted as a weighted sum of all input vectors $(x_1, ..., x_t)$ ([[dot product]] with a normalized weight [[vector]])
	→ each $y_i$ contains the context of all input vectors $(x_1, ..., x_t)$
$$
\begin{split}
&y_i = \sum_j w_{ij} x_i \in \mathbb{R}^{k} \\
&\text{with }\sum_j w_{ij}  = 1 \\
\end{split}
$$
The equation can be written as a [[matrix product]]

$$
\begin{split}
Y &= \begin{pmatrix}   y_1 \\   ... \\ y_t  \end{pmatrix}^\top \in \mathbb{R}^{k \times t} \\
X &= \begin{pmatrix}   x_1 \\   ... \\ x_t  \end{pmatrix}^\top \in \mathbb{R}^{k \times t}  \\
W &= \left(w_{ij}\right) \in \mathbb{R}^{k \times k}  \\
Y &= WX 
\end{split}
$$
## Simple non leaned attention weights
- use [[normalized]] [[dot product]] as weights
- [[dot product]] is a metric for now close the [[embeddings]] $x_i$ and $x_j$ are
	→ [[consine similariy]]
$$
w_{ij} =  \frac{x_ix_j^\top}{||x_ix_j^\top||}
$$

## learned weights
- we learn parameters $W_Q \in \mathbb{R}^{k \times k}$, $W_K \in \mathbb{R}^{k \times k}$ and $W_V \in \mathbb{R}^{k \times k}$
$$
\begin{split}
Q = XW_Q \\
K = KW_K \\
V = XW_V \\
\end{split}
$$
- insted of just taking the [[dot product]] between the input [[embeddings]] we tranform them with a [[linear layer]] before which is equal to a [[matrix product]] with a [[matrix]] of learned parameters 
- afterward we normalize the therm with the size of the context $t$
- and take the [[softmax function]] to make sure every row is normalized
$$
\begin{split}
Y = softmax\left(\frac{QK^\top}{\sqrt{t}}\right)V
\end{split}
$$

Tags: ml
<!--ID: 1685773791044-->
END