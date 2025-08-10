### steam process
- given a large partitioned [[parquet]] [[pa Dataset]] that should be processed
- there are 3 options: 
	- polars streaming if the full result fits in the memory
	- fragment processing if the single files of the dataset fit in the memory
	- batch processing if even single files need to be split up
#### polars streaming
- [[polars]] scans the dataset and processes with streaming but gathers the result in the [[li memory]]
- streaming only works of the operations allow it

```python
lf = (pl.scan_parquet("s3://bucket/ds/", storage_options=opts)
        .filter(pl.col("dt") >= pl.date(2025,1,1))
        .with_columns((pl.col("a")+1).alias("a2"))
        .select(["dt","a2","k"])
     )
# streaming compute; then hand off to pyarrow write_dataset if you need partitioning
df_streamed = lf.collect(streaming=True)
fs.write_to_dataset(dst_path, df_streamed, partition_by=["dt"])
```

- if the data does not fit in the [[li memory]] its possible to sink it directly in a file instead of collection it
- downside: [[polars]] can't write a partitioned parquet

```python
# Stream to a single S3 object
fs = fsspec.filesystem("s3", **storage_options)
with fs.open("s3://bucket/outputs/result.parquet", "wb") as f:
    lf.sink_parquet(f, compression="zstd", statistics=True)
```
#### fragment processing
- process fragment by fragment
- ds.Fragment = logical chunk of the dataset often eqivalent to a parquet file
- Start with **fragment-wise** if files/partitions fit in RAM (simpler, fewer small files).

```python
pa_fs, base_dir = fs._dataset_base_dir_and_fs(src_path)
dataset = ds.dataset(base_dir, filesystem=pa_fs, format="parquet")

def work(frag: ds.Fragment) -> int:
    # stream by batches if needed (see #2), or whole fragment if small enough
    tbl = frag.to_table()
    out = transform(pl.from_arrow(tbl))
    fs.write_to_dataset(dst_path, out, partition_by=["year","month"])
    return out.height

with ThreadPoolExecutor(max_workers=8) as ex:
    list(ex.map(work, dataset.get_fragments()))
fs.write_common_metadata(dst_path)
```
#### batch processing
- process batch by batch
- batch = **in-memory representation of a subset of rows from a fragment**
- can be broken down when max batch size is set
- Switch to **batch streaming** when fragments are too large or you need tight memory bounds.

```python
scanner = ds.Scanner.from_dataset(
    dataset,
    columns=needed_cols,                 # project early
    filter=ds.field("dt") >= "2025-01-01",  # pushdown filter
    batch_size=256_000                    # tune for memory
)
for batch in scanner.to_batches():
    df = transform(pl.from_arrow(batch))
    fs.write_to_dataset(dst_path, df, partition_by=part_cols, existing_data_behavior="overwrite_or_ignore")
fs.write_common_metadata(dst_path)
```

# anki

START
Basic
- given a large partitioned [[parquet]] [[pa Dataset]] that should be processed
- 3 ways on how to do it and when to use it

Back: 
### steam process
- given a large partitioned [[parquet]] [[pa Dataset]] that should be processed
- there are 3 options: 
	- polars streaming if the full result fits in the memory
	- fragment processing if the single files of the dataset fit in the memory
	- batch processing if even single files need to be split up
#### polars streaming
- [[polars]] scans the dataset and processes with streaming but gathers the result in the [[li memory]]
- streaming only works of the operations allow it

```python
lf = (pl.scan_parquet("s3://bucket/ds/", storage_options=opts)
        .filter(pl.col("dt") >= pl.date(2025,1,1))
        .with_columns((pl.col("a")+1).alias("a2"))
        .select(["dt","a2","k"])
     )
# streaming compute; then hand off to pyarrow write_dataset if you need partitioning
df_streamed = lf.collect(streaming=True)
fs.write_to_dataset(dst_path, df_streamed, partition_by=["dt"])
```

- if the data does not fit in the [[li memory]] its possible to sink it directly in a file instead of collection it
- downside: [[polars]] can't write a partitioned parquet

```python
# Stream to a single S3 object
fs = fsspec.filesystem("s3", **storage_options)
with fs.open("s3://bucket/outputs/result.parquet", "wb") as f:
    lf.sink_parquet(f, compression="zstd", statistics=True)
```
#### fragment processing
- process fragment by fragment
- ds.Fragment = logical chunk of the dataset often eqivalent to a parquet file
- Start with **fragment-wise** if files/partitions fit in RAM (simpler, fewer small files).

```python
pa_fs, base_dir = fs._dataset_base_dir_and_fs(src_path)
dataset = ds.dataset(base_dir, filesystem=pa_fs, format="parquet")

def work(frag: ds.Fragment) -> int:
    # stream by batches if needed (see #2), or whole fragment if small enough
    tbl = frag.to_table()
    out = transform(pl.from_arrow(tbl))
    fs.write_to_dataset(dst_path, out, partition_by=["year","month"])
    return out.height

with ThreadPoolExecutor(max_workers=8) as ex:
    list(ex.map(work, dataset.get_fragments()))
fs.write_common_metadata(dst_path)
```
#### batch processing
- process batch by batch
- batch = **in-memory representation of a subset of rows from a fragment**
- can be broken down when max batch size is set
- Switch to **batch streaming** when fragments are too large or you need tight memory bounds.

```python
scanner = ds.Scanner.from_dataset(
    dataset,
    columns=needed_cols,                 # project early
    filter=ds.field("dt") >= "2025-01-01",  # pushdown filter
    batch_size=256_000                    # tune for memory
)
for batch in scanner.to_batches():
    df = transform(pl.from_arrow(batch))
    fs.write_to_dataset(dst_path, df, partition_by=part_cols, existing_data_behavior="overwrite_or_ignore")
fs.write_common_metadata(dst_path)
```
Tags: code
<!--ID: 1754819152258-->
END
