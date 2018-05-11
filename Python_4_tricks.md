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


