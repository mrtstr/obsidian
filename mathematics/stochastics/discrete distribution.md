random variable
Given a [[random variable|discrete]] [[random variable]] (can take only finite or at least [[countable]] values)  $X: \Omega \mapsto \mathbb{R}$ on a [[sample space]] $\Omega$ we can derive [[event|events]] for all [[set|sets]] of real values $C \subseteq \mathbb{R}$ on the original [[probability space]]. The [[discrete distribution]] of a [[discrete random variable]] is the collection of the [[probability|probabilities]] of these [[event|events]] $X \in C$.
$$
\left\{P(X \in C) \mid C \subseteq \mathbb{R} \right\} = \left\{P\left(\left\{\omega \mid X(\omega) \in C\right\} \right) \mid C \subseteq \mathbb{R}\right\}
$$

### Example: tossing a coin 10 times
The [[sample space]] is containing all possible outcomes $\Omega = \left\{H, T\right\}^{10}$ with $\left|\Omega\right|=2^{10}$. We can define a [[discrete random variable]] on $\Omega$ that is counting the number of heads $X: \Omega \mapsto \left\{1,..,10\right\}$. 
For every [[set]] of numbers we can define an [[event]] with a [[probability]].
$$
\begin{split}
&C = \{10\} \\
&\Rightarrow \left\{ X \in \Omega \right\} =  \left\{\omega \mid X(\omega) \in C\right\} = \{HHHHHHHHHH\} \\
&\Rightarrow P\left(\left\{ X \in \Omega \right\}\right) = \frac{1}{2^{10}}
\\ \\
&C = \{9, 10\} \\
&\Rightarrow \left\{ X \in \Omega \right\} =  \left\{\omega \mid X(\omega) \in C\right\} = \{H^{10}, TH^9, HTH^8, ...\} \\
&\Rightarrow P\left(\left\{ X \in \Omega \right\}\right) = \frac{1 + 10}{2^{10}}
\end{split}
$$ 

## important [[discrete distribution]]

## [[bernoulli distribution|bernoulli distribution]]
![[bernoulli distribution#probability function]]
## [[discrete uniform distribution]]
![[discrete uniform distribution#probability function]]
## [[binomial distribution]]
![[binomial distribution#probability function]]
### [[poisson distribution]]
![[poisson distribution#probability function]]
### [[hypergeometric distribution]]
![[hypergeometric distribution#probability function]]

START
Basic
[[discrete distribution]] of a [[discrete random variable]]:
- definition
- example
Back: 
Given a [[discrete random variable]] $X: \Omega \mapsto \mathbb{R}$ on a [[sample space]] $\Omega$ we can derive [[event|events]] for all [[set|sets]] of real values $C \subseteq \mathbb{R}$ on the original [[probability space]].
The [[discrete distribution]] of a [[discrete random variable]] is the collection of the [[probability|probabilities]] of these [[event|events]] $X \in C$.
$$

\left\{P(X \in C) \mid C \subseteq \mathbb{R} \right\} = \left\{P\left(\left\{\omega \mid X(\omega) \in C\right\} \right) \mid C \subseteq \mathbb{R}\right\}

$$

### Example: tossing a coin 10 times
The [[sample space]] is containing all possible outcomes $\Omega = \left\{H, T\right\}^{10}$ with $\left|\Omega\right|=2^{10}$. We can define a [[random variable]] on $\Omega$ that is counting the number of heads $X: \Omega \mapsto \left\{1,..,10\right\}$. 
For every [[set]] of numbers we can define an [[event]] with a [[probability]].
$$
\begin{split}
&C = \{10\} \\
&\Rightarrow \left\{ X \in \Omega \right\} =  \left\{\omega \mid X(\omega) \in C\right\} = \{HHHHHHHHHH\} \\
&\Rightarrow P\left(\left\{ X \in \Omega \right\}\right) = \frac{1}{2^{10}}
\\ \\
&C = \{9, 10\} \\
&\Rightarrow \left\{ X \in \Omega \right\} =  \left\{\omega \mid X(\omega) \in C\right\} = \{H^{10}, TH^9, HTH^8, ...\} \\
&\Rightarrow P\left(\left\{ X \in \Omega \right\}\right) = \frac{1 + 10}{2^{10}}
\end{split}
$$ 
Tags: mathematics statistics
<!--ID: 1667204899520-->
END


START
Basic
## important [[discrete distribution]] summary
- [[probability function]]
- explainaition
Back: 

### [[bernoulli distribution]]
- binary [[random experiment]] 
- $p=$ probability of positive outcome
$$
\begin{split}
f_X(x | p) &= 
\begin{cases}
    p,& \text{if } x= 1\\
    1-p,& \text{if } x= 0\\
    0,              & \text{otherwise}
\end{cases} \\
&= 
\begin{cases}
    p^x (1-p)^{1-x},& \text{if } x= 0,1\\
    0,              & \text{otherwise}
\end{cases}
\end{split}
$$
### [[binomial distribution]]
- $n =$ number of [[bernoulli distribution|bernoulli experiments]] 
- $p=$ probability of positive outcome
- $x=$ number of positive outcomes

$$
f_X(X = x | n, p)= 
\begin{cases}
\overbrace{{n \choose x}}^\text{number of valid splits }
\overbrace{p^{x}(1-p)^{n-x}}^\text{ probability per split}
 
,& \text{if } x \in \{0,1,2,..., n\}\\
0
,& \text{otherwise}
\end{cases}
$$

### [[poisson distribution]]
- $\lambda = np$ with $n =$ number of [[bernoulli distribution|bernoulli experiments]] and $p=$ probability of positive outcome
- assumtions: $p \ll 1 \Leftrightarrow x \ll n$
- $x=$ number of positive outcomes
$$
f_X(x | \lambda) =
\begin{cases}
\frac{\lambda^xe^{-\lambda}}{x!}
& \text{if } x \in \{0,1,2,..., n\}\\
0
& \text{otherwise}
\end{cases}
$$

### [[hypergeometric distribution]]
- $n =$ number of [[unordered sampling without replacement|unordered samples without replacement]] 
- $a=$ number of positive balls
- $b=$ number of negative balls
- $x=$ number of positive outcomes
$$
f_X({x|a,b,n}) = \frac{
{a \choose x}{b \choose n-x}
}{{a+b \choose n}}
\quad for \: max\{0, n-b\}<x<min\{n, a\}
$$
### [[discrete uniform distribution]]
- has the same probability of taking all integers inside a range $\{a,...,b\}$ and 0 for all other values

$$
f_X(X = x | a, b)= 
\begin{cases}
\frac{1}{b-a+1}
,& \text{if } x \in \{a,a+1,...,b-1, b\}\\
0
,& \text{otherwise}
\end{cases}
$$

Tags: mathematics statistics
<!--ID: 1678520971208-->
END

