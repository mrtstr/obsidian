[[pandas]] [[pd dataframe]] can be broadcasted to a multiindex with [[pd dataframe|DataFrame]].reindex([[pd multiindex|MultiIndex]])

```python
df0
#               0         1
# one  y  1.519970 -0.493662
#      x  0.600178  0.274230
# zero y  0.132885 -0.023688
#      x  2.410179  1.450520

df = df0.groupby(level=0).mean()
df
#              0         1
# one   1.060074 -0.109716
# zero  1.271532  0.713416

df.reindex(df0.index, level=0)
df
#                0         1
# one  y  1.060074 -0.109716
#      x  1.060074 -0.109716
# zero y  1.271532  0.713416
#      x  1.271532  0.713416
```





