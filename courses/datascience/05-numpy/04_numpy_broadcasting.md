# NumPy Broadcasting

**Broadcasting** allows NumPy to perform **operations on arrays with different shapes** without explicitly copying data.

It automatically **expands smaller arrays** so they match the shape of larger arrays during operations.

---

# Simple Example

```python
import numpy as np

a = np.array([1, 2, 3])
b = 2

print(a + b)
```

### Output

```
[3 4 5]
```

Here, the scalar `2` is **broadcasted** to match the shape of array `a`.

---

# Broadcasting Rules

NumPy follows these rules when broadcasting arrays:

1. **Dimensions must be equal**, or  
2. **One of the dimensions must be 1**, or  
3. **One array may have fewer dimensions**

If these conditions are satisfied, NumPy **automatically expands the smaller array**.

---

# Broadcasting Example

```python
import numpy as np

a = np.array([[1],
              [2],
              [3]])

b = np.array([10, 20, 30])

print(a + b)
```

### Output

```
[[11 21 31]
 [12 22 32]
 [13 23 33]]
```

Explanation:

- `a` shape → `(3,1)`
- `b` shape → `(3,)`

NumPy automatically expands `b` to match the shape of `a`.

---

# Shape Visualization

| Array | Shape |
|------|------|
| `a` | (3,1) |
| `b` | (1,3) |
| Result | (3,3) |

---

# Benefits of Broadcasting

- Reduces memory usage
- Avoids unnecessary data duplication
- Enables fast vectorized operations
- Simplifies mathematical expressions

---

# Example with Scalar Broadcasting

```python
import numpy as np

arr = np.array([1, 2, 3, 4])

print(arr * 10)
```

Output

```
[10 20 30 40]
```

The scalar `10` is automatically **broadcast across the array**.

---

# Key Takeaway

Broadcasting allows NumPy to perform **efficient element-wise operations** on arrays of different shapes without manually reshaping them.