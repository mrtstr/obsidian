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

### [[bernoulli random variable|bernoulli distribution]]

### [[discrete uniform distribution]]

### [[binomial distribution]]

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
Tags: mathematics, statistics
<!--ID: 1667204899520-->
END