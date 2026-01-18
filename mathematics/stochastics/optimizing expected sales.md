## optimizing expected sales
### solving the problem for a single location
- **stock** $s$ is constant
- **demand**: $D$ is a [[random variable]] with the [[probability density function (PDF)]] $f(d)$ and the [[cumulative distribution function (CDF)]] $F(d)$

#### expected sales

$$
\begin{split}
\mathbb{E}[\min\{s, D\}] 
&= \int_0^\infty \min\{s, d\} f(d) dd \\
&=  \int_0^s d f(d) dd + s \int_s^\infty f(d) dd \\
&=  \int_0^s d f(d) dd + s \left(1-F(s)\right) \\
&=  s\cdot F(s) - \int_0^s  F(d) dd + s - sF(s) \\
&=  \underbrace{s}_{\int_0^s1 dd} - \int_0^s  F(d) dd  \\
&=  \int_0^s \left(1-F(d)\right) dd \\
\end{split}
$$

$$
\begin{split}
\int_0^s d f(d) dd
&= \left[d\cdot F(d)\right]_0^s - \int_0^s  F(d) dd \\
&= s\cdot F(s) - \int_0^s  F(d) dd \\
\end{split}
$$

#### gradient w.r.t. stock
- using the **fundamental theorem of calculus**: $G(x) = \int_0^xg(t)dt \Rightarrow G'(x)=g(x)$

$$
\begin{split}
\frac{\partial}{\partial s}\mathbb{E}[\min\{s, D\}] 
&= 1-F(s) \\
\end{split}
$$

#### optimality condition (diminishing marginal returns)
- given multiple warehouses/products and a global inventory target, the optimality condition is that the **marginal gains ([[gradient]]) are equal**. (in a problem with diminishing marginal returns)

##### maximizing the sales
$$
\begin{split}
1-F_i(s_i) &= 1-F_j(s_j) :=\lambda \\
s_i &= F_i^{-1}(\lambda)
\end{split}
$$

##### maximizing the profit
- if we are maximizing the profit we have the following condition with the profit contribution $p_i$ of the warehouse / product combination $i$

$$
\begin{split}
(1-F_i(s_i))*p_i &= (1-F_j(s_j))*p_j :=\lambda \\
s_i &= F_i^{-1}\left( 1-\frac{\lambda}{p_i}\right) \\
\end{split}
$$

note: since these functions are monotone, the optimal $\lambda$ can be found efficiently using bisection

### solving the problem for a supply chain network
- we have different articles $A$ and warehouses $W$
- each warehouse $w\in W$ has a demand $d_{aw}$ and a stock $s_{aw}$ of article $a \in A$
- there can be a route between certain warehouses for certain articles
- the result of one article does not depend on the results for other articles, but warehouses can not be treated independently because of the edges in the network

$$
\begin{split}
\frac{\partial}{\partial s_{a_1, w_1}}\mathbb{E}\left[\sum_{a \in A}\sum_{w\in W}\mathrm{Sales}_{a, w}\right] 
=&\mathbb{E}\left[\frac{\partial}{\partial s_{a_1, w_1}}\sum_{w\in W}\mathrm{Sales}_{a_1, w}\right] 
\end{split}
$$
#### gradient approximation via max-flow min-cut
- for a single set of demand samples and stock level we have the following (the article is ignored here for simplicity)

$$
\frac{\partial}{\partial s_{w_1}}\sum_{w\in W}\mathrm{Sales}_{w} = \begin{cases}
1 & \text{if the stock is the bottle neck in the network} \\
0 & \text{if the demand is the bottle neck in the network} \\
\end{cases}
$$

we model the supply chain as a flow network:
1. **source edges (S→w):** capacity equals stock $s_w$​. (represents supply)
2. **sink edges (w→T):** capacity equals demand $d_w$​. (represents potential sales)
3. **internal edges:** capacity is infinite

- the derivative of total sales w.r.t stock $s_{w_1}$​​ is $1$ if and only if the stock edge $e_{\mathrm{source}\to w}$ restricts the flow (i.e., is part of the **minimum cut**)

$$
\frac{\partial}{\partial s_{a_1, w_1}}\mathbb{E}\left[\sum_{a \in A}\sum_{w\in W}\mathrm{Sales}_{a, w}\right] \approx \frac{1}{n}  \sum_{k=1}^n \mathbb{I}  \left[e_{\mathrm{source}\to w_1} \in \mathrm{min\ cut}(d_k)\right]
$$

**note on stability:** For the (common) edge case $s=d=0$, we set $s=ϵ$ (small positive value). This ensures that if demand arises $(d>0)$, the gradient correctly identifies the stock as the bottleneck, while if $d=0$, the gradient remains 0. 

#### why this approach? (decomposition)
- **scale:** we have a stochastic problem with 1,000+ articles and 60+ warehouses (~60,000 decision variables) with 1000 demand samples we would have tens of millions constraints in an LP
- **coupling:** we have global inventory and warehouse capacity constraints that apply to _all_ articles simultaneously. Therefore, we cannot simply split the entire optimization problem into 1,000 separate problem's
- **complexity:** A standard stochastic solver would be too large to solve directly given the network complexity
- **decomposition Strategy:**
    - while the _constraints_ are coupled, the _objective function_ (total sales) is separable. The sales of one article do not depend on the flow of another
    - this allows us to estimate the **gradients** efficiently by splitting the work: we solve the Max-Flow sub-problem for each article independently to get its local gradient
    - we then aggregate these gradients to perform a global update step by using **optimality condition for problems with diminishing marginal returns** that respects the global constraints
- **efficiency:** The max-flow problem is solvable in polynomial time and the fastest exact method for the gradient estimation in this situation, making it feasible to run ~1,000 monte carlo samples per iteration → 100 iterations possible in under 20 seconds

# ----

![[quantile regression#quantile regression]]
# anki

START
Basic
proof for the following

$$
\begin{split}
\frac{\partial}{\partial s}\mathrm{E}[\min\{s, D\}] 
&= 1-F(d) \\
\end{split}
$$

Back: 
### expected sales

$$
\begin{split}
\mathrm{E}[\min\{s, D\}] 
&= \int_0^\infty \min\{s, d\} f(d) dd \\
&=  \int_0^s d f(d) dd + s \int_s^\infty f(d) dd \\
&=  \int_0^s d f(d) dd + s \left(1-F(s)\right) \\
&=  s\cdot F(s) - \int_0^s  F(d) dd + s - sF(s) \\
&=  \underbrace{s}_{\int_0^s1 dd} - \int_0^s  F(d) dd  \\
&=  \int_0^s \left(1-F(d)\right) dd \\
\end{split}
$$

$$
\begin{split}
\int_0^s d f(d) dd
&= \left[d\cdot F(d)\right]_0^s - \int_0^s  F(d) dd \\
&= s\cdot F(s) - \int_0^s  F(d) dd \\
\end{split}
$$

#### gradient wrt the stock
- using the **fundamental theorem of calculus**: $G(x) = \int_0^xg(t)dt \Rightarrow G'(x)=g(x)$

$$
\begin{split}
\frac{\partial}{\partial s}\mathrm{E}[\min\{s, D\}] 
&= 1-F(s) \\
\end{split}
$$

Tags: mathematics WS2526
<!--ID: 1768678971884-->
END