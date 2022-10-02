## concept
- reducing [[model complexity]] of [[tree models]]
- finding a subtree $T \subset T_0$ that is maximizing a cost complexity criterion by removing internal nodes of the initial tree $T_0$
- low complexity → better [[generalization]], less [[model variance]]
- high complexity → better [[training error]] less [[model bias|model bias]] 
- helps against over fitting
## cost complexity criterion
- $\left|T\right|$ number of nodes of tree model $T$
- $\alpha$ tuning parameter for [[training error]] / [[model complexity]] trade off
- $N_m = \left|\left\{y_i | x_i \in R_{m} \right\}\right|$ number of samples in terminal node $R_m$
$$
C_\alpha (T) = 
\underbrace
{
\alpha \cdot \left|T\right| 
}_\text{complexity penalty}
+
\underbrace
{
\sum\limits_{m=1}^{\left|T\right|}N_m \cdot Q_m(T)
}_\text{test error}
$$

- $Q_m(T)$ average test error within terminal leaf $R_m$ 
- e.g. [[mean square error]]:
$$
Q_m(T) = \frac{1}{N_m} \cdot \sum\limits_{\left\{y_i | x_i \in R_{m} \right\}}
\left(y_i - c_m\right)^2
$$
## optimality
- the optimal subtree $T_\alpha \subset T$ dependent on the pruning parameter $\alpha$ will always be found by [[greedy]] removing internal nodes until no improvement is possible 

START
Basic
pruning: context: concept and trade-off
Back: 
- reducing [[model complexity]] of [[tree models]]
- finding a subtree $T \subset T_0$ that is maximizing a cost complexity criterion by removing internal nodes of the initial tree $T_0$
- low complexity → better [[generalization]], less [[model variance]]
- high complexity → better [[training error]] less [[model bias|model bias]] 
- helps against over fitting
Tags: statistical learning, tree based models
<!--ID: 1662888972084-->
END

START
Basic
pruning: cost complexity criterion (with [[mean square error|MSE]] example)
Back: 
- $\left|T\right|$ number of nodes of tree model $T$
- $\alpha$ tuning parameter for [[training error]] / [[model complexity]] trade off
(j, s)- $N_m = \left|\left\{y_i | x_i \in R_{m} \right\}\right|$ number of samples in terminal node $R_m$
$$
C_\alpha (T) = 
\underbrace
{
\alpha \cdot \left|T\right| 
}_\text{complexity penalty}
+
\underbrace
{
\sum\limits_{m=1}^{\left|T\right|}N_m \cdot Q_m(T)
}_\text{test error}
$$

- $Q_m(T)$ average test error within terminal leaf $R_m$ 
- e.g. [[mean square error]]:
$$
Q_m(T) = \frac{1}{N_m} \cdot \sum\limits_{\left\{y_i | x_i \in R_{m} \right\}}
\left(y_i - c_m\right)^2
$$
Tags: statistical learning, tree based models
<!--ID: 1662888972086-->
END

START
Basic
pruning: how to find the optimal subtree $T_\alpha \subset T$ dependent on the pruning parameter $\alpha$
Back: 
 $T_\alpha \subset T$ will always be found by [[greedy]] removing internal nodes until no improvement is possible 
Tags: statistical learning, tree based models
<!--ID: 1662888972090-->
END