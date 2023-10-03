Any [[linear equation system]] can be represented using a [[matrix]] $A$ and a [[vector]] $b$
![[matrix#Matrix Definition]]

![[vector#vector Definition]]
## Defintion [[linear equation system]]
$$
\begin{split}
Ax&=b  \\
A_{(*,1)}x_1 + ...+ A_{(*,m)}x_m&=b  \\
A  \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}} &= \mathbb{R}^{n \times m}  \\
x \in \mathbb{R^{\left| \mathcal{J} \right|}}&= \mathbb{R}^{m}  \\
b \in \mathbb{R^{\left| \mathcal{I} \right|}}&= \mathbb{R}^{n}   \\
\end{split}
$$
- $n$ = number of equation
- $m$ = number of unknown valiables
## The solution set

The solution [[set]] $X$ is the [[set]] of all $x_k$ that satisy all equations
$$
X = \{x | Ax=b\}
$$
There are 3 possible situations
1) A unique sotution: $|X|=1$ 
2) No solution: $X=\emptyset$ 
3) Infinite solutions: $|X|=\infty$ 

## Consitency
A [[linear equation system]] is concitent if at least one solution $x$ exists that satisfies all equations.
$$
\begin{split}
&\text{the system of equation is consitent}\\
\Leftrightarrow&\exists x \text{ with }Ax=b \\
\Leftrightarrow&|X| \geq 0   \\
\end{split}
$$
## over and under determined [[linear equation system]]
#### under determined [[linear equation system]]
A [[linear equation system]] is under determined is there are fewer parameters $m$ then equations $n$. In this case there are either no or infinite solutions.
$$
\begin{split}
&m > n 
\Rightarrow& |X| = \infty \text{ or } |X| = 0 \\
\end{split}
$$
$|X| = 0$ is the case if there exist at least one pair of contradictory equations. Otherwise, $|X| = \infty$.
#### over determined [[linear equation system]]
A [[linear equation system]] is over determined is there are more parameters $m$ then equations $n$. There are almost always not solutions exept when all pairs of linear dependent equations are a scaled version of oneonther.
$$
\begin{split}
A_{(l,*)} \perp A_{(k,*)} 
\Rightarrow&\begin{pmatrix}  A_{(l,*)} \\ b_l   \end{pmatrix} = \begin{pmatrix}  A_{(k,*)} \\ b_k   \end{pmatrix} \cdot c \\
\end{split}
$$

## Existence Theorem
## given

![[rank#Definition]]
### Theorem
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
\Leftrightarrow& A_{(*:1)}x_1 + ... +A_{(*:n)}x_1 x_n =b  \\
\Leftrightarrow& b \text{ is a linear combination of} \{A_{(*:1)}, ... A_{(*:n)}\}  \\
\Leftrightarrow& rank(A) = rank\left(A|b\right)  \\
\end{split}
$$
### intutition
When there exists a valid solution, it can be one of the following two cases:
1) All row vectors of $A$ $\{A_{(1,*)}, ... , A_{(m,*)}\}$ are [[linear independent]]. In this case there will allways exist a [[intersection]] between the [[vector|vectors]] and thus there will exist a solution.
2) The equations represented by the linear dependent $A_{(l,*)}$ $A_{(k,*)}$ represent the same equation but scaled with facor $c$. In this case, the equations will have the same solution. In this case $\begin{pmatrix}  A_{(l,*)} \\ b_l   \end{pmatrix}$ and $\begin{pmatrix}  A_{(k,*)} \\ b_k   \end{pmatrix}$ will also be linear dependent.
$$
\begin{split}
&\begin{pmatrix}  A_{(l,*)} \\ b_l   \end{pmatrix} = \begin{pmatrix}  A_{(k,*)} \\ b_k   \end{pmatrix} \cdot c \\
\end{split}
$$
## general uniqueness theorem
### theorem
$$
\begin{split}
&Ax=b \\
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
### pseudo proof
The [[linear equation system]] can't be unterdetermined $m > n$ since it would have either contradictory equations or infinite solutions. So 
1) If $A$ is a [[square matrix]] $(m=n)$ the [[linear equation system]] has a unique solution if $A$ is a [[regular matrix]] ($\Leftrightarrow n=rank(A)$)
2) The [[linear equation system]] is overdetermined $m < n$ thus there are more equations than variables. In this case, the [[linear equation system]] is inconsitent except when all linear dependent equations represent a scaled version of oneonother and there exist $n$ non-equivalent equations, which is the case when $rank\left(A|b\right) = n$ 

# Anki
START
Basic
[[linear equation system]] existence theorem
- proof
- intutition
Back: 

## Defintion [[linear equation system]]
$$
\begin{split}
Ax&=b  \\
A_{(*,1)}x_1 + ...+ A_{(*,m)}x_m&=b  \\
A  \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}} &= \mathbb{R}^{n \times m}  \\
x \in \mathbb{R^{\left| \mathcal{J} \right|}}&= \mathbb{R}^{m}  \\
b \in \mathbb{R^{\left| \mathcal{I} \right|}}&= \mathbb{R}^{n}   \\
\end{split}
$$
- $n$ = number of equation
- $m$ = number of unknown valiables
## Definition [[rank]]

- The [[rank]] is equal to the number of [[linear independent]] columns vectors $A_{(*,j)}$
- The [[rank]] is equal to the number of [[linear independent]] row vectors $A_{(i,*)}$
- The [[rank]] is equal to the dimensions of the [[column space]]
$$
rank(A) = dim(range(A))
$$
- the [[rank]] is equal to the total number of column vectors $\left| \mathcal{J} \right|$ minus the [[nullity]]

$$
\underbrace{
rank(A)
}_\text{\# linear independent column vectors Aj}
  = 
\underbrace{
\left| \mathcal{J} \right|
}_\text{\# all column vectors Aj}
-
\underbrace{
nullity(A)
}_\text{\# linear dependent column vectors Aj}
$$

## Existence Theorem

### Theorem
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
\Leftrightarrow& A_{(*:1)}x_1 + ... +A_{(*:n)}x_1 x_n =b  \\
\Leftrightarrow& b \text{ is a linear combination of} \{A_{(*:1)}, ... A_{(*:n)}\}  \\
\Leftrightarrow& rank(A) = rank\left(A|b\right)  \\
\end{split}
$$
### intutition
When there exists a valid solution, it can be one of the following two cases:
1) All row vectors of $A$ $\{A_{(1,*)}, ... , A_{(m,*)}\}$ are [[linear independent]]. In this case there will allways exist a [[intersection]] between the [[vector|vectors]] and thus there will exist a solution.
2) The equations represented by the linear dependent $A_{(l,*)}$ $A_{(k,*)}$ represent the same equation but scaled with facor $c$. In this case, the equations will have the same solution. In this case $\begin{pmatrix}  A_{(l,*)} \\ b_l   \end{pmatrix}$ and $\begin{pmatrix}  A_{(k,*)} \\ b_k   \end{pmatrix}$ will also be linear dependent.
$$
\begin{split}
&\begin{pmatrix}  A_{(l,*)} \\ b_l   \end{pmatrix} = \begin{pmatrix}  A_{(k,*)} \\ b_k   \end{pmatrix} \cdot c \\
\end{split}
$$

Tags: mathematics linear_algebra
<!--ID: 1696327595051-->
END


START
Basic
[[linear equation system]]
- defintion and solution set and Consitency
Back: 
## Defintion [[linear equation system]]
$$
\begin{split}
Ax&=b  \\
A_{(*,1)}x_1 + ...+ A_{(*,m)}x_m&=b  \\
A  \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}} &= \mathbb{R}^{n \times m}  \\
x \in \mathbb{R^{\left| \mathcal{J} \right|}}&= \mathbb{R}^{m}  \\
b \in \mathbb{R^{\left| \mathcal{I} \right|}}&= \mathbb{R}^{n}   \\
\end{split}
$$
- $n$ = number of equation
- $m$ = number of unknown valiables
## The solution set

The solution [[set]] $X$ is the [[set]] of all $x_k$ that satisy all equations
$$
X = \{x | Ax=b\}
$$
There are 3 possible situations
1) A unique sotution: $|X|=1$ 
2) No solution: $X=\emptyset$ 
3) Infinite solutions: $|X|=\infty$ 

## Consitency
A [[linear equation system]] is concitent if at least one solution $x$ exists that satisfies all equations.
$$
\begin{split}
&\text{the system of equation is consitent}\\
\Leftrightarrow&\exists x \text{ with }Ax=b \\
\Leftrightarrow&|X| \geq 0   \\
\end{split}
$$

Tags: mathematics linear_algebra
<!--ID: 1696327595056-->
END


START
Basic
over and under determined [[linear equation system]]

Back: 
## Defintion [[linear equation system]]
$$
\begin{split}
Ax&=b  \\
A_{(*,1)}x_1 + ...+ A_{(*,m)}x_m&=b  \\
A  \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}} &= \mathbb{R}^{n \times m}  \\
x \in \mathbb{R^{\left| \mathcal{J} \right|}}&= \mathbb{R}^{m}  \\
b \in \mathbb{R^{\left| \mathcal{I} \right|}}&= \mathbb{R}^{n}   \\
\end{split}
$$
- $n$ = number of equation
- $m$ = number of unknown valiables
## The solution set

The solution [[set]] $X$ is the [[set]] of all $x_k$ that satisy all equations
$$
X = \{x | Ax=b\}
$$
There are 3 possible situations
1) A unique sotution: $|X|=1$ 
2) No solution: $X=\emptyset$ 
3) Infinite solutions: $|X|=\infty$ 


## over and under determined [[linear equation system]]
#### under determined [[linear equation system]]
A [[linear equation system]] is under determined is there are fewer parameters $m$ then equations $n$. In this case there are either no or infinite solutions.
$$
\begin{split}
&m > n 
\Rightarrow& |X| = \infty \text{ or } |X| = 0 \\
\end{split}
$$
$|X| = 0$ is the case if there exist at least one pair of contradictory equations. Otherwise, $|X| = \infty$.
#### over determined [[linear equation system]]
A [[linear equation system]] is over determined is there are more parameters $m$ then equations $n$. There are almost always not solutions exept when all pairs of linear dependent equations are a scaled version of oneonther.
$$
\begin{split}
A_{(l,*)} \perp A_{(k,*)} 
\Rightarrow&\begin{pmatrix}  A_{(l,*)} \\ b_l   \end{pmatrix} = \begin{pmatrix}  A_{(k,*)} \\ b_k   \end{pmatrix} \cdot c \\
\end{split}
$$

Tags: mathematics linear_algebra
<!--ID: 1696341992850-->
END

START
Basic
[[linear equation system]]

Back: 
## Defintion [[linear equation system]]
$$
\begin{split}
Ax&=b  \\
A_{(*,1)}x_1 + ...+ A_{(*,m)}x_m&=b  \\
A  \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}} &= \mathbb{R}^{n \times m}  \\
x \in \mathbb{R^{\left| \mathcal{J} \right|}}&= \mathbb{R}^{m}  \\
b \in \mathbb{R^{\left| \mathcal{I} \right|}}&= \mathbb{R}^{n}   \\
\end{split}
$$
- $n$ = number of equation
- $m$ = number of unknown valiables
## Definition [[rank]]

- The [[rank]] is equal to the number of [[linear independent]] columns vectors $A_{(*,j)}$
- The [[rank]] is equal to the number of [[linear independent]] row vectors $A_{(i,*)}$
- The [[rank]] is equal to the dimensions of the [[column space]]
$$
rank(A) = dim(range(A))
$$
- the [[rank]] is equal to the total number of column vectors $\left| \mathcal{J} \right|$ minus the [[nullity]]

$$
\underbrace{
rank(A)
}_\text{\# linear independent column vectors Aj}
  = 
\underbrace{
\left| \mathcal{J} \right|
}_\text{\# all column vectors Aj}
-
\underbrace{
nullity(A)
}_\text{\# linear dependent column vectors Aj}
$$


## general uniqueness theorem
### theorem
$$
\begin{split}
&Ax=b \\
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
### pseudo proof
The [[linear equation system]] can't be unterdetermined $m > n$ since it would have either contradictory equations or infinite solutions. So 
1) If $A$ is a [[square matrix]] $(m=n)$ the [[linear equation system]] has a unique solution if $A$ is a [[regular matrix]] ($\Leftrightarrow n=rank(A)$)
2) The [[linear equation system]] is overdetermined $m < n$ thus there are more equations than variables. In this case, the [[linear equation system]] is inconsitent except when all linear dependent equations represent a scaled version of oneonother and there exist $n$ non-equivalent equations, which is the case when $rank\left(A|b\right) = n$ 


## Existence Theorem

### Theorem
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
\Leftrightarrow& A_{(*:1)}x_1 + ... +A_{(*:n)}x_1 x_n =b  \\
\Leftrightarrow& b \text{ is a linear combination of} \{A_{(*:1)}, ... A_{(*:n)}\}  \\
\Leftrightarrow& rank(A) = rank\left(A|b\right)  \\
\end{split}
$$
### intutition
When there exists a valid solution, it can be one of the following two cases:
1) All row vectors of $A$ $\{A_{(1,*)}, ... , A_{(m,*)}\}$ are [[linear independent]]. In this case there will allways exist a [[intersection]] between the [[vector|vectors]] and thus there will exist a solution.
2) The equations represented by the linear dependent $A_{(l,*)}$ $A_{(k,*)}$ represent the same equation but scaled with facor $c$. In this case, the equations will have the same solution. In this case $\begin{pmatrix}  A_{(l,*)} \\ b_l   \end{pmatrix}$ and $\begin{pmatrix}  A_{(k,*)} \\ b_k   \end{pmatrix}$ will also be linear dependent.
$$
\begin{split}
&\begin{pmatrix}  A_{(l,*)} \\ b_l   \end{pmatrix} = \begin{pmatrix}  A_{(k,*)} \\ b_k   \end{pmatrix} \cdot c \\
\end{split}
$$

Tags: mathematics linear_algebra
<!--ID: 1696341992856-->
END

END

START
Basic
[[linear equation system]] symmary (no proofs)
- definition
- Consitency
- solutions for over and under determined 
- existence theorem
- uniqueness theorem

Back: 
## Defintion [[linear equation system]]
$$
\begin{split}
Ax&=b  \\
A_{(*,1)}x_1 + ...+ A_{(*,m)}x_m&=b  \\
A  \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}} &= \mathbb{R}^{n \times m}  \\
x \in \mathbb{R^{\left| \mathcal{J} \right|}}&= \mathbb{R}^{m}  \\
b \in \mathbb{R^{\left| \mathcal{I} \right|}}&= \mathbb{R}^{n}   \\
\end{split}
$$
- $n$ = number of equation
- $m$ = number of unknown valiables
## The solution set

The solution [[set]] $X$ is the [[set]] of all $x_k$ that satisy all equations
$$
X = \{x | Ax=b\}
$$
There are 3 possible situations
1) A unique sotution: $|X|=1$ 
2) No solution: $X=\emptyset$ 
3) Infinite solutions: $|X|=\infty$ 

## Consitency
A [[linear equation system]] is concitent if at least one solution $x$ exists that satisfies all equations.
$$
\begin{split}
&\text{the system of equation is consitent}\\
\Leftrightarrow&\exists x \text{ with }Ax=b \\
\Leftrightarrow&|X| \geq 0   \\
\end{split}
$$
## over and under determined [[linear equation system]]
#### under determined [[linear equation system]]
A [[linear equation system]] is under determined is there are fewer parameters $m$ then equations $n$. In this case there are either no or infinite solutions.
$$
\begin{split}
&m > n 
\Rightarrow& |X| = \infty \text{ or } |X| = 0 \\
\end{split}
$$
$|X| = 0$ is the case if there exist at least one pair of contradictory equations. Otherwise, $|X| = \infty$.
#### over determined [[linear equation system]]
A [[linear equation system]] is over determined is there are more parameters $m$ then equations $n$. There are almost always not solutions exept when all pairs of linear dependent equations are a scaled version of oneonther.
$$
\begin{split}
A_{(l,*)} \perp A_{(k,*)} 
\Rightarrow&\begin{pmatrix}  A_{(l,*)} \\ b_l   \end{pmatrix} = \begin{pmatrix}  A_{(k,*)} \\ b_k   \end{pmatrix} \cdot c \\
\end{split}
$$

## Existence Theorem
## given

### Theorem
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
\Leftrightarrow& A_{(*:1)}x_1 + ... +A_{(*:n)}x_1 x_n =b  \\
\Leftrightarrow& b \text{ is a linear combination of} \{A_{(*:1)}, ... A_{(*:n)}\}  \\
\Leftrightarrow& rank(A) = rank\left(A|b\right)  \\
\end{split}
$$
### intutition
When there exists a valid solution, it can be one of the following two cases:
1) All row vectors of $A$ $\{A_{(1,*)}, ... , A_{(m,*)}\}$ are [[linear independent]]. In this case there will allways exist a [[intersection]] between the [[vector|vectors]] and thus there will exist a solution.
2) The equations represented by the linear dependent $A_{(l,*)}$ $A_{(k,*)}$ represent the same equation but scaled with facor $c$. In this case, the equations will have the same solution. In this case $\begin{pmatrix}  A_{(l,*)} \\ b_l   \end{pmatrix}$ and $\begin{pmatrix}  A_{(k,*)} \\ b_k   \end{pmatrix}$ will also be linear dependent.
$$
\begin{split}
&\begin{pmatrix}  A_{(l,*)} \\ b_l   \end{pmatrix} = \begin{pmatrix}  A_{(k,*)} \\ b_k   \end{pmatrix} \cdot c \\
\end{split}
$$
## general uniqueness theorem
### theorem
$$
\begin{split}
&Ax=b \\
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
### pseudo proof
The [[linear equation system]] can't be unterdetermined $m > n$ since it would have either contradictory equations or infinite solutions. So 
1) If $A$ is a [[square matrix]] $(m=n)$ the [[linear equation system]] has a unique solution if $A$ is a [[regular matrix]] ($\Leftrightarrow n=rank(A)$)
2) The [[linear equation system]] is overdetermined $m < n$ thus there are more equations than variables. In this case, the [[linear equation system]] is inconsitent except when all linear dependent equations represent a scaled version of oneonother and there exist $n$ non-equivalent equations, which is the case when $rank\left(A|b\right) = n$ 

Tags: mathematics linear_algebra
<!--ID: 1696341992861-->
END