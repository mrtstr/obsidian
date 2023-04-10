## Schema
- A [[pa Schema]] is a collection of named [[pa Field|pa Fields]]
![[pa Field]]
- each [[pa Field]] holding additional information of a [[pa Array]] and both togather are a column
- similar to a [[pa StructType]]

```python
fields = [
	pa.field('id', pa.int32()),
	pa.field('first_name', pa.string()),
	pa.field('last_name', pa.string()),
]
schema1 = pa.schema(fields)
schema1 = pa.schema(    # shorter
   [
	   ('id', pa.int32()), 
	   ('first_name', pa.string()), 
	   ('last_name', pa.string()), ('s3', pa.string())
   ]
)
```

# anki

START
Basic
- [[pa Schema]] and relationship to [[pa Field]]
- example: create a [[pa Schema]] for a [[pa RecordBatch]] containing the id, the first and last name of persons
Back: 
# Schema
- A [[pa Schema]] is a collection of named [[pa Field|pa Fields]]

## Field
- defines a placeholder for data
- [[pa Field]] holds [[pa datatype]] and additional properties of values
- in addtion to a [[pa datatype]]
```python
name      # name of column
nullable  # nullable or not
type      # datatype
```
- each [[pa Field]] holding additional information of a [[pa Array]] and both togather are a column
- similar to a [[pa StructType]]

## example
```python
fields = [
	pa.field('id', pa.int32()),
	pa.field('first_name', pa.string()),
	pa.field('last_name', pa.string()),
]
schema1 = pa.schema(fields)
schema1 = pa.schema(    # shorter
   [
	   ('id', pa.int32()), 
	   ('first_name', pa.string()), 
	   ('last_name', pa.string()), ('s3', pa.string())
   ]
)
```

Tags: code pyarrow
<!--ID: 1681116775350-->
END