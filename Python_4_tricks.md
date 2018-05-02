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
if input_text > u'\u4e00' and input_text < u'\u9fff':
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
