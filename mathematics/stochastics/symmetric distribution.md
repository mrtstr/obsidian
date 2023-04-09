
## symmetric around its mean
### Definition
A [[distribution]] is symmetric around its mean iff $f_X(\mu + x) = f_X(\mu - x)$

### [[CDF]] of [[distribution|distributions]] that are symmetric around its mean
$$
\begin{split}
f_X(\mu + x) = f_X(\mu - x) 
&\Rightarrow F_X(\mu + x) = 1- F_X(\mu - x) \\
&\Rightarrow F_X(\mu - x) = 1- F_X(\mu + x) \\
\end{split}
$$
proof
$$
\begin{split}
f_X(\mu + x) = f_X(\mu - x) 
&\Rightarrow P\left(X \leq \mu - x\right) = P\left(X \geq \mu + x\right) \\ 
&\Rightarrow P\left(X \leq \mu - x\right) = 1 - P\left(X \leq \mu + x\right) \\ 
&\Rightarrow F_X\left( \mu - x\right) = 1 - F_X\left( \mu + x\right) \\ 
&\Rightarrow F_X\left( \mu + x\right) = 1 - F_X\left( \mu - x\right) \\ 


\end{split}
$$
## symmetric around zero
### Definition
A [[distribution]] is symmetric around its zero iff $f_X(x) = f_X(- x)$
![[1680838682257.jpg]]
### [[CDF]] of [[distribution|distributions]] that are symmetric around its zero
$$
\begin{split}
f_X(x) = f_X(- x) 
&\Rightarrow F_X(x) = 1- F_X(- x) \\
&\Rightarrow F_X(- x) = 1- F_X( x) \\
\end{split}
$$
proof
$$
\begin{split}
f_X(x) = f_X(- x) 
&\Rightarrow P\left(X \leq - x\right) = P\left(X \geq x\right) \\ 
&\Rightarrow P\left(X \leq - x\right) = 1 - P\left(X \leq  x\right) \\ 
&\Rightarrow F_X\left( x\right) = 1 - F_X\left( x\right) \\ 
&\Rightarrow F_X\left(  x\right) = 1 - F_X\left(  - x\right) \\ 
\end{split}
$$
### [[quantile function]] of [[distribution|distributions]] that are symmetric around its zero
$$
\begin{split}
f_X(x) = f_X(- x) 
&\Rightarrow F_X^{-1}(q) = -F_X^{-1}(1-q) \\
\end{split}
$$
Proof
$$
\begin{split}

1) &\quad f_X(x) = f_X(- x) \Rightarrow F_X(-x) = 1- F_X(x) \\
2) &\quad F_X(x) = q \Leftrightarrow F^{-1}_X(q) = x \\
\\  \\
&\Rightarrow F^{-1}_X\left(F_X(-x)\right) = F^{-1}_X\left(1- F_X(x)\right) \\ 
&\Rightarrow -x = F^{-1}_X\left(1- q\right) \\ 
&\Rightarrow x = -F^{-1}_X\left(1- q\right) \\ 
&\Rightarrow F^{-1}_X(q) = -F^{-1}_X\left(1- q\right) \\ 

\end{split}
$$

# anki

START
Basic
[[symmetric distribution]] (around its mean)
- definition
- [[CDF]] (proof)

Back: 
## symmetric around its mean
### Definition
A [[distribution]] is symmetric around its mean iff $f_X(\mu + x) = f_X(\mu - x)$

### [[CDF]] of [[distribution|distributions]] that are symmetric around its mean
$$
\begin{split}
f_X(\mu + x) = f_X(\mu - x) 
&\Rightarrow F_X(\mu + x) = 1- F_X(\mu - x) \\
&\Rightarrow F_X(\mu - x) = 1- F_X(\mu + x) \\
\end{split}
$$
proof
$$
\begin{split}
f_X(\mu + x) = f_X(\mu - x) 
&\Rightarrow P\left(X \leq \mu - x\right) = P\left(X \geq \mu + x\right) \\ 
&\Rightarrow P\left(X \leq \mu - x\right) = 1 - P\left(X \leq \mu + x\right) \\ 
&\Rightarrow F_X\left( \mu - x\right) = 1 - F_X\left( \mu + x\right) \\ 
&\Rightarrow F_X\left( \mu + x\right) = 1 - F_X\left( \mu - x\right) \\ 


\end{split}
$$

Tags: mathematics statistics
<!--ID: 1680425858038-->
END



START
Basic
[[symmetric distribution]] (around its zero)
- definition
- [[CDF]] (proof)
- [[quantile function]] (proof)
Back: 
## symmetric around zero
### Definition
A [[distribution]] is symmetric around its zero iff $f_X(x) = f_X(- x)$
![[1680838682257.jpg]]
### [[CDF]] of [[distribution|distributions]] that are symmetric around its zero
$$
\begin{split}
f_X(x) = f_X(- x) 
&\Rightarrow F_X(x) = 1- F_X(- x) \\
&\Rightarrow F_X(- x) = 1- F_X( x) \\
\end{split}
$$
proof
$$
\begin{split}
f_X(x) = f_X(- x) 
&\Rightarrow P\left(X \leq - x\right) = P\left(X \geq x\right) \\ 
&\Rightarrow P\left(X \leq - x\right) = 1 - P\left(X \leq  x\right) \\ 
&\Rightarrow F_X\left( x\right) = 1 - F_X\left( x\right) \\ 
&\Rightarrow F_X\left(  x\right) = 1 - F_X\left(  - x\right) \\ 
\end{split}
$$
### [[quantile function]] of [[distribution|distributions]] that are symmetric around its zero
$$
\begin{split}
f_X(x) = f_X(- x) 
&\Rightarrow F_X^{-1}(q) = -F_X^{-1}(1-q) \\
\end{split}
$$
Proof
$$
\begin{split}

1) &\quad f_X(x) = f_X(- x) \Rightarrow F_X(-x) = 1- F_X(x) \\
2) &\quad F_X(x) = q \Leftrightarrow F^{-1}_X(q) = x \\
\\  \\
&\Rightarrow F^{-1}_X\left(F_X(-x)\right) = F^{-1}_X\left(1- F_X(x)\right) \\ 
&\Rightarrow -x = F^{-1}_X\left(1- q\right) \\ 
&\Rightarrow x = -F^{-1}_X\left(1- q\right) \\ 
&\Rightarrow F^{-1}_X(q) = -F^{-1}_X\left(1- q\right) \\ 

\end{split}
$$

Tags: mathematics statistics
<!--ID: 1680839060975-->
END