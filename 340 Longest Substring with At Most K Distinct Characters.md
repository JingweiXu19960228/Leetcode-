1. Right code

```
class Solution:
    def lengthOfLongestSubstringKDistinct(self, s: str, k: int) -> int:
        
        n = len(s)
        if n*k == 0:
            return 0
        
        d = collections.defaultdict()
        
        left = 0
        right = 0
        
        res = 0
        while right<n:
            d[s[right]] = right
            right+=1
            
            if len(d)==k+1:
                ind = min(d.values())
                del d[s[ind]]
                left = ind+1
            res = max(res, right-left)
        
        return res
 ```
 
 2. Thoughts
 
 (1). The key is to find which index should the left pointer move to ('ind+1' in the code)
 
 (2). It has to be the leftmost index among all occurrences of letters 
                
