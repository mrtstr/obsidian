## [[integration by substitution]]

- the [[integration by substitution]] rule for the [[integral]] is the equivalent of the [[chain rule of derivative]]
- used to calculate the [[integral]] of [[function]] that is a [[composition]] of two [[function|functions]]


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
#### definit [[integral]]

By plugging this in the definition of the [[integral|definit integral]] we can prove the [[integration by substitution]] transformation rule
$$
\begin{split}
\int_a^b f\left(g(x)\right) \frac{dg(x)}{x}dx 
&= \int_a^b \frac{dF\left(g(x)\right)}{dx}dx \\
&= \int_{a_0}^b \frac{dF\left(g(x)\right)}{dx}dx -\int_{a_0}^{a} \frac{dF\left(g(x)\right)}{dx}dx \\
&= F\left(g(b)\right) - F\left(g(a_0)\right) - F\left(g(a)\right) + F\left(g(a_0)\right) \\
&= F\left(g(b)\right) - F\left(g(a)\right) \\
&= \int_{g(a)}^{g(b)} f\left(t\right) dt \quad \text{with} \quad t=g(x) \\
\end{split}
$$
#### infinit [[integral]]
$$
\begin{split}
\int f\left(g(x)\right) \frac{dg(x)}{x}dx 
&= \int \frac{dF\left(g(x)\right)}{dx}dx \\
&= F\left(g(x)\right) + C \quad \text{(definition as antiderivate)} \\
&= \left. \int f\left(t\right) dt \right|_{t=g(x)}  \\
\end{split}
$$
### examples
$$
\begin{split}
\int_0^2 x  \cos(x^2+1) dx 
&= \frac{1}{2} \int_0^2 2x  \cos(x^2+1) dx \\
&= \frac{1}{2} \int_0^2 \overbrace{ 2x}^{\frac{dg(x)}{dx}}  \overbrace{\cos(x^2+1)}^{f\left(g(x)\right)}  dx \\
&= \frac{1}{2} \int_{(0^2+1)}^{(2^2+1)} \cos(t) dt \quad with \: t=g(x)=x^2+1 \\
&= \frac{1}{2} \int_1^5 \cos(t) dt \quad with \: t=g(x)=x^2+1 \\
&= \frac{1}{2} \left(\sin(5) - \sin(1)\right) \\

\end{split}
$$
$$
\begin{split}
\int x  \cos(x^2+1) dx 
&= \frac{1}{2} \int 2x  \cos(x^2+1) dx \\
&= \frac{1}{2} \int \overbrace{ 2x}^{\frac{dg(x)}{dx}}  \overbrace{\cos(x^2+1)}^{f\left(g(x)\right)}  dx \\
&= \frac{1}{2} \int \cos(t) dt \quad with \: t=g(x)=x^2+1 \\
&= \frac{1}{2} \sin(t) + C \\
&= \frac{1}{2} \sin\left(x^2+1\right) + C \\
\end{split}
$$

$$
\begin{split}
&\int x  \sqrt{x+1}^3 dx \\
& t = \sqrt{x+1} \\
&\Rightarrow x = t^2+1 \\
&\Rightarrow \frac{dt}{dx} = \frac{d\sqrt{x+1}}{dx} = \frac{1}{2}\frac{1}{\sqrt{x+1}}\\
&\Rightarrow dx = 2 \sqrt{x+1} du = 2 \sqrt{t^2+1+1} du = 2 t du \\
\int x  \sqrt{x+1}^3 dx 
&= \int \left((t^2+1)  \sqrt{t^2+1+1}^3\right) 2 t du  \\
&= 2 \int (t^2+1)  t^4  du  \\
&= 2 \int t^6+t^4  du  \\
&= t^7 \frac{2}{7}+ t^5\frac{2}{5} + C  \\
&= \sqrt{x+1}^7 \frac{2}{7}+ \sqrt{x+1}^5\frac{2}{5}  + C  \\
&= (x+1)^6 \frac{2}{7}+ (x+1)^4\frac{2}{5}  + C  \\
\end{split}
$$
# anki
START
Basic
[[integration by substitution]] (definit)
- concept (2)
- theorem (definit)
- proof (definit)
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
Let $f(x)=\frac{dF(x)}{dx}$ be a [[continuous function]] defined for a [[function domain|domain]] $[a,b]$ that is the [[derivative]] of a [[function]] $F$. Since the **infinit [[integral]]** is the [[inverse function]] of the [[derivative]] it is defined as follows:

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
&= \int_{a_0}^b \frac{dF\left(g(x)\right)}{dx}dx -\int_{a_0}^{a} \frac{dF\left(g(x)\right)}{dx}dx \\
&= F\left(g(b)\right) - F\left(g(a_0)\right) - F\left(g(a)\right) + F\left(g(a_0)\right) \\
&= F\left(g(b)\right) - F\left(g(a)\right) \\
&= \int_{g(a)}^{g(b)} f\left(t\right) dt \quad \text{with} \quad t=g(x) \\
\end{split}
$$

Tags: mathematics
<!--ID: 1693731484504-->
END


START
Basic
[[integration by substitution]] (infinit)
- concept (2)
- theorem (infinit)
- proof (infinit)
Back: 
- the [[integration by substitution]] rule for the [[integral]] is the equivalent of the [[chain rule of derivative]]
- used to calculate the [[integral]] of [[function]] that is a [[composition]] of two [[function|functions]]

### theorem

$$
\begin{split}
\int f\left(g(x)\right) \frac{dg(x)}{x}dx = \left.\int f\left(t\right) dt \right|_{t=g(x)}
\end{split}
$$
### given
#### Infinite [[integral]] is an [[inverse function|inverse]] [[derivative]]
Let $f(x)=\frac{dF(x)}{dx}$ be a [[continuous function]] defined for a [[function domain|domain]] $[a,b]$ that is the [[derivative]] of a [[function]] $F$. Since the **infinit [[integral]]** is the [[inverse function]] of the [[derivative]] it is defined as follows:

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

$$
\begin{split}
\int f\left(g(x)\right) \frac{dg(x)}{x}dx 
&= \int \frac{dF\left(g(x)\right)}{dx}dx \\
&= F\left(g(x)\right) + C \quad \text{(definition as antiderivate)} \\
&= \left. \int f\left(t\right) dt \right|_{t=g(x)}  \\
\end{split}
$$

Tags: mathematics
<!--ID: 1694252282993-->
END


START
Basic

$$
\begin{split}
\int_0^2 x  \cos(x^2+1) dx 
\end{split}
$$
$$
\begin{split}
\int x  \cos(x^2+1) dx 
\end{split}
$$
$$
\begin{split}
&\int x  \sqrt{x+1}^3 dx \\
\end{split}
$$
Back: 
#### Theorem definite [[integral]]
$$
\begin{split}
\int_a^b f\left(g(x)\right) \frac{dg(x)}{x}dx = \int_{g(a)}^{g(b)} f\left(t\right) dt \quad \text{with} \quad t=g(x)
\end{split}
$$
$$
\begin{split}
\int_0^2 x  \cos(x^2+1) dx 
&= \frac{1}{2} \int_0^2 2x  \cos(x^2+1) dx \\
&= \frac{1}{2} \int_0^2 \overbrace{ 2x}^{\frac{dg(x)}{dx}}  \overbrace{\cos(x^2+1)}^{f\left(g(x)\right)}  dx \\
&= \frac{1}{2} \int_{(0^2+1)}^{(2^2+1)} \cos(t) dt \quad with \: t=g(x)=x^2+1 \\
&= \frac{1}{2} \int_1^5 \cos(t) dt \quad with \: t=g(x)=x^2+1 \\
&= \frac{1}{2} \left(\sin(5) - \sin(1)\right) \\

\end{split}
$$
#### Theorem infinite [[integral]]
$$
\begin{split}
\int f\left(g(x)\right) \frac{dg(x)}{x}dx = \left.\int f\left(t\right) dt \right|_{t=g(x)}
\end{split}
$$
$$
\begin{split}
\int x  \cos(x^2+1) dx 
&= \frac{1}{2} \int 2x  \cos(x^2+1) dx \\
&= \frac{1}{2} \int \overbrace{ 2x}^{\frac{dg(x)}{dx}}  \overbrace{\cos(x^2+1)}^{f\left(g(x)\right)}  dx \\
&= \frac{1}{2} \int \cos(t) dt \quad with \: t=g(x)=x^2+1 \\
&= \frac{1}{2} \sin(t) + C \\
&= \frac{1}{2} \sin\left(x^2+1\right) + C \\
\end{split}
$$

$$
\begin{split}
&\int x  \sqrt{x+1}^3 dx \\
& t = \sqrt{x+1} \\
&\Rightarrow x = t^2+1 \\
&\Rightarrow \frac{dt}{dx} = \frac{d\sqrt{x+1}}{dx} = \frac{1}{2}\frac{1}{\sqrt{x+1}} \\
&\Rightarrow dx = 2 \sqrt{x+1} du = 2 \sqrt{t^2+1+1} du = 2 t du \\
\int x  \sqrt{x+1}^3 dx 
&= \int \left((t^2+1)  \sqrt{t^2+1+1}^3\right) 2 t du  \\
&= 2 \int (t^2+1)  t^4  du  \\
&= 2 \int t^6+t^4  du  \\
&= t^7 \frac{2}{7}+ t^5\frac{2}{5}  + C  \\
&= \sqrt{x+1}^7 \frac{2}{7}+ \sqrt{x+1}^5\frac{2}{5}   + C  \\
&= (x+1)^6 \frac{2}{7}+ (x+1)^4\frac{2}{5}  + C   \\
\end{split}
$$
Tags: mathematics
<!--ID: 1694252282998-->
END