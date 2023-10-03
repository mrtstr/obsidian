Any [[linear equation]] can be represented using a [[matrix]] $A$ and a [[vector]] $b$
![[matrix#Matrix Definition]]

![[vector#vector Definition]]
## Defintion [[linear equation]]
$$
\begin{split}
&Ax=b \\
&A  \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}} = \mathbb{R}^{n \times m}  \\
&x \in \mathbb{R^{\left| \mathcal{J} \right|}}= \mathbb{R}^{m}  \\
&b \in \mathbb{R^{\left| \mathcal{I} \right|}}= \mathbb{R}^{n}   \\
\end{split}
$$
- $n$ = number of equation
- $m$ = number of unknown valiables
## The solution

The solution [[set]] $X$ is the [[set]] of all $x_k$ that satisy all equations
$$
X = \{x | Ax=b\}
$$
There are 3 possible situations
1) A unique sotution: $|X|=1$ 
2) No solution: $X=\emptyset$ 
3) Infinite solutions: $|X|=\infty$ 

## existence theorem
### theorem
$$
\begin{split}
&Ax=b \\
&A  \in \mathbb{R}^{n \times m}  \\
&X = \{x | Ax=b\}  \\
\end{split}
$$
The following is true
$$
\begin{split}
&rank(A) = rank\left(A|b\right) \Leftrightarrow |X| \geq 1
\end{split}
$$
### proof
$$
\begin{split}
&Ax=b \\
\Leftrightarrow& A_1x_1 + ... +A_n x_n =b  \\
\Leftrightarrow& b \text{ is a linear combination of} \{A_1, ... A_n\}  \\
\Leftrightarrow& rank(A) = rank\left(A|b\right)  \\
\end{split}
$$

## general uniqueness theorem
### theorem
$$
\begin{split}
&Ax=b \\
&b\neq 0 \\
&A  \in \mathbb{R}^{n \times m}  \\
&X = \{x | Ax=b \}  \\
\end{split}
$$
The following is true
$$
\begin{split}
& |X| = 1 \Rightarrow rank(A) = rank\left(A|b\right) = n 
\end{split}
$$


## uniqueness theorem for $n=m$
### theorem
$$
\begin{split}
&Ax=b \\
&b\neq 0 \\
&A  \in \mathbb{R}^{n \times n}  \\
&X = \{x | Ax=b\}  \\
\end{split}
$$
The following is true
$$
\begin{split}
& |X| = 1 \Leftrightarrow rank(A) = n  \\
& |X| = 1 \Leftrightarrow det(A) \neq 0  \\
\end{split}
$$

### proof
$$
\begin{split}
&Ax=b \\
\Leftrightarrow& A_1x_1 + ... +A_n x_n =b  \\
\Leftrightarrow& b \text{ is a linear combination of} \{A_1, ... A_n\}  \\
\Leftrightarrow& rank(A) = rank\left(A|b\right)  \\
\end{split}
$$

# Anki
START
Basic
[[linear equation]]
- existence theorem
Back: 

### theorem
$$
\begin{split}
&Ax=b \\
&A  \in \mathbb{R}^{n \times m}  \\
&X = \{x | Ax=b\}  \\
\end{split}
$$
The following is true
$$
\begin{split}
&rank(A) = rank\left(A|b\right) \Leftrightarrow |X| \geq 1
\end{split}
$$
### proof
$$
\begin{split}
&Ax=b \\
\Leftrightarrow& A_1x_1 + ... +A_n x_n =b  \\
\Leftrightarrow& b \text{ is a linear combination of} \{A_1, ... A_n\}  \\
\Leftrightarrow& rank(A) = rank\left(A|b\right)  \\
\end{split}
$$

## Defintion [[linear equation]]
$$
\begin{split}
&Ax=b \\
&A  \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}} = \mathbb{R}^{n \times m}  \\
&x \in \mathbb{R^{\left| \mathcal{J} \right|}}= \mathbb{R}^{m}  \\
&b \in \mathbb{R^{\left| \mathcal{I} \right|}}= \mathbb{R}^{n}   \\
\end{split}
$$
- $n$ = number of equation
- $m$ = number of unknown valiables
## The solution

The solution [[set]] $X$ is the [[set]] of all $x_k$ that satisy all equations
$$
X = \{x | Ax=b\}
$$
There are 3 possible situations
1) A unique sotution: $|X|=1$ 
2) No solution: $X=\emptyset$ 
3) Infinite solutions: $|X|=\infty$ 

Tags: mathematics linear_algebra
<!--ID: 1696327595051-->
END


START
Basic
[[linear equation]]
- defintion and solution set
Back: 
## Defintion [[linear equation]]
$$
\begin{split}
&Ax=b \\
&A  \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}} = \mathbb{R}^{n \times m}  \\
&x \in \mathbb{R^{\left| \mathcal{J} \right|}}= \mathbb{R}^{m}  \\
&b \in \mathbb{R^{\left| \mathcal{I} \right|}}= \mathbb{R}^{n}   \\
\end{split}
$$
- $n$ = number of equation
- $m$ = number of unknown valiables
## The solution

The solution [[set]] $X$ is the [[set]] of all $x_k$ that satisy all equations
$$
X = \{x | Ax=b\}
$$
There are 3 possible situations
1) A unique sotution: $|X|=1$ 
2) No solution: $X=\emptyset$ 
3) Infinite solutions: $|X|=\infty$ 

Tags: mathematics linear_algebra
<!--ID: 1696327595056-->
END