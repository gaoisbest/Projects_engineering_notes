# Python
- `Python_1_Iterable Iterator Generator.ipynb`: generator, iterator, iterable. See [Chinese Notes](http://url.cn/54BFOJR), [中文解读](http://url.cn/54BFOJR).
- `Python_2_list comprehension.ipynb`: list comprehension. See [Chinese Notes](http://url.cn/50UrGtb), [中文解读](http://url.cn/50UrGtb).
- `Python_3_property decorator.ipynb`: property decorator. See [Chinese Notes](http://url.cn/5rIEJJg), [中文解读](http://url.cn/5rIEJJg).
- `Python_4_tricks.md`: pip image, find package infomation, encoding etc.
- `Python_5_Cartesian_product.ipynb`: Cartesian product to substitute nested-for loop for hyper-parameter evaluating


# Numpy
- `Numpy_1_ndarray shape.ipynb`: ndarray shape. See [Chinese Notes](http://url.cn/58GGOaU), [中文解读](http://url.cn/58GGOaU)

# Pandas
- `Pandas_1_Series_DataFrame.ipynb`: introduction of `Series` and `DataFrame`
- `Pandas_2_DataFrame operations.ipynb`: `DataFrame` operations

# Spark
- `spark.md`: frequently functions

# Excel
- `Excel.md`: frequently operations

# Docker
- `Docker_notes.md`: frequently commands

# PyTorch
- `PyTorch.md`: frequently functions

# base64
## Save image to byte
```
image_src = 'teset.svg'
with open(image_src, "rb") as f:
    data = f.read()
    # to serialize in JSON, here decode("utf8") is needed
    a = {'status': base64.b64encode(data).decode("utf8")}
```

## Covnert byte to image
```
a = {'status':'csfdfdere'}
image_decode = base64.b64decode(a['status'].encode("utf8"))
image_res = open('/Users/test.svg', 'wb')
image_res.write(image_decode)
image_res.close()
```
