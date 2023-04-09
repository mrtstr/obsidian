- [[moments]] describe the properties of the [[distribution]] of [[random variable|random variables]]

# raw moments
$$
\mathbb{E}\left[X^k\right] = \int\limits_{-\infty}^\infty x^k f_X(x)dx = \mu_k[X]
$$
- contrains information about
	- $k\geq 1$: the overall magnitude of a [[random variable]]
	- $k\geq 2$: the spread ([[variance]]) of the [[distribution]] $f_X(x)$ 
	- $k\geq 3$: the [[skewness]] of the [[distribution]] $f_X(x)$ 
	- $k\geq 4$: the [[kurtosis]] of the [[distribution]] $f_X(x)$ 
	-  ...
- $\mu_1[X] = \mathbb{E}\left[X\right]$
## some properties
- $\mu_0[X]=1$
- $\mu_1[X]=\mathbb{E}\left[X\right]$ 
	- is called the [[expectation]] or mean of a [[random variable]] 
	- contains the isolated information about the overall magnitude of $X$
- $\mu_2[X]=\mathbb{E}\left[X^2\right]$ 
	- contains information about the overall magnitude and spread of $f_X(x)$
	- to isolate the information about the spread → central moment $\mu'_2=\mathbb{VAR}\left[X\right]$
- If $\mathbb{E}\left[X\right]=0$ and $f_X(x)$ is [[symmetric distribution|symmetric around its mean]] → $\mathbb{E}\left[X^{2k+1}\right] = 0 \: \forall k \in \mathbb{N}_0$ 
- $\mu_k[cX]=c^k\mu_k[X]$

# central moments
$$
\mathbb{E}\left[(X- \mu)^k\right] = \int\limits_{-\infty}^\infty (X- \mu)^k f_X(x)dx = \mu'_k[X]
$$
- shifted version of the raw moment
- does not contain information about the magnitude ($\mu_1[X]$) any more
- contrains information about
	- $k\geq 2$: the spread ([[variance]]) of the [[distribution]] $f_X(x)$ 
	- $k\geq 3$: the [[skewness]] of the [[distribution]] $f_X(x)$ 
	- $k\geq 4$: the [[kurtosis]] of the [[distribution]] $f_X(x)$ 
	- ...
-  Isolated Infiormation about the spread: [[variance]] $\mu'_2[X]=\mathbb{VAR}\left[X\right]$
## some properties
- $\mu'_0[X]=1$
- $\mu'_1[X]=0$ 
- $\mu'_2[X]=\mathbb{VAR}\left[X\right]$ 

$$
\mu'_k[X+c]=\mu'_k[X]
$$
$$
\mu'_k[cX]=c^k\mu'_k[X]
$$
$$
X \perp Y, k \in \{1,2,3\} \Rightarrow \mu'_k[X+Y]=\mu'_k[X]+\mu'_k[Y]
$$
# standadized moments
$$
\frac{
\mathbb{E}\left[(X- \mu)^k\right]
}{
\sqrt{\mathbb{E}\left[(X- \mu)^2\right]}^k
} = 
\frac{
\mathbb{E}\left[(X- \mu)^k\right]
}{
\sigma^k
} = 
\mu''_k[X]
$$
- normalized versiom of the central moment
- does not contain information about the magnitude (raw moment) and the spread (central moment) any more
- contrains information about
	- $k\geq 3$: the [[skewness]] of the [[distribution]] $f_X(x)$ 
	- $k\geq 4$: the [[kurtosis]] of the [[distribution]] $f_X(x)$ 
	- ...
-  Isolated Infiormation about the [[symmetric distribution|symmetry]] of $f_X(x)$: [[skewness]] $\mu''_3[X]=\frac{\mathbb{E}\left[(X-\mu)^3\right]}{\sigma^3}$

# anki

START
Basic
raw moments
- definition
- properties for $k \in \{0,1,2\}$ (3)
- gerneral properties (2)
Back: 
## Definition
$$
\mathbb{E}\left[X^k\right] = \int\limits_{-\infty}^\infty x^k f_X(x)dx = \mu_k[X]
$$
- contrains information about
	- $k\geq 1$: the overall magnitude of a [[random variable]]
	- $k\geq 2$: the spread ([[variance]]) of the [[distribution]] $f_X(x)$ 
	- $k\geq 3$: the [[skewness]] of the [[distribution]] $f_X(x)$ 
	- $k\geq 4$: the [[kurtosis]] of the [[distribution]] $f_X(x)$ 
	-  ...
- $\mu_1[X] = \mathbb{E}\left[X\right]$
## properties
- $\mu_0[X]=1$
- $\mu_1[X]=\mathbb{E}\left[X\right]$ 
	- is called the [[expectation]] or mean of a [[random variable]] 
	- contains the isolated information about the overall magnitude of $X$
- $\mu_2[X]=\mathbb{E}\left[X^2\right]$ 
	- contains information about the overall magnitude and spread of $f_X(x)$
	- to isolate the information about the spread → central moment $\mu'_2=\mathbb{VAR}\left[X\right]$
- If $\mathbb{E}\left[X\right]=0$ and $f_X(x)$ is [[symmetric distribution|symmetric around its mean]] → $\mathbb{E}\left[X^{2k+1}\right] = 0 \: \forall k \in \mathbb{N}_0$ 
- $\mu_k[cX]=c^k\mu_k[X]$

Tags: mathematics statistics
<!--ID: 1680157250276-->
END

START
Basic
central moments
- definition
- properties for $k \in \{0,1,2\}$ (3)
- gerneral properties (3)
Back: 
## Definition
$$
\mathbb{E}\left[(X- \mu)^k\right] = \int\limits_{-\infty}^\infty (X- \mu)^k f_X(x)dx = \mu'_k[X]
$$
- shifted version of the raw moment
- does not contain information about the magnitude ($\mu_1[X]$) any more
- contrains information about
	- $k\geq 2$: the spread ([[variance]]) of the [[distribution]] $f_X(x)$ 
	- $k\geq 3$: the [[skewness]] of the [[distribution]] $f_X(x)$ 
	- $k\geq 4$: the [[kurtosis]] of the [[distribution]] $f_X(x)$ 
	- ...
-  Isolated Infiormation about the spread: [[variance]] $\mu'_2[X]=\mathbb{VAR}\left[X\right]$
## properties
- $\mu'_0[X]=1$
- $\mu'_1[X]=0$ 
- $\mu'_2[X]=\mathbb{VAR}\left[X\right]$ 

$$
\mu'_k[X+c]=\mu'_k[X]
$$
$$
\mu'_k[cX]=c^k\mu'_k[X]
$$
$$
X \perp Y, k \in \{1,2,3\} \Rightarrow \mu'_k[X+Y]=\mu'_k[X]+\mu'_k[Y]
$$
Tags: mathematics statistics
<!--ID: 1680157250280-->
END


START
Basic
standadized moments
- definition and concept
- meaning for a [[distribution]]
Back: 
$$
\frac{
\mathbb{E}\left[(X- \mu)^k\right]
}{
\sqrt{\mathbb{E}\left[(X- \mu)^2\right]}^k
} = 
\frac{
\mathbb{E}\left[(X- \mu)^k\right]
}{
\sigma^k
} = 
\mu''_k[X]
$$
- normalized versiom of the central moment
- does not contain information about the magnitude (raw moment) and the spread (central moment) any more
- contrains information about
	- $k\geq 3$: the [[skewness]] of the [[distribution]] $f_X(x)$ 
	- $k\geq 4$: the [[kurtosis]] of the [[distribution]] $f_X(x)$ 
	- ...
-  Isolated Infiormation about the [[symmetric distribution|symmetry]] of $f_X(x)$: [[skewness]] $\mu''_3[X]=\frac{\mathbb{E}\left[(X-\mu)^3\right]}{\sigma^3}$

Tags: mathematics statistics
<!--ID: 1680157250284-->
END


START
Basic
moment summary (definition and meaning)
- raw moments
- central moments
- standadized moments
Back: 
- [[moments]] describe the properties of the [[distribution]] of [[random variable|random variables]]

### Raw Moments
$$
\mathbb{E}\left[X^k\right] = \int\limits_{-\infty}^\infty x^k f_X(x)dx = \mu_k[X]
$$
- contrains information about
	- $k\geq 1$: the overall magnitude of a [[random variable]]
	- $k\geq 2$: the spread ([[variance]]) of the [[distribution]] $f_X(x)$ 
	- $k\geq 3$: the [[skewness]] of the [[distribution]] $f_X(x)$ 
	- $k\geq 4$: the [[kurtosis]] of the [[distribution]] $f_X(x)$ 
	-  ...
- $\mu_1[X] = \mathbb{E}\left[X\right]$

### Central Moments
$$
\mathbb{E}\left[(X- \mu)^k\right] = \int\limits_{-\infty}^\infty (X- \mu)^k f_X(x)dx = \mu'_k[X]
$$
- shifted version of the raw moment
- does not contain information about the magnitude ($\mu_1[X]$) any more
- contrains information about
	- $k\geq 2$: the spread ([[variance]]) of the [[distribution]] $f_X(x)$ 
	- $k\geq 3$: the [[skewness]] of the [[distribution]] $f_X(x)$ 
	- $k\geq 4$: the [[kurtosis]] of the [[distribution]] $f_X(x)$ 
	- ...
-  Isolated Infiormation about the spread: [[variance]] $\mu'_2[X]=\mathbb{VAR}\left[X\right]$

### Standadized Moments
$$
\frac{
\mathbb{E}\left[(X- \mu)^k\right]
}{
\sqrt{\mathbb{E}\left[(X- \mu)^2\right]}^k
} = 
\frac{
\mathbb{E}\left[(X- \mu)^k\right]
}{
\sigma^k
} = 
\mu''_k[X]
$$
- normalized versiom of the central moment
- does not contain information about the magnitude (raw moment) and the spread (central moment) any more
- contrains information about
	- $k\geq 3$: the [[skewness]] of the [[distribution]] $f_X(x)$ 
	- $k\geq 4$: the [[kurtosis]] of the [[distribution]] $f_X(x)$ 
	- ...
-  Isolated Infiormation about the [[symmetric distribution|symmetry]] of $f_X(x)$: [[skewness]] $\mu''_3[X]=\frac{\mathbb{E}\left[(X-\mu)^3\right]}{\sigma^3}$

Tags: mathematics statistics
<!--ID: 1674122984711-->
END