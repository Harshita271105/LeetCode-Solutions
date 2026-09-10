# 217. Contains Duplicate

Difficulty: Easy  
Topic: Array, Hash Table, Sorting


## Problem

Given an integer array nums, return true if any value appears at least twice in the array.
Return false if every element appears only once.

### Example 1

Input
nums = [1,2,3,1]

Output
true

Explanation
The element 1 appears twice, at indices 0 and 3

### Example 2

Input
nums = [1,2,3,4]

Output
false

Explanation
Every element in the array is distinct.

### Example 3

Input
nums = [1,1,1,3,3,4,3,2,4,2]

Output
true

Explanation
Several values appear more than once.

## Approach

The easiest way to approach this is by brute forcing.

So the first thing we do is look at the first number,its one.How do we know it is a duplicate or not?
Well we compare it to every single number in rest of the array and that would be a big O(n) of time operation just to check if the first number is a duplicate or not.Then we have to check for 2nd number , we compare it with every other number.we do the same hing with 3rd and 4th number.

So time complexity would be O(n^2) where n is just the size of array.

So brute force solution is big O(n^2) time complexity and we don't need any extra memory. So the memory complexity is big O(1). 

Space complexity would be O(1).

## Alternative Approach - 1

Another possible approach is Sorting.

Sorting the inputs then any duplocate that do exist in the array then we can clearly see in the array there are going to be adjacent.So while trying to detct any duplocates in array, we have to iterate though the array once.

As we do that, we are just going to compare two neighbours in the array, checking tif they are duplicates.
Next we are going to shift to out pointers to the next spot until we finish the entire array.

In this case we see these two adjacent values are duplicates.

The time complexity would be O(nlogn) since sorting takes extra memory,it does not take extra time complexity.

Space complexity would be O(1).

## Alternative Approach - 2

If we use hash set method we are going to allow us to insert elements into the hash set in O(1) and also allow us to us check.we can ask our hash map does that certain value exist?
If we start at the beginning pf the array, nothing is in hashmap. So, a one does not exist in the hashmap, this means there is no duplicate of it. But after we have checked if this is a duplicate, we do have to add it to our hash set because later on if we encounter a one like over here,then we determine that this is a duplicate because we know that there's already a one in our hash set. So next we're going to check two. Two is not a duplicate. Add it here. Is three a duplicate? Nope. Add it here. One. Is this a duplicate? Yep, there's a one over here. So we return true. This does contain duplicates.

Time complexily is O(n) and space complexity is O(n) so we do not end up using extra memory.

// time complexity measures how long an algorithm takes to run, while space complexity measures how much memory the algorithm uses.