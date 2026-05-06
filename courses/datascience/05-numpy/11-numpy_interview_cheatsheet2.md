# NumPy Interview Cheatsheet

A quick reference for **commonly used NumPy functions and concepts** frequently asked in **Data Science, ML, and Python interviews**.

---

# Create Arrays

```python
np.array()
np.zeros()
np.ones()
np.arange()
np.linspace()
```

| Function | Description |
|--------|-------------|
| `np.array()` | Create array from list or tuple |
| `np.zeros()` | Array filled with zeros |
| `np.ones()` | Array filled with ones |
| `np.arange()` | Array with evenly spaced values |
| `np.linspace()` | Evenly spaced values between two numbers |

---

# Shape Operations

```python
arr.reshape()
arr.flatten()
arr.T
```

| Operation | Purpose |
|----------|--------|
| `reshape()` | Change array shape |
| `flatten()` | Convert multi-dimensional array to 1D |
| `arr.T` | Transpose of matrix |

---

# Indexing

```python
arr[0]
arr[1:3]
arr[arr > 5]
```

| Type | Example |
|----|----|
| Basic indexing | `arr[0]` |
| Slicing | `arr[1:3]` |
| Boolean indexing | `arr[arr > 5]` |

---

# Mathematical Functions

```python
np.sum()
np.mean()
np.std()
np.max()
np.min()
```

| Function | Purpose |
|--------|--------|
| `np.sum()` | Sum of elements |
| `np.mean()` | Average value |
| `np.std()` | Standard deviation |
| `np.max()` | Maximum value |
| `np.min()` | Minimum value |

---

# Linear Algebra

```python
np.dot()
np.linalg.inv()
np.linalg.det()
np.linalg.eig()
```

| Function | Purpose |
|--------|--------|
| `np.dot()` | Matrix multiplication |
| `np.linalg.inv()` | Matrix inverse |
| `np.linalg.det()` | Determinant |
| `np.linalg.eig()` | Eigenvalues and eigenvectors |

---

# Random Module

```python
np.random.rand()
np.random.randint()
np.random.normal()
np.random.seed()
```

| Function              | Purpose              |
| --------------------- | -------------------- |
| `np.random.rand()`    | Random float values  |
| `np.random.randint()` | Random integers      |
| `np.random.normal()`  | Normal distribution  |
| `np.random.seed()`    | Reproducible results |

---

# Important Interview Topics

Make sure you understand these concepts clearly:

- Broadcasting
- Vectorization
- Copy vs View
- Memory efficiency
- Axis operations
- Array reshaping
- Boolean indexing

---

# Quick Tips for Interviews

- NumPy arrays are **faster than Python lists** for numerical computation.
- NumPy uses **vectorized operations** instead of loops.
- NumPy arrays are **homogeneous** (same data type).
- Broadcasting enables **operations between different shaped arrays**.