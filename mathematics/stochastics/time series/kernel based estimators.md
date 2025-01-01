### kernel based estimators
- kernel density estimator $\hat f(x)$

$$
\hat f(x)=\frac{1}{nh} \sum_{i=1}^n K\left(\frac{x-x_i}{h}\right)
$$


$$
\begin{split}
 1 &\geq \left|\frac{\frac{t}{n} - u}{h}\right| \\
 h &\geq \left|\frac{t}{n} - u\right| \\
 h &\geq d\left(\frac{t}{n}, u\right) \\
\end{split}
$$


$$
\hat X_t=\frac{1}{nh} \sum_{i=1}^n X_{t_i} K\left(\frac{t-t_i}{h}\right)
$$