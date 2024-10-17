### training
- training a a [[LightGBM]] model needs the following input
	- [[lgb params]]
	- [[lgb callbacks]]
	- training data
	- list of validation data sets
	- `feval`: list of [[lgb custom eval function]]
	- init_model
	- **keep_training_booster** (_bool__,_ _optional_ _(__default=False__)_) – Whether the returned Booster will be used to keep training. If False, the returned value will be converted into _InnerPredictor before returning. This means you won’t be able to use `eval`, `eval_train` or `eval_valid` methods of the returned Booster. When your model is very large and cause the memory error, you can try to set this param to `True` to avoid the model conversion performed during the internal call of `model_to_string`. You can still use _InnerPredictor as `init_model` for future continue training.
- function: `lgb.train(param, train_data, num_round, valid_sets=[validation_data])`