# Outline

# Find python package path
```
pip show jieba
```

# Close printed information about jieba and tensorflow
```
# for jieba
Building prefix dict from /usr/lib/python2.7/site-packages/jieba/dict.txt ...
Loading model from cache /tmp/jieba.cache
Loading model cost 0.182227134705 seconds.
Prefix dict has been built succesfully.

import logging
jieba.setLogLevel(logging.INFO)


# for tensorflow
Your CPU supports instructions that this TensorFlow binary was not compiled to use: AVX2 FMA
import os
os.environ['TF_CPP_MIN_LOG_LEVEL'] = '2'
```
# Mac matplotlib show Chinese
```
# solution
matplotlib图例中文乱码? - 知乎
https://www.zhihu.com/question/25404709/answer/170849168
```
# install specified package version or Douban source
```
pip install -v package_name==0.9.3

# Douban source
pip install -i https://pypi.doubanio.com/simple/ tensor2tensor
```

# format digits
```
a = 0.8932
a_format = '%.2f' % a
```
# Ignore DeprecationWarning
```
# https://stackoverflow.com/questions/49545947/sklearn-deprecationwarning-truth-value-of-an-array
import warnings
warnings.filterwarnings(action='ignore', category=DeprecationWarning)
```

# convert doc or pdf to txt in Linux
```
# convert doc to txt
os.system("libreoffice --headless --convert-to txt '{}'".format(doc_file_path))

# convert pdf to txt
os.system("pdftotext '{}'".format(f_new))
```

# json example
```
a = {'a': 1}
b = json.dumps(a)
type(b) # <class 'str'>
c = json.loads(b)
type(c) # <class 'dict'>
```

# append text to the file
```
with open(file, mode='a') as f:
    f.write('')
```

# remove all space in a str
```
a = 'he l l o'
a = a.replace(' ', '')
```

# help(func) and dir(func)
Have a quick look at the documents of `func` and available methods of `func`.

# os.path.getsize
Return the size of the file in Byte unit.
```
# Example:
if os.path.getsize('a.txt') > 100000: # larger than 100kb
    os.remove('a.txt')
```

# contains Chinese character
```
if input_text >= u'\u4e00' and input_text <= u'\u9fff':
    rtn = True
```

# find site-packages
```
python -m site
```

# split with multiple conditions
```
re.split(r'[:：]', each_line, maxsplit=1)
```

# format a dict
```
infos = {'name': 'zhangsan', 'age': 18}
# **infos = 'name': 'zhangsan', 'age': 18
print('My name is {name}, and I am {age} years old.'.format(**infos))
# My name is zhangsan, and I am 18 years old.
```

# encoding format
```
# get system encoding format
import sys
sys.getfilesystemencoding()
```
In python3, there are `str` and `bytes` types, `str` stores `unicode` data and `bytes` stores `bytes` data.  
**Unicode**: a rule, two bytes represents a character.  
**Utf-8**: an implementation, one bytes represents a character.  
`str` encodes to `bytes`, decodes to `str`.  
```
a = '吃饭了' # unicode default in python3
a.encode('utf-8') # a bytes in 16 decimal
a.encode('utf-8').decode('utf-8') # '吃饭了'
```


