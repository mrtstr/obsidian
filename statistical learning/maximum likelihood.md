[[loss functions]]
[[statistical predictor]]

# Definition
$L(\Theta)=\sum_{(x_i,y_i) \in \mathcal{T}_{train}} log [f_{Y|X, \Theta}(y_i,x_i)] \rightarrow f_\Theta(x)$ 

# minumum
- $L(\Theta)=\sum_{(x_i,y_i) \in \mathcal{T}_{train}} log [f_{Y|X, \Theta}(y_i,x_i)] \rightarrow f_\Theta(x)$
- equal to [[mean square error]] when $f_{Y|X}(y|x) \sim \mathcal{N}$ 