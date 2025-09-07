# NumPy Practice Problems - PA #2

This repository contains solutions to practice problems using NumPy, including normalization and array operations. As a starter, to be able to access different codes and functions that includes arrays, math, linear algebra, etc., we use a numpy library that can be written as:

```python
    import numpy as np 
```

Things to take note of:<br>
- `import` -> just lets you use external libraries
- `numpy` -> the library to access and use for codes that involves arrays, math, linear algebra, etc.
- `as np` -> just an alias to shorten "numpy", so instead of using numpy.array(), we can just write np.array().

### Now onto the problems:
---
### NORMALIZATION PROBLEM:<br> 
For this problem, we have to create a random a 5 x 5 ndarray, normalize it, and save the normalized ndarray as *X_normalized.npy*. What is normalizing? Normalizing is a preprocessing technique that involves centering and scaling process. Centering means subracting data from the mean and scaling means dividing with its standard deviation. 

### Code:

```python

    X = np.random.random((5, 5))

    Normalize_X = ((X - X.mean())/(X.std()))

    np.save("X_normalized.npy", Normalize_X)
  
    data = np.load('X_normalized.npy')
    data

```

This code involves generating a random 5 x 5 array. So to be expected, every result that this code outputs will be different every single time. As such:<br>

### Example output:
```
array([[-1.44871327, -0.97489987,  0.92644544,  1.63857306, -0.28553693],
       [ 1.07872972,  1.7026327 , -1.2528608 ,  0.33668759, -1.24283109],
       ...
       [ 0.70353731,  0.32314468, -1.2522199 , -0.6964899 , -1.3971413 ]])
```

### How the code works:<br>
1. The code starts off by generating a random 5 x 5 ndarray using `X = np.random.random((5, 5))`. We assigned it to X as we can use it in multiple operations such as getting the mean and standard deviation.
2. Normalize by subracting the data from the mean and dividing with its standard deviation using `Normalize_X = ((X - X.mean())/(X.std()))`.
3. Save the normalized ndarray as X_normalized.npy using `np.save("X_normalized.npy", Normalize_X)`
4. Finally, load the saved ndarray by using `data = np.load('X_normalized.npy')` and execute the code by using `data` in the next line. 
---
       
### DIVISIBLE BY 3 PROBLEM:<br>
For this problem, we create a 10 x 10 ndarray, which are the squares of the first 100 positive integers. From this ndarray, we have to determine all the elemts that are divisible by 3 and save the result as *div_by_3.npy*.

### Code:

```python

    arr = np.arange(1, 101)**2
    arr = arr.reshape(10, 10)
    divisibleby3 = arr[arr % 3 == 0]

    np.save("div_by_3.npy", divisibleby3)
  
    data = np.load('div_by_3.npy')
    data

```

### Output:
```
array([   9,   36,   81,  144,  225,  324,  441,  576,  729,  900, 1089,
       1296, 1521, 1764, 2025, 2304, 2601, 2916, 3249, 3600, 3969, 4356,
       4761, 5184, 5625, 6084, 6561, 7056, 7569, 8100, 8649, 9216, 9801])
```

### How the code works:
1. The code starts off by assigning to a variable. In this case, we assign it to `arr`. We generate the squares of the first 100 positive integers using `np.arange(1, 101)**2`. Then we use `arr.reshape(10, 10)` to format it neatly.
2. We use `divisibleby3 = arr[arr % 3 == 0]` to get the squares of the first 100 positive integer that are divisible by 3. The prior codes revolves around the use of modulu operator `%`. In `arr % 3`, it gives the remander after division. Including an equility operator checks which numbers are divisible by 0. And finally, `arr[...]` is a boolean indexing, which just means it filters the array, keeping only the numbers that are `true`.  
3. Save the ndarray using `np.save("div_by_3.npy", divisibleby3)`, load it using `data = np.load('div_by_3.npy')`, and execute by using `data` in the next line.  
