# [[tree models]] for solving [[regression]] problems

## model definition
- $\widehat{f}(x)=\sum\limits_{m=1}^{J_m}c_m \cdot \mathbb{I}[x \in R_m]$ (tree model)
- $R_m$ (leaf of the tree model which represents a rectangle in the feature space)
- $\gamma_m=mean[y_i \:|\: x_i \in R_m]$ (value for each leaf)
- $J_m$ (number of leafs)

## training
1) build a complex tree until stop criterion is fulfilled
2) use pruning to reduce model complexity (tree size)


### build a complex tree until stop criterion is fulfilled
- start with complete feature space in one leaf
- separate feature space in rectangles by [[greedy]] splitting up existing rectangles 
	- choose the split that maximizes the [[mean square error]] criterion
- stop when e.g. minimal samples per leaf is reached or improvement of split too small


#### next split
- find the splitting variable $j$ and the splitting value $s$ that will improve the mean square error the most
- by solving ([[brute force]]) the following optimization problem will split one leaf $R_i$ in two leafs $R_{i,1}(j,s) = \left\{x \mid x_j \leq s \right\}$ and $R_{i,2}(j,s) = \left\{x \mid x_j > s \right\}$
$$
\underset{j,i, s}{min} 
\left[
\underset{c_1}{min}
\left[
\sum\limits_{\left\{y_i | x_i \in R_{i,1}(j, s) \right\}} 
\left(y_i - c_1\right)^2
\right]
+
\underset{c_2}{min}
\left[
\sum\limits_{\left\{y_i | x_i \in R_{i,2}(j, s) \right\}} 
\left(y_i - c_2\right)^2
\right]
\right]
$$
(with $c_{1}=mean[y_i \:|\: x_i \in R_{i,1}]$ and $c_2=mean[y_i \:|\: x_i \in R_{i,2}]$)


#### complexity
 - $O(N log(N) \cdot p)$ 
- $N$ = number of samples and $p$ = number of features

 
### [[pruning|cost complexity pruning]]: reduce [[model complexity]]/tree size
- choose a pruning parameter $\alpha$
- use [[pruning]] with [[mean square error]] until the optimal subtree $T_\alpha \subset T$ is found  
- (remove internal nodes until no improvement of cost-complexity criterion is possible)


START
Basic
regression tree: model definition
Back: 
- $\widehat{f}(x)=\sum\limits_{m=1}^{J_m}c_m \cdot \mathbb{I}[x \in R_m]$ (tree model)
- $R_m$ (leaf of the tree model which represents a rectangle in the feature space)
- $\gamma_m=mean[y_i \:|\: x_i \in R_m]$ (value for each leaf)
- $J_m$ (number of leafs)
Tags: statistical learning, tree based models
<!--ID: 1662888972068-->
END

START
Basic
regression tree: training process
Back: 
1) Build a complex tree until stop criterion is fulfilled
- start with complete feature space in one leaf
- separate feature space in rectangles by [[greedy]] splitting up existing rectangles 
	- choose the split that maximizes the [[mean square error]] criterion
- stop when e.g. minimal samples per leaf is reached or improvement of split too small
2) use pruning to reduce model complexity (tree size)
	- choose a pruning parameter $\alpha$
	- use [[pruning]] with [[mean square error]] until the optimal subtree $T_\alpha \subset T$ is found  
		- (remove internal nodes until no improvement of cost-complexity criterion is possible)
Tags: statistical learning, tree based models
<!--ID: 1662888972076-->
END

START
Basic
regression tree: algorithm for building up the tree (how to find the splits)
Back: 
### context
- start with complete feature space in one leaf
- separate feature space in rectangles by [[greedy]] splitting up existing rectangles 
	- choose the split that maximizes the [[mean square error]] criterion
- stop when e.g. minimal samples per leaf is reached or improvement of split too small
#### next split
- find the splitting variable $j$ and the splitting value $s$ that will improve the mean square error the most
- by solving ([[brute force]]) the following optimization problem will split one leaf $R_i$ in two leafs $R_{i,1}(j,s) = \left\{x \mid x_j \leq s \right\}$ and $R_{i,2}(j,s) = \left\{x \mid x_j > s \right\}$
$$
\underset{j,i, s}{min} 
\left[
\underset{c_1}{min}
\left[
\sum\limits_{\left\{y_i | x_i \in R_{i,1}(j, s) \right\}} 
\left(y_i - c_1\right)^2
\right]
+
\underset{c_2}{min}
\left[
\sum\limits_{\left\{y_i | x_i \in R_{i,2}(j, s) \right\}} 
\left(y_i - c_2\right)^2
\right]
\right]
$$
(with $c_{1}=mean[y_i \:|\: x_i \in R_{i,1}]$ and $c_2=mean[y_i \:|\: x_i \in R_{i,2}]$)
Tags: statistical learning, tree based models
<!--ID: 1662888972080-->
END