### kl divergence

$$
D_{KL} (P || Q) = \int_\mathbb{R} p(x) \log \left( \frac{p(x)}{q(x)} \right) dx
$$

### relationship to the entropy

$$
\begin{split}
D_{KL} (P || Q) 
&= \int_\mathbb{R} p(x) \log \left( \frac{p(x)}{q(x)} \right) dx \\
&= \int_\mathbb{R} p(x) \log(p(x)) dx - \int_\mathbb{R} p(x) \log(q(x)) dx \\
&= H(P) - \int_\mathbb{R} p(x) \log(q(x)) dx \\
\end{split}
$$


![[entropy#differential entropy]]