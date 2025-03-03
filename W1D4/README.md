# Question 1

## Java program to solve subset sum problem T or F

```java
import java.util.Arrays;

class SubsetTF {

 public static void main(String[] args) {
  var a1 = new int[] { 2, 3, 5, 8, 9, 15, 21, 33 };
  var k1 = 8;
  printResult(a1, k1, hasSubset(a1, k1));
 }

 static void printResult(int[] a, int k, boolean result) {
  System.out.println("Input: " + Arrays.toString(a) + ", K=" + k);
  System.out.println("Output: " + result);
 }

 // F(i, k) = or(F(i - 1, k), F(i - 1, S[k - i])
 static boolean hasSubset(int[] a, int k) {
  boolean[] row = new boolean[k + 1];
  row[0] = true;
  for (int element : a) {
   boolean[] updatedRow = new boolean[k + 1];
   updatedRow[0] = true;
   for (int i = 1; i <= k; i++) {
    updatedRow[i] = row[i] || (i >= element && row[i - element]);
   }
   row = updatedRow;
   if (row[k])
    return true;
  }
  return row[k];
 }

}

```

## Java program to solve subset sum problem One solution

```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

class SubsetOne {
 public static void main(String[] args) {
  var a1 = new int[] { 2, 3, 5, 8, 9, 15, 21, 33 };
  var k1 = 8;
  printResult(a1, k1, findSubset(a1, k1));
 }

 static void printResult(int[] a, int k, List<Integer> result) {
  System.out.println("Input: " + Arrays.toString(a) + ", K=" + k);
  if (result == null || result.isEmpty()) {
   System.out.println("Output: No subset found");
  } else {
   System.out.println("Output: " + result);
  }
 }

 static List<Integer> findSubset(int[] a, int k) {
  // row[i] will store the subset that sums to i (null if no such subset exists)
  List<Integer>[] row = new List[k + 1];

  // Empty set sums to 0
  row[0] = new ArrayList<>();

  for (int w : a) {
   // Process in reverse to avoid using the same element multiple times
   for (int i = k; i >= w; i--) {
    // If we can form sum (i-w) and haven't yet formed sum i
    if (row[i - w] != null && row[i] == null) {
     // Create a new list with all elements from row[i-w] plus the current element
     row[i] = new ArrayList<>(row[i - w]);
     row[i].add(w);

     // If we found our target sum, return it immediately
     if (i == k) {
      return row[k];
     }
    }
   }
  }

  // Return the subset for sum k (may be null if no solution exists)
  return row[k];
 }
}

```

## Java program to solve subset sum problem All solutions

```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

class SubsetAll {
 public static void main(String[] args) {
  var a1 = new int[] { 2, 3, 5, 8, 9, 15, 21, 33 };
  var k1 = 8;
  printResult(a1, k1, findAllSubsets(a1, k1));
 }

 static void printResult(int[] a, int k, List<List<Integer>> results) {
  System.out.println("Input: " + Arrays.toString(a) + ", K=" + k);
  if (results.isEmpty()) {
   System.out.println("Output: No subsets found");
  } else {
   System.out.println("Output: Found " + results.size() + " subsets");
   for (int i = 0; i < results.size(); i++) {
    System.out.println("  Subset " + (i + 1) + ": " + results.get(i));
   }
  }
 }

 static List<List<Integer>> findAllSubsets(int[] a, int k) {
  // row[i] will store all subsets that sum to i
  List<List<Integer>>[] row = new List[k + 1];

  // Initialize each element in row
  for (int i = 0; i <= k; i++) {
   row[i] = new ArrayList<>();
  }

  // Empty set sums to 0
  row[0].add(new ArrayList<>());

  for (int w : a) {
   // Process in reverse to avoid using the same element multiple times
   for (int i = k; i >= w; i--) {
    // Check if we can form sum (i-w)
    if (!row[i - w].isEmpty()) {
     // For each existing subset that sums to (i-w)
     for (List<Integer> subset : row[i - w]) {
      // Create a new subset with the current element
      List<Integer> newSubset = new ArrayList<>(subset);
      newSubset.add(w);
      row[i].add(newSubset);
     }
    }
   }
  }

  // Return all subsets that sum to k
  return row[k];
 }
}

```

# Question 2

# Question 3

# Question 4

# Question 5

# Question 6
