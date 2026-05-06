# NumPy Vectorization

**Vectorization** allows NumPy to perform **array operations without using explicit Python loops**.

It applies operations **element-wise across entire arrays**, making computations **faster and more efficient**.

---

# Python Loop Example

Using standard Python lists requires a loop.

```python
a = [1, 2, 3]
b = [4, 5, 6]

result = []

for i in range(len(a)):
    result.append(a[i] + b[i])

print(result)
```

Output

```
[5, 7, 9]
```

---

# NumPy Vectorized Example

NumPy performs the same operation **without loops**.

```python
import numpy as np

a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

print(a + b)
```

Output

```
[5 7 9]
```

---

# Benefits of Vectorization

| Benefit | Reason |
|--------|--------|
| Faster | Operations implemented in optimized C code |
| Cleaner | Requires less code |
| Efficient | Better memory and CPU utilization |

---

# Example: Vectorized Multiplication

```python
import numpy as np

arr = np.array([1, 2, 3, 4])

print(arr * 2)
```

Output

```
[2 4 6 8]
```

---

# Key Takeaway

Vectorization is one of the **most powerful features of NumPy**, allowing:

- Faster computation
- Cleaner code
- Efficient processing of large datasets

This is why NumPy is widely used in **Data Science, Machine Learning, and Scientific Computing**.