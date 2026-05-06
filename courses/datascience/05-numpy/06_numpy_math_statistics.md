# NumPy Math and Statistics

NumPy provides many **mathematical and statistical functions** that operate efficiently on arrays.

These functions are optimized and implemented in **C**, making them much faster than manual Python calculations.

---

# Mathematical Functions

```python
import numpy as np

arr = np.array([1, 4, 9, 16])

print(np.sqrt(arr))
```

### Output

```
[1. 2. 3. 4.]
```

---

# Common Mathematical Functions

| Function | Purpose |
|--------|--------|
| `np.add()` | Addition |
| `np.subtract()` | Subtraction |
| `np.multiply()` | Multiplication |
| `np.divide()` | Division |
| `np.power()` | Exponentiation |
| `np.sqrt()` | Square root |
| `np.exp()` | Exponential |
| `np.log()` | Natural logarithm |

---

# Statistical Functions

NumPy also provides many statistical operations.

```python
import numpy as np

arr = np.array([10, 20, 30, 40])

print(np.mean(arr))
print(np.std(arr))
```

### Output

```
25.0
11.180339887498949
```

---

# Common Statistical Functions

| Function | Purpose |
|--------|--------|
| `np.sum()` | Sum of elements |
| `np.mean()` | Average value |
| `np.median()` | Median value |
| `np.std()` | Standard deviation |
| `np.var()` | Variance |
| `np.max()` | Maximum value |
| `np.min()` | Minimum value |
| `np.argmax()` | Index of maximum value |
| `np.argmin()` | Index of minimum value |

---

# Axis Operations

Axis operations allow calculations **row-wise or column-wise** in multi-dimensional arrays.

```python
import numpy as np

arr = np.array([[1, 2, 3],
                [4, 5, 6]])

print(np.sum(arr, axis=0))  # Column-wise sum
print(np.sum(arr, axis=1))  # Row-wise sum
```

### Output

```
[5 7 9]
[ 6 15]
```

| Axis | Meaning |
|-----|--------|
| `axis=0` | Column operation |
| `axis=1` | Row operation |

---

# Cumulative Functions

Cumulative functions calculate running totals.

```python
import numpy as np

arr = np.array([1, 2, 3, 4])

print(np.cumsum(arr))
print(np.cumprod(arr))
```

Output

```
[ 1  3  6 10]
[ 1  2  6 24]
```

| Function | Purpose |
|--------|--------|
| `np.cumsum()` | Cumulative sum |
| `np.cumprod()` | Cumulative product |

---

# Universal Functions (ufuncs)

NumPy provides **Universal Functions (ufuncs)** that perform **element-wise operations** on arrays.

### Examples

```
np.sqrt()   # Square root
np.exp()    # Exponential
np.log()    # Natural logarithm
np.sin()    # Sine
np.cos()    # Cosine
np.tan()    # Tangent
```

### Example

```python
import numpy as np

arr = np.array([1, 2, 3])

print(np.sqrt(arr))
print(np.exp(arr))
```

---

# Key Takeaway

NumPy mathematical and statistical functions provide:

- Fast numerical calculations
- Built-in statistical analysis
- Efficient multi-dimensional operations
- Element-wise vectorized computation