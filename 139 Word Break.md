1. Wrong code

```
class Solution:
    
    def wordBreak(self, s: str, wordDict: List[str]) -> bool:
        
        def helper(s,wordDict):
            if s in wordDict:
                return True
            else:
                return False
            
        if helper(s,wordDict):
            return True
        
        status = False   

        for i in range(len(s)):
            if helper(s[:i+1],wordDict):
                status = status or self.wordBreak(s[i+1:],wordDict)
                
        return status
```
Not sure if this code is correct or not. At least, it exceeds time limit in Leetcode. I myself falied to figure out how to store previous values.

2. Right code:

```
class Solution:    
    def wordBreak(self, s: str, wordDict: List[str]) -> bool:
        L = len(s)+1
        dp = [False for i in range(L+1)]
        dp[0] = True
        
        for i in range(1,L+1):
            for j in range(i):
                if s[j:i] in wordDict and dp[j]:
                    dp[i] = True
                    
        return dp[-1]
```
        
        
 Be careful about the indexing! (i and j), and corner cases
