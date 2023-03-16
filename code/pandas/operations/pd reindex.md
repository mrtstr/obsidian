[[pd DataFrame|DataFrame]].reindex_like()
[[pd DataFrame|DataFrame]].reindex()

Set a new [[pd Index]] to a [[pd DataFrame]] and fill up after given rule

# anki

START
Basic
pandas dataframe:
how to broadcast a [[pandas]] [[pd DataFrame]] to a new [[pd Index]]
Back: 
[[pd DataFrame|DataFrame]].reindex_like()
[[pd DataFrame|DataFrame]].reindex()
Tags: code, pandas
<!--ID: 1668090818847-->
END


START
Basic
pandas dataframe:
[[pd DataFrame|DataFrame]].reindex_like()
[[pd DataFrame|DataFrame]].reindex()
- concept and modes
Back: 
Conform the object to the same index on all axes. Optional filling logic, placing NaN in locations having no value in the previous index
fill methods:
-   None (default): don’t fill gaps
-   pad / ffill: propagate last valid observation forward to next val
-   backfill / bfill: use next valid observation to fill gap
-   nearest: use nearest valid observations to fill gap.
Tags: code, pandas
<!--ID: 1668090818849-->
END