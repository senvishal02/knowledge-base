# Jupyter Notebook Cheat Sheet

Jupyter Notebook is an interactive environment used by data scientists for coding, visualization, and documentation.

---

# 1. Starting Jupyter Notebook

Start Jupyter Notebook from terminal:

```bash
jupyter notebook
```

Start using Anaconda:

```
Anaconda Navigator → Launch Jupyter Notebook
```

---

# 2. Jupyter Notebook Interface

Main components:

- Notebook Dashboard
- Code Cells
- Markdown Cells
- Kernel (Python Runtime)
- Menu Bar
- Toolbar

---

# 3. Cell Types

### Code Cell

Used to run Python code.

```python
print("Hello Data Science")
```

---

### Markdown Cell

Used for writing documentation.

Example:

```
# Heading
## Subheading
**Bold Text**
```

---

# 4. Running Cells

| Action | Shortcut |
|------|------|
| Run cell | Shift + Enter |
| Run cell without moving | Ctrl + Enter |
| Run cell and create new cell | Alt + Enter |

---

# 5. Cell Management

| Action | Shortcut |
|------|------|
| Insert cell above | A |
| Insert cell below | B |
| Delete cell | DD |
| Copy cell | C |
| Paste cell | V |
| Cut cell | X |

---

# 6. Change Cell Type

| Action | Shortcut |
|------|------|
| Convert to Code | Y |
| Convert to Markdown | M |

---

# 7. Kernel Commands

| Action | Menu |
|------|------|
| Restart Kernel | Kernel → Restart |
| Interrupt Kernel | Kernel → Interrupt |
| Restart and Run All | Kernel → Restart & Run All |

---

# 8. Saving and Exporting

| Action | Shortcut |
|------|------|
| Save notebook | Ctrl + S |

Export options:

```
File → Download As
```

Formats available:

- HTML
- PDF
- Markdown
- Python Script (.py)

---

# 9. Useful Notebook Commands

Clear all outputs:

```
Cell → All Output → Clear
```

Run all cells:

```
Cell → Run All
```

Restart kernel and run all:

```
Kernel → Restart & Run All
```

---

# 10. Magic Commands

Magic commands provide extra functionality.

### List all magic commands

```python
%lsmagic
```

---

### Measure execution time

```python
%time
sum(range(100000))
```

---

### Run external Python script

```python
%run script.py
```

---

### Display variables

```python
%who
```

---

# 11. Useful Python Examples

### Variables

```python
x = 10
y = 20
print(x + y)
```

---

### Using NumPy

```python
import numpy as np

data = np.array([1,2,3,4,5])
print(data.mean())
```

---

### Using Pandas

```python
import pandas as pd

data = {
    "Name": ["Alice", "Bob", "Charlie"],
    "Age": [25, 30, 35]
}

df = pd.DataFrame(data)
print(df)
```

---

# 12. Helpful Tips

- Use **Markdown cells** to explain your analysis.
- Keep notebooks **organized and well documented**.
- Restart the **kernel if code behaves unexpectedly**.
- Use **virtual environments** for package management.

---

# Quick Shortcut Summary

| Shortcut | Action |
|------|------|
| Shift + Enter | Run cell |
| Ctrl + Enter | Run cell without moving |
| Alt + Enter | Run cell and add new cell |
| A | Insert cell above |
| B | Insert cell below |
| DD | Delete cell |
| M | Markdown cell |
| Y | Code cell |
| Ctrl + S | Save notebook |