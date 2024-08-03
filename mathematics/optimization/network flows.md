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
\delta^{+}(S) &= \left\{(v, w) \in A: v \notin S \land w \in S  \right\} \\
\delta^{-}(S) &= \left\{(v, w) \in A : v \in S \land w \notin S  \right\} \\
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

### residual graph
- given a digraph $G(V,A)$ with flow in it the residual graph is $G_x(V, A_x)$ with the free capacity $u_x$ represents the avaliable capacity
- for each edge $(a, b) \in A$ with flow there is an edge $(b,a)$ added with $u(b,a)=x(a, b)$ because reducing the existing flow is equivalent to flow in the oposite direction
- apart from that the existing flow is subtracted from the free capacity
- edges with zero capacity are removed

$$
\begin{split}
A_x &= \{a \in A: x(a) < u(a)\} \cup \{a^1 \in A^1: x(a)\} \\
u_x &= \left\{\begin{matrix} 
u(a) - x(a) && a \in A \\ 
x(a^{-1}) && a^{-1} \in A
\end{matrix} \right. \\
\end{split}
$$

### optimality criterium for the max flow problem
- as solution of the **max flow problem** is optimal if there exists an **s-t-cut** $S$ such that there all edges of the **residual graph** in the incomming boundarys have a value of zero 
$$
\sum_{a \in \delta^+(S)} x(a) = 0
$$

### ford fulkerson algorithm
- algorithm for solving the **maxflow problem** with a greedy approach
- provides a mapping $x: A \to \mathbb{R}^{+}$ that assinges a flow to each edge

1) init $x(a) = 0 \forall a \in A$
2) construct residual graph $G_x, u_x$
3) if there is no path from $s$ to $t$ in $G_x$: return $x$
4) find path $P$ from $s$ to $t$ in $G_x$ with the bottleneck $\lambda$
5) adapt $x$ by adding a flow of $\lambda$ along $P$, GOTO 2)

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
\delta^{+}(S) &= \left\{(v, w) \in A: v \notin S \land w \in S  \right\} \\
\delta^{-}(S) &= \left\{(v, w) \in A : v \in S \land w \notin S  \right\} \\
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
\delta^{+}(S) &= \left\{(v, w) \in A: v \notin S \land w \in S  \right\} \\
\delta^{-}(S) &= \left\{(v, w) \in A : v \in S \land w \notin S  \right\} \\
\end{split}
$$

- a cut that contrains the sink $t$ but not the source $s$ is called an **s-t-cut**


Tags: mathematics
<!--ID: 1722609060413-->
END


START
Basic
residual graph
- definition
- interpretation
Back: 
### residual graph
- given a digraph $G(V,A)$ with flow in it the residual graph is $G_x(V, A_x)$ with the free capacity $u_x$ represents the avaliable capacity
- for each edge $(a, b) \in A$ with flow there is an edge $(b,a)$ added with $u(b,a)=x(a, b)$ because reducing the existing flow is equivalent to flow in the oposite direction
- apart from that the existing flow is subtracted from the free capacity
- edges with zero capacity are removed

$$
\begin{split}
A_x &= \{a \in A: x(a) < u(a)\} \cup \{a^1 \in A^1: x(a)\} \\
u_x &= \left\{\begin{matrix} 
u(a) - x(a) && a \in A \\ 
x(a^{-1}) && a^{-1} \in A
\end{matrix} \right. \\
\end{split}
$$

_________________

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
\delta^{+}(S) &= \left\{(v, w) \in A: v \notin S \land w \in S  \right\} \\
\delta^{-}(S) &= \left\{(v, w) \in A : v \in S \land w \notin S  \right\} \\
\end{split}
$$

- a cut that contrains the sink $t$ but not the source $s$ is called an **s-t-cut**


Tags: mathematics
<!--ID: 1722697409835-->
END


START
Basic
ford fulkerson algorithm
- what is it used for
- pseudocode

Back: 
### ford fulkerson algorithm
- algorithm for solving the **maxflow problem** with a greedy approach
- provides a mapping $x: A \to \mathbb{R}^{+}$ that assinges a flow to each edge

1) init $x(a) = 0 \forall a \in A$
2) construct residual graph $G_x, u_x$
3) if there is no path from $s$ to $t$ in $G_x$: return $x$
4) find path $P$ from $s$ to $t$ in $G_x$ with the bottleneck $\lambda$
5) adapt $x$ by adding a flow of $\lambda$ along $P$, GOTO 2)


### residual graph
- given a digraph $G(V,A)$ with flow in it the residual graph is $G_x(V, A_x)$ with the free capacity $u_x$ represents the avaliable capacity
- for each edge $(a, b) \in A$ with flow there is an edge $(b,a)$ added with $u(b,a)=x(a, b)$ because reducing the existing flow is equivalent to flow in the oposite direction
- apart from that the existing flow is subtracted from the free capacity
- edges with zero capacity are removed

$$
\begin{split}
A_x &= \{a \in A: x(a) < u(a)\} \cup \{a^1 \in A^1: x(a)\} \\
u_x &= \left\{\begin{matrix} 
u(a) - x(a) && a \in A \\ 
x(a^{-1}) && a^{-1} \in A
\end{matrix} \right. \\
\end{split}
$$

_________________

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
\delta^{+}(S) &= \left\{(v, w) \in A: v \notin S \land w \in S  \right\} \\
\delta^{-}(S) &= \left\{(v, w) \in A : v \in S \land w \notin S  \right\} \\
\end{split}
$$

- a cut that contrains the sink $t$ but not the source $s$ is called an **s-t-cut**


Tags: mathematics
<!--ID: 1722697409841-->
END