[[pyarrow]] manipulates [[pa array|pa arrays]] with the functions of `pa.compute`


## example sum of an [[pa array]]
![[pa array#example arrays]]

```python
import pyarrow.compute as pc
print(pc.sum(days))
```