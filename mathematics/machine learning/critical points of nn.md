## critical points of nn
### local minima
- when using [[neural network]] there are always multiple local minima
- with $L-1$ hidden layers with width we can always construct at least $n!^{L-1}$ equivalent local minima by switching weights
- when using [[rectified linear unit]] [[activation function]] we can even construct infinite local minima
- equivalent local minima are not problematic but local minima with much larger [[risk]] then the global minimum are problematic 
- under suitable conditions (**high dimensional**, **over parameterized**) it can be shown that **all local minima are almost global**
#### local maxima
- only problematic when the initial value is exactly the maximum (very unlikely)
### saddle points
- problematic because the gradients vanish
- the [[hessian]] has positive and negative [[eigenvalue]]
- [[stochastic gradient descent]] and perturbed [[gradient descent]] can escape saddle points
- [[momentum]] can also help get over saddle points when not initialized at the saddle point
- [[newton methode]] and [[full gradient descent]] can't escape because the saddle point is a critical point of the [[quadratic loss model]] and the gradient vanishes

![[ill conditioned hessians with gradient descent#ill conditioned hessians with gradient descent]]


# anki

START
Basic
[[critical points of nn]]: local minima
- are they unique?
- how many of them always exist?
- are they problematic? /  when are they problematic?

Back: 

### local minima
- when using [[neural network]] there are always multiple local minima
- with $L-1$ hidden layers with width we can always construct at least $n!^{L-1}$ equivalent local minima by switching weights
- when using [[rectified linear unit]] [[activation function]] we can even construct infinite local minima
- equivalent local minima are not problematic but local minima with much larger [[risk]] then the global minimum are problematic 
- under suitable conditions (**high dimensional**, **over parameterized**) it can be shown that **all local minima are almost global**
#### local maxima
- only problematic when the initial value is exactly the maximum (very unlikely)
### saddle points
- problematic because the gradients vanish
- the [[hessian]] has positive and negative [[eigenvalue]]
- [[stochastic gradient descent]] and perturbed [[gradient descent]] can escape saddle points
- [[momentum]] can also help get over saddle points when not initialized at the saddle point
- [[newton methode]] and [[full gradient descent]] can't escape because the saddle point is a critical point of the [[quadratic loss model]] and the gradient vanishes

___________
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
<!--ID: 1769619800835-->
END



START
Basic
[[critical points of nn]]: 
- can [[gradient descent]] converge at a local maximum?

Back: 

### local minima
- when using [[neural network]] there are always multiple local minima
- with $L-1$ hidden layers with width we can always construct at least $n!^{L-1}$ equivalent local minima by switching weights
- when using [[rectified linear unit]] [[activation function]] we can even construct infinite local minima
- equivalent local minima are not problematic but local minima with much larger [[risk]] then the global minimum are problematic 
- under suitable conditions (**high dimensional**, **over parameterized**) it can be shown that **all local minima are almost global**
#### local maxima
- only problematic when the initial value is exactly the maximum (very unlikely)
### saddle points
- problematic because the gradients vanish
- the [[hessian]] has positive and negative [[eigenvalue]]
- [[stochastic gradient descent]] and perturbed [[gradient descent]] can escape saddle points
- [[momentum]] can also help get over saddle points when not initialized at the saddle point
- [[newton methode]] and [[full gradient descent]] can't escape because the saddle point is a critical point of the [[quadratic loss model]] and the gradient vanishes

___________
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
<!--ID: 1769619800840-->
END



START
Basic
[[critical points of nn]]: saddle points
- why are they problemetic?
- how does the [[hessian]] look like?
- 2 algorithms that can escape and 2 algorithms that can't escape
- does [[moments]] always help?


Back: 

### local minima
- when using [[neural network]] there are always multiple local minima
- with $L-1$ hidden layers with width we can always construct at least $n!^{L-1}$ equivalent local minima by switching weights
- when using [[rectified linear unit]] [[activation function]] we can even construct infinite local minima
- equivalent local minima are not problematic but local minima with much larger [[risk]] then the global minimum are problematic 
- under suitable conditions (**high dimensional**, **over parameterized**) it can be shown that **all local minima are almost global**
#### local maxima
- only problematic when the initial value is exactly the maximum (very unlikely)
### saddle points
- problematic because the gradients vanish
- the [[hessian]] has positive and negative [[eigenvalue]]
- [[stochastic gradient descent]] and perturbed [[gradient descent]] can escape saddle points
- [[momentum]] can also help get over saddle points when not initialized at the saddle point
- [[newton methode]] and [[full gradient descent]] can't escape because the saddle point is a critical point of the [[quadratic loss model]] and the gradient vanishes

___________
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
<!--ID: 1769619800842-->
END
