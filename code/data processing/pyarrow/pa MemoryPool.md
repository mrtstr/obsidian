Base class for memory allocation.

Besides tracking its number of allocated bytes, a memory pool also takes care of the required 64-byte alignment for [[pyarrow]] data.