1. My code (kind of slow)

```
class Solution:
    def findContentChildren(self, g: List[int], s: List[int]) -> int:
        g.sort()
        s.sort()
        
        num = 0
        k = -1
        for i in range(len(s)):
            cookie = s[i]
            for j in range(k+1,len(g)):
                child = g[j]
                if cookie >= child:
                    num+=1
                    k = j
                    break                    
        return num
 ```
 The outer loop is s (cookies)
 
 
 2. Online solution 
 
 ```
 
 
            
