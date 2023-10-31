### [[py object]] definition
- in [[python]] all [[py function]], [[py module]], [[py class]]... are [[py object|objects]]
- all [[py object]] inherent from a [[py base object]] called `object`
### [[py dunder valiables]] [[py object]]
-   `__class__`: stores the [[py class]] of the [[py object]] (metaclass [[py type]] if it's a [[py class]] itself)
-   `__dict__`: stores the attributes of the [[py object]]

### [[py dunder valiables]] [[py object]] example
```
my_mutable_container.__class__=<
	class 'test_package.test_subpackage.module_sub.MutableContainer'
>

my_mutable_container.__dict__={'values': [11, 22, 33]}
```


![[py container objects#example mutable py container objects]]


# Anki
START
Basic
[[py object]]
- definition
- [[py dunder valiables]] (2)
Back: 
### [[py object]] definition
- in [[python]] all [[py function]], [[py module]], [[py class]]... are [[py object|objects]]
- all [[py object]] inherent from a [[py base object]] called `object`
### [[py dunder valiables]] [[py object]]
-   `__class__`: stores the [[py class]] of the [[py object]] (metaclass [[py type]] if it's a [[py class]] itself)
-   `__dict__`: stores the attributes of the [[py object]]

Tags: code python
<!--ID: 1698748522693-->
END