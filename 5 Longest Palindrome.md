1. Wrong code (unfinished)

class Solution:
    def longestPalindrome(self, s: str) -> str:
        @functools.lru_cache(None)
        def isPalindrome(s:str)-> bool:
            if len(s)==1:
                return True
            if len(s)==2:
                if s[0]==s[1]:
                    return True
            else:
                return False
            return isPalindrome(s[1:len(s)-1]) and s[0]==s[-1]
        
        for i in range(len(s)):
            for j in range(i,len(s)):
                if isPalindrome(s[i:j]):
