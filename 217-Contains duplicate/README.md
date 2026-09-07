# 217. Contains Duplicate

**Difficulty:** Easy  
**Topic:** Array, Hash Set

---

## Problem

Given an integer array `nums`, return `true` if any value appears at least twice in the array.

Return `false` if every element appears only once.

### Example 1

**Input:**
`nums = [1,2,3,1]`

**Output:**
`true`

**Explanation:**  
The element `1` appears twice, at indices `0` and `3`.

### Example 2

**Input:**
`nums = [1,2,3,4]`

**Output:**
`false`

**Explanation:**  
Every element in the array is distinct.

### Example 3

**Input:**
`nums = [1,1,1,3,3,4,3,2,4,2]`

**Output:**
`true`

**Explanation:**  
Several values appear more than once.

---

## Approach

We need to check whether any number appears more than once.

A **set** is useful for this problem because a set stores only unique elements.

We create an empty set and traverse the array one element at a time.

For every number:

1. Check whether the number is already present in the set.
2. If it is already present, a duplicate has been found, so return `True`.
3. If it is not present, add it to the set.
4. If we finish checking the entire array without finding a duplicate, return `False`.

---

## Step-by-Step Explanation

Suppose:

`nums = [1,2,3,1]`

Initially, the set is empty.

### Step 1

Take `1`.

`1` is not present in the set, so add it.

Set: `{1}`

### Step 2

Take `2`.

`2` is not present in the set, so add it.

Set: `{1,2}`

### Step 3

Take `3`.

`3` is not present in the set, so add it.

Set: `{1,2,3}`

### Step 4

Take `1`.

`1` is already present in the set.

Therefore, a duplicate has been found and we return `True`.

---

## Why Use a Set?

A set stores **unique values** and provides an efficient way to check whether an element already exists.

Instead of comparing every element with every other element, we can check whether the current element is already present in the set.

The average time for searching in a set is **O(1)**.

Therefore, we can detect duplicates efficiently while traversing the array.

---

## Alternative Approach

Another possible approach is to compare the length of the original array with the length of a set created from the array.

For example:

`len(nums) != len(set(nums))`

If the lengths are different, it means some duplicate values were removed when creating the set.

However, the traversal approach is useful because it can **return immediately when a duplicate is found**, without necessarily processing the remaining elements.

---

## Complexity Analysis

### Time Complexity

**O(n)**

We traverse the array once.

Set lookup and insertion take **O(1)** on average.

Therefore, the overall time complexity is:

**O(n)**

### Space Complexity

**O(n)**

In the worst case, all elements are unique, so the set stores all `n` elements.

Therefore, the space complexity is:

**O(n)**

---

## Key Takeaway

The main idea is to use a **Hash Set to keep track of elements that have already been seen**.

Whenever we encounter an element that is already present in the set, we know that a duplicate exists.

**Pattern:** Hash Set / Duplicate Detection