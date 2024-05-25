
### probability mass function (PMF)
A discrete probability function $f_X(x)$ of a [[random variable]] $X$ for a given real number gives the [[probability]] that $X$ takes the value.
$$f_X(x): \mathbb{R} \mapsto [0,1] = P(X=x)$$
probability of [[set|sets]] of real values
The probability that the [[probability mass function (PMF)]] $X$ is inside the [[set]] of real number $C \subseteq \mathbb{R}$ is equal to the sum of the probabilities of its set elements $x_i \in C$
$$
P(X \in C) = \sum\limits_{x_i \in C} f_X(x_i)
$$
A [[random variable]] in a [[probability space]] is a mapping from the [[sample space]] to a [[measurable space]] (often real numbers). A [[probability mass function (PMF)]] is a [[random variable]] that can take only a finite number of values or at most infinite but [[countable]] number of values.



# ----------------------

![[probability space#probability space]]

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