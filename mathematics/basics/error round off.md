### floating point representation
- let $fl(x)$ be the flowting point representation of $x \in \mathbb{R}$ with the base $p$ (e.g. decimal: $10$ or binary $2$) and the **mantisse** $a$ with $m$ digits end the **exponent** $t$ with $e$ digits
$$
fl(x) = a \cdot p^t  
$$
- when using a computer the number of bits of a number are shared between the mantissa and the exponent $n = m + e$

### round off error
- the following is the **absolut error** of the floting point representation
$$
|fl(x) - x| \leq \frac{p^{-m}}{2} \cdot p^t
$$
- the **relative error** $\epsilon$ is defined as follows und is used as roundoff unit
$$
\frac{|fl(x) - x|}{|x|} \leq \frac{p^{-m}}{2} \cdot p = \epsilon
$$
$$
fl(x) = x(1+\delta) \text{ with } |\delta| \leq \epsilon
$$
### floating point arithmetic
- for computer based numbers only the [[commutative]] law applies while [[associative]] and [[distributive]] laws do not apply

![[commutative#commutative]]

![[associative#associative]]

![[distributive#distributive]]


# anki

START
Basic
- how are floating point number represented?
- how large is the **relative error** and **absolute error**?
Back: 
### floating point representation
- let $fl(x)$ be the flowting point representation of $x \in \mathbb{R}$ with the base $p$ (e.g. decimal: $10$ or binary $2$) and the **mantisse** $a$ with $m$ digits end the **exponent** $t$ with $e$ digits
$$
fl(x) = a \cdot p^t  
$$
- when using a computer the number of bits of a number are shared between the mantissa and the exponent $n = m + e$

### round off error
- the following is the **absolut error** of the floting point representation
$$
|fl(x) - x| \leq \frac{p^{-m}}{2} \cdot p^t
$$
- the **relative error** $\epsilon$ is defined as follows und is used as roundoff unit
$$
\frac{|fl(x) - x|}{|x|} \leq \frac{p^{-m}}{2} \cdot p = \epsilon
$$
$$
fl(x) = x(1+\delta) \text{ with } |\delta| \leq \epsilon
$$


Tags: mathematics
<!--ID: 1721848483214-->
END


START
Basic
which of the arithmetic are still true for floating point arithmetic?
Back: 
### floating point arithmetic
- for computer based numbers only the [[commutative]] law applies while [[associative]] and [[distributive]] laws do not apply

#### commutative
a operation is commutative if the following is true in general
$$
a \circ b = b \circ a
$$

#### associative
$$
a \circ (b \circ c) = (a \circ b) \circ c
$$

#### distributive
two operations $\circ$ and $\times$ are distributive if the following is true in general
$$
(a \times b) \circ b = (a \circ c) \times (b \circ c)
$$

_________________
### floating point representation
- let $fl(x)$ be the flowting point representation of $x \in \mathbb{R}$ with the base $p$ (e.g. decimal: $10$ or binary $2$) and the **mantisse** $a$ with $m$ digits end the **exponent** $t$ with $e$ digits
$$
fl(x) = a \cdot p^t  
$$
- when using a computer the number of bits of a number are shared between the mantissa and the exponent $n = m + e$

### round off error
- the following is the **absolut error** of the floting point representation
$$
|fl(x) - x| \leq \frac{p^{-m}}{2} \cdot p^t
$$
- the **relative error** $\epsilon$ is defined as follows und is used as roundoff unit
$$
\frac{|fl(x) - x|}{|x|} \leq \frac{p^{-m}}{2} \cdot p = \epsilon
$$
$$
fl(x) = x(1+\delta) \text{ with } |\delta| \leq \epsilon
$$

Tags: mathematics
<!--ID: 1721848483220-->
END



