## Frobenius norm
Frobenius norm can decide whether two matrices are similar.
```
difference = np.linalg.norm(dists - dists_one, ord='fro')
The following norms can be calculated:
```

## np.concatenate, np.hstack, np.vstack
numpy.concatenate((a1, a2, ...), axis=0) is used to join a sequence of arrays along an existing axis.

np.hstack == np.concatenate(axis=1)  

np.vstack == np.concatenate(axis=0)

```
a = np.random.random((2,3))
array([[ 0.7468407 ,  0.05894208,  0.69324626],
       [ 0.67258335,  0.71953486,  0.20485528]])
       
b = np.random.random((2,3))
array([[ 0.96088597,  0.52390196,  0.48795642],
       [ 0.07738216,  0.38911414,  0.09043926]])

c = np.random.random((2,3))
array([[ 0.98500376,  0.52292523,  0.75430416],
       [ 0.63725618,  0.31863499,  0.6199581 ]])

# hstack: row is static
abc_hor = np.hstack((a,b,c)) 
array([[ 0.7468407 ,  0.05894208,  0.69324626,  0.96088597,  0.52390196,
         0.48795642,  0.98500376,  0.52292523,  0.75430416],
       [ 0.67258335,  0.71953486,  0.20485528,  0.07738216,  0.38911414,
         0.09043926,  0.63725618,  0.31863499,  0.6199581 ]])
abc_hor.shape #(2L, 9L)

abc_con_axis1 = np.concatenate((a,b,c), axis=1)
abc_con_axis1.shape # (2L, 9L)

# check the difference between abc_hor and abc_con_axis1
np.linalg.norm((abc_hor-abc_con_axis1), ord='fro') # 0.0


# vstack: column is static
abc_vec = np.vstack((a,b,c)) 
array([[ 0.7468407 ,  0.05894208,  0.69324626],
       [ 0.67258335,  0.71953486,  0.20485528],
       [ 0.96088597,  0.52390196,  0.48795642],
       [ 0.07738216,  0.38911414,  0.09043926],
       [ 0.98500376,  0.52292523,  0.75430416],
       [ 0.63725618,  0.31863499,  0.6199581 ]])
abc_vec.shape # (6L, 3L)

abc_con_axis0 = np.concatenate((a,b,c), axis=0) # or np.concatenate((a,b,c)) since axis=0 is default
abc_con_axis0.shape #(6L, 3L)

# check the difference between abc_vec and abc_con_axis0
np.linalg.norm((abc_vec-abc_con_axis0), ord='fro') #0.0
```

# np.array_split
numpy.array_split(ary, indices_or_sections, axis=0) is used to split an array into multiple sub-arrays.
```
x = np.arange(8.0)
np.array_split(x, 3) # [array([ 0.,  1.,  2.]), array([ 3.,  4.,  5.]), array([ 6.,  7.])]
```

# np.argsort 
numpy.argsort(a, axis=-1, kind='quicksort', order=None) returns the indices that would sort an array.
```
x = np.array([3, 1, 2])
np.argsort(x) # array([1, 2, 0])
```
