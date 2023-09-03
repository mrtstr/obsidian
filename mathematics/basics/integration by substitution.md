## [[integration by substitution]]

- the [[integration by substitution]] rule for the [[integral]] is the equivalent of the [[chain rule of derivative]]
- used to calculate the [[integral]] of [[function]] that is a [[composition]] of two [[function|functions]]


### theorem

$$
\begin{split}
\int_a^b f\left(g(x)\right) \frac{dg(x)}{x}dx = \int_{g(a)}^{g(b)} f\left(t\right) dt \quad \text{with} \quad t=g(x)
\end{split}
$$
### given

![[integral#Infinite integral is an inverse function inverse derivative]]

![[integral#definit integral]]

![[chain rule of derivative#composition chain rule for derivative]]

### Proof
Let $F$ be the [[integral|anti derivative]] of $f$.
$$
\begin{split}
F(x) &= \int_{a}^{x} f(t) dt \Leftrightarrow f(x) = \frac{dF(x)}{dx} \\
\end{split}
$$
We know the folowing from the [[chain rule of derivative]]
$$
\begin{split}
\frac{dF\left(g(x)\right)}{dx} 
&= \frac{dF\left(g(x)\right)}{dg(x)}\frac{dg(x)}{x} \\
&= f\left(g(x)\right)\frac{dg(x)}{x} \\
\end{split}
$$
By plugging this in the definition of the [[integral|definit integral]] we can prove the [[integration by substitution]] transformation rule
$$
\begin{split}
\int_a^b f\left(g(x)\right) \frac{dg(x)}{x}dx 
&= \int_a^b \frac{dF\left(g(x)\right)}{dx}dx \\
&= F\left(g(b)\right) - F\left(g(a)\right) \\
&= \int_{g(a)}^{g(b)} f\left(t\right) dt \quad \text{with} \quad t=g(x) \\
\end{split}
$$
### examples

# anki
START
Basic
[[integration by substitution]]
- concept (2)
- theorem
- proof
Back: 
- the [[integration by substitution]] rule for the [[integral]] is the equivalent of the [[chain rule of derivative]]
- used to calculate the [[integral]] of [[function]] that is a [[composition]] of two [[function|functions]]

### theorem

$$
\begin{split}
\int_a^b f\left(g(x)\right) \frac{dg(x)}{x}dx = \int_{g(a)}^{g(b)} f\left(t\right) dt \quad \text{with} \quad t=g(x)
\end{split}
$$

### given
#### Infinite [[integral]] is an [[inverse function|inverse]] [[derivative]]
Let $f(x)=\frac{dF(x)}{dx}$ be a [[continouse function]] defined for a [[function domain|domain]] $[a,b]$ that is the [[derivative]] of a [[function]] $F$. Since the **infinit [[integral]]** is the [[inverse function]] of the [[derivative]] it is defined as follows:

$$
\begin{split}
F(x) &= \int_a^x f(t) dt \\
\end{split}
$$
#### definit [[integral]]
 For $a_1,b_1$ with $a < a_1 < b_1 < b$ the **definit [[integral]]** is defined as follows.
$$
\begin{split}
\int_{a_1}^{b_1} f(x) dx &= F(b_1) - F(a_1)
\end{split}
$$

#### [[composition|chain]] rule for [[derivative]]
- [[derivative]] of the [[composition]] of two [[function|functions]]

$$
\frac{df\left(g(x)\right)}{dx} = \frac{df\left(g(x)\right)}{dg(x)} \cdot \frac{dg(x)}{dx} 
$$

### Proof
Let $F$ be the [[integral|anti derivative]] of $f$.
$$
\begin{split}
F(x) &= \int_{a}^{x} f(t) dt \Leftrightarrow f(x) = \frac{dF(x)}{dx} \\
\end{split}
$$
We know the folowing from the [[chain rule of derivative]]
$$
\begin{split}
\frac{dF\left(g(x)\right)}{dx} 
&= \frac{dF\left(g(x)\right)}{dg(x)}\frac{dg(x)}{x} \\
&= f\left(g(x)\right)\frac{dg(x)}{x} \\
\end{split}
$$
By plugging this in the definition of the [[integral|definit integral]] we can prove the [[integration by substitution]] transformation rule
$$
\begin{split}
\int_a^b f\left(g(x)\right) \frac{dg(x)}{x}dx 
&= \int_a^b \frac{dF\left(g(x)\right)}{dx}dx \\
&= F\left(g(b)\right) - F\left(g(a)\right) \\
&= \int_{g(a)}^{g(b)} f\left(t\right) dt \quad \text{with} \quad t=g(x) \\
\end{split}
$$


Tags: mathematics
<!--ID: 1693731484504-->
END