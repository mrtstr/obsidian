### l2 regularization
- given a [[neural network]] with the parameters $\theta$
- we introduce a penalty term $\Omega(\theta)$ with a weight factor $\gamma$ that penalized the size of the parameters of the weight metrics $W^{1}, ..., W^{L}$
- we ignore the bias term here because they are not prone to over fitting
$$
\begin{split}
\Omega(\theta) 
= \sum_{l=1}^L \frac{1}{2} ||W^{{l}}||^2_F 
= \sum_{l=1}^L \frac{1}{2} \sum_{i=1}^{n_l} \sum_{j=1}^{n_{l-1}} \left(W_{ij}^{(L)}\right)^2 
\end{split}
$$
- 
# ----------------

![[frobenius norm#frobenius norm]]

![[regularization#regularization]]