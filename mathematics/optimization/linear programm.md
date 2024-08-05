### linear primal programm
- [[constraint optimization problem]] with a [[linear map|linear]] objective function and [[linear map|linear]] contraint functions
- every [[linear map]] is [[convex]] thus every [[local minimum]] is a [[minimum|global minimum]] and 
- approach: first feasable then find optimal
### canonical form

$$
\begin{split}
\min_{x \in \mathbb{R}^m}& \quad  c^\top x \\
\mathrm{s.t.} \: &Ax \geq b \\
\end{split}
$$

- note: equallity constraints can be expressed as two inequallity constraints

### standard form
- [[linear programm]] that satisfies the following 3 conditions is in **standard form**
- the standard form is the stating point for the simplex algorithm
- used for dualizing a [[linear programm]]

1) non negativity of all varibales $x$
2) all remaining constraints are expressed as equality constrains
3) the right side vector $b$ is none negative
$$
\begin{split}
\min_{x \in \mathbb{R}^m}& \quad  c^\top x \\
\mathrm{s.t.} \: &Ax = b \\
&x \geq 0 \\
\end{split}
$$

#### converting to standard form
- greater or equal constraints $Ax \geq b$ are converted to $Ax - s = b$ with slack variable $s \geq 0$
- less or equal constraints $Ax \leq b$ are converted to $Ax + s = b$ with slack variable $s \geq 0$
- in case $b_i<0$ is negative both sides are multipled with $-1$  
- conditions $x_i \geq 0$ are transformed by subsituting $x_i$ with $y_i=-x_i$
- add $x\geq0$ condition (no details)

### linear dual programm
- given the following primal linear programm in canonical form with [[matrix]] $A\in \mathbb{R}^{n \times m}$
- approach: first optimal then feasability

$$
\begin{split}
\min_{x \in \mathbb{R}^m}& \quad  c^\top x \\
\mathrm{s.t.} \: &Ax \geq b \\
&x \geq 0 \\
\end{split}
$$
- there exists the following dual problem

$$
\begin{split}
\max_{x \in \mathbb{R}^m}& \quad  p^\top b \\
\mathrm{s.t.} \: &p^\top A \leq c^\top \\
&p\geq 0 \\
\end{split}
$$

#### transfomration primal to dual in general form
- the primal objective function $\min c^\top x$ becomes $\max p^\top b$
- for each constraint regading $x_j$ a constraint function is introduced based on its relation column vector $A_{(*, j)}$
	- $x_j \geq 0$ becomes $p^\top A_{(*, j)} \leq c_i$
	- $x_j \leq 0$ becomes $p^\top A_{(*, j)} \geq c_i$
	- $x=0$ becomes $p^\top A_{(*, j)} = c_i$
- for each row vector $A_{(i, *)}$ that is representing a constraint function a constraint regrading $p_i$ in introduced
	- $A_{(i, *)}x \geq b_i$ becomes $p_i\geq 0$
	- $A_{(i, *)}x \leq b_i$ becomes $p_i\leq 0$
	- $A_{(i, *)}x = b_i$ becomes $p_i=free$

#### interpretation
- the variable $p$ can be interpreted as
#### weak duality
- every feasible solution to the dual problem has an objective value lessor equal to that of every to that of ever solution of the probal problem
$$
c^\top x \geq p^\top b
$$

#### strong duality
- let $x^*$ and $p^*$ be optimal solutions for the primal and optimal problem then they have the same objective function

$$
c^\top x = p^\top b
$$

#### primal dual slackness
- let $x^*$ and $p^*$ be optimal solutions for the primal and optimal problem then they have the same objective function

$$
\begin{split}
p_i\left(A_{(i, *)} x - b_i\right) = 0 \\
\left(c_j - p^\top A_{(*, j)} \right)x_j = 0 \\
\end{split}
$$
# anki

START
Basic
[[linear programm]]
- two forms
Back: 
### linear primal programm
- [[constraint optimization problem]] with a [[linear map|linear]] objective function and [[linear map|linear]] contraint functions
- every [[linear map]] is [[convex]] thus every [[local minimum]] is a [[minimum|global minimum]] and 

### canonical form

$$
\begin{split}
\min_{x \in \mathbb{R}^m}& \quad  c^\top x \\
\mathrm{s.t.} \: &Ax \geq b \\
\end{split}
$$

- note: equallity constraints can be expressed as two inequallity constraints

### standard form
- [[linear programm]] that satisfies the following 3 conditions is in **standard form**
- the standard form is the stating point for the simplex algorithm
- used for dualizing a [[linear programm]]

1) non negativity of all varibales $x$
2) all remaining constraints are expressed as equality constrains
3) the right side vector $b$ is none negative
$$
\begin{split}
\min_{x \in \mathbb{R}^m}& \quad  c^\top x \\
\mathrm{s.t.} \: &Ax = b \\
&x \geq 0 \\
\end{split}
$$

Tags: mathematics linear_algebra
<!--ID: 1722798041219-->
END


START
Basic
[[linear programm]]
- how to convert ab problem from canonical form to standard form
Back: 
### standard form
- [[linear programm]] that satisfies the following 3 conditions is in **standard form**
- the standard form is the stating point for the simplex algorithm
- used for dualizing a [[linear programm]]

1) non negativity of all varibales $x$
2) all remaining constraints are expressed as equality constrains
3) the right side vector $b$ is none negative
$$
\begin{split}
\min_{x \in \mathbb{R}^m}& \quad  c^\top x \\
\mathrm{s.t.} \: &Ax = b \\
&x \geq 0 \\
\end{split}
$$

### linear primal programm
- [[constraint optimization problem]] with a [[linear map|linear]] objective function and [[linear map|linear]] contraint functions
- every [[linear map]] is [[convex]] thus every [[local minimum]] is a [[minimum|global minimum]] and 

### canonical form

$$
\begin{split}
\min_{x \in \mathbb{R}^m}& \quad  c^\top x \\
\mathrm{s.t.} \: &Ax \geq b \\
\end{split}
$$

- note: equallity constraints can be expressed as two inequallity constraints

### standard form
- [[linear programm]] that satisfies the following 3 conditions is in **standard form**
- the standard form is the stating point for the simplex algorithm
- used for dualizing a [[linear programm]]

1) non negativity of all varibales $x$
2) all remaining constraints are expressed as equality constrains
3) the right side vector $b$ is none negative
$$
\begin{split}
\min_{x \in \mathbb{R}^m}& \quad  c^\top x \\
\mathrm{s.t.} \: &Ax = b \\
&x \geq 0 \\
\end{split}
$$

Tags: mathematics linear_algebra
<!--ID: 1722798041224-->
END



START
Basic
build the dual problem for following primal linear programm in canonical form


$$
\begin{split}
\min_{x \in \mathbb{R}^m}& \quad  c^\top x \\
\mathrm{s.t.} \: &Ax \geq b \\
&x \geq 0 \\
\end{split}
$$

Back: 

### linear dual programm
- given the following primal linear programm in canonical form with [[matrix]] $A\in \mathbb{R}^{n \times m}$

$$
\begin{split}
\min_{x \in \mathbb{R}^m}& \quad  c^\top x \\
\mathrm{s.t.} \: &Ax \geq b \\
&x \geq 0 \\
\end{split}
$$
- there exists the following dual problem

$$
\begin{split}
\max_{x \in \mathbb{R}^m}& \quad  p^\top b \\
\mathrm{s.t.} \: &p^\top A \leq c^\top \\
&p\geq 0 \\
\end{split}
$$

#### transfomration primal to dual in general form
- the primal objective function $\min c^\top x$ becomes $\max p^\top b$
- for each constraint regading $x_j$ a constraint function is introduced based on its relation column vector $A_{(*, j)}$
	- $x_j \geq 0$ becomes $p^\top A_{(*, j)} \leq c_i$
	- $x_j \leq 0$ becomes $p^\top A_{(*, j)} \geq c_i$
	- $x=0$ becomes $p^\top A_{(*, j)} = c_i$
- for each row vector $A_{(i, *)}$ that is representing a constraint function a constraint regrading $p_i$ in introduced
	- $A_{(i, *)}x \geq b_i$ becomes $p_i\geq 0$
	- $A_{(i, *)}x \leq b_i$ becomes $p_i\leq 0$
	- $A_{(i, *)}x = b_i$ becomes $p_i=free$


_____________________

### linear primal programm
- [[constraint optimization problem]] with a [[linear map|linear]] objective function and [[linear map|linear]] contraint functions
- every [[linear map]] is [[convex]] thus every [[local minimum]] is a [[minimum|global minimum]] and 

### canonical form

$$
\begin{split}
\min_{x \in \mathbb{R}^m}& \quad  c^\top x \\
\mathrm{s.t.} \: &Ax \geq b \\
\end{split}
$$

- note: equallity constraints can be expressed as two inequallity constraints

### standard form
- [[linear programm]] that satisfies the following 3 conditions is in **standard form**
- the standard form is the stating point for the simplex algorithm
- used for dualizing a [[linear programm]]

1) non negativity of all varibales $x$
2) all remaining constraints are expressed as equality constrains
3) the right side vector $b$ is none negative
$$
\begin{split}
\min_{x \in \mathbb{R}^m}& \quad  c^\top x \\
\mathrm{s.t.} \: &Ax = b \\
&x \geq 0 \\
\end{split}
$$

#### converting to standard form
- greater or equal constraints $Ax \geq b$ are converted to $Ax - s = b$ with slack variable $s \geq 0$
- less or equal constraints $Ax \leq b$ are converted to $Ax + s = b$ with slack variable $s \geq 0$
- in case $b_i<0$ is negative both sides are multipled with $-1$  
- conditions $x_i \geq 0$ are transformed by subsituting $x_i$ with $y_i=-x_i$
- add $x\geq0$ condition (no details)
Tags: mathematics linear_algebra
<!--ID: 1722798041227-->
END



START
Basic
how to build the dual problem for a primal linear programm in general form?

Back: 
#### transfomration primal to dual in general form
- the primal objective function $\min c^\top x$ becomes $\max p^\top b$
- for each constraint regading $x_j$ a constraint function is introduced based on its relation column vector $A_{(*, j)}$
	- $x_j \geq 0$ becomes $p^\top A_{(*, j)} \leq c_i$
	- $x_j \leq 0$ becomes $p^\top A_{(*, j)} \geq c_i$
	- $x=0$ becomes $p^\top A_{(*, j)} = c_i$
- for each row vector $A_{(i, *)}$ that is representing a constraint function a constraint regrading $p_i$ in introduced
	- $A_{(i, *)}x \geq b_i$ becomes $p_i\geq 0$
	- $A_{(i, *)}x \leq b_i$ becomes $p_i\leq 0$
	- $A_{(i, *)}x = b_i$ becomes $p_i=free$

_____________________

### linear primal programm
- [[constraint optimization problem]] with a [[linear map|linear]] objective function and [[linear map|linear]] contraint functions
- every [[linear map]] is [[convex]] thus every [[local minimum]] is a [[minimum|global minimum]] and 

### canonical form

$$
\begin{split}
\min_{x \in \mathbb{R}^m}& \quad  c^\top x \\
\mathrm{s.t.} \: &Ax \geq b \\
\end{split}
$$

- note: equallity constraints can be expressed as two inequallity constraints

### standard form
- [[linear programm]] that satisfies the following 3 conditions is in **standard form**
- the standard form is the stating point for the simplex algorithm
- used for dualizing a [[linear programm]]

1) non negativity of all varibales $x$
2) all remaining constraints are expressed as equality constrains
3) the right side vector $b$ is none negative
$$
\begin{split}
\min_{x \in \mathbb{R}^m}& \quad  c^\top x \\
\mathrm{s.t.} \: &Ax = b \\
&x \geq 0 \\
\end{split}
$$

#### converting to standard form
- greater or equal constraints $Ax \geq b$ are converted to $Ax - s = b$ with slack variable $s \geq 0$
- less or equal constraints $Ax \leq b$ are converted to $Ax + s = b$ with slack variable $s \geq 0$
- in case $b_i<0$ is negative both sides are multipled with $-1$  
- conditions $x_i \geq 0$ are transformed by subsituting $x_i$ with $y_i=-x_i$
- add $x\geq0$ condition (no details)
Tags: mathematics linear_algebra
<!--ID: 1722798041230-->
END


START
Basic
- given two optimal solutions of the dual and primal problem of an [[linear programm]] $x$ and $p$
- how are they related?

Back: 
#### primal dual slackness
- let $x^*$ and $p^*$ be optimal solutions for the primal and optimal problem then they have the same objective function

$$
\begin{split}
p_i\left(A_{(i, *)} x - b_i\right) = 0 \\
\left(c_j - p^\top A_{(*, j)} \right)x_j = 0 \\
\end{split}
$$

_____________________
### linear dual programm
- given the following primal linear programm in canonical form with [[matrix]] $A\in \mathbb{R}^{n \times m}$

$$
\begin{split}
\min_{x \in \mathbb{R}^m}& \quad  c^\top x \\
\mathrm{s.t.} \: &Ax \geq b \\
&x \geq 0 \\
\end{split}
$$
- there exists the following dual problem

$$
\begin{split}
\max_{x \in \mathbb{R}^m}& \quad  p^\top b \\
\mathrm{s.t.} \: &p^\top A \leq c^\top \\
&p\geq 0 \\
\end{split}
$$

#### transfomration primal to dual in general form
- the primal objective function $\min c^\top x$ becomes $\max p^\top b$
- for each constraint regading $x_j$ a constraint function is introduced based on its relation column vector $A_{(*, j)}$
	- $x_j \geq 0$ becomes $p^\top A_{(*, j)} \leq c_i$
	- $x_j \leq 0$ becomes $p^\top A_{(*, j)} \geq c_i$
	- $x=0$ becomes $p^\top A_{(*, j)} = c_i$
- for each row vector $A_{(i, *)}$ that is representing a constraint function a constraint regrading $p_i$ in introduced
	- $A_{(i, *)}x \geq b_i$ becomes $p_i\geq 0$
	- $A_{(i, *)}x \leq b_i$ becomes $p_i\leq 0$
	- $A_{(i, *)}x = b_i$ becomes $p_i=free$

#### interpretation
- the variable $p$ can be interpreted as
#### weak duality
- every feasible solution to the dual problem has an objective value lessor equal to that of every to that of ever solution of the probal problem
$$
c^\top x \geq p^\top b
$$

#### strong duality
- let $x^*$ and $p^*$ be optimal solutions for the primal and optimal problem then they have the same objective function

$$
c^\top x = p^\top b
$$



### linear primal programm
- [[constraint optimization problem]] with a [[linear map|linear]] objective function and [[linear map|linear]] contraint functions
- every [[linear map]] is [[convex]] thus every [[local minimum]] is a [[minimum|global minimum]] and 

### canonical form

$$
\begin{split}
\min_{x \in \mathbb{R}^m}& \quad  c^\top x \\
\mathrm{s.t.} \: &Ax \geq b \\
\end{split}
$$

- note: equallity constraints can be expressed as two inequallity constraints

### standard form
- [[linear programm]] that satisfies the following 3 conditions is in **standard form**
- the standard form is the stating point for the simplex algorithm
- used for dualizing a [[linear programm]]

1) non negativity of all varibales $x$
2) all remaining constraints are expressed as equality constrains
3) the right side vector $b$ is none negative
$$
\begin{split}
\min_{x \in \mathbb{R}^m}& \quad  c^\top x \\
\mathrm{s.t.} \: &Ax = b \\
&x \geq 0 \\
\end{split}
$$

#### converting to standard form
- greater or equal constraints $Ax \geq b$ are converted to $Ax - s = b$ with slack variable $s \geq 0$
- less or equal constraints $Ax \leq b$ are converted to $Ax + s = b$ with slack variable $s \geq 0$
- in case $b_i<0$ is negative both sides are multipled with $-1$  
- conditions $x_i \geq 0$ are transformed by subsituting $x_i$ with $y_i=-x_i$
- add $x\geq0$ condition (no details)
Tags: mathematics linear_algebra
<!--ID: 1722798041232-->
END


START
Basic
- given a dual and primal [[linear programm]] 
- what can be said about the objective functions of
- feasable points $x$ and $p$
- of optimal point $x^*$ and $p^*$

Back: 
#### weak duality
- every feasible solution to the dual problem has an objective value lessor equal to that of every to that of ever solution of the probal problem
$$
c^\top x \geq p^\top b
$$

#### strong duality
- let $x^*$ and $p^*$ be optimal solutions for the primal and optimal problem then they have the same objective function

$$
c^\top x = p^\top b
$$

_____________________
### linear dual programm
- given the following primal linear programm in canonical form with [[matrix]] $A\in \mathbb{R}^{n \times m}$

$$
\begin{split}
\min_{x \in \mathbb{R}^m}& \quad  c^\top x \\
\mathrm{s.t.} \: &Ax \geq b \\
&x \geq 0 \\
\end{split}
$$
- there exists the following dual problem

$$
\begin{split}
\max_{x \in \mathbb{R}^m}& \quad  p^\top b \\
\mathrm{s.t.} \: &p^\top A \leq c^\top \\
&p\geq 0 \\
\end{split}
$$

#### transfomration primal to dual in general form
- the primal objective function $\min c^\top x$ becomes $\max p^\top b$
- for each constraint regading $x_j$ a constraint function is introduced based on its relation column vector $A_{(*, j)}$
	- $x_j \geq 0$ becomes $p^\top A_{(*, j)} \leq c_i$
	- $x_j \leq 0$ becomes $p^\top A_{(*, j)} \geq c_i$
	- $x=0$ becomes $p^\top A_{(*, j)} = c_i$
- for each row vector $A_{(i, *)}$ that is representing a constraint function a constraint regrading $p_i$ in introduced
	- $A_{(i, *)}x \geq b_i$ becomes $p_i\geq 0$
	- $A_{(i, *)}x \leq b_i$ becomes $p_i\leq 0$
	- $A_{(i, *)}x = b_i$ becomes $p_i=free$


#### primal dual slackness
- let $x^*$ and $p^*$ be optimal solutions for the primal and optimal problem then they have the same objective function

$$
\begin{split}
p_i\left(A_{(i, *)} x - b_i\right) = 0 \\
\left(c_j - p^\top A_{(*, j)} \right)x_j = 0 \\
\end{split}
$$

### linear primal programm
- [[constraint optimization problem]] with a [[linear map|linear]] objective function and [[linear map|linear]] contraint functions
- every [[linear map]] is [[convex]] thus every [[local minimum]] is a [[minimum|global minimum]] and 

### canonical form

$$
\begin{split}
\min_{x \in \mathbb{R}^m}& \quad  c^\top x \\
\mathrm{s.t.} \: &Ax \geq b \\
\end{split}
$$

- note: equallity constraints can be expressed as two inequallity constraints

### standard form
- [[linear programm]] that satisfies the following 3 conditions is in **standard form**
- the standard form is the stating point for the simplex algorithm
- used for dualizing a [[linear programm]]

1) non negativity of all varibales $x$
2) all remaining constraints are expressed as equality constrains
3) the right side vector $b$ is none negative
$$
\begin{split}
\min_{x \in \mathbb{R}^m}& \quad  c^\top x \\
\mathrm{s.t.} \: &Ax = b \\
&x \geq 0 \\
\end{split}
$$

#### converting to standard form
- greater or equal constraints $Ax \geq b$ are converted to $Ax - s = b$ with slack variable $s \geq 0$
- less or equal constraints $Ax \leq b$ are converted to $Ax + s = b$ with slack variable $s \geq 0$
- in case $b_i<0$ is negative both sides are multipled with $-1$  
- conditions $x_i \geq 0$ are transformed by subsituting $x_i$ with $y_i=-x_i$
- add $x\geq0$ condition (no details)
Tags: mathematics linear_algebra
<!--ID: 1722798041235-->
END