# Valid-Parentheses
Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.  An input string is valid if:  Open brackets must be closed by the same type of brackets. Open brackets must be closed in the correct order. Every close bracket has a corresponding open bracket of the same type.

class Solution:
    def isValid(self, s):
        stack = []
        bracket_mapping = {')': '(', '}': '{', ']': '['}

        for char in s:
            if char in bracket_mapping.values():
                stack.append(char)
            elif char in bracket_mapping.keys():
                if not stack or bracket_mapping[char] != stack.pop():
                    return False
            else:
                return False

        return not stack


solution = Solution()
print(solution.isValid("()"))     
print(solution.isValid("()[]{}"))  
print(solution.isValid("(]"))      
print(solution.isValid("([)]"))   
print(solution.isValid("{[]}"))  
