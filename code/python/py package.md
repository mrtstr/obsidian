## packages

- packages are a special kind of [[py module]]
- any [[py module]] that contains a `__path__` attribute is a [[py package]] and contains a [[py list]] with the path to the directory of the [[py package]]
- Subpackage names are separated from their parent package name by a dot
- there are two types of packages


![[py module#modules definition]]


### Regular packages
- directory containing an `__init__.py` file
- When a regular package is imported, this `__init__.py` file is implicitly executed, 
- objects it defines are bound to names in the package’s namespace

```
parent/
    __init__.py
    one/
        __init__.py
    two/
        __init__.py
    three/
        __init__.py
```


### Namespace packages
Namespace packages allow you to split the sub-packages and modules within a single 
[[py package]] across multiple, separate distribution packages


# anki

START
Basic
- what is the diffeence between a [[py package]] and a [[py module]]?
- two different types of [[py package]]

Back: 

### modules definition
- hirachical name space with [[py function]], [[py class]] or [[py object]] in it that can be accessed by `module_name.object_name`
- has a name saved in the [[py special valiables]] `__name__` containing the [[py module]] name as a [[py string]]
- file with the suffix `py.` containing [[python]] code or a directory

### packages
- packages are a special kind of [[py module]]
- any [[py module]] that contains a `__path__` attribute is a [[py package]] and contains a [[py list]] with the path to the directory of the [[py package]]t

#### Regular packages
- directory containing an `__init__.py` file
- When a regular package is imported, this `__init__.py` file is implicitly executed, 
- objects it defines are bound to names in the package’s namespace

```
parent/
    __init__.py
    one/
        __init__.py
    two/
        __init__.py
    three/
        __init__.py
```

#### Namespace packages
Namespace packages allow you to split the sub-packages and modules within a single 
[[py package]] across multiple, separate distribution packages

Tags: code python
<!--ID: 1698674406735-->
END