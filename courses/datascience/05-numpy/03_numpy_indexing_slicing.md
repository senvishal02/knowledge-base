# NumPy Indexing and Slicing

Indexing and slicing allow you to **access or modify elements in NumPy arrays** efficiently.

---

# 1D Indexing

Access elements from a **1D array** using their index.

```python
import numpy as np

arr = np.array([10, 20, 30])

print(arr[0])   # first element
print(arr[-1])  # last element
```

---

# 2D Indexing

Access elements in **multi-dimensional arrays** using row and column indexes.

```python
import numpy as np

arr = np.array([[1, 2, 3],
                [4, 5, 6]])

print(arr[0, 1])
```

Output

```
2
```

---

# Slicing

Slicing allows extracting a **range of elements**.

```python
import numpy as np

arr = np.array([1, 2, 3, 4, 5])

print(arr[1:4])
```

Output

```
[2 3 4]
```

---

# Step Slicing

You can specify **step size** in slicing.

```python
arr = np.array([1, 2, 3, 4, 5])

print(arr[::2])
```

Output

```
[1 3 5]
```

---

# Boolean Indexing

Boolean indexing allows filtering arrays based on conditions.

```python
import numpy as np

arr = np.array([10, 20, 30, 40])

print(arr[arr > 20])
```

Output

```
[30 40]
```

---

# Fancy Indexing

Fancy indexing allows selecting **multiple elements using index lists**.

```python
import numpy as np

arr = np.array([10, 20, 30, 40])

print(arr[[0, 2, 3]])
```

Output

```
[10 30 40]
```

---

# 2D Slicing

Extract specific rows and columns from a 2D array.

```python
import numpy as np

arr = np.array([[1,2,3],
                [4,5,6],
                [7,8,9]])

print(arr[0:2, 1:3])
```

Output

```
[[2 3]
 [5 6]]
```

---

# Full Slicing

Use `:` to select **entire rows or columns**.

```python
arr[:, 1]   # second column
arr[1, :]   # second row
```

---

# Using np.where()

`np.where()` returns indexes where a condition is true.

```python
import numpy as np

arr = np.array([10, 20, 30, 40])

print(np.where(arr > 20))
```

Output

```
(array([2, 3]),)
```

---

# Key Takeaways

- Indexing retrieves **specific elements**
- Slicing extracts **subsets of arrays**
- Boolean indexing filters **data based on conditions**
- Fancy indexing allows selecting **multiple positions**
- `np.where()` helps locate elements matching conditions