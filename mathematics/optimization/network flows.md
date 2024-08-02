### network flows
- given a digraph $G(V,A)$ with
	- a [[set]] of vertexes $V$ constaining a source $s \in V$ and a target $t\in V$ 
	- a [[set]] of edges $A \subseteq V \times V$
- given a [[function]] $x: A \to \mathbb{R}_{\geq0}$ that assigns a positive value to each edge that is modeling the flow
- for each vertex except the source and target there is flow conservation thus the incomming flow is eqivalent to the outgoing flow

$$
\forall v \in V \setminus \{a, t\} \sum_{w \in \left\{x \in V: (v, x) \in A \right\}} x(v, w) - \sum_{w \in \left\{x \in V: (x, v) \in A \right\}} x(w, v) = 0
$$

### cut and boundary
- given a garph $G(V,A)$
- a **cut**  $S \subseteq V$ is a subset of the vertices
- the **boundarys** $\delta^{+}(S)$ and $\delta^{-}(S)$ are a [[set]] of the edges where one of vertex is in the cut 

$$
\begin{split}
\delta^{+}(S) = \left\{(v, w) \in A: (x, v) \in A: v \notin S \land w \in S  \right\} \\
\delta^{-}(S) = \left\{(v, w) \in A: (x, v) \notin A: v \in S \land w \in S  \right\} \\
\end{split}
$$

- a cut that contrains the sink $t$ but not the source $s$ is called an **s-t-cut**

### excess of a vertex set
- the excess of a vertex [[set]] $S$ is defined as follows

$$
\mathrm{ex}_x(S) = \sum_{a \in \delta^+(S)} x(a) - \sum_{a \in \delta^-(S)} x(a)
$$


### max flow problem
- given a [[function]] $u: A \to \mathbb{R}_{\geq0}$ that assigns a positive value to each edge that is modeling the maximum possible flow
- the **max flow problem** is defined as follows

$$
\begin{split}
\min_{x \in \mathbb{R}^m} \quad & \mathrm{ex}_x\left(\{t\}\right)\\
\mathrm{s.t.} \quad & \mathrm{ex}_x\left(\{v\}\right) = 0 \quad && \forall v \in V \setminus\{s,t\} \\
\quad & x(a) \leq u(a)  \quad&& \forall a \in A  \\
\quad & x(a) \geq  0 \quad&& \forall a \in A  \\

\end{split}
$$

#### interpretation
- the exess flow in the sink/target $t$ is maximized and since in all vertices except the source $s$ and the target $t$ there is flow conservation this es equivalent to the flow from $s$ to $t$
- the solution has to be feasable in a sense that the maximal capacity $u(a)$ in each edge $a \in A$ cent be exceeded, and the flow has to be positive


# anki

START
Basic
definition
- network flows
- cut and boundary
Back: 
### network flows
- given a digraph $G(V,A)$ with
	- a [[set]] of vertexes $V$ constaining a source $s \in V$ and a target $t\in V$ 
	- a [[set]] of edges $A \subseteq V \times V$
- given a [[function]] $x: A \to \mathbb{R}_{\geq0}$ that assigns a positive value to each edge that is modeling the flow
- for each vertex except the source and target there is flow conservation thus the incomming flow is eqivalent to the outgoing flow

$$
\forall v \in V \setminus \{a, t\} \sum_{w \in \left\{x \in V: (v, x) \in A \right\}} x(v, w) - \sum_{w \in \left\{x \in V: (x, v) \in A \right\}} x(w, v) = 0
$$

### cut and boundary
- given a garph $G(V,A)$
- a **cut**  $S \subseteq V$ is a subset of the vertices
- the **boundarys** $\delta^{+}(S)$ and $\delta^{-}(S)$ are a [[set]] of the edges where one of vertex is in the cut 

$$
\begin{split}
\delta^{+}(S) = \left\{(v, w) \in A: (x, v) \in A: v \notin S \land w \in S  \right\} \\
\delta^{-}(S) = \left\{(v, w) \in A: (x, v) \notin A: v \in S \land w \in S  \right\} \\
\end{split}
$$

- a cut that contrains the sink $t$ but not the source $s$ is called an **s-t-cut**

### excess of a vertex set
- the excess of a vertex [[set]] $S$ is defined as follows

$$
\mathrm{ex}_x(S) = \sum_{a \in \delta^+(S)} x(a) - \sum_{a \in \delta^-(S)} x(a)
$$


### max flow problem
- given a [[function]] $u: A \to \mathbb{R}_{\geq0}$ that assigns a positive value to each edge that is modeling the maximum possible flow
- the **max flow problem** is defined as follows

$$
\begin{split}
\min_{x \in \mathbb{R}^m} \quad & \mathrm{ex}_x\left(\{t\}\right)\\
\mathrm{s.t.} \quad & \mathrm{ex}_x\left(\{v\}\right) = 0 \quad && \forall v \in V \setminus\{s,t\} \\
\quad & x(a) \leq u(a)  \quad&& \forall a \in A  \\
\quad & x(a) \geq  0 \quad&& \forall a \in A  \\

\end{split}
$$

#### interpretation
- the exess flow in the sink/target $t$ is maximized and since in all vertices except the source $s$ and the target $t$ there is flow conservation this es equivalent to the flow from $s$ to $t$
- the solution has to be feasable in a sense that the maximal capacity $u(a)$ in each edge $a \in A$ cent be exceeded, and the flow has to be positive


Tags: mathematics
<!--ID: 1722609060408-->
END




START
Basic
max flow problem
- definition
- interpretation
Back: 
### excess of a vertex set
- the excess of a vertex [[set]] $S$ is defined as follows

$$
\mathrm{ex}_x(S) = \sum_{a \in \delta^+(S)} x(a) - \sum_{a \in \delta^-(S)} x(a)
$$


### max flow problem
- given a [[function]] $u: A \to \mathbb{R}_{\geq0}$ that assigns a positive value to each edge that is modeling the maximum possible flow
- the **max flow problem** is defined as follows

$$
\begin{split}
\min_{x \in \mathbb{R}^m} \quad & \mathrm{ex}_x\left(\{t\}\right)\\
\mathrm{s.t.} \quad & \mathrm{ex}_x\left(\{v\}\right) = 0 \quad && \forall v \in V \setminus\{s,t\} \\
\quad & x(a) \leq u(a)  \quad&& \forall a \in A  \\
\quad & x(a) \geq  0 \quad&& \forall a \in A  \\

\end{split}
$$

#### interpretation
- the exess flow in the sink/target $t$ is maximized and since in all vertices except the source $s$ and the target $t$ there is flow conservation this es equivalent to the flow from $s$ to $t$
- the solution has to be feasable in a sense that the maximal capacity $u(a)$ in each edge $a \in A$ cent be exceeded, and the flow has to be positive

_________________

### network flows
- given a digraph $G(V,A)$ with
	- a [[set]] of vertexes $V$ constaining a source $s \in V$ and a target $t\in V$ 
	- a [[set]] of edges $A \subseteq V \times V$
- given a [[function]] $x: A \to \mathbb{R}_{\geq0}$ that assigns a positive value to each edge that is modeling the flow
- for each vertex except the source and target there is flow conservation thus the incomming flow is eqivalent to the outgoing flow

$$
\forall v \in V \setminus \{a, t\} \sum_{w \in \left\{x \in V: (v, x) \in A \right\}} x(v, w) - \sum_{w \in \left\{x \in V: (x, v) \in A \right\}} x(w, v) = 0
$$

### cut and boundary
- given a garph $G(V,A)$
- a **cut**  $S \subseteq V$ is a subset of the vertices
- the **boundarys** $\delta^{+}(S)$ and $\delta^{-}(S)$ are a [[set]] of the edges where one of vertex is in the cut 

$$
\begin{split}
\delta^{+}(S) = \left\{(v, w) \in A: (x, v) \in A: v \notin S \land w \in S  \right\} \\
\delta^{-}(S) = \left\{(v, w) \in A: (x, v) \notin A: v \in S \land w \in S  \right\} \\
\end{split}
$$

- a cut that contrains the sink $t$ but not the source $s$ is called an **s-t-cut**


Tags: mathematics
<!--ID: 1722609060413-->
END