### callbacks
- functions that are applied at each iteration

#### `lightgbm.early_stopping`
Activates early stopping. The model will train until the validation score doesn’t improve by at least `min_delta`. Validation score needs to improve at least every `stopping_rounds` round(s) to continue training. Requires at least one validation data and one metric. If there’s more than one, will check all of them. But the training data is ignored anyway. To check only the first metric set `first_metric_only` to True. The index of iteration that has the best performance will be saved in the `best_iteration` attribute of a model.

#### `lightgbm.log_evaluation`
- Create a callback that logs the evaluation results.

#### `lightgbm.record_evaluation`
- Create a callback that records the evaluation history into `eval_result`.

#### `lightgbm.reset_parameter`
- for setting dynamic training parameters by list or callable