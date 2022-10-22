> [leetcode maniac](README.md) - ***home***

## Best Time to Buy and Sell Stock
**easy**
[Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)

Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.

##### example 1:
    Input: nums = [1,2,3,1]
    Output: true

##### example 2:
    Input: nums = [1,2,3,4]
    Output: false


##### example 3:
    Input: nums = [1,1,1,3,3,4,3,2,4,2]
    Output: true



### My solution
>  python
>  time complexity - **O(n)**  space complexity - **O(1)**

    class Solution(object):
        def containsDuplicate(self, nums):
            lookup_dict = {}
            
            for x in nums:
                if lookup_dict.get(x) is not None:
                    return True
                else:
                    lookup_dict[x] = str(x)
                    
            return False








