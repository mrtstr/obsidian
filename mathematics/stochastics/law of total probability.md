
## [[law of total probability]] for [[event|events]]
for a [[partitioned sample space]] $B = \{B_i \mid i=1,2,...,k\}$ the following is true:
$$
P(A)=\sum\limits_{i=1}^{k}P(B_i)\cdot P(A \mid B_i)
$$
![[Selection_002.png]]


## [[law of total probability]] for a [[continuous random variable]]

With the [[multiplication rule]] $f_{XY}(x,y) =f_{X\mid Y}(x \mid y) \cdot f_Y(y)$ we can express the [[marginal distribution]] as the following to get the [[law of total probability]] for [[continuous random variable]]
$$
f_{X}(x) = 
\int\limits^{\infty}_{-\infty} f_{X\mid Y}(x \mid y) f_Y(y) dy
$$
## [[law of total probability]] for a [[discrete random variable]]
$$
f_{X}(x) = 
\sum\limits_{all \:y} f_{X\mid Y}(x \mid y) f_Y(y)
$$
# anki

START
Basic
[[law of total probability]] for [[event|events]]
Back: 
## Definition
for a [[partitioned sample space]] $B = \{B_i \mid i=1,2,...,k\}$ the following is true:
$$
P(A)=\sum\limits_{i=1}^{k}P(B_i)\cdot P(A \mid B_i)
$$
![[Selection_002.png]]

Tags: mathematics, statistics
<!--ID: 1666457499354-->
END


START
Basic
[[law of total probability]]
- [[continuous random variable]] 
- [[discrete random variable]]
Back: 
## [[law of total probability]] for a [[continuous random variable]]

With the [[multiplication rule]] $f_{XY}(x,y) =f_{X\mid Y}(x \mid y) \cdot f_Y(y)$ we can express the [[marginal distribution]] as the following to get the [[law of total probability]] for [[continuous random variable]]
$$
f_{X}(x) = 
\int\limits^{\infty}_{-\infty} f_{X\mid Y}(x \mid y) f_Y(y) dy
$$
## [[law of total probability]] for a [[discrete random variable]]

$$
f_{X}(x) = 
\sum\limits_{all \:y} f_{X\mid Y}(x \mid y) f_Y(y)
$$

Tags: mathematics, statistics
<!--ID: 1671186732883-->
END