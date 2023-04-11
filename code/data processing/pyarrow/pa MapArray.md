## MapArray
-  [[pa Array]] containing [[pa MapType]]

![[pa MapType#MapType]]

## Example
```python
data = [[('x', 1), ('y', 0)], [('a', 2), ('b', 45)]]
my_map_type = pa.map_(pa.string(), pa.int64())
my_map_array = pa.array(data, type=my_map_type)
my_map_array
# [
#	keys: [ "x", "y" ] values: [ 1, 0 ], 
#	keys: [ "a", "b" ] values: [ 2, 45 ] 
# ]
```

| | 0 | 
|---:|:----------------------| 
| 0 | [('x', 1), ('y', 0)] | 
| 1 | [('a', 2), ('b', 45)] |



# anki

START
Basic
[[pa MapArray]]
- properties auf [[pa MapType]]
	- attributes (2)
	- how to create it
- example: create a [[pa MapArray]] containing the following two dicts
```python
dict1 = {"x": 1, "y": 0} 
dict2 = {"a": 2, "b": 45} 
```
Back: 
# MapArray
-  [[pa Array]] containing [[pa MapType]]

### MapType
- [[py dict]] like structure in [[pyarrow]]
- can be created with `pa.map_(key_type, item_type, keys_sorted=False)`
- [[pa datatype]] of a [[pa MapArray]] 
- has two [[pa Field|pa Fields]]: one for the keys and one for the items
#### Attributes
```python
item_field # The field for items in the map entries.
item_type # The data type of items in the map entries.
key_field # The field for items in the map keys.
key_type # The data type of items in the map keys.
```

## Example
```python
data = [[('x', 1), ('y', 0)], [('a', 2), ('b', 45)]]
my_map_type = pa.map_(pa.string(), pa.int64())
my_map_array = pa.array(data, type=my_map_type)
my_map_array
# [
#	keys: [ "x", "y" ] values: [ 1, 0 ], 
#	keys: [ "a", "b" ] values: [ 2, 45 ] 
# ]
```

| | 0 | 
|---:|:----------------------| 
| 0 | [('x', 1), ('y', 0)] | 
| 1 | [('a', 2), ('b', 45)] |



Tags: code pyarrow
<!--ID: 1681116775332-->
END