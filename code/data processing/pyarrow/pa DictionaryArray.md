## DictionaryArray (categorical data)
- [[pa Array]] that hold categorical data (similar to [[pd categorical data]])

#### Attributes
```python
dictionary # StringArray that contains unique categories
indices    # IntArray maps positions in Array to dictionary elements
nbytes    # Total number of bytes consumed by the elements of the array.
type       # tyoe of the dictionary elements
null_count # number of null values in indices
offset     # A relative position into another array's data.
```
#### Methods

## example
```python
field(i) # Select a field by its column name or numeric index.
```

```python
indices = pa.array([0, 1, 0, 1, 2, 0, None, 2])
dictionary = pa.array(['foo', 'bar', 'baz'])
dict_array = pa.DictionaryArray.from_arrays(indices, dictionary)
# <pyarrow.lib.DictionaryArray object at 0x7f4364ff35a0> 
# -- dictionary: [ "foo", "bar", "baz" ] 
# -- indices: [ 0, 1, 0, 1, 2, 0, null, 2 ]
```

| | 0 | 
|---:|:----| 
| 0 | foo | 
| 1 | bar | 
| 2 | foo | 
| 3 | bar | 
| 4 | baz | 
| 5 | foo | 
| 6 | null | 
| 7 | baz |


# anki

START
Basic
[[pa DictionaryArray]]
- concept and diffence to [[pa MapArray]]
- attributes (6)
- example: create a [[pa DictionaryArray]] contraining the data in the following list
```python
datalist = ['foo', 'bar', 'foo', 'bar', 'baz', 'foo', None, 'baz']
```
Back: 
## [[pa DictionaryArray]] (categorical data)
- [[pa Array]] that hold categorical data (similar to [[pd categorical data]])

#### Attributes
```python
dictionary # StringArray that contains unique categories
indices    # IntArray maps positions in Array to dictionary elements
nbytes    # Total number of bytes consumed by the elements of the array.
type       # tyoe of the dictionary elements
null_count # number of null values in indices
offset     # A relative position into another array's data.
```

## example


```python
indices = pa.array([0, 1, 0, 1, 2, 0, None, 2])
dictionary = pa.array(['foo', 'bar', 'baz'])
dict_array = pa.DictionaryArray.from_arrays(indices, dictionary)
# <pyarrow.lib.DictionaryArray object at 0x7f4364ff35a0> 
# -- dictionary: [ "foo", "bar", "baz" ] 
# -- indices: [ 0, 1, 0, 1, 2, 0, null, 2 ]
```

| | 0 | 
|---:|:----| 
| 0 | foo | 
| 1 | bar | 
| 2 | foo | 
| 3 | bar | 
| 4 | baz | 
| 5 | foo | 
| 6 | null | 
| 7 | baz |


Tags: code pyarrow
<!--ID: 1681116775338-->
END