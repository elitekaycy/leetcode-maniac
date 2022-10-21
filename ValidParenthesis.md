> [leetcode maniac](README.md) - ***home***

## Valid Parenthesis
**easy**
[Valid Parenthesis](https://leetcode.com/problems/valid-parentheses/)

Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

    1. Open brackets must be closed by the same type of brackets.
    2. Open brackets must be closed in the correct order.
    3. Every close bracket has a corresponding open bracket of the same type.

##### example 1:
    Input: s = "()"
    Output: true

##### example 2:
    Input: s = "()[]{}"
    Output: true

##### example 3:
    Input: s = "(]"
    Output: false



### My solution
>  python
>  time complexity - **O(n)**  space complexity - **O(1)**

    from collections import deque

    class Solution(object):
        def isValid(self, s):
            
            stack = deque()
            parenthesis = {
                ")" : "(",
                "}" : "{",
                "]" : "["
            }
            
            for i in s:
                if i == "(" or i == "{" or i == "[":
                    stack.append(i)
                else:
                    if len(stack) == 0:
                        return False
                    val = stack.pop()
                    if parenthesis.get(i) != val:
                        return False
            
            return True if len(stack) == 0 else False








