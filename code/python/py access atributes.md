
### access in scope attributes 
-   `dir()` will give you the list of in-scope variables
-   `globals()` will give you a dictionary of global variables
-   `locals()` will give you a dictionary of local variables

### access attributes of an [[py object]]
- the [[py buidin functions]] `vars(<object, function or module>)` will return all attributes (data or [[py function]]) of the given [[py object]], [[py class]] or [[py module]] as a [[py dict]]
- this behanvour is implemented in the [[py object]] [[py magic method]] `__dict__`
- if `vars()` is called without arguments it will call if of the current [[py object]], [[py class]] or [[py module]] itself depending on where it is called from which is the same as calling `locals`


# anki

START
Basic
[[python]] from to access
- in scope valiables
- globals valiables
- local valiables
- variables of an object
Back: 
### access in scope attributes 
-   `dir()` will give you the list of in-scope variables
-   `globals()` will give you a dictionary of global variables
-   `locals()` will give you a dictionary of local variables

### access attributes of an [[py object]]
- the [[py buidin functions]] `vars(<object, function or module>)` will return all attributes (data or [[py function]]) of the given [[py object]], [[py class]] or [[py module]] as a [[py dict]]
- this behanvour is implemented in the [[py object]] [[py magic method]] `__dict__`
- if `vars()` is called without arguments it will call if of the current [[py object]], [[py class]] or [[py module]] itself depending on where it is called from which is the same as calling `locals()`


Tags: code python
<!--ID: 1698674406754-->
END

START
Basic
what are the [[py buidin functions]] `dir()` and `locals()` do?
what is the difference between `locals()` and `vars()`?
what does the [[py magic method]] `__dict__()` do?
Back: 
if `vars()` is called without arguments it will call if of the current [[py object]], [[py class]] or [[py module]] itself depending on where it is called from which is the same as calling `locals()` but vars can be called on any other [[py object]]

### access in scope attributes 
-   `dir()` will give you the list of in-scope variables
-   `globals()` will give you a dictionary of global variables
-   `locals()` will give you a dictionary of local variables

### access attributes of an [[py object]]
- the [[py buidin functions]] `vars(<object, function or module>)` will return all attributes (data or [[py function]]) of the given [[py object]], [[py class]] or [[py module]] as a [[py dict]]
- this behanvour is implemented in the [[py object]] [[py magic method]] `__dict__`
Tags: code python
<!--ID: 1698674406757-->
END