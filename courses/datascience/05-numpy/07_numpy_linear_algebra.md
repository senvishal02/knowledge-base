# Linear Algebra

NumPy provides a **Linear Algebra module** for performing matrix operations.

The module used for these operations is:

```
np.linalg
```

---

## Matrix Multiplication

```python
import numpy as np

A = np.array([[1, 2],
              [3, 4]])

B = np.array([[5, 6],
              [7, 8]])

result = np.dot(A, B)

print(result)
```

### Output

```
[[19 22]
 [43 50]]
```

---

## Determinant

The determinant of a matrix can be calculated using `np.linalg.det()`.

```python
import numpy as np

A = np.array([[1, 2],
              [3, 4]])

det = np.linalg.det(A)

print(det)
```

---

## Matrix Inverse

The inverse of a matrix can be calculated using `np.linalg.inv()`.

```python
import numpy as np

A = np.array([[1, 2],
              [3, 4]])

inverse = np.linalg.inv(A)

print(inverse)
```

---

## Eigenvalues and Eigenvectors

Eigenvalues and eigenvectors can be computed using `np.linalg.eig()`.

```python
import numpy as np

A = np.array([[1, 2],
              [3, 4]])

eigenvalues, eigenvectors = np.linalg.eig(A)

print("Eigenvalues:", eigenvalues)
print("Eigenvectors:")
print(eigenvectors)
```

---

## Common Linear Algebra Functions

| Function | Description |
|--------|-------------|
| `np.dot()` | Matrix multiplication |
| `np.matmul()` | Matrix multiplication (recommended for arrays) |
| `np.linalg.det()` | Determinant of matrix |
| `np.linalg.inv()` | Inverse of matrix |
| `np.linalg.eig()` | Eigenvalues and eigenvectors |
| `np.linalg.solve()` | Solve linear equations |
| `np.linalg.norm()` | Matrix/vector norm |

---

## Example: Solving Linear Equations

```python
import numpy as np

A = np.array([[2, 1],
              [1, 3]])

B = np.array([8, 13])

solution = np.linalg.solve(A, B)

print(solution)
```