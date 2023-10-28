[[pd dataframe|DataFrame]].reindex_like()
[[pd dataframe|DataFrame]].reindex()

Set a new [[pd index]] to a [[pd dataframe]] and fill up after given rule

# anki

START
Basic
pandas dataframe:
how to broadcast a [[pandas]] [[pd dataframe]] to a new [[pd index]]
Back: 
[[pd dataframe|DataFrame]].reindex_like()
[[pd dataframe|DataFrame]].reindex()
Tags: code pandas
<!--ID: 1668090818847-->
END


START
Basic
pandas dataframe:
[[pd dataframe|DataFrame]].reindex_like()
[[pd dataframe|DataFrame]].reindex()
- concept and modes
Back: 
Conform the object to the same index on all axes. Optional filling logic, placing NaN in locations having no value in the previous index
fill methods:
-   None (default): don’t fill gaps
-   pad / ffill: propagate last valid observation forward to next val
-   backfill / bfill: use next valid observation to fill gap
-   nearest: use nearest valid observations to fill gap.
Tags: code pandas
<!--ID: 1668090818849-->
END