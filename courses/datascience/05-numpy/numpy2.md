# NumPy Complete Guide

NumPy is the **core library for numerical computing in Python**.

It provides:
- Fast array operations
- Mathematical & statistical functions
- Linear algebra support
- Foundation for ML, Data Science

---

<!-- ## Table of Contents

1. Introduction  
2. Array Creation  
3. Array Attributes  
4. Data Types  
5. Indexing & Slicing  
6. Reshaping Arrays  
7. Flattening Arrays  
8. Arithmetic Operations  
9. Broadcasting  
10. Mathematical Functions  
11. Statistical Functions  
12. Axis Operations  
13. Cumulative Functions  
14. Sorting & Searching  
15. Stacking & Concatenation  
16. Splitting Arrays  
17. Boolean Indexing  
18. Handling NaN  
19. Array Modification  
20. Linear Algebra  
21. Utility Functions  
22. Copy vs View  
23. File Handling  
24. Summary   -->

---

## 1. Introduction

NumPy arrays are **homogeneous (same data type)** and **multi-dimensional**.

```python
arr = np.array([1, 2, 3])
print(arr)

# Output:
# [1 2 3]
```

---

## 2. Array Creation

```python
np.zeros((2,2))

# Output:
# [[0. 0.]
#  [0. 0.]]
```

```python
np.arange(0,5)

# Output:
# [0 1 2 3 4]
```

---

## 3. Array Attributes

```python
arr = np.array([[1,2,3],[4,5,6]])

print(arr.shape)
print(arr.ndim)

# Output:
# (2, 3)
# 2
```

---

## 4. Data Types

```python
np.array([1,2,3], dtype=float)

# Output:
# [1. 2. 3.]
```

---

# 5. Indexing & Slicing

```python
arr = np.array([10,20,30,40])

print(arr[1:3])

# Output:
# [20 30]
```

---

# 6. Reshaping Arrays

```python
np.arange(6).reshape(2,3)

# Output:
# [[0 1 2]
#  [3 4 5]]
```

---

# 7. Flattening Arrays

```python
np.array([[1,2],[3,4]]).flatten()

# Output:
# [1 2 3 4]
```

---

# 8. Arithmetic Operations

```python
arr = np.array([1,2,3])

print(arr + 2)
print(arr * 3)

# Output:
# [3 4 5]
# [3 6 9]
```

---

# 9. Broadcasting

```python
np.array([1,2,3]) + 10

# Output:
# [11 12 13]
```

---

# 10. Mathematical Functions

| Function | Example |
|--------|--------|
| sqrt | `np.sqrt([1,4,9]) → [1,2,3]` |
| power | `np.power(2,3) → 8` |
| exp | `np.exp(1)` |

```python
np.sqrt([1,4,9])

# Output:
# [1. 2. 3.]
```

---

# 11. Statistical Functions

| Function | Use |
|--------|-----|
| mean | Average |
| std | Spread |
| sum | Total |

```python
np.mean([10,20,30])

# Output:
# 20.0
```

---

# 12. Axis Operations

```python
arr = np.array([[1,2],[3,4]])

print(np.sum(arr, axis=0))
print(np.sum(arr, axis=1))

# Output:
# [4 6]
# [3 7]
```

---

# 13. Cumulative Functions

```python
np.cumsum([1,2,3])

# Output:
# [1 3 6]
```

---

# 14. Sorting & Searching

```python
np.sort([3,1,2])

# Output:
# [1 2 3]
```

```python
np.argmax([1,5,2])

# Output:
# 1
```

---

# 15. Stacking & Concatenation

```python
a = np.array([1,2])
b = np.array([3,4])

np.vstack((a,b))

# Output:
# [[1 2]
#  [3 4]]
```

---

# 16. Splitting Arrays

```python
np.split(np.array([1,2,3,4]), 2)

# Output:
# [array([1, 2]), array([3, 4])]
```

---

# 17. Boolean Indexing

```python
arr = np.array([1,5,10])

arr[arr > 5]

# Output:
# [10]
```

---

# 18. Handling NaN

```python
arr = np.array([1, np.nan])

np.isnan(arr)

# Output:
# [False  True]
```

---

# 19. Array Modification

```python
np.append([1,2], 3)

# Output:
# [1 2 3]
```

---

# 20. Linear Algebra

```python
np.dot([1,2],[3,4])

# Output:
# 11
```

---

# 21. Utility Functions

```python
np.clip([1,10,20], 5, 15)

# Output:
# [ 5 10 15]
```

---

# 22. Copy vs View

```python
a = np.array([1,2])
b = a.copy()

b[0] = 100

print(a)

# Output:
# [1 2]
```

---

# 23. File Handling

```python
np.save("a.npy", [1,2,3])
np.load("a.npy")

# Output:
# [1 2 3]
```

---

# 24. Summary

NumPy provides:
- Fast computations  
- Memory efficiency  
- Powerful math functions  
- Base for ML & Data Science  

---

# Real World Use Cases

| Scenario | Use |
|--------|-----|
| Data Analysis | Aggregations |
| Machine Learning | Matrix ops |
| Image Processing | Multi-d arrays |
| Finance | Statistical models |

---

# Next Step

After NumPy, learn:
- Pandas  
- Matplotlib  
- Scikit-learn  
