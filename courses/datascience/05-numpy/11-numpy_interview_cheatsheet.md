# NumPy Cheat Sheet (Concepts, Methods, Examples, Use Cases)

| Concept             | Method / Syntax       | Example                     | Use Case                           |
| ------------------- | --------------------- | --------------------------- | ---------------------------------- |
| Import NumPy        | `import numpy as np`  | `import numpy as np`        | Standard way to use NumPy          |
| Create Array        | `np.array()`          | `np.array([1,2,3])`         | Convert Python list to NumPy array |
| Zeros Array         | `np.zeros()`          | `np.zeros((3,3))`           | Initialize matrix with zeros       |
| Ones Array          | `np.ones()`           | `np.ones((2,2))`            | Create default matrix              |
| Identity Matrix     | `np.eye()`            | `np.eye(3)`                 | Linear algebra                     |
| Range               | `np.arange()`         | `np.arange(0,10,2)`         | Create sequences                   |
| Evenly spaced       | `np.linspace()`       | `np.linspace(0,1,5)`        | Data sampling                      |
| Random numbers      | `np.random.rand()`    | `np.random.rand(3,3)`       | Simulation                         |
| Random integers     | `np.random.randint()` | `np.random.randint(1,10,5)` | ML sampling                        |
| Normal distribution | `np.random.randn()`   | `np.random.randn(5)`        | Statistics / ML                    |

---

# Array Properties

| Concept        | Attribute  | Example        | Use Case              |
| -------------- | ---------- | -------------- | --------------------- |
| Dimensions     | `ndim`     | `arr.ndim`     | Check array dimension |
| Shape          | `shape`    | `arr.shape`    | Matrix size           |
| Total elements | `size`     | `arr.size`     | Data count            |
| Data type      | `dtype`    | `arr.dtype`    | Numerical precision   |
| Memory size    | `itemsize` | `arr.itemsize` | Memory optimization   |
| Total memory   | `nbytes`   | `arr.nbytes`   | Memory usage          |

---

# Indexing and Slicing

| Concept           | Method           | Example        | Use Case         |
| ----------------- | ---------------- | -------------- | ---------------- |
| Element access    | `arr[index]`     | `arr[0]`       | Retrieve element |
| Negative indexing | `arr[-1]`        | `arr[-1]`      | Last element     |
| 2D indexing       | `arr[row,col]`   | `arr[0,1]`     | Matrix access    |
| Slicing           | `arr[start:end]` | `arr[1:4]`     | Subset data      |
| Step slicing      | `arr[::2]`       | `arr[::2]`     | Sampling         |
| 2D slicing        | `arr[0:2,1:3]`   | `arr[0:2,1:3]` | Submatrix        |

---

# Boolean and Fancy Indexing

| Concept               | Method         | Example                         | Use Case                |
| --------------------- | -------------- | ------------------------------- | ----------------------- |
| Boolean mask          | `arr>value`    | `arr>20`                        | Filtering               |
| Boolean indexing      | `arr[arr>20]`  | `arr[arr>20]`                   | Data selection          |
| Fancy indexing        | `arr[[0,2,4]]` | `arr[[1,3]]`                    | Select multiple indices |
| Conditional selection | `np.where()`   | `np.where(arr>10,"High","Low")` | Feature engineering     |

---

# Array Manipulation

| Concept          | Method             | Example                 | Use Case          |
| ---------------- | ------------------ | ----------------------- | ----------------- |
| Reshape          | `reshape()`        | `arr.reshape(2,3)`      | Change dimensions |
| Flatten          | `flatten()`        | `arr.flatten()`         | Convert to 1D     |
| Ravel            | `ravel()`          | `arr.ravel()`           | Fast flatten      |
| Transpose        | `arr.T`            | `arr.T`                 | Swap rows/columns |
| Concatenate      | `np.concatenate()` | `np.concatenate([a,b])` | Merge arrays      |
| Vertical stack   | `np.vstack()`      | `np.vstack([a,b])`      | Stack rows        |
| Horizontal stack | `np.hstack()`      | `np.hstack([a,b])`      | Stack columns     |
| Split array      | `np.split()`       | `np.split(arr,2)`       | Divide dataset    |

---

# Mathematical Operations

| Concept        | Method          | Example            | Use Case               |
| -------------- | --------------- | ------------------ | ---------------------- |
| Addition       | `np.add()`      | `np.add(a,b)`      | Element-wise math      |
| Subtraction    | `np.subtract()` | `np.subtract(a,b)` | Data differences       |
| Multiplication | `np.multiply()` | `np.multiply(a,b)` | Element multiplication |
| Division       | `np.divide()`   | `np.divide(a,b)`   | Normalization          |
| Power          | `np.power()`    | `np.power(arr,2)`  | Squaring               |
| Square root    | `np.sqrt()`     | `np.sqrt(arr)`     | Statistics             |
| Absolute       | `np.abs()`      | `np.abs(arr)`      | Distance calculations  |

---

# Statistical Functions

| Concept            | Method            | Example                 | Use Case         |
| ------------------ | ----------------- | ----------------------- | ---------------- |
| Mean               | `np.mean()`       | `np.mean(arr)`          | Average          |
| Median             | `np.median()`     | `np.median(arr)`        | Central tendency |
| Standard deviation | `np.std()`        | `np.std(arr)`           | Data variability |
| Variance           | `np.var()`        | `np.var(arr)`           | Spread           |
| Minimum            | `np.min()`        | `np.min(arr)`           | Data range       |
| Maximum            | `np.max()`        | `np.max(arr)`           | Peak value       |
| Sum                | `np.sum()`        | `np.sum(arr)`           | Aggregation      |
| Percentile         | `np.percentile()` | `np.percentile(arr,90)` | Distribution     |


# Axis Operations

| Concept          | Method   | Example              | Use Case           |
| ---------------- | -------- | -------------------- | ------------------ |
| Column operation | `axis=0` | `np.sum(arr,axis=0)` | Column aggregation |
| Row operation    | `axis=1` | `np.sum(arr,axis=1)` | Row aggregation    |

Example:

```bash
[[1 2 3]
 [4 5 6]]
```

`axis=0 → columns`  
`axis=1 → rows`

---

# Sorting and Unique

| Concept       | Method        | Example          | Use Case          |
| ------------- | ------------- | ---------------- | ----------------- |
| Sort array    | `np.sort()`   | `np.sort(arr)`   | Ranking           |
| Unique values | `np.unique()` | `np.unique(arr)` | Remove duplicates |
| Argmax        | `np.argmax()` | `np.argmax(arr)` | Index of max      |
| Argmin        | `np.argmin()` | `np.argmin(arr)` | Index of min      |

---

# Linear Algebra

| Concept              | Method            | Example            | Use Case          |
| -------------------- | ----------------- | ------------------ | ----------------- |
| Dot product          | `np.dot()`        | `np.dot(a,b)`      | Vector math       |
| Matrix multiply      | `np.matmul()`     | `np.matmul(a,b)`   | ML algorithms     |
| Alternative multiply | `@`               | `a @ b`            | Cleaner syntax    |
| Matrix inverse       | `np.linalg.inv()` | `np.linalg.inv(a)` | Linear equations  |
| Determinant          | `np.linalg.det()` | `np.linalg.det(a)` | Matrix properties |
| Eigenvalues          | `np.linalg.eig()` | `np.linalg.eig(a)` | PCA               |

---

# Broadcasting and Vectorization

| Concept       | Method     | Example                           | Use Case       |
| ------------- | ---------- | --------------------------------- | -------------- |
| Broadcasting  | `arr + 10` | `[1,2,3]+10`                      | Efficient math |
| Vectorization | `a + b`    | `np.array([1,2])+np.array([3,4])` | Remove loops   |
|               |            |                                   |                |

Example:
```bash
[1,2,3] + 10
```
Output

```bash
[11 12 13]
```
---

# Random Module (ML & Simulation)

| Method                | Example                     | Use Case             |
| --------------------- | --------------------------- | -------------------- |
| `np.random.rand()`    | `np.random.rand(3)`         | Uniform distribution |
| `np.random.randn()`   | `np.random.randn(3)`        | Normal distribution  |
| `np.random.randint()` | `np.random.randint(1,10,5)` | Random integers      |
| `np.random.choice()`  | `np.random.choice(arr)`     | Sampling             |
| `np.random.shuffle()` | `np.random.shuffle(arr)`    | Data shuffling       |

---

# Memory and Performance

| Concept            | Method     | Example                  | Use Case           |
| ------------------ | ---------- | ------------------------ | ------------------ |
| Change datatype    | `astype()` | `arr.astype(np.float32)` | Reduce memory      |
| Copy array         | `copy()`   | `b=a.copy()`             | Independent arrays |
| View array         | `view()`   | `b=a.view()`             | Shared memory      |
| In-place operation | `+=`       | `arr+=5`                 | Faster operations  |

---

# Most Important Interview Topics

| Topic                 | Example              | Why Important        |
| --------------------- | -------------------- | -------------------- |
| ndarray               | `np.array()`         | Core object          |
| Broadcasting          | `arr+10`             | Efficient operations |
| Vectorization         | `a+b`                | Faster computation   |
| Boolean masking       | `arr[arr>10]`        | Filtering            |
| Fancy indexing        | `arr[[1,3]]`         | Selection            |
| Axis operations       | `np.sum(axis=0)`     | Aggregation          |
| Copy vs View          | `copy()` vs `view()` | Memory management    |
| Random module         | `np.random.rand()`   | ML pipelines         |
| Matrix multiplication | `a @ b`              | Linear algebra       |

---

# Typical Data Science Workflow

```text
Raw Data
   ↓
NumPy Array
   ↓
Data Cleaning
   ↓
Feature Engineering
   ↓
Machine Learning Models
```

Libraries using NumPy internally:
- Pandas
- Scikit-Learn
- TensorFlow
- PyTorch
- SciPy
- OpenCV

---

✅ This table works well as:
- NumPy quick reference
- Data science cheat sheet
- Interview preparation guide
- Documentation reference