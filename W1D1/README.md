# W1D1

## Learn and Repeat

### Exercise 1

An array is defined to be a **235 array** if the number of elements divisible by 2 plus the number of elements divisible by 3 plus the number of elements divisible by 5 plus the number of elements not divisible by 2, 3, or 5 is equal to the number of elements of the array.

Write a method named `is123Array` that returns `1` if its array argument is a **235 array**, otherwise it returns `0`.

**Note:** A number can be divisible by more than one number. For example, `10` is divisible by both `2` and `5`.

---

## Algorithm 3: Counting Method

```pseudo
function is235Array(a):

    total <- 0
    for i <- 0 to n – 1 do

        if (a[i] % 2 == 0) then
            total <- total + 1

        if (a[i] % 3 == 0) then
            total <- total + 1

        if (a[i] % 5 == 0) then
            total <- total + 1

        if (a[i] % 2 != 0 && a[i] % 3 != 0 && a[i] % 5 != 0) then
            total <- total + 1

    return (total == n) ? 1 : 0
```

## Algorithm 4: Test the Opposite Condition Method

```pseudo
function is235Array(a):
    for i <- 0 to n – 1 do
        if (a[i] % 6 == 0 || a[i] % 10 == 0 || a[i] % 15 == 0) then
            return 0

    return 1
```

## Performance Analysis

| Case             | Algorithm 3 | Algorithm 4 |
| ---------------- | ----------- | ----------- |
| **Best Case**    | O(n)        | O(1)        |
| **Average Case** | O(n)        | O(n)        |
| **Worst Case**   | O(n)        | O(n)        |
