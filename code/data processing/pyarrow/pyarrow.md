## concept
- library providing columnar data structures for in-memory computing
- optimizes for [[memory mapped data]] and [[zero copy]] operations
- base data representation of [[polars]] and [[pandas]] 2.0
- Arrow can be used with [[parquet]], [[pandas]], [[polars]], [[pyspark]]
![[Screenshot from 2023-04-09 20-11-37.png]]


Basically, a Table in PyArrow/Arrow C++ isn't really the data itself, but rather a container consisting of pointers to data. How it works is:




-   A Table contains 0+ ChunkedArrays. A Table is a 2D data structure (both columns and rows).
-   A RecordBatch contains 0+ Arrays. A RecordBatch is also a 2D data structure.

Hence, you can concantenate two Tables "zero copy" with `pyarrow.concat_tables`, by just copying pointers. But you cannot concatenate two RecordBatches "zero copy", because you have to concatenate the Arrays, and then you have to copy data out of buffers.


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
- optimizes for [[memory mapped data]] and [[zero copy]] operations
- base data representation of [[polars]] and [[pandas]] 2.0
- Arrow can be used with [[parquet]], [[pandas]], [[polars]], [[pyspark]]

![[Screenshot from 2023-04-09 20-11-37.png]]

Tags: code pyarrow
<!--ID: 1681037725709-->
END