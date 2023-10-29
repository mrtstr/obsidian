## how to use [[py asterisks]] in [[python]]
### to collect an arbitrary number of input values in a [[py list]]

```python
a, *bcd, e = "a", "b", "c", "d", "e"

print(f"{a=} {bcd=} {e=}")

# a='a' bcd=['b', 'c', 'd'] e='e'
```


### to pass a not fixed number of named and unnamed parameters to a [[py callable object]] that will be collected as a [[py list]] and [[py dict]]

```python
def func(
	name,
	*args,
	**kwargs
):
	print(name)
	print(args)
	print(kwargs)

func("bob", "fu", "bar", arg1= "baz")
# name='bob' 
# args=('fu', 'bar') 
# kwargs={'arg1': 'baz'}

func("bob", "fu", "bar", arg1= "baz")
func(*list_input)
# name='bob' 
# args=('fu', 'bar', 'baz') 
# kwargs={}

dict_input = {
	"name":"bob",
	"arg1": "fu",
	"arg2":"bar",
	"arg3":"baz"
}
func(**dict_input)
# name='bob' 
# args=() 
# kwargs={'arg1': 'fu', 'arg2': 'bar', 'arg3': 'baz'}
```

### to expand a [[py list]] or a [[py dict]] to pass values to a function 
```python
func("bob", "fu", "bar", arg1= "baz")
func(*list_input)
# name='bob' 
# args=('fu', 'bar', 'baz') 
# kwargs={}

dict_input = {
	"name":"bob",
	"arg1": "fu",
	"arg2":"bar",
	"arg3":"baz"
}
func(**dict_input)
# name='bob' 
# args=() 
# kwargs={'arg1': 'fu', 'arg2': 'bar', 'arg3': 'baz'}
```


# anki

START
Basic
how to use [[py asterisks]] in [[python]] (3)
Back: 

### to collect an arbitrary number of input values in a [[py list]]

```python
a, *bcd, e = "a", "b", "c", "d", "e"

print(f"{a=} {bcd=} {e=}")

# a='a' bcd=['b', 'c', 'd'] e='e'
```

### to pass a not fixed number of named and unnamed parameters to a [[py callable object]] that will be collected as a [[py list]] and [[py dict]]

```python
def func(
	name,
	*args,
	**kwargs
):
	print(name)
	print(args)
	print(kwargs)

func("bob", "fu", "bar", arg1= "baz")
# name='bob' 
# args=('fu', 'bar') 
# kwargs={'arg1': 'baz'}

func("bob", "fu", "bar", arg1= "baz")
func(*list_input)
# name='bob' 
# args=('fu', 'bar', 'baz') 
# kwargs={}

dict_input = {
	"name":"bob",
	"arg1": "fu",
	"arg2":"bar",
	"arg3":"baz"
}
func(**dict_input)
# name='bob' 
# args=() 
# kwargs={'arg1': 'fu', 'arg2': 'bar', 'arg3': 'baz'}
```

### to expand a [[py list]] or a [[py dict]] to pass values to a function 

```python
func("bob", "fu", "bar", arg1= "baz")
func(*list_input)
# name='bob' 
# args=('fu', 'bar', 'baz') 
# kwargs={}

dict_input = {
	"name":"bob",
	"arg1": "fu",
	"arg2":"bar",
	"arg3":"baz"
}
func(**dict_input)
# name='bob' 
# args=() 
# kwargs={'arg1': 'fu', 'arg2': 'bar', 'arg3': 'baz'}
```

Tags: code python
<!--ID: 1698577730911-->
END