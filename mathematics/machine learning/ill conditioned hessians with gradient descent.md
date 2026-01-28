### ill conditioned hessians with gradient descent
- using the [[quadratic loss model]] we have the following approximation for a point $\theta$ while the approximation is centered around the current parameter location $\theta_t$

$$
\begin{split}
\mathcal{R}(\theta) \approx \mathcal{R}(\theta_t) + g^\top (\theta - \theta_t) + \frac{1}{2} (\theta - \theta_t)^\top H (\theta - \theta_t) \\
\end{split}
$$

- with $\theta_{t+1} = \theta_t - \alpha g$ we have the following

$$
\begin{split}
\mathcal{R}(\theta - \alpha g) 
&\approx \mathcal{R}(\theta_t) + g^\top (\theta - \alpha g - \theta_t) + \frac{1}{2} (\theta - \alpha g - \theta_t)^\top H (\theta - \alpha g - \theta_t) \\
&\approx \mathcal{R}(\theta_t) - g^\top \alpha g + \frac{1}{2}  \alpha^2 g^\top H g  \\
\end{split}
$$

- in order to decrease the [[risk]] we want the following which means that its problematic if $g^\top H g$ is very large

$$
 \frac{1}{2}  \alpha g^\top H g <  g^\top  g  
$$

$$
\begin{split}
g^\top H g 
&= g^\top Q\Lambda Q^\top g \\
&= \sum_i \lambda_i g^\top Q_{(:, i)}  Q^\top_{(:, i)} g \\
&= \sum_i \lambda_i (g^\top Q_{(:, i)})^2 \\
\end{split}
$$

- if we have very large eigenvalues alpha needs to be very small $\alpha \propto \frac{1}{\lambda_{max}}$
- however if we have directions with small eigenvalues too there is almost no progress in these directions
- in the case the [[hessian]] is ill [[condition|conditioned]]

$$
\kappa(H) = \frac{|\lambda_{max}|}{|\lambda_{min}|} \gg 1
$$
#### intuition
- Geometrically, an ill-conditioned Hessian corresponds to a **narrow canyon** or ravine. In this landscape, standard gradient descent tends to **oscillate across the narrow direction** (steep walls) while making slow progress along the flat direction, resulting in poor convergence

#### second order optimization
- second order methods like the [[newton methode]] would not suffer from this problem because since the step contains the inverse of the [[hessian]] the step size is scaled in each direction individually based on its curvature
	→ balanced curvature corrected step

$$
\begin{split}
\nabla\mathcal{R}(\theta) &\approx  g  +   H d = 0 \\
\Rightarrow d &= -H^{-1}g \\
\Rightarrow \theta_{t+1}  &= \theta_{t} -H^{-1}g
\end{split}
$$

#### when using the adam optimizer
- the [[adam optimizer]] acts as a **Diagonal Quasi-Newton** method. It effectively approximates the scaling of the inverted [[hessian]] using the **accumulated squared gradients** to normalize the step sizes for each parameter individually
# --------

![[adam optimizer#adam optimizer]]

![[quadratic loss model#quadratic loss model]]


# anki

START
Basic
[[ill conditioned hessians with gradient descent]]
- why can this cause problems (with equations)
- what is happening intuitively?

Back: 
### ill conditioned hessians with gradient descent
- using the [[quadratic loss model]] we have the following approximation for a point $\theta$ while the approximation is centered around the current parameter location $\theta_t$

$$
\begin{split}
\mathcal{R}(\theta) \approx \mathcal{R}(\theta_t) + g^\top (\theta - \theta_t) + \frac{1}{2} (\theta - \theta_t)^\top H (\theta - \theta_t) \\
\end{split}
$$

- with $\theta_{t+1} = \theta_t - \alpha g$ we have the following

$$
\begin{split}
\mathcal{R}(\theta - \alpha g) 
&\approx \mathcal{R}(\theta_t) + g^\top (\theta - \alpha g - \theta_t) + \frac{1}{2} (\theta - \alpha g - \theta_t)^\top H (\theta - \alpha g - \theta_t) \\
&\approx \mathcal{R}(\theta_t) - g^\top \alpha g + \frac{1}{2}  \alpha^2 g^\top H g  \\
\end{split}
$$

- in order to decrease the [[risk]] we want the following which means that its problematic if $g^\top H g$ is very large

$$
 \frac{1}{2}  \alpha g^\top H g <  g^\top  g  
$$

$$
\begin{split}
g^\top H g 
&= g^\top Q\Lambda Q^\top g \\
&= \sum_i \lambda_i g^\top Q_{(:, i)}  Q^\top_{(:, i)} g \\
&= \sum_i \lambda_i (g^\top Q_{(:, i)})^2 \\
\end{split}
$$

- if we have very large eigenvalues alpha needs to be very small $\alpha \propto \frac{1}{\lambda_{max}}$
- however if we have directions with small eigenvalues too there is almost no progress in these directions
- in the case the [[hessian]] is ill [[condition|conditioned]]

$$
\kappa(H) = \frac{|\lambda_{max}|}{|\lambda_{min}|} \gg 1
$$
#### intuition
- Geometrically, an ill-conditioned Hessian corresponds to a **narrow canyon** or ravine. In this landscape, standard gradient descent tends to **oscillate across the narrow direction** (steep walls) while making slow progress along the flat direction, resulting in poor convergence

Tags: mathematics WS2526
<!--ID: 1769619800846-->
END


START
Basic
[[ill conditioned hessians with gradient descent]]
- show why second order optimization methods don't suffer from ill conditioned hessians
- what happens when using the [[adam optimizer]]? (no proof)

Back: 
#### second order optimization
- second order methods like the [[newton methode]] would not suffer from this problem because since the step contains the inverse of the [[hessian]] the step size is scaled in each direction individually based on its curvature
	→ balanced curvature corrected step

$$
\begin{split}
\nabla\mathcal{R}(\theta) &\approx  g  +   H d = 0 \\
\Rightarrow d &= -H^{-1}g \\
\Rightarrow \theta_{t+1}  &= \theta_{t} -H^{-1}g
\end{split}
$$
#### when using the adam optimizer

- the [[adam optimizer]] acts as a **Diagonal Quasi-Newton** method. It effectively approximates the scaling of the inverted [[hessian]] using the **accumulated squared gradients** to normalize the step sizes for each parameter individually
### ill conditioned hessians with gradient descent
- using the [[quadratic loss model]] we have the following approximation for a point $\theta$ while the approximation is centered around the current parameter location $\theta_t$

$$
\begin{split}
\mathcal{R}(\theta) \approx \mathcal{R}(\theta_t) + g^\top (\theta - \theta_t) + \frac{1}{2} (\theta - \theta_t)^\top H (\theta - \theta_t) \\
\end{split}
$$

- with $\theta_{t+1} = \theta_t - \alpha g$ we have the following

$$
\begin{split}
\mathcal{R}(\theta - \alpha g) 
&\approx \mathcal{R}(\theta_t) + g^\top (\theta - \alpha g - \theta_t) + \frac{1}{2} (\theta - \alpha g - \theta_t)^\top H (\theta - \alpha g - \theta_t) \\
&\approx \mathcal{R}(\theta_t) - g^\top \alpha g + \frac{1}{2}  \alpha^2 g^\top H g  \\
\end{split}
$$

- in order to decrease the [[risk]] we want the following which means that its problematic if $g^\top H g$ is very large

$$
 \frac{1}{2}  \alpha g^\top H g <  g^\top  g  
$$

$$
\begin{split}
g^\top H g 
&= g^\top Q\Lambda Q^\top g \\
&= \sum_i \lambda_i g^\top Q_{(:, i)}  Q^\top_{(:, i)} g \\
&= \sum_i \lambda_i (g^\top Q_{(:, i)})^2 \\
\end{split}
$$

- if we have very large eigenvalues alpha needs to be very small $\alpha \propto \frac{1}{\lambda_{max}}$
- however if we have directions with small eigenvalues too there is almost no progress in these directions
- in the case the [[hessian]] is ill [[condition|conditioned]]

$$
\kappa(H) = \frac{|\lambda_{max}|}{|\lambda_{min}|} \gg 1
$$
#### intuition
- Geometrically, an ill-conditioned Hessian corresponds to a **narrow canyon** or ravine. In this landscape, standard gradient descent tends to **oscillate across the narrow direction** (steep walls) while making slow progress along the flat direction, resulting in poor convergence

Tags: mathematics WS2526
<!--ID: 1769619800848-->
END