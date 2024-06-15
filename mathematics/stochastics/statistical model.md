### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on  $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of paraleters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 

### n fold statistical model
- given a [[statistical model]] $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with $n$ samples
- the result is a [[product probability space]] between $n$ times $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with itself


$$
(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta) = ( \mathfrak{X} \times ... \times \mathfrak{X}, \mathcal{L}' \otimes ... \otimes \mathcal{L}', \mathbb{P}'_\theta \otimes ... \otimes \mathbb{P}'_\theta: \theta \in \Theta)
$$

### different kinds of [[statistical model|statistical models]]
- if the [[parameter space]] $\Theta \subseteq \mathbb{R}$ the [[statistical model]] is a **one parameter model**
- if the [[sample space]] $\mathfrak{X}$ is [[discrete probability space|discrete]] the [[statistical model]] is a **discrete model**

# -----------------

![[product probability space#product probability space]]

# anki




START
Basic
[[statistical model]]
- defintion
- how can the [[probability measure]] be interpreted
Back: 
### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on  $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of paraleters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 
Tags: mathematics statistics
<!--ID: 1718476182014-->
END


START
Basic
when to use an n fold [[statistical model]] and when to use a normal [[statistical model]]?
Back: 
the n fold model is needed when there are multiple samples to estimate the parameters from

### n fold statistical model
- given a [[statistical model]] $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with $n$ samples
- the result is a [[product probability space]] between $n$ times $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with itself

$$
(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta) = ( \mathfrak{X} \times ... \times \mathfrak{X}, \mathcal{L}' \otimes ... \otimes \mathcal{L}', \mathbb{P}'_\theta \otimes ... \otimes \mathbb{P}'_\theta: \theta \in \Theta)
$$

### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on  $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of paraleters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 

_____________

### product probability space
- given the [[probability space|probability spaces]] $(\Omega_1, \mathcal{A}_1, \mathbb{P}_1)$ and $(\Omega_2, \mathcal{A}_2, \mathbb{P}_2)$
- we can construct a [[product probability space]] $(\Omega_1 \times \Omega_2, \mathcal{A}_1  \otimes \mathcal{A}_2 , \mathbb{P}_1 \otimes \mathbb{P}_2)$

$$
\mathcal{A}_1  \otimes \mathcal{A}_2 = \{A_1 \times A_2 : A_1 \in \mathcal{A}_1, A_2 \in \mathcal{A}_2\}
$$

$$
\begin{split}
\mathbb{P}_1 \otimes \mathbb{P}_2=\mathbb{P}(A_1 \times A_2) = \mathbb{P}(A_1)\mathbb{P}(A_2)
\end{split}
$$



Tags: mathematics statistics
<!--ID: 1718476182017-->
END


START
Basic
n fold statistical model
- defintion
- releated concept
- when is it used
Back: 

### n fold statistical model
- given a [[statistical model]] $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with $n$ samples
- the result is a [[product probability space]] between $n$ times $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with itself

$$
(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta) = ( \mathfrak{X} \times ... \times \mathfrak{X}, \mathcal{L}' \otimes ... \otimes \mathcal{L}', \mathbb{P}'_\theta \otimes ... \otimes \mathbb{P}'_\theta: \theta \in \Theta)
$$

_____________

### product probability space
- given the [[probability space|probability spaces]] $(\Omega_1, \mathcal{A}_1, \mathbb{P}_1)$ and $(\Omega_2, \mathcal{A}_2, \mathbb{P}_2)$
- we can construct a [[product probability space]] $(\Omega_1 \times \Omega_2, \mathcal{A}_1  \otimes \mathcal{A}_2 , \mathbb{P}_1 \otimes \mathbb{P}_2)$

$$
\mathcal{A}_1  \otimes \mathcal{A}_2 = \{A_1 \times A_2 : A_1 \in \mathcal{A}_1, A_2 \in \mathcal{A}_2\}
$$

$$
\begin{split}
\mathbb{P}_1 \otimes \mathbb{P}_2=\mathbb{P}(A_1 \times A_2) = \mathbb{P}(A_1)\mathbb{P}(A_2)
\end{split}
$$



### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on  $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of paraleters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 
Tags: mathematics statistics
<!--ID: 1718476182020-->
END