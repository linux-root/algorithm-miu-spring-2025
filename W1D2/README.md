# Lab W1D2

## Question 1: Comparing Algorithms

### Problem: Find the THIRD largest in an array

#### Algorithm 1

**Idea**: Use three loops one after another.

- First loop will find the maximum value.
- Second loop will find the second maximum value.
- Third loop will find the third maximum value.

```pseudo
Algorithm findThirdLargest(a, n)
  Input array a of integers with length >= 3, n : length of the array
  Output integer p of third largest number in array a

  start <- 0
  for start <- 0 to 2 then #Fixed 3 loops
     max <- a[start]
     for i <- (start + 1) to (n - 1) do
        if (a[i] > max) then
           max <- a[i]
           a[start] <- a[start] + a[i]
           a[i] <- a[start] - a[i]
           a[start] <- a[start] - a[i]

  return a[2]
```

**Note**: It is possible that the first max == second max == third max, as
in the array `[7, 20, 18, 4, 20, 19, 20, 3]`. In this case,
the program should return `20`.

#### Algorithm 2

**Idea**: Use one loop. Maintain three variables:

- `max`: to store the maximum value.
- `preMax`: to store the second largest value.
- `prePreMax`: to store the third largest value.

```pseudo
Algorithm findThirdLargest(a, n)
  Input array a of integers with length >= 3, n : length of the array
  Output integer p of third largest number in array a

     max <- a[0]
     preMax <- -1
     prePreMax <- -1

     for i <- 1 to n - 1 do
        if (a[i] > prePreMax) && (a[i] < preMax) then
           prePreMax <- a[i]
        else if (a[i] > preMax && a[i] < max) then
           prePreMax <- preMax
           preMax = a[i]
        else if (a[i] > max) then
           prePreMax <- preMax
           preMax <- max
           max <- a[i]

     return prePreMax
```

#### Algorithm 3

**Idea**: Use an ordered dictionary.

```pseudo
Algorithm findThirdLargest(a, n)
  Input array a of integers with length >= 3, n : length of the array
  Output integer p of third largest number in array a
     orderedDict <- [] # Ordered in descending order

     for i <- 1 to n - 1 do
        orderedDict <- orderDict + a[i]
        if (orderedDict.length > 3){
          orderedDict.dropLast()
        }

     return orderedList.getLast()
```

---

### Tasks for Each Algorithm

1. **Write the pseudo code** (must follow the notations and conventions used in today’s lecture).

---

## Question 2: Complexity Classes

### Problem

Consider the following functions and determine the relationships among their complexity classes:

```pseudo
10, 1, n^3, n^(1/3), log(log n), n^2, n^(1/2), log n, log n^n,
n^k (k > 3), n^(1/k) (k > 3), n log n, ln n, 2^n,
3^n, n^n, n^(1/2) log n, n^(1/3) log n, n!.
```

**Notation Clarification**:

- `log(log n) = log log n ≠ log^2 n = (log n)^2`.

### Partial Table

The table is given in strict ascending order. Your task is to complete the table.

| Function            | Complexity Class |
| ------------------- | ---------------- |
| 10, 1               | Θ(1)             |
| log(log n) | Θ(log(logn))  |
| log n,  ln n | Θ(log n)         |
| nlog n,              | Θ(nlogn)            |
| n^(1/k)  (k > 3)           | Θ(?)             |
| n^(1/3)             | Θ(?)             |
| n^(1/2)             | Θ(?)             |
| n^(1/2) log n, n^(1/3)log n             | Θ(?)             |
| n^2, n^3, n^k (k >3)            | Θ(n^k)             |
| 2^n, 3^n            | Θ(k^n)             |
| n!            | Θ(n!)             |
| n^n                 | Θ(n^n)             |

---

### Notes

- For **Question 1**, focus on writing clear pseudo code, analyzing time complexity, and implementing the algorithms in Java for empirical comparison.
- For **Question 2**, ensure you understand the relationships between the given functions and their complexity classes. Complete the table by filling in the missing entries.
