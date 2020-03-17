# Split one column to multiple columns
```
split_cols = func.split(func.col('utterance @ intent @ bot response'), split_symbol)
split_df = src_df.withColumn('utterance', split_cols.getItem(0)).\
        withColumn('intent', split_cols.getItem(1)).\
        withColumn('response', split_cols.getItem(2)).select('calllogid', 'utterance', 'intent', 'response')
 ```
