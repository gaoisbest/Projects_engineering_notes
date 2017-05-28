## np.concatenate, np.hstack, np.vstack
np.hstack = np.concatenate(axis=1)
np.vstack = np.concatenate(axis=0)

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
