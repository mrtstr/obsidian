# Variance Bias Trade-off
[[model bias]]
[[model variance]]

relationship of the [[error]] components [[model bias]] and [[model variance]]
## Decomposition
### [[statistical estimator]]
- given a [[statistical sample|sample]] $\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)$ from the true but unknown [[probability density function|distribution]] and the parameter estimation $\widehat{\theta}_\mathcal{T}$ based on $\mathcal{T}$
- in theory it is possible to predict the $\theta$ because it's a constant
- in this case the [[error]] is only depending on the [[model bias]] and [[model variance]]
- the [[mean square error]] of the [[statistical estimator]] can be decomposed as follows
$$
\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[
\left(\widehat{\theta}_\mathcal{T}-
\theta
\right)^2
\right]


$$
$$
\begin{split}
=
\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[
\widehat{\theta}_\mathcal{T}^2
\right]
+ \theta^2
- 2
\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[
\widehat{\theta}_\mathcal{T}
\right]
\theta
\\
+
\underbrace{
\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[
\widehat{\theta}_\mathcal{T}
\right]^2
-
\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[
\widehat{\theta}_\mathcal{T}
\right]^2
}_\text{$=0$}
\end{split}
$$
$$
\begin{split}
=
\underbrace{
\left(
\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[
\widehat{\theta}_\mathcal{T}^2
\right]

-
\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[
\widehat{\theta}_\mathcal{T}
\right]^2
\right)

}_\text{$variance$}
\\
+
\underbrace{
\left(

\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[
\widehat{\theta}_\mathcal{T}
\right]^2

+ \theta^2
- 2
\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[
\widehat{\theta}_\mathcal{T}
\right]
\theta
\right)
}_\text{$bias^2$}
\end{split}
$$
$$
=
\mathbb{VAR}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[\widehat{\theta}_\mathcal{T}\right]
+
\underbrace{
\left(
\theta
-
\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[
\widehat{\theta}_\mathcal{T}
\right]
\right)^2
}_\text{$bias^2$}
$$
$$
=
\mathbb{VAR}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[\widehat{\theta}_\mathcal{T}\right]
+
Bias\left[\widehat{\theta}_\mathcal{T}\right]^2
$$
- the [[error]] is the sum of the [[model variance]] and squared [[model bias]] 
### [[statistical predictor]]
- Given the approximated [[statistical predictor]] $\widehat{f}_{\mathcal{T}_{train}}(x)$ trained on a training set $\mathcal{T}_{train}=\{(x_i, y_i)\} \subset \mathcal{D}=\{(x, y) \; |\; (x, y) \sim f_{XY}(.,.)\}$ 
- optimal [[statistical predictor|estimator]] $f(x)=\mathbb{E}[Y \:|\:X=x]$
- here we don't want to predict a parameter but a target value
- because of the randomness of $f_{Y|X}(y|x)$ there will be a component of the [[error]] which is unavoidable
- the label $Y=f(x) + \epsilon$ can be described as the sum of the optimal [[statistical predictor]] $f(x)$ and the unavoidable [[error]] $\epsilon \sim f_\epsilon(x)$ with the property $\mathbb{E}[\epsilon] = 0$ and $\mathbb{VAR}[\epsilon] =\mathbb{VAR}[Y \:|\:X=x_0]$
- for a given point in the feature space $x_0$ the [[mean square error]] can be decomposed as follows
- the randomness is caused by the randomness of the training set $\mathcal{T}$ and $\epsilon$ which are assumed to be [[stochastic independent|independent]] $\mathcal{T} \perp \epsilon$
- $f(x)=\mathbb{E}[Y \:|\:X=x]$ is not depending on either of them and can be treated as non-stochastic

$$
\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}\left(x \mid \theta \right)
, \: \epsilon \sim f_\epsilon(x_0)
}\left[\left(
Y-
\widehat{f}_{\mathcal{T}}(x_0)
\right)^2\right]
$$
$$
=\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}
, \: \epsilon \sim f_\epsilon(x_0)
}\left[\left(
f(x) + \epsilon
-
\widehat{f}_{\mathcal{T}}(x_0)
\right)^2\right]
$$
$$
\begin{split}
=\mathbb{E}_{
\epsilon \sim f_\epsilon(x_0)
}\left[\left(
f(x) + \epsilon
\right)^2\right]
+
\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}
}\left[
\widehat{f}_{\mathcal{T}}(x_0)
^2\right]
\\
-
2
\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}
}\left[
\widehat{f}_{\mathcal{T}}(x_0)
\right]
\mathbb{E}_{
\epsilon \sim f_\epsilon(x_0)
}\left[
f(x_0) + \epsilon
\right]
\\
+
\underbrace{
\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}
}\left[
\widehat{f}_{\mathcal{T}}(x_0)
\right]^2
-
\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}
}\left[
\widehat{f}_{\mathcal{T}}(x_0)
\right]^2
}_\text{$=0$}
\end{split}
$$
$$
\begin{split}
=
\underbrace{
\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}
}\left[
\widehat{f}_{\mathcal{T}}(x_0)
^2\right]
-
\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}
}\left[
\widehat{f}_{\mathcal{T}}(x_0)
\right]^2
}_\text{$variance$}

\\
-
2
\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}
}\left[
\widehat{f}_{\mathcal{T}}(x_0)
\right]
\left(
\underbrace{
\mathbb{E}_{
\epsilon \sim f_\epsilon(x_0)
}\left[
\epsilon
\right]
}_\text{$=0$}
+
f(x)
\right)
\\

+
\underbrace{
\mathbb{E}_{
\epsilon \sim f_\epsilon(x_0)
}\left[
\epsilon
^2\right]
}_\text{$\mathbb{VAR}[\epsilon]$}
+ f(x)^2
+ 2f(x)
\underbrace{
\mathbb{E}_{
\epsilon \sim f_\epsilon(x_0)
}\left[
\epsilon
\right]
}_\text{$=0$}
\\
+

\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}
}\left[
\widehat{f}_{\mathcal{T}}(x_0)
\right]^2

\end{split}
$$
$$
\begin{split}
=
\mathbb{VAR}_{\mathcal{T} \sim \mathcal{D}}\left[\widehat{f}_{\mathcal{T}}(x_0)\right]
+
\mathbb{VAR}[\epsilon]
\\
\underbrace{
+f(x)^2
+
\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}
}\left[
\widehat{f}_{\mathcal{T}}(x_0)
\right]^2
-
2
\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}
}\left[
\widehat{f}_{\mathcal{T}}(x_0)
\right]
f(x)
}_\text{$bias^2$}
\end{split}
$$
$$
\begin{split}
=
\mathbb{VAR}_{\mathcal{T} \sim \mathcal{D}}\left[\widehat{f}_{\mathcal{T}}(x_0)\right]
+
\mathbb{VAR}[\epsilon]
+
Bias\left[\widehat{f}_{\mathcal{T}_{train}}(x_0)\right]^2
\end{split}
$$
- the [[error]] is the sum of the [[model variance]] and squared [[model bias]] and an unavoidable part that is depending on the variance of the data $\mathbb{VAR}[\epsilon] =\mathbb{VAR}[Y \:|\:X=x_0]$




START
Basic
variance bias trade-off for [[statistical estimator]]
- relationship to [[mean square error]] (equation)
- verbal explanation
Back: 
- given a [[statistical sample|sample]] $\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)$ from the true but unknown [[probability density function|distribution]] and the parameter estimation $\widehat{\theta}_\mathcal{T}$ based on $\mathcal{T}$
- in theory it is possible to predict the $\theta$ because it's a constant
- in this case the [[error]] is only depending on the [[model bias]] and [[model variance]]
$$
\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[
\left(\widehat{\theta}_\mathcal{T}-
\theta
\right)^2
\right]
=
\mathbb{VAR}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[\widehat{\theta}_\mathcal{T}\right]
+
Bias\left[\widehat{\theta}_\mathcal{T}\right]^2

$$
Tags: statistical learning
<!--ID: 1664782921024-->
END

START
Basic
variance bias trade-off for [[statistical predictor]]
- relationship to [[mean square error]] (equation)
- verbal explanation
Back: 
- Given the approximated [[statistical predictor]] $\widehat{f}_{\mathcal{T}_{train}}(x)$ trained on a training set $\mathcal{T}_{train}=\{(x_i, y_i)\} \subset \mathcal{D}=\{(x, y) \; |\; (x, y) \sim f_{XY}(.,.)\}$ 
- optimal [[statistical predictor|estimator]] $f(x)=\mathbb{E}[Y \:|\:X=x]$
- here we don't want to predict a parameter but a target value
- because of the randomness of $f_{Y|X}(y|x)$ there will be a component of the [[error]] which is unavoidable
- the label $Y=f(x) + \epsilon$ can be described as the sum of the optimal [[statistical predictor]] $f(x)$ and the unavoidable [[error]] $\epsilon \sim f_\epsilon(x)$ with the property $\mathbb{E}[\epsilon] = 0$ and $\mathbb{VAR}[\epsilon] =\mathbb{VAR}[Y \:|\:X=x_0]$
- the randomness is caused by the randomness of the training set $\mathcal{T}$ and $\epsilon$ which are assumed to be [[stochastic independence|independent]] $\mathcal{T} \perp \epsilon$

$$
\begin{split}
\mathbb{E}_{
\mathcal{T} \sim f_{X \mid \theta}\left(x \mid \theta \right)
, \: \epsilon \sim f_\epsilon(x_0)
}\left[\left(
Y-
\widehat{f}_{\mathcal{T}}(x_0)
\right)^2\right]
\\
=
\mathbb{VAR}_{\mathcal{T} \sim \mathcal{D}}\left[\widehat{f}_{\mathcal{T}}(x_0)\right]
+
\mathbb{VAR}[\epsilon]
+
Bias\left[\widehat{f}_{\mathcal{T}_{train}}(x_0)\right]^2
\end{split}
$$
Tags: statistical learning
<!--ID: 1664782921031-->
END


START
Basic
variance bias trade-off for [[statistical estimator]]
- relationship to [[mean square error]] (equation with proof)
Back: 
- given a [[statistical sample|sample]] $\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)$ from the true but unknown [[probability density function|distribution]] and the parameter estimation $\widehat{\theta}_\mathcal{T}$ based on $\mathcal{T}$
- in theory it is possible to predict the $\theta$ because it's a constant
- in this case the [[error]] is only depending on the [[model bias]] and [[model variance]]
- the [[mean square error]] of the [[statistical estimator]] can be decomposed as follows
$$
\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[
\left(\widehat{\theta}_\mathcal{T}-
\theta
\right)^2
\right]


$$
$$
\begin{split}
=
\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[
\widehat{\theta}_\mathcal{T}^2
\right]
+ \theta^2
- 2
\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[
\widehat{\theta}_\mathcal{T}
\right]
\theta
\\
+
\underbrace{
\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[
\widehat{\theta}_\mathcal{T}
\right]^2
-
\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[
\widehat{\theta}_\mathcal{T}
\right]^2
}_\text{=0}
\end{split}
$$
$$
\begin{split}
=
\underbrace{
\left(
\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[
\widehat{\theta}_\mathcal{T}^2
\right]

-
\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[
\widehat{\theta}_\mathcal{T}
\right]^2
\right)

}_\text{variance}
\\
+
\underbrace{
\left(

\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[
\widehat{\theta}_\mathcal{T}
\right]^2

+ \theta^2
- 2
\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[
\widehat{\theta}_\mathcal{T}
\right]
\theta
\right)
}_\text{bias2}
\end{split}
$$
$$
=
\mathbb{VAR}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[\widehat{\theta}_\mathcal{T}\right]
+
\underbrace{
\left(
\theta
-
\mathbb{E}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[
\widehat{\theta}_\mathcal{T}
\right]
\right)^2
}_\text{bias2}
$$
$$
=
\mathbb{VAR}_{\mathcal{T} \sim f_{X \mid \theta}(x \mid \theta)}\left[\widehat{\theta}_\mathcal{T}\right]
+
Bias\left[\widehat{\theta}_\mathcal{T}\right]^2
$$
- the [[error]] is the sum of the [[model variance]] and squared [[model bias]] 
Tags: statistical learning
<!--ID: 1664782921035-->
END

START
Basic
variance bias trade-off for [[statistical predictor]]
- relationship to [[mean square error]] (equation with proof)
Back: 
- Given the approximated [[statistical predictor]] $\widehat{f}_{\mathcal{T}_{train}}(x)$ trained on a training set $\mathcal{T}_{train}=\{(x_i, y_i)\} \subset \mathcal{D}=\{(x, y) \; |\; (x, y) \sim f_{XY}(.,.)\}$ 
- optimal [[statistical predictor|estimator]] $f(x)=\mathbb{E}[Y \:|\:X=x]$
- here we don't want to predict a parameter but a target value
- because of the randomness of $f_{Y|X}(y|x)$ there will be a component of the [[error]] which is unavoidable
- the label $Y=f(x) + \epsilon$ can be described as the sum of the optimal [[statistical predictor]] $f(x)$ and the unavoidable [[error]] $\epsilon \sim f_\epsilon(x)$ with the property $\mathbb{E}[\epsilon] = 0$ and $\mathbb{VAR}[\epsilon] =\mathbb{VAR}[Y \:|\:X=x_0]$
- for a given point in the feature space $x_0$ the [[mean square error]] can be decomposed as follows
- the randomness is caused by the randomness of the training set $\mathcal{T}$ and $\epsilon$ which are assumed to be [[stochastic independent|independent]] $\mathcal{T} \perp \epsilon$
- $f(x)=\mathbb{E}[Y \:|\:X=x]$ is not depending on either of them and can be treated as non-stochastic

$$
\mathbb{E}_{
\mathcal{T} \mathcal{D}
, \: \epsilon \sim f_\epsilon(x_0)
}\left[\left(
Y-
\widehat{f}_{\mathcal{T}}(x_0)
\right)^2\right]
$$
$$
=\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}
, \: \epsilon \sim f_\epsilon(x_0)
}\left[\left(
f(x) + \epsilon
-
\widehat{f}_{\mathcal{T}}(x_0)
\right)^2\right]
$$
$$
\begin{split}
=\mathbb{E}_{
\epsilon \sim f_\epsilon(x_0)
}\left[\left(
f(x_0) + \epsilon
\right)^2\right]
+
\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}
}\left[
\widehat{f}_{\mathcal{T}}(x_0)
^2\right]
\\
-
2
\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}
}\left[
\widehat{f}_{\mathcal{T}}(x_0)
\right]
\mathbb{E}_{
\epsilon \sim f_\epsilon(x_0)
}\left[
f(x_0) + \epsilon
\right]
\\
+
\underbrace{
\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}
}\left[
\widehat{f}_{\mathcal{T}}(x_0)
\right]^2
-
\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}
}\left[
\widehat{f}_{\mathcal{T}}(x_0)
\right]^2
}_\text{=0}
\end{split}
$$
$$
\begin{split}
=
\underbrace{
\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}
}\left[
\widehat{f}_{\mathcal{T}}(x_0)
^2\right]
-
\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}
}\left[
\widehat{f}_{\mathcal{T}}(x_0)
\right]^2
}_\text{variance}

\\
-
2
\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}
}\left[
\widehat{f}_{\mathcal{T}}(x_0)
\right]
\left(
\underbrace{
\mathbb{E}_{
\epsilon \sim f_\epsilon(x_0)
}\left[
\epsilon
\right]
}_\text{=0}
+
f(x)
\right)
\\

+
\underbrace{
\mathbb{E}_{
\epsilon \sim f_\epsilon(x_0)
}\left[
\epsilon
^2\right]
}_\text{VAR[epsilon]}
+ f(x)^2
+ 2f(x)
\underbrace{
\mathbb{E}_{
\epsilon \sim f_\epsilon(x_0)
}\left[
\epsilon
\right]
}_\text{=0}
\\
+

\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}
}\left[
\widehat{f}_{\mathcal{T}}(x_0)
\right]^2

\end{split}
$$
$$
\begin{split}
=
\mathbb{VAR}_{\mathcal{T} \sim \mathcal{D}}\left[\widehat{f}_{\mathcal{T}}(x_0)\right]
+
\mathbb{VAR}[\epsilon]
\\
\underbrace{
+f(x)^2
+
\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}
}\left[
\widehat{f}_{\mathcal{T}}(x_0)
\right]^2
-
2
\mathbb{E}_{
\mathcal{T} \sim \mathcal{D}
}\left[
\widehat{f}_{\mathcal{T}}(x_0)
\right]
f(x)
}_\text{bias2}
\end{split}
$$
$$
\begin{split}
=
\mathbb{VAR}_{\mathcal{T} \sim \mathcal{D}}\left[\widehat{f}_{\mathcal{T}}(x_0)\right]
+
\mathbb{VAR}[\epsilon]
+
Bias\left[\widehat{f}_{\mathcal{T}_{train}}(x_0)\right]^2
\end{split}
$$
- the [[error]] is the sum of the [[model variance]] and squared [[model bias]] and an unavoidable part that is depending on the variance of the data $\mathbb{VAR}[\epsilon] =\mathbb{VAR}[Y \:|\:X=x_0]$

Tags: statistical learning
<!--ID: 1664782921038-->
END


START
Basic
variance bias trade-off
- difference [[mean square error]] of a [[statistical predictor]] and a [[statistical estimator]]
Back: 
- for a [[statistical estimator]] we want to approximate a constant parameter $\theta$ of the true but unknown distribution of the data (which is possible without any error)
- in this case the [[error]] is only depending on the squared [[model bias]] and [[model variance]]
- for a [[statistical predictor]] we don't want to predict a parameter but a target value
- because of the randomness of $f_{Y|X}(y|x)$ there will be a component of the [[error]] which is unavoidable
- the unavoidable [[error]] $\epsilon \sim f_\epsilon(x_0)$ has the property $\mathbb{E}[\epsilon] = 0$ and $\mathbb{VAR}[\epsilon] =\mathbb{VAR}[Y \:|\:X=x_0]$
Tags: statistical learning
<!--ID: 1664782921041-->
END