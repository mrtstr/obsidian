# Definition Exponential
$$
f(x) = b^x
$$
```functionplot
---
title: 
xLabel: x
yLabel: exp(x)
bounds: [-2,2,0,5]
disableZoom: true
grid: true
---
f(x) = exp(x)
```

## for exponent $n \in \mathbb{Z}$ [[integer|integers]] 
given a [[real number]] $a \in \mathbb{R}$ called the basis and a [[integer]] $n \in \mathbb{Z}$ called the exponent
$$
a^n = \underbrace{a \cdot ... \cdot a}_\text{n times}
$$
$$
a^{-n} = \underbrace{\frac{1}{a \cdot ... \cdot a} }_\text{n times} = \frac{1}{a^n}
$$
## for exponent $q = \frac{n}{k} \in \mathbb{Q}$ [[rational number|rational numbers]] 
$$
a^{q} = a^\frac{n}{k} =
\frac{
\overbrace{a \cdot ... \cdot a}^\text{n times}
}{
\underbrace{a \cdot ... \cdot a}_\text{k times}
} 

$$

# Properties
$$
\forall a:a^0 = 1
$$
## [[addition]] of exponents
$$
\begin{split}
a^{r+s} 
&=\underbrace{a \cdot ... \cdot a}_\text{r times}
 \cdot \underbrace{a \cdot ... \cdot a}_\text{s times} \\
&= \underbrace{a \cdot ... \cdot a}_\text{r+s times} \\
&= a^r \cdot a^s \\
\end{split}
$$
## [[substraction]] of exponents
$$
\begin{split}
a^{r-s} 
&= \underbrace{\frac{a^s}{a^s}}_1 \cdot a^{r-s} \\
&= \frac{a^r}{a^s} \\ 
\end{split}
$$
## [[multiplication]] of basis

$$
\begin{split}
(ab)^{q} 
&= \underbrace{ab \cdot ... \cdot ab}_\text{q times} \\
&= \underbrace{a \cdot ... \cdot a}_\text{q times} \cdot \underbrace{b \cdot ... \cdot b}_\text{q times} \\
&= a^{q} \cdot b^{q}
\end{split}
$$
## [[division]] of basis

$$
\begin{split}
\left(\frac{a}{b}\right)^{r}
&= \underbrace{\frac{a}{b} \cdot ... \cdot \frac{a}{b}}_\text{q times} \\
&= \underbrace{a \cdot ... \cdot a}_\text{q times} \cdot \underbrace{\frac{1}{b} \cdot ... \cdot \frac{1}{b}}_\text{q times} \\
&= \frac{a^{r}}{b^{r}}
\end{split}
$$
## [[composition]]
$$
\begin{split}
\left(a^r\right)^s
&= \underbrace{a^r \cdot ... \cdot a^r}_\text{q times} \\
&= \underbrace{
\underbrace{a \cdot ... \cdot a}_\text{r times} \cdot ... \cdot \underbrace{a \cdot ... \cdot a}_\text{r times}
}_\text{q times} \\
&= a^{r \cdot s} 
\end{split}
$$

# anki
START
Basic
[[exponential]]
- definition
	- for exponent $n \in \mathbb{Z}$ [[integer|integers]] 
	- for exponent $q = \frac{n}{k} \in \mathbb{Q}$ [[rational number|rational numbers]] 
- properties
	- [[addition]] of exponents
	- [[substraction]] of exponents
	- [[multiplication]] of basis
	- [[division]] of basis
	- [[composition]]
Back: 
# Definition
## for exponent $n \in \mathbb{Z}$ [[integer|integers]] 
given a [[real number]] $a \in \mathbb{R}$ called the basis and a [[integer]] $n \in \mathbb{Z}$ called the exponent
$$
a^n = \underbrace{a \cdot ... \cdot a}_\text{n times}
$$
$$
a^{-n} = \underbrace{\frac{1}{a \cdot ... \cdot a} }_\text{n times} = \frac{1}{a^n}
$$
## for exponent $q = \frac{n}{k} \in \mathbb{Q}$ [[rational number|rational numbers]] 
$$
a^{q} = a^\frac{n}{k} =
\frac{
\overbrace{a \cdot ... \cdot a}^\text{n times}
}{
\underbrace{a \cdot ... \cdot a}_\text{k times}
} 

$$

# Properties
$$
\forall a:a^0 = 1
$$
## [[addition]] of exponents
$$
\begin{split}
a^{r+s} 
&=\underbrace{a \cdot ... \cdot a}_\text{r times}
 \cdot \underbrace{a \cdot ... \cdot a}_\text{s times} \\
&= \underbrace{a \cdot ... \cdot a}_\text{r+s times} \\
&= a^r \cdot a^s \\
\end{split}
$$
## [[substraction]] of exponents
$$
\begin{split}
a^{r-s} 
&= \underbrace{\frac{a^s}{a^s}}_1 \cdot a^{r-s} \\
&= \frac{a^r}{a^s} \\ 
\end{split}
$$
## [[multiplication]] of basis

$$
\begin{split}
(ab)^{q} 
&= \underbrace{ab \cdot ... \cdot ab}_\text{q times} \\
&= \underbrace{a \cdot ... \cdot a}_\text{q times} \cdot \underbrace{b \cdot ... \cdot b}_\text{q times} \\
&= a^{q} \cdot b^{q}
\end{split}
$$
## [[division]] of basis

$$
\begin{split}
\left(\frac{a}{b}\right)^{r}
&= \underbrace{\frac{a}{b} \cdot ... \cdot \frac{a}{b}}_\text{q times} \\
&= \underbrace{a \cdot ... \cdot a}_\text{q times} \cdot \underbrace{\frac{1}{b} \cdot ... \cdot \frac{1}{b}}_\text{q times} \\
&= \frac{a^{r}}{b^{r}}
\end{split}
$$
## [[composition]]
$$
\begin{split}
\left(a^r\right)^s
&= \underbrace{a^r \cdot ... \cdot a^r}_\text{q times} \\
&= \underbrace{
\underbrace{a \cdot ... \cdot a}_\text{r times} \cdot ... \cdot \underbrace{a \cdot ... \cdot a}_\text{r times}
}_\text{q times} \\
&= a^{r \cdot s} 
\end{split}
$$
Tags: mathematics
<!--ID: 1682941753037-->
END