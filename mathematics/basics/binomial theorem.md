## binomial theorem
$$
(x+y)^n = \sum_{k=0}^n {n \choose k} x^{n-k} y^k
$$

## proof

### [[proof by induction]]

### [[combinatorial methods|combinatorical]] [[proof]]

![[binomial coefficient#Definition]]

$$
\begin{split}
\sum_{k=0}^n {n \choose k} x^{n-k} y^k 
&= {n \choose 0} x^n y^0 + {n \choose 1} x^{n-1} y^1 + \: ... \: +{n \choose n} x^{0} y^n \\
&= 1 \cdot x^n \cdot 1 + n \cdot x^{n-1} y^1 + \: ... \: +  1 \cdot y^n \cdot 1 \\
\end{split}
$$
- the result of $(x+y)^n$ will be a [[sum]] of $n$ terms each of them will contain the product of $x^i\cdot y^j$ with $i + j = n$ 
- the coefficent ${n \choose k} ={i+j \choose i}={i+j \choose j}$ is the number possibilies to produce $x^i\cdot y^j$ 

# anki
START
Basic
[[binomial theorem]] with (informal) [[combinatorial methods|combinatorical]] [[proof]]
- plus name a different way now to prove it

Back: 
$$
(x+y)^n = \sum_{k=0}^n {n \choose k} x^{n-k} y^k
$$

proof

$$
\begin{split}
\sum_{k=0}^n {n \choose k} x^{n-k} y^k 
&= {n \choose 0} x^n y^0 + {n \choose 1} x^{n-1} y^1 + \: ... \: +{n \choose n} x^{0} y^n \\
&= 1 \cdot x^n \cdot 1 + n \cdot x^{n-1} y^1 + \: ... \: +  1 \cdot y^n \cdot 1 \\
\end{split}
$$
- the result of $(x+y)^n$ will be a [[sum]] of $n$ terms each of them will contain the product of $x^i\cdot y^j$ with $i + j = n$ 
- the coefficent ${n \choose k} ={i+j \choose i}={i+j \choose j}$ is the number possibilies to produce $x^i\cdot y^j$ 


([[proof by induction]] would also be possible)
Tags: mathematics
<!--ID: 1689496952607-->
END