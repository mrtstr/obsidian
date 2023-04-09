## Statistical Estimator
- given [[statistical sample|observations]] of a [[discrete random variable]] $X$ with the unknown [[probability density function]] $f_{X \mid \theta}(x \mid \theta)$
- $\theta$ is a property (often a parameter) of $f_{X \mid \theta}(x \mid \theta)$
- Goal: calculate an estimation $\widehat{\theta}$ of $\theta$ 

(in contrast, a [[statistical predictor]] predicting the relationship between input/features $x$ and output/labels $y$ by approximating properties of the [[conditional distribution]] $f_{X|Y}(x|y)$)

START
Basic
statistical estimator
- verbal definition 
Back: 
- given [[statistical sample|observations]] of a [[discrete random variable]] $X$ with the unknown [[probability density function]] $f_{X \mid \theta}(x \mid \theta)$
- $\theta$ is a property (often a parameter) of $f_{X \mid \theta}(x \mid \theta)$
- Goal: calculate an estimation $\widehat{\theta}$ of $\theta$ 
Tags: statistical learning
<!--ID: 1664723232163-->
END

START
Basic
difference statistical estimator and predictor

Back: 
### Statistical Estimator
- given [[statistical sample|observations]] of a [[discrete random variable]] $X$ with the unknown [[probability density function]] $f_{X \mid \theta}(x \mid \theta)$
- $\theta$ is a property (often a parameter) of $f_{X \mid \theta}(x \mid \theta)$
- Goal: calculate an estimation $\widehat{\theta}$ of $\theta$ 

### statistical predictor
- Goal: find connect between input/features $x$ and output/labels $y$
- because the [[joint distribution]] $f_{XY}(x,y)$ is hard to find the goal is to approximate [[conditional distribution]]  $f_{X|Y}(x|y)$ or its properties (e.g. mean)
Tags: statistical learning
<!--ID: 1664723232168-->
END