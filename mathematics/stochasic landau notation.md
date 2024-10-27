### stochasic landau notation

#### big O: stochstic bounded
- means that the term $\left|\frac{X_n}{a_n}\right|$ is bounded thus there is a constant value $M$ that is lager alomst surely

$$
\begin{split}
&X_n = \mathcal{O}_p(a_n) \\
&\Leftrightarrow  \exists M > 0 : \lim_{n \to \infty} \mathbb{P}\left(\left|\frac{X_n}{a_n}\right| > M\right) =0\\
&\Leftrightarrow  \exists M > 0: \forall \varepsilon > 0: N > 0: \forall n > N: \mathbb{P}\left(\left|\frac{X_n}{a_n}\right| > M\right) \leq \varepsilon \\
\end{split}
$$

- case $X_n = \mathcal{O}_p(1)$ means that $X_n$ is bounded by a constant alomst surely

#### small o
- means that the probability of $\left|\frac{X_n}{a_n}\right|$ [[convergence in probability|converges in probability]] to zero 

$$
\begin{split}
&X_n = \mathcal{o}_p(a_n) \\
&\Leftrightarrow \forall \delta > 0: \lim_{n \to \infty} \mathbb{P}\left(\left|\frac{X_n}{a_n}\right| > \delta \right) = 0 \\
&\Leftrightarrow \forall \delta > 0: \forall \epsilon > 0: \exists N \in \mathbb{N} : \forall n > N: \mathbb{P}\left(\left|\frac{X_n}{a_n}\right| > \delta\right) \leq \varepsilon \\
\end{split}
$$

#### difference
- for the big O notation its sufficient that it's bounded while for the small o notation the term has to go to zero


Algebra Rules
Can manipulate these algebraically if we are careful.
O(an)O(bn) = O(anbn)
cO(an) = O(an)
O(an)OP (bn) = OP (anbn)
OP (an)OP (bn) = OP (anbn)
O(an) + O(bn) = O(max{an, bn})
OP (an) + OP (bn) = OP (max{an, bn})


O(an)o(bn) = o(anbn)
o(O(an)) = o(an)
o(an)OP (bn) = oP (anbn)
oP (an)OP (bn) = oP (anbn)
o(an) + O(bn) = O(max{an, bn})
oP (an) + OP (bn) = OP (max{an, bn})
# -----------------
![[convergence in probability#convergence in probability]]


# anki

START
Basic
[[stochasic landau notation]]
- definition big vs small 0
- interpretation
- relationship to [[convergence in probability]]
- difference

Back: 
### stochasic landau notation

#### big O: stochstic bounded
- means that the term $\left|\frac{X_n}{a_n}\right|$ is bounded thus there is a constant value $M$ that is lager alomst surely

$$
\begin{split}
&X_n = \mathcal{O}_p(a_n) \\
&\Leftrightarrow  \exists M > 0 : \lim_{n \to \infty} \mathbb{P}\left(\left|\frac{X_n}{a_n}\right| > M\right) =0\\
&\Leftrightarrow  \exists M > 0: \forall \varepsilon > 0: N > 0: \forall n > N: \mathbb{P}\left(\left|\frac{X_n}{a_n}\right| > M\right) \leq \varepsilon \\
\end{split}
$$

- case $X_n = \mathcal{O}_p(1)$ means that $X_n$ is bounded by a constant alomst surely

#### small o
- means that the probability of $\left|\frac{X_n}{a_n}\right|$ [[convergence in probability|converges in probability]] to zero 

$$
\begin{split}
&X_n = \mathcal{o}_p(a_n) \\
&\Leftrightarrow \forall \delta > 0: \lim_{n \to \infty} \mathbb{P}\left(\left|\frac{X_n}{a_n}\right| > \delta \right) = 0 \\
&\Leftrightarrow \forall \delta > 0: \forall \epsilon > 0: \exists N \in \mathbb{N} : \forall n > N: \mathbb{P}\left(\left|\frac{X_n}{a_n}\right| > \delta\right) \leq \varepsilon \\
\end{split}
$$

#### difference
- for the big O notation its sufficient that it's bounded while for the small o notation the term has to go to zero

___________

### convergence in probability
- given a sequence of [[random variable]] $\{X_n\}$
- $X_n$ is converging against a [[random variable]] $X$ is the following is true

$$
\forall \epsilon > 0: \lim_{n \to \infty}\mathbb{P}\left(|X_n - X | \geq \epsilon\right)
$$
#### equivalent statements

$$
\mathbb{P}(X_n \leq x) \to \mathbb{P}(X \leq x)
$$

$$
\mathbb{E}[X_n] \to \mathbb{E}[X_n]
$$


Tags: mathematics statistics WS2425
<!--ID: 1729348023066-->
END