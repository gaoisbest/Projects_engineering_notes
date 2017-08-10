# Iterable, Iterator and Generator
- Generator
  - two types of generators: generator **function** (with `yield`) and generator **expression**
  - a `generator` is an `Iterable` / `Iterator`
  - `next` to get next value
  ```
  import types
  from collections import Iterable, Iterator
  
  if __name__ == '__main__':
      list_exam = ['a', 'b', 'c']
      list_exam_gen = (e for e in list_exam) # generation expression
      print(isinstance(list_exam_gen, types.GeneratorType)) # True
      print(isinstance(list_exam_gen, Iterator)) # True
      print(isinstance(list_exam_gen, Iterable)) # True
      print(next(list_exam_gen)) # a
      print(next(list_exam_gen)) # b
      print(next(list_exam_gen)) # c
      print(next(list_exam_gen)) # StopIteration
  ```
  - `yield` give a generator, when to use `yield` instead of `return` ?
  
  When you want to iterate over a sequence, but don’t want to store the entire sequence in memory. Note, you can only **iterate over them once** (because it does not store the values in memory)

  ```
  import codecs
  import types

  def read_file(filepath):
      file_content = codecs.open(filename=filepath, mode='r', encoding='utf-8')
      for each_line in file_content:
          yield each_line

  if __name__ == '__main__':
      print(isinstance(read_file(filepath='test_file.txt'), types.GeneratorType)) # True
      for each_line in read_file(filepath='test_file.txt'):
          print(each_line)

  ```
- Iterable
  - we can use `for... in...` to iterate Iterable
  - `str`, `list`, `tuple`, `set`, `dict` all are `Iterable`
  ```
  from collections import Iterable
  
  if __name__ == '__main__':
      str_exam = 'abc'
      print(isinstance(str_exam, Iterable)) # True
      list_exam = ['a', 'b', 'c']
      print(isinstance(list_exam, Iterable)) # True
      tuple_exam = ('a', 'b', 'c')
      print(isinstance(tuple_exam, Iterable)) # True
      set_exam = set(['a', 'b', 'c'])
      print(isinstance(set_exam, Iterable)) # True
      dict_exam = {1:'a', 2:'b', 3:'c'}
      print(isinstance(dict_exam, Iterable)) # True
  ```
  
 - Iterator
   - get `Iterator` by calling `iter` on `Iterable`
   - an `Iterator` is an `Iterable`
   - `next` to get next value
   ```
   from collections import Iterator, Iterable
   
   if __name__ == '__main__':
       list_exam = ['a', 'b', 'c']
       list_iterator = iter(list_exam)
       print(isinstance(list_iterator, Iterator)) # True
       print(isinstance(list_iterator, Iterable))  # True
       print(issubclass(Iterator, Iterable)) # True
       print(next(list_iterator)) # a
       print(next(list_iterator)) # b
       print(next(list_iterator)) # c
       print(next(list_iterator)) # StopIteration
   ```
 

references:

https://stackoverflow.com/questions/7883962/where-to-use-yield-in-python-best

https://stackoverflow.com/questions/231767/what-does-the-yield-keyword-do

https://stackoverflow.com/questions/2776829/difference-between-pythons-generators-and-iterators

https://stackoverflow.com/questions/6416538/how-to-check-if-an-object-is-a-generator-object-in-python

https://stackoverflow.com/questions/2776829/difference-between-pythons-generators-and-iterators

http://nvie.com/posts/iterators-vs-generators/
