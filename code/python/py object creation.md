## [[py type]] for object creation
- when a [[py class]] is instanciated the [[py interpreter]] will call the `__call__` [[py dunder method]] of the [[py class]] parent
- 





The expression `Foo()` creates a new instance of class `Foo`. When the interpreter encounters `Foo()`, the following occurs:

-   The `__call__()` method of `Foo`’s parent class is called. Since `Foo` is a standard new-style class, its parent class is the `type` metaclass, so `type`’s `__call__()` method is invoked.
    
-   That `__call__()` method in turn invokes the following:
    
    -   `__new__()`
    -   `__init__()`

## [[py object creation]]
### [[py object creation]] [[py dunder method]]
#### `__new__(cls, ...)`
- first method called in [[py object creation]]
- recives a reference to the [[py class]] (`cls`) plus all the arguments passed during the object creation call
#### `__init__(self, ...)`
- first method that is called after the [[py object]] is instanciated 
- recives a reference to the instance ([[py object]]) itself (`self`) plus all the arguments passed during the object creation call
#### `__del__(self)`
- destructor that is called when object is deleted 



# rest
`__new__(cls, [...)` is the first method to get called in an object's instantiation. It takes the class, then any other arguments that it will pass along to `__init__`. `__new__` is used fairly rarely, but it does have its purposes, particularly when subclassing an immutable type like a tuple or a string. I don't want to go in to too much detail on `__new__` because it's not too useful, but it is covered in great detail [in the Python docs](http://www.python.org/download/releases/2.2/descrintro/#__new__).



`__init__(self, [...)`

The initializer for the class. It gets passed whatever the primary constructor was called with (so, for example, if we called `x = SomeClass(10, 'foo')`, `__init__` would get passed `10` and `'foo'` as arguments. `__init__` is almost universally used in Python class definitions.

`__del__(self)`

If `__new__` and `__init__` formed the constructor of the object, `__del__` is the destructor. It doesn't implement behavior for the statement `del x` (so that code would not translate to `x.__del__()`). Rather, it defines behavior for when an object is garbage collected. It can be quite useful for objects that might require extra cleanup upon deletion, like sockets or file objects. Be careful, however, as there is no guarantee that `__del__` will be executed if the object is still alive when the interpreter exits, so `__del__` can't serve as a replacement for good coding practices (like always closing a connection when you're done with it. In fact, `__del__` should almost never be used because of the precarious circumstances under which it is called; use it with caution!
