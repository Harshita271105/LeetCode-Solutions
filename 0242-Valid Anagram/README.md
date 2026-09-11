# 0242. Valid Anagram

Difficulty: Easy  
Topic: String, Hash Table, Sorting


## Problem

Given two strings s and t, return true if t is an anagram of s, and false otherwise.

//An anagram is a word or phrase formed by rearranging the letters of a different word or phrase, using all the original letters exactly once.

## Example 1:

Input: s = "anagram", t = "nagaram"
Output: true
Explanation: all the letters of string s are used once in string t.

## Example 2:

Input: s = "rat", t = "car"
Output: false
Explanation: all the letters of string s are not used in string t.Like letter t from string s is not being used is string t.

## Constrains
1 <= s.length, t.length <= 5 * 104
s and t consist of lowercase English letters.
 

## Approach

Using 2 hashmap ,one for each string and key value in the hashmap is going to be character.so,in a string s,there are 3 a's, n,g,r,m as 1 and we know that string t as same as string s. so, at the end we can see that they are exact same hashmap.once we have built these hashmap,we can then go through the keys and then compare that the counts for each character are the exact same which in this case,yes it is. After comparison,we know that they are anagrams.

Time complexity is O(n) since we are going to iterate both the strings ,the memory complexity is the same O(s+t), the sixe of string s and t and would some extra memory.

## Alternative Approach

## How can u make a solution where we don't need extra memory?Can you do it with O(1) memory?

If you took all these characters and put them in a hashmap where we can count the occurence, then its preety easy to check if they equal, but isn't there any other way?
What if we made sure that the characters show up in the exact same order every single time? What do we mean by order?

One possible way would be sorted order. Because if they're if they really are the exact same characters,then if we put them in sorted order,then they should actually become the exact same string. Then we can literally just do an equals operation on both of the sorted strings and guarantee that they're going to be equal.

Time complexity would ne O(n^2) and the worst case could be O(nlogn) and space complexity would be O(n) which uses extra memory.