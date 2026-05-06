# NumPy Performance Tips

NumPy is designed for **high-performance numerical computation**.  
Following best practices can significantly improve **speed and memory efficiency**.

---

## Avoid Python Loops

Python loops are slower compared to NumPy's **vectorized operations**.

### Slow Approach (Python Loop)

```python
result = []
for i in range(len(arr)):
    result.append(arr[i] * 2)
```

### Fast Approach (NumPy Vectorization)

```python
result = arr * 2
```

---

## Use Built-in Functions

NumPy provides optimized functions implemented in **C**, which are much faster than manual implementations.

```python
np.sum()
np.mean()
np.max()
np.min()
```

Example:

```python
import numpy as np

arr = np.array([1, 2, 3, 4])

print(np.sum(arr))
print(np.mean(arr))
```

---

## Use Broadcasting

Broadcasting allows operations between arrays of **different shapes without creating extra copies**.

```python
arr = np.array([1, 2, 3])

result = arr + 5
```

Output

```
[6 7 8]
```

This avoids unnecessary array expansion.

---

## Use Correct Data Types

Choosing the right data type improves both **performance and memory usage**.

Example:

```python
arr = np.array([1, 2, 3], dtype=np.int8)
```

Smaller data types use **less memory and improve cache efficiency**.

---

## Use In-place Operations

In-place operations modify the array **without creating a new one**, improving performance.

### Inefficient

```python
arr = arr + 5
```

### Efficient

```python
arr += 5
```

---

## Summary

| Optimization Technique | Benefit |
|----------------------|--------|
| Vectorization | Faster computation |
| Built-in NumPy functions | Optimized C implementation |
| Broadcasting | Avoid extra memory usage |
| Correct data types | Lower memory footprint |
| In-place operations | Avoid unnecessary array creation |