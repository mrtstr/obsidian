### statistical test
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ 
- with a [[disjoint]] seperated [[parameter space]] $\Theta_0$ and $\Theta_1 = \Theta \setminus \Theta_0$ 
- every [[statistics]] $\varphi: \mathfrak{X} \to [0,1]$ is called a [[statistical test]] of the **nullhypothesis** $\Theta_0$ against $\Theta_1$
- given an observation $x \in \mathfrak{X}$ the [[statistics]] $\varphi(x) \in [0,1]$ is the properbility of deciding for the alternative $\Theta_1$ thus the **rejection rate** 
$$
\begin{split}
\varphi(X) = \mathbb{P}\left(H_1 | X\right)
\end{split}
$$

#### randomized vs non-random tests
- non-random tests if $\forall x \in \mathfrak{X}: \varphi(x) \in \{0,1\}$ and random otherwise ($\varphi(x) \in [0,1]$)
- for a non-random test $\varphi$ will look like this:

$$
\varphi\left(X_1, ..., X_n\right) = 
\left\{
\begin{matrix}
1 & \Leftrightarrow & \qquad\text{reject } H_0\\
0 & \Leftrightarrow & \qquad\text{dont reject } H_0\\
\end{matrix} \right.
$$
- for a randomized test $\varphi$ will look like this:
$$
\varphi\left(X_1, ..., X_n\right) = 
\left\{
\begin{matrix}
1 & \Leftrightarrow & \qquad\text{reject } H_0\\
\gamma(x) & \Leftrightarrow &  \\
0 & \Leftrightarrow & \qquad\text{dont reject } H_0\\
\end{matrix} \right.
$$


##### effective level of a [[statistical test]] $\varphi$
- the **effective level** of a [[statistical test]] $\varphi$ is defined as follows
$$
\sup_{\vartheta \in \Theta} \mathbb{E}_{\vartheta} [\varphi]
= \sup_{\vartheta \in \Theta} \mathbb{E}_{x \sim \mathbb{P}_\vartheta} [\varphi(x)]
$$
- it is the maximal value the [[expectation]] of the [[statistical test]] $\varphi$ can take with parameters from the nullhypothesis $\Theta_0$
- thus it is the maximal **expected rejection rate** that is possible with parameters from the nullhypothesis $\Theta_0$ (if the obervations are sampled $x \sim \mathbb{P}_\vartheta$ from the [[distribution]] $\mathbb{P}_\vartheta$)

##### test level of a [[statistical test]] $\varphi$
- a [[statistical test]] $\varphi$ is a test of level $\alpha$ if the following is true
$$
\sup_{\vartheta \in \Theta} \mathbb{E}_{\vartheta} [\varphi] \leq \alpha
$$
- the test level can be interpreted as the confidence level or an **upper bound for the expected rejection rate**

##### power function of a [[statistical test]] $\varphi$
- for a [[statistical test]] $\varphi$ the power function $\beta_\varphi: \Theta \to [0,1]$ is defined as follows 
$$
\beta_\varphi (\vartheta) = \mathbb{E}_{\vartheta} [\varphi] = \mathbb{E}_{x \sim \mathbb{P}_\vartheta} [\varphi(x)] = \mathbb{P}_\vartheta\left(H_1 | X\right)
$$

- the power function $\beta_\varphi$ can be interpreted as the **expected rejection rate** for a given parameter [[set]] $\vartheta$ if the obervations are sampled $x \sim \mathbb{P}_\vartheta$ from the [[distribution]] $\mathbb{P}_\vartheta$
- ideally $\beta_\varphi (\vartheta)$ should be close to $0$ for $\vartheta \in \Theta_0$ and close to $1$ for $\vartheta \in \Theta_1$

#### power function $\beta_\varphi (\vartheta)$ vs [[statistics]] $\varphi(x) \in [0,1]$ 
- both are the proberbility of $H_1$ given the observation $X \in \mathfrak{X}$ but $\varphi(\vartheta(X))$ is a [[statistics]] and thus extracts a characteristic from $\mathbb{P}_\vartheta$ based on an estimated parameters $\vartheta(X)$ 
- the power function $\beta_\varphi (\vartheta)$ evaluates $\mathbb{P}_\vartheta\left(H_1 | X\right)$ for a specific parameter $\vartheta$ 
- this is needed because we want to calculate the [[supremum]] of $\beta_\varphi (\vartheta)$ to extract a specific parameter $\vartheta_0$
### error types

##### type I error
- type I error if $H_0$ is rejected but $H_0$ is correct
- for a given parameter set $\vartheta \in \Theta_0$ the **type I error probability** is given by $\beta_\varphi (\vartheta)$
- thus the **type I error probability** is bounded by the **test level** $\alpha$
- concidered more servere and thus controlled by $\alpha$
→ only the rejection of a hypothesis $H_0$ is reliable

##### type II error
- type II error if $H_0$ is accepted but $H_1$ is correct
- for a given parameter set $\vartheta \in \Theta_1$ the **type II error probability** is given by $1-\beta_\varphi (\vartheta)$
- theoreticly bounded by $1 - \alpha$ but practicly uncontrolled
→ acceptence of $H_0$ is not reliable



### calculation
- given $\alpha$ and an observation $X$

$$
\begin{split}
\sup_{\vartheta \in \Theta_0} \mathbb{P}_{\vartheta}(H_1|X) = \sup_{\vartheta \in \Theta_0} \mathbb{E}_{\vartheta} \left[\varphi \left(X\right)\right] = \alpha \\
\end{split}
$$

- we define $\vartheta_0$ as the parameter that is on the theshold between rejection and accepence of $H_0$
- then we calculate the probability of an observation in $H_1$ (reject $H_0$) under the condition that $H_0$ is true to calculate the upper bound for the rejection rate $\alpha$ for parameters in $\Theta_0$
- then we resolve the equation after $\vartheta_0$ to find the parameter that has a rejection rate of at worst $\alpha$ under the assumtion that $H_0$ is true

# -----------------------


![[statistics#statistics]]

# anki


START
Basic
[[statistical test]]
- definition
- interpretation power function
- interpretation effective level
- interpretation test level
- difference randomized vs non-random tests
Back: 
### statistical test
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ 
- with a [[disjoint]] seperated [[parameter space]] $\Theta_0$ and $\Theta_1 = \Theta \setminus \Theta_0$ 
- every [[statistics]] $\varphi: \mathfrak{X} \to [0,1]$ is called a [[statistical test]] of the **nullhypothesis** $\Theta_0$ against $\Theta_1$
- given an observation $x \in \mathfrak{X}$ the [[statistics]] $\varphi(x) \in [0,1]$ is the properbility of deciding for the alternative $\Theta_1$ thus the **rejection rate**

$$
\begin{split}
\varphi(X) = \mathbb{P}\left(H_1 | X\right)
\end{split}
$$

#### randomized vs non-random tests
- non-random tests if $\forall x \in \mathfrak{X}: \varphi(x) \in \{0,1\}$ and random otherwise ($\varphi(x) \in [0,1]$)
- for a non-random test $\varphi$ will look like this:

$$
\varphi\left(X_1, ..., X_n\right) = 
\left\{
\begin{matrix}
1 & \Leftrightarrow & \qquad\text{reject } H_0\\
0 & \Leftrightarrow & \qquad\text{dont reject } H_0\\
\end{matrix} \right.
$$
- for a randomized test $\varphi$ will look like this:
$$
\varphi\left(X_1, ..., X_n\right) = 
\left\{
\begin{matrix}
1 & \Leftrightarrow & \qquad\text{reject } H_0\\
\gamma(x) & \Leftrightarrow &  \\
0 & \Leftrightarrow & \qquad\text{dont reject } H_0\\
\end{matrix} \right.
$$


##### effective level of a [[statistical test]] $\varphi$
- the **effective level** of a [[statistical test]] $\varphi$ is defined as follows
$$
\sup_{\vartheta \in \Theta} \mathbb{E}_{\vartheta} [\varphi]
= \sup_{\vartheta \in \Theta} \mathbb{E}_{x \sim \mathbb{P}_\vartheta} [\varphi(x)]
$$
- it is the maximal value the [[expectation]] of the [[statistical test]] $\varphi$ can take with parameters from the nullhypothesis $\Theta_0$
- thus it is the maximal **expected rejection rate** that is possible with parameters from the nullhypothesis $\Theta_0$ (if the obervations are sampled $x \sim \mathbb{P}_\vartheta$ from the [[distribution]] $\mathbb{P}_\vartheta$)

##### test level of a [[statistical test]] $\varphi$
- a [[statistical test]] $\varphi$ is a test of level $\alpha$ if the following is true
$$
\sup_{\vartheta \in \Theta} \mathbb{E}_{\vartheta} [\varphi] \leq \alpha
$$
- the test level can be interpreted as the confidence level or an **upper bound for the expected rejection rate**

##### power function of a [[statistical test]] $\varphi$
- for a [[statistical test]] $\varphi$ the power function $\beta_\varphi: \Theta \to [0,1]$ is defined as follows 
$$
\beta_\varphi (\vartheta) = \mathbb{E}_{\vartheta} [\varphi] = \mathbb{E}_{x \sim \mathbb{P}_\vartheta} [\varphi(x)]
$$

- the power function $\beta_\varphi$ can be interpreted as the **expected rejection rate** for a given parameter [[set]] $\vartheta$ if the obervations are sampled $x \sim \mathbb{P}_\vartheta$ from the [[distribution]] $\mathbb{P}_\vartheta$
- ideally $\beta_\varphi (\vartheta)$ should be close to $0$ for $\vartheta \in \Theta_0$ and close to $1$ for $\vartheta \in \Theta_1$

Tags: mathematics statistics
<!--ID: 1719830006825-->
END



START
Basic
[[statistical test]]
- definition
- how what values should the power function ideally take?
- difference between the **effective level** and the **test level** of a [[statistical test]] $\varphi$
Back: 
### statistical test
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ 
- with a [[disjoint]] seperated [[parameter space]] $\Theta_0$ and $\Theta_1 = \Theta \setminus \Theta_0$ 
- every [[statistics]] $\varphi: \mathfrak{X} \to [0,1]$ is called a [[statistical test]] of the **nullhypothesis** $\Theta_0$ against $\Theta_1$
- given an observation $x \in \mathfrak{X}$ the [[statistics]] $\varphi(x) \in [0,1]$ is the properbility of deciding for the alternative $\Theta_1$ thus the **rejection rate**

$$
\begin{split}
\varphi(X) = \mathbb{P}\left(H_1 | X\right)
\end{split}
$$

#### randomized vs non-random tests
- non-random tests if $\forall x \in \mathfrak{X}: \varphi(x) \in \{0,1\}$ and random otherwise ($\varphi(x) \in [0,1]$)
- for a non-random test $\varphi$ will look like this:

$$
\varphi\left(X_1, ..., X_n\right) = 
\left\{
\begin{matrix}
1 & \Leftrightarrow & \qquad\text{reject } H_0\\
0 & \Leftrightarrow & \qquad\text{dont reject } H_0\\
\end{matrix} \right.
$$
- for a randomized test $\varphi$ will look like this:
$$
\varphi\left(X_1, ..., X_n\right) = 
\left\{
\begin{matrix}
1 & \Leftrightarrow & \qquad\text{reject } H_0\\
\gamma(x) & \Leftrightarrow &  \\
0 & \Leftrightarrow & \qquad\text{dont reject } H_0\\
\end{matrix} \right.
$$


##### effective level of a [[statistical test]] $\varphi$
- the **effective level** of a [[statistical test]] $\varphi$ is defined as follows
$$
\sup_{\vartheta \in \Theta} \mathbb{E}_{\vartheta} [\varphi]
= \sup_{\vartheta \in \Theta} \mathbb{E}_{x \sim \mathbb{P}_\vartheta} [\varphi(x)]
$$
- it is the maximal value the [[expectation]] of the [[statistical test]] $\varphi$ can take with parameters from the nullhypothesis $\Theta_0$
- thus it is the maximal **expected rejection rate** that is possible with parameters from the nullhypothesis $\Theta_0$ (if the obervations are sampled $x \sim \mathbb{P}_\vartheta$ from the [[distribution]] $\mathbb{P}_\vartheta$)

##### test level of a [[statistical test]] $\varphi$
- a [[statistical test]] $\varphi$ is a test of level $\alpha$ if the following is true
$$
\sup_{\vartheta \in \Theta} \mathbb{E}_{\vartheta} [\varphi] \leq \alpha
$$
- the test level can be interpreted as the confidence level or an **upper bound for the expected rejection rate**

##### power function of a [[statistical test]] $\varphi$
- for a [[statistical test]] $\varphi$ the power function $\beta_\varphi: \Theta \to [0,1]$ is defined as follows 
$$
\beta_\varphi (\vartheta) = \mathbb{E}_{\vartheta} [\varphi] = \mathbb{E}_{x \sim \mathbb{P}_\vartheta} [\varphi(x)]
$$

- the power function $\beta_\varphi$ can be interpreted as the **expected rejection rate** for a given parameter [[set]] $\vartheta$ if the obervations are sampled $x \sim \mathbb{P}_\vartheta$ from the [[distribution]] $\mathbb{P}_\vartheta$
- ideally $\beta_\varphi (\vartheta)$ should be close to $0$ for $\vartheta \in \Theta_0$ and close to $1$ for $\vartheta \in \Theta_1$

Tags: mathematics statistics
<!--ID: 1719830006831-->
END



START
Basic
[[statistical test]]
- error types
- error rate for a given parameter
- upper bound for errors
Back: 

### error types

##### type I error
- type I error if $H_0$ is rejected but $H_0$ is correct
- for a given parameter set $\vartheta \in \Theta_0$ the **type I error probability** is given by $\beta_\varphi (\vartheta)$
- thus the **type I error probability** is bounded by the **test level** $\alpha$
- concidered more servere and thus controlled by $\alpha$
→ only the rejection of a hypothesis $H_0$ is reliable

##### type II error
- type II error if $H_0$ is accepted but $H_1$ is correct
- for a given parameter set $\vartheta \in \Theta_1$ the **type II error probability** is given by $1-\beta_\varphi (\vartheta)$
- theoreticly bounded by $1 - \alpha$ but practicly uncontrolled
→ acceptence of $H_0$ is not reliable


### statistical test
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ 
- with a [[disjoint]] seperated [[parameter space]] $\Theta_0$ and $\Theta_1 = \Theta \setminus \Theta_0$ 
- every [[statistics]] $\varphi: \mathfrak{X} \to [0,1]$ is called a [[statistical test]] of the **nullhypothesis** $\Theta_0$ against $\Theta_1$
- given an observation $x \in \mathfrak{X}$ the [[statistics]] $\varphi(x) \in [0,1]$ is the properbility of deciding for the alternative $\Theta_1$ thus the **rejection rate**

$$
\begin{split}
\varphi(X) = \mathbb{P}\left(H_1 | X\right)
\end{split}
$$

#### randomized vs non-random tests
- non-random tests if $\forall x \in \mathfrak{X}: \varphi(x) \in \{0,1\}$ and random otherwise ($\varphi(x) \in [0,1]$)
- for a non-random test $\varphi$ will look like this:

$$
\varphi\left(X_1, ..., X_n\right) = 
\left\{
\begin{matrix}
1 & \Leftrightarrow & \qquad\text{reject } H_0\\
0 & \Leftrightarrow & \qquad\text{dont reject } H_0\\
\end{matrix} \right.
$$
- for a randomized test $\varphi$ will look like this:
$$
\varphi\left(X_1, ..., X_n\right) = 
\left\{
\begin{matrix}
1 & \Leftrightarrow & \qquad\text{reject } H_0\\
\gamma(x) & \Leftrightarrow &  \\
0 & \Leftrightarrow & \qquad\text{dont reject } H_0\\
\end{matrix} \right.
$$


##### effective level of a [[statistical test]] $\varphi$
- the **effective level** of a [[statistical test]] $\varphi$ is defined as follows
$$
\sup_{\vartheta \in \Theta} \mathbb{E}_{\vartheta} [\varphi]
= \sup_{\vartheta \in \Theta} \mathbb{E}_{x \sim \mathbb{P}_\vartheta} [\varphi(x)]
$$
- it is the maximal value the [[expectation]] of the [[statistical test]] $\varphi$ can take with parameters from the nullhypothesis $\Theta_0$
- thus it is the maximal **expected rejection rate** that is possible with parameters from the nullhypothesis $\Theta_0$ (if the obervations are sampled $x \sim \mathbb{P}_\vartheta$ from the [[distribution]] $\mathbb{P}_\vartheta$)

##### test level of a [[statistical test]] $\varphi$
- a [[statistical test]] $\varphi$ is a test of level $\alpha$ if the following is true
$$
\sup_{\vartheta \in \Theta} \mathbb{E}_{\vartheta} [\varphi] \leq \alpha
$$
- the test level can be interpreted as the confidence level or an **upper bound for the expected rejection rate**

##### power function of a [[statistical test]] $\varphi$
- for a [[statistical test]] $\varphi$ the power function $\beta_\varphi: \Theta \to [0,1]$ is defined as follows 
$$
\beta_\varphi (\vartheta) = \mathbb{E}_{\vartheta} [\varphi] = \mathbb{E}_{x \sim \mathbb{P}_\vartheta} [\varphi(x)]
$$

- the power function $\beta_\varphi$ can be interpreted as the **expected rejection rate** for a given parameter [[set]] $\vartheta$ if the obervations are sampled $x \sim \mathbb{P}_\vartheta$ from the [[distribution]] $\mathbb{P}_\vartheta$
- ideally $\beta_\varphi (\vartheta)$ should be close to $0$ for $\vartheta \in \Theta_0$ and close to $1$ for $\vartheta \in \Theta_1$

Tags: mathematics statistics
<!--ID: 1719830006834-->
END



START
Basic
[[statistical test]]
- can $H_0$ be reliably accepted or rejected?
- What is the maximal error rate?
Back: 

### error types

##### type I error
- type I error if $H_0$ is rejected but $H_0$ is correct
- for a given parameter set $\vartheta \in \Theta_0$ the **type I error probability** is given by $\beta_\varphi (\vartheta)$
- thus the **type I error probability** is bounded by the **test level** $\alpha$
- concidered more servere and thus controlled by $\alpha$
→ only the rejection of a hypothesis $H_0$ is reliable

##### type II error
- type II error if $H_0$ is accepted but $H_1$ is correct
- for a given parameter set $\vartheta \in \Theta_1$ the **type II error probability** is given by $1-\beta_\varphi (\vartheta)$
- theoreticly bounded by $1 - \alpha$ but practicly uncontrolled
→ acceptence of $H_0$ is not reliable


### statistical test
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ 
- with a [[disjoint]] seperated [[parameter space]] $\Theta_0$ and $\Theta_1 = \Theta \setminus \Theta_0$ 
- every [[statistics]] $\varphi: \mathfrak{X} \to [0,1]$ is called a [[statistical test]] of the **nullhypothesis** $\Theta_0$ against $\Theta_1$
- given an observation $x \in \mathfrak{X}$ the [[statistics]] $\varphi(x) \in [0,1]$ is the properbility of deciding for the alternative $\Theta_1$ thus the **rejection rate**

$$
\begin{split}
\varphi(X) = \mathbb{P}\left(H_1 | X\right)
\end{split}
$$

#### randomized vs non-random tests
- non-random tests if $\forall x \in \mathfrak{X}: \varphi(x) \in \{0,1\}$ and random otherwise ($\varphi(x) \in [0,1]$)
- for a non-random test $\varphi$ will look like this:

$$
\varphi\left(X_1, ..., X_n\right) = 
\left\{
\begin{matrix}
1 & \Leftrightarrow & \qquad\text{reject } H_0\\
0 & \Leftrightarrow & \qquad\text{dont reject } H_0\\
\end{matrix} \right.
$$
- for a randomized test $\varphi$ will look like this:
$$
\varphi\left(X_1, ..., X_n\right) = 
\left\{
\begin{matrix}
1 & \Leftrightarrow & \qquad\text{reject } H_0\\
\gamma(x) & \Leftrightarrow &  \\
0 & \Leftrightarrow & \qquad\text{dont reject } H_0\\
\end{matrix} \right.
$$


##### effective level of a [[statistical test]] $\varphi$
- the **effective level** of a [[statistical test]] $\varphi$ is defined as follows
$$
\sup_{\vartheta \in \Theta} \mathbb{E}_{\vartheta} [\varphi]
= \sup_{\vartheta \in \Theta} \mathbb{E}_{x \sim \mathbb{P}_\vartheta} [\varphi(x)]
$$
- it is the maximal value the [[expectation]] of the [[statistical test]] $\varphi$ can take with parameters from the nullhypothesis $\Theta_0$
- thus it is the maximal **expected rejection rate** that is possible with parameters from the nullhypothesis $\Theta_0$ (if the obervations are sampled $x \sim \mathbb{P}_\vartheta$ from the [[distribution]] $\mathbb{P}_\vartheta$)

##### test level of a [[statistical test]] $\varphi$
- a [[statistical test]] $\varphi$ is a test of level $\alpha$ if the following is true
$$
\sup_{\vartheta \in \Theta} \mathbb{E}_{\vartheta} [\varphi] \leq \alpha
$$
- the test level can be interpreted as the confidence level or an **upper bound for the expected rejection rate**

##### power function of a [[statistical test]] $\varphi$
- for a [[statistical test]] $\varphi$ the power function $\beta_\varphi: \Theta \to [0,1]$ is defined as follows 
$$
\beta_\varphi (\vartheta) = \mathbb{E}_{\vartheta} [\varphi] = \mathbb{E}_{x \sim \mathbb{P}_\vartheta} [\varphi(x)]
$$

- the power function $\beta_\varphi$ can be interpreted as the **expected rejection rate** for a given parameter [[set]] $\vartheta$ if the obervations are sampled $x \sim \mathbb{P}_\vartheta$ from the [[distribution]] $\mathbb{P}_\vartheta$
- ideally $\beta_\varphi (\vartheta)$ should be close to $0$ for $\vartheta \in \Theta_0$ and close to $1$ for $\vartheta \in \Theta_1$

Tags: mathematics statistics
<!--ID: 1719830006837-->
END



START
Basic
[[statistical test]]
- how to calculate it in general?
Back: 

### calculation
- given $\alpha$ and an observation $X$

$$
\begin{split}
\sup_{\vartheta \in \Theta_0} \mathbb{P}_{\vartheta}(H_1|X) = \sup_{\vartheta \in \Theta_0} \mathbb{E}_{\vartheta} \left[\varphi \left(X\right)\right] = \alpha \\
\end{split}
$$

- we define $\vartheta_0$ as the parameter that is on the theshold between rejection and accepence of $H_0$
- then we calculate the probability of an observation in $H_1$ (reject $H_0$) under the condition that $H_0$ is true to calculate the upper bound for the rejection rate $\alpha$ for parameters in $\Theta_0$
- then we resolve the equation after $\vartheta_0$ to find the parameter that has a rejection rate of at worst $\alpha$ under the assumtion that $H_0$ is true

#### power function $\beta_\varphi (\vartheta)$ vs [[statistics]] $\varphi(x) \in [0,1]$ 
- both are the proberbility of $H_1$ given the observation $X \in \mathfrak{X}$ but $\varphi(\vartheta(X))$ is a [[statistics]] and thus extracts a characteristic from $\mathbb{P}_\vartheta$ based on an estimated parameters $\vartheta(X)$ 
- the power function $\beta_\varphi (\vartheta)$ evaluates $\mathbb{P}_\vartheta\left(H_1 | X\right)$ for a specific parameter $\vartheta$ 
- this is needed because we want to calculate the [[supremum]] of $\beta_\varphi (\vartheta)$ to extract a specific parameter $\vartheta_0$

### statistical test
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ 
- with a [[disjoint]] seperated [[parameter space]] $\Theta_0$ and $\Theta_1 = \Theta \setminus \Theta_0$ 
- every [[statistics]] $\varphi: \mathfrak{X} \to [0,1]$ is called a [[statistical test]] of the **nullhypothesis** $\Theta_0$ against $\Theta_1$
- given an observation $x \in \mathfrak{X}$ the [[statistics]] $\varphi(x) \in [0,1]$ is the properbility of deciding for the alternative $\Theta_1$ thus the **rejection rate**

$$
\begin{split}
\varphi(X) = \mathbb{P}\left(H_1 | X\right)
\end{split}
$$

#### randomized vs non-random tests
- non-random tests if $\forall x \in \mathfrak{X}: \varphi(x) \in \{0,1\}$ and random otherwise ($\varphi(x) \in [0,1]$)
- for a non-random test $\varphi$ will look like this:

$$
\varphi\left(X_1, ..., X_n\right) = 
\left\{
\begin{matrix}
1 & \Leftrightarrow & \qquad\text{reject } H_0\\
0 & \Leftrightarrow & \qquad\text{dont reject } H_0\\
\end{matrix} \right.
$$
- for a randomized test $\varphi$ will look like this:
$$
\varphi\left(X_1, ..., X_n\right) = 
\left\{
\begin{matrix}
1 & \Leftrightarrow & \qquad\text{reject } H_0\\
\gamma(x) & \Leftrightarrow &  \\
0 & \Leftrightarrow & \qquad\text{dont reject } H_0\\
\end{matrix} \right.
$$


##### effective level of a [[statistical test]] $\varphi$
- the **effective level** of a [[statistical test]] $\varphi$ is defined as follows
$$
\sup_{\vartheta \in \Theta} \mathbb{E}_{\vartheta} [\varphi]
= \sup_{\vartheta \in \Theta} \mathbb{E}_{x \sim \mathbb{P}_\vartheta} [\varphi(x)]
$$
- it is the maximal value the [[expectation]] of the [[statistical test]] $\varphi$ can take with parameters from the nullhypothesis $\Theta_0$
- thus it is the maximal **expected rejection rate** that is possible with parameters from the nullhypothesis $\Theta_0$ (if the obervations are sampled $x \sim \mathbb{P}_\vartheta$ from the [[distribution]] $\mathbb{P}_\vartheta$)

##### test level of a [[statistical test]] $\varphi$
- a [[statistical test]] $\varphi$ is a test of level $\alpha$ if the following is true
$$
\sup_{\vartheta \in \Theta} \mathbb{E}_{\vartheta} [\varphi] \leq \alpha
$$
- the test level can be interpreted as the confidence level or an **upper bound for the expected rejection rate**

##### power function of a [[statistical test]] $\varphi$
- for a [[statistical test]] $\varphi$ the power function $\beta_\varphi: \Theta \to [0,1]$ is defined as follows 
$$
\beta_\varphi (\vartheta) = \mathbb{E}_{\vartheta} [\varphi] = \mathbb{E}_{x \sim \mathbb{P}_\vartheta} [\varphi(x)]
$$

- the power function $\beta_\varphi$ can be interpreted as the **expected rejection rate** for a given parameter [[set]] $\vartheta$ if the obervations are sampled $x \sim \mathbb{P}_\vartheta$ from the [[distribution]] $\mathbb{P}_\vartheta$
- ideally $\beta_\varphi (\vartheta)$ should be close to $0$ for $\vartheta \in \Theta_0$ and close to $1$ for $\vartheta \in \Theta_1$

Tags: mathematics statistics
<!--ID: 1719947613399-->
END


START
Basic
[[statistical test]]
- difference power function $\beta_\varphi (\vartheta)$ vs [[statistics]] $\varphi(x) \in [0,1]$ 
Back: 
#### power function $\beta_\varphi (\vartheta)$ vs [[statistics]] $\varphi(x) \in [0,1]$ 
- both are the proberbility of $H_1$ given the observation $X \in \mathfrak{X}$ but $\varphi(\vartheta(X))$ is a [[statistics]] and thus extracts a characteristic from $\mathbb{P}_\vartheta$ based on an estimated parameters $\vartheta(X)$ 
- the power function $\beta_\varphi (\vartheta)$ evaluates $\mathbb{P}_\vartheta\left(H_1 | X\right)$ for a specific parameter $\vartheta$ 
- this is needed because we want to calculate the [[supremum]] of $\beta_\varphi (\vartheta)$ to extract a specific parameter $\vartheta_0$

### statistical test
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ 
- with a [[disjoint]] seperated [[parameter space]] $\Theta_0$ and $\Theta_1 = \Theta \setminus \Theta_0$ 
- every [[statistics]] $\varphi: \mathfrak{X} \to [0,1]$ is called a [[statistical test]] of the **nullhypothesis** $\Theta_0$ against $\Theta_1$
- given an observation $x \in \mathfrak{X}$ the [[statistics]] $\varphi(x) \in [0,1]$ is the properbility of deciding for the alternative $\Theta_1$ thus the **rejection rate** 
$$
\begin{split}
\varphi(X) = \mathbb{P}\left(H_1 | X\right)
\end{split}
$$

#### randomized vs non-random tests
- non-random tests if $\forall x \in \mathfrak{X}: \varphi(x) \in \{0,1\}$ and random otherwise ($\varphi(x) \in [0,1]$)
- for a non-random test $\varphi$ will look like this:

$$
\varphi\left(X_1, ..., X_n\right) = 
\left\{
\begin{matrix}
1 & \Leftrightarrow & \qquad\text{reject } H_0\\
0 & \Leftrightarrow & \qquad\text{dont reject } H_0\\
\end{matrix} \right.
$$
- for a randomized test $\varphi$ will look like this:
$$
\varphi\left(X_1, ..., X_n\right) = 
\left\{
\begin{matrix}
1 & \Leftrightarrow & \qquad\text{reject } H_0\\
\gamma(x) & \Leftrightarrow &  \\
0 & \Leftrightarrow & \qquad\text{dont reject } H_0\\
\end{matrix} \right.
$$


##### effective level of a [[statistical test]] $\varphi$
- the **effective level** of a [[statistical test]] $\varphi$ is defined as follows
$$
\sup_{\vartheta \in \Theta} \mathbb{E}_{\vartheta} [\varphi]
= \sup_{\vartheta \in \Theta} \mathbb{E}_{x \sim \mathbb{P}_\vartheta} [\varphi(x)]
$$
- it is the maximal value the [[expectation]] of the [[statistical test]] $\varphi$ can take with parameters from the nullhypothesis $\Theta_0$
- thus it is the maximal **expected rejection rate** that is possible with parameters from the nullhypothesis $\Theta_0$ (if the obervations are sampled $x \sim \mathbb{P}_\vartheta$ from the [[distribution]] $\mathbb{P}_\vartheta$)

##### test level of a [[statistical test]] $\varphi$
- a [[statistical test]] $\varphi$ is a test of level $\alpha$ if the following is true
$$
\sup_{\vartheta \in \Theta} \mathbb{E}_{\vartheta} [\varphi] \leq \alpha
$$
- the test level can be interpreted as the confidence level or an **upper bound for the expected rejection rate**

##### power function of a [[statistical test]] $\varphi$
- for a [[statistical test]] $\varphi$ the power function $\beta_\varphi: \Theta \to [0,1]$ is defined as follows 
$$
\beta_\varphi (\vartheta) = \mathbb{E}_{\vartheta} [\varphi] = \mathbb{E}_{x \sim \mathbb{P}_\vartheta} [\varphi(x)] = \mathbb{P}_\vartheta\left(H_1 | X\right)
$$

- the power function $\beta_\varphi$ can be interpreted as the **expected rejection rate** for a given parameter [[set]] $\vartheta$ if the obervations are sampled $x \sim \mathbb{P}_\vartheta$ from the [[distribution]] $\mathbb{P}_\vartheta$
- ideally $\beta_\varphi (\vartheta)$ should be close to $0$ for $\vartheta \in \Theta_0$ and close to $1$ for $\vartheta \in \Theta_1$




Tags: mathematics statistics
<!--ID: 1720034252065-->
END
