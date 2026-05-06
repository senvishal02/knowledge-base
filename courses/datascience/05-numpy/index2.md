# NumPy Notes (Python)

NumPy (**Numerical Python**) is a powerful Python library used for **numerical computing**. It provides high-performance **multi-dimensional arrays** and tools for working with mathematical, scientific, and statistical operations.

---

# 1. What is NumPy?

NumPy is a Python library designed for:

- Fast numerical computation
- Working with large datasets
- Matrix and vector operations
- Scientific computing
- Machine Learning and Data Science preprocessing

## Core Object

```python
numpy.ndarray
```

A **NumPy array** is similar to a Python list but optimized for:

- Speed
- Memory efficiency
- Mathematical operations

### Example

```python
import numpy as np

arr = np.array([1,2,3,4])
print(arr)
```

**Output**

```
[1 2 3 4]
```

---

# 2. Purpose / Use Cases of NumPy

| Use Case | Explanation | Example |
|--------|-------------|--------|
| Scientific Computing | Mathematical operations | Matrix multiplication |
| Data Science | Preprocessing large datasets | Normalization |
| Machine Learning | Input to ML models | Feature arrays |
| Image Processing | Pixel matrices | Reshape images |
| Simulation | Random distributions | Monte Carlo |
| Linear Algebra | Matrix operations | Dot product |
| Statistics | Mean, variance, std | Data analysis |

### Example

```python
import numpy as np

data = np.array([10,20,30,40])
print(np.mean(data))
```

---

# 3. NumPy vs Python Data Structures

| Feature | List | Tuple | Set | Dict | NumPy Array |
|------|------|------|------|------|------|
| Ordered | Yes | Yes | No | Yes | Yes |
| Mutable | Yes | No | Yes | Yes | Yes |
| Duplicate Allowed | Yes | Yes | No | No | Yes |
| Indexed | Yes | Yes | No | Key-based | Yes |
| Numerical Computation | Slow | Slow | No | No | Very Fast |
| Memory Efficient | No | No | No | No | Yes |
| Vectorized Operations | No | No | No | No | Yes |

### Example

#### Python List

```python
a = [1,2,3]
b = [4,5,6]

result = []
for i in range(len(a)):
    result.append(a[i] + b[i])

print(result)
```

#### NumPy

```python
import numpy as np

a = np.array([1,2,3])
b = np.array([4,5,6])

print(a + b)
```

**Output**

```
[5 7 9]
```

NumPy is **much faster** due to vectorization.

---

# 4. Creating NumPy Arrays

## From List

```python
import numpy as np

arr = np.array([1,2,3,4])
```

## 2D Array

```python
arr = np.array([[1,2],[3,4]])
```

## Zeros

```python
np.zeros((3,3))
```

## Ones

```python
np.ones((2,2))
```

## Range

```python
np.arange(0,10,2)
```

## Evenly Spaced Numbers

```python
np.linspace(0,10,5)
```

## Random Values

```python
np.random.rand(3,3)
```

---

# 5. NumPy Data Types

NumPy arrays use **fixed data types**.

| Data Type | Description |
|------|------|
| int8 | 8-bit integer |
| int16 | 16-bit integer |
| int32 | 32-bit integer |
| int64 | 64-bit integer |
| float16 | 16-bit float |
| float32 | 32-bit float |
| float64 | 64-bit float |
| bool | True/False |
| complex | Complex numbers |

### Example

```python
arr = np.array([1,2,3], dtype=np.float32)
print(arr.dtype)
```

**Output**

```
float32
```

### Why Data Types Matter

- Control memory usage
- Improve performance
- Ensure consistent numerical operations

---

# 6. Changing Data Types

Using `astype()`:

```python
import numpy as np

arr = np.array([1,2,3])

new_arr = arr.astype(float)

print(new_arr)
```

**Output**

```
[1. 2. 3.]
```

---

# 7. Array Attributes

| Attribute | Description |
|------|------|
| ndim | Number of dimensions |
| shape | Size of each dimension |
| size | Total elements |
| dtype | Data type |
| itemsize | Memory per element |
| nbytes | Total memory used |

### Example

```python
arr = np.array([[1,2,3],[4,5,6]])

print(arr.shape)
print(arr.ndim)
print(arr.size)
```

---

# 8. Indexing

## 1D Indexing

```python
arr = np.array([10,20,30,40])

print(arr[0])
print(arr[-1])
```

## 2D Indexing

```python
arr = np.array([
    [1,2,3],
    [4,5,6]
])

print(arr[0,1])
```

**Output**

```
2
```

---

# 9. Slicing

## 1D Slicing

```python
arr = np.array([1,2,3,4,5,6])

print(arr[1:4])
```

**Output**

```
[2 3 4]
```

## Step Slicing

```python
print(arr[::2])
```

**Output**

```
[1 3 5]
```

## 2D Slicing

```python
arr = np.array([
    [1,2,3],
    [4,5,6],
    [7,8,9]
])

print(arr[0:2,1:3])
```

**Output**

```
[[2 3]
 [5 6]]
```

---

# 10. Updating Elements

```python
arr = np.array([1,2,3])

arr[0] = 100

print(arr)
```

**Output**

```
[100 2 3]
```

## Updating Slice

```python
arr[1:3] = 50
```

**Output**

```
[100 50 50]
```

---

# 11. Mathematical Operations

| Operation | Example |
|------|------|
| Addition | `a + b` |
| Subtraction | `a - b` |
| Multiplication | `a * b` |
| Division | `a / b` |
| Power | `a ** 2` |

### Example

```python
import numpy as np

a = np.array([1,2,3])
b = np.array([4,5,6])

print(a + b)
print(a * b)
```

---

# 12. Aggregation Functions

| Function | Use Case |
|------|------|
| np.sum() | Total |
| np.mean() | Average |
| np.min() | Minimum |
| np.max() | Maximum |
| np.std() | Standard deviation |
| np.var() | Variance |

### Example

```python
data = np.array([10,20,30])

print(np.sum(data))
print(np.mean(data))
```

---

# 13. Reshaping Arrays

```python
arr = np.arange(6)

new_arr = arr.reshape(2,3)

print(new_arr)
```

**Output**

```
[[0 1 2]
 [3 4 5]]
```

---

# 14. Flatten Array

```python
arr = np.array([[1,2],[3,4]])

print(arr.flatten())
```

**Output**

```
[1 2 3 4]
```

---

# 15. Stacking Arrays

## Vertical Stack

```python
np.vstack((a,b))
```

## Horizontal Stack

```python
np.hstack((a,b))
```

### Example

```python
a = np.array([1,2])
b = np.array([3,4])

print(np.vstack((a,b)))
```

---

# 16. Random Module

| Function | Description |
|------|------|
| np.random.rand() | Random numbers |
| np.random.randint() | Random integers |
| np.random.randn() | Normal distribution |

### Example

```python
np.random.randint(1,10,5)
```

---

# 17. Linear Algebra

```python
a = np.array([[1,2],
              [3,4]])

b = np.array([[5,6],
              [7,8]])

print(np.dot(a,b))
```

---

# 18. Broadcasting

Broadcasting allows operations between arrays of different shapes.

### Example

```python
arr = np.array([1,2,3])

print(arr + 10)
```

**Output**

```
[11 12 13]
```

---

# 19. NumPy in Data Science Workflow

Typical pipeline:

```
Raw Data
   ↓
NumPy Array
   ↓
Data Cleaning
   ↓
Feature Engineering
   ↓
Machine Learning Models
```

NumPy is used heavily with:

- Pandas
- Scikit-Learn
- TensorFlow
- PyTorch

---

# 20. Performance Comparison

### List Operation

```python
import numpy as np
import time

size = 1000000

list1 = list(range(size))
list2 = list(range(size))

start = time.time()
result = [a+b for a,b in zip(list1,list2)]
print("List time:", time.time()-start)
```

### NumPy Operation

```python
a = np.arange(size)
b = np.arange(size)

start = time.time()
result = a + b
print("NumPy time:", time.time()-start)
```

---

# Summary

NumPy provides:

- Fast numerical computation
- Multi-dimensional arrays
- Vectorized operations
- Advanced indexing and slicing
- Mathematical and statistical functions
- Linear algebra support
- Random number generation

NumPy is a **core foundation for Data Science, Machine Learning, and Scientific Computing in Python**.


---

# Cheat Sheet

# Advanced NumPy Cheat Sheet (Data Science + ML + Interviews)

This guide covers **advanced NumPy concepts used in real-world ML/Data Science projects and technical interviews**.

---

# 1. Broadcasting

Broadcasting allows NumPy to perform operations on arrays with **different shapes**.

### Rules

1. Dimensions must match, OR  
2. One of them must be `1`

### Example

```python
import numpy as np

a = np.array([1,2,3])
b = 10

print(a + b)
```

**Output**

```
[11 12 13]
```

### Example 2

```python
a = np.array([[1],[2],[3]])
b = np.array([10,20,30])

print(a + b)
```

**Output**

```
[[11 21 31]
 [12 22 32]
 [13 23 33]]
```

---

# 2. Vectorization

Vectorization means applying operations to entire arrays **without loops**.

### Python Loop

```python
a = [1,2,3]
b = [4,5,6]

result = []
for i in range(len(a)):
    result.append(a[i] * b[i])
```

### NumPy Vectorization

```python
import numpy as np

a = np.array([1,2,3])
b = np.array([4,5,6])

result = a * b
```

### Benefits

| Benefit | Explanation |
|--------|-------------|
| Faster | Uses C backend |
| Cleaner code | Less loops |
| Efficient memory | Optimized operations |

---

# 3. Boolean Masking

Used to filter arrays based on conditions.

### Example

```python
import numpy as np

arr = np.array([10,20,30,40,50])

mask = arr > 30
print(mask)
```

**Output**

```
[False False False True True]
```

### Filtering

```python
print(arr[arr > 30])
```

**Output**

```
[40 50]
```

---

# 4. Conditional Selection

Using `np.where()`.

```python
import numpy as np

arr = np.array([10,20,30,40])

result = np.where(arr > 25, "High", "Low")

print(result)
```

**Output**

```
['Low' 'Low' 'High' 'High']
```

---

# 5. Fancy Indexing

Selecting multiple indices at once.

### Example

```python
arr = np.array([10,20,30,40,50])

print(arr[[0,2,4]])
```

**Output**

```
[10 30 50]
```

### 2D Example

```python
arr = np.array([
    [1,2,3],
    [4,5,6],
    [7,8,9]
])

print(arr[[0,2]])
```

**Output**

```
[[1 2 3]
 [7 8 9]]
```

---

# 6. Boolean Indexing

```python
import numpy as np

arr = np.array([5,10,15,20,25])

print(arr[arr >= 15])
```

**Output**

```
[15 20 25]
```

---

# 7. Important NumPy Methods (Most Used)

| Method | Purpose | Example |
|------|------|------|
| `np.array()` | Create array | `np.array([1,2,3])` |
| `np.arange()` | Range array | `np.arange(0,10)` |
| `np.linspace()` | Evenly spaced numbers | `np.linspace(0,1,5)` |
| `np.zeros()` | Array of zeros | `np.zeros((3,3))` |
| `np.ones()` | Array of ones | `np.ones((2,2))` |
| `np.eye()` | Identity matrix | `np.eye(3)` |
| `np.random.rand()` | Random numbers | `np.random.rand(3)` |
| `np.random.randint()` | Random integers | `np.random.randint(1,10,5)` |
| `reshape()` | Change shape | `arr.reshape(2,3)` |
| `flatten()` | Flatten array | `arr.flatten()` |
| `concatenate()` | Combine arrays | `np.concatenate([a,b])` |
| `vstack()` | Vertical stack | `np.vstack([a,b])` |
| `hstack()` | Horizontal stack | `np.hstack([a,b])` |

---

# 8. Mathematical Functions

| Function | Use Case |
|------|------|
| `np.add()` | Addition |
| `np.subtract()` | Subtraction |
| `np.multiply()` | Multiplication |
| `np.divide()` | Division |
| `np.sqrt()` | Square root |
| `np.power()` | Exponent |
| `np.abs()` | Absolute value |

### Example

```python
import numpy as np

arr = np.array([1,4,9,16])

print(np.sqrt(arr))
```

**Output**

```
[1. 2. 3. 4.]
```

---

# 9. Statistical Functions

| Function | Description |
|------|------|
| `np.mean()` | Average |
| `np.median()` | Median |
| `np.std()` | Standard deviation |
| `np.var()` | Variance |
| `np.sum()` | Sum |
| `np.min()` | Minimum |
| `np.max()` | Maximum |
| `np.percentile()` | Percentile |

### Example

```python
arr = np.array([10,20,30,40])

print(np.mean(arr))
print(np.std(arr))
```

---

# 10. Axis Concept (Very Important)

Axis defines the **direction of operation**.

### Example Array

```python
arr = np.array([
    [1,2,3],
    [4,5,6]
])
```

### Axis Visualization

```
axis=0 → columns
axis=1 → rows
```

### Example

```python
print(np.sum(arr, axis=0))
```

**Output**

```
[5 7 9]
```

### Example

```python
print(np.sum(arr, axis=1))
```

**Output**

```
[ 6 15]
```

---

# 11. Sorting Arrays

```python
import numpy as np

arr = np.array([4,2,1,3])

print(np.sort(arr))
```

**Output**

```
[1 2 3 4]
```

### 2D Sorting

```python
np.sort(arr, axis=0)
```

---

# 12. Unique Values

```python
import numpy as np

arr = np.array([1,2,2,3,3,3])

print(np.unique(arr))
```

**Output**

```
[1 2 3]
```

---

# 13. Memory Optimization

NumPy arrays use **contiguous memory blocks**, making them faster.

### Example

```python
arr = np.array([1,2,3], dtype=np.int8)
```

### Memory Comparison

| Type | Memory |
|------|------|
| int64 | 8 bytes |
| int32 | 4 bytes |
| int16 | 2 bytes |
| int8 | 1 byte |

---

# 14. Copy vs View (Important Interview Topic)

### View

```python
a = np.array([1,2,3])

b = a.view()

b[0] = 100

print(a)
```

**Output**

```
[100 2 3]
```

### Copy

```python
b = a.copy()
```

Now changes **do not affect the original array**.

---

# 15. Transpose

Swap rows and columns.

```python
import numpy as np

arr = np.array([
    [1,2,3],
    [4,5,6]
])

print(arr.T)
```

**Output**

```
[[1 4]
 [2 5]
 [3 6]]
```

---

# 16. Matrix Multiplication

```python
import numpy as np

a = np.array([
    [1,2],
    [3,4]
])

b = np.array([
    [5,6],
    [7,8]
])

print(np.matmul(a,b))
```

### Alternative

```python
a @ b
```

---

# 17. NumPy Random Module (Used in ML)

| Function | Use Case |
|------|------|
| `np.random.rand()` | Uniform distribution |
| `np.random.randn()` | Normal distribution |
| `np.random.randint()` | Random integers |
| `np.random.choice()` | Random selection |
| `np.random.shuffle()` | Shuffle array |

### Example

```python
np.random.randint(1,100,10)
```

---

# 18. Useful Array Transformations

### Reshape

```python
arr.reshape(3,3)
```

### Flatten

```python
arr.flatten()
```

### Ravel (Faster Flatten)

```python
arr.ravel()
```

---

# 19. Performance Tips

### Best Practices

| Tip | Reason |
|------|------|
| Avoid Python loops | Use vectorization |
| Use correct dtype | Reduce memory |
| Use broadcasting | Faster computation |
| Use NumPy functions | Optimized C backend |

---

# 20. NumPy in ML Pipeline

Typical flow:

```
Raw Dataset
   ↓
NumPy Array
   ↓
Data Cleaning
   ↓
Feature Engineering
   ↓
Model Training
```

Libraries using NumPy internally:

- Pandas
- Scikit-Learn
- TensorFlow
- PyTorch
- OpenCV
- SciPy

---

# 21. Most Important NumPy Interview Topics

Must know:

- `ndarray`
- Broadcasting
- Vectorization
- Boolean masking
- Fancy indexing
- `reshape()` / `flatten()`
- Axis operations
- Copy vs View
- Random module
- Matrix multiplication

---

# 22. Quick NumPy Cheatsheet

| Task | Code |
|------|------|
| Create array | `np.array([1,2,3])` |
| Range | `np.arange(10)` |
| Zeros | `np.zeros((3,3))` |
| Ones | `np.ones((3,3))` |
| Identity | `np.eye(3)` |
| Reshape | `arr.reshape(2,3)` |
| Flatten | `arr.flatten()` |
| Mean | `np.mean(arr)` |
| Sum | `np.sum(arr)` |
| Max | `np.max(arr)` |
| Sort | `np.sort(arr)` |
| Unique | `np.unique(arr)` |
| Matrix multiply | `a @ b` |

---

# Summary

NumPy provides:

- Fast numerical arrays
- Broadcasting
- Vectorized computation
- Statistical operations
- Linear algebra
- Random number generation
- Memory efficient computation

NumPy is the **foundation of the entire Python Data Science ecosystem**.