# 0001. Two Sum

Difficulty: Easy  
Topic: Junior, Array, Hash Table

## Problem

You are given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.
You can return the answer in any order.

## Example 1:

Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].

## Example 2:

Input: nums = [3,2,4], target = 6
Output: [1,2]
Explanation: Because nums[1] + nums[2] == 6 , we return [1,2]

## Example 3:

Input: nums = [3,3], target = 6
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 6 , we return [0,1]

## Constrains

2 <= nums.length <= 104
-109 <= nums[i] <= 109
-109 <= target <= 109
Only one valid answer exists.
 
Follow-up: Can you come up with an algorithm that is less than O(n2) time complexity?
 
## Approach

check every combination of 2 values to the target.starting with 2 , we make every combinagion with 2 and check. keep repeating until we get out target.
time complexity for the worst case would be O(n^2) and best case would be O(n).

## Alternative Approach - 1

we look at our very first number from the array and target, find out the difference between them and look for that number in the array, so we don;t have to check every numbers.
looking at example 1 , our first number is 2 from array and our target is 9, heance we find the difference between them which is 7 and look for 7 in the array.

## Alternative Approach - 2

using hashmap, we would be mapping each value to the index of each value. so the index of 2 is 0 , index of 1 is 1, index of 5 is 2 and index of 3 is 3.
now we could see our target which is 4, now at index 0 is 2, so 4-2=2, now we search for 2 in the array, it isn't present hence we in our hashmap we write 0->2, and we to next number. 
coming on to index 3 which is 3, 4-3=1, now we search for 1 in the array, it is present hence it satisfies our problem of finding our target [1,3].

time complexity is O(n) and since we are using extra memory so memory complexity is O(n) because we can potentially add every value to hashmap.
