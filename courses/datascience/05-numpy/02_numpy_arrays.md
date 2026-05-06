# NumPy Arrays

NumPy arrays are **homogeneous multidimensional arrays**, meaning all elements must have the **same data type**.

They are the **core data structure in NumPy** and provide:

- Fast numerical computation
- Efficient memory usage
- Multi-dimensional data representation

---

# Creating Arrays

## 1. From Python List

```python
import numpy as np

arr = np.array([1, 2, 3])
print(arr)
```

### Output

```
[1 2 3]
```

---

## 2. Creating a 2D Array

```python
import numpy as np

arr = np.array([[1, 2], [3, 4]])
print(arr)
```

### Output

```
[[1 2]
 [3 4]]
```

---

## 3. Array of Zeros

Creates an array filled with **0 values**.

```python
import numpy as np

arr = np.zeros((3, 3))
print(arr)
```

### Output

```
[[0. 0. 0.]
 [0. 0. 0.]
 [0. 0. 0.]]
```

---

## 4. Array of Ones

Creates an array filled with **1 values**.

```python
import numpy as np

arr = np.ones((2, 2))
print(arr)
```

### Output

```
[[1. 1.]
 [1. 1.]]
```

---

## 5. Range of Numbers

`np.arange()` creates an array within a **range of numbers**.

```python
import numpy as np

arr = np.arange(0, 10)
print(arr)
```

### Output

```
[0 1 2 3 4 5 6 7 8 9]
```

---

## 6. Evenly Spaced Numbers

`np.linspace()` creates **evenly spaced numbers between a range**.

```python
import numpy as np

arr = np.linspace(0, 10, 5)
print(arr)
```

### Output

```
[ 0.   2.5  5.   7.5 10. ]
```

---

# Specifying Data Types

You can specify the **data type (dtype)** when creating arrays.

```python
import numpy as np

arr = np.array([1, 2, 3], dtype=np.float32)
print(arr)
```

### Common Data Types

| Data Type | Description |
|--------|-------------|
| `int32` | 32-bit integer |
| `int64` | 64-bit integer |
| `float32` | 32-bit float |
| `float64` | 64-bit float |
| `bool` | Boolean values |

---

# Array Attributes

NumPy arrays provide attributes to understand the structure.

```python
import numpy as np

arr = np.array([[1, 2, 3], [4, 5, 6]])

print(arr.shape)
print(arr.ndim)
print(arr.size)
print(arr.dtype)
```

### Output Example

```
(2, 3)
2
6
int64
```

---

# NumPy Array Attributes Table

| Attribute | Meaning |
|----------|--------|
| `shape` | Dimensions of array |
| `ndim` | Number of dimensions |
| `size` | Total number of elements |
| `dtype` | Data type of elements |

---

# Reshaping Arrays

Reshape allows changing the **structure of an array**.

```python
import numpy as np

arr = np.arange(6)

reshaped = arr.reshape(2, 3)

print(reshaped)
```

### Output

```
[[0 1 2]
 [3 4 5]]
```

---

# Flattening Arrays

Flatten converts **multi-dimensional arrays into 1D arrays**.

```python
arr = np.array([[1,2,3],[4,5,6]])

print(arr.flatten())
```

Output

```
[1 2 3 4 5 6]
```

---

# Changing Data Type

Use `astype()` to convert data types.

```python
arr = np.array([1,2,3])

arr_float = arr.astype(float)

print(arr_float)
```

---

# Key Takeaway

NumPy arrays provide:

- Efficient numerical storage
- Fast mathematical computation
- Multi-dimensional array support
- Flexible data type management
- Powerful reshaping and transformation tools