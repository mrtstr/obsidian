## concept
- library providing columnar data structures for in-memory computing
- can handle large datasets by partitioning of data in smaller chunks
- base data representation of [[polars]] and [[pandas]] 2.0
- Arrow can be used with [[parquet]], [[pandas]], [[polars]], [[pyspark]]
![[Screenshot from 2023-04-09 20-11-37.png]]

## datastructures
[[pa Field]]
- placeholder for data: holds [[pa datatype]] and additional properties of values 
[[pa Schema]]: 
- collection of named [[pa Field|pa Fields]]
- defines structure of a [[pa RecordBatch]], [[pa Table]], [[pa RecordBatchReader]]
[[pa Array]]
- immutable collection of data of the same [[pa datatype]]
[[pa RecordBatch]]
- collection of [[pa Array]] of the same length with a [[pa Schema]]
[[pa Table]]
- same properties as a [[pa RecordBatch]] but can contrain one or multiple [[pa RecordBatch|pa RecordBatchs]] of the same [[pa Schema]] that are logicly treated as one
# anki

START
Basic
[[pyarrow]]
- conecpt (4)
Back: 
## concept
- library providing columnar data structures for in-memory computing
- can handle large datasets by partitioning of data in smaller chunks
- base data representation of [[polars]] and [[pandas]] 2.0
- Arrow can be used with [[parquet]], [[pandas]], [[polars]], [[pyspark]]

![[Screenshot from 2023-04-09 20-11-37.png]]

Tags: code pyarrow
<!--ID: 1681037725709-->
END