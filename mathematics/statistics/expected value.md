#### Concept
- Defined for [[random variable]]
- Generalization of the weighted mean: mean of possible outcomes weighted by its probability
- defined for [[conditional distribution|conditional distributions]]: [[conditional expectation]] 

#### expected values of a [[continuous random variable]] $X$ with a [[PDF|PDF]] $f_X(x)$:
$\mathbb{E}[X]=\int\limits_\infty^\infty x f_X(x)dx$  

#### expected value of a [[discrete random variable]] $X$:
$\mathbb{E}[X]=\sum\limits_{i=0}^\infty x_i p(x_i)$  

#### expected value of the product of two random variables $X$ and $Y$ with a [[joint distribution]] $f_{XY}(x,y)$
$\mathbb{E}[XY]=\int\limits_\infty^\infty \int\limits_\infty^\infty xyf_{XY}(x,y)dx dy = \mathbb{E}[X] \cdot\mathbb{E}[Y]+\mathbb{COV}[X,Y]$  
(with $\mathbb{COV}[X,Y]=0$ when $X$ and $Y$ [[independence|independent]])

#### expected value of a function of a random variable
$\mathbb{E}[g(X)]=\int\limits_\infty^\infty g(x) \cdot f_X(x)dx$  

#### properties
- $\mathbb{E}[aX+bY]=a\mathbb{E}[X]+b\mathbb{E}[Y]$  (linearity)
- $X\geq Y \Leftrightarrow \mathbb{E}[X] \geq \mathbb{E}[Y]$ (monoton)
- $\mathbb{E}[\mathbb{E}[X]]=\mathbb{E}[X]$ because $\mathbb{E}[a]=a$

START
Basic
expected values of a continuous and discrete random variables
Back: 
continuous:
$\mathbb{E}[X]=\int\limits_\infty^\infty x f_X(x)dx$ 
discrete:
$\mathbb{E}[X]=\sum\limits_{i=0}^\infty x_i p(x_i)$  
Tags: mathematics, statistics
<!--ID: 1661882015629-->
END

START
Basic
expected value of the product of two random variables $X$ and $Y$ with a joint distribution $f_{XY}(x,y)$
Back: 
$\mathbb{E}[XY]=\int\limits_\infty^\infty \int\limits_\infty^\infty xyf_{XY}(x,y)dx dy = \mathbb{E}[X] \cdot\mathbb{E}[Y]+\mathbb{COV}[X,Y]$  
(with $\mathbb{COV}[X,Y]=0$ when $X$ and $Y$ independent)
Tags: mathematics, statistics
<!--ID: 1661882015633-->
END

START
Basic
expected value of a function $g(.)$ of a random variable
Back: 
$\mathbb{E}[g(X)]=\int\limits_\infty^\infty g(x) \cdot f_X(x)dx$  
Tags: mathematics, statistics
<!--ID: 1661882015635-->
END

START
Basic
expected value of the sum of two random variables
Back: 
$\mathbb{E}[aX+bY]=a\mathbb{E}[X]+b\mathbb{E}[Y]$  
Tags: mathematics, statistics
<!--ID: 1661882015637-->
END