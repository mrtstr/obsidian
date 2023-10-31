## [[py import]]
after a [[py module]] is [[py import|imported]] in [[python]] the [[py interpreter]] will search and execute the [[py module]] 

### search 
#### 1) search in the [[py buildin moduls]]
![[py buildin moduls]]

#### 2) search in the [[py sys.path]]
![[py sys.path#py sys.path]]

### execute the module
- the complete code of the imported [[py module]] in executed but only the first time it was imported
- in case of an import from a [[py package|subpackage]] the code is executed in the following order
	1) `__init__.py` file of the parent [[py package]]
	2) `__init__.py` file of the parent [[py package|subpackage]]
	3) the imported module itself
- everything that was imported or instantiated is avalibale under the namespace where it was imported/instantiated
```
test_package/
    __init__.py
    module.py
    test_subpackage/
        __init__.py
        module2.py
```

```python
from test_package.module_parent import say_by
say_by()

from test_package.test_subpackage.module_sub import say_hi
say_hi()

# test package has been executed
# module2 has been executed
# By!
# test sub package has been executed
# module1 has been executed#
# Hi!
```


# anki

START
Basic
what happens when a [[py module]] is [[py import|imported]] and in which order?
Back: 
after a [[py module]] is [[py import|imported]] in [[python]] the [[py interpreter]] will search and execute the [[py module]] 

### search 
#### 1) search in the [[py buildin moduls]] 
#### 2) search in the [[py sys.path]]
#### [[py sys.path]]
A list of strings that specifies the search path for [[py module|modules]]. 
It is initilized with the following priority
1) The directory containing the input script (or the current directory when no file is specified).
2) `PYTHONPATH`
3) installation-dependent default (by convention including a `site-packages` directory,

After initialization, Python programs can modify `sys.path`. The directory containing the script being run is placed at the beginning of the search path, ahead of the standard library path

### execute the module
- the complete code of the imported [[py module]] in executed but only the first time it was imported
- in case of an import from a [[py package|subpackage]] the code is executed in the following order
	1) `__init__.py` file of the parent [[py package]]
	2) `__init__.py` file of the parent [[py package|subpackage]]
	3) the imported module itself
- everything that was imported or instantiated is avalibale under the namespace where it was imported/instantiated

```
test_package/
    __init__.py
    module.py
    test_subpackage/
        __init__.py
        module2.py
```

```python
from test_package.module_parent import say_by
say_by()

from test_package.test_subpackage.module_sub import say_hi
say_hi()

# test package has been executed
# module2 has been executed
# By!
# test sub package has been executed
# module1 has been executed#
# Hi!
```

Tags: code python
<!--ID: 1698674406738-->
END

START
Basic
where are modules in python searched for and in which priority
Back: 


### search 
#### 1) search in the [[py buildin moduls]]
#### 2) search in the [[py sys.path]] (`sys.builtin_module_names`)
#### [[py sys.path]]
A list of strings that specifies the search path for [[py module|modules]]. 
It is initilized with the following priority
1) The directory containing the input script (or the current directory when no file is specified).
2) `PYTHONPATH`
3) installation-dependent default (by convention including a `site-packages` directory,

After initialization, Python programs can modify `sys.path`. The directory containing the script being run is placed at the beginning of the search path, ahead of the standard library path

Tags: code python
<!--ID: 1698674406742-->
END


START
Basic
What is executed when a [[python]] [[py package|subpackage]] is imported in in which order
Back: 

- the complete code of the imported [[py module]] in executed but only the first time it was imported
- in case of an import from a [[py package|subpackage]] the code is executed in the following order
	1) `__init__.py` file of the parent [[py package]]
	2) `__init__.py` file of the parent [[py package|subpackage]]
	3) the imported module itself
- everything that was imported or instantiated is avalibale under the namespace where it was imported/instantiated

#### example

```
test_package/
    __init__.py
    module.py
    test_subpackage/
        __init__.py
        module2.py
```

```python
from test_package.module_parent import say_by
say_by()

from test_package.test_subpackage.module_sub import say_hi
say_hi()

# test package has been executed
# module2 has been executed
# By!
# test sub package has been executed
# module1 has been executed#
# Hi!
```

Tags: code python
<!--ID: 1698674406747-->
END



START
Basic
given the following example: in which order are the files executed and why?

```
test_package/
    __init__.py
    module.py
    test_subpackage/
        __init__.py
        module2.py
```

```python
from test_package.module_parent import say_by
say_by()

from test_package.test_subpackage.module_sub import say_hi
say_hi()
```

Back: 

```python
from test_package.module_parent import say_by
say_by()

from test_package.test_subpackage.module_sub import say_hi
say_hi()

# test package has been executed
# module2 has been executed
# By!
# test sub package has been executed
# module1 has been executed#
# Hi!
```


- the complete code of the imported [[py module]] in executed but only the first time it was imported
- in case of an import from a [[py package|subpackage]] the code is executed in the following order
	1) `__init__.py` file of the parent [[py package]]
	2) `__init__.py` file of the parent [[py package|subpackage]]
	3) the imported module itself
- everything that was imported or instantiated is avalibale under the namespace where it was imported/instantiated

Tags: code python
<!--ID: 1698674406750-->
END