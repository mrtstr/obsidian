
### probability mass function (PMF)
- given a [[random variable]] $X$ in a [[discrete probability space]] $(\Omega, \mathcal{A}, P)$ 

$$f_X(x): \mathbb{R} \mapsto [0,1] = P(X=x)$$

The probability that the [[probability mass function (PMF)]] $X$ is inside the [[set]] of real number $C \subseteq \mathbb{R}$ is equal to the sum of the probabilities of its set elements $x_i \in C$
$$
P(X \in C) = \sum\limits_{x_i \in C} f_X(x_i)
$$
A [[random variable]] in a [[probability space]] is a mapping from the [[sample space]] to a [[measurable space]] (often real numbers). A [[probability mass function (PMF)]] is a [[random variable]] that can take only a finite number of values or at most infinite but [[countable]] number of values.


### Example
The [[sample space]] is containing all possible outcomes $\Omega = \left\{H, T\right\}^{10}$ with $\left|\Omega\right|=2^{10}$. We can define a [[probability mass function (PMF)]] on $\Omega$ that is counting the number of heads $X: \Omega \mapsto \left\{1,..,10\right\}$. 
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

# ----------------------
![[continuous probability space#continuous probability space]]

![[random variable#a random variable induces a probability measure]]


![[random variable#random variable]]

![[probability space#probability space]]


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





# ----------------------


![[discrete distribution#discrete distribution]]

START
Basic
[[probability mass function (PMF)]]:
- definition
- example
Back: 
A [[random variable]] in a [[probability space]] is a mapping from the [[sample space]] to a [[measurable space]] (often real numbers). A [[probability mass function (PMF)]] is a [[random variable]] that can take only a finite number of values or at most infinite but [[countable]] number of values.

## Definition
$$
X: \Omega \mapsto \mathbb{R}
$$
For every [[set]] of real values  $\left\{\omega \mid X(\omega \in \Omega) \in C\right\} \in \mathcal{F}$, we can define a [[probability]] that $X$ takes a value inside $C$. This can be defined in the original [[probability space]] with the corresponding [[event]] $\left\{\omega \mid X(\omega \in \Omega) \in C\right\} \in \mathcal{F}$ inside the [[event space]].
$$
P(X \in C) = P\left(\left\{\omega \mid X(\omega) \in C\right\}\right)
$$
## Example: tossing a coin 10 times
The [[sample space]] is containing all possible outcomes $\Omega = \left\{H, T\right\}^{10}$ with $\left|\Omega\right|=2^{10}$. We can define a [[probability mass function (PMF)]] on $\Omega$ that is counting the number of heads $X: \Omega \mapsto \left\{1,..,10\right\}$.

Tags: mathematics statistics
<!--ID: 1664442661951-->
END


START
Basic
[[probability mass function (PMF)]]:
- [[discrete distribution]]
- probability function
- probability of [[set|sets]] of real values
- support of a [[probability mass function (PMF)]]
Back: 
## [[discrete distribution]] 
Given all possible [[set|sets]] of real values $C \subseteq \mathbb{R}$. Each [[set]] $C$ defines a [[event]] in the original [[probability space]].  The [[discrete distribution|distribution]] of a [[probability mass function (PMF)]] is [[set]] of the [[probability|probabilities]] of these [[event|events]].
$$
\left\{P(X \in C) \mid C \subseteq \mathbb{R} \right\} = \left\{P\left(\left\{\omega \mid X(\omega) \in C\right\} \right) \mid C \subseteq \mathbb{R}\right\}
$$

## Discrete probability function
A discrete probability function $f_X(x)$ of a [[random variable]] $X$ for a given real number gives the [[probability]] that $X$ takes the value.
$$f_X(x): \mathbb{R} \mapsto [0,1] = P(X=x)$$
## probability of [[set|sets]] of real values
The probability that the [[probability mass function (PMF)]] $X$ is inside the [[set]] of real number $C \subseteq \mathbb{R}$ is equal to the sum of the probabilities of its set elements $x_i \in C$
$$
P(X \in C) = \sum\limits_{x_i \in C} f_X(x_i)
$$
## support of a [[probability mass function (PMF)]]
Is the [[set]] of values with a probability greater than zero
$$
\left\{ x \mid f_X(x) > 0\right\}
$$

Tags: mathematics statistics
<!--ID: 1667211139255-->
END



START
Basic
[[discrete distribution]] of a [[probability mass function (PMF)]]:
- definition
- example
Back: 
Given a [[probability mass function (PMF)]] $X: \Omega \mapsto \mathbb{R}$ on a [[sample space]] $\Omega$ we can derive [[event|events]] for all [[set|sets]] of real values $C \subseteq \mathbb{R}$ on the original [[probability space]].
The [[discrete distribution]] of a [[probability mass function (PMF)]] is the collection of the [[probability|probabilities]] of these [[event|events]] $X \in C$.
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