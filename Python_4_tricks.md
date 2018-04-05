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
