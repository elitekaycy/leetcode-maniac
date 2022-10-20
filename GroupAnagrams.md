> [leetcode maniac](README.md) - ***home***

## Group Anagrams
**medium**
[leetcode anagram question](https://leetcode.com/problems/group-anagrams/)

Given an array of strings strs, group the anagrams together. You can return the answer in any order.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

##### example 1:
    Input: strs = ["eat","tea","tan","ate","nat","bat"]
    Output: [["bat"],["nat","tan"],["ate","eat","tea"]]

##### example 2:
    Input: strs = [""]
    Output: [[""]]

##### example 3:
    Input: strs = ["a"]
    Output: [["a"]]



### My solution
> python
>  time complexity - **O(n)**  space complexity - **O(n)**

    class Solution(object):
        def groupAnagrams(self, strs):
            lookup_dict = {}
            res = []
            
            if len(strs) == 0: return [[""]]
            if len(strs) == 1: return [strs]
            
            for word in strs:
                sorte = sorted(word)
                if lookup_dict.get(str(sorte)) is not None:
                    lookup_dict[str(sorte)].append(str(word))
                else:
                    lookup_dict[str(sorte)] = [str(word)]
                    
            for keys in lookup_dict:
                res.append(lookup_dict.get(keys))
            
            return res








