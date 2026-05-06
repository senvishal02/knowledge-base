# NumPy Memory Optimization

NumPy arrays use **fixed data types**, which makes them more **memory efficient** compared to Python lists.

Optimizing memory usage is important when working with **large datasets in Data Science and Machine Learning**.

---

## Example: Using Smaller Data Types

```python
import numpy as np

arr = np.array([1, 2, 3], dtype=np.int8)
print(arr)
```

Using smaller data types (like `int8` instead of `int64`) can **reduce memory consumption**.

---

## Copy vs View

NumPy arrays can create either **views** or **copies** of data.

### View (Shares Memory)

A **view** shares the same memory as the original array.

```python
view = arr.view()
```

Changes in the view will **affect the original array**.

---

### Copy (New Memory)

A **copy** creates a completely new array in memory.

```python
copy = arr.copy()
```

Changes in the copy **do not affect the original array**.

---

## Check Memory Usage

You can check the memory used by an array using `nbytes`.

```python
arr.nbytes
```

Example Output

```
3
```

---

## Efficient Data Types

Choosing the correct data type can significantly **reduce memory usage**.

| Data Type | Bytes per Element |
|----------|------------------|
| `int64` | 8 |
| `int32` | 4 |
| `int16` | 2 |
| `int8`  | 1 |

---

## Example: Memory Comparison

```python
import numpy as np

arr1 = np.array([1,2,3,4], dtype=np.int64)
arr2 = np.array([1,2,3,4], dtype=np.int8)

print(arr1.nbytes)
print(arr2.nbytes)
```

Output

```
32
4
```

This shows how choosing the **right dtype can drastically reduce memory usage**.

---

## Key Tips for Memory Optimization

- Use **smaller data types** when possible
- Avoid unnecessary array copies
- Use **views instead of copies**
- Monitor memory using `arr.nbytes`