# 0347. Top K Frequent Elements

Difficulty: Medium
Topic: Array, Hash Table, Divide and Conquer, Sorting, Heap (Priority Queue), Bucket Sort, Counting, Quickselect

## Problem

Given an integer array nums and an integer k, return the k most frequent elements. You may return the answer in any order.

## Example 1:

Input: nums = [1,1,1,2,2,3], k = 2
Output: [1,2]
Explanation: the most frequent elements to occur are 1 and 2 appearing 3 and 2 times, when compared to 3 which occuring only once.

## Example 2:

Input: nums = [1], k = 1
Output: [1]
Explanation: since there is only 1 element in the array, the most frequent number will that number only ,1 occuring once.

## Example 3:

Input: nums = [1,2,1,2,1,2,3,1,3,2], k = 2
Output: [1,2]
Explanation: here the most frequent elements to occur are 1 and 2 each occuring for 4 times, when to compared to 3 which is occuring twice only.

## Constrains
1 <= nums.length <= 105
-104 <= nums[i] <= 104
k is in the range [1, the number of unique elements in the array].
It is guaranteed that the answer is unique.

Follow up: Your algorithm's time complexity must be better than O(n log n), where n is the array's size.
 
## Approach

one approach could be arranging them according to how many times each element is occuring and arrange them in ascending order. like in example 1, 1->3, 2->2, 3->1 arranging the number of times appering in ascending order we get 1,2,3...so the most frequent to occur is 3 and 2 hence element 1 and 2.

Time complexity is O(nlogn) would be the worst case, if every value here was distinct.

## Alternative Approach - 1

Another approach is maxheap, we would still perform the above approach and count the number of occurence and add to our max heap, the key of the max heap would be number of occurences, and then we pop from our heap for k times.adding would be called heapify for linear time with O(n) and we know we are going to popping off from the heap k times, each pop is going to take logn, so it will be O(k.logn).

## Alternative Approach - 2

Another approach is bucket sort.
we would be arranging index in first row and values in second row, index would be the length of the input array and values would be how many times each element is occuring, suppose in 1st example 1 is occuring 3 times so at index 3, 1 would be placed, index 2, 2 would be placed and at index 1, 3 would be placed. looking the values row, we can see that 3 and 2 are most frequent occuring, the answer would be [1,2].