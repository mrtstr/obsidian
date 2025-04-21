### linear regression
- given real valued [[random variable|random variables]] $Y_1, ..., Y_n$ that satisfy the following equation
- with [[white noise]] $e_i$
- with fewer parameters that equations $K < n$
- with a design matrix $X \in \mathbb{R}^{n \times k}$ with a full [[rank]] $rank(A) = k$

$$
\begin{split}
Y 
&= \left(\begin{matrix} Y_1 \\ ...\\ Y_n \end{matrix} \right) \\
&= \sum_{i=1}^k \beta_i X_i + \left(\begin{matrix} e_1 \\ ...\\ e_n \end{matrix} \right) \ \\
&= A \beta + e \ \\
\end{split}
$$

- there always exists [[linear least squares]] solutions $\beta_{LS} = \left(A^\top A\right)^{-1} A^\top Y$ and its unique
- $\beta_{LS}$ is unbiased

### high dimensional linear regression
- for the high dimensional case there exists a lower dimensional matrix $A_k$ such that $\beta_{LS} = \left(A_k^\top A_k\right)^{-1} A_k^\top Y$ still optimizes the [[linear least squares]]

$$
\beta = \mathrm{argmin} ||A_kc - Y||_2^2
$$
- $rank(A_k) = k$


### rige regression
- rige regression is penalized least squares with $l_2$ penalty term 
- generally the problem has the solution $A^\top A b = A^\top Y$ but in the case $K>n$ $A^\top A$ is not [[inverse matrix|invertable]] 
- since $A^\top A$ is still a positive semi definite matrix $A^\top A + \lambda I_k$ is positive definite and thus invertible

$$
\begin{split}
\beta_{rige, \lambda} 
&= \mathrm{argmin} ||Y - Ab||^2 + \lambda ||b||^2 \\
&= \left(A^\top A + \lambda I_k\right)^{-1} A^\top Y \\
\end{split}
$$

### lasso regression
- the lasso regression is penalized least squares with $l_1$ penalty term 

$$
\begin{split}
\beta_{lasso, \lambda} 
&= \mathrm{argmin} \frac{1}{n}||Y - Ab||^2 + \lambda ||b||_1 \\
\end{split}
$$
# -----------------------------

![[linear least squares#linear least squares]]

![[linear least squares#normal equation]]

![[linear least squares#existence of a solution]]