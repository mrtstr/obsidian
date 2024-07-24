### penalty methods CNLP
- a [[constraint optimization problem]] can be transformed into a [[unconstraint optimization problem]] by replacing the contraint functions with a pentaly term $\phi(x)$
$$
\phi_1(x) = ||g(x)||_1 + ||[h(x)]^-||_1
$$
- with a function that replaces the positve entries of $h$ with zero and keeps only the negative ones $[h(x)]^-= \left(\min(h(x)_i, 0)\right)_{i \in [k]}$
- the new optimization problems looks like the following with a penalty factor $\theta>0$ 
- with a high enough $\theta$ this will result in a [[feasible set|feasible]] solution
$$
\begin{split}
\min_{x \in \mathbb{R}^m} &f(x) + \theta \cdot \phi(x) \\
\end{split}
$$
- since $\phi_1(x)$ is not [[differentiabe]] we can use $\phi_2(x)$ instead, but this does not lead nessearily to an [[feasible set|feasible]] solution

$$
\phi_2(x) = ||g(x)||_2^2 + ||[h(x)]^-||_2^2
$$

# --------------------------

![[constraint optimization problem#constraint optimization problem]]


START
Basic
[[penalty methods CNLP]]
- definition
- potential problem and how it can be solved
Back: 
### penalty methods CNLP
- a [[constraint optimization problem]] can be transformed into a [[unconstraint optimization problem]] by replacing the contraint functions with a pentaly term $\phi(x)$
$$
\phi_1(x) = ||g(x)||_1 + ||[h(x)]^-||_1
$$
- with a function that replaces the positve entries of $h$ with zero and keeps only the negative ones $[h(x)]^-= \left(\min(h(x)_i, 0)\right)_{i \in [k]}$
- the new optimization problems looks like the following with a penalty factor $\theta>0$ 
- with a high enough $\theta$ this will result in a [[feasible set|feasible]] solution
$$
\begin{split}
\min_{x \in \mathbb{R}^m} &f(x) + \theta \cdot \phi(x) \\
\end{split}
$$
- since $\phi_1(x)$ is not [[differentiabe]] we can use $\phi_2(x)$ instead, but this does not lead nessearily to an [[feasible set|feasible]] solution

$$
\phi_2(x) = ||g(x)||_2^2 + ||[h(x)]^-||_2^2
$$

Tags: mathematics
<!--ID: 1721748376590-->
END