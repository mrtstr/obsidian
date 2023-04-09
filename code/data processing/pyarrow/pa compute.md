[[pyarrow]] manipulates [[pa Array|pa arrays]] with the functions of `pa.compute`


## example sum of an [[pa Array]]
![[pa Array#example arrays]]

```python
import pyarrow.compute as pc
print(pc.sum(days))
```