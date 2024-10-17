## params

### core_params
#### objective (loss function)
- `L2 regression` (aliases `regression`, `regression_l2`, `l2`, `mean_squared_error`, `mse`, `l2_root`, `root_mean_squared_error`, `rmse`)
- `regression_l1` (aliases `l1`, `mean_absolute_error`, `mae`)
- `quantile` 
- `huber` `poission`, `mape`, `gamma`...

#### learning_rate

#### num_leaves

#### tree_learner
#### num_iterations

alpha: 0.95
bagging_fraction: 0.9
bagging_freq: 5
colsample_bytree: 0.8
lambda_l1: 0.58
lambda_l2: 2.06
learning_rate: 0.08
max_depth: 8
metric: quantile
min_child_samples: 100
min_sum_hessian_in_leaf: 100
num_leaves: 53
objective: quantile
verbose: -1

### Learning Control Parameters
### train_params:
    num_boost_round: 2
