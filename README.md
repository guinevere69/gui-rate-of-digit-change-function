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
---
## Example values

$D(12)$ = 1.0,
$D(90909)$ = 9.0,
$D(111111)$ = 0.0

---

## Motivation

While related functions such as A297330 measure the total digit variation, `D(n)` normalizes this measure by the number of digit transitions, producing a mean rate of change.  
This allows comparisons between numbers of different lengths and provides a basis for digit-based randomness and complexity analysis.

---

## Related Work and Extensions
- `A297330`: Total sum of digit variations.  
- `A004216`: Number of digits in n.  
- `R(n)`: A variance-based extension of D(n) capturing irregularity in digit transitions.  

---

## Applications
- Measuring numerical irregularity or randomness in integers.  
- Classifying numbers based on rate of digit change.  
- Teaching examples for absolute difference, normalization, and mean functions.  
- Basis for exploring digit dynamics or pseudo-randomness in base-10 representations.

---

## License
This project is licensed under the [Creative Commons Attribution 4.0 International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

---
