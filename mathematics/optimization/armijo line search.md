### condition for monotoneity
- for every point $x\in \mathbb{R}^m$ and a [[descent direction]] $d$ with $\nabla f(x)^\top d < 0$ a setpsize $\alpha \in (0,1]$ with $f(x + \alpha d) < f(x)$ gives a sequence of monotonically decreasing function values $\left\{ f\left(x^{(k)}\right)\right\}$

### armijo condition
- condition for a sufficiently large decending step size
- based on a tuning parameter $\gamma \in (0,1]$ 
$$
f(x + \alpha d) < f(x) + \gamma \alpha \nabla f(x)^\top d
$$
- to calculate a stepsize that satsifies the condition there are multiple methods e.g. select $\beta \in (0, 1)$ and try $\alpha = \beta^i$ until $\alpha$ satisfies the armijo condition 

### optimal step size
- condition for optimal step size (not for practicle use because computantionally to expensive)
- with the direction being the negative [[gradient]] $d =\nabla f\left(x^{(k)}\right)$ the optimal step size is reachen when the [[gradient]] in the point $x^{(k)}$ and $x^{(k+1)}$ are [[orthogonal]] to each other

$$
\begin{split}
\alpha^* &= arg\min f\left(x^{(k)} + \alpha d\right) \\
0 
&= \frac{d}{d\alpha} f\left(x^{(k)} + \alpha d \right) \\
&= \nabla f\left(x^{(k)} + \alpha d \right)^\top d \\
&= \nabla f\left(x^{(k+1)}\right)^\top \nabla f\left(x^{(k)}\right) \\
\end{split}
$$

# ------------------------

![[gradient descent#gradient descent]]

# anki

START
Basic
[[gradient descent]] step
- which condition needs the step size satisfy to garantee monotine decreasing function values?
- which condition needs the step size satisfy for a suficiently large decent?
- how to find such a set size?
Back: 
### condition for monotoneity
- for every point $x\in \mathbb{R}^m$ and a [[descent direction]] $d$ with $\nabla f(x)^\top d < 0$ a setpsize $\alpha \in (0,1]$ with $f(x + \alpha d) < f(x)$ gives a sequence of monotonically decreasing function values $\left\{ f\left(x^{(k)}\right)\right\}$

### armijo condition
- condition for a sufficiently large decending step size
- based on a tuning parameter $\gamma \in (0,1]$ 
$$
f(x + \alpha d) < f(x) + \gamma \alpha \nabla f(x)^\top d
$$
- to calculate a stepsize that satsifies the condition there are multiple methods e.g. select $\beta \in (0, 1)$ and try $\alpha = \beta^i$ until $\alpha$ satisfies the armijo condition 


______________________________

### gradient descent
- iterative algorithm for solving continious optimization problems using the first order [[derivative]]
- [[gradient descent]] is a [[general descent method]] where we use the negative [[gradient]] $\nabla f\left(x^{(k)}\right)$ as direction which is the direction of the steeptest desecent in point $x^{(k)}$
- we choose a stepsize $\alpha^{(k)} \in (0,1]$

$$
x^{(k+1)} = x^{(k)} - \alpha^{(k)} \nabla f\left(x^{(k)}\right)
$$
### optimal step size
- condition for optimal step size (not for practicle use because computantionally to expensive)
- with the direction being the negative [[gradient]] $d =\nabla f\left(x^{(k)}\right)$ the optimal step size is reachen when the [[gradient]] in the point $x^{(k)}$ and $x^{(k+1)}$ are [[orthogonal]] to each other

$$
\begin{split}
\alpha^* &= arg\min f\left(x^{(k)} + \alpha d\right) \\
0 
&= \frac{d}{d\alpha} f\left(x^{(k)} + \alpha d \right) \\
&= \nabla f\left(x^{(k)} + \alpha d \right)^\top d \\
&= \nabla f\left(x^{(k+1)}\right)^\top \nabla f\left(x^{(k)}\right) \\
\end{split}
$$
- this can be iterpreted as seaching the [[minimum]] of the [[linear aproximation]] of $f$ in each point

Tags: mathematics
<!--ID: 1721056221173-->
END


START
Basic
[[gradient descent]] step
- which condition needs the step size satisfy to be the optimal step size?
- how to find the step size in practice?

Back: 
### optimal step size
- condition for optimal step size (not for practicle use because computantionally to expensive)
- with the direction being the negative [[gradient]] $d =\nabla f\left(x^{(k)}\right)$ the optimal step size is reachen when the [[gradient]] in the point $x^{(k)}$ and $x^{(k+1)}$ are [[orthogonal]] to each other

$$
\begin{split}
\alpha^* &= arg\min f\left(x^{(k)} + \alpha d\right) \\
0 
&= \frac{d}{d\alpha} f\left(x^{(k)} + \alpha d \right) \\
&= \nabla f\left(x^{(k)} + \alpha d \right)^\top d \\
&= \nabla f\left(x^{(k+1)}\right)^\top \nabla f\left(x^{(k)}\right) \\
\end{split}
$$

### armijo condition
- condition for a sufficiently large decending step size
- based on a tuning parameter $\gamma \in (0,1]$ 
$$
f(x + \alpha d) < f(x) + \gamma \alpha \nabla f(x)^\top d
$$
- to calculate a stepsize that satsifies the condition there are multiple methods e.g. select $\beta \in (0, 1)$ and try $\alpha = \beta^i$ until $\alpha$ satisfies the armijo condition

______________________________

### gradient descent
- iterative algorithm for solving continious optimization problems using the first order [[derivative]]
- [[gradient descent]] is a [[general descent method]] where we use the negative [[gradient]] $\nabla f\left(x^{(k)}\right)$ as direction which is the direction of the steeptest desecent in point $x^{(k)}$
- we choose a stepsize $\alpha^{(k)} \in (0,1]$

$$
x^{(k+1)} = x^{(k)} - \alpha^{(k)} \nabla f\left(x^{(k)}\right)
$$

- this can be iterpreted as seaching the [[minimum]] of the [[linear aproximation]] of $f$ in each point

Tags: mathematics
<!--ID: 1721056221178-->
END