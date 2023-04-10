## StructArray
- [[pa Array]] containing [[pa StructType]] 

![[pa StructType#StructType]]

## example
```python
fields = [
	pa.field('id', pa.int32()),
	pa.field('first_name', pa.string()),
	pa.field('last_name', pa.string()),
]
person_struct = pa.struct(fields)

data = [
	{'id':1,'first_name':"hans", 'last_name':"muller"},
	{'id':2,'first_name':"lisa", 'last_name':"maier"},
]

person_struct_array = pa.array(data, type=person_struct)
#-- child 0 type: int32 [ 1, 2 ] 
#-- child 1 type: string [ "hans", "lisa" ] 
#-- child 2 type: string [ "muller", "maier" ]
```

| | 0 | 
|---:|:-------------------------------------------------------| 
| 0 | {'id': 1, 'first_name': 'hans', 'last_name': 'muller'} | 
| 1 | {'id': 2, 'first_name': 'lisa', 'last_name': 'maier'} |


# anki

START
Basic
[[pa StructArray]]
- concept
- [[pa StructType]]
- example: create a [[pa StructArray]] contraining the following persons:
		1) ID: 1 first_name: hans, last_name: muller
	2) ID: 2 first_name: lisa, last_name: maier
Back: 
# StructArray
- [[pa Array]] containing [[pa StructType]] 

### StructType
- [[pa datatype]] of a StructArray
- A [[pa StructType]] is a collection of named [[pa Field|pa Fields]]
- similar to the [[pa Schema]] of a [[pa Table]]

#### Attributes
```python
num_fields # The field for items in the map entries.
```
#### Methods
```python
field(i) # Select a field by its column name or numeric index.
```

## example
```python
fields = [
	pa.field('id', pa.int32()),
	pa.field('first_name', pa.string()),
	pa.field('last_name', pa.string()),
]
person_struct = pa.struct(fields)

data = [
	{'id':1,'first_name':"hans", 'last_name':"muller"},
	{'id':2,'first_name':"lisa", 'last_name':"maier"},
]

person_struct_array = pa.array(data, type=person_struct)
#-- child 0 type: int32 [ 1, 2 ] 
#-- child 1 type: string [ "hans", "lisa" ] 
#-- child 2 type: string [ "muller", "maier" ]
```

| | 0 | 
|---:|:-------------------------------------------------------| 
| 0 | {'id': 1, 'first_name': 'hans', 'last_name': 'muller'} | 
| 1 | {'id': 2, 'first_name': 'lisa', 'last_name': 'maier'} |




Tags: code pyarrow
<!--ID: 1681116775343-->
END