`__copy__(self)`

Defines behavior for `copy.copy()` for instances of your class. `copy.copy()` returns a _shallow copy_ of your object -- this means that, while the instance itself is a new instance, all of its data is referenced -- i.e., the object itself is copied, but its data is still referenced (and hence changes to data in a shallow copy may cause changes in the original).

`__deepcopy__(self, memodict={})`

Defines behavior for `copy.deepcopy()` for instances of your class. `copy.deepcopy()` returns a _deep copy_ of your object -- the object _and_ its data are both copied. `memodict` is a cache of previously copied objects -- this optimizes copying and prevents infinite recursion when copying recursive data structures. When you want to deep copy an individual attribute, call `copy.deepcopy()` on that attribute with `memodict` as the first argument.