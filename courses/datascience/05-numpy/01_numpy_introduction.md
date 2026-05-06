# NumPy Introduction

**NumPy** stands for **Numerical Python**.

It is a Python library designed for **high-performance numerical computation** and is widely used in **data science, machine learning, and scientific computing**.

---

# Core Object

## numpy.ndarray

`ndarray` is a **multi-dimensional array object** provided by NumPy.

It allows efficient storage and manipulation of **large numerical datasets**.

---

# Basic Example

```python
import numpy as np

arr = np.array([1, 2, 3, 4])
print(arr)
```

### Output

```
[1 2 3 4]
```

---

# Why Use NumPy

| Feature | Benefit |
|-------|--------|
| Fast computation | Implemented in C |
| Memory efficient | Uses compact arrays |
| Vectorization | Avoids loops |
| Broadcasting | Automatic element-wise operations |

---

# NumPy vs Python List

| Feature | Python List | NumPy Array |
|--------|-------------|-------------|
| Speed | Slower | Faster |
| Memory Usage | Higher | Efficient |
| Mathematical Operations | Manual loops required | Built-in operations |
| Multi-dimensional Support | Difficult | Native support |

---

# Example Comparison

## Python List Example

```python
a = [1, 2, 3]
b = [4, 5, 6]

result = []

for i in range(len(a)):
    result.append(a[i] + b[i])

print(result)
```

### Output

```
[5, 7, 9]
```

---

## NumPy Example

```python
import numpy as np

a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

print(a + b)
```

### Output

```
[5 7 9]
```

---

# Key Takeaway

NumPy provides:

- Faster numerical computation
- Efficient memory usage
- Built-in mathematical operations
- Support for multi-dimensional arrays

Because of these features, NumPy is the **foundation library for Data Science and Machine Learning in Python**.