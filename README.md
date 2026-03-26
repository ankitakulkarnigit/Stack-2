# Stack-2

## Problem1 Exclusive Time of Functions (https://leetcode.com/problems/exclusive-time-of-functions/)




## Problem2 Valid Parentheses (https://leetcode.com/problems/valid-parentheses/)


class Solution:
    def isValid(self, s: str) -> bool:
        seq = list(s)
        bracket_map = {"(":")", "[":"]", "{":"}"}
        parastack = []
        
        if len(seq) <= 1 or seq[0] == ")" or seq[0] == "}" or seq[0] == "]":
            return False

        for i in seq:
            if i == "(" or i == "{" or i == "[":
                parastack.append(i)
            elif len(parastack) > 0 and i == bracket_map[parastack[-1]]:
                parastack.pop()
            else:
                return False
        
        return parastack == []
