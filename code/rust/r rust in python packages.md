## rust in python packages
- its possible to include [[rust]] code in [[python]] packages (wheels) using PyO3 and maturin
- [[python]] can **dynamically loads** **CPython extension modules** from `cdylib` files ([[r library crates#dylib / cdylib]]) under the following conditions  
	- are compiled with the **C ABI** and the **CPython C-API**
	- export an init symbol **`PyInit_<module_name>`**
	- have a filename and location that match the **import path**
	- are on `sys.path` (typically inside **site-packages** or a wheel).
→ `.so` file created by maturin can be added to the site-package folder of the python venv and can be imported as a normal python module
### PyO3
- compiles [[rust]] code into binary's that can be interpreted as python modules by python
- makes it possible to call python from inside rust (embedded in CPython) e.g. manage the GIL
- converts python types to rust types and vise versa 
	- `Vec<T>` ↔ list
	- `HashMap` ↔ dict 
	- `Option` ↔ `None`
	- `Result` ↔ exceptions
- exposes rust APIs to python
	- `#[pyfunction]` to export functions
	- `#[pyclass]`/`#[pymethods]` to export classes & methods
	- `#[pymodule]` to define the module initializer
	- Raise Python exceptions with `PyErr`

### maturin
- build backend for hybrid python and rust packages 
- creates 
	- [[py wheel]] containing the python code and the compiles `.so` files (no compilation and tool chain needed during installation)
	- [[py sdist]] containing metadata (`pyproject.toml` and `Cargo.toml`) the python and rust source code → needs the complete rust toolchain to install
- has a `Cargo.toml` and `pyproject.toml` that contain the environments in the respective language and the maturin settings
- compiles the rust code into a `cdylib` (see [[r library crates#dylib / cdylib]]) - a shared library intended to be loaded by _non-Rust_ hosts → `.so` file that python can interpret as a python module

# anki

START
Basic
[[r rust in python packages]]
- how does it work in general (how to make python use binarys?)
- two tools that are needed and what they are doing

Back: 

## rust in python packages
- its possible to include [[rust]] code in [[python]] packages (wheels) using PyO3 and maturin
- [[python]] can **dynamically loads** **CPython extension modules** from `cdylib` files ([[r library crates#dylib / cdylib]]) under the following conditions  
	- are compiled with the **C ABI** and the **CPython C-API**
	- export an init symbol **`PyInit_<module_name>`**
	- have a filename and location that match the **import path**
	- are on `sys.path` (typically inside **site-packages** or a wheel).
→ `.so` file created by maturin can be added to the site-package folder of the python venv and can be imported as a normal python module
### PyO3
- compiles [[rust]] code into binary's that can be interpreted as python modules by python
- makes it possible to call python from inside rust (embedded in CPython) e.g. manage the GIL
- converts python types to rust types and vise versa 
	- `Vec<T>` ↔ list
	- `HashMap` ↔ dict 
	- `Option` ↔ `None`
	- `Result` ↔ exceptions
- exposes rust APIs to python
	- `#[pyfunction]` to export functions
	- `#[pyclass]`/`#[pymethods]` to export classes & methods
	- `#[pymodule]` to define the module initializer
	- Raise Python exceptions with `PyErr`

### maturin
- build backend for hybrid python and rust packages 
- creates 
	- [[py wheel]] containing the python code and the compiles `.so` files (no compilation and tool chain needed during installation)
	- [[py sdist]] containing metadata (`pyproject.toml` and `Cargo.toml`) the python and rust source code → needs the complete rust toolchain to install
- has a `Cargo.toml` and `pyproject.toml` that contain the environments in the respective language and the maturin settings
- compiles the rust code into a `cdylib` (see [[r library crates#dylib / cdylib]]) - a shared library intended to be loaded by _non-Rust_ hosts → `.so` file that python can interpret as a python module


______________________

## rust library crates
- way to expose compiled code to other **programs or crates**.
- generated during the [[compiler#code generation]] and**not executable** themselves
- inputs to the [[compiler#linking]] process (dynamic or static) and for dynamic libs loaded at runtime
- **ABI** = how functions/data look at the binary boundary (calling convention, name mangling, layout…).
    
### lib / rlib
- Intermediate/static artifact produced by the [[r compiler]] and for the [[r compiler]]
- for static [[compiler#linking]]
- `*.rlib` (Rust static artifact) file

### dylib / cdylib
- library for dynamic [[compiler#linking]] can be used as interface to other languages
-  files types depend on the operating system
	- `.so` for [[linux]]
	- `.dylib` for macOS 
	- `.dll` for window
- available in two different ABIs
	- `dylib`: uses **Rust ABI** (unstable and rare)
	-  `cdylib`: uses **C-ABI** = the stable, widely supported ABI used by C. Most languages (Python, Ruby, Java via JNI, etc.) can interop with it.


### staticlib
- **Static** C-ABI library (`.a`/`.lib`)
- Final archive of object files linked **at build time** into a host program
- **Consumer:** Non-Rust linkers (C/C++/Swift, etc.).


Tags: code rust
END