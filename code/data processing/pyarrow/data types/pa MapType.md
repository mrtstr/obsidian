![[pa Field#Field]]

## MapType
- [[py dict]] like structure in [[pyarrow]]
- can be created with `pa.map_(key_type, item_type, keys_sorted=False)`
- [[pa datatype]] of a [[pa MapArray]] 
- has two [[pa Field|pa Fields]]: one for the keys and one for the items
### Attributes
```python
item_field # The field for items in the map entries.
item_type # The data type of items in the map entries.
```

## example
```python
my_map_type = pa.map_(pa.string(), pa.int64())
```