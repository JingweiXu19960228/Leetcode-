1. Right code
```
class Solution:
    def isPalindrome(self,s:str) -> bool:
        return s == s[::-1]
    
    def partition(self, s: str) -> List[List[str]]:
        if not s:
            return [[]]
        
        result = []
        for i in range(len(s)):
            if self.isPalindrome(s[:i+1]):
                for item in self.partition(s[i+1:]):
                    result.append([s[:i+1]] + item)
        return result
 ```
        
        
2. Thoughts

A palindrome (s[0:i+1]) + Sub-problem (s[i+1: end]) =. Whole-problem 

