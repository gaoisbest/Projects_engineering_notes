# Check is RDD or Dataframe
```
from pyspark.sql import DataFrame
from pyspark.rdd import RDD

isinstance(a, RDD)
```

# UDF return list of tuple of String type
```
def my_udf():
    return [('a', 'b'), ('c', 'd')]
    
label_udf = udf(my_udf, ArrayType(ArrayType(StringType())))

```

# Cast column type
```
from pyspark.sql.types import DoubleType

col('a').cast(DoubleType())

```

# Split one column to multiple columns
```
split_cols = func.split(func.col('utterance @ intent @ bot response'), split_symbol)
split_df = src_df.withColumn('utterance', split_cols.getItem(0)).\
        withColumn('intent', split_cols.getItem(1)).\
        withColumn('response', split_cols.getItem(2)).select('calllogid', 'utterance', 'intent', 'response')
 ```
