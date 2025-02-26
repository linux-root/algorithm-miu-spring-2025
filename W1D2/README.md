# Lab W1D2

## Question 1: Comparing Algorithms

### Problem: Find the THIRD largest in an array

#### Algorithm 1

**Idea**: Use three loops one after another.

- First loop will find the maximum value.
- Second loop will find the second maximum value.
- Third loop will find the third maximum value.

**Note**: It is possible that the first max == second max == third max, as in the array `[7, 20, 18, 4, 20, 19, 20, 3]`. In this case, the program should return `20`.

#### Algorithm 2

**Idea**: Use one loop. Maintain three variables:

- `max`: to store the maximum value.
- `preMax`: to store the second largest value.
- `prePreMax`: to store the third largest value.

#### Algorithm 3

**Idea**: Use an ordered dictionary.

---

### Tasks for Each Algorithm

1. **Write the pseudo code** (must follow the notations and conventions used in today’s lecture).

---

## Question 2: Complexity Classes

### Problem

Consider the following functions and determine the relationships among their complexity classes:

```pseudo
10, 1, n^3, n^(1/3), log(log n), n^2, n^(1/2), log n, log n^n, n^k (k > 3), n^(1/k) (k > 3), n log n, ln n, 2^n, 3^n, n^n, n^(1/2) log n, n^(1/3) log n, n!.
```

**Notation Clarification**:

- `log(log n) = log log n ≠ log^2 n = (log n)^2`.

### Partial Table

The table is given in strict ascending order. Your task is to complete the table.

| Function | Complexity Class |
| -------- | ---------------- |
| 10       | Θ(1)             |
| 1        | Θ(1)             |
| log n    | Θ(log n)         |
| n^(1/2)  | Θ(√n)            |
| ...      | ...              |

---

### Notes

- For **Question 1**, focus on writing clear pseudo code, analyzing time complexity, and implementing the algorithms in Java for empirical comparison.
- For **Question 2**, ensure you understand the relationships between the given functions and their complexity classes. Complete the table by filling in the missing entries.

```

```
