- Valiables set by and used by the [[py interpreter]]
- [[py object]], [[py function]], [[py class]], [[py module]] all have different [[py dunder valiables]] defined decribing its properties

#### [[py class]]:
![[py class#py dunder valiables py class]]


#### [[py function]]

![[py function#py dunder valiables py function]]


#### [[py module]]
![[py module#py dunder valiables py module]]


# Anki
START
Basic
[[py dunder valiables]]
- definition
- 3 examples and what they do
Back: 
### [[py dunder valiables]] [[py object]]
-   `__class__`: stores the [[py class]] of the [[py object]] 
-   `__dict__`: stores the attributes of the [[py object]]
- plus [[py dunder valiables]] [[py object]]

## [[py dunder valiables]] [[py class]]
- `__name__`: stores the name of the [[py class]]
-   `__module__`: stores the name of the [[py module]] they were defined in within
-   `__bases__`: stores their base classes
- -   `__mro__`: stores their method resolution order (see [[py inheritance]])
- plus [[py dunder valiables]] [[py object]]

### [[py dunder valiables]] [[py function]]
- `__name__`: stores the name of the [[py function]]
-   `__module__`: stores the name of the module they were defined in within
-   `__defaults__` and `__kwdefaults__`: store their default argument values
- plus [[py dunder valiables]] [[py object]]

## [[py dunder valiables]] [[py module]]
- `__name__`: stores the name of the [[py module]]
-   `__file__`: the file this module was loaded from (though some modules are missing this)
- plus [[py dunder valiables]] [[py object]]

Tags: code python
<!--ID: 1698674406761-->
END

START
Basic
what is saved under the following [[py dunder valiables]]?

-   `__class__`
-   `__dict__`
- `__name__`
-   `__module__`
-   `__bases__`
- `__mro__`

Back: 
-   `__class__`: stores the [[py class]] of the [[py object]] 
-   `__dict__`: stores the attributes of the [[py object]] / scope
- `__name__`: stores the name of the [[py class]] / [[py function]] / [[py module]]...
-   `__module__`: stores the name of the [[py module]] they were defined in within
-   `__bases__`: stores their base [[py class]] of a [[py class]]
- `__mro__`: stores their method resolution order (see [[py inheritance]])

Tags: code python
<!--ID: 1698674406766-->
END