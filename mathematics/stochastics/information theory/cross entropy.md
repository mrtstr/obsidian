### cross entropy
- [[cross entropy]] is a measure of the dissimilarity between two probability distributions: a **true distribution** $P$ and an **estimated (or assumed) distribution** $Q$
- It quantifies the **expected number of bits** needed to encode samples from $P$
  using a code that is optimized for $Q$
- It is defined as the **expected negative log-likelihood** under $Q$
  when the data is actually drawn from $P$

#### Continuous Case

$$
\begin{split}
H\left(P , Q \right) 
&= - \int_\mathbb{R} p(x) \log \left( q(x) \right) dx \\
&= - \mathbb{E}_p\left[\log \left( q(x) \right)\right] \\
\end{split}
$$

#### Discrete Case

$$
\begin{split}
H\left(P , Q \right) 
&= - \sum_{x \in \mathcal{X}} p(x) \log \left( q(x) \right) dx \\
&= - \mathbb{E}_p\left[\log \left( q(x) \right)\right] \\
\end{split}
$$

#### range
- The **minimum** cross-entropy is reached when $P=Q$ in which case it reduces to the **entropy** of $P$:

$$
H(P, Q) = H(P) \quad \text{if and only if} \quad P = Q
$$

- can go to infinity if there are regions where  $p(x) > 0$ but $q(x) = 0$ because $\log \left(q(x)\right)=\log \left(0\right) = -\infty$, and thus the expectation $-\mathbb{E}_{x \sim P}[\log q(x)]$ becomes infinite.

$$
\text{supp}(P) \nsubseteq \text{supp}(Q)
$$
### cross entropy of independent random variables

$$
\begin{split}
H\left(P , Q \right) 
&= - \int_\mathbb{R} p(x) \log \left( q(x) \right) dx \\

\end{split}
$$
# -------

![[entropy#entropy]]
# anki

START
Basic
[[cross entropy]]
- definition
- intuition
- range with edge cases

Back: 
### cross entropy
- [[cross entropy]] is a measure of the dissimilarity between two probability distributions: a **true distribution** $P$ and an **estimated (or assumed) distribution** $Q$
- It quantifies the **expected number of bits** needed to encode samples from $P$
  using a code that is optimized for $Q$
- It is defined as the **expected negative log-likelihood** under $Q$
  when the data is actually drawn from $P$

#### Continuous Case

$$
\begin{split}
H\left(P , Q \right) 
&= - \int_\mathbb{R} p(x) \log \left( q(x) \right) dx \\
&= - \mathbb{E}_p\left[\log \left( q(x) \right)\right] \\
\end{split}
$$

#### Discrete Case

$$
\begin{split}
H\left(P , Q \right) 
&= - \sum_{x \in \mathcal{X}} p(x) \log \left( q(x) \right) dx \\
&= - \mathbb{E}_p\left[\log \left( q(x) \right)\right] \\
\end{split}
$$

#### range
- The **minimum** cross-entropy is reached when $P=Q$ in which case it reduces to the **entropy** of $P$:

$$
H(P, Q) = H(P) \quad \text{if and only if} \quad P = Q
$$

- can go to infinity if there are regions where  $p(x) > 0$ but $q(x) = 0$ because $\log \left(q(x)\right)=\log \left(0\right) = -\infty$, and thus the expectation $-\mathbb{E}_{x \sim P}[\log q(x)]$ becomes infinite.

$$
\text{supp}(P) \nsubseteq \text{supp}(Q)
$$

_______________


### entropy
- measure of the **average amount of information** contained in an observation of a [[random variable]] in bits (if the $\log_2$ is used)
- in other words the average amount of removed uncertainty by an observation 
- for a discrete random variable with the [[probability function]] $p_X$ the [[entropy]] is defined as follows

$$
H(X) = \mathbb{E}\left[-\log\left(p_X(X)\right)\right] = - \sum p_X(x_i) \log\left(p_X(x_i)\right)
$$

- $H(X)$ is positive, and its maximum value depends on the [[distribution]] of $X$
##### example
- [[bernoulli distribution]] with $p=0.9$ and $p=0.5$
- We see that the entropy is **higher** when $p=0.5$, indicating that this outcome is **more uncertain** and thus contains **more information per observation**.

$$
\begin{split}
H(X) &= - 0.1 \cdot \log_2(0.1) - 0.9 \cdot \log_2(0.9) = 0.33 + 0.14 = 0.47 \\
H(X) &= - 0.5 \cdot \log_2(0.5) - 0.5 \cdot \log_2(0.5) = \frac{1}{2} + \frac{1}{2} = 1 \\
\end{split}
$$

### differential entropy
- for continuous random variables the concept of [[entropy]] can be extended
- does not have an intuitive interpretation other than **measurement for uncertainty or spread**
- other than the [[entropy]] the differential entropy can be negative and is sensitive to scaling

- for a continuous random variable with the [[probability density function (PDF)]] $f_X$ the differential entropy is defined as follows

$$
H(X) = \mathbb{E}\left[-\log\left(f_X(X)\right)\right] = - \int_\mathbb{R} f_X(x) \log\left(f_X(x)\right) dx
$$
##### example
- [[exponential distribution]]

$$
\begin{split}
H(X) 
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \ln\left(\lambda e^{-\lambda x})\right) dx \\
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \left(\ln(\lambda)  -\lambda x\right) dx \\
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \ln(\lambda) dx + \lambda \int_\mathbb{R} \lambda e^{-\lambda x}  x dx \\
&= - \ln(\lambda) + \lambda \int_\mathbb{R}  \mathbb{E}[X] \\
&= - \ln(\lambda) + \frac{\lambda}{\lambda} \\
&= 1 - \ln(\lambda) \\
\end{split}
$$

- the higher $\lambda$ is the less the PDF spreads thus $1-\ln(2)=0.3<1-\ln(1)=1$

Tags: mathematics statistics SS25
<!--ID: 1748278959140-->
END