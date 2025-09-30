### workspace
- a [[r workspace]] in [[rust]] is a group of multiple [[r package|packages]] that share a `Cargo.toml` file a `target` folder
- it can be used for sharing dependencies and metadata

example:
```toml
[workspace]
members = [
	"cli_example",
	"wrapped_example_rs"
]
# Optional: prevent Cargo from searching for crates in other folders
exclude = [
	"pysrc", # your Python code
	"*.ipynb", # notebooks
]
# (optional) you can set shared dependencies if needed
[workspace.dependencies]
anyhow = "1.0"
polars = "0.39"

# (optional) shared metadata: can be inherented by the packages
# if <parameter>.workspace = true is set
[workspace.package]
version = "0.1.0"
edition = "2021"
authors = ["M S <ms@example.com>"]
```