### linear convergent
- a [[convergence|convergent]] sequence $\left\{x^{(k)}\right\}$ with a limit $x^*$ is **linearly convergent** if the following is true

$$
\exists K: \exists \kappa \in [0,1]: \forall k > K: \frac{\left|\left| x^{(k+1)} -x^* \right|\right|}{\left|\left| x^{(k)} -x^* \right|\right|} \leq \kappa
$$
### superlinear convergent
- a [[convergence|convergent]] sequence $\left\{x^{(k)}\right\}$ with a limit $x^*$ is **superlinear convergent** if there exists a linear converging sequence $\kappa^{(k)} \xrightarrow{k \to \infty} 0$ and $\kappa^{(k)} \in [0,1]:$ such that the following is true

$$
\exists K: \forall k > K: \frac{\left|\left| x^{(k+1)} -x^* \right|\right|}{\left|\left| x^{(k)} -x^* \right|\right|} \leq \kappa^{(k)}
$$
### quadratic convergent
- a [[convergence|convergent]] sequence $\left\{x^{(k)}\right\}$ with a limit $x^*$ is **quadratic convergent** if the following is true

$$
\exists K: \exists \omega \in [0,\infty): \forall k > K: \frac{\left|\left| x^{(k+1)} -x^* \right|\right|}{\left|\left| x^{(k)} -x^* \right|\right|^2} \leq \omega
$$


# -----------------

![[convergence#convergence in a normed space $ left(V, +, cdot, cdot right)$]]


START
Basic
definitions for 
- linear convergent
- superlinear convergent
- quadratic convergent
Back: 
### linear convergent
- a [[convergence|convergent]] sequence $\left\{x^{(k)}\right\}$ with a limit $x^*$ is **linearly convergent** if the following is true

$$
\exists K: \exists \kappa \in [0,1]: \forall k > K: \frac{\left|\left| x^{(k+1)} -x^* \right|\right|}{\left|\left| x^{(k)} -x^* \right|\right|} \leq \kappa
$$
### superlinear convergent
- a [[convergence|convergent]] sequence $\left\{x^{(k)}\right\}$ with a limit $x^*$ is **superlinear convergent** if there exists a linear converging sequence $\kappa^{(k)} \xrightarrow{k \to \infty} 0$ and $\kappa^{(k)} \in [0,1]:$ such that the following is true

$$
\exists K: \forall k > K: \frac{\left|\left| x^{(k+1)} -x^* \right|\right|}{\left|\left| x^{(k)} -x^* \right|\right|} \leq \kappa^{(k)}
$$
### quadratic convergent
- a [[convergence|convergent]] sequence $\left\{x^{(k)}\right\}$ with a limit $x^*$ is **quadratic convergent** if the following is true

$$
\exists K: \exists \omega \in [0,\infty): \forall k > K: \frac{\left|\left| x^{(k+1)} -x^* \right|\right|}{\left|\left| x^{(k)} -x^* \right|\right|^2} \leq \omega
$$

_________________

### convergence in a [[normed space]] $\left(V, +, \cdot, ||\cdot||\right)$
- given a [[sequence]] $v_n \in V$  
- $v_n$ is converging against $v^*$ if the following is true

$$
\begin{split}
&\forall \epsilon>0: \exists N \in \mathbb{N}: n \geq N \Rightarrow ||a_n - a^*|| \leq \epsilon \\
&\Leftrightarrow \\
&||v_n - v^* || \xrightarrow{n \rightarrow \infty} 0
\end{split}
$$

Tags: mathematics
<!--ID: 1721056221185-->
END