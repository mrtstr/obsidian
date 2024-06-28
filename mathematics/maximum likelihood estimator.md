### maximum likelihood estimator
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[likelihood function]] $\varrho: \mathfrak{X} \times \Theta \to (0,\infty)$  
- a [[statistical estimator]] $T: \mathfrak{X} \to \Omega$ for a [[statistics]] with a characteristics $\tau(\vartheta)=\vartheta$ for an observation $x \in \mathfrak{X}$ is called the [[maximum likelihood estimator]] if it's maximizing the [[likelihood function]]
$$
T(x) = arg\max  \varrho(x, \vartheta)
$$
- the [[maximum likelihood]] [[statistical estimator]] can be interpreted the parameter [[set]] out of the [[parameter space]] that explaines the observation best


### calculation of the [[maximum likelihood estimator]]
- given $n$ samples $X_1, ..., X_n \sim f_X(x | \theta)$ with a [[n fold statistical model]] the [[likelihood function]] will look like the following

$$
\varrho(\vartheta) = \prod_{i=1}^n f_X(X_i | \theta)
$$
- to calculate the maximum we need the [[derivative]] but we can use the fact that the paramter that maximizes the [[likelihood function]] will also maximize the [[logarithm]] of the [[likelihood function]]
$$
arg\max_\vartheta  \ln(\varrho(x, \vartheta)) = arg\max_\vartheta  \varrho(x, \vartheta)
$$
- thus we can maximize the following function instead
$$
\ln(\varrho(\vartheta)) = \sum_{i=1}^n \ln(f_X(X_i | \theta))
$$
$$
\frac{d\ln(\varrho(\vartheta))}{d\vartheta} = \sum_{i=1}^n \frac{d\ln\left(f_X(X_i | \theta)\right)}{d\vartheta} = 0
$$

### [[maximum likelihood estimator]] for the [[normal distribution]]
- given an [[n fold statistical model]] for n samples $X_1, ..., X_n \sim \mathcal{N}(\mu, \sigma^2)$ and a [[parameter space]] $\Theta = \mathbb{R} \times (0, \infty)$ 

![[normal distribution#probability density function (PDF)]]

- the following [[statistical estimator]] are the [[maximum likelihood estimator|maximum likelihood estimator]]
$$
\begin{split}
\hat\mu^{ML} &= \frac{1}{n} \sum_{i=1}^n X_i \\
\hat\sigma^{2,ML} &= \frac{1}{n} \sum_{i=1}^n (X_i-\hat\mu^{ML})^2
\end{split}
$$
#### proof
$$
\begin{split}
&\sum_{i = 1}^n\frac{d\ln\left(f_X\left(X_1|\mu, \sigma^2\right)\right)}{d\mu} = 0 \\
\Rightarrow&\sum_{i = 1}^n \frac{d}{d\mu} \ln\left(\exp{\left[-\frac{1}{2}\frac{(X_i-\mu)^2}{\sigma^2}\right]}\right) = 0 \\
\Rightarrow&\sum_{i = 1}^n \frac{d}{d\mu} -\frac{1}{2}\frac{(X_i-\mu)^2}{\sigma^2} = 0 \\
\Rightarrow&\sum_{i = 1}^n \frac{(X_i-\mu)}{\sigma^2}= 0 \\
\Rightarrow&\sum_{i = 1}^nX_i-\mu= 0 \\
\Rightarrow&\left(\sum_{i = 1}^nX_i\right)-n\mu= 0 \\
\Rightarrow&\hat\mu^{ML} = \frac{1}{n} \sum_{i=1}^n X_i
\end{split}
$$


$$
\begin{split}
&\sum_{i = 1}^n\frac{d\ln\left(f_X\left(X_1|\mu, \sigma^2\right)\right)}{d\sigma^2} = 0 \\
\Rightarrow&\sum_{i = 1}^n \frac{d}{d\sigma^2} \ln\left(\frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(X_i-\mu)^2}{\sigma^2}\right]}\right) = 0 \\
\Rightarrow&\sum_{i = 1}^n \frac{d}{d\sigma^2} \ln\left(\frac{1}{\sqrt{2 \pi \sigma^2}}\right) + \frac{d}{d\sigma^2} \ln\left(\exp{\left[-\frac{1}{2}\frac{(X_i-\mu)^2}{\sigma^2}\right]}\right) = 0 \\
\Rightarrow&\sum_{i = 1}^n (-1) \frac{d}{d\sigma^2} \ln\left((2 \pi \sigma^2)^{\frac{1}{2}}\right) + \frac{d}{d\sigma^2} \left({-\frac{1}{2}\frac{(X_i-\mu)^2}{\sigma^2}}\right) = 0 \\
\Rightarrow&\sum_{i = 1}^n (-\frac{1}{2}) \frac{d}{d\sigma^2} \ln\left(2 \pi \sigma^2\right) + \frac{d}{d\sigma^2} \left({-\frac{1}{2}\frac{(X_i-\mu)^2}{\sigma^2}}\right) = 0 \\
\Rightarrow&\sum_{i = 1}^n (-\frac{1}{2}) \frac{2\pi}{2\pi \sigma^2}
+ {\frac{(X_i-\mu)^2}{\left(\sigma^2\right)^2}} = 0 \\
\Rightarrow&\sum_{i = 1}^n \frac{-1}{\sigma^2} + {\frac{(X_i-\mu)^2}{\left(\sigma^2\right)^2}} = 0 \\
\Rightarrow&\sum_{i = 1}^n -1 + {\frac{(X_i-\mu)^2}{\sigma^2}} = 0 \\
\Rightarrow&\sum_{i = 1}^n (X_i-\mu)^2 -\sigma^2n  = 0 \\
\Rightarrow&\hat\sigma^{2,ML} = \frac{1}{n} \sum_{i=1}^n (X_i-\hat\mu^{ML})^2\\
\end{split}
$$


### [[maximum likelihood estimator]] for the [[exponential distribution]]
- given an [[n fold statistical model]] for n samples $X_1, ..., X_n$ with an [[exponential distribution]] and a [[parameter space]] $\Theta = (0, \infty)$ 

![[exponential distribution#probability function]]

$$
\lambda^{ML}_n = \left(\frac{1}{n} \sum_{i=1}^n X_i \right)^{-1}
$$
#### proof
$$
\begin{split}
&\sum_{i = 1}^n\frac{d\ln\left(f_X\left(X_i|\lambda\right)\right)}{d\lambda} = 0 \\
\Rightarrow& \sum_{i = 1}^n\frac{d}{d\lambda} \ln\left(\lambda e^{-\lambda X_i}\right) = 0  \\
\Rightarrow& \sum_{i = 1}^n\frac{d}{d\lambda}\ln(\lambda) + \frac{d}{d\lambda}\ln\left( e^{-\lambda X_i}\right) = 0  \\
\Rightarrow& \sum_{i = 1}^n\frac{d}{d\lambda}\ln(\lambda) - \frac{d}{d\lambda}\lambda X_i = 0  \\
\Rightarrow& \sum_{i = 1}^n\frac{1}{\lambda} -  X_i = 0  \\
\Rightarrow& \frac{n}{\lambda} - \sum_{i = 1}^n X_i = 0  \\
\Rightarrow& \frac{1}{\lambda}   = \frac{1}{n} \sum_{i = 1}^n X_i  \\
\Rightarrow& \lambda^{ML}_n = \left(\frac{1}{n} \sum_{i=1}^n X_i \right)^{-1}  \\
\end{split}
$$


### [[maximum likelihood estimator]] for the [[continous uniform distribution]]

- given a random sample from an [[continous uniform distribution]] $\mathcal{U}(0, b)$ of size $n$
- given a [[statistical model#n fold statistical model|n fold statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with $\mathbb{P}_\vartheta$ being the [[continous uniform distribution]] and $\vartheta = b$
$$
\begin{split}
\mathfrak{X} &= [0, \infty)^n \\
\Theta &= [0, \infty) \\
\mathbb{P}_\vartheta &= \frac{1}{\vartheta^n} \\
f_X &= \frac{1}{\vartheta} \\
\end{split}
$$
- given a [[statistics]] $\tau(\vartheta) = \vartheta$ that describes the paramter itself
- the following is the [[maximum likelihood estimator]]

$$
\hat\vartheta^{ML} = \max\{X_1, ..., X_n\}
$$
#### proof
- in this case we dont need to calculate the log of the [[likelihood function]]
- its easy to see that the [[likelihood function]] $\varrho(x, \vartheta)$ does not have a maximum
$$
\begin{split}
\varrho(x, \vartheta) 
&= f_X\left(X_i|\vartheta\right) \\
&= \frac{1}{\vartheta^n} \\
\end{split}
$$
TODO finish

### [[maximum likelihood estimator]] for the [[binomial distribution]]
- given a one random sample from an [[binomial distribution]] $\mathcal{B}(n, p)$ 

![[binomial distribution#probability function]]

- the following is the [[maximum likelihood estimator]]

$$
\hat p^{ML} = \frac{X}{n}
$$
#### proof
- in this case we dont need to calculate the log of the [[likelihood function]]
- its easy to see that the [[likelihood function]] $\varrho(x, \vartheta)$ does not have a maximum
$$
\begin{split}
\varrho(X, \vartheta) 
&= f_X\left(X_i|n, p\right) \\
&= {n \choose X} p^{X} (1-p)^{n-X} \\
\end{split}
$$

$$
\begin{split}
\ln\varrho(X, \vartheta) 
&= \ln{n \choose X} + \ln\left( p^{X}\right) + \ln \left((1-p)^{n-X}\right) \\
&= \ln{n \choose X} + X \ln\left( p\right) + (n-X) \ln \left(1-p\right) \\
\end{split}
$$

$$
\begin{split}
\frac{d}{dp}\ln\varrho(X, \vartheta) 
&=  X \frac{d}{dp}\ln\left( p\right) + (n-X) \frac{d}{dp}\ln \left(1-p\right) \\
&=   \frac{X}{p} - \frac{n-X}{1-p} \\
&   \frac{X}{p} = \frac{n-X}{1-p} \\
&  (1-p) X = p(n-X) \\
&  X-pX  = pn-pX \\
&  X  = pn \\
&  p  = \frac{X}{n} \\

\end{split}
$$

# ------------------

![[likelihood function#likelihood function]]

![[statistical estimator#statistical estimator]]


![[n fold statistical model#n fold statistical model]]

# anki


START
Basic
[[maximum likelihood estimator]]
- definition
- interpretation

[[likelihood function]]
- definition
- interpretation

Back: 
### maximum likelihood estimator
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[likelihood function]] $\varrho: \mathfrak{X} \times \Theta \to (0,\infty)$  
- a [[statistical estimator]] $T: \mathfrak{X} \to \Omega$ for a [[statistics]] with a characteristics $\tau(\vartheta)=\vartheta$ for an observation $x \in \mathfrak{X}$ is called the [[maximum likelihood estimator]] if it's maximizing the [[likelihood function]]
$$
T(x) = arg\max  \varrho(x, \vartheta)
$$
- the [[maximum likelihood]] [[statistical estimator]] can be interpreted the parameter [[set]] out of the [[parameter space]] that explaines the observation best

### likelihood function
- the [[likelihood function]] is the [[probability density function (PDF)|density]] of the observed data as a function of the parameter $\vartheta \in \Theta$
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ where the [[distribution]] $\mathbb{P}_\vartheta: \mathcal{L} \to [0,1]$ has a [[probability density function (PDF)]] $\varrho: \mathfrak{X} \times \Theta \to (0,\infty)$  
- for a given observation $x \in \mathfrak{X}$ the function $\varrho(x, \: \cdot \:): \Theta \to (0, \infty)$ is called the [[likelihood function]]
- the [[likelihood function]] can be interpreted as a measurment for how well a parameter [[set]] $\vartheta \in \Theta$ discribes a given observation $x \in \mathfrak{X}$

#### the [[likelihood function]] is not a [[probability density function (PDF)]]
- note that the density $\varrho: \mathfrak{X} \times \Theta \to (0,\infty)$ is normalzed when integrated over all possible observations
$$
\int_\mathfrak{X} \varrho(x, \vartheta) dx = 1
$$
- but the [[likelihood function]] is a function of the parameters and because $\int_\Theta \varrho(x, \vartheta) d\vartheta$ does not have to be $1$ the [[likelihood function]] is not a [[probability density function (PDF)]]

______________________
### distribution
- given a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$ and a [[random variable]] $X: \Omega \to \mathbb{R}$ (which is a [[measurable function]] $X: (\Omega, \mathcal{A}) \to \left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$)
- $X$ is inducing the [[probability measure]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ from the [[borel sigma algebra]] $\mathcal{B}(\mathbb{R})$ it the interval $[0,1]$ (assigning a probability to each borel set $\subset \mathbb{R}$)
- $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ is called the [[distribution]] of $X$ and exists for every [[random variable]] 
$$
\begin{split}
\mathcal{P}_X(C) 
&= \mathbb{P}\left(X^{-1}(C \subseteq \mathbb{R})\right) \\
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) \in C\right\}\right) \\
\end{split}
$$

### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of parameters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 

### probability density function
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ in a [[continuous probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ with the [[distribution]] $\mathcal{P}_X:\mathcal{B}(\mathbb{R}) \to [0,1]$ and its [[cumulative distribution function (CDF)]] $F_X: \mathbb{R} \to [0,1]$
- the [[probability mass function (PMF)]] would be undefined but the [[probability density function (PDF)]] $f_X: \mathbb{R} \to [0,1]$ can be derived from the [[cumulative distribution function (CDF)]]

$$
f_X(x) = \frac{dF_X(x)}{dx}
$$

Tags: mathematics statistics
<!--ID: 1719251749341-->
END

START
Basic
- given $n$ samples $X_1, ..., X_n \sim f_X(x | \theta)$ 
- how to calculate the [[maximum likelihood estimator]] in general?


Back: 
### calculation of the [[maximum likelihood estimator]]
- given $n$ samples $X_1, ..., X_n \sim f_X(x | \theta)$ with a [[n fold statistical model]] the [[likelihood function]] will look like the following

$$
\varrho(\vartheta) = \prod_{i=1}^n f_X(X_i | \theta)
$$
- to calculate the maximum we need the [[derivative]] but we can use the fact that the paramter that maximizes the [[likelihood function]] will also maximize the [[logarithm]] of the [[likelihood function]]
$$
arg\max_\vartheta  \ln(\varrho(x, \vartheta)) = arg\max_\vartheta  \varrho(x, \vartheta)
$$
- thus we can maximize the following function instead
$$
\ln(\varrho(\vartheta)) = \sum_{i=1}^n \ln(f_X(X_i | \theta))
$$
$$
\frac{d\ln(\varrho(\vartheta))}{d\vartheta} = \sum_{i=1}^n \frac{d\ln\left(f_X(X_i | \theta)\right)}{d\vartheta} = 0
$$


### maximum likelihood estimator
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[likelihood function]] $\varrho: \mathfrak{X} \times \Theta \to (0,\infty)$  
- a [[statistical estimator]] $T: \mathfrak{X} \to \Omega$ for a [[statistics]] with a characteristics $\tau(\vartheta)=\vartheta$ for an observation $x \in \mathfrak{X}$ is called the [[maximum likelihood estimator]] if it's maximizing the [[likelihood function]]
$$
T(x) = arg\max  \varrho(x, \vartheta)
$$
- the [[maximum likelihood]] [[statistical estimator]] can be interpreted the parameter [[set]] out of the [[parameter space]] that explaines the observation best

______________________

### likelihood function
- the [[likelihood function]] is the [[probability density function (PDF)|density]] of the observed data as a function of the parameter $\vartheta \in \Theta$
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ where the [[distribution]] $\mathbb{P}_\vartheta: \mathcal{L} \to [0,1]$ has a [[probability density function (PDF)]] $\varrho: \mathfrak{X} \times \Theta \to (0,\infty)$  
- for a given observation $x \in \mathfrak{X}$ the function $\varrho(x, \: \cdot \:): \Theta \to (0, \infty)$ is called the [[likelihood function]]
- the [[likelihood function]] can be interpreted as a measurment for how well a parameter [[set]] $\vartheta \in \Theta$ discribes a given observation $x \in \mathfrak{X}$

#### the [[likelihood function]] is not a [[probability density function (PDF)]]
- note that the density $\varrho: \mathfrak{X} \times \Theta \to (0,\infty)$ is normalzed when integrated over all possible observations
$$
\int_\mathfrak{X} \varrho(x, \vartheta) dx = 1
$$
- but the [[likelihood function]] is a function of the parameters and because $\int_\Theta \varrho(x, \vartheta) d\vartheta$ does not have to be $1$ the [[likelihood function]] is not a [[probability density function (PDF)]]


### distribution
- given a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$ and a [[random variable]] $X: \Omega \to \mathbb{R}$ (which is a [[measurable function]] $X: (\Omega, \mathcal{A}) \to \left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$)
- $X$ is inducing the [[probability measure]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ from the [[borel sigma algebra]] $\mathcal{B}(\mathbb{R})$ it the interval $[0,1]$ (assigning a probability to each borel set $\subset \mathbb{R}$)
- $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ is called the [[distribution]] of $X$ and exists for every [[random variable]] 
$$
\begin{split}
\mathcal{P}_X(C) 
&= \mathbb{P}\left(X^{-1}(C \subseteq \mathbb{R})\right) \\
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) \in C\right\}\right) \\
\end{split}
$$

### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of parameters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 

### probability density function
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ in a [[continuous probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ with the [[distribution]] $\mathcal{P}_X:\mathcal{B}(\mathbb{R}) \to [0,1]$ and its [[cumulative distribution function (CDF)]] $F_X: \mathbb{R} \to [0,1]$
- the [[probability mass function (PMF)]] would be undefined but the [[probability density function (PDF)]] $f_X: \mathbb{R} \to [0,1]$ can be derived from the [[cumulative distribution function (CDF)]]

$$
f_X(x) = \frac{dF_X(x)}{dx}
$$

Tags: mathematics statistics
<!--ID: 1719332121172-->
END



START
Basic
### [[maximum likelihood estimator]] for the [[normal distribution]]
- given an [[n fold statistical model]] for n samples $X_1, ..., X_n \sim \mathcal{N}(\mu, \sigma^2)$ and a [[parameter space]] $\Theta = \mathbb{R} \times (0, \infty)$ 
- what the is the [[maximum likelihood estimator]] for $\mu$? (with proof)

Back: 

$$
f_X\left(x|\mu, \sigma^2\right) = \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(x-\mu)^2}{\sigma^2}\right]}
$$

- the following [[statistical estimator]] are the [[maximum likelihood estimator|maximum likelihood estimator]]
$$
\begin{split}
\hat\mu^{ML} &= \frac{1}{n} \sum_{i=1}^n X_i \\
\end{split}
$$
#### proof
$$
\begin{split}
&\sum_{i = 1}^n\frac{d\ln\left(f_X\left(X_1|\mu, \sigma^2\right)\right)}{d\mu} = 0 \\
\Rightarrow&\sum_{i = 1}^n \frac{d}{d\mu} \ln\left(\exp{\left[-\frac{1}{2}\frac{(X_i-\mu)^2}{\sigma^2}\right]}\right) = 0 \\
\Rightarrow&\sum_{i = 1}^n \frac{d}{d\mu} -\frac{1}{2}\frac{(X_i-\mu)^2}{\sigma^2} = 0 \\
\Rightarrow&\sum_{i = 1}^n \frac{(X_i-\mu)}{\sigma^2}= 0 \\
\Rightarrow&\sum_{i = 1}^nX_i-\mu= 0 \\
\Rightarrow&\left(\sum_{i = 1}^nX_i\right)-n\mu= 0 \\
\Rightarrow&\hat\mu^{ML} = \frac{1}{n} \sum_{i=1}^n X_i
\end{split}
$$




______________________

### calculation of the [[maximum likelihood estimator]]
- given $n$ samples $X_1, ..., X_n \sim f_X(x | \theta)$ with a [[n fold statistical model]] the [[likelihood function]] will look like the following

$$
\varrho(\vartheta) = \prod_{i=1}^n f_X(X_i | \theta)
$$
- to calculate the maximum we need the [[derivative]] but we can use the fact that the paramter that maximizes the [[likelihood function]] will also maximize the [[logarithm]] of the [[likelihood function]]
$$
arg\max_\vartheta  \ln(\varrho(x, \vartheta)) = arg\max_\vartheta  \varrho(x, \vartheta)
$$
- thus we can maximize the following function instead
$$
\ln(\varrho(\vartheta)) = \sum_{i=1}^n \ln(f_X(X_i | \theta))
$$
$$
\frac{d\ln(\varrho(\vartheta))}{d\vartheta} = \sum_{i=1}^n \frac{d\ln\left(f_X(X_i | \theta)\right)}{d\vartheta} = 0
$$


### maximum likelihood estimator
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[likelihood function]] $\varrho: \mathfrak{X} \times \Theta \to (0,\infty)$  
- a [[statistical estimator]] $T: \mathfrak{X} \to \Omega$ for a [[statistics]] with a characteristics $\tau(\vartheta)=\vartheta$ for an observation $x \in \mathfrak{X}$ is called the [[maximum likelihood estimator]] if it's maximizing the [[likelihood function]]
$$
T(x) = arg\max  \varrho(x, \vartheta)
$$
- the [[maximum likelihood]] [[statistical estimator]] can be interpreted the parameter [[set]] out of the [[parameter space]] that explaines the observation best


### likelihood function
- the [[likelihood function]] is the [[probability density function (PDF)|density]] of the observed data as a function of the parameter $\vartheta \in \Theta$
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ where the [[distribution]] $\mathbb{P}_\vartheta: \mathcal{L} \to [0,1]$ has a [[probability density function (PDF)]] $\varrho: \mathfrak{X} \times \Theta \to (0,\infty)$  
- for a given observation $x \in \mathfrak{X}$ the function $\varrho(x, \: \cdot \:): \Theta \to (0, \infty)$ is called the [[likelihood function]]
- the [[likelihood function]] can be interpreted as a measurment for how well a parameter [[set]] $\vartheta \in \Theta$ discribes a given observation $x \in \mathfrak{X}$

#### the [[likelihood function]] is not a [[probability density function (PDF)]]
- note that the density $\varrho: \mathfrak{X} \times \Theta \to (0,\infty)$ is normalzed when integrated over all possible observations
$$
\int_\mathfrak{X} \varrho(x, \vartheta) dx = 1
$$
- but the [[likelihood function]] is a function of the parameters and because $\int_\Theta \varrho(x, \vartheta) d\vartheta$ does not have to be $1$ the [[likelihood function]] is not a [[probability density function (PDF)]]


### distribution
- given a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$ and a [[random variable]] $X: \Omega \to \mathbb{R}$ (which is a [[measurable function]] $X: (\Omega, \mathcal{A}) \to \left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$)
- $X$ is inducing the [[probability measure]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ from the [[borel sigma algebra]] $\mathcal{B}(\mathbb{R})$ it the interval $[0,1]$ (assigning a probability to each borel set $\subset \mathbb{R}$)
- $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ is called the [[distribution]] of $X$ and exists for every [[random variable]] 
$$
\begin{split}
\mathcal{P}_X(C) 
&= \mathbb{P}\left(X^{-1}(C \subseteq \mathbb{R})\right) \\
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) \in C\right\}\right) \\
\end{split}
$$

### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of parameters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 

### probability density function
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ in a [[continuous probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ with the [[distribution]] $\mathcal{P}_X:\mathcal{B}(\mathbb{R}) \to [0,1]$ and its [[cumulative distribution function (CDF)]] $F_X: \mathbb{R} \to [0,1]$
- the [[probability mass function (PMF)]] would be undefined but the [[probability density function (PDF)]] $f_X: \mathbb{R} \to [0,1]$ can be derived from the [[cumulative distribution function (CDF)]]

$$
f_X(x) = \frac{dF_X(x)}{dx}
$$

Tags: mathematics statistics
<!--ID: 1719332121176-->
END




START
Basic
### [[maximum likelihood estimator]] for the [[normal distribution]]
- given an [[n fold statistical model]] for n samples $X_1, ..., X_n \sim \mathcal{N}(\mu, \sigma^2)$ and a [[parameter space]] $\Theta = \mathbb{R} \times (0, \infty)$ 
- what is the [[maximum likelihood estimator]] for $\sigma^2$? (with proof)

Back: 

$$
f_X\left(x|\mu, \sigma^2\right) = \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(x-\mu)^2}{\sigma^2}\right]}
$$

- the following [[statistical estimator]] are the [[maximum likelihood estimator|maximum likelihood estimator]]
$$
\begin{split}
\hat\mu^{ML} &= \frac{1}{n} \sum_{i=1}^n X_i \\
\hat\sigma^{2,ML} &= \frac{1}{n} \sum_{i=1}^n (X_i-\hat\mu^{ML})^2
\end{split}
$$
#### proof



$$
\begin{split}
&\sum_{i = 1}^n\frac{d\ln\left(f_X\left(X_1|\mu, \sigma^2\right)\right)}{d\sigma^2} = 0 \\
\Rightarrow&\sum_{i = 1}^n \frac{d}{d\sigma^2} \ln\left(\frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(X_i-\mu)^2}{\sigma^2}\right]}\right) = 0 \\
\Rightarrow&\sum_{i = 1}^n \frac{d}{d\sigma^2} \ln\left(\frac{1}{\sqrt{2 \pi \sigma^2}}\right) + \frac{d}{d\sigma^2} \ln\left(\exp{\left[-\frac{1}{2}\frac{(X_i-\mu)^2}{\sigma^2}\right]}\right) = 0 \\
\Rightarrow&\sum_{i = 1}^n (-1) \frac{d}{d\sigma^2} \ln\left((2 \pi \sigma^2)^{\frac{1}{2}}\right) + \frac{d}{d\sigma^2} \left({-\frac{1}{2}\frac{(X_i-\mu)^2}{\sigma^2}}\right) = 0 \\
\Rightarrow&\sum_{i = 1}^n (-\frac{1}{2}) \frac{d}{d\sigma^2} \ln\left(2 \pi \sigma^2\right) + \frac{d}{d\sigma^2} \left({-\frac{1}{2}\frac{(X_i-\mu)^2}{\sigma^2}}\right) = 0 \\
\Rightarrow&\sum_{i = 1}^n (-\frac{1}{2}) \frac{2\pi}{2\pi \sigma^2}
+ {\frac{(X_i-\mu)^2}{\left(\sigma^2\right)^2}} = 0 \\
\Rightarrow&\sum_{i = 1}^n \frac{-1}{\sigma^2} + {\frac{(X_i-\mu)^2}{\left(\sigma^2\right)^2}} = 0 \\
\Rightarrow&\sum_{i = 1}^n -1 + {\frac{(X_i-\mu)^2}{\sigma^2}} = 0 \\
\Rightarrow&\sum_{i = 1}^n (X_i-\mu)^2 -\sigma^2n  = 0 \\
\Rightarrow&\hat\sigma^{2,ML} = \frac{1}{n} \sum_{i=1}^n (X_i-\hat\mu^{ML})^2\\
\end{split}
$$



not needed:

$$
\begin{split}
&\sum_{i = 1}^n\frac{d\ln\left(f_X\left(X_1|\mu, \sigma^2\right)\right)}{d\mu} = 0 \\
\Rightarrow&\sum_{i = 1}^n \frac{d}{d\mu} \ln\left(\exp{\left[-\frac{1}{2}\frac{(X_i-\mu)^2}{\sigma^2}\right]}\right) = 0 \\
\Rightarrow&\sum_{i = 1}^n \frac{d}{d\mu} -\frac{1}{2}\frac{(X_i-\mu)^2}{\sigma^2} = 0 \\
\Rightarrow&\sum_{i = 1}^n \frac{(X_i-\mu)}{\sigma^2}= 0 \\
\Rightarrow&\sum_{i = 1}^nX_i-\mu= 0 \\
\Rightarrow&\left(\sum_{i = 1}^nX_i\right)-n\mu= 0 \\
\Rightarrow&\hat\mu^{ML} = \frac{1}{n} \sum_{i=1}^n X_i
\end{split}
$$

______________________

### calculation of the [[maximum likelihood estimator]]
- given $n$ samples $X_1, ..., X_n \sim f_X(x | \theta)$ with a [[n fold statistical model]] the [[likelihood function]] will look like the following

$$
\varrho(\vartheta) = \prod_{i=1}^n f_X(X_i | \theta)
$$
- to calculate the maximum we need the [[derivative]] but we can use the fact that the paramter that maximizes the [[likelihood function]] will also maximize the [[logarithm]] of the [[likelihood function]]
$$
arg\max_\vartheta  \ln(\varrho(x, \vartheta)) = arg\max_\vartheta  \varrho(x, \vartheta)
$$
- thus we can maximize the following function instead
$$
\ln(\varrho(\vartheta)) = \sum_{i=1}^n \ln(f_X(X_i | \theta))
$$
$$
\frac{d\ln(\varrho(\vartheta))}{d\vartheta} = \sum_{i=1}^n \frac{d\ln\left(f_X(X_i | \theta)\right)}{d\vartheta} = 0
$$


### maximum likelihood estimator
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[likelihood function]] $\varrho: \mathfrak{X} \times \Theta \to (0,\infty)$  
- a [[statistical estimator]] $T: \mathfrak{X} \to \Omega$ for a [[statistics]] with a characteristics $\tau(\vartheta)=\vartheta$ for an observation $x \in \mathfrak{X}$ is called the [[maximum likelihood estimator]] if it's maximizing the [[likelihood function]]
$$
T(x) = arg\max  \varrho(x, \vartheta)
$$
- the [[maximum likelihood]] [[statistical estimator]] can be interpreted the parameter [[set]] out of the [[parameter space]] that explaines the observation best


### likelihood function
- the [[likelihood function]] is the [[probability density function (PDF)|density]] of the observed data as a function of the parameter $\vartheta \in \Theta$
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ where the [[distribution]] $\mathbb{P}_\vartheta: \mathcal{L} \to [0,1]$ has a [[probability density function (PDF)]] $\varrho: \mathfrak{X} \times \Theta \to (0,\infty)$  
- for a given observation $x \in \mathfrak{X}$ the function $\varrho(x, \: \cdot \:): \Theta \to (0, \infty)$ is called the [[likelihood function]]
- the [[likelihood function]] can be interpreted as a measurment for how well a parameter [[set]] $\vartheta \in \Theta$ discribes a given observation $x \in \mathfrak{X}$

#### the [[likelihood function]] is not a [[probability density function (PDF)]]
- note that the density $\varrho: \mathfrak{X} \times \Theta \to (0,\infty)$ is normalzed when integrated over all possible observations
$$
\int_\mathfrak{X} \varrho(x, \vartheta) dx = 1
$$
- but the [[likelihood function]] is a function of the parameters and because $\int_\Theta \varrho(x, \vartheta) d\vartheta$ does not have to be $1$ the [[likelihood function]] is not a [[probability density function (PDF)]]


### distribution
- given a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$ and a [[random variable]] $X: \Omega \to \mathbb{R}$ (which is a [[measurable function]] $X: (\Omega, \mathcal{A}) \to \left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$)
- $X$ is inducing the [[probability measure]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ from the [[borel sigma algebra]] $\mathcal{B}(\mathbb{R})$ it the interval $[0,1]$ (assigning a probability to each borel set $\subset \mathbb{R}$)
- $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ is called the [[distribution]] of $X$ and exists for every [[random variable]] 
$$
\begin{split}
\mathcal{P}_X(C) 
&= \mathbb{P}\left(X^{-1}(C \subseteq \mathbb{R})\right) \\
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) \in C\right\}\right) \\
\end{split}
$$

### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of parameters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 

### probability density function
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ in a [[continuous probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ with the [[distribution]] $\mathcal{P}_X:\mathcal{B}(\mathbb{R}) \to [0,1]$ and its [[cumulative distribution function (CDF)]] $F_X: \mathbb{R} \to [0,1]$
- the [[probability mass function (PMF)]] would be undefined but the [[probability density function (PDF)]] $f_X: \mathbb{R} \to [0,1]$ can be derived from the [[cumulative distribution function (CDF)]]

$$
f_X(x) = \frac{dF_X(x)}{dx}
$$

Tags: mathematics statistics
<!--ID: 1719332121179-->
END



START
Basic
### [[maximum likelihood estimator]] for the [[exponential distribution]]
- given an [[n fold statistical model]] for n samples $X_1, ..., X_n$ with an [[exponential distribution]] and a [[parameter space]] $\Theta = (0, \infty)$ 
- what is the [[maximum likelihood estimator]] wir $\lambda$? (with proof)

Back: 


$$
f_X(x) = \lambda e^{-\lambda x}
$$

$$
\lambda^{ML}_n = \left(\frac{1}{n} \sum_{i=1}^n X_i \right)^{-1}
$$
#### proof
$$
\begin{split}
&\sum_{i = 1}^n\frac{d\ln\left(f_X\left(X_i|\lambda\right)\right)}{d\lambda} = 0 \\
\Rightarrow& \sum_{i = 1}^n\frac{d}{d\lambda} \ln\left(\lambda e^{-\lambda X_i}\right) = 0  \\
\Rightarrow& \sum_{i = 1}^n\frac{d}{d\lambda}\ln(\lambda) + \frac{d}{d\lambda}\ln\left( e^{-\lambda X_i}\right) = 0  \\
\Rightarrow& \sum_{i = 1}^n\frac{d}{d\lambda}\ln(\lambda) - \frac{d}{d\lambda}\lambda X_i = 0  \\
\Rightarrow& \sum_{i = 1}^n\frac{1}{\lambda} -  X_i = 0  \\
\Rightarrow& \frac{n}{\lambda} - \sum_{i = 1}^n X_i = 0  \\
\Rightarrow& \frac{1}{\lambda}   = \frac{1}{n} \sum_{i = 1}^n X_i  \\
\Rightarrow& \lambda^{ML}_n = \left(\frac{1}{n} \sum_{i=1}^n X_i \right)^{-1}  \\
\end{split}
$$

______________________

### calculation of the [[maximum likelihood estimator]]
- given $n$ samples $X_1, ..., X_n \sim f_X(x | \theta)$ with a [[n fold statistical model]] the [[likelihood function]] will look like the following

$$
\varrho(\vartheta) = \prod_{i=1}^n f_X(X_i | \theta)
$$
- to calculate the maximum we need the [[derivative]] but we can use the fact that the paramter that maximizes the [[likelihood function]] will also maximize the [[logarithm]] of the [[likelihood function]]
$$
arg\max_\vartheta  \ln(\varrho(x, \vartheta)) = arg\max_\vartheta  \varrho(x, \vartheta)
$$
- thus we can maximize the following function instead
$$
\ln(\varrho(\vartheta)) = \sum_{i=1}^n \ln(f_X(X_i | \theta))
$$
$$
\frac{d\ln(\varrho(\vartheta))}{d\vartheta} = \sum_{i=1}^n \frac{d\ln\left(f_X(X_i | \theta)\right)}{d\vartheta} = 0
$$


### maximum likelihood estimator
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[likelihood function]] $\varrho: \mathfrak{X} \times \Theta \to (0,\infty)$  
- a [[statistical estimator]] $T: \mathfrak{X} \to \Omega$ for a [[statistics]] with a characteristics $\tau(\vartheta)=\vartheta$ for an observation $x \in \mathfrak{X}$ is called the [[maximum likelihood estimator]] if it's maximizing the [[likelihood function]]
$$
T(x) = arg\max  \varrho(x, \vartheta)
$$
- the [[maximum likelihood]] [[statistical estimator]] can be interpreted the parameter [[set]] out of the [[parameter space]] that explaines the observation best


### likelihood function
- the [[likelihood function]] is the [[probability density function (PDF)|density]] of the observed data as a function of the parameter $\vartheta \in \Theta$
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ where the [[distribution]] $\mathbb{P}_\vartheta: \mathcal{L} \to [0,1]$ has a [[probability density function (PDF)]] $\varrho: \mathfrak{X} \times \Theta \to (0,\infty)$  
- for a given observation $x \in \mathfrak{X}$ the function $\varrho(x, \: \cdot \:): \Theta \to (0, \infty)$ is called the [[likelihood function]]
- the [[likelihood function]] can be interpreted as a measurment for how well a parameter [[set]] $\vartheta \in \Theta$ discribes a given observation $x \in \mathfrak{X}$

#### the [[likelihood function]] is not a [[probability density function (PDF)]]
- note that the density $\varrho: \mathfrak{X} \times \Theta \to (0,\infty)$ is normalzed when integrated over all possible observations
$$
\int_\mathfrak{X} \varrho(x, \vartheta) dx = 1
$$
- but the [[likelihood function]] is a function of the parameters and because $\int_\Theta \varrho(x, \vartheta) d\vartheta$ does not have to be $1$ the [[likelihood function]] is not a [[probability density function (PDF)]]


### distribution
- given a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$ and a [[random variable]] $X: \Omega \to \mathbb{R}$ (which is a [[measurable function]] $X: (\Omega, \mathcal{A}) \to \left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$)
- $X$ is inducing the [[probability measure]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ from the [[borel sigma algebra]] $\mathcal{B}(\mathbb{R})$ it the interval $[0,1]$ (assigning a probability to each borel set $\subset \mathbb{R}$)
- $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ is called the [[distribution]] of $X$ and exists for every [[random variable]] 
$$
\begin{split}
\mathcal{P}_X(C) 
&= \mathbb{P}\left(X^{-1}(C \subseteq \mathbb{R})\right) \\
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) \in C\right\}\right) \\
\end{split}
$$

### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of parameters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 

### probability density function
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ in a [[continuous probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ with the [[distribution]] $\mathcal{P}_X:\mathcal{B}(\mathbb{R}) \to [0,1]$ and its [[cumulative distribution function (CDF)]] $F_X: \mathbb{R} \to [0,1]$
- the [[probability mass function (PMF)]] would be undefined but the [[probability density function (PDF)]] $f_X: \mathbb{R} \to [0,1]$ can be derived from the [[cumulative distribution function (CDF)]]

$$
f_X(x) = \frac{dF_X(x)}{dx}
$$

Tags: mathematics statistics
<!--ID: 1719338370391-->
END



START
Basic
### [[maximum likelihood estimator]] for the [[binomial distribution]]
- given a one random sample from an [[binomial distribution]] $\mathcal{B}(n, p)$ 
- what is the [[maximum likelihood estimator]] for $p$? (with proof)
Back: 

- the following is the [[maximum likelihood estimator]]

$$
\hat p^{ML} = \frac{X}{n}
$$
#### proof
- in this case we dont need to calculate the log of the [[likelihood function]]
- its easy to see that the [[likelihood function]] $\varrho(x, \vartheta)$ does not have a maximum
$$
\begin{split}
\varrho(X, \vartheta) 
&= f_X\left(X_i|n, p\right) \\
&= {n \choose X} p^{X} (1-p)^{n-X} \\
\end{split}
$$

$$
\begin{split}
\ln\varrho(X, \vartheta) 
&= \ln{n \choose X} + \ln\left( p^{X}\right) + \ln \left((1-p)^{n-X}\right) \\
&= \ln{n \choose X} + X \ln\left( p\right) + (n-X) \ln \left(1-p\right) \\
\end{split}
$$

$$
\begin{split}
\frac{d}{dp}\ln\varrho(X, \vartheta) 
&=  X \frac{d}{dp}\ln\left( p\right) + (n-X) \frac{d}{dp}\ln \left(1-p\right) \\
&=   \frac{X}{p} - \frac{n-X}{1-p} \\
&   \frac{X}{p} = \frac{n-X}{1-p} \\
&  (1-p) X = p(n-X) \\
&  X-pX  = pn-pX \\
&  X  = pn \\
&  p  = \frac{X}{n} \\

\end{split}
$$

______________________

### calculation of the [[maximum likelihood estimator]]
- given $n$ samples $X_1, ..., X_n \sim f_X(x | \theta)$ with a [[n fold statistical model]] the [[likelihood function]] will look like the following

$$
\varrho(\vartheta) = \prod_{i=1}^n f_X(X_i | \theta)
$$
- to calculate the maximum we need the [[derivative]] but we can use the fact that the paramter that maximizes the [[likelihood function]] will also maximize the [[logarithm]] of the [[likelihood function]]
$$
arg\max_\vartheta  \ln(\varrho(x, \vartheta)) = arg\max_\vartheta  \varrho(x, \vartheta)
$$
- thus we can maximize the following function instead
$$
\ln(\varrho(\vartheta)) = \sum_{i=1}^n \ln(f_X(X_i | \theta))
$$
$$
\frac{d\ln(\varrho(\vartheta))}{d\vartheta} = \sum_{i=1}^n \frac{d\ln\left(f_X(X_i | \theta)\right)}{d\vartheta} = 0
$$


### maximum likelihood estimator
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[likelihood function]] $\varrho: \mathfrak{X} \times \Theta \to (0,\infty)$  
- a [[statistical estimator]] $T: \mathfrak{X} \to \Omega$ for a [[statistics]] with a characteristics $\tau(\vartheta)=\vartheta$ for an observation $x \in \mathfrak{X}$ is called the [[maximum likelihood estimator]] if it's maximizing the [[likelihood function]]
$$
T(x) = arg\max  \varrho(x, \vartheta)
$$
- the [[maximum likelihood]] [[statistical estimator]] can be interpreted the parameter [[set]] out of the [[parameter space]] that explaines the observation best


### likelihood function
- the [[likelihood function]] is the [[probability density function (PDF)|density]] of the observed data as a function of the parameter $\vartheta \in \Theta$
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ where the [[distribution]] $\mathbb{P}_\vartheta: \mathcal{L} \to [0,1]$ has a [[probability density function (PDF)]] $\varrho: \mathfrak{X} \times \Theta \to (0,\infty)$  
- for a given observation $x \in \mathfrak{X}$ the function $\varrho(x, \: \cdot \:): \Theta \to (0, \infty)$ is called the [[likelihood function]]
- the [[likelihood function]] can be interpreted as a measurment for how well a parameter [[set]] $\vartheta \in \Theta$ discribes a given observation $x \in \mathfrak{X}$

#### the [[likelihood function]] is not a [[probability density function (PDF)]]
- note that the density $\varrho: \mathfrak{X} \times \Theta \to (0,\infty)$ is normalzed when integrated over all possible observations
$$
\int_\mathfrak{X} \varrho(x, \vartheta) dx = 1
$$
- but the [[likelihood function]] is a function of the parameters and because $\int_\Theta \varrho(x, \vartheta) d\vartheta$ does not have to be $1$ the [[likelihood function]] is not a [[probability density function (PDF)]]


### distribution
- given a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$ and a [[random variable]] $X: \Omega \to \mathbb{R}$ (which is a [[measurable function]] $X: (\Omega, \mathcal{A}) \to \left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$)
- $X$ is inducing the [[probability measure]] $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ from the [[borel sigma algebra]] $\mathcal{B}(\mathbb{R})$ it the interval $[0,1]$ (assigning a probability to each borel set $\subset \mathbb{R}$)
- $\mathcal{P}_X: \mathcal{B}(\mathbb{R}) \to [0,1]$ is called the [[distribution]] of $X$ and exists for every [[random variable]] 
$$
\begin{split}
\mathcal{P}_X(C) 
&= \mathbb{P}\left(X^{-1}(C \subseteq \mathbb{R})\right) \\
&= \mathbb{P}\left(\left\{\omega \in \Omega : X(\omega) \in C\right\}\right) \\
\end{split}
$$

### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of parameters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 

### probability density function
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ in a [[continuous probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ with the [[distribution]] $\mathcal{P}_X:\mathcal{B}(\mathbb{R}) \to [0,1]$ and its [[cumulative distribution function (CDF)]] $F_X: \mathbb{R} \to [0,1]$
- the [[probability mass function (PMF)]] would be undefined but the [[probability density function (PDF)]] $f_X: \mathbb{R} \to [0,1]$ can be derived from the [[cumulative distribution function (CDF)]]

$$
f_X(x) = \frac{dF_X(x)}{dx}
$$

Tags: mathematics statistics
<!--ID: 1719338370398-->
END