### product probability space
- given the [[probability space|probability spaces]] $(\Omega_1, \mathcal{A}_1, \mathbb{P}_1)$ and $(\Omega_2, \mathcal{A}_2, \mathbb{P}_2)$
- we can construct a [[product probability space]] $(\Omega_1 \times \Omega_2, \times \mathcal{A}, \mathbb{P})$

$$
\mathcal{A} = \{A_1 \times A_2 : A_1 \in \mathcal{A}_1, A_2 \in \mathcal{A}_2\}
$$

$$
\begin{split}
&\mathcal{A} = \{A_1 \times A_2 : A_1 \in \mathcal{A}_1, A_2 \in \mathcal{A}_2\} \\
&\mathbb{P}(A_1 \times A_2) = \mathbb{P}(A_1)\mathbb{P}(A_2)
\end{split}
$$

# ------------------
![[probability space#probability space]]



START
Basic
[[product probability space]]
- definition

Back: 
### product probability space
- given the [[probability space|probability spaces]] $(\Omega_1, \mathcal{A}_1, \mathbb{P}_1)$ and $(\Omega_2, \mathcal{A}_2, \mathbb{P}_2)$
- we can construct a [[product probability space]] $(\Omega_1 \times \Omega_2, \times \mathcal{A}, \mathbb{P})$

$$
\mathcal{A} = \{A_1 \times A_2 : A_1 \in \mathcal{A}_1, A_2 \in \mathcal{A}_2\}
$$

$$
\begin{split}
&\mathcal{A} = \{A_1 \times A_2 : A_1 \in \mathcal{A}_1, A_2 \in \mathcal{A}_2\} \\
&\mathbb{P}(A_1 \times A_2) = \mathbb{P}(A_1)\mathbb{P}(A_2)
\end{split}
$$

_________________

### probability space
- a [[probability space]] $(\Omega, \mathcal{A}, P)$ is a formal model for a [[random process]]
- if a [[measurable space]] $\left(\Omega, \mathcal{A}=\sigma(\Omega)\right)$ is equiped with a [[probability measure]] $P$ it is a [[probability space]]

#### [[sample space]] $\Omega$
- the nonempty [[set]] $\Omega$ is the [[sample space]] of a [[random experiment]] of it contains all posible outcomes
- the elements of the [[sample space]] are called outcomes $\omega \in \Omega$  
- e.g. for a die throw $\Omega = \left\{1,2,3,4,5,6\right\}$
- can be [[countable]] (in a discrete [[probability space]]) or [[countable|noncountable]] (in a continuous [[probability space]])

#### [[event space]] $\mathcal{A}=\sigma(\Omega)$ 
- [[sigma algebra]] on the [[sample space]]
- an [[event]] is a [[set]] of outcomes $\omega \in \Omega$  
- the [[event space]] is a [[set]] of all possible [[event|envents]] and thus contains subsets of the [[sample space]] $\Omega$ and thus is a subset of the [[power set]] of $\Omega$
$$\mathcal{A} \subseteq \mathcal{P}(\Omega) = \{A \mid A \subseteq \Omega \}$$

- e.g. for a die throw: a [[set]] of numbers between 1 and 6

#### [[probability measure]] $P$
- a [[probability measure]] on the [[measurable space]] $(\Omega, \mathcal{A})$ that assignes a [[probability]] to each event $P: \mathcal{A} \to [0,1]$
- e.g. for a die throw: $P\left(\left\{2,4,6\right\}\right) = \frac{1}{2}$ 


Tags: mathematics statistics
<!--ID: 1717918464913-->
END