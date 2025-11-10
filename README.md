**Author**: Zhenxuan Gui
# Gui Rate of Digit Change Function

This repository introduces **$D(n)$**, a mathematical function defining the **mean absolute rate of digit change** between consecutive digits of an integer.  
It also explores related variance-based metrics such as **$R(n)$** for measuring numerical digit irregularity.

---

## Definition

Let $n$ have numerical digits $d_1, d_2, ..., d_L$.

Define

$$
D(n) = 
\begin{cases}
0, & \text{if } L = 1\\ 
\frac{1}{L-1} \sum_{i=1}^{L-1} |d_{i+1} - d_i|, & \text{if } L \ge 2
\end{cases}
$$



---

## Python Implementation of $D(n)$

```python
def D(n):
    s=str(n)
    total = 0
    if len(s) == 1:
        return 0
    for i in range(len(s)-1):
        total += abs(int(s[i+1])-int(s[i]))
    return (total/(len(s)-1))
```
---
## Example values of $D(n)$

$D(12)$ = $1.0$,
$D(90909)$ = $9.0$,
$D(111111)$ = $0.0$

---

## Concept

While related functions such as A297330 measure the total digit variation, $D(n)$ normalizes this measure by the number of digit transitions, producing a mean rate of change.  
This allows comparisons between numbers of different lengths and provides a basis for digit-based randomness and complexity analysis.

---

## Related Work
- `A297330`: Total sum of digit variations.  
- `A004216`: Number of digits in n.  

---

## Extension
- $R(n)$: A variance-based extension of $D(n)$ capturing irregularity in digit transitions.

$R(n)$ is calculated from:

$$
R(n) = 
\begin{cases}
0, & \text{if } L \le 2 \\
\sqrt{\frac{1}{L - 1} \sum_{i=1}^{L - 1} \left( \left| d_{i+1} - d_i \right| - D(n) \right)^2 }, & \text{if } L \ge 3
\end{cases}
$$

---

## Python Implementation of $R(n)$

```python
def R(n):
    variance = 0
    k=str(n)
    if len(k) == 1:
        return 0
    for i in range(len(k)-1):
        variance += (abs(int(k[i+1])-int(k[i]))-D(n))**2
    return math.sqrt(variance/(len(k)-1))
```
---

## Example values of $R(n)$

$R(100)$ = $0.5$,
$R(12345)$ = $0.0$,
$R(390475)$ = $2.4819347291981715$


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
