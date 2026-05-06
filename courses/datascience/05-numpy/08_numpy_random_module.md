# NumPy Random Module

The **NumPy Random module** is used for generating **random numbers and random arrays**.

It is widely used in:

- Machine Learning
- Simulations
- Data Sampling
- Statistical Modeling

---

## Generate a Random Number

```python
import numpy as np

np.random.rand()
```

Returns a **random float between 0 and 1**.

Example Output

```
0.3745401188473625
```

---

## Generate a Random Array

```python
import numpy as np

np.random.rand(3, 3)
```

Creates a **3×3 array of random values** between `0` and `1`.

Example Output

```
[[0.37 0.95 0.73]
 [0.59 0.15 0.15]
 [0.05 0.86 0.60]]
```

---

## Generate Random Integers

```python
import numpy as np

np.random.randint(1, 10, 5)
```

Generates **5 random integers between 1 and 10**.

Example Output

```
[3 7 2 9 5]
```

---

## Normal Distribution

```python
import numpy as np

np.random.normal(0, 1, 10)
```

Generates **10 random numbers from a normal (Gaussian) distribution**.

Parameters:

- `0` → Mean  
- `1` → Standard deviation  
- `10` → Number of samples

---

## Set Random Seed

```python
import numpy as np

np.random.seed(42)
```

Setting a seed ensures **reproducible results**.

Example:

```python
np.random.seed(42)
print(np.random.rand(3))
```

Running the code again will produce the **same random numbers**.

---

## Common Random Functions

| Function | Purpose |
|--------|--------|
| `np.random.rand()` | Random float values (0–1) |
| `np.random.randn()` | Random values from normal distribution |
| `np.random.randint()` | Random integers |
| `np.random.normal()` | Normal distribution |
| `np.random.choice()` | Random selection from array |
| `np.random.seed()` | Reproducible results |

---

## Example: Random Selection

```python
import numpy as np

arr = [10, 20, 30, 40]

np.random.choice(arr)
```