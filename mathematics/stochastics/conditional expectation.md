[[expected value]] for [[conditional distribution|conditional distributions]]
$\mathbb{E}[Y|X=x]=\int\limits_\infty^\infty y f_{Y|X=x}(x)dy$

proof for $\mathbb{E}[Y]  = \mathbb{E}\left[\mathbb{E}[Y|X]\right]$ 
$$
\begin{split}
\mathbb{E}\left[\mathbb{E}[X|Y]\right] 
& =\int\limits_{-\infty}^\infty f_{X}(x) 
\underbrace{ \int\limits_{-\infty}^\infty y  f_{Y|X}(y \mid x)dy 
}_\text{$\mathbb{E}[X|Y]$}
\:dx \\
& = \int\limits_{-\infty}^\infty \int\limits_{-\infty}^\infty y f_{X}(x) f_{Y|X}(y \mid x)dy \:dx \\
& = \int\limits_{-\infty}^{\infty} y f_{Y}(y)dy  \\
& = \mathbb{E}\left[Y\right]
\end{split}
$$


START
Basic
conditional expected values: 
- definition
- proof for $\mathbb{E}[Y]  = \mathbb{E}\left[\mathbb{E}[Y|X]\right]$ 
Back: 
$\mathbb{E}[Y|X=x]=\int\limits_\infty^\infty y f_{Y|X=x}(x)dy$

proof for $\mathbb{E}[Y]  = \mathbb{E}\left[\mathbb{E}[Y|X]\right]$:
$$
\begin{split}
\mathbb{E}\left[\mathbb{E}[X|Y]\right] 
& =\int\limits_{-\infty}^\infty f_{X}(x) 
\underbrace{ \int\limits_{-\infty}^\infty y  f_{Y|X}(y \mid x)dy 
}_\text{E[X|Y]}
\:dx \\
& = \int\limits_{-\infty}^\infty \int\limits_{-\infty}^\infty y f_{X}(x) f_{Y|X}(y \mid x)dy \:dx \\
& = \int\limits_{-\infty}^{\infty} y f_{Y}(y)dy  \\
& = \mathbb{E}\left[Y\right]
\end{split}
$$

Tags: mathematics, statistics
<!--ID: 1661928261922-->
END