The [[integral]] can be interpreted as 
- a continuous [[sum]] of a [[function]]
- generalization of areas under a [[function]]

The **infinit [[integral]]** is defined as the [[inverse function|inverse]] of the [[derivative]] while the **definit [[integral]]** is defined as a signed area under a [[continouse function]]

![[derivative#definition derivative]]

### infinite [[integral]] is an [[inverse function|inverse]] [[derivative]]
let $f$ be a [[continouse function]] defined for a [[function domain|domain]] $[a,b]$ then the following is true for every value $x \in [a,b]$. Let the [[function]] $F$ be defined as follows. 
$$
\begin{split}
F(x) &= \int_a^x f(t) dt \\
\end{split}
$$
Then the following is true for every value $x \in [a,b]$. Thus, the **infinit [[integral]]** is the [[inverse function]] of the [[derivative]].
$$
\begin{split}
\frac{dF(x)}{dx} = f(x)  
\end{split}
$$

### definit [[integral]]
Let $f$ be the [[derivative]] of a [[continouse function]] $F$ on the interval $[a,b]$.
$$
\begin{split}
f(x) =&  \frac{dF(x)}{dx} \\
\end{split}
$$
 For $a_1,b_1$ with $a < a_1 < b_1 < b$ the **definit [[integral]]** is defined as follows.
$$
\begin{split}
\int_{a_1}^{b_1} f(x) dx &= F(b_1) - F(a_1)
\end{split}
$$
#### intutiton
From the definition of the **infinit [[integral]]** we know the following
$$
\begin{split}
f(x) =&  \frac{dF(x)}{dx} \\
\Rightarrow F(x) &= \int_a^x f(t) dt \\
\end{split}
$$

From the properties from the [[sum]] it follows for the **definit [[integral]]** 
$$
\begin{split}
\int_{a_1}^{b_1} f(x) dx 
&= \int_{a_1}^{b_1} f(x) dx  + \int_a^{a_1} f(t) dt - \int_a^{a_1} f(t) dt  \\
&= \int_{a}^{b_1} f(t) dt - \int_a^{a_1} f(t) dt  \\
&= F(b_1) - F(a_1)
\end{split}
$$



# anki
START
Basic
[[integral]]
- 2 types of [[integral|integrals]]
- interpretation

Back: 
The [[integral]] can be interpreted as 
- a continuous [[sum]] of a [[function]]
- generalization of areas under a [[function]]

The **infinit [[integral]]** is defined as the [[inverse function|inverse]] of the [[derivative]] while the **definit [[integral]]** is defined as a signed area under a [[continouse function]]

Tags: mathematics
<!--ID: 1693125425154-->
END

START
Basic
Definition **infinit [[integral]]** and **definit [[integral]]**

Back: 
The [[integral]] can be interpreted as 
- a continuous [[sum]] of a [[function]]
- generalization of areas under a [[function]]

The **infinit [[integral]]** is defined as the [[inverse function|inverse]] of the [[derivative]] while the **definit [[integral]]** is defined as a signed area under a [[continouse function]]



### infinite [[integral]] is an [[inverse function|inverse]] [[derivative]]
let $f$ be a [[continouse function]] defined for a [[function domain|domain]] $[a,b]$ then the following is true for every value $x \in [a,b]$. Let the [[function]] $F$ be defined as follows. 
$$
\begin{split}
F(x) &= \int_a^x f(t) dt \\
\end{split}
$$
Then the following is true for every value $x \in [a,b]$. Thus, the **infinit [[integral]]** is the [[inverse function]] of the [[derivative]].
$$
\begin{split}
\frac{dF(x)}{dx} = f(x)  
\end{split}
$$

### definit [[integral]]
Let $f$ be the [[derivative]] of a [[continouse function]] $F$ on the interval $[a,b]$.
$$
\begin{split}
f(x) =&  \frac{dF(x)}{dx} \\
\end{split}
$$
 For $a_1,b_1$ with $a < a_1 < b_1 < b$ the **definit [[integral]]** is defined as follows.
$$
\begin{split}
\int_{a_1}^{b_1} f(x) dx &= F(b_1) - F(a_1)
\end{split}
$$
#### intutiton
From the definition of the **infinit [[integral]]** we know the following
$$
\begin{split}
f(x) =&  \frac{dF(x)}{dx} \\
\Rightarrow F(x) &= \int_a^x f(t) dt \\
\end{split}
$$

From the properties from the [[sum]] it follows for the **definit [[integral]]** 
$$
\begin{split}
\int_{a_1}^{b_1} f(x) dx 
&= \int_{a_1}^{b_1} f(x) dx  + \int_a^{a_1} f(t) dt - \int_a^{a_1} f(t) dt  \\
&= \int_{a}^{b_1} f(t) dt - \int_a^{a_1} f(t) dt  \\
&= F(b_1) - F(a_1)
\end{split}
$$


Tags: mathematics
<!--ID: 1693125425158-->
END