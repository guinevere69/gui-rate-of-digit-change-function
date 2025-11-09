# Gui Rate of Digit Change Function

This repository introduces **D(n)**, a mathematical function defining the **mean absolute rate of digit change** between consecutive digits of an integer.  
It also explores related variance-based metrics such as **R(n)** for measuring numerical digit irregularity.

---

## Definition

Let $n$ have decimal digits $d_1, d_2, ..., d_L$.

Define

$$
D(n) = \frac{1}{L-1} \sum_{i=1}^{L-1} |d_{i+1} - d_i|,
$$

with $D(n)$ = 0 if $L$ = 1.
---

## Python Implementation

```python
def D(n):
    s = str(n)
    m = len(s) - 1
    if m <= 0:
        return 0.0
    total = sum(abs(int(s[i+1]) - int(s[i])) for i in range(m))
    return (total / m)
```
## Example values

$D(12)$ = 1.0
$D(90909)$ = 9.0
$D(111111)$ = 0.0
