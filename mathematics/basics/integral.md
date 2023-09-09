The [[integral]] can be interpreted as 
- a continuous [[sum]] of a [[function]]
- generalization of areas under a [[function]]

The **infinit [[integral]]** is defined as the [[inverse function|inverse]] of the [[derivative]] while the **definit [[integral]]** is defined as a signed area under a [[continouse function]]

![[derivative#definition derivative]]

## Infinite [[integral]] is an [[inverse function|inverse]] [[derivative]]
Let $f(x)=\frac{dF(x)}{dx}$ be a [[continouse function]] defined for a [[function domain|domain]] $[a,b]$ that is the [[derivative]] of a [[function]] $F$. Since the **infinit [[integral]]** is the [[inverse function]] of the [[derivative]] it is defined as follows:

$$
\begin{split}
F(x) &= \int_a^x \frac{dF(x)}{dx} dt \\
&= \int_a^x f(t) dt \\
\end{split}
$$
This $F(x) = \int_a^x \frac{dF(x) + C}{dx} dt$ is true for every constant $C$ there exist a infinite number of antiderivatives. A constant has to be added to the definition. 
$$
\begin{split}
F(x) + C
&= \int_a^x f(t) dt \\
\end{split}
$$

## definit [[integral]]
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


![[integration by parts#theorem integration by parts]]

![[integration by substitution#theorem integration by substitution]]

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

## Infinite [[integral]] is an [[inverse function|inverse]] [[derivative]]
Let $f(x)=\frac{dF(x)}{dx}$ be a [[continouse function]] defined for a [[function domain|domain]] $[a,b]$ that is the [[derivative]] of a [[function]] $F$. Since the **infinit [[integral]]** is the [[inverse function]] of the [[derivative]] it is defined as follows:

$$
\begin{split}
F(x) &= \int_a^x \frac{dF(x)}{dx} dt \\
&= \int_a^x f(t) dt \\
\end{split}
$$
This $F(x) = \int_a^x \frac{dF(x) + C}{dx} dt$ is true for every constant $C$ there exist a infinite number of antiderivatives. A constant has to be added to the definition. 
$$
\begin{split}
F(x) + C
&= \int_a^x f(t) dt \\
\end{split}
$$



## definit [[integral]]
 For $a_1,b_1$ with $a < a_1 < b_1 < b$ the **definit [[integral]]** is defined as follows.
$$
\begin{split}
\int_{a_1}^{b_1} f(x) dx &= F(b_1) - F(a_1)
\end{split}
$$
Tags: mathematics
<!--ID: 1693125425154-->
END

START
Basic
[[integral]] summary
- definition (2 types)
- two important theorems

Back: 
### definition
#### Infinite [[integral]] is an [[inverse function|inverse]] [[derivative]]
Let $f(x)=\frac{dF(x)}{dx}$ be a [[continouse function]] defined for a [[function domain|domain]] $[a,b]$ that is the [[derivative]] of a [[function]] $F$. Since the **infinit [[integral]]** is the [[inverse function]] of the [[derivative]] it is defined as follows:

$$
\begin{split}
F(x) &= \int_a^x \frac{dF(x)}{dx} dt \\
&= \int_a^x f(t) dt \\
\end{split}
$$
This $F(x) = \int_a^x \frac{dF(x) + C}{dx} dt$ is true for every constant $C$ there exist a infinite number of antiderivatives. A constant has to be added to the definition. 
$$
\begin{split}
F(x) + C
&= \int_a^x f(t) dt \\
\end{split}
$$

#### definit [[integral]]
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
### theorem [[integration by parts]]

$$
\begin{split}
\int f(x) \frac{dg(x)}{x}dx = f(x)g(x)-\int g(x) \frac{df(x)}{dx} dx
\end{split}
$$

### theorem [[integration by substitution]]

#### definit [[integral]]
$$
\begin{split}
\int_a^b f\left(g(x)\right) \frac{dg(x)}{x}dx = \int_{g(a)}^{g(b)} f\left(t\right) dt \quad \text{with} \quad t=g(x)
\end{split}
$$
#### infinit [[integral]]
$$
\begin{split}
\int f\left(g(x)\right) \frac{dg(x)}{x}dx = \left.\int f\left(t\right) dt \right|_{t=g(x)}
\end{split}
$$

Tags: mathematics
<!--ID: 1694252283001-->
END


START
Basic
Definition **infinit [[integral]]** and **definit [[integral]]**
- definition
- proof for **definit [[integral]]**
Back: 
The [[integral]] can be interpreted as 
- a continuous [[sum]] of a [[function]]
- generalization of areas under a [[function]]

The **infinit [[integral]]** is defined as the [[inverse function|inverse]] of the [[derivative]] while the **definit [[integral]]** is defined as a signed area under a [[continouse function]]



## Infinite [[integral]] is an [[inverse function|inverse]] [[derivative]]
Let $f(x)=\frac{dF(x)}{dx}$ be a [[continouse function]] defined for a [[function domain|domain]] $[a,b]$ that is the [[derivative]] of a [[function]] $F$. Since the **infinit [[integral]]** is the [[inverse function]] of the [[derivative]] it is defined as follows:

$$
\begin{split}
C + F(x) &= \int_a^x f(t) dt \\
\end{split}
$$


## definit [[integral]]
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