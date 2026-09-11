# LeetCode 349 – Intersection of Two Arrays

## Problem Statement

Given two integer arrays `nums1` and `nums2`, return an array containing their **intersection**.

Each element in the result must be **unique**, and the result can be returned in any order.

### Example

**Input:**


nums1 = [1,2,2,1]
nums2 = [2,2]


Output:


[2]

### Another Example

**Input:**

```text
nums1 = [4,9,5]
nums2 = [9,4,9,8,4]
```

**Output:**

```text
[4,9]
```

---

## Approach

We can solve this problem using a **HashSet**.

### Steps

1. Store all elements of `nums1` in a `HashSet`.
2. Traverse through `nums2`.
3. If an element exists in the set, add it to the result set.
4. Since a `HashSet` stores only unique elements, duplicates are automatically removed.
5. Convert the result set into an integer array.

---

## Java Solution

```java
import java.util.*;

class Solution {
    public int[] intersection(int[] nums1, int[] nums2) {

        Set<Integer> set1 = new HashSet<>();

        for (int num : nums1) {
            set1.add(num);
        }

        Set<Integer> result = new HashSet<>();

        for (int num : nums2) {
            if (set1.contains(num)) {
                result.add(num);
            }
        }

        int[] ans = new int[result.size()];
        int i = 0;

        for (int num : result) {
            ans[i++] = num;
        }

        return ans;
    }
}
```

---

## Dry Run

### Input

```text
nums1 = [1,2,2,1]
nums2 = [2,2]
```

### Step 1

Store `nums1` in a HashSet:

```text
set1 = [1, 2]
```

### Step 2

Traverse `nums2`:

```text
2 → present → add to result
2 → present → already exists
```

Result:

```text
[2]
```

---

## Complexity Analysis

Let:

* `n` = length of `nums1`
* `m` = length of `nums2`

### Time Complexity

```text
O(n + m)
```

We traverse both arrays once on average.

### Space Complexity

```text
O(n + m)
```

The HashSets store unique elements from the arrays.

---

## Key Concepts

* Arrays
* HashSet
* Hashing
* Searching
* Removing duplicates
* Time and Space Complexity

---

## LeetCode

**Problem:** 349 – Intersection of Two Arrays

**Difficulty:** Easy

**Topic:** Array, Hash Table, Two Pointers, Binary Search

---

## Key Takeaway

Using a `HashSet` makes it easy to find the intersection while automatically handling duplicate elements.

```text
nums1 → HashSet → Check nums2 → Unique Intersection
```
