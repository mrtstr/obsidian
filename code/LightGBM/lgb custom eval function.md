### custom eval function
- during [[lgb training]] a list of callable for custom evaluation can be provided under `feval`
- need to accept the input preds, eval_data, and return eval_name, eval_result, is_higher_better or list of such tuples