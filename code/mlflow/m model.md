### model
- directory containing arbitrary files ([[m artifactory]])
- contains everything needed to load and use the model
- contains
	- serialized (python) model object that wraps the real model and implements functions like `fit`, `predict`, `evaluate` ...
	- parameters
	- dependencies
	- `MLmodel` metadata (type, id, mlflow version...)

#### loading the model
- can be loaded using `mlflow.pyfunc.load_model(model_uri)`
- the `model_uri` has the format `runs:/{run_id}/{math_to_model_folder}`

#### saving a model
- model logging=saving in a [[m run]] vs save model = saving in the file system
- can be saved in a [[m run]] using the function `mlflow.pyfunc.log_model(artifact_path, python_model=self)`
- can also be saved using APIs for specific libraries e.g. `mlflow.lightgbm.autolog` for logging [[LightGBM]] models
#### example `MLmodel`
```
artifact_path: model
flavors:
  lightgbm:
    code: null
    data: model.lgb
    lgb_version: 4.5.0
    model_class: lightgbm.basic.Booster
  python_function:
    data: model.lgb
    env:
      conda: conda.yaml
      virtualenv: python_env.yaml
    loader_module: mlflow.lightgbm
    python_version: 3.10.11
mlflow_version: 2.16.2
model_size_bytes: 16722
model_uuid: 019fe4c303744ca0ace54ecd6fa109ef
run_id: 7dd549762cf5452d9f322375bc2a4f58
signature:
  inputs: '[{"type": "double", "name": "site", "required": true}, {"type": "double",
 
```