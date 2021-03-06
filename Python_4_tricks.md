# Outline

## Sort dict by value
```
# from https://stackoverflow.com/questions/613183/how-do-i-sort-a-dictionary-by-value
sorted_dict = {k: v for k, v in sorted(src.items(), key=lambda x: x[1])}
```

## Install specified package version or Douban source
```
pip install -v package_name==0.9.3

# Douban source
pip install -i https://pypi.doubanio.com/simple/ tensor2tensor

# force update
pip install --upgrade --force-reinstall tensorflow-gpu==1.9.0
```

## Convert pdf to txt
```
# python 2
pip install pdfminer

# python 3
pip install pdfminer.six
```

## Config user-defined dictionary for jieba
```
python -m site find site-packages location, and find the folder of jieba, such as, /usr/lib/python3.6/site-packages/jieba

cd jieba_folder, rename dict.txt to dict_src.txt

copy user-defined dict to jieba_folder, and rename it to dict.txt

cd /tmp remove old jieba.cache
```

## Find python package path
```
pip show jieba
```

## Find site-packages
```
python -m site
```

## Python3 pickle load python2 files
```
# from https://stackoverflow.com/questions/11305790/pickle-incompatibility-of-numpy-arrays-between-python-2-and-3
import pickle

with open('mnist.pkl', 'rb') as f:
    u = pickle._Unpickler(f)
    u.encoding = 'latin1'
    p = u.load()
    print(p)
    
```

## Close printed information about jieba and tensorflow
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

## Ignore DeprecationWarning
```
# https://stackoverflow.com/questions/49545947/sklearn-deprecationwarning-truth-value-of-an-array
import warnings
warnings.filterwarnings(action='ignore', category=DeprecationWarning)
```


## Mac matplotlib show Chinese
```
# solution
matplotlib图例中文乱码? - 知乎
https://www.zhihu.com/question/25404709/answer/170849168
```

## Format digits
```
a = 0.8932
a_format = '%.2f' % a
```

## Convert doc or pdf to txt in Linux
```
# convert doc to txt
os.system("libreoffice --headless --convert-to txt '{}'".format(doc_file_path))

# convert pdf to txt
os.system("pdftotext '{}'".format(f_new))
```

## Json example
```
a = {'a': 1}
b = json.dumps(a)
type(b) # <class 'str'>
c = json.loads(b)
type(c) # <class 'dict'>
```

## help(func) and dir(func)
Have a quick look at the documents of `func` and available methods of `func`.

## os.path.getsize
Return the size of the file in Byte unit.
```
# Example:
if os.path.getsize('a.txt') > 100000: # larger than 100kb
    os.remove('a.txt')
```

## Contains Chinese character
```
if input_text >= u'\u4e00' and input_text <= u'\u9fff':
    rtn = True
```



## Split with multiple conditions
```
re.split(r'[:：]', each_line, maxsplit=1)
```

## Format a dict
```
infos = {'name': 'zhangsan', 'age': 18}
# **infos = 'name': 'zhangsan', 'age': 18
print('My name is {name}, and I am {age} years old.'.format(**infos))
# My name is zhangsan, and I am 18 years old.
```

## Encoding format
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


