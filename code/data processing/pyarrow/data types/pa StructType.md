![[pa Field#Field]]

## StructType
- [[pa datatype]] of a StructArray
- A [[pa StructType]] is a collection of named [[pa Field|pa Fields]]
- similar to the [[pa Schema]] of a [[pa Table]]

### Attributes
```python
num_fields # The field for items in the map entries.
```
### Methods

```python
field(i) # Select a field by its column name or numeric index.
```



## Example

```python
fields = [
	pa.field('id', pa.int32()),
	pa.field('first_name', pa.string()),
	pa.field('last_name', pa.string()),
]
my_struct1 = pa.struct(fields)
my_struct2 = pa.struct(    # shorter
   [
	   ('id', pa.int32()), 
	   ('first_name', pa.string()), 
	   ('last_name', pa.string()), ('s3', pa.string())
   ]
)
```