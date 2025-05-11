### quadratic forms of random variables
- give a [[symmetric]] non-random [[matrix]] $A$ and a [[random vector]] $X$
- let $\Sigma = \mathbb{VAR}[X]$ and $\mathrm{m}=\mathbb{E}[X]$

____________

$$
\begin{split}
\mathbb{E}\left[X^\top A X\right] 
&= \mathrm{TR}\left(A\Sigma\right) + \mathrm{m}^\top A \mathrm{m}
\end{split}
$$


$$
\begin{split}
X^\top A X
&= \left(X + \mathrm{m} - \mathrm{m} \right)^\top A \left(X + \mathrm{m} - \mathrm{m} \right) \\
&= \left(X  - \mathrm{m} \right)^\top A \left(X - \mathrm{m} \right) + \mathrm{m}^\top A \mathrm{m} \\
&= \mathrm{TR}\left(\left(X  - \mathrm{m} \right)^\top A \left(X - \mathrm{m} \right)\right) + \mathrm{m}^\top A \mathrm{m} \\
&= \mathrm{TR}\left( A \left(X - \mathrm{m} \right) \left(X  - \mathrm{m} \right)^\top\right) + \mathrm{m}^\top A \mathrm{m} \\
\mathbb{E}\left[X^\top A X\right]
&= \mathbb{E}\left[\mathrm{TR}\left( A \left(X - \mathrm{m} \right) \left(X  - \mathrm{m} \right)^\top\right)\right] + \mathrm{m}^\top A \mathrm{m} \\
&= \mathrm{TR}\left( A \mathbb{E}\left[\left(X - \mathrm{m} \right) \left(X  - \mathrm{m} \right)^\top\right]\right) + \mathrm{m}^\top A \mathrm{m} \\
&= \mathrm{TR}\left(A\Sigma\right) + \mathrm{m}^\top A \mathrm{m} \\
\end{split}
$$

_________

$$
\begin{split}
\mathbb{E}\left[X^\top  X\right] 
&= \Sigma + \mathrm{m}\mathrm{m}^\top \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[X^\top  X\right] 
&= \mathbb{E}\left[\left(X + \mathrm{m} - \mathrm{m} \right)^\top  \left(X + \mathrm{m} - \mathrm{m} \right)\right]  \\
&= \mathbb{E}\left[\left(X  - \mathrm{m} \right)^\top  \left(X  - \mathrm{m} \right)\right] + \mathrm{m}\mathrm{m}^\top \\
&= \Sigma + \mathrm{m}\mathrm{m}^\top \\
\end{split}
$$


_________

$$
\begin{split}
\mathbb{E}\left[X^\top \mathrm{a}^\top  X\right] 
&= \left(\Sigma + \mathrm{m}\mathrm{m}^\top \right)\mathrm{a} \\
\end{split}
$$

