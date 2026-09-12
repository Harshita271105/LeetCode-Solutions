# 0049. Group Anagrams

Difficulty: Medium  
Topic: Array, Hash Table, String, Sorting

## Problem

Given an array of strings strs, group the anagrams together. You can return the answer in any order.

### Example 1

Input: strs = ["eat","tea","tan","ate","nat","bat"]
Output: [["bat"],["nat","tan"],["ate","eat","tea"]]
Explanation:There is no string in strs that can be rearranged to form "bat".
The strings "nat" and "tan" are anagrams as they can be rearranged to form each other.
The strings "ate", "eat", and "tea" are anagrams as they can be rearranged to form each other.

### Example 2

Input: strs = [""]
Output: [[""]]
Explanation: Here, the array contains only one string, and that string is empty ("").
There are no letters to rearrange, so there is nothing else that can be an anagram of it.
Therefore, we simply put the empty string into its own group.

### Example 3

Input: strs = ["a"]
Output: [["a"]]
Explanation:Again, there is only one string.
The string is "a" and there are no other strings to compare it with.
So "a" forms its own group.

## Contrains
1 <= strs.length <= 104
0 <= strs[i].length <= 100
strs[i] consists of lowercase English letters.

## Approach

one way would be taking the strings in the input and swap them but the time complexity would be O(m.nlogn) where n is average of each input string and m is m times we would do this, how many input strings are given (length of input string).

## Alternative Approach - 1

Another possible approach is using hashmap.

we have the given words in lowercasee from a to z, so in hashmap we would keep the key as 1->a , 1->e, 1->t and values would be how many words are made using these 1 a, 1 e and 1 t.we would then group them together since at last we are doing is counting of each characters.

The time complexity would be O(m.n.26) where m is total number in input string given and n is average length of string because we have to count how many of each character has it and we are counting in this arrau=y in out hashmap,we would need to multiply by 26.but we know this reduces so it becomes O(m.n) 

