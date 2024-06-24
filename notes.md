


$$
\begin{split}
\tilde{T_n^*} = \frac{n+1}{n} \tilde{T_n}  \\
\end{split}
$$
$$
\begin{split}
\mathbb{VAR}_\vartheta\left[\tilde{T_n}\right]  
&= \frac{\vartheta^2 n}{(n+2)(n+1)^2}    \\
\end{split}
$$
$$
\begin{split}
\mathbb{VAR}_\vartheta\left[\tilde{T_n^*}\right]  
&= \mathbb{VAR}_\vartheta\left[\frac{n+1}{n} \tilde{T_n} \right]   \\
&= \frac{(n+1)^2}{n^2} \mathbb{VAR}_\vartheta\left[ \tilde{T_n} \right]   \\
&= \frac{(n+1)^2}{n^2} \frac{\vartheta^2 n}{(n+2)(n+1)^2}    \\
&= \frac{\vartheta^2}{n(n+2)}    \\
\end{split}
$$
var_estimator_script

### proof
- to show that the given condition is sufficient to show that $X$ is a [[measurable function]] we will prove the following
$$
\begin{split}
\forall x \in \mathbb{R}: &X^{-1}\left((-\infty, x]\right)  \in \mathcal{A} \\
&\Rightarrow \\
\forall x < y \in \mathbb{R}: &X^{-1}\left([y, x]\right)  \in \mathcal{A} \\
&\Rightarrow \\
\forall E \subseteq \mathbb{R}: &X^{-1}\left(E\right)  \in \mathcal{A}
\end{split}
$$
- first part
$$
\begin{split}
&\forall x \in \mathbb{R} \forall \epsilon > 0 \in \mathbb{R}: X^{-1}\left((-\infty, x]\right)  \in \mathcal{A} \land X^{-1}\left((-\infty, x + \epsilon]\right)  \in \mathcal{A} \\
&\Rightarrow X^{-1}\left((-\infty, y]\right) \setminus X^{-1}\left((-\infty, x]\right)  \in \mathcal{A} \qquad \text{(a sigma algbra is closed over difference)} \\
&\Rightarrow\forall x < y \in \mathbb{R}:  X^{-1}\left([x, y]\right)   \in \mathcal{A} \\
\end{split}
$$
- the second part can be proved because a [[sigma algebra]] is closed over [[union]]
